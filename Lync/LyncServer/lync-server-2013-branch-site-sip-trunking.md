---
title: 'Lync Server 2013: магистральная магистральная линия SIP для сайта филиала'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 161964bc7a183672323ac277eae4f3a7ce0d2b82
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="007f3-102">Магистральная линия SIP сайта филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="007f3-102">Branch site SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="007f3-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="007f3-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="007f3-104">В некоторых случаях может потребоваться реализация распределенной магистрали SIP на выбранных сайтах филиалов.</span><span class="sxs-lookup"><span data-stu-id="007f3-104">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="007f3-105">Чтобы определить, нужна ли магистраль SIP для сайта филиала, ознакомьтесь со сведениями в разделе [как реализация распределения каналов SIP в Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="007f3-105">To determine whether a SIP trunk is needed for a branch site, review the information in [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="007f3-106">Дополнительные сведения о поддерживаемых параметрах топологии для развертывания магистральных каналов SIP в филиалах представлены [в статье решение для обеспечения устойчивости сайтов филиалов в Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="007f3-106">For details about the supported topology options for deploying SIP trunks in branch sites, see [Branch-site resiliency solutions in Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span></span>

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="007f3-107">Пример анализа требований к магистрали SIP для офиса филиала</span><span class="sxs-lookup"><span data-stu-id="007f3-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="007f3-108">При развертывании канала SIP для сайта филиала необходимо выполнить анализ затрат для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="007f3-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="007f3-109">Например, если предприятие с центральным сайтом в Редмонде, Вашингтонм и филиалом в Нью-Йорке, необходимо выполнить анализ, чтобы определить, следует ли реализовать магистраль SIP с сайта Нью-Йоркного поставщика услуг локальной службы.</span><span class="sxs-lookup"><span data-stu-id="007f3-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>

<span data-ttu-id="007f3-110">Чтобы определить, является ли экономически выгодной распределенная магистраль SIP в Нью-Йорке, определите, какие номера для прямого соединения с внутренними абонентами будет использовать магистраль SIP, и проанализируйте число звонков, совершаемых из офиса в Нью-Йорке в области, не включающие Рэдмонд (425).</span><span class="sxs-lookup"><span data-stu-id="007f3-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="007f3-111">Вы можете приувольненияся к сайту филиала на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="007f3-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="007f3-112">Например, центр Redmond может размещать номера для сайта филиала Нью-Йорка.</span><span class="sxs-lookup"><span data-stu-id="007f3-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="007f3-113">Если затраты на реализацию распределенной магистрали SIP меньше, чем затраты на эти вызовы, рекомендуется реализовать магистраль SIP на сайте Нью-Йорка.</span><span class="sxs-lookup"><span data-stu-id="007f3-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span>

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="007f3-114">Другие требования к магистрали SIP для офиса филиала</span><span class="sxs-lookup"><span data-stu-id="007f3-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="007f3-115">Выбор между развертыванием магистрали SIP вместо шлюза основан на разнице тарифов за междугородные звонки в телефонной сети общего пользования в каждом из вариантов.</span><span class="sxs-lookup"><span data-stu-id="007f3-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="007f3-116">При развертывании канала SIP для сайта филиала необходимо также определить требования к устойчивости и пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="007f3-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="007f3-117">Если связь между сайтом филиала и центральным сайтом является устойчивой и достаточным пропускной способностью, можно развернуть магистраль SIP или шлюз.</span><span class="sxs-lookup"><span data-stu-id="007f3-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="007f3-118">Нет необходимости развертывать устройство для обеспечения связи в филиалах на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="007f3-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="007f3-119">Если связь между сайтом филиала и центральным сайтом не является устойчивой, разверните устройство для обеспечения связи в филиалах или разверните сервер для обеспечения связи в филиалах с помощью шлюза или магистрали SIP на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="007f3-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

