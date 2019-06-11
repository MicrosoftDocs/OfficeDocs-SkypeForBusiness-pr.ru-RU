---
title: 'Lync Server 2013: процесс планирования большого количества собраний'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af97cdbd07603c420780a92fbbe0a03c8a4d0520
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="35d8d-102">Процесс планирования большого количества собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35d8d-102">Large-meeting scheduling process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35d8d-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="35d8d-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="35d8d-104">Поскольку в выделенном большом пуле собраний поддерживается только одно большое собрание, мы рекомендуем реализовать большой процесс планирования собраний, чтобы предотвратить конфликты крупных собраний.</span><span class="sxs-lookup"><span data-stu-id="35d8d-104">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="35d8d-105">Цель такого процесса планирования состоит в том, чтобы упростить настройку крупных собраний.</span><span class="sxs-lookup"><span data-stu-id="35d8d-105">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="35d8d-106">Такая возможность не предоставляется непосредственно клиентам Lync Server или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35d8d-106">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="35d8d-107">Этот процесс может быть реализован, в частности, на основе системы билетов, если в данной организации такая система применяется в службе поддержки.</span><span class="sxs-lookup"><span data-stu-id="35d8d-107">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="35d8d-108">Для организаторов крупных собраний планирование большого собрания включает в себя выполнение описанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="35d8d-108">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="35d8d-p102">Организатор собрания или делегат определяет время, продолжительность и размер предстоящего собрания, а также список выступающих. Если ожидаемый размер собрания превышает 250 пользователей или если требуется улучшить взаимодействие с пользователями при числе участников меньше 250, организатор или делегат подает запрос на проведение большого собрания.</span><span class="sxs-lookup"><span data-stu-id="35d8d-p102">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters. If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="35d8d-p103">Специалист по планированию проверяет свободны ли требуемые дата и время. Поскольку мы поддерживаем одновременное проведение только одного большого собрания в выделенном пуле, специалисту по планированию требуется свериться с календарем больших собраний, чтобы определить, не запланировано ли на этот день и это время другое собрание. Если запрошенное время доступно, специалист по планированию утверждает запрос на собрание.</span><span class="sxs-lookup"><span data-stu-id="35d8d-p103">The scheduling staff checks to see whether the requested date and time is available. Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time. If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="35d8d-114">Если запрос утверждается, сотрудники планировщика (с использованием учетных данных в выделенном пуле) используют надстройку "собрание по сети" для Lync 2013 с Outlook, чтобы настроить собрание в специальном пуле для крупных собраний.</span><span class="sxs-lookup"><span data-stu-id="35d8d-114">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="35d8d-115">URL-адрес для присоединения к собранию предоставляется инициатору запроса в составе уведомления об утверждении.</span><span class="sxs-lookup"><span data-stu-id="35d8d-115">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="35d8d-p105">Организатор собрания или уполномоченный пользователь с помощью Outlook планирует предстоящее собрание, добавляя к приглашению на собрание URL-адрес для присоединения к собранию. Затем организатор собрания или уполномоченный пользователь определяет пользователей, которых требуется пригласить, и рассылает приглашение на собрание.</span><span class="sxs-lookup"><span data-stu-id="35d8d-p105">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation. The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="35d8d-118">На приведенном ниже рисунке показан типичный рабочий процесс запроса и утверждения для планирования крупных собраний.</span><span class="sxs-lookup"><span data-stu-id="35d8d-118">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="35d8d-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d] (images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="35d8d-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

