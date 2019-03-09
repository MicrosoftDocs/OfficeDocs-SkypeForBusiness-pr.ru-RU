---
title: Управление политиками собрания
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 03/01/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: Сведения для управления параметров политики в группах собрания.
ms.openlocfilehash: f8f7e4bbf18fa96ebc8de3fd219945a06c05c0b3
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494087"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="3be3e-103">Управление политиками собрания в группах</span><span class="sxs-lookup"><span data-stu-id="3be3e-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="3be3e-104">Политик собраний используются для управления функциональные возможности, доступные для участников собраний, запланированных пользователями в вашей организации собрания.</span><span class="sxs-lookup"><span data-stu-id="3be3e-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="3be3e-105">После создания политики и внесите изменения, затем можно назначить с помощью политики.</span><span class="sxs-lookup"><span data-stu-id="3be3e-105">After you create a policy and make your changes, you can then assign uses to the policy.</span></span> 

<span data-ttu-id="3be3e-106">По умолчанию создается политика, с именем Global (по умолчанию в масштабах организации).</span><span class="sxs-lookup"><span data-stu-id="3be3e-106">By default, a policy named Global (org-wide default) is created.</span></span> <span data-ttu-id="3be3e-107">Все пользователи в вашей организации будет назначен эта политика собрания по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3be3e-107">All users in your organization will be assigned this meeting policy by default.</span></span> <span data-ttu-id="3be3e-108">Можно внести изменения в этой политике или создание одного или нескольких настраиваемых политик и назначение пользователям.</span><span class="sxs-lookup"><span data-stu-id="3be3e-108">You can either make changes to this policy or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="3be3e-109">При создании пользовательскую политику, можно разрешить или запретить определенные функциональные возможности доступными для пользователей и назначьте его одному или нескольким пользователям, которые будут иметь параметров, примененных к ним.</span><span class="sxs-lookup"><span data-stu-id="3be3e-109">When you create a custom policy, you can allow or prevent certain features from being available to your users and then assign it to one or more users who will have the settings applied to them.</span></span> 

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="3be3e-110">Изменение или создание политики собрания</span><span class="sxs-lookup"><span data-stu-id="3be3e-110">Change or create a meeting policy</span></span>

<span data-ttu-id="3be3e-111">Чтобы изменить или создать политику собрания, перейдите в **Центр администрирования группами Майкрософт** > **собраний** > **политик собраний**.</span><span class="sxs-lookup"><span data-stu-id="3be3e-111">To change or create a meeting policy, go to **Microsoft Teams admin center** > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="3be3e-112">Выберите соответствующую политику в списке, или выберите **новую политику**.</span><span class="sxs-lookup"><span data-stu-id="3be3e-112">Select a policy from the list, or select **New policy**.</span></span> <span data-ttu-id="3be3e-113">Выберите параметры, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3be3e-113">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="3be3e-114">Допустим, у вас есть несколько пользователей и для ограничения пропускной способности, который требуется их собрания.</span><span class="sxs-lookup"><span data-stu-id="3be3e-114">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="3be3e-115">Вам нужно создать новый пользовательскую политику с именем «Ограниченной пропускной способностью» и отключить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="3be3e-115">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="3be3e-116">В разделе **& звук видео**:</span><span class="sxs-lookup"><span data-stu-id="3be3e-116">Under **Audio & video**:</span></span>
- <span data-ttu-id="3be3e-117">Отключить облачных записи</span><span class="sxs-lookup"><span data-stu-id="3be3e-117">Turn off cloud recording</span></span>
- <span data-ttu-id="3be3e-118">Отключить видео разрешенных IP-адресов</span><span class="sxs-lookup"><span data-stu-id="3be3e-118">Turn off Allow IP video</span></span>

<span data-ttu-id="3be3e-119">В разделе **общий доступ к содержимому**:</span><span class="sxs-lookup"><span data-stu-id="3be3e-119">Under **Content sharing**:</span></span>
- <span data-ttu-id="3be3e-120">Отключение режима совместного использования экрана</span><span class="sxs-lookup"><span data-stu-id="3be3e-120">Disable screen sharing mode</span></span>
- <span data-ttu-id="3be3e-121">Отключить доски</span><span class="sxs-lookup"><span data-stu-id="3be3e-121">Turn off whiteboard</span></span>
- <span data-ttu-id="3be3e-122">Отключить общие заметки</span><span class="sxs-lookup"><span data-stu-id="3be3e-122">Turn off shared notes</span></span>

<span data-ttu-id="3be3e-123">Назначьте политику для пользователей.</span><span class="sxs-lookup"><span data-stu-id="3be3e-123">Then assign the policy to the users.</span></span>

