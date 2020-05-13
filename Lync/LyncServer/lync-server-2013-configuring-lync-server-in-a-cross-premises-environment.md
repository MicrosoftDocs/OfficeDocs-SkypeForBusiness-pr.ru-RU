---
title: 'Lync Server 2013: Настройка Lync Server в распределенной среде'
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
ms.openlocfilehash: 7dcbdb7ac12dcb8fc768a1f9e537622d01191b8f
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a><span data-ttu-id="f4971-102">Настройка Microsoft Lync Server 2013 в распределенной среде</span><span class="sxs-lookup"><span data-stu-id="f4971-102">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4971-103">_**Последнее изменение темы:** 2017-02-21_</span><span class="sxs-lookup"><span data-stu-id="f4971-103">_**Topic Last Modified:** 2017-02-21_</span></span>

<span data-ttu-id="f4971-104">В конфигурации с несколькими локальными пользователями некоторые пользователи размещаются в локальной установке Microsoft Lync Server 2013, в то время как другие пользователи размещены в версии Lync Server для Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4971-104">In a cross-premise configuration, some of your users are homed on an on-premises installation of Microsoft Lync Server 2013 while other users are homed on the Microsoft 365 or Office 365 version of Lync Server.</span></span> <span data-ttu-id="f4971-105">Чтобы настроить межсерверную проверку подлинности в распределенной среде, необходимо сначала настроить локальную установку Lync Server 2013, чтобы доверять серверу авторизации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f4971-105">In order to configure server-to-server authentication in a cross-premises environment, you must first configure your on-premises installation of Lync Server 2013 to trust the Microsoft 365 Authorization server.</span></span> <span data-ttu-id="f4971-106">Для выполнения этого процесса можно выполнить следующий сценарий консоли управления Lync Server:</span><span class="sxs-lookup"><span data-stu-id="f4971-106">The initial step in this process can be carried out by running the following Lync Server Management Shell script:</span></span>

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

<span data-ttu-id="f4971-p102">Помните о том, что имя области для клиента обычно отличается от имени организации; на деле имя области почти всегда совпадает с идентификатором клиента. Поэтому первая строка скрипта используется для получения значения свойства TenantId для заданного клиента (в данном случае это fabrikam.com) и последующего назначения этого имени переменной $TenantId:</span><span class="sxs-lookup"><span data-stu-id="f4971-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

<span data-ttu-id="f4971-109">После выполнения сценария необходимо настроить отношение доверия между Lync Server 2013 и сервером авторизации, а также второе отношение доверия между Exchange 2013 и сервером авторизации.</span><span class="sxs-lookup"><span data-stu-id="f4971-109">After the script completes you must then configure a trust relationship between Lync Server 2013 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="f4971-110">Это можно выполнить только с помощью командлетов Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="f4971-110">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f4971-111">Если вы еще не установили командлеты Microsoft Online Services, то для продолжения вам потребуется выполнить две операции.</span><span class="sxs-lookup"><span data-stu-id="f4971-111">If you have not installed the Microsoft Online Services cmdlets you will need to do two things before proceeding.</span></span> <span data-ttu-id="f4971-112">Во-первых, загрузите и установите 64-разрядную версию помощника по входу в Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="f4971-112">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="f4971-113">После завершения установки Скачайте и установите 64-разрядную версию модуля Microsoft Online Services для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4971-113">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="f4971-114">Подробные сведения об установке и использовании модуля Microsoft Online Services можно найти на веб-сайте Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4971-114">Detailed information for installing and using the Microsoft Online Services Module can be found on the Microsoft 365 or Office 365 web site.</span></span> <span data-ttu-id="f4971-115">В этих инструкциях также рассказывается, как настроить единый вход, Федерацию и синхронизацию между Microsoft 365 или Office 36 и Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f4971-115">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Microsoft 365 or Office 36 and Active Directory.</span></span><BR><span data-ttu-id="f4971-116">Если вы не установили эти командлеты, сценарий завершится с ошибками, так как командлет Get-CsTenant будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="f4971-116">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>



</div>

<span data-ttu-id="f4971-117">После того как вы настроили Microsoft 365 и создали субъекты службы Microsoft 365 или Office 365 для Lync Server 2013 и Exchange 2013, вам потребуется зарегистрировать учетные данные этих субъектов службы.</span><span class="sxs-lookup"><span data-stu-id="f4971-117">After you have configured Microsoft 365, and after you have created Microsoft 365 or Office 365 service principals for Lync Server 2013 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="f4971-118">Для этого вам следует сначала получить X.509 Base64 в виде файла CER.</span><span class="sxs-lookup"><span data-stu-id="f4971-118">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="f4971-119">Затем этот сертификат будет применяться к субъектам служб Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4971-119">This certificate will then be applied to the Microsoft 365 or Office 365 service principals.</span></span>

