---
title: Добавление ботов для приватных чатов и каналов в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lucarras
description: Сведения о добавлении ботов для приватного чата и каналов в Microsoft Teams, создании пользовательских ботов и загрузке собственного неопубликованного бота для приватного чата.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50abaf5e6fb15451bfa1695ab2a16e0ce1747232
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="b6ca9-103">Добавление ботов для приватных чатов и каналов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b6ca9-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="b6ca9-104">Боты — это автоматические программы, которые отвечают на запросы или предоставляют интересующие пользователя уведомления и данные.</span><span class="sxs-lookup"><span data-stu-id="b6ca9-104">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="b6ca9-105">Они позволяют пользователю взаимодействовать с облачными службами, предназначенными, например, для управления задачами, планирования и опросов, через беседы чата в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b6ca9-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="b6ca9-106">Боты для Microsoft Teams создаются на платформе [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span><span class="sxs-lookup"><span data-stu-id="b6ca9-106">Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span></span> <span data-ttu-id="b6ca9-107">Поэтому для Microsoft Teams можно легко адаптировать любые боты, разработанные на этой платформе.</span><span class="sxs-lookup"><span data-stu-id="b6ca9-107">The bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span> <span data-ttu-id="b6ca9-108">Для получения дополнительных сведений см [Управление группами Майкрософт в организации Office 365](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="b6ca9-108">For more information, see [Manage Microsoft Teams features in your Office 365 organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="b6ca9-109">Сейчас Microsoft Teams поддерживает боты в приватных чатах и каналах внутри команды.</span><span class="sxs-lookup"><span data-stu-id="b6ca9-109">Currently, Microsoft Teams support bots in private chats and channels within a team.</span></span> <span data-ttu-id="b6ca9-110">Администраторы могут разрешить или запретить боты в клиенте Office 365.<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="b6ca9-110">Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="b6ca9-111">Microsoft Teams позволяет использовать боты, разработанные сообществом.</span><span class="sxs-lookup"><span data-stu-id="b6ca9-111">Bots developed by the community can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="b6ca9-112">Для работы пользовательских ботов требуется включить боты и их загрузку на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="b6ca9-112">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="b6ca9-113">Боты можно использовать в приватных чатах или каналах.</span><span class="sxs-lookup"><span data-stu-id="b6ca9-113">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="b6ca9-114">В последних боты могут добавлять участники или владельцы команды.</span><span class="sxs-lookup"><span data-stu-id="b6ca9-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="b6ca9-115">Дополнительные сведения см. в статье Using Bots (Использование ботов) раздела [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) (приложения и службы).</span><span class="sxs-lookup"><span data-stu-id="b6ca9-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 




<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="b6ca9-116">Создание пользовательских ботов для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b6ca9-116">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="b6ca9-117">С помощью Microsoft Bot Framework вы можете легко создать бот, интегрирующийся с вашими бизнес-приложениями.</span><span class="sxs-lookup"><span data-stu-id="b6ca9-117">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework.</span></span> <span data-ttu-id="b6ca9-118">Сведения о разработке и публикации своих ботов см. в руководстве [Создание и тестирование бота для Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371).</span><span class="sxs-lookup"><span data-stu-id="b6ca9-118">Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="b6ca9-119">Создавая и регистрируя бот в Bot Framework, вы также можете опубликовать его.</span><span class="sxs-lookup"><span data-stu-id="b6ca9-119">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="b6ca9-120">Без публикации бот остается частным.</span><span class="sxs-lookup"><span data-stu-id="b6ca9-120">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="b6ca9-121">Вы также можете потребовать, чтобы перед работой с ботом пользователи входили в систему.</span><span class="sxs-lookup"><span data-stu-id="b6ca9-121">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="b6ca9-122">Такой обязательный вход позволяет предоставить доступ к боту только сотрудникам вашей организации, даже если станет известен его идентификатор приложения.</span><span class="sxs-lookup"><span data-stu-id="b6ca9-122">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="b6ca9-123">В описании [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) на сайте GitHub приведен пример кода для проверки подлинности пользователей в Active Directory с помощью ботов.</span><span class="sxs-lookup"><span data-stu-id="b6ca9-123">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="b6ca9-124">Перед развертыванием в Teams боты можно тестировать с помощью [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373).</span><span class="sxs-lookup"><span data-stu-id="b6ca9-124">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="b6ca9-125">Загрузка собственного неопубликованного бота для приватного чата</span><span class="sxs-lookup"><span data-stu-id="b6ca9-125">Side load your own bot for private chat</span></span>
---------------------------------------

1.  <span data-ttu-id="b6ca9-126">Создав свой бот, зайдите на страницу **Bot Dashboard** — [информационную панель](https://go.microsoft.com/fwlink/?linkid=854374) разработанного вами бота, а затем в разделе **Details** (Сведения) скопируйте **Microsoft App ID** (Идентификатор приложения Майкрософт).![Снимок экрана страницы сведений с выделенным идентификатором приложения Майкрософт.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="b6ca9-126">After you have created your bot, go to the **Bot Dashboard** [page](https://go.microsoft.com/fwlink/?linkid=854374) for the bot you developed, and then under **Details**, copy the **Microsoft App ID**.![Screenshot of details page for a bot with the Microsoft App ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span> 



2.  <span data-ttu-id="b6ca9-127">В области **Чат** Microsoft Teams выберите **значок добавления чата**.</span><span class="sxs-lookup"><span data-stu-id="b6ca9-127">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="b6ca9-128">В поле **Кому** вставьте **идентификатор приложения Майкрософт** своего бота.</span><span class="sxs-lookup"><span data-stu-id="b6ca9-128">For **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="b6ca9-129">![Снимок экрана с областью чата, где находится значок добавления чата и строка "Кому", а также выделен идентификатор приложения Майкрософт.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="b6ca9-129">![Screenshot of a chat pane with the icon for Add chat and the To line with the Microsoft app ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="b6ca9-130">Идентификатор разрешается в **имя бота**, после чего вы можете запустить беседу с этим ботом.</span><span class="sxs-lookup"><span data-stu-id="b6ca9-130">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>
