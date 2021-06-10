---
title: Управление политиками собраний
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- seo-marvel-apr2020
description: Узнайте, как управлять настройками политики собраний в Teams управлять функциями, доступными участникам собрания для собраний, запланированных пользователями.
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598762"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="723bb-103">Управление политиками собраний в Teams</span><span class="sxs-lookup"><span data-stu-id="723bb-103">Manage meeting policies in Teams</span></span>

<span data-ttu-id="723bb-104"><a name="bkautomatically-admit-people"> </a></span><span class="sxs-lookup"><span data-stu-id="723bb-104"><a name="bkautomatically-admit-people"> </a></span></span>

<span data-ttu-id="723bb-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span><span class="sxs-lookup"><span data-stu-id="723bb-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span></span>

<span data-ttu-id="723bb-106"><a name="bkallow-transcription"> </a></span><span class="sxs-lookup"><span data-stu-id="723bb-106"><a name="bkallow-transcription"> </a></span></span>

<span data-ttu-id="723bb-107">Политики собраний используются для управления функциями, которые доступны участникам собрания для собраний, запланированных пользователями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="723bb-107">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="723bb-108">Вы можете использовать глобальную (по умолчанию в пределах организации) политику, создаваемую автоматически, или создавать и назначать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="723bb-108">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="723bb-109">Управлять политиками собраний можно в Центре администрирования Microsoft Teams или с помощью [PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="723bb-109">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="723bb-110">Сведения об использовании ролей для управления разрешениями участников и выступающих собрания см. в статье [Роли в собрании Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span><span class="sxs-lookup"><span data-stu-id="723bb-110">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="723bb-111">Вы можете реализовать политики следующими способами, которые определяют возможности, доступные пользователям до, во время или после собраний.</span><span class="sxs-lookup"><span data-stu-id="723bb-111">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="723bb-112">Тип реализации</span><span class="sxs-lookup"><span data-stu-id="723bb-112">Implementation type</span></span>  |<span data-ttu-id="723bb-113">Описание</span><span class="sxs-lookup"><span data-stu-id="723bb-113">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="723bb-114">Для организатора</span><span class="sxs-lookup"><span data-stu-id="723bb-114">Per-organizer</span></span>    |<span data-ttu-id="723bb-115">Когда вы реализуете политику для организатора, она будет унаследована всеми участниками собрания.</span><span class="sxs-lookup"><span data-stu-id="723bb-115">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="723bb-116">Например,  автоматическое допуск пользователей — это политика "на каждого организатора", которая управляет тем, присоединяются ли пользователи к собранию напрямую или будут ждать в "ожидании" для собраний, запланированных пользователем, которому назначена политика.</span><span class="sxs-lookup"><span data-stu-id="723bb-116">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="723bb-117">Для пользователя</span><span class="sxs-lookup"><span data-stu-id="723bb-117">Per-user</span></span>    |<span data-ttu-id="723bb-118">Когда вы реализуете политику для пользователя, только она применяется для ограничения определенных возможностей организатора или участников собрания.</span><span class="sxs-lookup"><span data-stu-id="723bb-118">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="723bb-119">Пример: **Разрешить быстрые незапланированные собрания в каналах** — это политика для пользователя.</span><span class="sxs-lookup"><span data-stu-id="723bb-119">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="723bb-120">Для организатора и для пользователя</span><span class="sxs-lookup"><span data-stu-id="723bb-120">Per-organizer and per-user</span></span>     |<span data-ttu-id="723bb-121">Когда вы реализуете сочетание политик для организатора и для пользователя, определенные возможности участников собрания будут ограничены согласно их политикам, а также политике организатора.</span><span class="sxs-lookup"><span data-stu-id="723bb-121">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="723bb-122">Пример: **Разрешить запись в облаке** — это политика для организатора и для пользователя.</span><span class="sxs-lookup"><span data-stu-id="723bb-122">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="723bb-123">Включив этот параметр, организатор и участники собрания могут начинать и останавливать запись.</span><span class="sxs-lookup"><span data-stu-id="723bb-123">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="723bb-124">Вы можете изменить параметры глобальной политики или создать и назначить одну или несколько настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="723bb-124">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="723bb-125">Пользователям будет назначена глобальная политика, если вы не создали и не назначили настраиваемую политику.</span><span class="sxs-lookup"><span data-stu-id="723bb-125">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="723bb-126">Кнопка сведений о собрании будет доступна, если у пользователя есть лицензии на аудиоконференции или пользователю разрешено использовать аудиоконференции. В противном случае сведения о собрании будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="723bb-126">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="723bb-127">Создание настраиваемой политики собраний</span><span class="sxs-lookup"><span data-stu-id="723bb-127">Create a custom meeting policy</span></span>

1. <span data-ttu-id="723bb-128">В Центре администрирования Microsoft Teams в области навигации слева выберите **Собрания** > **Политики собраний**.</span><span class="sxs-lookup"><span data-stu-id="723bb-128">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="723bb-129">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="723bb-129">Click **Add**.</span></span>
3. <span data-ttu-id="723bb-130">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="723bb-130">Enter a name and description for the policy.</span></span> <span data-ttu-id="723bb-131">Имя не может содержать специальные символы. Длина имени не должна превышать 64 символа.</span><span class="sxs-lookup"><span data-stu-id="723bb-131">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="723bb-132">Выберите нужные параметры.</span><span class="sxs-lookup"><span data-stu-id="723bb-132">Choose the settings that you want.</span></span>
5. <span data-ttu-id="723bb-133">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="723bb-133">Click **Save**.</span></span>

<span data-ttu-id="723bb-134">Например, предположим, что нужно ограничить пропускную способность собрания, в котором будет участвовать множество пользователей.</span><span class="sxs-lookup"><span data-stu-id="723bb-134">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="723bb-135">Для этого следует создать новую настраиваемую политику с именем "Ограниченная пропускная способность" и отключить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="723bb-135">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="723bb-136">В разделе **Аудио и видео**:</span><span class="sxs-lookup"><span data-stu-id="723bb-136">Under **Audio & video**:</span></span>

- <span data-ttu-id="723bb-137">Отключите параметр "Разрешить запись в облаке".</span><span class="sxs-lookup"><span data-stu-id="723bb-137">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="723bb-138">Отключите параметр "Разрешить видео по IP".</span><span class="sxs-lookup"><span data-stu-id="723bb-138">Turn off Allow IP video.</span></span>

<span data-ttu-id="723bb-139">В разделе **Общий доступ к содержимому**:</span><span class="sxs-lookup"><span data-stu-id="723bb-139">Under **Content sharing**:</span></span>

- <span data-ttu-id="723bb-140">Отключите режим демонстрации экрана.</span><span class="sxs-lookup"><span data-stu-id="723bb-140">Disable screen sharing mode.</span></span>
- <span data-ttu-id="723bb-141">Отключите параметр "Разрешить доски".</span><span class="sxs-lookup"><span data-stu-id="723bb-141">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="723bb-142">Отключите параметр "Разрешить общие заметки".</span><span class="sxs-lookup"><span data-stu-id="723bb-142">Turn off Allow shared notes.</span></span>

<span data-ttu-id="723bb-143">Затем назначьте политику пользователям.</span><span class="sxs-lookup"><span data-stu-id="723bb-143">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="723bb-144">Изменение политики собраний</span><span class="sxs-lookup"><span data-stu-id="723bb-144">Edit a meeting policy</span></span>

<span data-ttu-id="723bb-145">Вы можете изменить глобальную политику и любые создаваемые настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="723bb-145">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="723bb-146">В Центре администрирования Microsoft Teams в области навигации слева выберите **Собрания** > **Политики собраний**.</span><span class="sxs-lookup"><span data-stu-id="723bb-146">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="723bb-147">Выберите политику, щелкнув слева от ее имени, а затем нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="723bb-147">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="723bb-148">Внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="723bb-148">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="723bb-149">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="723bb-149">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="723bb-150">Пользователю может быть назначена только одна политика собраний за раз.</span><span class="sxs-lookup"><span data-stu-id="723bb-150">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="723bb-151">Назначение пользователям политики собрания</span><span class="sxs-lookup"><span data-stu-id="723bb-151">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="723bb-152">Вы не можете удалить политику, если ей назначены пользователи.</span><span class="sxs-lookup"><span data-stu-id="723bb-152">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="723bb-153">Требуется сначала назначить другую политику для всех затронутых пользователей, и после этого можно удалить исходную политику.</span><span class="sxs-lookup"><span data-stu-id="723bb-153">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="723bb-154">Параметры политик собраний</span><span class="sxs-lookup"><span data-stu-id="723bb-154">Meeting policy settings</span></span>

<span data-ttu-id="723bb-155">Выбрав существующую политику на  странице Политики собраний или настроив добавить новую политику, вы можете настроить следующие параметры: </span><span class="sxs-lookup"><span data-stu-id="723bb-155">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="723bb-156">Общее</span><span class="sxs-lookup"><span data-stu-id="723bb-156">General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="723bb-157">Аудио и видео</span><span class="sxs-lookup"><span data-stu-id="723bb-157">Audio & video</span></span>](meeting-policies-audio-and-video.md)
- [<span data-ttu-id="723bb-158">Отправка контента</span><span class="sxs-lookup"><span data-stu-id="723bb-158">Content sharing</span></span>](meeting-policies-content-sharing.md)
- [<span data-ttu-id="723bb-159">Участники и гости</span><span class="sxs-lookup"><span data-stu-id="723bb-159">Participants & guests</span></span>](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a><span data-ttu-id="723bb-160">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="723bb-160">Related topics</span></span>

- [<span data-ttu-id="723bb-161">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="723bb-161">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="723bb-162">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="723bb-162">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="723bb-163">Удаление политики собраний Teams RestrictedAnonymousAccess для пользователей</span><span class="sxs-lookup"><span data-stu-id="723bb-163">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)