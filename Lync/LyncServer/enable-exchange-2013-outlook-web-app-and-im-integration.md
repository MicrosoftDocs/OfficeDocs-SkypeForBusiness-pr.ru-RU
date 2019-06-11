---
title: Включение Exchange 2013 Outlook Web App и интеграции с помощью мгновенных сообщений
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69df3f33f0671d3014e90859fd39cc2b85f9558b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="22204-102">Включение Exchange 2013 Outlook Web App и интеграции с помощью мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="22204-102">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22204-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="22204-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="22204-104">Для обеспечения интеграции Exchange 2013 Outlook Web Access (OWA) и обмена мгновенными сообщениями с Lync Server 2013 необходимо добавить сервер клиентского доступа Exchange 2013 в топологию Lync Server 2013 как доверенный сервер приложений.</span><span class="sxs-lookup"><span data-stu-id="22204-104">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="22204-105">Создание надежного пула приложений</span><span class="sxs-lookup"><span data-stu-id="22204-105">To create a trusted application pool</span></span>

1.  <span data-ttu-id="22204-106">Запустите консоль управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22204-106">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="22204-107">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="22204-107">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="22204-108">Возвращает идентификатор сайта для сайта, на котором создается пул.</span><span class="sxs-lookup"><span data-stu-id="22204-108">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="22204-109">Дополнительные сведения можно найти в [статьях Get-кссите](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) в документации по среде управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22204-109">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="22204-110">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="22204-110">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="22204-111">Подробные сведения можно найти в разделе [New-кструстедаппликатионпул](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) в документации по среде управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22204-111">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="22204-112">Полное доменное имя Exchange Server должно быть задано в качестве имени субъекта сертификата Exchange OWA (SN) или альтернативного имени субъекта (SAN).</span><span class="sxs-lookup"><span data-stu-id="22204-112">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="22204-113">В Exchange OWA убедитесь, что полное доменное имя пула также является надежным.</span><span class="sxs-lookup"><span data-stu-id="22204-113">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="22204-114">Если ваш сервер CAS <EM>не</EM> размещен на том же сервере, на котором работает единая система обмена сообщениями Exchange 2013 (UM), пропустите оставшиеся действия, описанные в этой процедуре, и выполните описанную ниже процедуру "Создание надежного приложения для сервера Exchange 2013". разделе.</span><span class="sxs-lookup"><span data-stu-id="22204-114">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="22204-115">Если ваш сервер CAS размещен на том же сервере, на котором работает единая система обмена сообщениями Exchange 2013 (UM), выполните действия, описанные в этой процедуре, и не выполняйте процедуру "создать доверенное приложение для сервера Exchange 2013 SharePoint" ниже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="22204-115">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="22204-116">Запустите **Enable-кстопологи**.</span><span class="sxs-lookup"><span data-stu-id="22204-116">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="22204-117">Откройте построитель топологии и скачайте существующую топологию.</span><span class="sxs-lookup"><span data-stu-id="22204-117">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="22204-118">В левой области разверните дерево, пока не дойдете до **доверенных серверов приложений**.</span><span class="sxs-lookup"><span data-stu-id="22204-118">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="22204-119">Разверните узел **серверы доверенных приложений** .</span><span class="sxs-lookup"><span data-stu-id="22204-119">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="22204-120">Появится сервер Exchange 2013 CAS, указанный как доверенный сервер приложений.</span><span class="sxs-lookup"><span data-stu-id="22204-120">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="22204-121">Создание надежного приложения для сервера Exchange 2013 CAS</span><span class="sxs-lookup"><span data-stu-id="22204-121">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="22204-122">Запустите консоль управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22204-122">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="22204-123">Если ваш сервер CAS *не* размещен на том же сервере, на котором работает единая система обмена сообщениями Exchange 2013 (UM), запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="22204-123">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="22204-124">Подробные сведения можно найти в разделе [New-кструстедаппликатион](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) в документации по среде управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22204-124">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="22204-125">Запустите **Enable-кстопологи**.</span><span class="sxs-lookup"><span data-stu-id="22204-125">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="22204-126">В области слева построитель топологии разверните дерево, пока вы не дойдете до **доверенных серверов приложений**.</span><span class="sxs-lookup"><span data-stu-id="22204-126">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="22204-127">Разверните узел **серверы доверенных приложений** .</span><span class="sxs-lookup"><span data-stu-id="22204-127">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="22204-128">Появится сервер Exchange 2013 CAS, указанный как доверенный сервер приложений.</span><span class="sxs-lookup"><span data-stu-id="22204-128">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

