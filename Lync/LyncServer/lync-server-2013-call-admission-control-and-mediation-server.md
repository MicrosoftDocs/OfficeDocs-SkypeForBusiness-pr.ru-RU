---
title: 'Lync Server 2013: контроль допуска звонков и сервер-посредник'
description: 'Lync Server 2013: контроль допуска звонков и сервер-посредник.'
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
ms.openlocfilehash: 77e4b12a11f941923d50f3ffcab7a8f9b6a9edc5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569225"
---
# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="7126e-103">Контроль допуска звонков и сервер-посредник в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7126e-103">Call admission control and Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7126e-104">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7126e-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7126e-105">Контроль допуска звонков (CAC), который впервые появился в Lync Server 2010, управляет назначением сеанса в режиме реального времени, основанное на доступной пропускной способности, для предотвращения низкого качества взаимодействия (QoE) для пользователей в перегруженных сетях.</span><span class="sxs-lookup"><span data-stu-id="7126e-105">Call admission control (CAC), first introduced in Lync Server 2010, manages real-time session establishment, based on available bandwidth, to help prevent poor Quality of Experience (QoE) for users on congested networks.</span></span> <span data-ttu-id="7126e-106">Для поддержки этой возможности сервер-посредник, обеспечивающий передачу сигналов и трансляцию мультимедиа между инфраструктурой корпоративной голосовой связи и шлюзом или поставщиком магистральной линии SIP, отвечает за управление пропускной способностью для двух действий на стороне Lync Server и на стороне шлюза.</span><span class="sxs-lookup"><span data-stu-id="7126e-106">To support this capability, the Mediation Server, which provides signaling and media translation between the Enterprise Voice infrastructure and a gateway or SIP trunking provider, is responsible for bandwidth management for its two interactions on the Lync Server side and on the gateway side.</span></span> <span data-ttu-id="7126e-107">При использовании контроля допуска звонков за резервирование пропускной способности отвечает объект-получатель звонка.</span><span class="sxs-lookup"><span data-stu-id="7126e-107">In call admission control, the terminating entity for a call handles the bandwidth reservation.</span></span> <span data-ttu-id="7126e-108">Узлы шлюза (шлюз PSTN, IP-УАТС, SBC), с которым взаимодействует сервер-посредник, не поддерживает управление допуском звонков Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7126e-108">The gateway peers (PSTN gateway, IP-PBX, SBC) that the Mediation Server interacts with on the gateway side do not support Lync Server 2013 call admission control.</span></span> <span data-ttu-id="7126e-109">Таким образом, сервер-посредник должен обрабатывать взаимодействия пропускной способности от имени своего узла шлюза.</span><span class="sxs-lookup"><span data-stu-id="7126e-109">Thus, the Mediation Server has to handle bandwidth interactions on behalf of its gateway peer.</span></span> <span data-ttu-id="7126e-110">По мере возможности сервер-посредник будет зарезервировать пропускную способность заранее.</span><span class="sxs-lookup"><span data-stu-id="7126e-110">Whenever possible, the Mediation Server will reserve bandwidth in advance.</span></span> <span data-ttu-id="7126e-111">Если это невозможно (например, если расположение конечной точки сервера-посредника на стороне шлюза для исходящего звонка на одноранговый шлюз неизвестно), пропускная способность резервируется в момент выполнения звонка.</span><span class="sxs-lookup"><span data-stu-id="7126e-111">If that is not possible (for example, if the locality of the ultimate media endpoint on the gateway side is unknown for an outgoing call to the gateway peer), bandwidth is reserved when the call is placed.</span></span> <span data-ttu-id="7126e-112">Это может приводить к избыточному выделению полосы пропускания, однако это единственный способ предотвратить ошибочные звонки.</span><span class="sxs-lookup"><span data-stu-id="7126e-112">This behavior can result in oversubscription of bandwidth, but it is the only way to prevent false rings.</span></span>

<span data-ttu-id="7126e-113">Обход сервера-посредника и резервирование пропускной способности являются взаимоисключающими подходами.</span><span class="sxs-lookup"><span data-stu-id="7126e-113">Media bypass and bandwidth reservation are mutually exclusive.</span></span> <span data-ttu-id="7126e-114">Если для звонка используется обход сервера-посредника, контроль допуска звонков не осуществляется.</span><span class="sxs-lookup"><span data-stu-id="7126e-114">If a media bypass is employed for a call, call admission control is not performed for that call.</span></span> <span data-ttu-id="7126e-115">При этом предполагается, что при выполнении звонка отсутствуют каналы с ограниченной пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="7126e-115">The assumption here is that there are no links with constrained bandwidth involved in the call.</span></span> <span data-ttu-id="7126e-116">Если контроль допуска звонков используется для определенного вызова, включающего сервер-посредник, этот вызов не может использовать обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="7126e-116">If call admission control is used for a particular call that involves the Mediation Server, that call cannot employ media bypass.</span></span>

<span data-ttu-id="7126e-117">Дополнительные сведения об обходе и контроле допуска звонков приведены в статье [Планирование обхода сервера мультимедиа в Lync server 2013](lync-server-2013-planning-for-media-bypass.md) или [Планирование контроля допуска звонков в Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="7126e-117">For details about media bypass or call admission control, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) or [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

