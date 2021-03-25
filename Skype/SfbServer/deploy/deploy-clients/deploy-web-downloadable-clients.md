---
title: Развертывание веб-загружаемых клиентов в Skype для бизнеса Server
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: Сводка. Развертывание приложения Skype для бизнеса и skype Meetings App, используемая в Skype для бизнеса.
ms.openlocfilehash: 20489dddb244b179908f8c8a565bb1f4d539a5a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122133"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Развертывание веб-загружаемых клиентов в Skype для бизнеса Server

**Сводка:** Развертывание приложения Skype для бизнеса 2015 и приложения Skype Meetings, используемой в Skype для бизнеса Server.

Skype for Business Web App — это веб-клиент Службы интернет-информации (IIS), установленный на сервере Под управлением Skype для бизнеса Server и по умолчанию развертывается по требованию для встреч с пользователями, у которых еще нет клиента Skype для бизнеса. Эти пользователи собраний чаще всего не подключаются из-за вашей сети. Всякий раз, когда пользователь щелкает URL-адрес собрания, но не установлен клиент Skype для бизнеса, пользователю будет представлена возможность присоединиться к собранию с помощью последней версии Skype для бизнеса Веб-приложения, Skype Meetings App или Skype для бизнеса для Mac.

Функции голосовой, видео- и совместной работы в Веб-приложении Skype для бизнеса требуют ActiveX microsoft, который используется в качестве плагина в браузере пользователя. Вы можете установить элемент управления ActiveX заранее или разрешить пользователям устанавливать его по запросу, что происходит при первом использовании Skype для бизнеса веб-приложения или при первом доступе к функции, которая требует ActiveX управления.

> [!NOTE]
> В развертываниях Skype для бизнес-сервера Edge Server для клиентского доступа к Skype для бизнеса требуется обратный прокси-сервер HTTPS в сети периметра. Вам также нужно опубликовать простые URL-адреса. Подробные сведения см. [в материале Настройка требований к](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers) обратным прокси-серверам и DNS для простых URL-адресов [в Skype для бизнеса Server.](../../plan-your-deployment/network-requirements/simple-urls.md)

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Включить многофакторную проверку подлинности для Веб-приложения Skype для бизнеса
<a name="MFA"> </a>

Skype для бизнеса Веб-приложение, Skype Meetings App и Skype для бизнеса для Mac поддерживают многофакторную проверку подлинности. Помимо имени пользователя и пароля, вам могут потребоваться дополнительные методы проверки подлинности, такие как смарт-карты или ПИН-коды, для проверки подлинности пользователей, присоединявшихся к внешним сетям при входе на собрания Skype для бизнеса. Можно включить многофакторную проверку подлинности, развернув сервер федерации Active Directory Federation Service (AD FS) и включив пассивную проверку подлинности в Skype для бизнеса Server. После настройки AD FS внешним пользователям, пытающихся присоединиться к собраниям Skype для бизнеса, будет представлена веб-страница многофакторной проверки подлинности AD FS, которая содержит имя пользователя и вызов пароля, а также дополнительные методы проверки подлинности, которые вы настроили.

> [!IMPORTANT]
> Если вы планируете настроить службу федерации Active Directory для многофакторной проверки подлинности, учтите следующие рекомендации.

- Многофакторная проверка подлинности ADFS работает, если участник и организатор собрания находятся в одной организации или оба из федераированной организации AD FS. Многофакторная проверка подлинности ADFS не работает для федерационных пользователей Lync, так как веб-инфраструктура сервера Lync в настоящее время не поддерживает ее.

- Если вы используете балансиры нагрузки оборудования, в используйте сохранение файлов cookie на балансире нагрузки, чтобы все запросы от клиентов Skype для бизнес-веб-приложения или приложений meetings обрабатывались тем же сервером переднего входа.

- При создании доверительной группы между серверами Skype для бизнеса Server и AD FS назначьте срок службы маркера, который будет достаточно длительным для максимальной продолжительности собраний Skype для бизнеса. Как правило, 240 минут бывает достаточно.

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

Функция BranchCache в Windows 7 и Windows Server 2008 R2 может мешать веб-компонентам Skype для бизнеса. Чтобы предотвратить проблемы для пользователей веб-приложений Skype для бизнеса, убедитесь, что BranchCache не включен.

