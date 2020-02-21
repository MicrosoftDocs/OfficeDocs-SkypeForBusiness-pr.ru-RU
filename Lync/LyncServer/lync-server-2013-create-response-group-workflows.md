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
ms.openlocfilehash: c69a3401073762071dfbe6a235ffb8a2eab0a3fa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="2acd0-102">Создание рабочих процессов группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2acd0-102">Create Response Group workflows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2acd0-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2acd0-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2acd0-p101">Рабочий процесс определяет порядок обработки вызова с момента телефонного звонка до момента ответа на вызов. Этот рабочий процесс задает очередь удержания вызова и определяет метод маршрутизации, используемый для сервисных групп, а также вопросы и ответы, используемые для интерактивных групп ответа. Рабочий процесс также задает такие параметры, как приветственное сообщение, музыка при удержании, часы работы и выходные.</span><span class="sxs-lookup"><span data-stu-id="2acd0-p101">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call. The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups. A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

<span data-ttu-id="2acd0-107">Для создания рабочих процессов используется средство настройки группы ответа.</span><span class="sxs-lookup"><span data-stu-id="2acd0-107">You use the Response Group Configuration Tool to create workflows.</span></span> <span data-ttu-id="2acd0-108">Доступ к средству настройки группы ответа можно получить на странице "группа ответа" в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2acd0-108">You can access the Response Group Configuration Tool from the Response Group page of Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2acd0-109">Вы должны создать группы агентов и очереди перед созданием рабочего процесса, в котором они используются.</span><span class="sxs-lookup"><span data-stu-id="2acd0-109">You must create agent groups and queues before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2acd0-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="2acd0-110">In This Section</span></span>

  - [<span data-ttu-id="2acd0-111">Создание или изменение рабочего процесса сервисной группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2acd0-111">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="2acd0-112">Проектирование потоков вызовов интерактивного голосового ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2acd0-112">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="2acd0-113">Создание или изменение интерактивного рабочего процесса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2acd0-113">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="2acd0-114">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="2acd0-114">Related Sections</span></span>

  - [<span data-ttu-id="2acd0-115">Создание групп агентов группы ответа Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2acd0-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="2acd0-116">Создание очередей группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2acd0-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

