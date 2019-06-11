---
title: 'Lync Server 2013: создание или изменение рабочего процесса'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a workflow
ms:assetid: 5ac1c0f3-e82f-40ca-b972-91950e38c05b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520997(v=OCS.15)
ms:contentKeyID: 48184225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9725958a302f50b0d1cdddf399b98fdd47ff6fc2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-workflow-in-lync-server-2013"></a><span data-ttu-id="49ce6-102">Создание или изменение рабочего процесса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49ce6-102">Create or modify a workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49ce6-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="49ce6-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="49ce6-104">Lync Server 2013 поддерживает два типа рабочих процессов: группу слежения и интерактивный голосовой ответ (интерактивный автоответчик).</span><span class="sxs-lookup"><span data-stu-id="49ce6-104">Lync Server 2013 supports two types of workflows: hunt group and interactive voice response (IVR).</span></span> <span data-ttu-id="49ce6-105">Когда вы создаете рабочий процесс, вы можете указать используемую очередь и другие параметры, такие как приветственное сообщение, музыка на удержании, рабочие часы и вопросы о том, что приложение группы ответа запрашивает вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="49ce6-105">When you create a workflow, you use the Response Group Configuration Tool to specify the queue to use and other settings, such as a welcome message, music on hold, business hours, and questions that the Response Group application asks the caller.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="49ce6-106">Вам следует создать группы агентов и очереди до создания рабочего процесса, который их использует.</span><span class="sxs-lookup"><span data-stu-id="49ce6-106">You must create agent groups and queues before you create a workflow that uses them.</span></span> <span data-ttu-id="49ce6-107">Если вы хотите создать стандартные рабочие часы и праздничные дни, которые можно использовать для нескольких рабочих процессов, необходимо также определить эти часы и праздничные дни перед созданием рабочего процесса, в котором они используются.</span><span class="sxs-lookup"><span data-stu-id="49ce6-107">If you want to create predefined business hours and holidays that you can use for multiple workflows, you must also define these hours and holidays before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="49ce6-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="49ce6-108">In This Section</span></span>

  - [<span data-ttu-id="49ce6-109">Создание или изменение рабочего процесса группы слежения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49ce6-109">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="49ce6-110">Создание или изменение интерактивного рабочего процесса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49ce6-110">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="49ce6-111">См. также</span><span class="sxs-lookup"><span data-stu-id="49ce6-111">See Also</span></span>


[<span data-ttu-id="49ce6-112">Создание или изменение группы агента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49ce6-112">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  
[<span data-ttu-id="49ce6-113">Создание и изменение очереди в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49ce6-113">Create or modify a queue in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-queue.md)  
[<span data-ttu-id="49ce6-114">Необязательно Определение наборов праздников группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49ce6-114">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="49ce6-115">Необязательно Определение группы ответа в рабочее время в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49ce6-115">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

