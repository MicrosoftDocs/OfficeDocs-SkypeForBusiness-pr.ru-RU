---
title: 'Lync Server 2013: оценка объема использования и трафика голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf321dc7668682e2c41765955c348a7e155214ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a><span data-ttu-id="5c26e-102">Оценка объема использования и трафика голосовой связи для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c26e-102">Estimating voice usage and traffic for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c26e-103">_**Тема последнего изменения:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="5c26e-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="5c26e-104">Microsoft Lync Server 2013, средство планирования использует следующие показатели для оценки трафика пользователей на каждом сайте и количество портов, необходимых для поддержки этого трафика.</span><span class="sxs-lookup"><span data-stu-id="5c26e-104">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>

  - <span></span>  
    <span data-ttu-id="5c26e-105">Для **легкого трафика** (один звонок через ТСОП на одного пользователя в час) — 15 пользователей на порт.</span><span class="sxs-lookup"><span data-stu-id="5c26e-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="5c26e-106">Для **среднего трафика** (2 звонка через ТСОП на одного пользователя в час) — 10 пользователей на порт.</span><span class="sxs-lookup"><span data-stu-id="5c26e-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="5c26e-107">Для **тяжелого трафика** (3 или больше звонков через ТСОП на вызовы пользователя в час) — 5 пользователей на порт.</span><span class="sxs-lookup"><span data-stu-id="5c26e-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>

<span data-ttu-id="5c26e-108">Число портов, в свою очередь, определяет количество серверов и шлюзов, которые должны быть необходимы.</span><span class="sxs-lookup"><span data-stu-id="5c26e-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="5c26e-109">Шлюзы ТСОП, которые развертывают большинство организаций, могут содержать от 2 до 960 портов.</span><span class="sxs-lookup"><span data-stu-id="5c26e-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="5c26e-110">(Существуют и более крупные шлюзы, но они в основном используются поставщиками услуг телефонии.)</span><span class="sxs-lookup"><span data-stu-id="5c26e-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>

<span data-ttu-id="5c26e-p102">Например, организация с 10000 пользователей и средним трафиком требуется 1000 портов. Число шлюзов равно общему числу необходимых портов, что определяется общей емкостью шлюзов.</span><span class="sxs-lookup"><span data-stu-id="5c26e-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

