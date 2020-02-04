---
title: 'Lync Server 2013: контроль допуска звонков и сервер-посредник'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aa12bd22f27cbe25946c14ad04977b98025d557
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="a7ea5-102">Контроль допуска звонков и сервер-посредник в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7ea5-102">Call admission control and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7ea5-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a7ea5-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a7ea5-104">Управление допуском звонков (CAC), впервые введенное в Lync Server 2010, управляет набором сеансов в реальном времени, основываясь на доступной пропускной способности, чтобы предотвратить низкое качество работы (QoE) для пользователей в перегруженных сетях.</span><span class="sxs-lookup"><span data-stu-id="a7ea5-104">Call admission control (CAC), first introduced in Lync Server 2010, manages real-time session establishment, based on available bandwidth, to help prevent poor Quality of Experience (QoE) for users on congested networks.</span></span> <span data-ttu-id="a7ea5-105">Для поддержки этой возможности сервер-посредник, который обеспечивает передачу сигналов и трансляцию мультимедиа между корпоративной инфраструктурой голосовой связи и поставщиком магистральной адресацией SIP, отвечает за управление пропускной способностью для двух видов взаимодействия в Lync. На стороне сервера и на стороне шлюза.</span><span class="sxs-lookup"><span data-stu-id="a7ea5-105">To support this capability, the Mediation Server, which provides signaling and media translation between the Enterprise Voice infrastructure and a gateway or SIP trunking provider, is responsible for bandwidth management for its two interactions on the Lync Server side and on the gateway side.</span></span> <span data-ttu-id="a7ea5-106">При управлении допуском звонков оконечная сущность для вызова обрабатывает резервирование пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="a7ea5-106">In call admission control, the terminating entity for a call handles the bandwidth reservation.</span></span> <span data-ttu-id="a7ea5-107">Узлы шлюзов (шлюз PSTN, IP-УАТС, SBC), с помощью которого сервер-посредник взаимодействует на стороне шлюза, не поддерживают управление допуском звонков в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7ea5-107">The gateway peers (PSTN gateway, IP-PBX, SBC) that the Mediation Server interacts with on the gateway side do not support Lync Server 2013 call admission control.</span></span> <span data-ttu-id="a7ea5-108">Таким образом, сервер обновлений должен обрабатывать взаимодействие с пропускной способностью от имени ее партнера.</span><span class="sxs-lookup"><span data-stu-id="a7ea5-108">Thus, the Mediation Server has to handle bandwidth interactions on behalf of its gateway peer.</span></span> <span data-ttu-id="a7ea5-109">По мере возможности сервер, на котором выполняется исправление, резервирует пропускную способность заранее.</span><span class="sxs-lookup"><span data-stu-id="a7ea5-109">Whenever possible, the Mediation Server will reserve bandwidth in advance.</span></span> <span data-ttu-id="a7ea5-110">Если это невозможно (например, если локальная конечная точка Media на стороне шлюза неизвестна для исходящего звонка на узел шлюза), при помещении звонка пропускная способность резервируется.</span><span class="sxs-lookup"><span data-stu-id="a7ea5-110">If that is not possible (for example, if the locality of the ultimate media endpoint on the gateway side is unknown for an outgoing call to the gateway peer), bandwidth is reserved when the call is placed.</span></span> <span data-ttu-id="a7ea5-111">Это может привести к превышению подписку на использование пропускной способности, но это единственный способ предотвратить ложный звонок.</span><span class="sxs-lookup"><span data-stu-id="a7ea5-111">This behavior can result in oversubscription of bandwidth, but it is the only way to prevent false rings.</span></span>

<span data-ttu-id="a7ea5-112">Обход сервера-посредника и резервирование пропускной способности являются взаимоисключающими подходами.</span><span class="sxs-lookup"><span data-stu-id="a7ea5-112">Media bypass and bandwidth reservation are mutually exclusive.</span></span> <span data-ttu-id="a7ea5-113">Если для вызова используются обходные номера мультимедиа, управление допуском звонков для этого звонка не выполняется.</span><span class="sxs-lookup"><span data-stu-id="a7ea5-113">If a media bypass is employed for a call, call admission control is not performed for that call.</span></span> <span data-ttu-id="a7ea5-114">Предполагается, что при выполнении вызова отсутствуют каналы с ограниченной пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="a7ea5-114">The assumption here is that there are no links with constrained bandwidth involved in the call.</span></span> <span data-ttu-id="a7ea5-115">Если для определенного звонка, включающего сервер-посредника, используется управление допуском звонков, этот звонок не может использовать функцию обхода мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="a7ea5-115">If call admission control is used for a particular call that involves the Mediation Server, that call cannot employ media bypass.</span></span>

<span data-ttu-id="a7ea5-116">Дополнительные сведения об управлении мультимедийными данными и допуском звонков можно найти в разделе [Планирование обхода мультимедиа в Lync server 2013](lync-server-2013-planning-for-media-bypass.md) или [Планирование управления допуском звонков в Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="a7ea5-116">For details about media bypass or call admission control, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) or [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

