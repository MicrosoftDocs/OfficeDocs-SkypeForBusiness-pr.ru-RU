---
title: 'Lync Server 2013: управление инфраструктурой сети Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Lync Server 2013 network infrastructure
ms:assetid: cb13456a-8f66-4595-be21-8887f30ad4eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182585(v=OCS.15)
ms:contentKeyID: 48185638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bd95ac0259e86f3ac8fd39a09276bffa88cfc75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="ce966-102">Управление инфраструктурой сети Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce966-102">Managing the Lync Server 2013 network infrastructure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce966-103">_**Тема последнего изменения:** 2014-02-11_</span><span class="sxs-lookup"><span data-stu-id="ce966-103">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="ce966-104">Microsoft Lync Server 2013 включает поддержку управления допуском звонков (CAC) и обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="ce966-104">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="ce966-105">Для реализации этих функций необходимо настроить сеть регионов, сайтов, подсетей и т. д., благодаря которой вы сможете управлять пропускной способностью в ситуациях, когда необходимо ограничить передачу звука и видео.</span><span class="sxs-lookup"><span data-stu-id="ce966-105">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="ce966-106">Кроме того, вы можете использовать сетевую технологию качества обслуживания (QoS) для обеспечения оптимального взаимодействия с конечными пользователями для голосовой и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="ce966-106">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="ce966-107">С помощью панели управления Lync Server вы можете настроить CAC, обход мультимедиа и качество обслуживания, а также управлять ими.</span><span class="sxs-lookup"><span data-stu-id="ce966-107">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="ce966-108">В следующих разделах приведены инструкции по выполнению этой задачи.</span><span class="sxs-lookup"><span data-stu-id="ce966-108">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ce966-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="ce966-109">In This Section</span></span>

  - [<span data-ttu-id="ce966-110">Управление качеством обслуживания (QoS) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce966-110">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="ce966-111">Управление допуском звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce966-111">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="ce966-112">Сетевые интерфейсы Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce966-112">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="ce966-113">Запрещение новых подключений к Lync Server 2013 для обслуживания сервера</span><span class="sxs-lookup"><span data-stu-id="ce966-113">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="ce966-114">Методология качества звонков Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce966-114">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="ce966-115">Индикаторы работоспособности ключа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce966-115">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

