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
ms.openlocfilehash: a95f2fba2d65f0d25f1fa9b843dd7bb47240aa6c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a><span data-ttu-id="da15e-102">Настройка Microsoft Lync Server 2013 в распределенной среде</span><span class="sxs-lookup"><span data-stu-id="da15e-102">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da15e-103">_**Последнее изменение темы:** 2017-02-21_</span><span class="sxs-lookup"><span data-stu-id="da15e-103">_**Topic Last Modified:** 2017-02-21_</span></span>

<span data-ttu-id="da15e-104">В конфигурации с несколькими локальными пользователями некоторые пользователи размещаются в локальной установке Microsoft Lync Server 2013, в то время как другие пользователи размещены в версии Lync Server для Office 365.</span><span class="sxs-lookup"><span data-stu-id="da15e-104">In a cross-premise configuration, some of your users are homed on an on-premises installation of Microsoft Lync Server 2013 while other users are homed on the Office 365 version of Lync Server.</span></span> <span data-ttu-id="da15e-105">Чтобы настроить межсерверную проверку подлинности в распределенной среде, необходимо сначала настроить локальную установку Lync Server 2013, чтобы доверять серверу авторизации Office 365.</span><span class="sxs-lookup"><span data-stu-id="da15e-105">In order to configure server-to-server authentication in a cross-premises environment, you must first configure your on-premises installation of Lync Server 2013 to trust the Office 365 Authorization server.</span></span> <span data-ttu-id="da15e-106">Для выполнения этого процесса можно выполнить следующий сценарий консоли управления Lync Server:</span><span class="sxs-lookup"><span data-stu-id="da15e-106">The initial step in this process can be carried out by running the following Lync Server Management Shell script:</span></span>

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

<span data-ttu-id="da15e-p102">Помните о том, что имя области для клиента обычно отличается от имени организации; на деле имя области почти всегда совпадает с идентификатором клиента. Поэтому первая строка скрипта используется для получения значения свойства TenantId для заданного клиента (в данном случае это fabrikam.com) и последующего назначения этого имени переменной $TenantId:</span><span class="sxs-lookup"><span data-stu-id="da15e-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

<span data-ttu-id="da15e-109">После выполнения сценария необходимо настроить отношение доверия между Lync Server 2013 и сервером авторизации, а также второе отношение доверия между Exchange 2013 и сервером авторизации.</span><span class="sxs-lookup"><span data-stu-id="da15e-109">After the script completes you must then configure a trust relationship between Lync Server 2013 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="da15e-110">Это можно выполнить только с помощью командлетов Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="da15e-110">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da15e-111">Если вы еще не установили командлеты Microsoft Online Services, то для продолжения вам потребуется выполнить две операции.</span><span class="sxs-lookup"><span data-stu-id="da15e-111">If you have not installed the Microsoft Online Services cmdlets you will need to do two things before proceeding.</span></span> <span data-ttu-id="da15e-112">Во-первых, загрузите и установите 64-разрядную версию помощника по входу в Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="da15e-112">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="da15e-113">После завершения установки Скачайте и установите 64-разрядную версию модуля Microsoft Online Services для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da15e-113">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="da15e-114">Подробные сведения об установке и использовании модуля Microsoft Online Services см. на веб-сайте, посвященном Office 365.</span><span class="sxs-lookup"><span data-stu-id="da15e-114">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="da15e-115">Данные инструкции также помогут вам настроить единый вход, федерацию и синхронизацию между Office 365 и Active Directory.</span><span class="sxs-lookup"><span data-stu-id="da15e-115">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span><BR><span data-ttu-id="da15e-116">Если вы не установили эти командлеты, сценарий завершится с ошибками, так как командлет Get-CsTenant будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="da15e-116">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>



</div>

<span data-ttu-id="da15e-117">После настройки Office 365 и создания субъектов службы Office 365 для Lync Server 2013 и Exchange 2013 необходимо зарегистрировать учетные данные этих субъектов службы.</span><span class="sxs-lookup"><span data-stu-id="da15e-117">After you have configured Office 365, and after you have created Office 365 service principals for Lync Server 2013 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="da15e-118">Для этого вам следует сначала получить X.509 Base64 в виде файла CER.</span><span class="sxs-lookup"><span data-stu-id="da15e-118">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="da15e-119">После этого данный сертификат применяется к субъектам-службам Office 365.</span><span class="sxs-lookup"><span data-stu-id="da15e-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="da15e-120">После получения сертификата X. 509 запустите модуль Microsoft Online Services (нажмите кнопку **Пуск**, выберите **все программы**, затем **Microsoft Online Services**, а затем выберите **модуль Microsoft Online Services для Windows PowerShell**).</span><span class="sxs-lookup"><span data-stu-id="da15e-120">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="da15e-121">После открытия модуля "службы" введите следующую команду, чтобы импортировать модуль Microsoft Online Windows PowerShell, содержащий командлеты, которые можно использовать для управления субъектами-службами:</span><span class="sxs-lookup"><span data-stu-id="da15e-121">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

    Import-Module MSOnlineExtended

