---
title: Развертывание веб-загружаемых клиентов в Skype для бизнеса Server
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: Сводка. Развертывание приложения Skype для бизнеса Web App и Skype собраний, используемой с Skype для бизнеса.
ms.openlocfilehash: c262ab4e9180ae9e02bc899793437a86ffe12ead
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761597"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Развертывание веб-загружаемых клиентов в Skype для бизнеса Server

**Сводка:** Развертывание Skype для бизнеса 2015 г. и Skype собраний, используемой с Skype для бизнеса Server.

Skype для бизнеса Web App является веб службы IIS(IIS) веб-клиентом, который устанавливается на сервере с Skype для бизнеса Server и по умолчанию развертывается по требованию для встреч с пользователями, у которых еще нет Skype для бизнеса клиента. Эти пользователи собраний чаще всего не подключаются из-за вашей сети. Всякий раз, когда пользователь щелкает URL-адрес собрания, но не установлен клиент Skype для бизнеса, ему будет представлена возможность присоединиться к собранию с помощью последней версии Skype для бизнеса Web App, Skype Meetings App или Skype для бизнеса на Mac.

Функции голосового, видео и общего доступа Skype для бизнеса Web App требуют управления microsoft ActiveX, который используется в качестве плагина в браузере пользователя. Вы можете либо установить элемент управления ActiveX, либо разрешить пользователям устанавливать его при первом использовании Skype для бизнеса Web App или при первом доступе к функции, требуемой ActiveX управления.

> [!NOTE]
> В Skype для бизнеса Server развертывании Edge Server для доступа клиентов требуется обратный прокси HTTPS в сети периметра Skype для бизнеса Web App. Вам также нужно опубликовать простые URL-адреса. Подробные сведения см. [в материале Настройка обратных](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers) прокси-серверов и DNS-требований к простым URL-адресам [в Skype для бизнеса Server.](../../plan-your-deployment/network-requirements/simple-urls.md)

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Включить многофакторную проверку подлинности для Skype для бизнеса Web App
<a name="MFA"> </a>

Skype для бизнеса Web App, Skype и Skype для бизнеса на Mac поддерживают многофакторную проверку подлинности. Помимо имени пользователя и пароля, вам могут потребоваться дополнительные методы проверки подлинности, такие как смарт-карты или ПИН-коды, для проверки подлинности пользователей, присоединявшихся к внешним сетям при входе на Skype для бизнеса собрания. Можно включить многофакторную проверку подлинности, развернув сервер федерации Active Directory Federation Service (AD FS) и включив пассивную проверку подлинности в Skype для бизнеса Server. После настройки AD FS внешние пользователи, пытаемые присоединиться к Skype для бизнеса собраниям, будут представлены веб-страницей многофакторной проверки подлинности AD FS, содержаной имя пользователя и пароль, а также любые дополнительные методы проверки подлинности, которые вы настроили.

> [!IMPORTANT]
> Если вы планируете настроить службу федерации Active Directory для многофакторной проверки подлинности, учтите следующие рекомендации.

- Многофакторная проверка подлинности ADFS работает, если участник и организатор собрания находятся в одной организации или оба из федераированной организации AD FS. Многофакторная проверка подлинности ADFS не работает для федерационных пользователей Lync, так как веб-инфраструктура сервера Lync в настоящее время не поддерживает ее.

- Если вы используете балансиры нагрузки оборудования, в используйте сохранение файлов cookie на балансире нагрузки, чтобы все запросы от клиентов приложения Skype для бизнеса Web App или Meetings App обрабатывались с помощью одного и того же переднего сервера.

- Если вы устанавливаете доверительные отношения между Skype для бизнеса Server и серверами AD FS, назначьте срок службы маркера, достаточный для максимальной продолжительности Skype для бизнеса собраний. Как правило, 240 минут бывает достаточно.

- Эта конфигурация не применяется к мобильным клиентам Lync.

### <a name="configure-multi-factor-authentication"></a>Настройка многофакторной проверки подлинности

1. Установите роль сервера федерации службы федерации Active Directory. Сведения см. в руководстве по развертыванию [Active Directory Federation Services 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))

