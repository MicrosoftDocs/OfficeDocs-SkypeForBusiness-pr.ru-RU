---
title: 'Lync Server 2013: Настройка группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c40f48b52759bfc12441a558b85de89d149f4bf1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196492"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a><span data-ttu-id="bc15d-102">Настройка группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc15d-102">Configuring Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc15d-103">_**Последнее изменение темы:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="bc15d-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="bc15d-104">Группа ответа — это функция корпоративной голосовой связи, которая выполняет маршрутизацию и очередность входящих звонков в группы людей, называемых *агентами*, например службой поддержки или службой поддержки клиентов.</span><span class="sxs-lookup"><span data-stu-id="bc15d-104">Response Group is an Enterprise Voice feature that routes and queues incoming calls to groups of people, called *agents*, such as a help desk or a customer service desk.</span></span>

<span data-ttu-id="bc15d-105">Компоненты, необходимые для группы ответа, устанавливаются и включаются автоматически на сервере переднего плана или сервере Standard Edition при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="bc15d-105">The components that Response Group requires are installed and enabled automatically on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="bc15d-106">Чтобы предоставить доступ к группе ответа пользователям, необходимо настроить группы агентов, затем очереди и рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="bc15d-106">To make Response Group available to users, you must configure agent groups, then queues, and then workflows.</span></span> <span data-ttu-id="bc15d-107">Кроме того, администратор группы ответа может делегировать настройку существующего рабочего процесса диспетчеру группы ответа, который может изменить и изменить рабочий процесс и связанные с ним группы агентов и очереди.</span><span class="sxs-lookup"><span data-stu-id="bc15d-107">Additionally, a Response Group Administrator can delegate configuration of an existing workflow to a Response Group Manager, who can then modify and reconfigure the workflow and its associated agent groups and queues.</span></span>

<span data-ttu-id="bc15d-108">В этом разделе описывается настройка группы ответа Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc15d-108">This section guides you through the configuration of Lync Server 2013 Response Group.</span></span> <span data-ttu-id="bc15d-109">Предполагается, что вы уже прочитали разделы планирования, связанные с группой ответа и развернули сервер Enterprise Edition или сервер Standard Edition с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="bc15d-109">It assumes that you have already read the planning sections related to Response Group and have deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="bc15d-110">Для получения дополнительных сведений о создании группы ответа с помощью командной консоли Lync Server, в том числе примера скрипта, обратитесь к разделу "Создание первой группы ответа с помощью <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A>командной консоли Lync Server".</span><span class="sxs-lookup"><span data-stu-id="bc15d-110">For details about creating a Response Group by using Lync Server Management Shell, including a sample script, see "Creating Your First Response Group Using Lync Server Management Shell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bc15d-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="bc15d-111">In This Section</span></span>

  - [<span data-ttu-id="bc15d-112">Разрешения и необходимые условия для настройки группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc15d-112">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [<span data-ttu-id="bc15d-113">Процесс развертывания для группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc15d-113">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

  - [<span data-ttu-id="bc15d-114">Обзор сценариев создания рабочих процессов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc15d-114">Overview of workflow creation scenarios in Lync Server 2013</span></span>](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [<span data-ttu-id="bc15d-115">Создание групп агентов группы ответа Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc15d-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="bc15d-116">Создание очередей группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc15d-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

  - [<span data-ttu-id="bc15d-117">Необязательно Определение рабочих часов для группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc15d-117">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="bc15d-118">Необязательно Определение наборов праздников группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc15d-118">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="bc15d-119">Создание рабочих процессов группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc15d-119">Create Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-create-response-group-workflows.md)

  - [<span data-ttu-id="bc15d-120">Необязательно Проверка развертывания группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc15d-120">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bc15d-121">См. также</span><span class="sxs-lookup"><span data-stu-id="bc15d-121">See Also</span></span>


[<span data-ttu-id="bc15d-122">Планирование функций управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc15d-122">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