<span data-ttu-id="da15e-122">После завершения импорта модуля введите следующую команду и нажмите клавишу ВВОД для подключения к Office 365:</span><span class="sxs-lookup"><span data-stu-id="da15e-122">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

    Connect-MsolService

<span data-ttu-id="da15e-p107">После нажатия клавиши ВВОД отображается диалоговое окно. Введите в нем имя пользователя и пароль Office 365, а затем нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="da15e-p107">After you press ENTER, a credentials dialog box will appear. Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="da15e-125">После подключения к Office 365 вы можете запустить следующую команду для получения информации о субъектах-службах:</span><span class="sxs-lookup"><span data-stu-id="da15e-125">As soon as you are connected to Office 365 you can then run the following command in order to return information about your service principals:</span></span>

    Get-MsolServicePrincipal

<span data-ttu-id="da15e-126">Команда возвращает для всех субъектов-служб сведения, похожие на следующие:</span><span class="sxs-lookup"><span data-stu-id="da15e-126">You should get back information similar to this for all your service principals:</span></span>

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

<span data-ttu-id="da15e-127">Следующий этап состоит из импорта, кодирования и назначения сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="da15e-127">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="da15e-128">Чтобы импортировать и закодировать сертификат, используйте следующие команды Windows PowerShell, чтобы указать полный путь к файлу. CER-файл при вызове метода Import:</span><span class="sxs-lookup"><span data-stu-id="da15e-128">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

<span data-ttu-id="da15e-129">После завершения импорта и кодирования сертификата вы можете назначить его своим субъектам-службам Office 365.</span><span class="sxs-lookup"><span data-stu-id="da15e-129">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="da15e-130">Для этого сначала воспользуйтесь командлетом Get-MsolServicePrincipal, чтобы извлечь значение свойства AppPrincipalId для субъектов-служб Lync Server и Microsoft Exchange; это значение свойства AppPrincipalId будет использоваться для идентификации субъекта-службы, которому назначается сертификат.</span><span class="sxs-lookup"><span data-stu-id="da15e-130">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Lync Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="da15e-131">С помощью значения свойства AppPrincipalId для Lync Server 2013 в наличии выполните следующую команду, чтобы назначить сертификат версии Office 365 для Lync Server (свойства StartDate и EndDate должны соответствовать сроку действия сертификата):</span><span class="sxs-lookup"><span data-stu-id="da15e-131">With the AppPrincipalId property value for Lync Server 2013 in hand, use the following command to assign the certificate to the Office 365 version of Lync Server (the StartDate and EndDate properties should correspond to the validity period for the certificate):</span></span>

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

<span data-ttu-id="da15e-132">Затем необходимо повторить команду, на этот раз используя значение свойства AppPrincipalId для Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="da15e-132">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="da15e-133">Если позднее вам потребуется удалить этот сертификат, сначала вам потребуется получить для него значение KeyId:</span><span class="sxs-lookup"><span data-stu-id="da15e-133">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="da15e-134">Эта команда возвращает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="da15e-134">That command will return data like this one:</span></span>

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

<span data-ttu-id="da15e-135">После этого вы можете удалить сертификат с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="da15e-135">You can then delete the certificate by using a command similar to this:</span></span>

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

<span data-ttu-id="da15e-136">В дополнение к назначению сертификата необходимо также настроить субъект-службу Office 365 для Exchange Online, добавив имя участника сервера для локальной версии Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da15e-136">In addition to assigning a certificate you must also configure the Office 365 Service Principal for Exchange Online by adding the Server Principal Name for your on-premise version of Lync Server 2013.</span></span> <span data-ttu-id="da15e-137">Это можно сделать, выполнив следующие четыре строки в сеансе PowerShell Microsoft Online Services:</span><span class="sxs-lookup"><span data-stu-id="da15e-137">This can be done by running the following four lines in a Microsoft Online Services PowerShell session:</span></span>

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