2. Создание сертификатов для AD FS. Дополнительные сведения см. в разделе ["Сертификаты](/previous-versions/azure/azure-services/jj205462(v=azure.100)) сервера Федерации" в разделе Plan for and deploy AD FS for use with single sign-on topic.

3. Из интерфейса Windows PowerShell командной строки запустите следующую команду:

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. Установите отношение доверия, выполнив следующую команду.

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. Настройте правила проверяющей стороны.

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>Отключение BranchCache
<a name="MFA"> </a>

Функция BranchCache в Windows 7 и Windows Server 2008 R2 может мешать Skype для бизнеса Web App веб-компонентам. Чтобы предотвратить проблемы для Skype для бизнеса Web App пользователей, убедитесь, что BranchCache не включен.

Сведения об отключении BranchCache см. в руководстве по развертыванию [BranchCache.](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)

## <a name="verifying-skype-for-business-web-app-deployment"></a>Проверка Skype для бизнеса Web App развертывания
<a name="MFA"> </a>

С помощью командлета Test-CsUcwaConference вы можете проверить возможность участия двух тестовых пользователей в конференции с использованием веб-интерфейса API объединенных коммуникаций (UCWA). Подробные сведения об этом комлете см. в документации [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) Skype для бизнеса Server Management Shell.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Устранение неполадок установка подключаемого подключения Windows Server 2008 R2
<a name="MFA"> </a>

Если установка подключаемого плагина не работает на компьютере с Windows Server 2008 R2, может потребоваться изменить параметр безопасности Internet Explorer или параметр параметра реестра DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Изменение параметра безопасности в Internet Explorer

1. Откройте Internet Explorer.

2. В меню **Сервис** выберите пункт **Свойства обозревателя** и перейдите на вкладку **Дополнительно**.

3. Перейдите к разделу **Безопасность**.

4. Снимите флажок **Не сохранять зашифрованные страницы на диск** и нажмите кнопку **ОК**.

    > [!NOTE]
    > При выборе этого параметра также может быть допущена ошибка при попытке скачать вложение из Skype для бизнеса Web App.

5. Присоединитесь к собранию повторно. Подключаемый модуль должен загрузиться без ошибок.

### <a name="modify-the-disablemsi-registry-setting"></a>Изменение параметра реестра DisableMSI

1. В меню **Пуск** выберите пункт **Выполнить**.

2. Чтобы открыть редактор реестра, введите **regedit**.

3. Перейдите к разделу HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Измените или добавьте параметр реестра DisableMSI типа REG_DWORD и задайте для него значение 0.

5. Присоединитесь к собранию повторно.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Включить Skype для замены Skype для бизнеса Web App (необязательный, только Skype для бизнеса Server 2015 г.)
<a name="SMA_Enable"> </a>

Эта процедура необязательна и применяется Skype для бизнеса Server 2015 cu5 и более поздней. Если вы не используете его, внешние пользователи будут продолжать присоединяться к собраниям с помощью Skype для бизнеса Web App.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Включить упрощенное приложение для Skype собраний

1. При включении доступа к сеть доставки содержимого (CDN) пользователи смогут подключаться к CDN в Интернете и получать Skype Meetings App (на Windows) и Skype для бизнеса на Mac (на Mac), а также использовать упрощенную процедуру подключения к собраниям.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Разрешить ведение телеметрии в стороне клиента с веб-страницы собрания или приложения Skype собраний, которые будут отправлены на серверы Майкрософт (команда по умолчанию является ложной).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Сведения, отправленные в Корпорацию Майкрософт, строго Skype для бизнеса [практике сбора данных.](/skypeforbusiness/legal-and-regulatory/data-collection-practices)

3. Задайте время перед тем, как вернуться к локально размещенной Skype для бизнеса Web App, если CDN недоступна. Значение по умолчанию — 6 секунд. Если это значение установлено до 0, время не будет.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> В meetingUxUseCdn в Skype для бизнеса Server 2015 накопительного обновления 5 значение по умолчанию задается значение False. Это приводит к проблеме, Skype для бизнеса на Mac клиент не может присоединиться к собраниям не федерационных партнеров в качестве гостя, даже если Skype для бизнеса администратор установил MeetingUxUseCdn для True. Для этого в Skype для бизнеса Server 2015 г. необходимо иметь накопительное обновление 7, 6.0.9319.534 или более позднее. См. в Skype в приложении [Enable Skype для бизнеса Web App 2015 Skype для бизнеса Server.](https://support.microsoft.com/kb/4132312)


## <a name="see-also"></a>См. также
<a name="SMA_Enable"> </a>

[Планирование для клиентов собраний (Web App и Meetings App)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Настройка страницы присоединиться к собранию в Skype для бизнеса Server](../../manage/conferencing/meeting-join-page.md)

[Заявление о конфиденциальности корпорации Microsoft](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[Условия лицензирования и документация](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)