> [!NOTE] 
> <span data-ttu-id="3be3e-124">Пользователь может быть назначен только один собрания политики за раз.</span><span class="sxs-lookup"><span data-stu-id="3be3e-124">A user can be assigned only one meeting policy at a time.</span></span> 

## <a name="assign-a-meeting-policy-to-a-user"></a><span data-ttu-id="3be3e-125">Назначение собрания политику для пользователя</span><span class="sxs-lookup"><span data-stu-id="3be3e-125">Assign a meeting policy to a user</span></span>

<span data-ttu-id="3be3e-126">Назначение политики, перейдите в **Центр администрирования группами Майкрософт** > **пользователей**.</span><span class="sxs-lookup"><span data-stu-id="3be3e-126">To assign a policy, go to **Microsoft Teams admin center** > **Users**.</span></span> 
 
<span data-ttu-id="3be3e-127">В случае применения политики одному пользователю, выберите отображаемое имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="3be3e-127">If you are applying the policy to one user, select the user's display name.</span></span> <span data-ttu-id="3be3e-128">Рядом с пунктом **назначения политики**выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="3be3e-128">Next to **Assigned policies**, select **Edit**.</span></span> <span data-ttu-id="3be3e-129">В области **Изменение политик пользователей** в разделе **Политика собрания**, выберите политика собрания из раскрывающегося списка и выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3be3e-129">Then, in the **Edit user policies** pane, under **Meeting policy**, select the meeting policy from the drop-down list, and select **Save**.</span></span> <span data-ttu-id="3be3e-130">Кроме того, можно изменить параметры в списке пользователей.</span><span class="sxs-lookup"><span data-stu-id="3be3e-130">You can also edit settings from the list of users.</span></span> <span data-ttu-id="3be3e-131">Для этого выберите пользователя, нажав кнопку слева от отображаемое имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="3be3e-131">To do this, select the user by clicking to the left of the user's display name.</span></span> <span data-ttu-id="3be3e-132">Выберите **Изменить параметры**.</span><span class="sxs-lookup"><span data-stu-id="3be3e-132">Select **Edit settings**.</span></span> <span data-ttu-id="3be3e-133">Затем в области **Изменение параметров** в разделе **Политика собрания**, выберите параметр из раскрывающегося списка и выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3be3e-133">Then, on the **Edit settings** pane, under **Meeting policy**, select the policy from the drop-down list and then select **Save**.</span></span> 
 
<span data-ttu-id="3be3e-134">В случае применения политики более чем одному пользователю, выберите каждого из пользователей, щелкнув слева от имени пользователя и нажмите кнопку **Изменить параметры**.</span><span class="sxs-lookup"><span data-stu-id="3be3e-134">If you are applying a policy to more than one user, select each of the users by clicking to the left of the user name, and then click **Edit settings**.</span></span> <span data-ttu-id="3be3e-135">В области **Изменить параметры** в разделе **Политика собрания**выберите параметр из раскрывающегося списка и выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3be3e-135">On the **Edit Settings** pane, under **Meeting policy**, select the policy from the drop-down list and then select **Save**.</span></span>
 
<span data-ttu-id="3be3e-136">Это также можно сделать, перейдя на **Центр администрирования группами Майкрософт** > **собраний** >  **политик собраний**.</span><span class="sxs-lookup"><span data-stu-id="3be3e-136">You can also do this by going to **Microsoft Teams admin center** > **Meetings** >  **Meeting policies**.</span></span> <span data-ttu-id="3be3e-137">Выберите политику, а затем выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="3be3e-137">Select the policy and then select **Manage users**.</span></span> <span data-ttu-id="3be3e-138">В области **Управление пользователями** поиск пользователя по имени отображаемой области или пользователя.</span><span class="sxs-lookup"><span data-stu-id="3be3e-138">In the **Manage users** pane, search for the user by display or user name.</span></span> <span data-ttu-id="3be3e-139">Выберите имя, а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3be3e-139">Select the name and select **Add**.</span></span> <span data-ttu-id="3be3e-140">Завершив добавление пользователей, выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3be3e-140">When you are finished adding users, select **Save**.</span></span>

> [!NOTE] 
> <span data-ttu-id="3be3e-141">Не удается удалить политику, если пользователи назначаются.</span><span class="sxs-lookup"><span data-stu-id="3be3e-141">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="3be3e-142">Сначала необходимо назначить разные политики для всех заинтересованных пользователей и удалите исходное политики.</span><span class="sxs-lookup"><span data-stu-id="3be3e-142">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>
 
 
## <a name="user-policy-settings"></a><span data-ttu-id="3be3e-143">Параметры политики пользователя</span><span class="sxs-lookup"><span data-stu-id="3be3e-143">User policy settings</span></span>

<span data-ttu-id="3be3e-144">При выборе существующей политики на странице **политик собраний** или выберите **новую политику** для добавления новой политики можно настроить следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="3be3e-144">When you select an existing policy on the **Meeting policies** page or select **New policy** to add a new policy, you can configure the following settings.</span></span>

