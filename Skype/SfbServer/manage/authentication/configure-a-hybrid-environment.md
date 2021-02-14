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
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="5d385-103">Настройка проверки подлинности "сервер-сервер" для гибридной среды Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5d385-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="5d385-104">**Сводка:** Настройка проверки подлинности "сервер-сервер" для гибридной среды Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5d385-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="5d385-105">В гибридной конфигурации некоторые пользователи находятся в локальной установке Skype для бизнеса Server, а другие — в версии Microsoft 365 или Office 365 Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5d385-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Microsoft 365 or Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="5d385-106">Чтобы настроить проверку подлинности "сервер-сервер" в гибридной среде, необходимо сначала настроить локальной установке Skype для бизнеса Server доверие серверу авторизации.</span><span class="sxs-lookup"><span data-stu-id="5d385-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the authorization server.</span></span> <span data-ttu-id="5d385-107">Для начального шага этого процесса можно использовать следующий сценарий в оболочке управления Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="5d385-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

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

<span data-ttu-id="5d385-p102">Помните о том, что имя области для клиента обычно отличается от имени организации; на деле имя области почти всегда совпадает с идентификатором клиента. Поэтому первая строка скрипта используется для получения значения свойства TenantId для заданного клиента (в данном случае это fabrikam.com) и последующего назначения этого имени переменной $TenantId:</span><span class="sxs-lookup"><span data-stu-id="5d385-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="5d385-110">Для выполнения этого сценария необходимо установить модуль PowerShell Skype для бизнеса Online и подключиться к вашему арендатору с помощью этого модуля.</span><span class="sxs-lookup"><span data-stu-id="5d385-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="5d385-111">Если эти cmdlets не установлены, то сценарий не будет работать, так как Get-CsTenant не будет доступен.</span><span class="sxs-lookup"><span data-stu-id="5d385-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="5d385-112">После выполнения сценария необходимо настроить отношение доверия между Skype для бизнеса Server и сервером авторизации, а также второе отношение доверия между Exchange 2013/2016 и сервером авторизации.</span><span class="sxs-lookup"><span data-stu-id="5d385-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="5d385-113">Это можно выполнить только с помощью командлетов Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="5d385-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="5d385-114">Если вы не установили Microsoft Online Services, необходимо установить его из репозитория PowerShell с помощью этого. `install-module MSOnline`</span><span class="sxs-lookup"><span data-stu-id="5d385-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="5d385-115">Подробные сведения об установке и использовании модуля Microsoft Online Services можно найти на веб-сайте Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5d385-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Microsoft 365 web site.</span></span> <span data-ttu-id="5d385-116">В этих инструкциях также посясят, как настроить единый вход, федерацию и синхронизацию между Microsoft 365 или Office 365 и Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5d385-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Microsoft 365 or Office 365 and Active Directory.</span></span> 



<span data-ttu-id="5d385-117">После настройки Microsoft 365 или Office 365 и создания основных служб Microsoft 365 или Office 365 для Skype для бизнеса Server и Exchange 2013 вам потребуется зарегистрировать свои учетные данные в этих компаниях-службах.</span><span class="sxs-lookup"><span data-stu-id="5d385-117">After you have configured Microsoft 365 or Office 365, and after you have created Microsoft 365 or Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="5d385-118">Для этого необходимо сначала получить сертификат X.509 Base64, сохраненный в качестве . CER-файл.</span><span class="sxs-lookup"><span data-stu-id="5d385-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="5d385-119">Затем этот сертификат будет применен к основным службам Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d385-119">This certificate will then be applied to the Microsoft 365 or Office 365 service principals.</span></span>

<span data-ttu-id="5d385-120">Получив сертификат X.509, откройте консоль PowerShell и импортируете модуль Microsoft Online Windows PowerShell, содержащий командлеты, которые можно использовать для управления основными службами:</span><span class="sxs-lookup"><span data-stu-id="5d385-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```PowerShell
Import-Module MSOnline
```

<span data-ttu-id="5d385-121">После импорта модуля введите следующую команду и нажмите ввод:</span><span class="sxs-lookup"><span data-stu-id="5d385-121">When the module has been imported, type the following command and then press ENTER:</span></span>

```PowerShell
Connect-MsolService
```

<span data-ttu-id="5d385-122">После нажатия клавиши ВВОД отображается диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="5d385-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="5d385-123">Введите имя пользователя и пароль Microsoft 365 или Office 365 в диалоговом окне и нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="5d385-123">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="5d385-124">Как только вы подключились к Microsoft 365 или Office 365, вы можете выполнить следующую команду, чтобы получить сведения о своих основных службах:</span><span class="sxs-lookup"><span data-stu-id="5d385-124">As soon as you are connected to Microsoft 365 or Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```PowerShell
Get-MsolServicePrincipal
```

<span data-ttu-id="5d385-125">Команда возвращает для всех субъектов-служб сведения, похожие на следующие:</span><span class="sxs-lookup"><span data-stu-id="5d385-125">You should get back information similar to this for all your service principals:</span></span>

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

<span data-ttu-id="5d385-126">Следующий этап состоит из импорта, кодирования и назначения сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="5d385-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="5d385-127">Чтобы импортировать и закодировать сертификат, используйте следующие команды Windows PowerShell, указав полный путь к файлу. CER-файл при вызове метода Import:</span><span class="sxs-lookup"><span data-stu-id="5d385-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

<span data-ttu-id="5d385-128">После импорта и кодирования сертификата вы можете назначить его своим основной службе Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d385-128">After the certificate has been imported and encoded, you can then assign the certificate to your Microsoft 365 or Office 365 service principals.</span></span> <span data-ttu-id="5d385-129">Для этого сначала используйте Get-MsolServicePrincipal, чтобы получить значение свойства AppPrincipalId для skype для бизнеса Server и основных служб Microsoft Exchange; Значение свойства AppPrincipalId будет использоваться для идентификации основного объекта-службы, назначенного сертификату.</span><span class="sxs-lookup"><span data-stu-id="5d385-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="5d385-130">Используя значение свойства AppPrincipalId для Skype для бизнеса Server, назначьте сертификат версии Skype для бизнеса Online с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="5d385-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="5d385-131">Затем необходимо повторить команду, на этот раз используя значение свойства AppPrincipalId для Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="5d385-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="5d385-132">Если позднее вам потребуется удалить этот сертификат, например, если срок его действия истек, вы можете сделать это, сначала получить KeyId для сертификата:</span><span class="sxs-lookup"><span data-stu-id="5d385-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="5d385-133">Эта команда возвращает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="5d385-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="5d385-134">После этого вы можете удалить сертификат с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="5d385-134">You can then delete the certificate by using a command similar to this:</span></span>

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="5d385-135">Помимо назначения сертификата, необходимо также настроить основное приложение-службу Exchange Online и url-адреса внешних веб-служб Skype для бизнеса Server в качестве основного сервера-службы Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d385-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as a Microsoft 365 or Office 365 service principal.</span></span> <span data-ttu-id="5d385-136">Для этого можно использовать следующие две команды.</span><span class="sxs-lookup"><span data-stu-id="5d385-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="5d385-137">В следующем примере Pool1ExternalWebFQDN.contoso.com url-адрес внешних веб-служб для пула Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5d385-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="5d385-138">Повторите эти действия, чтобы добавить все ВНЕШНИЕ URL-адреса веб-служб в развертывании.</span><span class="sxs-lookup"><span data-stu-id="5d385-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
