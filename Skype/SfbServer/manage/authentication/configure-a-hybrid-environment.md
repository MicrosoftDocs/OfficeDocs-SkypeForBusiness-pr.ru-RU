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
description: 'Сводка: Настройка проверки подлинности "сервер-сервер" для гибридной среды Skype для бизнеса Server.'
ms.openlocfilehash: 6cc408677af4629d36b577da4ae38cd420195483
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221683"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Настройка проверки подлинности "сервер-сервер" для гибридной среды Skype для бизнеса Server.

**Сводка:** Настройка проверки подлинности "сервер-сервер" для гибридной среды Skype для бизнеса Server.

В гибридной конфигурации некоторые пользователи размещаются в локальной установке Skype для бизнеса Server, в то время как другие пользователи размещены в Microsoft 365 или Office 365 Skype для бизнеса Server. Чтобы настроить межсерверную проверку подлинности в гибридной среде, необходимо сначала настроить локальную установку Skype для бизнеса Server, чтобы доверять серверу авторизации. Чтобы выполнить этот процесс, выполните следующий сценарий консоли управления Skype для бизнеса Server:

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

Для выполнения этого сценария необходимо установить модуль PowerShell Skype для бизнеса Online и подключиться к клиенту с помощью этого модуля. Если вы не установили эти командлеты, сценарий завершится с ошибками, так как командлет Get-CsTenant будет недоступен. После выполнения сценария необходимо настроить отношение доверия между Skype для бизнеса Server и сервером авторизации, а также второе отношение доверия между Exchange 2013/2016 и сервером авторизации. Это можно выполнить только с помощью командлетов Microsoft Online Services.

> [!NOTE]
> Если командлеты Microsoft Online Services не установлены, их необходимо будет установить из репозитория PowerShell с помощью командлета `install-module MSOnline` . Подробные сведения об установке и использовании модуля Microsoft Online Services можно найти на веб-сайте Microsoft 365. В этих инструкциях также рассказывается, как настроить единый вход, Федерацию и синхронизацию между Microsoft 365 или Office 365 и Active Directory. 



После того как вы настроили Microsoft 365 или Office 365, а после создания Microsoft 365 или Office 365 субъектов-служб для Skype для бизнеса Server и 2013 Exchange Server, вам потребуется зарегистрировать учетные данные этих субъектов-служб. Для этого сначала необходимо получить сертификат X. 509 Base64, сохраненный в формате. CER-файл. Затем этот сертификат будет применяться к субъектам служб Microsoft 365 или Office 365.

После получения сертификата X. 509 откройте консоль PowerShell и импортируйте модуль Microsoft Online Windows PowerShell, содержащий командлеты, которые можно использовать для управления субъектами-службами:

```PowerShell
Import-Module MSOnline
```

После импорта модуля введите следующую команду и нажмите клавишу ВВОД:

```PowerShell
Connect-MsolService
```

После нажатия клавиши ВВОД отображается диалоговое окно. Введите в диалоговом окне имя пользователя и пароль Microsoft 365 или Office 365, а затем нажмите кнопку ОК.

После подключения к Microsoft 365 или Office 365 можно выполнить следующую команду, чтобы получить сведения о субъектах службы:

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

Следующий этап состоит из импорта, кодирования и назначения сертификата X.509. Чтобы импортировать и закодировать сертификат, используйте следующие команды Windows PowerShell, чтобы указать полный путь к файлу. CER-файл при вызове метода Import:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

После импорта и кодирования сертификата вы можете назначить сертификат для участников службы Microsoft 365 или Office 365. Для этого сначала используйте Get-MsolServicePrincipal, чтобы получить значение свойства AppPrincipalId как для Skype для бизнеса Server, так и для субъектов-служб Microsoft Exchange. значение свойства AppPrincipalId будет использоваться для идентификации участника службы, которому назначается сертификат. С помощью значения свойства AppPrincipalId для Skype для бизнеса Server в наличии выполните следующую команду, чтобы назначить сертификат для версии Skype для бизнеса Online:

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Затем необходимо повторить команду, на этот раз используя значение свойства AppPrincipalId для Exchange 2013.

Если позднее потребуется удалить этот сертификат, например, если срок его действия истек, сначала необходимо получить него значение KeyID для сертификата:

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

В дополнение к назначению сертификата необходимо также настроить субъект-службу Exchange Online и настроить локальную версию внешних URL-адресов Skype для бизнеса Server как в качестве субъекта-службы Microsoft 365 или Office 365. Для этого можно выполнить следующие две команды. 

В следующем примере Pool1ExternalWebFQDN.contoso.com — это URL-адрес внешней веб-службы для пула Skype для бизнеса Server. Необходимо повторить эти действия, чтобы добавить все URL-адреса внешних веб-служб в развертывании.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
