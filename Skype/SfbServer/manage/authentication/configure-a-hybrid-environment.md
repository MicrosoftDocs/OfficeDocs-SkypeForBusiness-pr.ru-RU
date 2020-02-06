---
title: Настройка проверки подлинности "сервер-сервер" для гибридной среды Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Сводка: Настройка проверки подлинности серверов и серверов для гибридной среды Skype для бизнеса Server.'
ms.openlocfilehash: ed82e72c04d6fca0702a37819778d880b45ef617
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818841"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Настройка проверки подлинности "сервер-сервер" для гибридной среды Skype для бизнеса Server.

**Сводка:** Настройка проверки подлинности "сервер-сервер" в гибридной среде Skype для бизнеса Server.

В гибридной конфигурации некоторые пользователи размещаются в локальной установке Skype для бизнеса Server, в то время как другие пользователи находятся в версии Office 365 для Skype для бизнеса Server. Чтобы настроить проверку подлинности "сервер-сервер" в гибридной среде, необходимо сначала настроить локальную установку Skype для бизнеса Server, чтобы доверять серверу авторизации Office 365. Чтобы выполнить этот процесс, выполните следующие действия в сценарии командной консоли для управления Skype для бизнеса Server.

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId

$sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue

   if ($sts -eq $null)
      {
         New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
      }
   else
      {
         if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
            {
               Remove-CsOAuthServer microsoft.sts
               New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
            }
        }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue

if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
             New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
          }
       else
          {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
          }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Помните о том, что имя области для клиента обычно отличается от имени организации; на деле имя области почти всегда совпадает с идентификатором клиента. Поэтому первая строка скрипта используется для получения значения свойства TenantId для заданного клиента (в данном случае это fabrikam.com) и последующего назначения этого имени переменной $TenantId:

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

Для выполнения этого сценария необходимо установить модуль PowerShell Skype для бизнеса Online и подключиться к вашему клиенту с помощью этого модуля. Если вы не выполнили установку этих командлетов, то произойдет сбой вашего сценария, так как командлет Get-CsTenant будет недоступен. После завершения работы сценария необходимо настроить доверительные отношения между Skype для бизнеса Server и сервером авторизации, а также второе отношение доверия между Exchange 2013/2016 и сервером авторизации. Это возможно только с помощью командлетов Microsoft Online Services.

> [!NOTE]
> Если вы не установили командлеты Microsoft Online Services, вам нужно будет установить его из репозитория PowerShell с помощью командлета `install-module MSOnline`. Подробные сведения об установке и использовании модуля Microsoft Online Services можно найти на веб-сайте Office 365. В этих инструкциях также рассказывается о том, как настроить единый вход, Федерацию и синхронизацию между Office 365 и Active Directory. 



После настройки Office 365 и создания субъектов-служб Office 365 для Skype для бизнеса Server и Exchange 2013 вы должны зарегистрировать свои учетные данные для этих субъектов-служб. Для этого сначала необходимо получить сертификат X. 509 Base64, сохраненный как. Файл CER. Этот сертификат будет затем применен к участникам службы Office 365.

После получения сертификата X. 509 откройте консоль PowerShell и импортируйте модуль Microsoft Online Windows PowerShell, содержащий командлеты, которые можно использовать для управления субъектами служб.

```PowerShell
Import-Module MSOnline
```

После импорта модуля введите указанную ниже команду и нажмите клавишу ВВОД, чтобы подключиться к Office 365:

```PowerShell
Connect-MsolService
```

При нажатии клавиши Enter отображается диалоговое окно учетных данных. В диалоговом окне введите имя пользователя и пароль Office 365 и нажмите кнопку ОК.

После подключения к Office 365 вы можете выполнить следующую команду, чтобы получить сведения об участниках службы.

```PowerShell
Get-MsolServicePrincipal
```

Команда возвращает для всех субъектов-служб сведения, похожие на следующие:

<pre>
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
</pre>

На следующем шаге выполняется импорт, кодирование и назначение сертификата X.509. Для импорта и кодирования сертификата используйте указанные ниже команды Windows PowerShell, чтобы указать полный путь к файлу. CER при вызове метода Import:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

После того как сертификат будет импортирован и закодирован, вы можете назначить сертификат участникам службы Office 365. Для этого сначала используйте Get-МсолсервицепринЦипал для получения значения свойства АпппринЦипалид как для сервера Skype для бизнеса, так и для участников службы Microsoft Exchange. значение свойства АпппринЦипалид будет использоваться для идентификации субъекта-службы, которому назначается сертификат. С помощью значения свойства АпппринЦипалид в Skype для бизнеса Server вы можете присвоить сертификат для версии Skype для бизнеса Online, выполнив следующую команду:

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Затем следует повторить команду, на этот раз используя значение свойства АпппринЦипалид для Exchange 2013.

Если позже вам потребуется удалить этот сертификат, например, если срок его действия истек, сначала нужно получить Кэйид сертификата.

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

Эта команда возвращает следующие данные:

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

После этого вы можете удалить сертификат с помощью следующей команды:

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

Помимо назначения сертификата необходимо также настроить участника службы Exchange Online и настроить локальную версию веб-службы Skype для бизнеса Server как участника обслуживания Office 365. Для этого можно выполнить две следующие команды: 

В следующем примере Pool1ExternalWebFQDN.contoso.com — URL-адрес внешней веб-службы для пула сервера Skype для бизнеса. Вы должны повторить эти действия, чтобы добавить URL-адреса внешних веб-служб в развертывание.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
