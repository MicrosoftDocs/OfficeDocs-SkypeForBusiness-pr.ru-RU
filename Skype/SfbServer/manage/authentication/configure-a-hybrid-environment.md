---
title: Настройка проверки подлинности "сервер-сервер" для гибридной среды Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Сводка: Настройка проверки подлинности серверов и серверов для гибридной среды Skype для бизнеса Server.'
ms.openlocfilehash: 2879a1acc35a2c8928a95af913476c26028d6e6c
ms.sourcegitcommit: 1721acdd507591d16a4e766b390b997979d985e5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "37305775"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="35e8b-103">Настройка проверки подлинности "сервер-сервер" для гибридной среды Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="35e8b-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="35e8b-104">**Сводка:** Настройка проверки подлинности "сервер-сервер" в гибридной среде Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="35e8b-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="35e8b-105">В гибридной конфигурации некоторые пользователи размещаются в локальной установке Skype для бизнеса Server, в то время как другие пользователи находятся в версии Office 365 для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="35e8b-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="35e8b-106">Чтобы настроить проверку подлинности "сервер-сервер" в гибридной среде, необходимо сначала настроить локальную установку Skype для бизнеса Server, чтобы доверять серверу авторизации Office 365.</span><span class="sxs-lookup"><span data-stu-id="35e8b-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the Office 365 authorization server.</span></span> <span data-ttu-id="35e8b-107">Чтобы выполнить этот процесс, выполните следующие действия в сценарии командной консоли для управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="35e8b-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

