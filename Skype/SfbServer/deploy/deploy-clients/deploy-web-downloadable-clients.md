---
title: Развертывание загружаемых веб-клиентов в Skype для бизнеса Server
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
description: Сводка. Развертывание Skype для бизнеса Web App и приложения "Собрания Skype", используемой вместе со Skype для бизнеса.
ms.openlocfilehash: afab5d0977adb8749fb514f946b676598d42ea32
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805929"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Развертывание загружаемых веб-клиентов в Skype для бизнеса Server

**Сводка:** Развертывание Skype для бизнеса 2015 Web App и приложения собраний Skype, используемых вместе со Skype для бизнеса Server.

Skype для бизнеса Web App — это веб-клиент служб IIS, установленный на сервере Skype для бизнеса Server и по умолчанию развернутый по требованию для собраний пользователей, у которых еще нет клиента Skype для бизнеса. Эти пользователи собраний чаще, чем не подключаются из-за пределов вашей сети. Каждый раз, когда пользователь щелкает URL-адрес собрания, но не имеет установленного клиента Skype для бизнеса, ему будет доступно присоединиться к собранию с помощью последней версии Skype для бизнеса Web App, приложения "Собрания Skype" или Skype для бизнеса для Mac.

Для работы функций голосовой и видеосвязи и общего доступа в Skype для бизнеса Web App требуется ActiveX Microsoft ActiveX, используемый браузером пользователя в качестве подключаемого модуль. Вы можете установить элемент управления ActiveX заранее или разрешить пользователям устанавливать его по запросу, что происходит при первом использовании Skype для бизнеса Web App или при первом доступе к функции, для которой требуется ActiveX управления.

> [!NOTE]
> В развертываниях Skype для бизнеса Server Edge Server обратный прокси-сервер HTTPS в сети периметра необходим для клиентского доступа Skype для бизнеса Web App. Вам также нужно опубликовать простые URL-адреса. For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server.](../../plan-your-deployment/network-requirements/simple-urls.md)

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Включить многофакторную проверку подлинности для Skype для бизнеса Web App
<a name="MFA"> </a>

Skype для бизнеса Web App, приложение "Собрания Skype" и Skype для бизнеса для Mac поддерживают многофакторную проверку подлинности. Помимо имени пользователя и пароля, для проверки подлинности пользователей, которые присоединяются из внешних сетей при входе в собрания Skype для бизнеса, могут потребоваться дополнительные методы проверки подлинности, например смарт-карты или ПИН-коды. Чтобы включить многофакторную проверку подлинности, развернем сервер федерации службы федерации Active Directory (AD FS) и включив пассивную проверку подлинности в Skype для бизнеса Server. После настройки AD FS внешние пользователи, пытаемые присоединиться к собраниям Skype для бизнеса, будут представлены на веб-странице многофакторной проверки подлинности AD FS, которая содержит имя пользователя и пароль, а также любые дополнительные настроенные методы проверки подлинности.

> [!IMPORTANT]
> Если вы планируете настроить службу федерации Active Directory для многофакторной проверки подлинности, учтите следующие рекомендации.

- Многофакторная проверка подлинности ADFS работает, если участник и организатор собрания находятся в одной организации или оба являются участниками федерационной организации AD FS. Многофакторная проверка подлинности ADFS не работает для федераированных пользователей Lync, так как веб-инфраструктура сервера Lync в настоящее время не поддерживает ее.

- Если вы используете аппаратные балансиры нагрузки, в течение сохраняемого файла cookie в них можно включить сохраняемость файлов cookie, чтобы все запросы от клиентов Skype для бизнеса Web App или приложений для собраний обрабатывались на одном сервере переднего сервера.

- When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings. Как правило, 240 минут бывает достаточно.

- Эта конфигурация не применяется к мобильным клиентам Lync.

### <a name="configure-multi-factor-authentication"></a>Настройка многофакторной проверки подлинности

