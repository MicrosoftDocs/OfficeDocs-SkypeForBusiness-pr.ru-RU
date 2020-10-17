---
title: Проверка сведений о топологии
description: Проверьте сведения о топологии.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ed41cd95fffdca629e710dcf443631d0c74c69e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555495"
---
# <a name="verify-topology-information"></a><span data-ttu-id="3d6c0-103">Проверка сведений о топологии</span><span class="sxs-lookup"><span data-stu-id="3d6c0-103">Verify topology information</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d6c0-104">_**Последнее изменение темы:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="3d6c0-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="3d6c0-105">На первом этапе проверки успешного выполнения слияния необходимо просмотреть сведения о топологии Office Communications Server 2007 R2, Объединенные с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-105">The first step in verifying the merge completed successfully is to view the Office Communications Server 2007 R2 topology information that you merged with Lync Server 2013.</span></span> <span data-ttu-id="3d6c0-106">В построителе топологий узел **BackCompatSite** отображает полное доменное имя каждого пула Office Communications Server 2007 R2 и объединяемого сервера.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-106">In Topology Builder, the **BackCompatSite** node displays the fully qualified domain name (FQDN) of each Office Communications Server 2007 R2 pool and server that you merged.</span></span>

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a><span data-ttu-id="3d6c0-107">Просмотр узла BackCompatSite в построителе топологий</span><span class="sxs-lookup"><span data-stu-id="3d6c0-107">To view BackCompatSite in Topology Builder</span></span>

1.  <span data-ttu-id="3d6c0-108">В среде Office Communications Server 2007 R2 откройте средство администрирования Office Communications Server 2007 R2 и запомните полные доменные имена устаревших пулов и серверов.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-108">In your Office Communications Server 2007 R2 environment, open the Office Communications Server 2007 R2 administrative tool and note the FQDNs of the legacy pools and servers.</span></span>

2.  <span data-ttu-id="3d6c0-109">В среде Lync Server 2013 откройте построитель топологий и разверните узел **BackCompatSite** .</span><span class="sxs-lookup"><span data-stu-id="3d6c0-109">In your Lync Server 2013 environment, open Topology Builder and then expand the **BackCompatSite** node.</span></span>

3.  <span data-ttu-id="3d6c0-110">Проверьте, отображаются ли полные доменные имена объединяемых пулов и серверов.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-110">Verify that the FQDNs for the pools and servers that you merge are displayed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3d6c0-111">В узле <STRONG>BackCompatSite</STRONG> не отображаются сведения о ролях серверов, размещаемых совместно на сервере переднего плана или сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-111">You do not see any information in <STRONG>BackCompatSite</STRONG> for server roles that are collocated on a Front End Server or Standard Edition server.</span></span> <span data-ttu-id="3d6c0-112">Показаны только роли серверов, необходимые для взаимодействия между Office Communications Server 2007 R2 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-112">Only server roles that are required for interoperability between Office Communications Server 2007 R2 and Lync Server 2013 are shown.</span></span>

    
    </div>

<span data-ttu-id="3d6c0-113">![Диалоговое окно "BackCompatSite" в построителе топологий](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Диалоговое окно "BackCompatSite" в построителе топологий")</span><span class="sxs-lookup"><span data-stu-id="3d6c0-113">![Topology Builder BackCompatSite dialog box](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder BackCompatSite dialog box")</span></span>

<span data-ttu-id="3d6c0-114">Вы также можете использовать панель управления Lync Server 2013 для просмотра объединенной топологии.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-114">You can also use Lync Server 2013 Control Panel to view your merged topology.</span></span> <span data-ttu-id="3d6c0-115">В панели управления Lync Server 2013 можно просмотреть полное доменное имя сервера, полное доменное имя пула и имя сайта для объединенной топологии.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-115">In Lync Server 2013 Control Panel, you can see each server FQDN, pool FQDN, and site name for your merged topology.</span></span> <span data-ttu-id="3d6c0-116">В поле **Сайт** для объединенных серверов указано имя **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-116">Merged servers have a **Site** name of **BackCompatSite**.</span></span>

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a><span data-ttu-id="3d6c0-117">Просмотр объединенной топологии в панели управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d6c0-117">To view the merged topology in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="3d6c0-118">Откройте панель управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-118">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="3d6c0-119">Щелкните пункт **Топология**.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-119">Click **Topology**.</span></span>

3.  <span data-ttu-id="3d6c0-120">На вкладке **Состояние** проверьте, отображаются ли объединенные серверы и пулы, найдя серверы и пулы с именем **BackCompatSite** в столбце **Сайт**.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-120">On the **Status** tab, verify that servers and pools you merged appear by looking for **BackCompatSite** in the **Site** column.</span></span>

<span data-ttu-id="3d6c0-121">![Панель управления Lync Server, в которой отображается Объединенная топология](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Панель управления Lync Server, в которой отображается Объединенная топология")</span><span class="sxs-lookup"><span data-stu-id="3d6c0-121">![Lync Server Control Panel showing merged topology](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server Control Panel showing merged topology")</span></span>

<span data-ttu-id="3d6c0-122">Чтобы получить дополнительные сведения об объединенном пуле, воспользуйтесь командлетом **Get-CsPool**.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-122">To see more detail about a merged pool, use the **Get-CsPool** cmdlet.</span></span> <span data-ttu-id="3d6c0-123">В дополнение к сведениям, доступным в построителе топологий и панели управления Lync Server 2013, в этом командлете отображаются службы, которые выполняются в пуле Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-123">In addition to the information that is available in Topology Builder and Lync Server 2013 Control Panel, this cmdlet displays the services that run on the Lync Server 2013 pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3d6c0-124">При публикации топологии после запуска мастера слияния в построителе топологий каталоги конференций объединяются в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-124">When you publish the topology after running the Merge wizard in Topology Builder, conference directories are merged to Lync Server 2013.</span></span> <span data-ttu-id="3d6c0-125">Каталоги конференций можно проверить с помощью командлета <STRONG>Get-CsConferenceDirectory</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-125">Conference directories can be verified by running the <STRONG>Get-CsConferenceDirectory</STRONG> cmdlet.</span></span>



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a><span data-ttu-id="3d6c0-126">Просмотр служб в объединенном пуле</span><span class="sxs-lookup"><span data-stu-id="3d6c0-126">To view services on a merged pool</span></span>

1.  <span data-ttu-id="3d6c0-127">Откройте консоль управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-127">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="3d6c0-128">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d6c0-128">At the command line, type the following:</span></span>
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    <span data-ttu-id="3d6c0-129">Пример:</span><span class="sxs-lookup"><span data-stu-id="3d6c0-129">For example:</span></span>
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a><span data-ttu-id="3d6c0-130">Проверка объединения каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="3d6c0-130">To verify conference directories merged</span></span>

1.  <span data-ttu-id="3d6c0-131">Откройте консоль управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-131">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="3d6c0-132">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d6c0-132">At the command line, type the following:</span></span>
    
        Get-CsConferenceDirectory

3.  <span data-ttu-id="3d6c0-133">Убедитесь, что все каталоги конференций для пула или сервера, которые вы хотите объединить, теперь находятся в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d6c0-133">Verify that all the conference directories for the pool or server you are merging are now in Lync Server 2013.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

