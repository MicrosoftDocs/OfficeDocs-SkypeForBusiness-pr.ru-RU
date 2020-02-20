---
title: 'Lync Server 2013: создание рабочих процессов группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group workflows
ms:assetid: 41272258-728d-42bd-b4d4-2a499734c720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425918(v=OCS.15)
ms:contentKeyID: 48183954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f927d5257c3e4217c8f16f3e5138d075d91b858c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="f0a44-102">Создание рабочих процессов группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0a44-102">Create Response Group workflows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0a44-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f0a44-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f0a44-p101">Рабочий процесс определяет порядок обработки вызова с момента телефонного звонка до момента ответа на вызов. Этот рабочий процесс задает очередь удержания вызова и определяет метод маршрутизации, используемый для сервисных групп, а также вопросы и ответы, используемые для интерактивных групп ответа. Рабочий процесс также задает такие параметры, как приветственное сообщение, музыка при удержании, часы работы и выходные.</span><span class="sxs-lookup"><span data-stu-id="f0a44-p101">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call. The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups. A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

<span data-ttu-id="f0a44-107">Для создания рабочих процессов используется средство настройки группы ответа.</span><span class="sxs-lookup"><span data-stu-id="f0a44-107">You use the Response Group Configuration Tool to create workflows.</span></span> <span data-ttu-id="f0a44-108">Доступ к средству настройки группы ответа можно получить на странице "группа ответа" в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0a44-108">You can access the Response Group Configuration Tool from the Response Group page of Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f0a44-109">Вы должны создать группы агентов и очереди перед созданием рабочего процесса, в котором они используются.</span><span class="sxs-lookup"><span data-stu-id="f0a44-109">You must create agent groups and queues before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f0a44-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="f0a44-110">In This Section</span></span>

  - [<span data-ttu-id="f0a44-111">Создание или изменение рабочего процесса сервисной группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0a44-111">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="f0a44-112">Проектирование потоков вызовов интерактивного голосового ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0a44-112">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="f0a44-113">Создание или изменение интерактивного рабочего процесса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0a44-113">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="f0a44-114">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f0a44-114">Related Sections</span></span>

  - [<span data-ttu-id="f0a44-115">Создание групп агентов группы ответа Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0a44-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="f0a44-116">Создание очередей группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0a44-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