### <a name="new-meeting-policy-name-and-description"></a><span data-ttu-id="3be3e-145">Создание встречи, имя и описание политики</span><span class="sxs-lookup"><span data-stu-id="3be3e-145">New meeting policy name and description</span></span>
   - <span data-ttu-id="3be3e-146">**Имя** Это имя политики, которое будет отображаться на странице **политик собраний** .</span><span class="sxs-lookup"><span data-stu-id="3be3e-146">**Name** This is the name of the policy that will appear on the **Meeting policies** page.</span></span> <span data-ttu-id="3be3e-147">Не может содержать специальные символы или превышать 64 символов.</span><span class="sxs-lookup"><span data-stu-id="3be3e-147">It can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="3be3e-148">Обратите внимание на то, что не может изменить имя существующей политики.</span><span class="sxs-lookup"><span data-stu-id="3be3e-148">Note that you can't change an existing policy's name.</span></span>
   - <span data-ttu-id="3be3e-149">**Описание** Можно размещать в понятное описание для политики, которые можно создать.</span><span class="sxs-lookup"><span data-stu-id="3be3e-149">**Description** You can put in a friendly description for the policy you create.</span></span> <span data-ttu-id="3be3e-150">Будут полезны, если вы хотите назначить политику для группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="3be3e-150">This will be helpful if you want to assign a policy to a group of users.</span></span>
::: zone-end 

<span data-ttu-id="3be3e-151"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="3be3e-151"></span></span>
### <a name="general"></a><span data-ttu-id="3be3e-152">Общий</span><span class="sxs-lookup"><span data-stu-id="3be3e-152">General</span></span>
   - <span data-ttu-id="3be3e-153">**Разрешить теперь удовлетворение** Для включения это позволит функции провести собрание, чтобы оно было доступно для пользователей, у которых присоединение к собраниям.</span><span class="sxs-lookup"><span data-stu-id="3be3e-153">**Allow Meet Now** Turning this on will allow the Meet Now feature to be available to users that join meetings.</span></span>
   - <span data-ttu-id="3be3e-154">**Разрешить надстройки Outlook** Для включения это позволит пользователей, назначенных для политики имеют надстройки Outlook недоступны при планировании собрания.</span><span class="sxs-lookup"><span data-stu-id="3be3e-154">**Allow the Outlook add-in** Turning this on will let users assigned to the policy have the Outlook add-in available when they schedule meetings.</span></span>
   - <span data-ttu-id="3be3e-155">**Разрешить канала планирования собраний** Для включения это позволит планирования собраний канала.</span><span class="sxs-lookup"><span data-stu-id="3be3e-155">**Allow Channel meeting scheduling** Turning this on will allow Channel Meeting scheduling.</span></span>
   - <span data-ttu-id="3be3e-156">**Разрешить планирование частных собраний** Для включения это позволит пользователям, которые присоединиться к собранию для планирования собраний закрытый.</span><span class="sxs-lookup"><span data-stu-id="3be3e-156">**Allow scheduling private meetings** Turning this on will allow users that join a meeting to schedule private meetings.</span></span>

<span data-ttu-id="3be3e-157"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="3be3e-157"></span></span>

### <a name="audio--video"></a><span data-ttu-id="3be3e-158">Звуковое & видео</span><span class="sxs-lookup"><span data-stu-id="3be3e-158">Audio & video</span></span>
   - <span data-ttu-id="3be3e-159">**Разрешить транскрибирования** Если включить это, подписка на собрания будут доступны пользователям.</span><span class="sxs-lookup"><span data-stu-id="3be3e-159">**Allow transcription** If you turn this on, transcription of the meeting will be available to users.</span></span>
   - <span data-ttu-id="3be3e-160">**Облако разрешить запись** Для включения это позволит сохранять в облаке записи.</span><span class="sxs-lookup"><span data-stu-id="3be3e-160">**Allow cloud recording** Turning this on will allow recordings to be saved in the cloud.</span></span>
   - <span data-ttu-id="3be3e-161">**Разрешить IP-адрес видео** Для включения это позволит IP-адрес видео во время собрания.</span><span class="sxs-lookup"><span data-stu-id="3be3e-161">**Allow IP video** Turning this on will allow IP videos during meetings.</span></span>
   - <span data-ttu-id="3be3e-162">**Мультимедиа скорость потока (КБ)** Можно задать скорость потока для собраний.</span><span class="sxs-lookup"><span data-stu-id="3be3e-162">**Media bit rate (KBs)** You can set the bit rate for meetings.</span></span> <span data-ttu-id="3be3e-163">Значение по умолчанию — 50 МБ.</span><span class="sxs-lookup"><span data-stu-id="3be3e-163">The default is 50 MB.</span></span>