<span data-ttu-id="f4971-120">После получения сертификата X. 509 запустите модуль Microsoft Online Services (нажмите кнопку **Пуск**, выберите **все программы**, затем **Microsoft Online Services**, а затем выберите **модуль Microsoft Online Services для Windows PowerShell**).</span><span class="sxs-lookup"><span data-stu-id="f4971-120">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="f4971-121">После открытия модуля "службы" введите следующую команду, чтобы импортировать модуль Microsoft Online Windows PowerShell, содержащий командлеты, которые можно использовать для управления субъектами-службами:</span><span class="sxs-lookup"><span data-stu-id="f4971-121">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

    Import-Module MSOnlineExtended

<span data-ttu-id="f4971-122">После импорта модуля введите следующую команду и нажмите клавишу ВВОД, чтобы подключиться к Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="f4971-122">When the module has been imported, type the following command and then press ENTER in order to connect to Microsoft 365:</span></span>

    Connect-MsolService

<span data-ttu-id="f4971-123">После нажатия клавиши ВВОД отображается диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="f4971-123">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="f4971-124">Введите в диалоговом окне имя пользователя и пароль Microsoft 365 или Office 365, а затем нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="f4971-124">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="f4971-125">После подключения к Microsoft 365 можно выполнить следующую команду, чтобы получить сведения о субъектах службы:</span><span class="sxs-lookup"><span data-stu-id="f4971-125">As soon as you are connected to Microsoft 365 you can then run the following command in order to return information about your service principals:</span></span>

    Get-MsolServicePrincipal

<span data-ttu-id="f4971-126">Команда возвращает для всех субъектов-служб сведения, похожие на следующие:</span><span class="sxs-lookup"><span data-stu-id="f4971-126">You should get back information similar to this for all your service principals:</span></span>

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

<span data-ttu-id="f4971-127">Следующий этап состоит из импорта, кодирования и назначения сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="f4971-127">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="f4971-128">Чтобы импортировать и закодировать сертификат, используйте следующие команды Windows PowerShell, чтобы указать полный путь к файлу. CER-файл при вызове метода Import:</span><span class="sxs-lookup"><span data-stu-id="f4971-128">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

<span data-ttu-id="f4971-129">После импорта и кодирования сертификата вы можете назначить сертификат для участников службы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f4971-129">After the certificate has been imported and encoded, you can then assign the certificate to your Microsoft 365 service principals.</span></span> <span data-ttu-id="f4971-130">Для этого сначала воспользуйтесь командлетом Get-MsolServicePrincipal, чтобы извлечь значение свойства AppPrincipalId для субъектов-служб Lync Server и Microsoft Exchange; это значение свойства AppPrincipalId будет использоваться для идентификации субъекта-службы, которому назначается сертификат.</span><span class="sxs-lookup"><span data-stu-id="f4971-130">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Lync Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="f4971-131">Используя значение свойства AppPrincipalId для Lync Server 2013, выполните следующую команду, чтобы назначить сертификат для версии Lync Server для Microsoft 365 (свойства StartDate и EndDate должны соответствовать сроку действия сертификата):</span><span class="sxs-lookup"><span data-stu-id="f4971-131">With the AppPrincipalId property value for Lync Server 2013 in hand, use the following command to assign the certificate to the Microsoft 365 version of Lync Server (the StartDate and EndDate properties should correspond to the validity period for the certificate):</span></span>

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

<span data-ttu-id="f4971-132">Затем необходимо повторить команду, на этот раз используя значение свойства AppPrincipalId для Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="f4971-132">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="f4971-133">Если позднее вам потребуется удалить этот сертификат, сначала вам потребуется получить для него значение KeyId:</span><span class="sxs-lookup"><span data-stu-id="f4971-133">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="f4971-134">Эта команда возвращает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="f4971-134">That command will return data like this one:</span></span>

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

<span data-ttu-id="f4971-135">После этого вы можете удалить сертификат с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="f4971-135">You can then delete the certificate by using a command similar to this:</span></span>

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

<span data-ttu-id="f4971-136">В дополнение к назначению сертификата необходимо также настроить субъект-службу Microsoft 365 для Exchange Online, добавив имя участника сервера для локальной версии Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4971-136">In addition to assigning a certificate you must also configure the Microsoft 365 Service Principal for Exchange Online by adding the Server Principal Name for your on-premise version of Lync Server 2013.</span></span> <span data-ttu-id="f4971-137">Это можно сделать, выполнив следующие четыре строки в сеансе PowerShell Microsoft Online Services:</span><span class="sxs-lookup"><span data-stu-id="f4971-137">This can be done by running the following four lines in a Microsoft Online Services PowerShell session:</span></span>

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

