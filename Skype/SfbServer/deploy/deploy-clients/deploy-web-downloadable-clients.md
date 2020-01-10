---
title: Развертывание веб-клиентов, доступных для загрузки, в Skype для бизнеса Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Сводка: развертывание приложения Skype для бизнеса Web App и собраний Skype, которое используется в Skype для бизнеса.'
ms.openlocfilehash: eb939ddf394ff62b9173939622a8ef3f20faaca9
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003529"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Развертывание веб-клиентов, доступных для загрузки, в Skype для бизнеса Server

**Сводка:** Развертывание приложения Skype для бизнеса 2015 веб-приложения и собраний Skype, которое используется в Skype для бизнеса Server.

Skype для бизнеса Web App — это веб-клиент служб IIS, установленный на сервере, на котором работает Skype для бизнеса Server, и по умолчанию он развертывается по запросу для пользователей собраний, у которых еще нет клиента Skype для бизнеса. Эти пользователи собраний чаще всего, чем подключение к сети извне. Каждый раз, когда пользователь щелкает URL-адрес собрания, но на нем не установлен клиент Skype для бизнеса, пользователю предоставляется возможность присоединиться к собранию с помощью последней версии Skype для бизнеса Web App, приложения для собраний Skype или Skype для бизнеса для Mac.

Функции голосового и видеосвязи в Skype для бизнеса Web App требуют наличия элемента управления Microsoft ActiveX, который используется в качестве подключаемого модуля браузера пользователя. Вы можете либо установить элемент ActiveX заранее, либо разрешить пользователям устанавливать его при появлении соответствующего запроса, что происходит при первом использовании Skype для бизнеса Web App или при первом доступе к функции, для которой требуется элемент ActiveX.