```
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

<span data-ttu-id="35e8b-p102">Помните о том, что имя области для клиента обычно отличается от имени организации; на деле имя области почти всегда совпадает с идентификатором клиента. Поэтому первая строка скрипта используется для получения значения свойства TenantId для заданного клиента (в данном случае это fabrikam.com) и последующего назначения этого имени переменной $TenantId:</span><span class="sxs-lookup"><span data-stu-id="35e8b-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="35e8b-110">Для выполнения этого сценария необходимо установить модуль PowerShell Skype для бизнеса Online и подключиться к вашему клиенту с помощью этого модуля.</span><span class="sxs-lookup"><span data-stu-id="35e8b-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="35e8b-111">Если вы не выполнили установку этих командлетов, то произойдет сбой вашего сценария, так как командлет Get-CsTenant будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="35e8b-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="35e8b-112">После завершения работы сценария необходимо настроить доверительные отношения между Skype для бизнеса Server и сервером авторизации, а также второе отношение доверия между Exchange 2013/2016 и сервером авторизации.</span><span class="sxs-lookup"><span data-stu-id="35e8b-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="35e8b-113">Это возможно только с помощью командлетов Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="35e8b-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="35e8b-114">Если вы не установили командлеты Microsoft Online Services, вам нужно будет установить его из репозитория PowerShell с помощью командлета `install-module MSOnline`.</span><span class="sxs-lookup"><span data-stu-id="35e8b-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="35e8b-115">Подробные сведения об установке и использовании модуля Microsoft Online Services можно найти на веб-сайте Office 365.</span><span class="sxs-lookup"><span data-stu-id="35e8b-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="35e8b-116">В этих инструкциях также рассказывается о том, как настроить единый вход, Федерацию и синхронизацию между Office 365 и Active Directory.</span><span class="sxs-lookup"><span data-stu-id="35e8b-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 



<span data-ttu-id="35e8b-117">После настройки Office 365 и создания субъектов-служб Office 365 для Skype для бизнеса Server и Exchange 2013 вы должны зарегистрировать свои учетные данные для этих субъектов-служб.</span><span class="sxs-lookup"><span data-stu-id="35e8b-117">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="35e8b-118">Для этого сначала необходимо получить сертификат X. 509 Base64, сохраненный как. Файл CER.</span><span class="sxs-lookup"><span data-stu-id="35e8b-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="35e8b-119">Этот сертификат будет затем применен к участникам службы Office 365.</span><span class="sxs-lookup"><span data-stu-id="35e8b-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="35e8b-120">После получения сертификата X. 509 откройте консоль PowerShell и импортируйте модуль Microsoft Online Windows PowerShell, содержащий командлеты, которые можно использовать для управления субъектами служб.</span><span class="sxs-lookup"><span data-stu-id="35e8b-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```
Import-Module MSOnline
```

<span data-ttu-id="35e8b-121">После импорта модуля введите указанную ниже команду и нажмите клавишу ВВОД, чтобы подключиться к Office 365:</span><span class="sxs-lookup"><span data-stu-id="35e8b-121">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

```
Connect-MsolService
```

<span data-ttu-id="35e8b-122">При нажатии клавиши Enter отображается диалоговое окно учетных данных.</span><span class="sxs-lookup"><span data-stu-id="35e8b-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="35e8b-123">В диалоговом окне введите имя пользователя и пароль Office 365 и нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="35e8b-123">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="35e8b-124">После подключения к Office 365 вы можете выполнить следующую команду, чтобы получить сведения об участниках службы.</span><span class="sxs-lookup"><span data-stu-id="35e8b-124">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```
Get-MsolServicePrincipal
```

<span data-ttu-id="35e8b-125">Команда возвращает для всех субъектов-служб сведения, похожие на следующие:</span><span class="sxs-lookup"><span data-stu-id="35e8b-125">You should get back information similar to this for all your service principals:</span></span>

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

<span data-ttu-id="35e8b-126">На следующем шаге выполняется импорт, кодирование и назначение сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="35e8b-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="35e8b-127">Для импорта и кодирования сертификата используйте указанные ниже команды Windows PowerShell, чтобы указать полный путь к файлу. CER при вызове метода Import:</span><span class="sxs-lookup"><span data-stu-id="35e8b-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="35e8b-128">После того как сертификат будет импортирован и закодирован, вы можете назначить сертификат участникам службы Office 365.</span><span class="sxs-lookup"><span data-stu-id="35e8b-128">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="35e8b-129">Для этого сначала используйте Get-МсолсервицепринЦипал для получения значения свойства АпппринЦипалид как для сервера Skype для бизнеса, так и для участников службы Microsoft Exchange. значение свойства АпппринЦипалид будет использоваться для идентификации субъекта-службы, которому назначается сертификат.</span><span class="sxs-lookup"><span data-stu-id="35e8b-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="35e8b-130">С помощью значения свойства АпппринЦипалид в Skype для бизнеса Server вы можете присвоить сертификат для версии Skype для бизнеса Online, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="35e8b-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="35e8b-131">Затем следует повторить команду, на этот раз используя значение свойства АпппринЦипалид для Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="35e8b-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="35e8b-132">Если позже вам потребуется удалить этот сертификат, например, если срок его действия истек, сначала нужно получить Кэйид сертификата.</span><span class="sxs-lookup"><span data-stu-id="35e8b-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="35e8b-133">Эта команда возвращает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="35e8b-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="35e8b-134">После этого вы можете удалить сертификат с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="35e8b-134">You can then delete the certificate by using a command similar to this:</span></span>

```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="35e8b-135">Помимо назначения сертификата необходимо также настроить участника службы Exchange Online и настроить локальную версию веб-службы Skype для бизнеса Server как участника обслуживания Office 365.</span><span class="sxs-lookup"><span data-stu-id="35e8b-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="35e8b-136">Для этого можно выполнить две следующие команды:</span><span class="sxs-lookup"><span data-stu-id="35e8b-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="35e8b-137">В следующем примере Pool1ExternalWebFQDN.contoso.com — URL-адрес внешней веб-службы для пула сервера Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="35e8b-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="35e8b-138">Вы должны повторить эти действия, чтобы добавить URL-адреса внешних веб-служб в развертывание.</span><span class="sxs-lookup"><span data-stu-id="35e8b-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
