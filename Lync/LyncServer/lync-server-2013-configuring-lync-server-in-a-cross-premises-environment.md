---
title: 'Lync Server 2013: Настройка сервера Lync Server в нескольких локальных средах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02696b85921e2f408b7a7ec5531b0596aaef49ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a><span data-ttu-id="7d7c6-102">Настройка Microsoft Lync Server 2013 в нескольких локальных средах</span><span class="sxs-lookup"><span data-stu-id="7d7c6-102">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d7c6-103">_**Тема последнего изменения:** 2017-02-21_</span><span class="sxs-lookup"><span data-stu-id="7d7c6-103">_**Topic Last Modified:** 2017-02-21_</span></span>

<span data-ttu-id="7d7c6-104">В многолокальных конфигурациях некоторые пользователи находятся в локальной установке Microsoft Lync Server 2013, а другие пользователи находятся в версии Office 365 на Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-104">In a cross-premise configuration, some of your users are homed on an on-premises installation of Microsoft Lync Server 2013 while other users are homed on the Office 365 version of Lync Server.</span></span> <span data-ttu-id="7d7c6-105">Чтобы настроить проверку подлинности "сервер-сервер" в нескольких локальных средах, необходимо сначала настроить локальную установку Lync Server 2013, чтобы доверять серверу авторизации Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-105">In order to configure server-to-server authentication in a cross-premises environment, you must first configure your on-premises installation of Lync Server 2013 to trust the Office 365 Authorization server.</span></span> <span data-ttu-id="7d7c6-106">Чтобы выполнить этот процесс, запустите следующий сценарий оболочки управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-106">The initial step in this process can be carried out by running the following Lync Server Management Shell script:</span></span>

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

<span data-ttu-id="7d7c6-p102">Помните о том, что имя области для клиента обычно отличается от имени организации; на деле имя области почти всегда совпадает с идентификатором клиента. Поэтому первая строка скрипта используется для получения значения свойства TenantId для заданного клиента (в данном случае это fabrikam.com) и последующего назначения этого имени переменной $TenantId:</span><span class="sxs-lookup"><span data-stu-id="7d7c6-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

<span data-ttu-id="7d7c6-109">После завершения работы сценария необходимо настроить отношение доверия между Lync Server 2013 и сервером авторизации, а также вторым отношением доверия между Exchange 2013 и сервером авторизации.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-109">After the script completes you must then configure a trust relationship between Lync Server 2013 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="7d7c6-110">Это возможно только с помощью командлетов Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-110">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7d7c6-111">Если вы не установили командлеты Microsoft Online Services, перед продолжением вам потребуется выполнить два действия.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-111">If you have not installed the Microsoft Online Services cmdlets you will need to do two things before proceeding.</span></span> <span data-ttu-id="7d7c6-112">Во-первых, скачайте и установите 64-разрядную версию помощника по входу в Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-112">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="7d7c6-113">После завершения установки Скачайте и установите 64-разрядную версию модуля Microsoft Online Services для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-113">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="7d7c6-114">Подробные сведения об установке и использовании модуля Microsoft Online Services можно найти на веб-сайте Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-114">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="7d7c6-115">В этих инструкциях также рассказывается о том, как настроить единый вход, Федерацию и синхронизацию между Office 365 и Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-115">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span><BR><span data-ttu-id="7d7c6-116">Если вы не выполнили установку этих командлетов, то произойдет сбой вашего сценария, так как командлет Get-CsTenant будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-116">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>



</div>

<span data-ttu-id="7d7c6-117">После того как вы настроили Office 365, и после создания участников служб Office 365 для Lync Server 2013 и Exchange 2013, вам потребуется зарегистрировать ваши учетные данные для этих субъектов-служб.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-117">After you have configured Office 365, and after you have created Office 365 service principals for Lync Server 2013 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="7d7c6-118">Для этого необходимо сначала получить X.509 Base64 в виде файла CER.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-118">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="7d7c6-119">Этот сертификат будет затем применен к участникам службы Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="7d7c6-120">После получения сертификата X. 509 запустите модуль Microsoft Online Services (нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **веб-службы Майкрософт**, а затем — **модуль Microsoft Online Services для Windows PowerShell**).</span><span class="sxs-lookup"><span data-stu-id="7d7c6-120">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="7d7c6-121">После открытия модуля "службы" введите следующую команду для импорта модуля Microsoft Online Windows PowerShell, содержащего командлеты, которые можно использовать для управления субъектами-службами.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-121">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

    Import-Module MSOnlineExtended

