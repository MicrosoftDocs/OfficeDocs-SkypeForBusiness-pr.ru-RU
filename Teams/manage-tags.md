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
ms.openlocfilehash: cd2c2e69054923ccf287f35a15fcebb870d6a5d5
ms.sourcegitcommit: 545e466f1fa9163bb00cc96c8db70a70b02af697
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928452"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="ceaaa-103">Управление тегами в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ceaaa-103">Manage tags in Microsoft Teams</span></span>

<span data-ttu-id="ceaaa-104">Теги в Microsoft Teams позволяют пользователям общаться с подмножеством пользователей в команде.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-104">Tags in Microsoft Teams let users communicate with a subset of people on a team.</span></span> <span data-ttu-id="ceaaa-105">Теги можно добавлять в один или несколько участников группы для быстрого соединения с подмножеством пользователей.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-105">Tags can be added to one or multiple team members to easily connect with the right subset of people.</span></span> <span data-ttu-id="ceaaa-106">Владельцы и участники групп (если эта функция включена) может добавить к человеку одного или нескольких тегов.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-106">Team owners and members (if the feature is enabled for them) can add one or more tags to a person.</span></span> <span data-ttu-id="ceaaa-107">Затем Теги можно использовать в @mentions для всех участников группы в канале POST или для начала беседы только с теми людьми, которым назначен этот тег.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-107">The tags can then be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

> [!NOTE]
> <span data-ttu-id="ceaaa-108">В закрытых каналах Теги пока не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-108">Tags are not yet supported in private channels.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="ceaaa-109">Принцип работы тегов</span><span class="sxs-lookup"><span data-stu-id="ceaaa-109">How tags work</span></span>

<span data-ttu-id="ceaaa-110">Вы можете добавить тег для человека в определенной команде.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-110">A tag can be added to a person on a specific team.</span></span> <span data-ttu-id="ceaaa-111">После добавления тега его можно использовать в @mentions в чате или в любом стандартном канале команды.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-111">After a tag is added, it can be used in @mentions in a chat or in any standard channel of the team.</span></span> <span data-ttu-id="ceaaa-112">Вот несколько примеров использования тегов в teams:</span><span class="sxs-lookup"><span data-stu-id="ceaaa-112">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="ceaaa-113">Руководитель магазина хочет опубликовать извещение в канале и уведомит всех кассиров.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-113">A store manager wants to post an announcement to a channel and notify all cashiers.</span></span>
- <span data-ttu-id="ceaaa-114">Руководитель группы проектов хочет получать сообщения всех руководителей продуктов в канале.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-114">A group product manager wants to message all product managers in a channel.</span></span>
- <span data-ttu-id="ceaaa-115">Администратор больницы хочет отправить сообщение всем радиологистс в канале.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-115">A hospital administrator wants to send a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="ceaaa-116">Руководитель маркетинговой программы хочет начать групповой чат со всеми дизайнерами.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-116">A marketing manager wants to start a group chat with all designers.</span></span> 

