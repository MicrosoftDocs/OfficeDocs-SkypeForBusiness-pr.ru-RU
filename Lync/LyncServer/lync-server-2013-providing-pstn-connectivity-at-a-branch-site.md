---
title: 'Lync Server 2013: обеспечение подключения ТСОП в сайте филиала'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Providing PSTN connectivity at a branch site
ms:assetid: d78d76fb-2dd1-42cb-b25a-bfaff9650a70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398945(v=OCS.15)
ms:contentKeyID: 48185633
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5dfc039b0b1cd2995d0a658f1c1c78e0941d405d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="providing-pstn-connectivity-at-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="0973e-102">Обеспечение подключения ТСОП в сайте филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0973e-102">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0973e-103">_**Тема последнего изменения:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="0973e-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="0973e-104">Рекомендуем использовать средство Microsoft Lync Server 2013, планирование для добавления сайтов филиалов в топологию и настройки вашей голосовой инфраструктуры на сайтах филиалов.</span><span class="sxs-lookup"><span data-stu-id="0973e-104">We recommend using the Microsoft Lync Server 2013, Planning Tool to add branch sites to your topology and to set up your voice infrastructure in branch sites.</span></span>

<span data-ttu-id="0973e-105">Если вы не используете средство планирования, выполните действия, описанные в разделах в этом разделе, чтобы добавить сайты филиалов, а затем — для настройки своей инфраструктуры, определив шлюз IP/коммутируемой телефонной сети (PSTN) и/или настроив магистраль SIP (с обобщениям и без него).</span><span class="sxs-lookup"><span data-stu-id="0973e-105">If you are not using the Planning Tool, use the procedures in the topics in this section—first, to add the branch sites, and then, to set up your voice infrastructure by defining the IP/public switched telephone network (PSTN) gateway and/or by configuring the SIP trunk (with or without media bypass).</span></span> <span data-ttu-id="0973e-106">Подключение к сайту филиала может быть еще одним вариантом.</span><span class="sxs-lookup"><span data-stu-id="0973e-106">Connecting a private branch exchange (PBX) to the branch site is another option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0973e-107">Если вы хотите обеспечить устойчивость сайтов филиалов, необходимо развернуть работающее устройство филиала, временный сервер филиалов или стандартный сервер Standard Edition на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="0973e-107">If you want to provide branch-site resiliency, you must deploy a Survivable Branch Appliance, a Survivable Branch Server, or Standard Edition server at the branch site.</span></span> <span data-ttu-id="0973e-108">Дополнительные сведения можно найти в разделе Развертывание работающего <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">устройства филиалов или сервера с помощью Lync server 2013</A> или <A href="lync-server-2013-deploying-lync-server.md">развертывание Lync Server 2013</A>(в зависимости от того, что нужно) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="0973e-108">For details, see <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, as appropriate, in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0973e-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="0973e-109">In This Section</span></span>

  - [<span data-ttu-id="0973e-110">Добавление сайтов филиалов в топологию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0973e-110">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="0973e-111">Определение шлюза ТСОП для сайта филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0973e-111">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - [<span data-ttu-id="0973e-112">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0973e-112">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="0973e-113">Настройка магистрали без обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0973e-113">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0973e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0973e-114">See Also</span></span>


[<span data-ttu-id="0973e-115">Планирование обхода серверов-посредников в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0973e-115">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="0973e-116">Планирование подключений PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0973e-116">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

