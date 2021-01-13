---
title: Настройка проверки подлинности "сервер-сервер" для гибридной среды Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: Сводка. Настройка проверки подлинности "сервер-сервер" для гибридной среды Skype для бизнеса Server.
ms.openlocfilehash: 6f4e11b54f0292b1ccb91ab486e2e638a4dcceb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828489"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Настройка проверки подлинности "сервер-сервер" для гибридной среды Skype для бизнеса Server.

**Сводка:** Настройка проверки подлинности "сервер-сервер" для гибридной среды Skype для бизнеса Server.

В гибридной конфигурации некоторые пользователи находятся в локальной установке Skype для бизнеса Server, а другие — в версии Microsoft 365 или Office 365 Skype для бизнеса Server. Чтобы настроить проверку подлинности "сервер-сервер" в гибридной среде, необходимо сначала настроить локальной установке Skype для бизнеса Server доверие серверу авторизации. Для начального шага этого процесса можно использовать следующий сценарий в оболочке управления Skype для бизнеса Server:

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

Для выполнения этого сценария необходимо установить модуль PowerShell Skype для бизнеса Online и подключиться к вашему арендатору с помощью этого модуля. Если эти cmdlets не установлены, то сценарий не будет работать, так как Get-CsTenant не будет доступен. После выполнения сценария необходимо настроить отношение доверия между Skype для бизнеса Server и сервером авторизации, а также второе отношение доверия между Exchange 2013/2016 и сервером авторизации. Это можно выполнить только с помощью командлетов Microsoft Online Services.

> [!NOTE]
> Если вы не установили Microsoft Online Services, необходимо установить его из репозитория PowerShell с помощью этого. `install-module MSOnline` Подробные сведения об установке и использовании модуля Microsoft Online Services можно найти на веб-сайте Microsoft 365. В этих инструкциях также поется, как настроить единый вход, федерацию и синхронизацию между Microsoft 365 или Office 365 и Active Directory. 



После настройки Microsoft 365 или Office 365 и создания основных служб Microsoft 365 или Office 365 для Skype для бизнеса Server и Exchange 2013 вам потребуется зарегистрировать свои учетные данные в этих компаниях-службах. Для этого необходимо сначала получить сертификат X.509 Base64, сохраненный в качестве . CER-файл. Затем этот сертификат будет применен к основным службам Microsoft 365 или Office 365.

Получив сертификат X.509, откройте консоль PowerShell и импортируете модуль Microsoft Online Windows PowerShell, содержащий командлеты, которые можно использовать для управления основными службами:

```PowerShell
Import-Module MSOnline
```

После импорта модуля введите следующую команду и нажмите ввод:

```PowerShell
Connect-MsolService
```

После нажатия клавиши ВВОД отображается диалоговое окно. Введите имя пользователя и пароль Microsoft 365 или Office 365 в диалоговом окне и нажмите кнопку "ОК".

Как только вы подключились к Microsoft 365 или Office 365, вы можете выполнить следующую команду, чтобы получить сведения о своих основных службах:

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

Следующий этап состоит из импорта, кодирования и назначения сертификата X.509. Чтобы импортировать и закодировать сертификат, используйте следующие команды Windows PowerShell, указав полный путь к файлу. CER-файл при вызове метода Import:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

После импорта и кодирования сертификата вы можете назначить его своим основной службе Microsoft 365 или Office 365. Для этого сначала используйте Get-MsolServicePrincipal, чтобы получить значение свойства AppPrincipalId для skype для бизнеса Server и основных служб Microsoft Exchange; Значение свойства AppPrincipalId будет использоваться для идентификации основного объекта-службы, назначенного сертификату. Используя значение свойства AppPrincipalId для Skype для бизнеса Server, назначьте сертификат версии Skype для бизнеса Online с помощью следующей команды:

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Затем необходимо повторить команду, на этот раз используя значение свойства AppPrincipalId для Exchange 2013.

Если позднее вам потребуется удалить этот сертификат, например, если срок его действия истек, вы можете сделать это, сначала получить KeyId для сертификата:

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

Помимо назначения сертификата, необходимо также настроить основное приложение-службу Exchange Online и url-адреса внешних веб-служб Skype для бизнеса Server в качестве основного сервера-службы Microsoft 365 или Office 365. Для этого можно использовать следующие две команды. 

В следующем примере Pool1ExternalWebFQDN.contoso.com url-адрес внешних веб-служб для пула Skype для бизнеса Server. Повторите эти действия, чтобы добавить все внешние URL-адреса веб-служб в развертывании.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
