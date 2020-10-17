---
title: 'Lync Server 2013: развертывание сайтов филиалов'
description: 'Lync Server 2013: развертывание сайтов филиалов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d653e3f06de832693d97bfb229f122a67c28640e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552645"
---
# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="0a65d-103">Развертывание сайтов филиалов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a65d-103">Deploying branch sites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a65d-104">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0a65d-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0a65d-105">Пользователи сайта филиала получают большинство функций Lync Server 2013 с сервера на центральном сайте, с которым связан сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="0a65d-105">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="0a65d-106">Каждый узел филиала связан ровно с одним центральным узлом.</span><span class="sxs-lookup"><span data-stu-id="0a65d-106">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="0a65d-107">Чтобы позволить совершать вызовы по ТСОП, узел филиала может содержать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="0a65d-107">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="0a65d-108">шлюз ТСОП и, возможно, сервер-посредник;</span><span class="sxs-lookup"><span data-stu-id="0a65d-108">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="0a65d-109">SIP-магистраль;</span><span class="sxs-lookup"><span data-stu-id="0a65d-109">A SIP trunk</span></span>

  - <span data-ttu-id="0a65d-110">существующая инфраструктура голосовой связи с УАТС;</span><span class="sxs-lookup"><span data-stu-id="0a65d-110">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="0a65d-111">Устройство для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="0a65d-111">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="0a65d-112">Сервер для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="0a65d-112">A Survivable Branch Server</span></span>

<span data-ttu-id="0a65d-113">Сайты филиалов с устройством для обеспечения связи в филиалах или сервером для обеспечения связи в филиалах являются более устойчивыми во время сбоев в глобальной сети или центральных сайтах, чем для сайтов филиалов без одного из этих решений.</span><span class="sxs-lookup"><span data-stu-id="0a65d-113">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="0a65d-114">Например, на сайте с устройством для обеспечения связи в филиале или с развернутым сервером для обеспечения связи в филиалах пользователи по-прежнему могут совершать и принимать звонки PSTN, если сеть, соединяющую сайт филиала, с центральным сайтом отключена.</span><span class="sxs-lookup"><span data-stu-id="0a65d-114">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="0a65d-115">Другой способ достижения устойчивости сайта филиала заключается в использовании шлюза PSTN или магистральной линии SIP с полным развертыванием Lync Server на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="0a65d-115">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="0a65d-116">Сведения о том, какое развертывание сайта филиала подходит для вашей организации, в том числе необходимые условия и другие рекомендации по планированию, приведены в статье [Планирование подключения PSTN в Lync server 2013](lync-server-2013-planning-for-pstn-connectivity.md) и [Планирование устойчивости голосовой связи на сайте филиала в Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="0a65d-116">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0a65d-117">Содержание</span><span class="sxs-lookup"><span data-stu-id="0a65d-117">In This Section</span></span>

  - [<span data-ttu-id="0a65d-118">Обеспечение подключения PSTN на сайте филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a65d-118">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="0a65d-119">Развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a65d-119">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

