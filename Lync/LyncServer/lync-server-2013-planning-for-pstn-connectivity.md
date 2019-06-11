---
title: 'Lync Server 2013: Планирование подключений PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for PSTN connectivity
ms:assetid: 280f684a-740a-443d-8ecf-574241382a42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425749(v=OCS.15)
ms:contentKeyID: 48183684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d64089661b5d185362a8e47128e9a890b03edfd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a><span data-ttu-id="30ec9-102">Планирование подключений PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30ec9-102">Planning for PSTN connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30ec9-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="30ec9-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="30ec9-104">Решение VoIP корпоративного уровня должно предусматривать входящие и исходящие вызовы на телефонную сеть общего пользования (ТСОП) без какого-либо снижения качества обслуживания (QoS).</span><span class="sxs-lookup"><span data-stu-id="30ec9-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="30ec9-105">Пользователи, которые размещаются и принимают звонки, не должны знать о базовой технологии: с точки зрения пользователя, Звонок между корпоративной инфраструктурой голосовой связи и PSTN должен казаться просто другим телефонным звонком.</span><span class="sxs-lookup"><span data-stu-id="30ec9-105">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>

<span data-ttu-id="30ec9-106">Lync Server 2013 обеспечивает надежную и масштабируемую КОММУТИРУЕМую связь с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="30ec9-106">Lync Server 2013 provides reliable, scalable PSTN connectivity by using the following options:</span></span>

  - <span data-ttu-id="30ec9-107">**магистрали SIP**, соединяющие с оператором телефонной связи по сети Интернет;</span><span class="sxs-lookup"><span data-stu-id="30ec9-107">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="30ec9-108">**прямые подключения SIP** к шлюзу ТСОП;</span><span class="sxs-lookup"><span data-stu-id="30ec9-108">**Direct SIP connections** to a PSTN gateway</span></span>

  - <span data-ttu-id="30ec9-109">**прямые подключения SIP** к УАТС.</span><span class="sxs-lookup"><span data-stu-id="30ec9-109">**Direct SIP connections** to a PBX</span></span>

<span data-ttu-id="30ec9-110">В зависимости от размеров предприятия, охватываемой территории и существующей инфраструктуры голосовой связи можно применять один и тот же способ на всем предприятии либо два или все три способа в разных подразделениях.</span><span class="sxs-lookup"><span data-stu-id="30ec9-110">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="30ec9-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="30ec9-111">In This Section</span></span>

  - [<span data-ttu-id="30ec9-112">Магистральные линии SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30ec9-112">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)

  - [<span data-ttu-id="30ec9-113">Прямые подключения по протоколу SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30ec9-113">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)

  - [<span data-ttu-id="30ec9-114">М:Н магистраль в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30ec9-114">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="30ec9-115">Правила перевода в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30ec9-115">Translation rules in Lync Server 2013</span></span>](lync-server-2013-translation-rules.md)

  - [<span data-ttu-id="30ec9-116">Планирование маршрутизации исходящей голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30ec9-116">Planning outbound voice routing in Lync Server 2013</span></span>](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

