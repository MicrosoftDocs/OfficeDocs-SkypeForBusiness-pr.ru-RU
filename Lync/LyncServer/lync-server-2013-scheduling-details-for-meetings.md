---
title: 'Lync Server 2013: планирование сведений о собраниях'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dd61ce47daf1898afd1fb654493ef12ebee9ff1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a><span data-ttu-id="2ab51-102">Сведения о планировании собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ab51-102">Scheduling details for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ab51-103">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="2ab51-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="2ab51-104">После проверки отсутствия другого запланированного собрания на запрашиваемое время, персонал поддержки, который обрабатывает запрос, планирует собрание в пуле больших собраний.</span><span class="sxs-lookup"><span data-stu-id="2ab51-104">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> <span data-ttu-id="2ab51-105">Используйте надстройку "собрание по сети" для Lync, установленную вместе с клиентом Lync Server 2013 для выполнения этой задачи, используя учетные данные пользователя, доступного для Lync Server, в выделенном пуле больших собраний.</span><span class="sxs-lookup"><span data-stu-id="2ab51-105">Use the Online Meeting Add-in for Lync that is installed with the Lync Server 2013 client to perform this task, using the credentials of a user enabled for Lync Server in the dedicated large-meeting pool.</span></span>

<span data-ttu-id="2ab51-106">Чтобы обеспечить наилучшее взаимодействие с пользователями, важно запланировать большое собрание с правильными уровнями доступа и параметрами, соответствующими потребностям организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="2ab51-106">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer’s needs.</span></span> <span data-ttu-id="2ab51-107">Мы рекомендуем использовать следующие параметры планирования, настроенные в параметрах собрания Lync:</span><span class="sxs-lookup"><span data-stu-id="2ab51-107">We recommend the following scheduling settings configured in Lync Meeting options:</span></span>

  - <span data-ttu-id="2ab51-108">Используйте новое место собрания для каждого большого собрания вместо повторного использования выделенного места собрания.</span><span class="sxs-lookup"><span data-stu-id="2ab51-108">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span>

  - <span data-ttu-id="2ab51-109">Указывайте уровень доступа к собранию следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2ab51-109">Specify the meeting access level as follows:</span></span>
    
      - <span data-ttu-id="2ab51-p103">Если хотя бы один приглашенный является внешним по отношению к организации, установите тип доступа к собранию **Все (без исключений)**. Это позволит исключить необходимость управления потенциально большим "залом ожидания" во время проведения собрания.</span><span class="sxs-lookup"><span data-stu-id="2ab51-p103">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions**. This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
      - <span data-ttu-id="2ab51-112">Если собрание только внутреннее, установите тип доступа к собранию **Все во организации**.</span><span class="sxs-lookup"><span data-stu-id="2ab51-112">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2ab51-113">Избегайте устанавливать тип доступа к собранию <STRONG>Приглашенные пользователи из организации</STRONG>, поскольку при использовании этого параметра придется добавлять адреса электронной почты всех пользователей в список приглашенных. Кроме того, при использовании этого параметра не работает приглашение групп рассылки.</span><span class="sxs-lookup"><span data-stu-id="2ab51-113">Avoid setting the meeting access type to <STRONG>People I invite from my company</STRONG> because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span><BR><span data-ttu-id="2ab51-p104">Избегайте устанавливать тип доступа <STRONG>Только организатор</STRONG>, поскольку при использовании этого параметра во время проведения собрания в "зал ожидания" должны помещаться все участники собрания, включая выступающих. Лицо, отвечающее за проведение собрания, должно затем постоянно наблюдать за реестром "зала ожидания" и допускать новых пользователей из "зала ожидания".</span><span class="sxs-lookup"><span data-stu-id="2ab51-p104">Avoid setting the meeting access type to <STRONG>Only me, the meeting organizer</STRONG> because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time. The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>

        
        </div>

  - <span data-ttu-id="2ab51-116">Разрешите пользователям автоматически присоединяться к собранию путем вызова с телефонного аппарата, включив параметр **Вызывающие абоненты присоединяются напрямую**.</span><span class="sxs-lookup"><span data-stu-id="2ab51-116">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>

  - <span data-ttu-id="2ab51-117">Явным образом приглашайте следующих пользователей:</span><span class="sxs-lookup"><span data-stu-id="2ab51-117">Explicitly invite the following users:</span></span>
    
      - <span data-ttu-id="2ab51-118">организатор собрания и делегат (инициатор запроса);</span><span class="sxs-lookup"><span data-stu-id="2ab51-118">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="2ab51-119">список выступающих, предоставленный инициатором запроса на собрание.</span><span class="sxs-lookup"><span data-stu-id="2ab51-119">The list of presenters provided by a meeting requester</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2ab51-120">Если установлен тип доступа к собранию <STRONG>Выбранные пользователи</STRONG>, то требуется явно добавлять каждого участника большого собрания как приглашенного на собрание.</span><span class="sxs-lookup"><span data-stu-id="2ab51-120">If the meeting access type is set to <STRONG>People I choose</STRONG>, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="2ab51-p105">Явно управляйте докладчиками вместо определения параметра докладчика в качестве одного из значений автоматического продвижения. Убедитесь, что следующие пользователи добавлены в качестве докладчиков:</span><span class="sxs-lookup"><span data-stu-id="2ab51-p105">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
      - <span data-ttu-id="2ab51-123">организатор собрания и делегат (инициатор запроса);</span><span class="sxs-lookup"><span data-stu-id="2ab51-123">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="2ab51-124">список выступающих, предоставленный инициаторами запроса на большое собрание.</span><span class="sxs-lookup"><span data-stu-id="2ab51-124">The list of presenters provided by large meeting requesters</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2ab51-p106">Явное управление выступающими позволяет контролировать количество докладчиков, чтобы можно было сузить количество докладчиков до количества, достаточного для проведения эффективного большого собрания. Если большинство участников имеет роль участника, это помогает уменьшить вероятность случайного получения контроля над выступлением, удаления презентации PowerPoint, включения или отключения микрофона выступающих и других нарушений в собрании.</span><span class="sxs-lookup"><span data-stu-id="2ab51-p106">By explicitly managing presenters, you can control the number of presenters, so that you can limit presenters to a small enough number to make it possible to have an effective large meeting. If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="2ab51-127">Проверьте параметр **Отключить всех участников**, чтобы было слышно только докладчиков.</span><span class="sxs-lookup"><span data-stu-id="2ab51-127">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>

  - <span data-ttu-id="2ab51-128">Проверьте параметр **Заблокировать видео участников**, чтобы было видно только докладчиков.</span><span class="sxs-lookup"><span data-stu-id="2ab51-128">Check the **Block attendees’ video** setting to make sure only presenters can broadcast video into the meeting.</span></span>

<span data-ttu-id="2ab51-129">На следующем рисунке показаны рекомендуемые параметры для надстройки "собрание по сети" для Lync.</span><span class="sxs-lookup"><span data-stu-id="2ab51-129">The following figure shows the recommended settings for the Online Meeting Add-in for Lync.</span></span>

<span data-ttu-id="2ab51-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span><span class="sxs-lookup"><span data-stu-id="2ab51-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