<span data-ttu-id="ceaaa-117">Чтобы узнать больше, ознакомьтесь [с помощью тегов в Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span><span class="sxs-lookup"><span data-stu-id="ceaaa-117">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

## <a name="manage-tags-for-your-organization"></a><span data-ttu-id="ceaaa-118">Управление тегами в Организации</span><span class="sxs-lookup"><span data-stu-id="ceaaa-118">Manage tags for your organization</span></span>

<span data-ttu-id="ceaaa-119">Администраторы могут управлять тем, кто может добавлять теги, а также использовать теги в центре администрирования Microsoft Teams в рамках своей организации.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-119">As an admin, you can control who can add tags and how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Снимок экрана: параметры разметки в центре администрирования Microsoft Teams](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a><span data-ttu-id="ceaaa-121">Назначение пользователей, которые могут добавлять теги</span><span class="sxs-lookup"><span data-stu-id="ceaaa-121">Set who can add tags</span></span>

<span data-ttu-id="ceaaa-122">По умолчанию владельцы групп могут добавлять теги.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-122">By default, team owners can add tags.</span></span> <span data-ttu-id="ceaaa-123">Вы можете изменить этот параметр, чтобы разрешить владельцам групп и участникам группы добавлять теги, или вы можете отключить теги для своей организации.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-123">You can change this setting to allow team owners and team members to add tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="ceaaa-124">В левой области навигации центра администрирования Microsoft Teams щелкните**Параметры Teams**для **организационной настройки** > .</span><span class="sxs-lookup"><span data-stu-id="ceaaa-124">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="ceaaa-125">В разделе **Разметка**рядом с полем разметка **включена**выберите один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-125">Under **Tagging**, next to **Tagging is enabled for**, select one of the following options:</span></span>

    - <span data-ttu-id="ceaaa-126">**Владельцы и участники групп**: предоставление владельцам групп и участникам возможности добавлять теги.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-126">**Team owners and members**: Allow team owners and members to add tags.</span></span>
    - <span data-ttu-id="ceaaa-127">**Владельцы групп**: разрешение владельцам групп добавлять теги.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-127">**Team owners**: Allow team owners to add tags.</span></span>
    - <span data-ttu-id="ceaaa-128">**Disabled**(отключить Теги).</span><span class="sxs-lookup"><span data-stu-id="ceaaa-128">**Disabled**: Turn off tags.</span></span>

### <a name="configure-tags-settings"></a><span data-ttu-id="ceaaa-129">Настройка параметров тегов</span><span class="sxs-lookup"><span data-stu-id="ceaaa-129">Configure tags settings</span></span>

<span data-ttu-id="ceaaa-130">Вы можете настроить следующие параметры тегов, чтобы управлять использованием тегов в Организации.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-130">You can configure the following tags settings to control how tags are used across your organization.</span></span>

1. <span data-ttu-id="ceaaa-131">В левой области навигации центра администрирования Microsoft Teams щелкните**Параметры Teams**для **организационной настройки** > .</span><span class="sxs-lookup"><span data-stu-id="ceaaa-131">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="ceaaa-132">В разделе **Разметка**выберите следующие значения в зависимости от потребностей Организации.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-132">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="ceaaa-133">**Владелец группы может переопределить пользователей, которые могут применять теги**: Если эта функция включена, владельцы групп могут разрешать или запрещать участникам добавлять теги в параметрах группы.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-133">**Team owner can override who can apply tags**: When this is turned on, team owners can allow or disallow members to add tags in team settings.</span></span>
    - <span data-ttu-id="ceaaa-134">**Участники могут добавлять дополнительные теги**: Если вы разрешаете участникам группы добавлять теги, включите этот параметр, чтобы участники группы могли добавлять теги, отличные от предложенных тегов по умолчанию, которые вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-134">**Members can add additional tags**: If you allow team members to add tags, turn this on to let team members add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="ceaaa-135">Если этот параметр отключен, участники группы могут использовать только теги по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-135">If this is turned off, team members can only use the default tags.</span></span>
    - <span data-ttu-id="ceaaa-136">**Предлагаемые Теги по умолчанию**: Используйте этот параметр, чтобы добавить набор тегов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-136">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="ceaaa-137">Вы можете добавить до 25 тегов, и каждый тег может содержать не более 25 символов.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-137">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="ceaaa-138">Владельцы и участники групп (если эта функция включена) может использовать эти предложения, добавлять в них или создавать новые теги.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-138">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>

## <a name="manage-tags-settings-for-a-team"></a><span data-ttu-id="ceaaa-139">Управление параметрами тегов для команды</span><span class="sxs-lookup"><span data-stu-id="ceaaa-139">Manage tags settings for a team</span></span>

<span data-ttu-id="ceaaa-140">Если вы включили в качестве **владельца команды** параметр "Теги" в центре администрирования Microsoft Teams, владельцы групп могут указать, могут ли участники добавлять теги на уровне группы.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-140">If you turned on the **Team owner can override who can apply tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="ceaaa-141">Для этого на вкладке **Параметры** группы перейдите к разделу **теги**и выберите, кто может добавлять теги.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-141">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![Снимок экрана: Настройка тегов на уровне группы](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a><span data-ttu-id="ceaaa-143">Добавление тегов в Teams</span><span class="sxs-lookup"><span data-stu-id="ceaaa-143">Add tags in Teams</span></span>

<span data-ttu-id="ceaaa-144">В Teams вкладка " **члены** " на странице "Управление группой" для группы включает столбец " **теги** ".</span><span class="sxs-lookup"><span data-stu-id="ceaaa-144">In Teams, the **Members** tab of the Manage team page for a team includes a **Tags** column.</span></span> <span data-ttu-id="ceaaa-145">Владельцы и участники групп (если функция включена для них) можно нажать кнопку **Управление тегами** рядом с элементом, чтобы просмотреть список предлагаемых тегов для этого пользователя и добавить в список Теги.</span><span class="sxs-lookup"><span data-stu-id="ceaaa-145">Team owners and members (if the feature is enabled for them) can click **Manage tags** next to a member to see the list of suggested tags for that member and add tags to the list.</span></span>

![<span data-ttu-id="ceaaa-146">Снимок экрана: применение тегов в клиенте Teams</span><span class="sxs-lookup"><span data-stu-id="ceaaa-146">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png) 
