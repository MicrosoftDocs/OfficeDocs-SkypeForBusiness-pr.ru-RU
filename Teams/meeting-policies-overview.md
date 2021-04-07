---
title: Управление политиками собрания
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
description: Узнайте, как управлять настройками политики собраний в Teams и использовать их для управления функциями, доступными участникам собрания для собраний, запланированных пользователями.
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598762"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="f30ea-103">Управление политиками собраний в Teams</span><span class="sxs-lookup"><span data-stu-id="f30ea-103">Manage meeting policies in Teams</span></span>

<span data-ttu-id="f30ea-104"><a name="bkautomatically-admit-people"> </a></span><span class="sxs-lookup"><span data-stu-id="f30ea-104"><a name="bkautomatically-admit-people"> </a></span></span>

<span data-ttu-id="f30ea-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span><span class="sxs-lookup"><span data-stu-id="f30ea-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span></span>

<span data-ttu-id="f30ea-106"><a name="bkallow-transcription"> </a></span><span class="sxs-lookup"><span data-stu-id="f30ea-106"><a name="bkallow-transcription"> </a></span></span>

<span data-ttu-id="f30ea-107">Политики собраний используются для управления функциями, которые доступны участникам собрания для собраний, запланированных пользователями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f30ea-107">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="f30ea-108">Вы можете использовать глобальную (по умолчанию в организации) политику, которая автоматически создает или создает и назначает настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="f30ea-108">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="f30ea-109">Вы управляете политиками собраний в Центре администрирования Microsoft Teams или с помощью [PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f30ea-109">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f30ea-110">Сведения об использовании ролей для управления разрешениями участников и участников собрания см. в сведениях об использовании ролей [в собрании Teams.](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)</span><span class="sxs-lookup"><span data-stu-id="f30ea-110">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="f30ea-111">Вы можете реализовать политики следующими способами, которые влияют на работу пользователей до начала, во время собрания или после собрания.</span><span class="sxs-lookup"><span data-stu-id="f30ea-111">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="f30ea-112">Тип реализации</span><span class="sxs-lookup"><span data-stu-id="f30ea-112">Implementation type</span></span>  |<span data-ttu-id="f30ea-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f30ea-113">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="f30ea-114">Один организатор</span><span class="sxs-lookup"><span data-stu-id="f30ea-114">Per-organizer</span></span>    |<span data-ttu-id="f30ea-115">При реализации политики "на организатор" все участники собрания наследуют политику организатора.</span><span class="sxs-lookup"><span data-stu-id="f30ea-115">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="f30ea-116">Например,  автоматическое допуск пользователей — это политика "на организатор" и управление тем, будут ли пользователи присоединяться к собранию напрямую или ждать в "ожидании" для собраний, запланированных пользователем, которому назначена политика.</span><span class="sxs-lookup"><span data-stu-id="f30ea-116">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="f30ea-117">На пользователя</span><span class="sxs-lookup"><span data-stu-id="f30ea-117">Per-user</span></span>    |<span data-ttu-id="f30ea-118">При реализации политики "на пользователя" применяется только политика "на пользователя", которая ограничивает определенные функции организатора и (или) участников собрания.</span><span class="sxs-lookup"><span data-stu-id="f30ea-118">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="f30ea-119">Например, **политика "Разрешить сейчас"** в каналах является политикой "на пользователя".</span><span class="sxs-lookup"><span data-stu-id="f30ea-119">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="f30ea-120">По организатору и по пользователю</span><span class="sxs-lookup"><span data-stu-id="f30ea-120">Per-organizer and per-user</span></span>     |<span data-ttu-id="f30ea-121">При реализации сочетания политики "на пользователя" и "на пользователя" участники собрания могут ограничить некоторые возможности в зависимости от их политики и политики организатора.</span><span class="sxs-lookup"><span data-stu-id="f30ea-121">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="f30ea-122">Например, **"Разрешить запись в облаке"** — это политика "на пользователя" и "на пользователя".</span><span class="sxs-lookup"><span data-stu-id="f30ea-122">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="f30ea-123">Включив этот параметр, организатор и участники собрания могут начинать и останавливать запись.</span><span class="sxs-lookup"><span data-stu-id="f30ea-123">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="f30ea-124">Вы можете изменить параметры глобальной политики, а также создать и назначить одну или несколько настраиваемой политики.</span><span class="sxs-lookup"><span data-stu-id="f30ea-124">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="f30ea-125">Пользователи получат глобальную политику, если вы не создайте и не назначите ее.</span><span class="sxs-lookup"><span data-stu-id="f30ea-125">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="f30ea-126">Кнопка "Сведения о собрании" будет доступна, если у пользователя включены лицензии на аудиоконференции или пользователь разрешил аудиоконференцию, если он не имеет права на аудиоконференцию, сведения о собрании будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="f30ea-126">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="f30ea-127">Создание настраиваемой политики собраний</span><span class="sxs-lookup"><span data-stu-id="f30ea-127">Create a custom meeting policy</span></span>

