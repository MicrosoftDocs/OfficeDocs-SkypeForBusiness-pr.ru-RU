---
title: 'Lync Server 2013: сервер обхода сервера-посредника и сервер-посредник'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ef294e9aa5a9d53b11316ab8d64a0880ea6a938
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524626"
---
# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="92172-102">Обход сервера-посредника и сервер-посредник в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92172-102">Media bypass and Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92172-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="92172-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="92172-104">Обход сервера-посредника — это возможность Lync Server, которая позволяет администратору настроить маршрутизацию вызовов для направления непосредственно между конечной точкой пользователя и шлюзом PSTN без обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="92172-104">Media bypass is a Lync Server capability that enables an administrator to configure call routing to flow directly between the user endpoint and the public switched telephone network (PSTN) gateway without traversing the Mediation Server.</span></span> <span data-ttu-id="92172-105">Обход сервера мультимедиа улучшает качество связи за счет сокращения задержки, ненужных преобразований, вероятности потери пакетов и количества потенциальных точек сбоя.</span><span class="sxs-lookup"><span data-stu-id="92172-105">Media bypass improves call quality by reducing latency, unnecessary translation, possibility of packet loss, and the number of potential points of failure.</span></span> <span data-ttu-id="92172-106">Если удаленный сайт без сервера-посредника подключен к центральному сайту с помощью одной или нескольких каналов глобальной сети с ограниченной пропускной способностью, обход сервера-посредника понижает требования к пропускной способности, позволяя компьютеру из клиента на удаленном сайте напрямую переключаться к его локальному шлюзу без необходимости перетекать через канал WAN к серверу-посреднику на центральном сайте и обратно. Это сокращение обработки мультимедиа также дополняет возможность сервера-посредника управлять несколькими шлюзами.</span><span class="sxs-lookup"><span data-stu-id="92172-106">Where a remote site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by enabling media from a client at a remote site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.This reduction in media processing also complements the Mediation Server’s ability to control multiple gateways.</span></span>

<span data-ttu-id="92172-p102">Обход сервера-посредника и контроль допуска звонков являются взаимоисключающими функциями. Если для вызова применяется обход сервера-посредника, то для него не применяется контроль допуска звонков. Предполагается, что нет никакой связи с ограниченной пропускной способностью сторон, участвующих в вызове.</span><span class="sxs-lookup"><span data-stu-id="92172-p102">Media bypass and call admission control (CAC) are mutually exclusive. If media bypass is employed for a call, CAC is not performed for that call. The assumption is that there are no links with constrained bandwidth involved in the call.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="92172-110">См. также</span><span class="sxs-lookup"><span data-stu-id="92172-110">See Also</span></span>


[<span data-ttu-id="92172-111">Контроль допуска звонков и сервер-посредник в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92172-111">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)  


[<span data-ttu-id="92172-112">Планирование обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92172-112">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

