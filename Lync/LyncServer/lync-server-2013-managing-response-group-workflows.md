---
title: 'Lync Server 2013: Управление рабочими процессами группы ответа'
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
ms.openlocfilehash: 4175d92e8d94313cfe03fd7e87b511573e4e313c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="d7ac2-102">Управление рабочими процессами группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7ac2-102">Managing Response Group workflows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7ac2-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d7ac2-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d7ac2-104">Рабочий процесс группы ответа определяет поведение звонка с момента звонка с телефона на время, когда агент отвечает на вызов.</span><span class="sxs-lookup"><span data-stu-id="d7ac2-104">A Response Group workflow defines the behavior of a call from the time that the phone rings to the time that an agent answers the call.</span></span> <span data-ttu-id="d7ac2-105">Этот рабочий процесс включает сведения об очереди и маршрутизации, а также сведения либо о сервисной группе, либо об интерактивном автоответчике (IVR).</span><span class="sxs-lookup"><span data-stu-id="d7ac2-105">The workflow includes queue and routing information, and includes either hunt group or interactive voice response (IVR) information.</span></span>

<span data-ttu-id="d7ac2-106">В разделах этой статьи даются рекомендации по разработке рабочих процессов IVR, а также объясняется создание пользовательских наборов рабочих часов и праздников, создание и изменение рабочих процессов, а также удаление рабочих групп.</span><span class="sxs-lookup"><span data-stu-id="d7ac2-106">Topics in this section identify best practices for designing IVR workflows, and explain how to create customized business hours and holiday sets, how to create or modify workflows, and how to delete workgroups.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d7ac2-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="d7ac2-107">In This Section</span></span>

  - [<span data-ttu-id="d7ac2-108">Проектирование потоков вызовов интерактивного голосового ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7ac2-108">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="d7ac2-109">Необязательно Определение рабочих часов для группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7ac2-109">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="d7ac2-110">Необязательно Определение наборов праздников группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7ac2-110">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="d7ac2-111">Создание или изменение рабочего процесса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7ac2-111">Create or modify a workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-workflow.md)

  - [<span data-ttu-id="d7ac2-112">Удаление рабочего процесса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7ac2-112">Delete a workflow in Lync Server 2013</span></span>](lync-server-2013-delete-a-workflow.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