1. <span data-ttu-id="f30ea-128">В левой области навигации Центра администрирования Microsoft Teams перейдите **к** политикам  >  **собраний собраний собраний.**</span><span class="sxs-lookup"><span data-stu-id="f30ea-128">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="f30ea-129">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f30ea-129">Click **Add**.</span></span>
3. <span data-ttu-id="f30ea-130">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="f30ea-130">Enter a name and description for the policy.</span></span> <span data-ttu-id="f30ea-131">Имя не может содержать специальные символы. Длина имени не должна превышать 64 символа.</span><span class="sxs-lookup"><span data-stu-id="f30ea-131">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="f30ea-132">Выберите нужные параметры.</span><span class="sxs-lookup"><span data-stu-id="f30ea-132">Choose the settings that you want.</span></span>
5. <span data-ttu-id="f30ea-133">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f30ea-133">Click **Save**.</span></span>

<span data-ttu-id="f30ea-134">Например, предположим, что нужно ограничить пропускную способность собрания, в котором будет участвовать множество пользователей.</span><span class="sxs-lookup"><span data-stu-id="f30ea-134">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="f30ea-135">Для этого следует создать новую настраиваемую политику с именем "Ограниченная пропускная способность" и отключить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f30ea-135">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="f30ea-136">В разделе **Аудио и видео**:</span><span class="sxs-lookup"><span data-stu-id="f30ea-136">Under **Audio & video**:</span></span>

- <span data-ttu-id="f30ea-137">Отключите параметр "Разрешить запись в облаке".</span><span class="sxs-lookup"><span data-stu-id="f30ea-137">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="f30ea-138">Отключите параметр "Разрешить видео по IP".</span><span class="sxs-lookup"><span data-stu-id="f30ea-138">Turn off Allow IP video.</span></span>

<span data-ttu-id="f30ea-139">В разделе **Общий доступ к содержимому**:</span><span class="sxs-lookup"><span data-stu-id="f30ea-139">Under **Content sharing**:</span></span>

- <span data-ttu-id="f30ea-140">Отключите режим демонстрации экрана.</span><span class="sxs-lookup"><span data-stu-id="f30ea-140">Disable screen sharing mode.</span></span>
- <span data-ttu-id="f30ea-141">Отключите параметр "Разрешить доски".</span><span class="sxs-lookup"><span data-stu-id="f30ea-141">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="f30ea-142">Отключите параметр "Разрешить общие заметки".</span><span class="sxs-lookup"><span data-stu-id="f30ea-142">Turn off Allow shared notes.</span></span>

<span data-ttu-id="f30ea-143">Затем назначьте политику пользователям.</span><span class="sxs-lookup"><span data-stu-id="f30ea-143">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="f30ea-144">Изменение политики собрания</span><span class="sxs-lookup"><span data-stu-id="f30ea-144">Edit a meeting policy</span></span>

<span data-ttu-id="f30ea-145">Вы можете изменить глобальную политику и любые настраиваемые политики, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="f30ea-145">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="f30ea-146">В левой области навигации Центра администрирования Microsoft Teams перейдите **к** политикам собраний  >  **собраний.**</span><span class="sxs-lookup"><span data-stu-id="f30ea-146">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="f30ea-147">Выберите политику, щелкнув слева от ее имени, а затем нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="f30ea-147">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="f30ea-148">Внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="f30ea-148">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="f30ea-149">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f30ea-149">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="f30ea-150">Одновременно пользователю может быть назначена только одна политика собрания.</span><span class="sxs-lookup"><span data-stu-id="f30ea-150">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="f30ea-151">Назначение пользователям политики собрания</span><span class="sxs-lookup"><span data-stu-id="f30ea-151">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="f30ea-152">Политику, назначенную пользователям, удалить нельзя.</span><span class="sxs-lookup"><span data-stu-id="f30ea-152">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="f30ea-153">Сначала необходимо назначить другую политику всем затронутым пользователям, а затем удалить исходную политику.</span><span class="sxs-lookup"><span data-stu-id="f30ea-153">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="f30ea-154">Параметры политики собраний</span><span class="sxs-lookup"><span data-stu-id="f30ea-154">Meeting policy settings</span></span>

<span data-ttu-id="f30ea-155">При выборе существующей политики  на странице "Политики собраний" или выборе "Добавить" для добавления новой политики можно настроить следующие параметры: </span><span class="sxs-lookup"><span data-stu-id="f30ea-155">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="f30ea-156">Общие</span><span class="sxs-lookup"><span data-stu-id="f30ea-156">General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="f30ea-157">Аудиофайл & видео</span><span class="sxs-lookup"><span data-stu-id="f30ea-157">Audio & video</span></span>](meeting-policies-audio-and-video.md)
- [<span data-ttu-id="f30ea-158">Общий доступ к содержимому</span><span class="sxs-lookup"><span data-stu-id="f30ea-158">Content sharing</span></span>](meeting-policies-content-sharing.md)
- [<span data-ttu-id="f30ea-159">Участники & гостей</span><span class="sxs-lookup"><span data-stu-id="f30ea-159">Participants & guests</span></span>](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a><span data-ttu-id="f30ea-160">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f30ea-160">Related topics</span></span>

- [<span data-ttu-id="f30ea-161">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="f30ea-161">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="f30ea-162">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="f30ea-162">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="f30ea-163">Удаление политики собраний RestrictedAnonymousAccess Teams для пользователей</span><span class="sxs-lookup"><span data-stu-id="f30ea-163">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)