1. Установите роль сервера федерации службы федерации Active Directory. Подробные сведения см. в руководстве по развертыванию служб федерации [Active Directory 2.0](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Создайте сертификаты для AD FS. Дополнительные сведения см. в разделе ["Сертификаты](https://go.microsoft.com/fwlink/p/?LinkId=285376) сервера федерации" статьи "Планирование и развертывание AD FS для использования с единым входом".

3. В интерфейсе Windows PowerShell командной строки запустите следующую команду:

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

Функция BranchCache в Windows 7 и Windows Server 2008 R2 может мешать веб-компонентам Skype для бизнеса Web App. Чтобы предотвратить проблемы для пользователей Skype для бизнеса Web App, убедитесь, что BranchCache не включен.

Подробные сведения об отключке BranchCache см. в руководстве [по развертыванию BranchCache.](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)

## <a name="verifying-skype-for-business-web-app-deployment"></a>Проверка развертывания Skype для бизнеса Web App
<a name="MFA"> </a>

С помощью командлета Test-CsUcwaConference вы можете проверить возможность участия двух тестовых пользователей в конференции с использованием веб-интерфейса API объединенных коммуникаций (UCWA). For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Устранение неполадок при установке подключаемого Windows Server 2008 R2
<a name="MFA"> </a>

Если установка подключаемого модуль не удается на компьютере, на Windows Server 2008 R2, может потребоваться изменить параметры безопасности Internet Explorer или Параметры реестра DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Изменение параметра безопасности в Internet Explorer

1. Откройте Internet Explorer.

2. В меню **Сервис** выберите пункт **Свойства обозревателя** и перейдите на вкладку **Дополнительно**.

3. Перейдите к разделу **Безопасность**.

4. Снимите флажок **Не сохранять зашифрованные страницы на диск** и нажмите кнопку **ОК**.

    > [!NOTE]
    > Если этот параметр выбран, при попытке скачать вложение из Skype для бизнеса Web App также будет происходить ошибка.

5. Присоединитесь к собранию повторно. Подключаемый модуль должен загрузиться без ошибок.

### <a name="modify-the-disablemsi-registry-setting"></a>Изменение параметра реестра DisableMSI

1. В меню **Пуск** выберите пункт **Выполнить**.

2. Чтобы открыть редактор реестра, введите **regedit**.

3. Перейдите к разделу HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Измените или добавьте параметр реестра DisableMSI типа REG_DWORD и задайте для него значение 0.

5. Присоединитесь к собранию повторно.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)
<a name="SMA_Enable"> </a>

Эта процедура является необязательной и применяется к Skype для бизнеса Server 2015 CU5 и более поздним. Если вы не используете его, внешние пользователи продолжат присоединяться к собраниям с помощью Skype для бизнеса Web App.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Enable simplified meeting join and Skype Meetings App

1. При включении доступа к сети доставки содержимого (CDN) пользователи смогут подключаться к сети CDN и получать приложение "Собрания Skype" (в Windows) и Skype для бизнеса для Mac (на Mac) и будут использовать упрощенное присоединение к собраниям.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Разрешить серверы Майкрософт отослать телеметрию ведения журнала на стороне клиента с веб-страницы присоединить к собранию или приложение "Собрания Skype" (команда по умолчанию имеет значение false).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Информация, отданная в корпорацию Майкрософт, строго соответствует методикам сбора данных Skype для [бизнеса.](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)

3. Задайте время, прежде чем вернуться к локально размещенной сети Skype для бизнеса Web App, если сеть CDN недоступна. Значение по умолчанию — 6 секунд. Если за установлено значение 0, время не будет установлено.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False. Это приводит к проблеме, из-за которой клиент Skype для бизнеса для Mac не может присоединяться к собраниям не федерационных партнеров в качестве гостя, даже если администратор Skype для бизнеса установил для MeetingUxUseCdn true. Для этого Skype для бизнеса Server 2015 должен иметь накопительный обновления 7, 6.0.9319.534 или более поздней версии. См. ["Приложение "Включить собрания Skype" для замены Skype для бизнеса Web App в Skype для бизнеса Server 2015.](https://support.microsoft.com/kb/4132312)


## <a name="see-also"></a>См. также
<a name="SMA_Enable"> </a>

[Планирование клиентов собраний (Веб-приложение и приложение для собраний)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Настройка страницы присоединить к собранию в Skype для бизнеса Server](../../manage/conferencing/meeting-join-page.md)

[Заявление о конфиденциальности корпорации Microsoft](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[Условия лицензирования и документация](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