> [!NOTE]
> В развертывании приложения пограничного сервера в Skype для бизнеса Server требуется обратный прокси-сервер HTTPS в демилитаризованной зоне, необходимый для доступа клиента Skype для бизнеса Web App. Помимо этого, необходимо опубликовать простые URL-адреса. Подробности можно найти в разделе [Настройка обратных прокси-серверов](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) и [требований DNS к простым URL-адресам в Skype для бизнеса Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Включение многофакторной проверки подлинности для Skype для бизнеса Web App
<a name="MFA"> </a>

Веб-приложение Skype для бизнеса, приложение "собрания Skype" и Skype для бизнеса для Mac поддерживают многофакторную проверку подлинности. Помимо имени пользователя и пароля, для проверки подлинности пользователей, присоединяющихся к собраниям Skype для бизнеса, вы можете потребовать дополнительных способов проверки подлинности, например смарт-карт или контактов. Вы можете включить многофакторную проверку подлинности, развернув сервер федерации служб федерации Active Directory (AD FS) и включив пассивную проверку подлинности в Skype для бизнеса Server. После настройки службы AD FS внешние пользователи, пытающиеся присоединиться к собраниям в Skype для бизнеса, будут представлены с помощью веб-страницы многофакторной проверки подлинности AD FS, которая содержит имя пользователя и пароль, а также дополнительные способы проверки подлинности, которые вы настроен.

> [!IMPORTANT]
> Если вы планируете настроить службу федерации Active Directory для многофакторной проверки подлинности, учтите следующие рекомендации.

- Многофакторная проверка подлинности службы федерации Active Directory действует в том случае, если как участник, так и организатор собрания относятся к одной организации (в том числе с федерацией AD FS). Многофакторная проверка подлинности службы федерации Active Directory не действует для федеративных пользователей Lync, так как веб-инфраструктура сервера Lync не поддерживает такую возможность в настоящий момент.

- Если вы используете подсистемы балансировки нагрузки для оборудования, включите сохраняемость файлов cookie для подсистем балансировки нагрузки, чтобы все запросы из клиентов приложений Skype для бизнеса Web App или собраний обрабатывались на одном и том же внешнем сервере.

- Если вы устанавливаете отношение доверия проверяющей стороны между серверами Skype для бизнеса Server и AD FS, назначьте жизненный цикл, достаточно длинный, чтобы занимать максимальную длину собраний Skype для бизнеса. Как правило, 240 минут бывает достаточно.

- Эта конфигурация не действует для мобильных клиентов Lync.

### <a name="configure-multi-factor-authentication"></a>Настройка многофакторной проверки подлинности

1. Установите роль сервера федерации служб федерации Active Directory. Дополнительные сведения можно найти в [руководстве по развертыванию служб федерации Active Directory 2,0](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Создайте сертификаты для служб федерации Active Directory. Дополнительные сведения можно найти в разделе ["сертификаты серверов федерации"](https://go.microsoft.com/fwlink/p/?LinkId=285376) плана и развертывания AD FS для использования с одним разделом входа.

3. В интерфейсе командной строки Windows PowerShell выполните следующую команду:

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. Установите партнерство, выполнив следующую команду:

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. Настройте следующие правила проверяющей стороны:

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>Отключить функцию BranchCache 
<a name="MFA"> </a>

Функция BranchCache в Windows 7 и Windows Server 2008 R2 может повлиять на веб-компоненты Skype для бизнеса Web App. Чтобы предотвратить проблемы для пользователей Skype для бизнеса Web App, убедитесь, что служба BranchCache не включена.

Подробнее об отключении BranchCache можно узнать в [руководстве по развертыванию BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Проверка развертывания Skype для бизнеса Web App
<a name="MFA"> </a>

С помощью командлета Test-CsUcwaConference вы можете проверить возможность участия двух тестовых пользователей в конференции с использованием веб-API объединенных коммуникаций (UCWA). Подробные сведения об этом командлете можно найти в разделе [Test-ксукваконференце](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) в документации по среде управления в Skype для бизнеса Server.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Устранение неполадок при установке модулей в Windows Server 2008 R2
<a name="MFA"> </a>

Если установка надстройки завершается сбоем на компьютере под управлением Windows Server 2008 R2, возможно, потребуется изменить параметр безопасности Internet Explorer или параметр раздела реестра Дисаблемси.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Изменение параметра безопасности в Internet Explorer

1. Откройте Internet Explorer.

2. В меню **Сервис** выберите пункт **Свойства обозревателя** и перейдите на вкладку **Дополнительно**.

3. Перейдите к разделу **Безопасность**.

4. Снимите флажок **Не сохранять зашифрованные страницы на диск** и нажмите кнопку **ОК**.

    > [!NOTE]
    > Если этот параметр установлен, при попытке загрузить вложение из Skype для бизнеса Web App может возникнуть ошибка.

5. Присоединитесь к собранию повторно. Подключаемый модуль должен загрузиться без ошибок.

### <a name="modify-the-disablemsi-registry-setting"></a>Изменение параметра реестра DisableMSI

1. В меню **Пуск** выберите пункт **Выполнить**.

2. Чтобы открыть редактор реестра, введите команду **regedit**.

3. Перейдите к разделу HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Измените или добавьте параметр реестра DisableMSI типа REG_DWORD и задайте для него значение 0.

5. Присоединитесь к собранию повторно.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Включение возможности замены Skype для бизнеса Web App приложением "собрания Skype" (необязательно, Skype для бизнеса Server 2015)
<a name="SMA_Enable"> </a>

Эта процедура необязательна и применима к Skype для бизнеса Server 2015 CU5 и более поздних версий. Если вы не используете его, внешние пользователи продолжат присоединяться к собраниям с помощью Skype для бизнеса Web App.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Включение упрощенного присоединения к собранию и приложения для собраний Skype

1. При включении доступа к сети доставки содержимого (CDN) пользователи получат возможность подключаться к CDN Online и получать приложения для собраний Skype (в Windows) и Skype для бизнеса для Mac (на Mac) и использовать упрощенное соединение для собраний.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Разрешить отправку журнала на стороне клиента с веб-страницы присоединения к собранию или из приложения "собрания Skype" для отправки на серверы Майкрософт (по умолчанию для команды задано значение "ложь").

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Сведения, отправляемые в корпорацию Майкрософт, строго соответствуют [рекомендациям по сбору данных в Skype для бизнеса](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).

3. Установите время ожидания перед переходом на локальное веб-приложение Skype для бизнеса, если сеть CDN недоступна. По умолчанию установлено значение 6 с. Если установлено значение 0, никакого времени ожидания не будет.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Благодаря Митингуксусекдн в Skype для бизнеса Server 2015 накопительного обновления 5 значение по умолчанию равно false. Это приводит к тому, что клиент Skype для бизнеса для Mac не может присоединиться к собраниям, не являющимся федеративных партнерами, в качестве гостя, даже если администратор Skype для бизнеса установил для Митингуксусекдн значение true. Для этого в Skype для бизнеса Server 2015 должен быть установлен накопительный пакет обновления 7, 6.0.9319.534 или более поздней версии. [В разделе Включение собраний Skype можно заменить приложение Skype для бизнеса Web App в Skype для бизнеса Server 2015](https://support.microsoft.com/kb/4132312).


## <a name="see-also"></a>См. также
<a name="SMA_Enable"> </a>

[Планирование для клиентов собраний (Skype для бизнеса Web App и приложение "Собрания Skype")](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Настройка страницы присоединения к собранию в Skype для бизнеса Server](../../manage/conferencing/meeting-join-page.md)

[Заявление о конфиденциальности Microsoft Online Services](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[Условия лицензионного соглашения и документация](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
