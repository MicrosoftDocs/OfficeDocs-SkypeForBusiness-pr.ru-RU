---
title: 'Lync Server 2013: планирование мониторинга'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for monitoring
ms:assetid: 26cead5a-183c-42f1-a4b0-0e8d61c6159d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204752(v=OCS.15)
ms:contentKeyID: 48183671
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a866be23c9bcf59133fb60f4facf46e867d3d08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="1d61c-102">Планирование мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d61c-102">Planning for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d61c-103">_**Тема последнего изменения:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="1d61c-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="1d61c-104">Служба мониторинга в Microsoft Lync Server 2013 предоставляет администраторам способ сбора данных об использовании, тенденциях и качества обслуживания для сеансов связи, выполняемых в своей организации.</span><span class="sxs-lookup"><span data-stu-id="1d61c-104">The monitoring service in Microsoft Lync Server 2013 provides a way for administrators to collect usage, trend, and quality of service data for the communication sessions that take place in their organization.</span></span> <span data-ttu-id="1d61c-105">Для наблюдения в Lync Server 2013 больше не требуется отдельная серверная роль; Вместо этого служба мониторинга встроена в каждый сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1d61c-105">Monitoring in Lync Server 2013 no longer requires a separate server role; instead, the monitoring service is built into each Front End server.</span></span> <span data-ttu-id="1d61c-106">Однако наблюдение по умолчанию не включено в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61c-106">However, by default monitoring is not enabled in Lync Server 2013.</span></span> <span data-ttu-id="1d61c-107">Этот документ поможет вам определить, следует ли включить мониторинг в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1d61c-107">This document will help you determine whether or not monitoring should be enabled in your organization.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1d61c-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="1d61c-108">In This Section</span></span>

  - [<span data-ttu-id="1d61c-109">Общие сведения об отслеживании в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d61c-109">Overview of monitoring in Lync Server 2013</span></span>](lync-server-2013-overview-of-monitoring.md)

  - [<span data-ttu-id="1d61c-110">Определение требований к мониторингу в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d61c-110">Defining your requirements for monitoring in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-monitoring.md)

  - [<span data-ttu-id="1d61c-111">Включение мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d61c-111">Enabling monitoring in Lync Server 2013</span></span>](lync-server-2013-enabling-monitoring.md)

  - [<span data-ttu-id="1d61c-112">Доступ к данным мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d61c-112">Accessing monitoring data in Lync Server 2013</span></span>](lync-server-2013-accessing-monitoring-data.md)

  - [<span data-ttu-id="1d61c-113">Компоненты и топологии для мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d61c-113">Components and topologies for monitoring in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-monitoring.md)

  - [<span data-ttu-id="1d61c-114">Развертывание контрольного списка для мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d61c-114">Deployment checklist for monitoring in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-monitoring.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

