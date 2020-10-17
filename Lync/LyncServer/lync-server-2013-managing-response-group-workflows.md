---
title: 'Lync Server 2013: Управление рабочими процессами группы ответа'
description: 'Lync Server 2013: Управление рабочими процессами группы ответа.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group workflows
ms:assetid: 42cfccdd-2844-4875-b4e3-813e1df15f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520986(v=OCS.15)
ms:contentKeyID: 48183974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2223fed2b5b030a2c92e0b958ae8545a7717f848
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560415"
---
# <a name="managing-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="f8093-103">Управление рабочими процессами группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8093-103">Managing Response Group workflows in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8093-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f8093-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f8093-105">Рабочий процесс группы ответа определяет поведение звонка с момента звонка с телефона на время, когда агент отвечает на вызов.</span><span class="sxs-lookup"><span data-stu-id="f8093-105">A Response Group workflow defines the behavior of a call from the time that the phone rings to the time that an agent answers the call.</span></span> <span data-ttu-id="f8093-106">Этот рабочий процесс включает сведения об очереди и маршрутизации, а также сведения либо о сервисной группе, либо об интерактивном автоответчике (IVR).</span><span class="sxs-lookup"><span data-stu-id="f8093-106">The workflow includes queue and routing information, and includes either hunt group or interactive voice response (IVR) information.</span></span>

<span data-ttu-id="f8093-107">В разделах этой статьи даются рекомендации по разработке рабочих процессов IVR, а также объясняется создание пользовательских наборов рабочих часов и праздников, создание и изменение рабочих процессов, а также удаление рабочих групп.</span><span class="sxs-lookup"><span data-stu-id="f8093-107">Topics in this section identify best practices for designing IVR workflows, and explain how to create customized business hours and holiday sets, how to create or modify workflows, and how to delete workgroups.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f8093-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="f8093-108">In This Section</span></span>

  - [<span data-ttu-id="f8093-109">Проектирование потоков вызовов интерактивного голосового ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8093-109">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="f8093-110">Необязательно Определение рабочих часов для группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8093-110">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="f8093-111">Необязательно Определение наборов праздников группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8093-111">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="f8093-112">Создание или изменение рабочего процесса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8093-112">Create or modify a workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-workflow.md)

  - [<span data-ttu-id="f8093-113">Удаление рабочего процесса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8093-113">Delete a workflow in Lync Server 2013</span></span>](lync-server-2013-delete-a-workflow.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

