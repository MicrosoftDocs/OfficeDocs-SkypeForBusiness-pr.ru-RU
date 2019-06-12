---
title: Проверка сведений о топологии
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7657bb80d7acb6d48a4027c665fae70e469bb236
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a><span data-ttu-id="a55ad-102">Проверка сведений о топологии</span><span class="sxs-lookup"><span data-stu-id="a55ad-102">Verify topology information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a55ad-103">_**Тема последнего изменения:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="a55ad-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="a55ad-104">Первый этап проверки успешности слияния — Просмотр сведений о топологии Office Communications Server 2007 R2, которые вы объединили с помощью Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a55ad-104">The first step in verifying the merge completed successfully is to view the Office Communications Server 2007 R2 topology information that you merged with Lync Server 2013.</span></span> <span data-ttu-id="a55ad-105">В построителе топологии в узле **бакккомпатсите** отображается полное доменное имя (FQDN) для каждого пула и сервера Office Communications Server 2007 R2, который вы объединили.</span><span class="sxs-lookup"><span data-stu-id="a55ad-105">In Topology Builder, the **BackCompatSite** node displays the fully qualified domain name (FQDN) of each Office Communications Server 2007 R2 pool and server that you merged.</span></span>

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a><span data-ttu-id="a55ad-106">Просмотр Бакккомпатсите в построителе топологии</span><span class="sxs-lookup"><span data-stu-id="a55ad-106">To view BackCompatSite in Topology Builder</span></span>

1.  <span data-ttu-id="a55ad-107">В среде Office Communications Server 2007 R2 откройте средство администрирования Office Communications Server 2007 R2 и запомните полные доменные имена старых пулов и серверов.</span><span class="sxs-lookup"><span data-stu-id="a55ad-107">In your Office Communications Server 2007 R2 environment, open the Office Communications Server 2007 R2 administrative tool and note the FQDNs of the legacy pools and servers.</span></span>

2.  <span data-ttu-id="a55ad-108">В среде Lync Server 2013 откройте "Построитель топологии", а затем разверните узел **бакккомпатсите** .</span><span class="sxs-lookup"><span data-stu-id="a55ad-108">In your Lync Server 2013 environment, open Topology Builder and then expand the **BackCompatSite** node.</span></span>

3.  <span data-ttu-id="a55ad-109">Убедитесь в том, что полные доменные имена для объединяемых пулов и серверов отображены.</span><span class="sxs-lookup"><span data-stu-id="a55ad-109">Verify that the FQDNs for the pools and servers that you merge are displayed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a55ad-110">В <STRONG>бакккомпатсите</STRONG> не отображаются никакие данные для ролей сервера, размещенных на сервере переднего плана или стандартном сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a55ad-110">You do not see any information in <STRONG>BackCompatSite</STRONG> for server roles that are collocated on a Front End Server or Standard Edition server.</span></span> <span data-ttu-id="a55ad-111">Показаны только роли сервера, необходимые для взаимодействия между Office Communications Server 2007 R2 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a55ad-111">Only server roles that are required for interoperability between Office Communications Server 2007 R2 and Lync Server 2013 are shown.</span></span>

    
    </div>

