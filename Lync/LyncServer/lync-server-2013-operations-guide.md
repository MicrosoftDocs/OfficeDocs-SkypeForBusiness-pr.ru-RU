---
title: 'Lync Server 2013: руководство по работе'
description: 'Lync Server 2013: руководство по работе.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operations Guide
ms:assetid: dcb9ddff-6fe3-4077-a2e3-0ba64f65e264
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720467(v=OCS.15)
ms:contentKeyID: 63969658
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85e562b96e87f54529a9e2ce077a0a82574020c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565891"
---
# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="f8c22-103">Руководство по работе для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8c22-103">Operations Guide for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8c22-104">_**Последнее изменение темы:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="f8c22-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="f8c22-105">В этом документе описываются рабочие процессы, задачи и инструменты, необходимые для обслуживания программной среды Microsoft Lync Server 2013 Communications.</span><span class="sxs-lookup"><span data-stu-id="f8c22-105">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="f8c22-106">В этой статье объясняется, как управлять Lync Server 2013 в соответствии с моделью Microsoft Operations Framework (MOF), и он поможет вам разработать эффективную среду управления, которая включает в себя внедрение расписаний, процессов и процедур для поддержки эффективной рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="f8c22-106">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f8c22-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="f8c22-107">In This Section</span></span>

<span data-ttu-id="f8c22-108">Включены следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="f8c22-108">The following sections are included:</span></span>

  - [<span data-ttu-id="f8c22-109">Рекомендации по работе с средами Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8c22-109">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="f8c22-110">Ежедневные задачи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8c22-110">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="f8c22-111">Еженедельные задачи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8c22-111">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="f8c22-112">Ежемесячные задачи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8c22-112">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="f8c22-113">Задачи, необходимые для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8c22-113">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="f8c22-114">Контрольные списки операций для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8c22-114">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="f8c22-115">Мониторинг Lync Server 2013 с помощью System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="f8c22-115">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="f8c22-116">Операционные зависимости в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8c22-116">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="f8c22-117">Устранение неполадок и ключевые индикаторы работоспособности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8c22-117">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="f8c22-118">Предполагается, что развертывание Microsoft Lync Server 2013 завершено.</span><span class="sxs-lookup"><span data-stu-id="f8c22-118">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="f8c22-119">Если это не так, ознакомьтесь с разделом "планирование и развертывание" для Microsoft Lync Server 2013, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="f8c22-119">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f8c22-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f8c22-120">See Also</span></span>


[<span data-ttu-id="f8c22-121">Начало работы с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8c22-121">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="f8c22-122">Планирование для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8c22-122">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="f8c22-123">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8c22-123">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="f8c22-124">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="f8c22-124">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

