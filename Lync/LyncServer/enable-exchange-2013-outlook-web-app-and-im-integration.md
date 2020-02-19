---
title: Включение Exchange 2013 Outlook Web App и интеграция обмена мгновенными сообщениями
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da4289f663d62d1638c0f669e17a5e318e0788d3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="3210c-102">Включение Exchange 2013 Outlook Web App и интеграция обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="3210c-102">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3210c-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3210c-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3210c-104">Чтобы включить интеграцию с Exchange 2013 Outlook Web Access (OWA) и службу обмена мгновенными сообщениями с Lync Server 2013, необходимо добавить сервер сервера клиентского доступа Exchange 2013 в топологию Lync Server 2013 в качестве доверенного сервера приложений.</span><span class="sxs-lookup"><span data-stu-id="3210c-104">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="3210c-105">Чтобы создать пул доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="3210c-105">To create a trusted application pool</span></span>

1.  <span data-ttu-id="3210c-106">Запустите командную консоль Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3210c-106">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="3210c-107">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="3210c-107">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="3210c-108">Это вернет siteID для siteName, имени сайта, в котором следует создать пул.</span><span class="sxs-lookup"><span data-stu-id="3210c-108">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="3210c-109">Дополнительные сведения см. в статье [Get – CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) в документации по консоли управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3210c-109">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="3210c-110">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="3210c-110">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="3210c-111">Дополнительные сведения см. в статье [New – кструстедаппликатионпул](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) в документации по среде управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3210c-111">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="3210c-112">Полное доменное имя Exchange Server должно быть настроено в сертификате Exchange OWA как имя субъекта или альтернативное имя субъекта (SAN).</span><span class="sxs-lookup"><span data-stu-id="3210c-112">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="3210c-113">Убедитесь, что в Exchange OWA полное доменное имя пула также является доверенным.</span><span class="sxs-lookup"><span data-stu-id="3210c-113">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3210c-114">Если сервер CAS <EM>не</EM> размещен на том же сервере, на котором работает единая система обмена сообщениями Exchange 2013, пропустите оставшиеся действия, описанные в этой процедуре, и выполните процедуру "создание доверенного приложения для сервера клиентского доступа Exchange 2013" Далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="3210c-114">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="3210c-115">Если сервер CAS размещен на том же сервере, на котором работает единая система обмена сообщениями Exchange 2013, выполните действия, описанные в этой процедуре, и не выполняйте процедуру "создание доверенного приложения для сервера клиентского доступа Exchange 2013" Далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="3210c-115">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="3210c-116">Запустите **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="3210c-116">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="3210c-117">Откройте построитель топологий и загрузите текущую топологию.</span><span class="sxs-lookup"><span data-stu-id="3210c-117">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="3210c-118">На левой панели разверните дерево, пока не достигните узла **Серверы доверенных приложений**.</span><span class="sxs-lookup"><span data-stu-id="3210c-118">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="3210c-119">Разверните узел **Серверы доверенных приложений**.</span><span class="sxs-lookup"><span data-stu-id="3210c-119">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="3210c-120">Теперь сервер клиентского доступа Exchange 2013, указанный в качестве доверенного сервера приложений, должен отображаться как доверенный.</span><span class="sxs-lookup"><span data-stu-id="3210c-120">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="3210c-121">Создание доверенного приложения для сервера клиентского доступа Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="3210c-121">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="3210c-122">Запустите командную консоль Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3210c-122">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="3210c-123">Если сервер CAS *не* размещен на том же сервере, на котором работает единая система обмена сообщениями Exchange 2013, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="3210c-123">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="3210c-124">Для получения дополнительных сведений обратитесь к разделу [New – кструстедаппликатион](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) в документации по консоли управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3210c-124">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="3210c-125">Запустите **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="3210c-125">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="3210c-126">В построителе решений на левой панели разверните дерево, пока не достигните узла **Серверы доверенных приложений**.</span><span class="sxs-lookup"><span data-stu-id="3210c-126">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="3210c-127">Разверните узел **Серверы доверенных приложений**.</span><span class="sxs-lookup"><span data-stu-id="3210c-127">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="3210c-128">Теперь сервер клиентского доступа Exchange 2013, указанный в качестве доверенного сервера приложений, должен отображаться как доверенный.</span><span class="sxs-lookup"><span data-stu-id="3210c-128">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

