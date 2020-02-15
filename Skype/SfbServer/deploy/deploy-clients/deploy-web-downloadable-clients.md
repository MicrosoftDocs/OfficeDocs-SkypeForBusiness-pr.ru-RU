---
title: Развертывание веб-клиентов, загружаемых через Интернет, в Skype для бизнеса Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: Сводка. Развертывание приложения Skype для бизнеса Web App и собраний Skype, используемого в Skype для бизнеса.
ms.openlocfilehash: 7f6bebbc9950a7eb5da202c3b818b1288c811f17
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029050"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Развертывание веб-клиентов, загружаемых через Интернет, в Skype для бизнеса Server

**Сводка:** Разверните приложение Skype для бизнеса 2015 веб-приложение и собрания Skype, используемые с Skype для бизнеса Server.

Skype для бизнеса Web App — это веб-клиент служб IIS, установленный на сервере Skype для бизнеса Server, и по умолчанию он развертывается по запросу для собраний пользователей, у которых еще нет клиента Skype для бизнеса. Эти пользователи встречаются чаще, чем не подключаются к сети извне. Когда пользователь щелкает URL-адрес собрания, но не имеет установленного клиента Skype для бизнеса, пользователю предоставляется возможность присоединиться к собранию с помощью последней версии приложения Skype для бизнеса Web App, приложения для собраний Skype или Skype для бизнеса для Mac.

Функции голосовых, видео и общего доступа в Skype для бизнеса Web App требуют наличия элемента управления Microsoft ActiveX, используемого в качестве подключаемого модуля браузером пользователя. Вы можете либо установить элемент управления ActiveX заранее, либо разрешить пользователям устанавливать его при первом запуске приложения Skype для бизнеса Web App или при первом обращении к функции, требующей использования элемента управления ActiveX.

