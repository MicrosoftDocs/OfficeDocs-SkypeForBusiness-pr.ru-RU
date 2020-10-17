---
title: 'Lync Server 2013: Планирование обхода сервера мультимедиа'
description: 'Lync Server 2013: Планирование обхода сервера мультимедиа.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d92a50d9d838b0f13fd6837cbfadee1c48712f0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549445"
---
# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="f44e5-103">Планирование обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f44e5-103">Planning for media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f44e5-104">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f44e5-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f44e5-105">Обход сервера-посредника — это устранение сервера-посредника из пути мультимедиа везде, где это возможно, для вызовов, передача сигналов которых проходит через сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="f44e5-105">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="f44e5-106">Обход сервера-посредника может улучшить качество звука, поскольку уменьшается задержка, потребность в преобразовании, вероятность потери пакетов и число точек вероятного сбоя.</span><span class="sxs-lookup"><span data-stu-id="f44e5-106">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="f44e5-107">Может улучшиться масштабируемость, поскольку устранение обработки мультимедиа для вызовов с обходом сервера-посредника уменьшает нагрузку на сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="f44e5-107">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="f44e5-108">Это сокращение нагрузки дополняет способность сервера-посредника управлять несколькими шлюзами.</span><span class="sxs-lookup"><span data-stu-id="f44e5-108">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="f44e5-109">Когда сайт филиала без сервера-посредника подключается к центральному сайту с помощью одной или нескольких каналов глобальной сети с ограниченной пропускной способностью, обход сервера-посредника снижает требования к пропускной способности, позволяя мультимедиа от клиента на сайте филиала напрямую переключаться к локальному шлюзу без необходимости переключаться между ГЛОБАЛЬным шлюзом и сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="f44e5-109">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="f44e5-110">Освобождая сервер-посредник из обработки мультимедиа позволяет сократить количество серверов-посредников, необходимых для инфраструктуры корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f44e5-110">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="f44e5-111">На следующем рисунке показаны основные пути мультимедиа и передачи сигналов в топологиях с обходом сервера-посредника и без такого обхода.</span><span class="sxs-lookup"><span data-stu-id="f44e5-111">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="f44e5-112">**Пути мультимедиа и передачи сигналов с обходом сервера-посредника и без обхода**</span><span class="sxs-lookup"><span data-stu-id="f44e5-112">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="f44e5-113">![Режим обхода подключений голосовой связи для передачи голоса](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Режим обхода подключений голосовой связи для передачи голоса")</span><span class="sxs-lookup"><span data-stu-id="f44e5-113">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="f44e5-114">Общая рекомендация состоит в том, чтобы включать обход сервера-посредника везде, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="f44e5-114">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f44e5-115">Содержание</span><span class="sxs-lookup"><span data-stu-id="f44e5-115">In This Section</span></span>

  - [<span data-ttu-id="f44e5-116">Обзор обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f44e5-116">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="f44e5-117">Режимы обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f44e5-117">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="f44e5-118">Обход сервера мультимедиа и контроль допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f44e5-118">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="f44e5-119">Технические требования для обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f44e5-119">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="f44e5-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f44e5-120">Related Sections</span></span>

[<span data-ttu-id="f44e5-121">Развертывание расширенных функций корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f44e5-121">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f44e5-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f44e5-122">See Also</span></span>


[<span data-ttu-id="f44e5-123">Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f44e5-123">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="f44e5-124">Глобальные параметры обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f44e5-124">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