<span data-ttu-id="a55ad-112">![Диалоговое окно "Бакккомпатсите Topology Builder"] (images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Диалоговое окно \"Бакккомпатсите Topology Builder\"")</span><span class="sxs-lookup"><span data-stu-id="a55ad-112">![Topology Builder BackCompatSite dialog box](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder BackCompatSite dialog box")</span></span>

<span data-ttu-id="a55ad-113">Вы также можете использовать панель управления Lync Server 2013, чтобы просмотреть объединенную топологию.</span><span class="sxs-lookup"><span data-stu-id="a55ad-113">You can also use Lync Server 2013 Control Panel to view your merged topology.</span></span> <span data-ttu-id="a55ad-114">В панели управления Lync Server 2013 вы можете просмотреть полные доменные имена серверов, FQDN и имя пула для объединенной топологии.</span><span class="sxs-lookup"><span data-stu-id="a55ad-114">In Lync Server 2013 Control Panel, you can see each server FQDN, pool FQDN, and site name for your merged topology.</span></span> <span data-ttu-id="a55ad-115">У Объединенных серверов есть имя **сайта** **бакккомпатсите**.</span><span class="sxs-lookup"><span data-stu-id="a55ad-115">Merged servers have a **Site** name of **BackCompatSite**.</span></span>

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a><span data-ttu-id="a55ad-116">Просмотр объединенной топологии в Lync Server 2013 панели управления</span><span class="sxs-lookup"><span data-stu-id="a55ad-116">To view the merged topology in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="a55ad-117">Откройте панель управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a55ad-117">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="a55ad-118">Нажмите **топология**.</span><span class="sxs-lookup"><span data-stu-id="a55ad-118">Click **Topology**.</span></span>

3.  <span data-ttu-id="a55ad-119">На вкладке **Status (состояние** ) убедитесь в том, что Объединенные серверы и пулы отображаются по столбцу " **сайт** ", выполнив поиск **бакккомпатсите** .</span><span class="sxs-lookup"><span data-stu-id="a55ad-119">On the **Status** tab, verify that servers and pools you merged appear by looking for **BackCompatSite** in the **Site** column.</span></span>

<span data-ttu-id="a55ad-120">![Объединенная топология на панели управления сервера Lync Server] (images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Объединенная топология на панели управления сервера Lync Server")</span><span class="sxs-lookup"><span data-stu-id="a55ad-120">![Lync Server Control Panel showing merged topology](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server Control Panel showing merged topology")</span></span>

<span data-ttu-id="a55ad-121">Чтобы просмотреть дополнительные сведения о объединенном пуле, используйте командлет **Get-кспул** .</span><span class="sxs-lookup"><span data-stu-id="a55ad-121">To see more detail about a merged pool, use the **Get-CsPool** cmdlet.</span></span> <span data-ttu-id="a55ad-122">В дополнение к сведениям, доступным в построителе топологии и панели управления Lync Server 2013, в этом командлете выводятся службы, которые выполняются в пуле Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a55ad-122">In addition to the information that is available in Topology Builder and Lync Server 2013 Control Panel, this cmdlet displays the services that run on the Lync Server 2013 pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a55ad-123">После публикации топологии после запуска мастера слияния в построителе топологии каталоги конференций объединяются в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a55ad-123">When you publish the topology after running the Merge wizard in Topology Builder, conference directories are merged to Lync Server 2013.</span></span> <span data-ttu-id="a55ad-124">Каталоги конференций можно проверить, запустив командлет <STRONG>Get-ксконференцедиректори</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="a55ad-124">Conference directories can be verified by running the <STRONG>Get-CsConferenceDirectory</STRONG> cmdlet.</span></span>



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a><span data-ttu-id="a55ad-125">Просмотр служб в Объединенном пуле</span><span class="sxs-lookup"><span data-stu-id="a55ad-125">To view services on a merged pool</span></span>

1.  <span data-ttu-id="a55ad-126">Откройте консоль управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a55ad-126">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="a55ad-127">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a55ad-127">At the command line, type the following:</span></span>
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    <span data-ttu-id="a55ad-128">Например:</span><span class="sxs-lookup"><span data-stu-id="a55ad-128">For example:</span></span>
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a><span data-ttu-id="a55ad-129">Проверка Объединенных каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="a55ad-129">To verify conference directories merged</span></span>

1.  <span data-ttu-id="a55ad-130">Откройте консоль управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a55ad-130">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="a55ad-131">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a55ad-131">At the command line, type the following:</span></span>
    
        Get-CsConferenceDirectory

3.  <span data-ttu-id="a55ad-132">Убедитесь в том, что все каталоги конференций для пула или сервера, который вы собираетесь объединять, теперь находятся в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a55ad-132">Verify that all the conference directories for the pool or server you are merging are now in Lync Server 2013.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

