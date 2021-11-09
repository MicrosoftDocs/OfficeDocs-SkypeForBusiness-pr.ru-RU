---
title: Настройка проверки подлинности от сервера к серверу для Skype для бизнеса Server гибридной среды
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: Сводка. Настройка проверки подлинности от сервера к серверу для Skype для бизнеса Server гибридной среды.
ms.openlocfilehash: 617c388dc4c4120beb457e4e2c90246e06c76d6d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830933"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Настройка проверки подлинности от сервера к серверу для Skype для бизнеса Server гибридной среды.

**Сводка:** Настройка проверки подлинности от сервера к серверу для Skype для бизнеса Server гибридной среды.

В гибридной конфигурации некоторые пользователи находятся в локальной установке Skype для бизнеса Server, а другие — в Microsoft 365 или Office 365 версии Skype для бизнеса Server. Чтобы настроить проверку подлинности от сервера к серверу в гибридной среде, сначала необходимо настроить локальное установку Skype для бизнеса Server, чтобы доверять серверу авторизации. Начальный шаг в этом процессе может быть выполнен при запуске следующего сценария Skype для бизнеса Server Management Shell:

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

Для выполнения этого сценария необходимо установить Skype для бизнеса PowerShell и подключиться к вашему клиенту с помощью этого модуля. Если вы не установили эти cmdlets, ваш сценарий не удастся, так как Get-CsTenant не будет доступен. После завершения сценария необходимо настроить доверительные отношения между Skype для бизнеса Server и сервером авторизации и второе отношение доверия между Exchange 2013/2016 и сервером авторизации. Это можно выполнить только с помощью командлетов Microsoft Online Services.

> [!NOTE]
> Если вы не установили Microsoft Online Services, вам потребуется установить его из репозитория PowerShell с помощью cmdlet `install-module MSOnline` . Подробные сведения об установке и использовании Microsoft Online Services модуля можно найти на Microsoft 365 веб-сайте. В этих инструкциях также будет указана настройка единого входного знака, федерации и синхронизации между Microsoft 365 или Office 365 и Active Directory. 



После настройки Microsoft 365 или Office 365, а также после создания Microsoft 365 или Office 365 для Skype для бизнеса Server и Exchange 2013 года необходимо зарегистрировать учетные данные с этими главами служб. Для этого необходимо сначала получить сертификат X.509 Base64, сохраненный в качестве . CER-файл. Затем этот сертификат будет применяться к Microsoft 365 или Office 365 службы.

Когда вы получили сертификат X.509, откройте консоль PowerShell и импортируете модуль Microsoft Online Windows PowerShell, содержащий командлеты, которые можно использовать для управления основными службами:

```PowerShell
Import-Module MSOnline
```

При импорте модуля введите следующую команду и нажмите кнопку ENTER:

```PowerShell
Connect-MsolService
```

После нажатия клавиши ВВОД отображается диалоговое окно. Введите Microsoft 365 или Office 365 имя пользователя и пароль в диалоговом окне, а затем нажмите кнопку ОК.

Как только вы подключились к Microsoft 365 или Office 365, вы можете выполнить следующую команду, чтобы вернуть сведения о главных службах:

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

Следующий этап состоит из импорта, кодирования и назначения сертификата X.509. Чтобы импортировать и кодировать сертификат, используйте следующие Windows PowerShell, чтобы указать полный путь к файлу. Файл CER при вызове метода Импорт:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

После импорта и закодирования сертификата можно назначить сертификат Microsoft 365 или Office 365 службы. Для этого сначала используйте Get-MsolServicePrincipal для получения значения свойства AppPrincipalId как для Skype для бизнеса Server, так и для Exchange майкрософт; значение свойства AppPrincipalId будет использоваться для определения доверенного объекта службы, назначенного сертификату. Со значением свойства AppPrincipalId для Skype для бизнеса Server в руке, используйте следующую команду, чтобы назначить сертификат для Skype для бизнеса Online версии:

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Затем следует повторить команду, на этот раз используя значение свойства AppPrincipalId для Exchange 2013.

Если позже необходимо удалить этот сертификат, например, если срок действия сертификата истек, вы можете сделать это, предварительно ирисовав keyId для сертификата:

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

Помимо назначения сертификата необходимо также настроить Exchange Online-директора службы и настроить локальной версии URL-адресов внешних веб-служб Skype для бизнеса Server как Microsoft 365 или Office 365. Это можно сделать с помощью следующих двух команд. 

В следующем примере Pool1ExternalWebFQDN.contoso.com url-адрес внешних веб-служб для Skype для бизнеса Server пула. Необходимо повторить эти действия, чтобы добавить все URL-адреса внешних веб-служб в развертывание.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
