---
title: 'Lync Server 2013: планирование обхода серверов-посредников'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa60b6658eca7a73e509a7f6c707c3cf48c7f16e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="a6a19-102">Планирование обхода серверов-посредников в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6a19-102">Planning for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6a19-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a6a19-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a6a19-104">Обойтись обозначает удаление сервера обновлений из пути к носителю, если это возможно, для звонков, сигнализация которых проходит на сервер обновлений.</span><span class="sxs-lookup"><span data-stu-id="a6a19-104">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="a6a19-105">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span><span class="sxs-lookup"><span data-stu-id="a6a19-105">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="a6a19-106">Масштабируемость может быть улучшена, так как при отключении обработки мультимедиа для обходных вызовов уменьшается нагрузка на сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="a6a19-106">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="a6a19-107">Благодаря этому снижению нагрузки сервер может управлять несколькими шлюзами.</span><span class="sxs-lookup"><span data-stu-id="a6a19-107">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="a6a19-108">Если сайт филиала без сервера-посредника подключен к центральному сайту по одной или нескольким ГЛОБАЛЬным каналам связи с ограниченной пропускной способностью, пропустите требования к пропускной способности, разрешая доступ к мультимедиа от клиента на сайте филиала для передачи данных непосредственно локальному шлюзу без Сначала перейдете по каналу глобальной сети на сервер-посредник на центральном сайте и обратно.</span><span class="sxs-lookup"><span data-stu-id="a6a19-108">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="a6a19-109">Вырелиевинг сервер из обработки мультимедийных сообщений, вы также можете уменьшить количество серверов, которые потребуются при работе с корпоративной голосовой сетью.</span><span class="sxs-lookup"><span data-stu-id="a6a19-109">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="a6a19-110">На следующем рисунке показаны основные пути мультимедиа и передачи сигналов в топологиях с обходом сервера-посредника и без такого обхода.</span><span class="sxs-lookup"><span data-stu-id="a6a19-110">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="a6a19-111">**Пути передачи мультимедийных данных и сигналов при включенном и отключенном режиме обхода сервера-посредника**</span><span class="sxs-lookup"><span data-stu-id="a6a19-111">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="a6a19-112">![Обход принудительного подключения мультимедиа с использованием голосовой почты] (images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Обход принудительного подключения мультимедиа с использованием голосовой почты")</span><span class="sxs-lookup"><span data-stu-id="a6a19-112">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="a6a19-113">Общая рекомендация состоит в том, чтобы включать обход сервера-посредника везде, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="a6a19-113">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a6a19-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="a6a19-114">In This Section</span></span>

  - [<span data-ttu-id="a6a19-115">Общие сведения об обходном пропуске мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6a19-115">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="a6a19-116">Режимы обхода сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6a19-116">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="a6a19-117">Обход сервера-посредника и контроль допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6a19-117">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="a6a19-118">Технические требования для сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6a19-118">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="a6a19-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a6a19-119">Related Sections</span></span>

[<span data-ttu-id="a6a19-120">Развертывание улучшенных функций голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6a19-120">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a6a19-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a6a19-121">See Also</span></span>


[<span data-ttu-id="a6a19-122">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6a19-122">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="a6a19-123">Глобальные параметры обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6a19-123">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

