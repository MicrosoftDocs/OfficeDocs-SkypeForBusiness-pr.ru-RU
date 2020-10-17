---
title: 'Lync Server 2013: обеспечение подключения PSTN на сайте филиала'
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
ms.openlocfilehash: 38c76d378db31cb8a6619a18072ec0218260843e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513176"
---
# <a name="providing-pstn-connectivity-at-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="d907c-102">Обеспечение подключения PSTN на сайте филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d907c-102">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d907c-103">_**Последнее изменение темы:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="d907c-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="d907c-104">Мы рекомендуем использовать средство планирования Microsoft Lync Server 2013, средство планирования для добавления сайтов филиалов в топологию и настройки инфраструктуры голосовой связи на сайтах филиалов.</span><span class="sxs-lookup"><span data-stu-id="d907c-104">We recommend using the Microsoft Lync Server 2013, Planning Tool to add branch sites to your topology and to set up your voice infrastructure in branch sites.</span></span>

<span data-ttu-id="d907c-105">Если вы не используете средство планирования, используйте процедуры, описанные в подразделах этого раздела, для добавления сайтов филиалов, а затем для настройки инфраструктуры голосовой связи путем определения шлюза IP/общедоступной телефонной сети (PSTN) и/или путем настройки магистральной линии SIP (с обходом сервера-посредника или без него).</span><span class="sxs-lookup"><span data-stu-id="d907c-105">If you are not using the Planning Tool, use the procedures in the topics in this section—first, to add the branch sites, and then, to set up your voice infrastructure by defining the IP/public switched telephone network (PSTN) gateway and/or by configuring the SIP trunk (with or without media bypass).</span></span> <span data-ttu-id="d907c-106">Кроме того, можно добавить в сайт филиала УАТС.</span><span class="sxs-lookup"><span data-stu-id="d907c-106">Connecting a private branch exchange (PBX) to the branch site is another option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d907c-107">Если требуется обеспечить устойчивость сайта филиала, необходимо развернуть устройство для обеспечения связи в филиалах, сервер для обеспечения связи в филиалах или сервер Standard Edition на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="d907c-107">If you want to provide branch-site resiliency, you must deploy a Survivable Branch Appliance, a Survivable Branch Server, or Standard Edition server at the branch site.</span></span> <span data-ttu-id="d907c-108">Дополнительные сведения: <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync server 2013</A> или <A href="lync-server-2013-deploying-lync-server.md">развертывание Lync Server 2013</A>(при необходимости) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="d907c-108">For details, see <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, as appropriate, in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d907c-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="d907c-109">In This Section</span></span>

  - [<span data-ttu-id="d907c-110">Добавление сайтов филиалов в топологию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d907c-110">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="d907c-111">Определение шлюза PSTN для сайта филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d907c-111">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - [<span data-ttu-id="d907c-112">Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d907c-112">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="d907c-113">Настройка магистрали без обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d907c-113">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d907c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d907c-114">See Also</span></span>


[<span data-ttu-id="d907c-115">Планирование обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d907c-115">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="d907c-116">Планирование подключения по протоколу PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d907c-116">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

