---
title: 'Lync Server 2013: планирование данных для собраний'
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
ms.openlocfilehash: a4a0f85e93588e725e825fee22a8c2e95b74095b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a><span data-ttu-id="1dcfa-102">Сведения о расписании собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1dcfa-102">Scheduling details for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dcfa-103">_**Тема последнего изменения:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="1dcfa-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="1dcfa-104">После проверки отсутствия другого запланированного собрания на запрашиваемое время, персонал поддержки, который обрабатывает запрос, планирует собрание в пуле больших собраний.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-104">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> <span data-ttu-id="1dcfa-105">Используйте надстройку "собрание по сети" для Lync, установленную в клиенте Lync Server 2013 для выполнения этой задачи, используя учетные данные пользователя, доступного для Lync Server, в специальном пуле для крупных собраний.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-105">Use the Online Meeting Add-in for Lync that is installed with the Lync Server 2013 client to perform this task, using the credentials of a user enabled for Lync Server in the dedicated large-meeting pool.</span></span>

<span data-ttu-id="1dcfa-106">Для оптимального взаимодействия с пользователями важно при планировании большого собрания задать уровни прав доступа и параметры, соответствующие задачам организатора.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-106">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer’s needs.</span></span> <span data-ttu-id="1dcfa-107">Для параметров собрания Lync рекомендуется настроить следующие параметры планирования:</span><span class="sxs-lookup"><span data-stu-id="1dcfa-107">We recommend the following scheduling settings configured in Lync Meeting options:</span></span>

  - <span data-ttu-id="1dcfa-108">Используйте новое место собрания для каждого большого собрания вместо повторного использования выделенного места собрания.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-108">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span>

  - <span data-ttu-id="1dcfa-109">Указывайте уровень доступа к собранию следующим образом.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-109">Specify the meeting access level as follows:</span></span>
    
      - <span data-ttu-id="1dcfa-110">Если по крайней мере один приглашенный пользователь является внешним по отношению к Организации, задайте для него тип доступа к собранию " **все" (без ограничений**).</span><span class="sxs-lookup"><span data-stu-id="1dcfa-110">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions**.</span></span> <span data-ttu-id="1dcfa-111">Это устраняет необходимость в управлении потенциально большим "залом ожидания" во время собрания.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-111">This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
      - <span data-ttu-id="1dcfa-112">Если собрание полностью внутреннее, задайте тип доступа к собранию **Все пользователи из моей организации**.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-112">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1dcfa-113">Не рекомендуется задавать тип доступа к собранию <STRONG>Приглашенные мной люди из организации</STRONG>, так как в этом режиме организаторы должны добавлять к списку приглашенных адреса электронной почты всех пользователей, и пригласить группу рассылки невозможно.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-113">Avoid setting the meeting access type to <STRONG>People I invite from my company</STRONG> because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span><BR><span data-ttu-id="1dcfa-114">Не рекомендуется задавать тип доступа к собранию <STRONG>Только мне, организатору собрания</STRONG>, так как в этом режиме необходимо, чтобы все участники, включая докладчиков, были помещены в "зал ожидания" во время собрания.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-114">Avoid setting the meeting access type to <STRONG>Only me, the meeting organizer</STRONG> because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time.</span></span> <span data-ttu-id="1dcfa-115">Сотрудник, отвечающий за проведение большого собрания, в этом случае должен постоянно проверять состав "зала ожидания" и допускать новых пользователей, находящихся в "зале ожидания".</span><span class="sxs-lookup"><span data-stu-id="1dcfa-115">The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>

        
        </div>

  - <span data-ttu-id="1dcfa-116">Разрешите пользователям, подключающимся с телефона, автоматический вход на собрание, установив флажок **Абоненты попадают напрямую**.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-116">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>

  - <span data-ttu-id="1dcfa-117">Явным образом приглашайте следующих пользователей:</span><span class="sxs-lookup"><span data-stu-id="1dcfa-117">Explicitly invite the following users:</span></span>
    
      - <span data-ttu-id="1dcfa-118">организатор собрания и делегат (инициатор запроса);</span><span class="sxs-lookup"><span data-stu-id="1dcfa-118">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="1dcfa-119">список выступающих, предоставленный инициатором запроса на собрание.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-119">The list of presenters provided by a meeting requester</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1dcfa-120">Если задан тип доступа к собранию <STRONG>Выбранные пользователи</STRONG>, потребуется в явном виде добавить каждого участника большого собрания как приглашенного на собрание.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-120">If the meeting access type is set to <STRONG>People I choose</STRONG>, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="1dcfa-p105">Явно управляйте докладчиками вместо определения параметра докладчика в качестве одного из значений автоматического продвижения. Убедитесь, что следующие пользователи добавлены в качестве докладчиков:</span><span class="sxs-lookup"><span data-stu-id="1dcfa-p105">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
      - <span data-ttu-id="1dcfa-123">организатор собрания и делегат (инициатор запроса);</span><span class="sxs-lookup"><span data-stu-id="1dcfa-123">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="1dcfa-124">список выступающих, предоставленный инициаторами запроса на большое собрание.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-124">The list of presenters provided by large meeting requesters</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1dcfa-125">Явно управляя выступающими, вы можете управлять количеством выступающих, чтобы ограничить выступающие небольшим числом, чтобы можно было использовать для них эффективное большое собрание.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-125">By explicitly managing presenters, you can control the number of presenters, so that you can limit presenters to a small enough number to make it possible to have an effective large meeting.</span></span> <span data-ttu-id="1dcfa-126">Если большинство на собрании составляют обычные участники, снижается вероятность случайной передачи управления презентацией, удаления презентации PowerPoint, включения или отключения микрофонов докладчиков и других нарушений нормального хода собрания.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-126">If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="1dcfa-127">Если установлен флажок **Отключить микрофоны всех участников**, транслировать звук на собрании могут только докладчики.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-127">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>

  - <span data-ttu-id="1dcfa-128">Если установлен флажок **Блокировать видео участников**, транслировать видеоизображение на собрании могут только докладчики.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-128">Check the **Block attendees’ video** setting to make sure only presenters can broadcast video into the meeting.</span></span>

<span data-ttu-id="1dcfa-129">На приведенном ниже рисунке показаны рекомендуемые параметры для надстройки "собрание по сети" для Lync.</span><span class="sxs-lookup"><span data-stu-id="1dcfa-129">The following figure shows the recommended settings for the Online Meeting Add-in for Lync.</span></span>

<span data-ttu-id="1dcfa-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span><span class="sxs-lookup"><span data-stu-id="1dcfa-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

