---
title: 'Lync Server 2013: процесс планирования больших собраний'
description: 'Lync Server 2013: процесс планирования больших собраний.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96d383b6da96fb7d36e031485feac2ff927df347
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557595"
---
# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="e2734-103">Процесс планирования больших собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2734-103">Large-meeting scheduling process in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2734-104">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="e2734-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="e2734-105">Поскольку в выделенном пуле больших собраний одновременно можно проводить только одно большое собрание, мы рекомендуем внедрить процесс планирования больших собраний, чтобы избежать конфликтов между большими собраниями.</span><span class="sxs-lookup"><span data-stu-id="e2734-105">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="e2734-106">Задача такого процесса планирования заключается в упрощении проведения больших собраний.</span><span class="sxs-lookup"><span data-stu-id="e2734-106">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="e2734-107">Такая возможность не предоставляется непосредственно клиентами Lync Server или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e2734-107">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="e2734-108">Одним из способов реализации такого процесса является использование билетной системы службы технической поддержки вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e2734-108">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="e2734-109">Планирование большого собрания у организаторов больших собраний включает в себя следующие этапы:</span><span class="sxs-lookup"><span data-stu-id="e2734-109">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="e2734-p102">Организатор собрания или делегат определяет  время, продолжительность и размер предстоящего собрания, а также список выступающих. Если ожидаемый размер собрания превышает 250 пользователей или если требуется улучшить взаимодействие с пользователями при числе участников меньше 250, организатор или делегат подает запрос на проведение большого собрания.</span><span class="sxs-lookup"><span data-stu-id="e2734-p102">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters. If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="e2734-p103">Специалист по планированию проверяет свободны ли требуемые дата и время. Поскольку мы поддерживаем одновременное проведение только одного большого собрания в выделенном пуле, специалисту по планированию требуется свериться с календарем больших собраний, чтобы определить, не запланировано ли на этот день и это время другое собрание. Если запрошенное время доступно, специалист по планированию утверждает запрос на собрание.</span><span class="sxs-lookup"><span data-stu-id="e2734-p103">The scheduling staff checks to see whether the requested date and time is available. Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time. If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="e2734-115">Если запрос утвержден, сотрудники планирования (с использованием учетных данных в выделенном пуле) используют надстройку "собрание по сети" для Lync 2013 с Outlook, чтобы настроить собрание в выделенном пуле больших собраний.</span><span class="sxs-lookup"><span data-stu-id="e2734-115">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="e2734-116">URL-адрес для присоединения к собранию предоставляется инициатору запроса в рамках процедуры утверждения.</span><span class="sxs-lookup"><span data-stu-id="e2734-116">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="e2734-117">Организатор собрания или представитель использует Outlook для планирования предстоящего собрания, добавляя URL-адрес для присоединения к собранию к приглашению на собрание.</span><span class="sxs-lookup"><span data-stu-id="e2734-117">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="e2734-118">После этого организатор собрания или делегат указывает приглашенных пользователей и рассылает приглашение на собрание.</span><span class="sxs-lookup"><span data-stu-id="e2734-118">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="e2734-119">На следующем рисунке приведена иллюстрация для типичного рабочего процесса запроса и утверждения при планировании больших собраний.</span><span class="sxs-lookup"><span data-stu-id="e2734-119">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="e2734-120">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="e2734-120">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

