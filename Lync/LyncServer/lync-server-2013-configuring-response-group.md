---
title: 'Lync Server 2013: настройка группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4d12d1ee21cfa5e480dea52a0de9f89b250715c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a><span data-ttu-id="152db-102">Настройка группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="152db-102">Configuring Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="152db-103">_**Тема последнего изменения:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="152db-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="152db-104">Группа ответа — это корпоративная функция голосовой связи, которая направляет входящие звонки на группы пользователей, называемые *агентами*, например службой поддержки пользователей или рабочим столом.</span><span class="sxs-lookup"><span data-stu-id="152db-104">Response Group is an Enterprise Voice feature that routes and queues incoming calls to groups of people, called *agents*, such as a help desk or a customer service desk.</span></span>

<span data-ttu-id="152db-105">Компоненты, необходимые для группы ответа, устанавливаются и включаются автоматически на сервере переднего плана или стандартном сервере Standard Edition при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="152db-105">The components that Response Group requires are installed and enabled automatically on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="152db-106">Чтобы предоставить доступ к группе ответа пользователям, необходимо настроить группы агента, затем очереди и рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="152db-106">To make Response Group available to users, you must configure agent groups, then queues, and then workflows.</span></span> <span data-ttu-id="152db-107">Кроме того, администратор группы ответа может делегировать настройку существующего рабочего процесса в Диспетчер групп ответа, который может затем изменить и повторно настроить рабочий процесс, а также связанные группы агентов и очереди.</span><span class="sxs-lookup"><span data-stu-id="152db-107">Additionally, a Response Group Administrator can delegate configuration of an existing workflow to a Response Group Manager, who can then modify and reconfigure the workflow and its associated agent groups and queues.</span></span>

<span data-ttu-id="152db-108">В этом разделе рассказывается, как настроить группу ответа Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="152db-108">This section guides you through the configuration of Lync Server 2013 Response Group.</span></span> <span data-ttu-id="152db-109">Предполагается, что вы уже прочитали разделы планирование, связанные с группой ответа и развернули сервер Enterprise Edition либо сервер Standard Edition с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="152db-109">It assumes that you have already read the planning sections related to Response Group and have deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="152db-110">Сведения о создании группы ответа с помощью командной консоли Lync Server Management Shell, включая пример сценария, приведены в <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>разделе "Создание первой группы ответа с помощью командной консоли Lync Server".</span><span class="sxs-lookup"><span data-stu-id="152db-110">For details about creating a Response Group by using Lync Server Management Shell, including a sample script, see "Creating Your First Response Group Using Lync Server Management Shell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="152db-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="152db-111">In This Section</span></span>

  - [<span data-ttu-id="152db-112">Разрешения и необходимые условия для настройки группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="152db-112">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [<span data-ttu-id="152db-113">Процесс развертывания группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="152db-113">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

  - [<span data-ttu-id="152db-114">Обзор сценариев создания рабочих процессов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="152db-114">Overview of workflow creation scenarios in Lync Server 2013</span></span>](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [<span data-ttu-id="152db-115">Создание групп агента группы ответа Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="152db-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="152db-116">Создание очередей группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="152db-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

  - [<span data-ttu-id="152db-117">Необязательно Определение группы ответа в рабочее время в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="152db-117">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="152db-118">Необязательно Определение наборов праздников группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="152db-118">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="152db-119">Создание рабочих процессов для группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="152db-119">Create Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-create-response-group-workflows.md)

  - [<span data-ttu-id="152db-120">Необязательно Проверка развертывания группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="152db-120">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="152db-121">См. также</span><span class="sxs-lookup"><span data-stu-id="152db-121">See Also</span></span>


[<span data-ttu-id="152db-122">Планирование функций управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="152db-122">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

