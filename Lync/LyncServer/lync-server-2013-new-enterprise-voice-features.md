---
title: 'Lync Server 2013: новые функции корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Enterprise Voice features
ms:assetid: db0ad7b9-e469-4c29-89d9-52fed018ef08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398964(v=OCS.15)
ms:contentKeyID: 48185591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf51e5d06241ece778d5bdb6dc41691e64682f18
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42124412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="19b80-102">Новые функции корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19b80-102">New Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19b80-103">_**Последнее изменение темы:** 2013-05-01_</span><span class="sxs-lookup"><span data-stu-id="19b80-103">_**Topic Last Modified:** 2013-05-01_</span></span>

<span data-ttu-id="19b80-104">В Lync Server 2013 представлено несколько новых функций маршрутизации и управления звонками, которые улучшают корпоративную голосовую связь.</span><span class="sxs-lookup"><span data-stu-id="19b80-104">Lync Server 2013 introduces several new routing and call management features that enhance Enterprise Voice.</span></span>

<span data-ttu-id="19b80-105">Lync Server 2013 поддерживает несколько магистральных каналов между серверами-посредниками и шлюзами.</span><span class="sxs-lookup"><span data-stu-id="19b80-105">Lync Server 2013 supports multiple trunks between Mediation Servers and gateways.</span></span> <span data-ttu-id="19b80-106">*Магистраль* — это логическая связь между номером порта и сервером-посредником с помощью номера порта и шлюза.</span><span class="sxs-lookup"><span data-stu-id="19b80-106">A *trunk* is a logical association between a port number and Mediation Server with a port number and gateway.</span></span> <span data-ttu-id="19b80-107">Это означает, что сервер-посредник может иметь несколько магистральных линий на различные шлюзы, а шлюз может иметь несколько магистральных каналов для разных серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="19b80-107">This means that a Mediation Server can have multiple trunks to different gateways, and a gateway can have multiple trunks to different Mediation Servers.</span></span> <span data-ttu-id="19b80-108">Маршрутизация по магистрали позволяет Lync Server 2013 подключаться к IP-УАТС к шлюзу телефонной сети общего пользования (PSTN) или к нескольким системам IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="19b80-108">Intertrunk routing makes it possible for Lync Server 2013 to interconnect an IP-PBX to a public switched telephone network (PSTN) gateway or to interconnect multiple IP-PBX systems.</span></span> <span data-ttu-id="19b80-109">Lync Server 2013 выступает в качестве связывающего (то есть, подключения) между различными системами телефонии.</span><span class="sxs-lookup"><span data-stu-id="19b80-109">Lync Server 2013 serves as the glue (that is, the interconnection) between different telephony systems.</span></span>

<span data-ttu-id="19b80-110">Microsoft Lync Server 2013 делает улучшения в областях переадресации вызовов, одновременных звонков, обработки голосовой почты и презентации идентификации звонящего.</span><span class="sxs-lookup"><span data-stu-id="19b80-110">Microsoft Lync Server 2013 makes improvements in the areas of call forwarding, simultaneous ringing, voice mail handling, and caller ID presentation.</span></span> <span data-ttu-id="19b80-111">Эти функции улучшают вызов корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="19b80-111">These features enrich the Enterprise Voice call experience.</span></span>

<span data-ttu-id="19b80-112">Lync Server 2013 содержит следующие новые расширения корпоративной голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="19b80-112">Lync Server 2013 introduces the following new enhancements to Enterprise Voice:</span></span>

  - [<span data-ttu-id="19b80-113">Новые функции звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19b80-113">New call features in Lync Server 2013</span></span>](lync-server-2013-new-call-features.md)

  - [<span data-ttu-id="19b80-114">Новая функция идентификации звонящего в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19b80-114">New caller ID feature in Lync Server 2013</span></span>](lync-server-2013-new-caller-id-feature.md)

  - [<span data-ttu-id="19b80-115">Новая функция голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19b80-115">New voice mail feature in Lync Server 2013</span></span>](lync-server-2013-new-voice-mail-feature.md)

  - [<span data-ttu-id="19b80-116">Новая функция магистрали в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19b80-116">New trunk feature in Lync Server 2013</span></span>](lync-server-2013-new-trunk-feature.md)

  - [<span data-ttu-id="19b80-117">Новая функция межмагистрали в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19b80-117">New intertrunk feature in Lync Server 2013</span></span>](lync-server-2013-new-intertrunk-feature.md)

  - [<span data-ttu-id="19b80-118">Новые функции управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19b80-118">New call management features in Lync Server 2013</span></span>](lync-server-2013-new-call-management-features.md)

</div>

<span> </span>

</div>

</div>

</div>

