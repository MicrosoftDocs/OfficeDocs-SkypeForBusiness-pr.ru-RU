---
title: 'Lync Server 2013: Обзор сценариев создания рабочих процессов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of workflow creation scenarios
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204646(v=OCS.15)
ms:contentKeyID: 48183309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27383db13176150078bf4855dee4df57cb1615af
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "41989884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a><span data-ttu-id="da5a5-102">Обзор сценариев создания рабочих процессов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da5a5-102">Overview of workflow creation scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da5a5-103">_**Последнее изменение темы:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="da5a5-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="da5a5-104">Существует два возможных сценария создания рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="da5a5-104">When you create workflows, there are two possible scenarios:</span></span>

  - <span data-ttu-id="da5a5-105">**Администратор создает и настраивает рабочий процесс**. Участник роли CsResponseGroupAdministrator (или эквивалентной роли) создает и активирует рабочий процесс и все элементы в этом рабочем процессе, такие как группы агентов, очереди, выходные дни, рабочие часы, воспроизведение музыки на удержании и т. д.</span><span class="sxs-lookup"><span data-stu-id="da5a5-105">**The Administrator creates and configures the workflow** — The CsResponseGroupAdministrator role member (or equivalent) creates and activates the workflow and all elements in the workflow, such as the agent groups, queues, holiday and business hours, music on hold, and so on.</span></span>

  - <span data-ttu-id="da5a5-p101">**Администратор создает рабочий процесс, а менеджер настраивает параметры**. Участник роли CsResponseGroupAdministrator (или эквивалентной роли) задает основной SIP URI, отображаемое имя, назначает хотя бы одного участника роли CsResponseGroupManager и выбирает очередь. Администратор устанавливает рабочий процесс, но не активирует его. Затем участник роли CsResponseGroupManager может войти и изменить конфигурацию рабочего процесса, создав группы агентов и назначив эти группы в очередь, настроив телефонный номер, выходные дни, рабочие часы, воспроизведение музыки на удержании и другие параметры.</span><span class="sxs-lookup"><span data-stu-id="da5a5-p101">**The Administrator creates the workflow and the Manager configures options** — The CsResponseGroupAdministrator role member (or equivalent) defines the primary SIP URI, Display Name, assigns a member or members of the CsResponseGroupManager role, and selects a queue and activates the workflow. The CsResponseGroupManager can then log on and edit the configuration of the workflow by creating agent groups and also assigns the group to the queue, configuring the telephone number, holiday and business hours, music on hold, and so on.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da5a5-p102">Если нужно создать управляемый рабочий процесс, рабочий процесс необходимо создать как активный. После сохранения активный управляемый процесс можно изменить и отключить.</span><span class="sxs-lookup"><span data-stu-id="da5a5-p102">When you want to create a managed workflow, you need to create the workflow as active. After you save an active, managed workflow, you can then modify and deactivate the workflow.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

