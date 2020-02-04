---
title: 'Lync Server 2013: руководство по эксплуатации'
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
ms.openlocfilehash: 21b4f3e0a9beaae9419b11bf7353319b3b3ad2b0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="e63aa-102">Operations Guide for Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e63aa-102">Operations Guide for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e63aa-103">_**Тема последнего изменения:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="e63aa-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="e63aa-104">В этом документе описаны рабочие процессы, задачи и инструменты, необходимые для поддержки программной среды Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e63aa-104">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="e63aa-105">В этой статье объясняется, как управлять Lync Server 2013 в соответствии с моделью Microsoft Operations Framework (MOF), и это поможет вам спроектировать эффективную среду управления, которая включает в себя расписания, процессы и процедуры для поддержки Эффективная рабочая среда.</span><span class="sxs-lookup"><span data-stu-id="e63aa-105">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e63aa-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="e63aa-106">In This Section</span></span>

<span data-ttu-id="e63aa-107">Включены следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="e63aa-107">The following sections are included:</span></span>

  - [<span data-ttu-id="e63aa-108">Рекомендации по работе с средами Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e63aa-108">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="e63aa-109">Ежедневные задачи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e63aa-109">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="e63aa-110">Еженедельные задачи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e63aa-110">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="e63aa-111">Ежемесячные задачи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e63aa-111">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="e63aa-112">Задачи, необходимые для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e63aa-112">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="e63aa-113">Контрольные списки операций для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e63aa-113">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="e63aa-114">Мониторинг сервера Lync Server 2013 с помощью System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="e63aa-114">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="e63aa-115">Операционные зависимости в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e63aa-115">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="e63aa-116">Устранение неполадок и индикаторов работоспособности ключа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e63aa-116">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="e63aa-117">Предполагается, что развертывание Microsoft Lync Server 2013 завершено.</span><span class="sxs-lookup"><span data-stu-id="e63aa-117">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="e63aa-118">Если это не так, ознакомьтесь с разделом Планирование и развертывание для Microsoft Lync Server 2013, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="e63aa-118">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e63aa-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e63aa-119">See Also</span></span>


[<span data-ttu-id="e63aa-120">Начало работы с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e63aa-120">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="e63aa-121">Планирование для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e63aa-121">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="e63aa-122">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e63aa-122">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="e63aa-123">командная консоль Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e63aa-123">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

