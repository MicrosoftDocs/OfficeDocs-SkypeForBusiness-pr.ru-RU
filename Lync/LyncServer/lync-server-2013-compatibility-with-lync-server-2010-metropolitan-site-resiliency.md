---
title: Совместимость Lync Server 2013 с использованием устойчивости сайта Lync Server 2010 для микрогородка
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7f1c637c49784dd5acb81c26d8ab36400730278
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="af697-102">Устойчивость сайта Lync Server 2010 для городового сайта</span><span class="sxs-lookup"><span data-stu-id="af697-102">Lync Server 2010 metropolitan site resiliency</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af697-103">_**Последнее изменение темы:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="af697-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="af697-104">Решение устойчивости сайта, поддерживаемое для Lync Server 2010, не поддерживается для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af697-104">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="af697-105">Это решение включает расширение одного пула переднего плана для охвата двух центров обработки данных в одном и том же регионе.</span><span class="sxs-lookup"><span data-stu-id="af697-105">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="af697-106">Решение устойчивости сайта с использованием объекта, предназначенное для восстановления после потери полного центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="af697-106">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="af697-107">При охвате пула на два центра обработки данных вы обычно располагаете половину интерфейсных концов в одном центре обработки данных, а вторая половина — в другом.</span><span class="sxs-lookup"><span data-stu-id="af697-107">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="af697-108">Если вы потеряете весь центр обработки данных, вы потеряли половину серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="af697-108">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="af697-109">Это может привести к проблемам с новой моделью распределенной системы для пулов переднего плана в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af697-109">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="af697-110">Для получения дополнительных сведений см [топология и компоненты для серверов переднего плана, обмена мгновенными сообщениями и сведений о присутствии в Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="af697-110">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

