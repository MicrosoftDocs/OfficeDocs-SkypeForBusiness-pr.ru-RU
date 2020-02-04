---
title: 'Lync Server 2013: развертывание сайтов филиалов'
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
ms.openlocfilehash: facfda5d1d7ce67ea08f71cbfb943792eeced7a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="4d559-102">Развертывание сайтов филиалов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d559-102">Deploying branch sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d559-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4d559-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4d559-104">Пользователи сайтов филиалов получают большинство функций Lync Server 2013 с сервера центрального сайта, с которым связан сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="4d559-104">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="4d559-105">Каждый сайт филиала связан только с одним центральным сайтом.</span><span class="sxs-lookup"><span data-stu-id="4d559-105">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="4d559-106">Для передачи звонков из коммутируемой телефонной сети с открытым коммутируемым подключением сайт филиала может содержать любые из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="4d559-106">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="4d559-107">Шлюз PSTN и, возможно, сервер Медитатион</span><span class="sxs-lookup"><span data-stu-id="4d559-107">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="4d559-108">Магистральная линия SIP</span><span class="sxs-lookup"><span data-stu-id="4d559-108">A SIP trunk</span></span>

  - <span data-ttu-id="4d559-109">Существующая инфраструктура голосовой связи с частным обменом филиалов (АТС)</span><span class="sxs-lookup"><span data-stu-id="4d559-109">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="4d559-110">Бесперебойно работающее устройство филиала</span><span class="sxs-lookup"><span data-stu-id="4d559-110">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="4d559-111">Бесперебойный сервер филиала</span><span class="sxs-lookup"><span data-stu-id="4d559-111">A Survivable Branch Server</span></span>

<span data-ttu-id="4d559-112">Сайты филиалов с бесперебойно работающими управляющими системами или работающими серверами филиалов более устойчивы во время многофакторной сети или сбоя центрального сайта, чем для сайтов филиалов без одного из этих решений.</span><span class="sxs-lookup"><span data-stu-id="4d559-112">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="4d559-113">Например, на сайте с бесперебойно работающим управляющим устройством филиала или развернутом работающем сервере филиала пользователи по-прежнему могут совершать и принимать звонки PSTN, если сеть, соединяющая сайт ветви с центральным сайтом, не работает.</span><span class="sxs-lookup"><span data-stu-id="4d559-113">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="4d559-114">Кроме того, вы можете достичь устойчивости сайта с помощью шлюза PSTN или магистральной магистрали SIP с полным развертыванием Lync Server на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="4d559-114">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="4d559-115">Сведения о том, какое развертывание сайтов филиалов подходит для вашей организации, в том числе о предварительных требованиях и других вопросах планирования, приведены в разделе [Планирование подключений PSTN в Lync server 2013](lync-server-2013-planning-for-pstn-connectivity.md) и [Планирование обеспечения устойчивости голоса на филиалах в Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="4d559-115">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4d559-116">Содержание</span><span class="sxs-lookup"><span data-stu-id="4d559-116">In This Section</span></span>

  - [<span data-ttu-id="4d559-117">Обеспечение подключения ТСОП в сайте филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d559-117">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="4d559-118">Развертывание устройства или сервера обеспечения связи в филиалах с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d559-118">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