<span data-ttu-id="3be3e-164"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="3be3e-164"></span></span>

### <a name="content-sharing"></a><span data-ttu-id="3be3e-165">Общий доступ к содержимому</span><span class="sxs-lookup"><span data-stu-id="3be3e-165">Content sharing</span></span>
   - <span data-ttu-id="3be3e-166">**Режим совместное использование рабочего стола** Вы можете выбрать совместного использования режима экрана.</span><span class="sxs-lookup"><span data-stu-id="3be3e-166">**Screen sharing mode** You can select the screen sharing mode.</span></span> <span data-ttu-id="3be3e-167">Это будет размер экрана, который будет использоваться во время собрания, пользователь, которому назначен политику можно использовать.</span><span class="sxs-lookup"><span data-stu-id="3be3e-167">This will be the size of the screen that will be used during a meeting that a user assigned with the policy can use.</span></span>
   - <span data-ttu-id="3be3e-168">**Разрешить участника для предоставления или запросить управление** Это позволяет всех участников собрания и запросить управление совместное использование рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="3be3e-168">**Allow a participant to give or request control** This allows all participants in a meeting to give and request control of screen sharing.</span></span>
   - <span data-ttu-id="3be3e-169">**Разрешить внешних участников предоставить или запросить управление** Это позволяет external (кто-то не является частью вашего organziation) участника и запросить управление собрания при совместном экрана.</span><span class="sxs-lookup"><span data-stu-id="3be3e-169">**Allow an external participant to give or request control** This allows an external (someone not part of your organziation) participant to give and request control of a meeting when the screen is being shared.</span></span>
   - <span data-ttu-id="3be3e-170">**Общий доступ к возможным PowerPoint** При включении этого, пользователи, планировать собрания могут совместно использовать наборов слайдов PowerPoint слайд во время собрания.</span><span class="sxs-lookup"><span data-stu-id="3be3e-170">**Allow PowerPoint sharing** If you turn this on, users that schedule meetings can share PowerPoint slide decks during a meeting.</span></span>
   - <span data-ttu-id="3be3e-171">**Разрешить доски** Если отключить этот доске можно участникам собрания во время собрания.</span><span class="sxs-lookup"><span data-stu-id="3be3e-171">**Allow whiteboard** If you turn this on, the whiteboard will be available to meeting participants during a meeting.</span></span>
   - <span data-ttu-id="3be3e-172">**Разрешить общие заметки** Если отключить этот Общие заметки будут доступны участникам собрания во время собрания.</span><span class="sxs-lookup"><span data-stu-id="3be3e-172">**Allow shared notes** If you turn this on, shared notes will be available to meeting participants during a meeting.</span></span>

<span data-ttu-id="3be3e-173"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="3be3e-173"></span></span>

### <a name="participants--guests"></a><span data-ttu-id="3be3e-174">Гости & участников</span><span class="sxs-lookup"><span data-stu-id="3be3e-174">Participants & guests</span></span>
   - <span data-ttu-id="3be3e-175">**Разрешить анонимным пользователям начать собраний** Если этот параметр отключен, только тот, кто прошел проверку подлинности на собрание с помощью команды приложения можно начать собрание.</span><span class="sxs-lookup"><span data-stu-id="3be3e-175">**Allow anonymous users to start meetings** If this setting is off, then only someone who has been authenticated to the meeting with a Teams app can start the meeting.</span></span> <span data-ttu-id="3be3e-176">Если это всем пользователям можно начать собрание.</span><span class="sxs-lookup"><span data-stu-id="3be3e-176">If it's on, then anyone can start the meeting.</span></span>
   - <span data-ttu-id="3be3e-177">**Автоматически одобрять пользователей** Если отключить этот режим, затем участникам собрания остается в зале ожидания пока кто-то создает собрание.</span><span class="sxs-lookup"><span data-stu-id="3be3e-177">**Automatically admit users** If you turn this off, then meeting participants will be left in the lobby until someone starts the meeting.</span></span> <span data-ttu-id="3be3e-178">Если он установлен, участникам собрания могут присоединиться к собранию автоматически.</span><span class="sxs-lookup"><span data-stu-id="3be3e-178">If it's on, meeting participants will be allowed to join the meeting automatically.</span></span>

[<span data-ttu-id="3be3e-179">Полный текст статьи</span><span class="sxs-lookup"><span data-stu-id="3be3e-179">Full article</span></span>](meeting-policies-in-teams.md)

### <a name="related-topics"></a><span data-ttu-id="3be3e-180">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3be3e-180">Related topics</span></span>
[<span data-ttu-id="3be3e-181">Политик обмена сообщениями в группах</span><span class="sxs-lookup"><span data-stu-id="3be3e-181">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)