> [!NOTE]
> В развертываниях пограничных серверов Skype для бизнеса Server для клиентского доступа к Skype для бизнеса Web App необходим обратный прокси-сервер HTTPS в сети периметра. Вам также нужно опубликовать простые URL-адреса. Дополнительные сведения см. в статье [Настройка обратных прокси-серверов](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) и [требований DNS для простых URL-адресов в Skype для бизнеса Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Включение многофакторной проверки подлинности для Skype для бизнеса Web App
<a name="MFA"> </a>

Веб-приложение Skype для бизнеса, приложение для собраний Skype и Skype для бизнеса для Mac поддерживают многофакторную проверку подлинности. Помимо имени пользователя и пароля, для проверки подлинности пользователей, присоединяющихся к собраниям Skype для бизнеса, могут потребоваться дополнительные методы проверки подлинности, такие как смарт-карты или ПИН-коды. Вы можете включить многофакторную проверку подлинности, развернув сервер федерации службы федерации Active Directory (AD FS) и включив пассивную проверку подлинности в Skype для бизнеса Server. После настройки AD FS внешние пользователи, пытающиеся присоединиться к собраниям Skype для бизнеса, будут представлены с помощью веб-страницы многофакторной проверки подлинности AD FS, которая содержит имя пользователя и пароль, а также дополнительные методы проверки подлинности, которые настроен.

> [!IMPORTANT]
> Если вы планируете настроить службу федерации Active Directory для многофакторной проверки подлинности, учтите следующие рекомендации.

- Многофакторная проверка подлинности в службах ADFS работает, если участник и организатор собрания одновременно находятся в одной организации или в федеративной организации AD FS. Многофакторная проверка подлинности ADFS не работает для федеративных пользователей Lync, так как веб-инфраструктура Lync Server в настоящее время не поддерживает эту службу.

- Если вы используете аппаратные средства балансировки нагрузки, включите сохранение файлов cookie в подсистемах балансировки нагрузки, чтобы все запросы от клиентов приложений Skype для бизнеса Web App или собраний обрабатывались одним сервером переднего плана.

- При установке отношения доверия с проверяющей стороной между Skype для бизнеса Server и серверами AD FS назначьте срок жизни маркера, достаточно длинного для достижения максимальной длины собраний Skype для бизнеса. Как правило, 240 минут бывает достаточно.

- Эта конфигурация не применяется к мобильным клиентам Lync.

### <a name="configure-multi-factor-authentication"></a>Настройка многофакторной проверки подлинности

1. Установите роль сервера федерации службы федерации Active Directory. Дополнительные сведения см. в [руководстве по развертыванию служб федерации Active Directory 2,0](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Создайте сертификаты для AD FS. Дополнительные сведения можно найти в разделе ["сертификаты сервера федерации"](https://go.microsoft.com/fwlink/p/?LinkId=285376) плана for AD FS для использования с единым входом.

3. В интерфейсе командной строки Windows PowerShell выполните следующую команду:

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

Функция BranchCache в Windows 7 и Windows Server 2008 R2 может повлиять на веб-компоненты Skype для бизнеса Web App Web App. Чтобы предотвратить возникновение проблем для пользователей Skype для бизнеса Web App, убедитесь, что служба BranchCache отключена.

Дополнительные сведения об отключении BranchCache содержатся в [руководстве по развертыванию BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Проверка развертывания веб-приложения Skype для бизнеса
<a name="MFA"> </a>

С помощью командлета Test-CsUcwaConference вы можете проверить возможность участия двух тестовых пользователей в конференции с использованием веб-интерфейса API объединенных коммуникаций (UCWA). Подробнее об этом командлете можно узнать в статье [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) в документации по среде управления Skype для бизнеса Server.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Устранение неполадок при установке подключаемого модуля в Windows Server 2008 R2
<a name="MFA"> </a>

Если при установке подключаемого модуля произошел сбой на компьютере под управлением Windows Server 2008 R2, может потребоваться изменить параметр безопасности Internet Explorer или раздел реестра параметр DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Изменение параметра безопасности в Internet Explorer

1. Откройте Internet Explorer.

2. В меню **Сервис** выберите пункт **Свойства обозревателя** и перейдите на вкладку **Дополнительно**.

3. Перейдите к разделу **Безопасность**.

4. Снимите флажок **Не сохранять зашифрованные страницы на диск** и нажмите кнопку **ОК**.

    > [!NOTE]
    > Если выбран этот параметр, то при попытке скачать вложение из Skype для бизнеса Web App будет вычислено сообщение об ошибке.

5. Присоединитесь к собранию повторно. Подключаемый модуль должен загрузиться без ошибок.

### <a name="modify-the-disablemsi-registry-setting"></a>Изменение параметра реестра параметр DisableMSI

1. В меню **Пуск** выберите пункт **Выполнить**.

2. Чтобы открыть редактор реестра, введите **regedit**.

3. Перейдите к разделу HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Измените или добавьте параметр реестра DisableMSI типа REG_DWORD и задайте для него значение 0.

5. Присоединитесь к собранию повторно.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Включить в приложении для собраний Skype замену веб-приложения Skype для бизнеса (необязательно, Skype для бизнеса Server 2015)
<a name="SMA_Enable"> </a>

Эта процедура является необязательной и применима к Skype для бизнеса Server 2015 CU5 и более поздних версий. Если вы не используете его, внешние пользователи продолжат присоединяться к собраниям с помощью Skype для бизнеса Web App.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Включение упрощенного присоединения к собранию и приложения для собраний Skype

1. Когда вы включаете доступ к сети доставки содержимого (CDN), пользователи смогут подключаться к сети CDN и получать приложение для собраний Skype (в Windows) и Skype для бизнеса для Mac (на Mac), а также использовать упрощенное подключение к собранию.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Разрешить отправку данных из журнала на стороне клиента с веб-страницы присоединения к собранию или приложения собраний Skype на серверы Майкрософт (по умолчанию для команды задано значение false).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Сведения, отправляемые в корпорацию Майкрософт, задаются в соответствии с [рекомендациями по сбору данных в Skype для бизнеса](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).

3. Установите время ожидания до возврата к локальному интерфейсу веб-приложения Skype для бизнеса, если сеть CDN недоступна. Значение по умолчанию — 6 секунд. Если этому параметру присвоено значение 0, время ожидания не будет превышаться.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> В Митингуксусекдн в Skype для бизнеса Server 2015 с накопительным пакетом обновления 5 для установки по умолчанию установлено значение false. Это приводит к тому, что клиент Skype для бизнеса для Mac не может присоединяться к собраниям по нефедеративных партнерам в качестве гостя, даже если для администратора Skype для бизнеса задано значение Митингуксусекдн. Чтобы это работало, Skype для бизнеса Server 2015 должен иметь накопительный пакет обновления 7, 6.0.9319.534 или более поздней версии. [В статье Включение приложения для собраний Skype замените веб-приложение Skype для бизнеса на Skype для бизнеса Server 2015](https://support.microsoft.com/kb/4132312).


## <a name="see-also"></a>См. также
<a name="SMA_Enable"> </a>

[Планирование для клиентов собраний (приложение для веб-приложений и собраний)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Настройка страницы присоединения к собранию в Skype для бизнеса Server](../../manage/conferencing/meeting-join-page.md)

[Заявление о конфиденциальности корпорации Microsoft](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[Условия лицензирования и документация](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
