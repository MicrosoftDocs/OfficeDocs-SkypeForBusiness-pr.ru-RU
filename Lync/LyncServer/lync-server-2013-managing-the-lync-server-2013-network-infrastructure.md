---
title: 'Lync Server 2013: управление инфраструктурой сети Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Lync Server 2013 network infrastructure
ms:assetid: cb13456a-8f66-4595-be21-8887f30ad4eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182585(v=OCS.15)
ms:contentKeyID: 48185638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f958e6532738720bb5969199d72e38a79a3bc6ce
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="0c3b0-102">Управление инфраструктурой сети Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c3b0-102">Managing the Lync Server 2013 network infrastructure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c3b0-103">_**Последнее изменение темы:** 2014-02-11_</span><span class="sxs-lookup"><span data-stu-id="0c3b0-103">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="0c3b0-104">Microsoft Lync Server 2013 включает поддержку контроля допуска звонков (CAC) и обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="0c3b0-104">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="0c3b0-105">Для реализации этих возможностей необходимо настроить сетевые области, узлы, подсети и т. д., которые позволят регулировать полосу пропускания в ситуациях, когда передачу аудио- и видеоданных нужно ограничить.</span><span class="sxs-lookup"><span data-stu-id="0c3b0-105">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="0c3b0-106">Можно также использовать сетевую технологию качества обслуживания (QoS) для обеспечения оптимальной работы пользователя при организации аудио- и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="0c3b0-106">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="0c3b0-107">С помощью панели управления Lync Server вы можете настроить CAC и управлять ими, а также выполнять обход сервера мультимедиа и качество обслуживания.</span><span class="sxs-lookup"><span data-stu-id="0c3b0-107">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="0c3b0-108">В следующих разделах описаны действия, позволяющие это сделать</span><span class="sxs-lookup"><span data-stu-id="0c3b0-108">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0c3b0-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="0c3b0-109">In This Section</span></span>

  - [<span data-ttu-id="0c3b0-110">Управление качеством обслуживания (QoS) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c3b0-110">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="0c3b0-111">Управление допуском звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c3b0-111">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="0c3b0-112">Сетевые интерфейсы Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c3b0-112">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="0c3b0-113">Предотвращение новых подключений к Lync Server 2013 для обслуживания серверов</span><span class="sxs-lookup"><span data-stu-id="0c3b0-113">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="0c3b0-114">Методология качества вызовов Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c3b0-114">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="0c3b0-115">Ключевые индикаторы работоспособности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c3b0-115">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

