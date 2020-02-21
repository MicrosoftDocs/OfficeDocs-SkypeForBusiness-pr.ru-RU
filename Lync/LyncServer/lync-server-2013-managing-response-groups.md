---
title: 'Lync Server 2013: Управление группами ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 286ffe3450c3363b94e3ef1b0cd1905e70fd36eb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-response-groups-in-lync-server-2013"></a><span data-ttu-id="c9771-102">Управление группами ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9771-102">Managing response groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9771-103">_**Последнее изменение темы:** 2018-02-01_</span><span class="sxs-lookup"><span data-stu-id="c9771-103">_**Topic Last Modified:** 2018-02-01_</span></span>

<span data-ttu-id="c9771-104">Группы ответа — это компонент управления вызовами, который позволяет поместить в очередь вызовы, предназначенные определенной области, например службе технической поддержки, и затем перенаправить их группе назначенных людей, которых называют *агентами*.</span><span class="sxs-lookup"><span data-stu-id="c9771-104">Response groups are a call management feature that enables you to queue calls that are made to a specific area, such as a Help Desk, and then route the calls to a designated group of people, called *agents*.</span></span>

<span data-ttu-id="c9771-105">Чтобы управлять группами ответов, следует настроить группы агентов, очереди и рабочие процессы, которые определяют, что происходит с вызовом с момента его получения до момента ответа на него агентом.</span><span class="sxs-lookup"><span data-stu-id="c9771-105">To manage response groups, you configure agent groups, queues, and workflows, which define what happens to a call from the time it is placed until an agent answers it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9771-106">Если в развертывании группы ответа более 300 рабочих процессов, лучше использовать командлеты командной консоли Lync Server для создания рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="c9771-106">If you have more than 300 workflows in a single pool in your Response Group deployment, it is better to use Lync Server Management Shell cmdlets to create the workflows.</span></span> <span data-ttu-id="c9771-107">Если для создания рабочих процессов в пуле с более чем 300 рабочими процессами использовать средство настройки группы ответа, загрузка веб-страницы занимает слишком много времени.</span><span class="sxs-lookup"><span data-stu-id="c9771-107">If you use the Response Group Configuration Tool to create workflows for a pool that has more than 300 workflows, the webpage takes a long time to load.</span></span> <span data-ttu-id="c9771-108">Количество агентов, косвенно связанных с рабочими процессами через очереди, также имеет пропорциональные эффекты загрузки страниц.</span><span class="sxs-lookup"><span data-stu-id="c9771-108">The number of agents that are indirectly associated with workflows through the queues also has a proportional effect on page loading.</span></span>



</div>

<span data-ttu-id="c9771-109">В подразделах этого раздела приводятся пошаговые процедуры для выполнения задач по настройке и обслуживанию приложения группы ответа в развертывании.</span><span class="sxs-lookup"><span data-stu-id="c9771-109">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Response Group application in your deployment</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c9771-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="c9771-110">In This Section</span></span>

  - [<span data-ttu-id="c9771-111">Управление группами агентов группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9771-111">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)

  - [<span data-ttu-id="c9771-112">Управление очередями групп ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9771-112">Managing Response Group queues in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-queues.md)

  - [<span data-ttu-id="c9771-113">Управление рабочими процессами группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9771-113">Managing Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-workflows.md)

  - [<span data-ttu-id="c9771-114">Управление параметрами группы ответа уровня приложения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9771-114">Managing application-level Response Group settings in Lync Server 2013</span></span>](lync-server-2013-managing-application-level-response-group-settings.md)

  - [<span data-ttu-id="c9771-115">Перемещение групп ответа в новый пул в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9771-115">Moving response groups to a new pool in Lync Server 2013</span></span>](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [<span data-ttu-id="c9771-116">Управление группами ответа в Lync Server 2013 во время аварии</span><span class="sxs-lookup"><span data-stu-id="c9771-116">Managing response groups in Lync Server 2013 during a disaster</span></span>](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

