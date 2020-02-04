---
title: 'Lync Server 2013: новые возможности корпоративной голосовой связи'
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
ms.openlocfilehash: 92c1c264b9ffa5459962b2b6e915ea0fef2cf775
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="208a9-102">Новые возможности корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="208a9-102">New Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="208a9-103">_**Тема последнего изменения:** 2013-05-01_</span><span class="sxs-lookup"><span data-stu-id="208a9-103">_**Topic Last Modified:** 2013-05-01_</span></span>

<span data-ttu-id="208a9-104">Lync Server 2013 предлагает несколько новых функций маршрутизации и управления звонками, повышающих эффективность работы с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="208a9-104">Lync Server 2013 introduces several new routing and call management features that enhance Enterprise Voice.</span></span>

<span data-ttu-id="208a9-105">Lync Server 2013 поддерживает несколько каналов связи между серверами и шлюзами обновлений.</span><span class="sxs-lookup"><span data-stu-id="208a9-105">Lync Server 2013 supports multiple trunks between Mediation Servers and gateways.</span></span> <span data-ttu-id="208a9-106">*Магистраль* — это логическая связь между номером порта и сервером-посредником с номером порта и шлюзом.</span><span class="sxs-lookup"><span data-stu-id="208a9-106">A *trunk* is a logical association between a port number and Mediation Server with a port number and gateway.</span></span> <span data-ttu-id="208a9-107">Это означает, что сервер-посредник может иметь несколько магистральных каналов для разных шлюзов, и шлюз может иметь несколько магистральных каналов для разных серверов-исправлений.</span><span class="sxs-lookup"><span data-stu-id="208a9-107">This means that a Mediation Server can have multiple trunks to different gateways, and a gateway can have multiple trunks to different Mediation Servers.</span></span> <span data-ttu-id="208a9-108">Межсетевая маршрутизация позволяет Lync Server 2013 использовать IP-УАТС для связи с шлюзом КОММУТИРУЕМой телефонной сети или межсетевым подключением к нескольким системам IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="208a9-108">Intertrunk routing makes it possible for Lync Server 2013 to interconnect an IP-PBX to a public switched telephone network (PSTN) gateway or to interconnect multiple IP-PBX systems.</span></span> <span data-ttu-id="208a9-109">Lync Server 2013 является связующим (т. е. межсоединением) между различными системами телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="208a9-109">Lync Server 2013 serves as the glue (that is, the interconnection) between different telephony systems.</span></span>

<span data-ttu-id="208a9-110">Microsoft Lync Server 2013 вносит улучшения в области переадресации звонков, одновременных звонков, обработки голосовой почты и презентации идентификации вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="208a9-110">Microsoft Lync Server 2013 makes improvements in the areas of call forwarding, simultaneous ringing, voice mail handling, and caller ID presentation.</span></span> <span data-ttu-id="208a9-111">Эти функции улучшают возможности корпоративного голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="208a9-111">These features enrich the Enterprise Voice call experience.</span></span>

<span data-ttu-id="208a9-112">В Lync Server 2013 появились следующие усовершенствования, повышающие эффективность корпоративной голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="208a9-112">Lync Server 2013 introduces the following new enhancements to Enterprise Voice:</span></span>

  - [<span data-ttu-id="208a9-113">Новые функции звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="208a9-113">New call features in Lync Server 2013</span></span>](lync-server-2013-new-call-features.md)

  - [<span data-ttu-id="208a9-114">Новая функция АОН в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="208a9-114">New caller ID feature in Lync Server 2013</span></span>](lync-server-2013-new-caller-id-feature.md)

  - [<span data-ttu-id="208a9-115">Новая функция голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="208a9-115">New voice mail feature in Lync Server 2013</span></span>](lync-server-2013-new-voice-mail-feature.md)

  - [<span data-ttu-id="208a9-116">Новая функция магистрали в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="208a9-116">New trunk feature in Lync Server 2013</span></span>](lync-server-2013-new-trunk-feature.md)

  - [<span data-ttu-id="208a9-117">Новая функция промежуточной магистрали в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="208a9-117">New intertrunk feature in Lync Server 2013</span></span>](lync-server-2013-new-intertrunk-feature.md)

  - [<span data-ttu-id="208a9-118">Новые функции управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="208a9-118">New call management features in Lync Server 2013</span></span>](lync-server-2013-new-call-management-features.md)

</div>

<span> </span>

</div>

</div>

</div>