<span data-ttu-id="7d7c6-122">После импорта модуля введите указанную ниже команду и нажмите клавишу ВВОД, чтобы подключиться к Office 365:</span><span class="sxs-lookup"><span data-stu-id="7d7c6-122">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

    Connect-MsolService

<span data-ttu-id="7d7c6-123">При нажатии клавиши Enter отображается диалоговое окно учетных данных.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-123">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="7d7c6-124">В диалоговом окне введите имя пользователя и пароль Office 365 и нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-124">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="7d7c6-125">После подключения к Office 365 вы можете выполнить следующую команду, чтобы получить сведения об участниках служб.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-125">As soon as you are connected to Office 365 you can then run the following command in order to return information about your service principals:</span></span>

    Get-MsolServicePrincipal

<span data-ttu-id="7d7c6-126">Команда возвращает для всех субъектов-служб сведения, похожие на следующие:</span><span class="sxs-lookup"><span data-stu-id="7d7c6-126">You should get back information similar to this for all your service principals:</span></span>

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

<span data-ttu-id="7d7c6-127">На следующем шаге выполняется импорт, кодирование и назначение сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-127">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="7d7c6-128">Для импорта и кодирования сертификата используйте указанные ниже команды Windows PowerShell, чтобы указать полный путь к файлу. CER при вызове метода Import:</span><span class="sxs-lookup"><span data-stu-id="7d7c6-128">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

<span data-ttu-id="7d7c6-129">После того как сертификат будет импортирован и закодирован, вы можете назначить сертификат участникам службы Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-129">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="7d7c6-130">Для этого сначала используйте Get-МсолсервицепринЦипал для получения значения свойства АпппринЦипалид как для сервера Lync, так и для участников службы Microsoft Exchange. значение свойства АпппринЦипалид будет использоваться для идентификации субъекта-службы, которому назначается сертификат.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-130">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Lync Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="7d7c6-131">С помощью значения свойства АпппринЦипалид для Lync Server 2013 можно назначить сертификат версии Office 365 для Lync Server (свойства StartDate и EndDate должны соответствовать сроку действия сертификата).</span><span class="sxs-lookup"><span data-stu-id="7d7c6-131">With the AppPrincipalId property value for Lync Server 2013 in hand, use the following command to assign the certificate to the Office 365 version of Lync Server (the StartDate and EndDate properties should correspond to the validity period for the certificate):</span></span>

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

<span data-ttu-id="7d7c6-132">Затем следует повторить команду, на этот раз используя значение свойства АпппринЦипалид для Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-132">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="7d7c6-133">Если позднее вам потребуется удалить этот сертификат, сначала вам потребуется получить для него значение KeyId:</span><span class="sxs-lookup"><span data-stu-id="7d7c6-133">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="7d7c6-134">Эта команда возвращает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="7d7c6-134">That command will return data like this one:</span></span>

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

<span data-ttu-id="7d7c6-135">После этого вы можете удалить сертификат с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="7d7c6-135">You can then delete the certificate by using a command similar to this:</span></span>

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

<span data-ttu-id="7d7c6-136">Помимо назначения сертификата необходимо также настроить субъект-службу Office 365 для Exchange Online, добавив имя участника сервера для локальной версии Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-136">In addition to assigning a certificate you must also configure the Office 365 Service Principal for Exchange Online by adding the Server Principal Name for your on-premise version of Lync Server 2013.</span></span> <span data-ttu-id="7d7c6-137">Это можно сделать, выполнив следующие четыре строки в сеансе PowerShell Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="7d7c6-137">This can be done by running the following four lines in a Microsoft Online Services PowerShell session:</span></span>

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