Сведения об отключении BranchCache см. в руководстве по развертыванию [BranchCache.](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)

## <a name="verifying-skype-for-business-web-app-deployment"></a>Проверка развертывания веб-приложений Skype для бизнеса
<a name="MFA"> </a>

С помощью командлета Test-CsUcwaConference вы можете проверить возможность участия двух тестовых пользователей в конференции с использованием веб-интерфейса API объединенных коммуникаций (UCWA). Подробные сведения об этом комлете см. в документации [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) в документации skype for Business Server Management Shell.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Устранение неполадок в установке подключаемого Windows Server 2008 R2
<a name="MFA"> </a>

Если установка подключаемого плагина не удается на компьютере с Windows Server 2008 R2, возможно, потребуется изменить параметр безопасности Internet Explorer или параметр параметра отключения ключевых реестров DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Изменение параметра безопасности в Internet Explorer

1. Откройте Internet Explorer.

2. В меню **Сервис** выберите пункт **Свойства обозревателя** и перейдите на вкладку **Дополнительно**.

3. Перейдите к разделу **Безопасность**.

4. Снимите флажок **Не сохранять зашифрованные страницы на диск** и нажмите кнопку **ОК**.

    > [!NOTE]
    > При выборе этого параметра также может быть допущена ошибка при попытке скачать вложение из Веб-приложения Skype для бизнеса.

5. Присоединитесь к собранию повторно. Подключаемый модуль должен загрузиться без ошибок.

### <a name="modify-the-disablemsi-registry-setting"></a>Изменение параметра реестра DisableMSI

1. В меню **Пуск** выберите пункт **Выполнить**.

2. Чтобы открыть редактор реестра, введите **regedit**.

3. Перейдите к разделу HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Измените или добавьте параметр реестра DisableMSI типа REG_DWORD и задайте для него значение 0.

5. Присоединитесь к собранию повторно.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Включить приложение Skype Meetings для замены Веб-приложения Skype для бизнеса (необязательно, только Skype для бизнеса Server 2015)
<a name="SMA_Enable"> </a>

Эта процедура необязательна и применяется к Skype для бизнеса Server 2015 CU5 и более поздней. Если вы не используете его, внешние пользователи будут продолжать присоединяться к собраниям с помощью Skype для бизнеса веб-приложения.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Включить упрощенное приложение для собраний и собраний Skype

1. При включении доступа к сети доставки контента (CDN) пользователи смогут подключаться к CDN в Интернете и получать приложение Skype Meetings App (на Windows) и Skype для бизнеса для Mac (на Mac), а также использовать упрощенную процедуру подключения к собраниям.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Разрешить абонентской стороне ведения журнала телеметрии с веб-страницы собрания присоединиться к веб-странице или Skype Meetings App, которые будут отправлены на серверы Майкрософт (команда по умолчанию является ложной).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Информация, отправленная в Корпорацию Майкрософт, строго соответствует практикам сбора данных [Skype для бизнеса.](/skypeforbusiness/legal-and-regulatory/data-collection-practices)

3. Задайте время перед тем, как вернуться к локально размещенной службе Skype для бизнес-веб-приложения, если cdN не доступен. Значение по умолчанию — 6 секунд. Если это значение установлено до 0, время не будет.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Благодаря meetingUxUseCdn в Skype для бизнеса Server 2015 Кумулятивное обновление 5 значение по умолчанию задается значением False. Это приводит к проблеме, из-за которой клиент Skype для бизнеса для Mac не может присоединяться к собраниям партнеров, не вступив в качестве гостя, даже если Skype для бизнеса администратор установил MeetingUxUseCdn для True. Для этого Skype для бизнеса Server 2015 должен иметь накопительное обновление 7, 6.0.9319.534 или более позднее. См. [в приложении Enable Skype Meetings App для замены Skype для бизнеса в Skype для бизнеса Server 2015.](https://support.microsoft.com/kb/4132312)


## <a name="see-also"></a>См. также
<a name="SMA_Enable"> </a>

[Планирование для клиентов собраний (Web App и Meetings App)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Настройка страницы присоединиться к собранию в Skype для бизнеса Server](../../manage/conferencing/meeting-join-page.md)

[Заявление о конфиденциальности корпорации Microsoft](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[Условия лицензирования и документация](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)