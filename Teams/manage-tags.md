---
title: Управление тегами в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Научитесь управлять использованием тегов в Организации в Microsoft Teams.
ms.openlocfilehash: 3ade2f47474fe8aaf16c568e8c141dcd84526d86
ms.sourcegitcommit: 561b9bab7d6f5a621436bc85ea28ea14657e7868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034524"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="e7d57-103">Управление тегами в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e7d57-103">Manage tags in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="e7d57-104">Вы еще не видите эту функцию в центре администрирования Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="e7d57-104">Don't see this feature in the Microsoft Teams admin center yet?</span></span> <span data-ttu-id="e7d57-105">Ее развертывание идет постепенно, и в вашей организации она, возможно, пока недоступна.</span><span class="sxs-lookup"><span data-stu-id="e7d57-105">It's currently being rolled out and might not be available in your organization yet.</span></span> <span data-ttu-id="e7d57-106">Чтобы всегда оставаться на связи с возможностями предстоящих групп, ознакомьтесь с [планом Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span><span class="sxs-lookup"><span data-stu-id="e7d57-106">To stay on top of upcoming Teams features, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span></span>

<span data-ttu-id="e7d57-107">Теги в Microsoft Teams позволяют пользователям общаться с подмножеством пользователей в команде.</span><span class="sxs-lookup"><span data-stu-id="e7d57-107">Tags in Microsoft Teams let users communicate with a subset of people on a team.</span></span> <span data-ttu-id="e7d57-108">Теги можно добавлять в один или несколько участников группы для быстрого соединения с подмножеством пользователей.</span><span class="sxs-lookup"><span data-stu-id="e7d57-108">Tags can be added to one or multiple team members to easily connect with the right subset of people.</span></span> <span data-ttu-id="e7d57-109">Владельцы и участники групп (если эта функция включена) может добавить к человеку одного или нескольких тегов.</span><span class="sxs-lookup"><span data-stu-id="e7d57-109">Team owners and members (if the feature is enabled for them) can add one or more tags to a person.</span></span> <span data-ttu-id="e7d57-110">Затем Теги можно использовать в @mentions в разделе "Отправка канала", чтобы общаться только с теми людьми, которым назначен этот тег.</span><span class="sxs-lookup"><span data-stu-id="e7d57-110">The tags can then be used in @mentions by anyone on the team in a channel post to communicate with only those people who are assigned that tag.</span></span>

> [!NOTE]
> <span data-ttu-id="e7d57-111">В закрытых каналах Теги пока не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="e7d57-111">Tags are not yet supported in private channels.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="e7d57-112">Принцип работы тегов</span><span class="sxs-lookup"><span data-stu-id="e7d57-112">How tags work</span></span>

<span data-ttu-id="e7d57-113">Вы можете добавить тег для человека в определенной команде.</span><span class="sxs-lookup"><span data-stu-id="e7d57-113">A tag can be added to a person on a specific team.</span></span> <span data-ttu-id="e7d57-114">После добавления тега его можно использовать в @mentions в любом стандартном канале команды.</span><span class="sxs-lookup"><span data-stu-id="e7d57-114">After a tag is added, it can be used in @mentions in any standard channel of the team.</span></span> <span data-ttu-id="e7d57-115">Вот несколько примеров использования тегов в teams:</span><span class="sxs-lookup"><span data-stu-id="e7d57-115">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="e7d57-116">Руководитель магазина хочет опубликовать извещение в канале и уведомит всех кассиров.</span><span class="sxs-lookup"><span data-stu-id="e7d57-116">A store manager wants to post an announcement to a channel and notify all cashiers.</span></span>
- <span data-ttu-id="e7d57-117">Руководитель группы проектов хочет получать сообщения всех руководителей продуктов в канале.</span><span class="sxs-lookup"><span data-stu-id="e7d57-117">A group product manager wants to message all product managers in a channel.</span></span>
- <span data-ttu-id="e7d57-118">Администратор больницы хочет отправить сообщение всем радиологистс в канале.</span><span class="sxs-lookup"><span data-stu-id="e7d57-118">A hospital administrator wants to send a message to all radiologists in a channel.</span></span>

<span data-ttu-id="e7d57-119">Чтобы узнать больше, ознакомьтесь [с помощью тегов в Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span><span class="sxs-lookup"><span data-stu-id="e7d57-119">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

## <a name="manage-tags-for-your-organization"></a><span data-ttu-id="e7d57-120">Управление тегами в Организации</span><span class="sxs-lookup"><span data-stu-id="e7d57-120">Manage tags for your organization</span></span>

<span data-ttu-id="e7d57-121">Администраторы могут управлять тем, кто может добавлять теги, а также использовать теги в центре администрирования Microsoft Teams в рамках своей организации.</span><span class="sxs-lookup"><span data-stu-id="e7d57-121">As an admin, you can control who can add tags and how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Снимок экрана: параметры разметки в центре администрирования Microsoft Teams](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a><span data-ttu-id="e7d57-123">Назначение пользователей, которые могут добавлять теги</span><span class="sxs-lookup"><span data-stu-id="e7d57-123">Set who can add tags</span></span>

<span data-ttu-id="e7d57-124">По умолчанию владельцы групп могут добавлять теги.</span><span class="sxs-lookup"><span data-stu-id="e7d57-124">By default, team owners can add tags.</span></span> <span data-ttu-id="e7d57-125">Вы можете изменить этот параметр, чтобы разрешить владельцам групп и участникам группы добавлять теги, или вы можете отключить теги для своей организации.</span><span class="sxs-lookup"><span data-stu-id="e7d57-125">You can change this setting to allow team owners and team members to add tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="e7d57-126">В левой области навигации центра администрирования Microsoft Teams щелкните**Параметры Teams**для **организационной настройки** > .</span><span class="sxs-lookup"><span data-stu-id="e7d57-126">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="e7d57-127">В разделе **Разметка**рядом с полем разметка **включена**выберите один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="e7d57-127">Under **Tagging**, next to **Tagging is enabled for**, select one of the following options:</span></span>

    - <span data-ttu-id="e7d57-128">**Владельцы и участники групп**: предоставление владельцам групп и участникам возможности добавлять теги.</span><span class="sxs-lookup"><span data-stu-id="e7d57-128">**Team owners and members**: Allow team owners and members to add tags.</span></span>
    - <span data-ttu-id="e7d57-129">**Владельцы групп**: разрешение владельцам групп добавлять теги.</span><span class="sxs-lookup"><span data-stu-id="e7d57-129">**Team owners**: Allow team owners to add tags.</span></span>
    - <span data-ttu-id="e7d57-130">**Disabled**(отключить Теги).</span><span class="sxs-lookup"><span data-stu-id="e7d57-130">**Disabled**: Turn off tags.</span></span>

### <a name="configure-tags-settings"></a><span data-ttu-id="e7d57-131">Настройка параметров тегов</span><span class="sxs-lookup"><span data-stu-id="e7d57-131">Configure tags settings</span></span>

<span data-ttu-id="e7d57-132">Вы можете настроить следующие параметры тегов, чтобы управлять использованием тегов в Организации.</span><span class="sxs-lookup"><span data-stu-id="e7d57-132">You can configure the following tags settings to control how tags are used across your organization.</span></span>

1. <span data-ttu-id="e7d57-133">В левой области навигации центра администрирования Microsoft Teams щелкните**Параметры Teams**для **организационной настройки** > .</span><span class="sxs-lookup"><span data-stu-id="e7d57-133">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="e7d57-134">В разделе **Разметка**выберите следующие значения в зависимости от потребностей Организации.</span><span class="sxs-lookup"><span data-stu-id="e7d57-134">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="e7d57-135">**Владелец группы может переопределить пользователей, которые могут применять теги**: Если эта функция включена, владельцы групп могут разрешать или запрещать участникам добавлять теги в параметрах группы.</span><span class="sxs-lookup"><span data-stu-id="e7d57-135">**Team owner can override who can apply tags**: When this is turned on, team owners can allow or disallow members to add tags in team settings.</span></span>
    - <span data-ttu-id="e7d57-136">**Участники могут добавлять дополнительные теги**: Если вы разрешаете участникам группы добавлять теги, включите этот параметр, чтобы участники группы могли добавлять теги, отличные от предложенных тегов по умолчанию, которые вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="e7d57-136">**Members can add additional tags**: If you allow team members to add tags, turn this on to let team members add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="e7d57-137">Если этот параметр отключен, участники группы могут использовать только теги по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e7d57-137">If this is turned off, team members can only use the default tags.</span></span>
    - <span data-ttu-id="e7d57-138">**Предлагаемые Теги по умолчанию**: Используйте этот параметр, чтобы добавить набор тегов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e7d57-138">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="e7d57-139">Вы можете добавить до 25 тегов, и каждый тег может содержать не более 25 символов.</span><span class="sxs-lookup"><span data-stu-id="e7d57-139">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="e7d57-140">Владельцы и участники групп (если эта функция включена) может использовать эти предложения, добавлять в них или создавать новые теги.</span><span class="sxs-lookup"><span data-stu-id="e7d57-140">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>

## <a name="manage-tags-settings-for-a-team"></a><span data-ttu-id="e7d57-141">Управление параметрами тегов для команды</span><span class="sxs-lookup"><span data-stu-id="e7d57-141">Manage tags settings for a team</span></span>

<span data-ttu-id="e7d57-142">Если вы включили в качестве **владельца команды** параметр "Теги" в центре администрирования Microsoft Teams, владельцы групп могут указать, могут ли участники добавлять теги на уровне группы.</span><span class="sxs-lookup"><span data-stu-id="e7d57-142">If you turned on the **Team owner can override who can apply tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="e7d57-143">Для этого на вкладке **Параметры** группы перейдите к разделу **теги**и выберите, кто может добавлять теги.</span><span class="sxs-lookup"><span data-stu-id="e7d57-143">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![Снимок экрана: Настройка тегов на уровне группы](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a><span data-ttu-id="e7d57-145">Добавление тегов в Teams</span><span class="sxs-lookup"><span data-stu-id="e7d57-145">Add tags in Teams</span></span>

<span data-ttu-id="e7d57-146">В Teams вкладка " **члены** " на странице "Управление группой" для группы включает столбец " **теги** ".</span><span class="sxs-lookup"><span data-stu-id="e7d57-146">In Teams, the **Members** tab of the Manage team page for a team includes a **Tags** column.</span></span> <span data-ttu-id="e7d57-147">Владельцы и участники групп (если функция включена для них) можно нажать кнопку **Управление тегами** рядом с элементом, чтобы просмотреть список предлагаемых тегов для этого пользователя и добавить в список Теги.</span><span class="sxs-lookup"><span data-stu-id="e7d57-147">Team owners and members (if the feature is enabled for them) can click **Manage tags** next to a member to see the list of suggested tags for that member and add tags to the list.</span></span>

![<span data-ttu-id="e7d57-148">Снимок экрана: применение тегов в клиенте Teams</span><span class="sxs-lookup"><span data-stu-id="e7d57-148">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png) 
