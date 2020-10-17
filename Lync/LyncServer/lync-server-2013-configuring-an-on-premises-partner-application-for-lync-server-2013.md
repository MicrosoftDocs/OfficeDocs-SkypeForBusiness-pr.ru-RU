---
title: Настройка локального партнерского приложения для Lync Server 2013
description: Настройка локального партнерского приложения для Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring an on-premises partner application for Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48184412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0401634c6cb7afc451652ffbaf55cdc01a7ca89
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570925"
---
# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a><span data-ttu-id="450ff-103">Настройка локального приложения партнера для Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="450ff-103">Configuring an on-premises partner application for Microsoft Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="450ff-104">_**Последнее изменение темы:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="450ff-104">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="450ff-105">После назначения сертификата OAuthTokenIssuer необходимо настроить партнерские приложения Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="450ff-105">After you have assigned the OAuthTokenIssuer certificate you must then configure your Microsoft Lync Server 2013 partner applications.</span></span> <span data-ttu-id="450ff-106">(В описанной процедуре описывается настройка Microsoft Exchange Server 2013 и Microsoft SharePoint для работы в качестве партнерских приложений.) Чтобы настроить локальное партнерское приложение, необходимо сначала скопировать приведенный ниже сценарий Windows PowerShell и вставить код в Блокнот (или любой другой текстовый редактор):</span><span class="sxs-lookup"><span data-stu-id="450ff-106">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and Microsoft SharePoint to act as partner applications.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>

    if ((Get-CsPartnerApplication -ErrorAction SilentlyContinue) -ne $Null)
       {
           Remove-CsPartnerApplication app
       }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
    New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full 
               }
         }
    
    $shp = Get-CsPartnerApplication microsoft.sharepoint -ErrorAction SilentlyContinue
            
    if ($shp -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
        }
    else
        {
           if ($shp.ApplicationIdentifier -ne "00000003-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.sharepoint
      
                 New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
                }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="450ff-107">После копирования кода сохраните скрипт с помощью. Расширение файла PS1 (например, C: \\ scripts \\ServerToServerAuth.ps1).</span><span class="sxs-lookup"><span data-stu-id="450ff-107">After copying the code, save the script using a .PS1 file extension (for example, C:\\Scripts\\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="450ff-108">Обратите внимание, что перед выполнением этого сценария необходимо заменить URL-адреса метаданных https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 и http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx URL-адреса метаданных, используемые серверами Exchange 2013 и SharePoint соответственно.</span><span class="sxs-lookup"><span data-stu-id="450ff-108">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="450ff-109">Сведения о том, как определить URL-адрес метаданных соответствующего продукта, можно найти в документации по продукту Exchange 2013 и SharePoint.</span><span class="sxs-lookup"><span data-stu-id="450ff-109">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>

<span data-ttu-id="450ff-110">Если посмотреть на последнюю строку скрипта, можно заметить, что командлет Set-CsOAuthConfiguration вызывается помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="450ff-110">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="450ff-p103">Поскольку параметр Realm не использовался при вызове Set-CsOAuthConfiguration, область устанавливается автоматически как полное доменное имя организации (например, litwareinc.com). Если имя области отличается от имени организации, нужно указать имя области, например:</span><span class="sxs-lookup"><span data-stu-id="450ff-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

<span data-ttu-id="450ff-113">После внесения этих изменений можно выполнить скрипт и настроить для них как Exchange 2013, так и SharePoint как партнерские приложения, запустив файл скрипта из командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="450ff-113">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="450ff-114">Например:</span><span class="sxs-lookup"><span data-stu-id="450ff-114">For example:</span></span>

    C:\Scripts\ServerToServerAuth.ps1

<span data-ttu-id="450ff-115">Обратите внимание, что вы можете запустить этот сценарий, даже если у вас нет серверов Exchange 2013 и SharePoint Server:, если вы, скажем, настроили SharePoint Server как партнерское приложение, несмотря на то что у вас не установлен SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="450ff-115">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>

<span data-ttu-id="450ff-116">При выполнении этого скрипта может отображаться сообщение об ошибке, похожее на следующее:</span><span class="sxs-lookup"><span data-stu-id="450ff-116">When you run this script you might receive an error message similar to the following:</span></span>

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

<span data-ttu-id="450ff-p105">Это сообщение об ошибке обычно означает одно из двух: 1) один из URL-адресов, указанных в скрипте, недействительный (то есть один из URL-адресов метаданных не является фактическим URL-адресом метаданных); 2) не удалось связаться с одним из URL-адресов метаданных. В этом случае убедитесь, что заданы правильные и доступные URL-адреса, и повторно выполните скрипт.</span><span class="sxs-lookup"><span data-stu-id="450ff-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>

<span data-ttu-id="450ff-119">После создания партнерского приложения для Lync Server 2013 необходимо настроить Lync Server в качестве партнерского приложения для Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="450ff-119">After creating the partner application for Lync Server 2013 you must then configure Lync Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="450ff-120">Вы можете настроить партнерские приложения для Exchange 2013, выполнив Configure-EnterprisePartnerApplication.ps1 сценариев; все, что вам нужно сделать, — указать URL-адрес метаданных для Lync Server и указать, что Lync Server является новым партнерским приложением.</span><span class="sxs-lookup"><span data-stu-id="450ff-120">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Lync Server and indicate that Lync Server is the new partner application.</span></span>

<span data-ttu-id="450ff-121">Чтобы настроить Lync Server в качестве партнерского приложения для Exchange, откройте командную консоль Exchange и выполните команду, подобную следующей.</span><span class="sxs-lookup"><span data-stu-id="450ff-121">To configure Lync Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

