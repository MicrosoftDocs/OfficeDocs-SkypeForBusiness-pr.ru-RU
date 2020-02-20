---
title: 'Lync Server 2013: планирование подключения PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for PSTN connectivity
ms:assetid: 280f684a-740a-443d-8ecf-574241382a42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425749(v=OCS.15)
ms:contentKeyID: 48183684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65474919bdd189f35431700f834402c5815d959c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a><span data-ttu-id="eb642-102">Планирование подключения по протоколу PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb642-102">Planning for PSTN connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb642-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="eb642-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="eb642-104">Решение VoIP корпоративного уровня должно обеспечивать вызовы в телефонную сеть общего пользования (ТСОП) и обратно без ухудшения качества обслуживания (QoS).</span><span class="sxs-lookup"><span data-stu-id="eb642-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="eb642-105">Пользователи, получающие и принимающие звонки, не должны знать о базовой технологии: с точки зрения пользователя, вызов между инфраструктурой корпоративной голосовой связи и PSTN должен выглядеть так же, как и другой телефонный звонок.</span><span class="sxs-lookup"><span data-stu-id="eb642-105">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>

<span data-ttu-id="eb642-106">Lync Server 2013 обеспечивает надежное, масштабируемая возможность подключения по протоколу PSTN с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="eb642-106">Lync Server 2013 provides reliable, scalable PSTN connectivity by using the following options:</span></span>

  - <span data-ttu-id="eb642-107">**SIP-магистрали** для поставщика услуг Интернет-телефонии (ITSP);</span><span class="sxs-lookup"><span data-stu-id="eb642-107">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="eb642-108">**прямые SIP-подключения** для шлюза ТСОП;</span><span class="sxs-lookup"><span data-stu-id="eb642-108">**Direct SIP connections** to a PSTN gateway</span></span>

  - <span data-ttu-id="eb642-109">**прямые SIP-подключения** для УАТС.</span><span class="sxs-lookup"><span data-stu-id="eb642-109">**Direct SIP connections** to a PBX</span></span>

<span data-ttu-id="eb642-110">В зависимости от размера, географического покрытия и существующей инфраструктуры системы голосовой связи предприятия могут использовать один, два или даже все три этих варианта в различных местоположениях.</span><span class="sxs-lookup"><span data-stu-id="eb642-110">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eb642-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="eb642-111">In This Section</span></span>

  - [<span data-ttu-id="eb642-112">Распределение каналов SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb642-112">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)

  - [<span data-ttu-id="eb642-113">Прямые подключения SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb642-113">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)

  - [<span data-ttu-id="eb642-114">Магистраль M:N в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb642-114">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="eb642-115">Правила преобразования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb642-115">Translation rules in Lync Server 2013</span></span>](lync-server-2013-translation-rules.md)

  - [<span data-ttu-id="eb642-116">Планирование маршрутизации исходящих голосовых вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb642-116">Planning outbound voice routing in Lync Server 2013</span></span>](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

