---
title: "Добавление ботов для приватных чатов и каналов в Microsoft Teams | Служба поддержки Майкрософт"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения о добавлении ботов для приватного чата и каналов в Microsoft Teams, создании пользовательских ботов и загрузке собственного неопубликованного бота для приватного чата."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 905a105fba269aebb2b01cbccc1a47e7667ca341
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2017
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="23316-103">Добавление ботов для приватных чатов и каналов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="23316-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="23316-104">Боты — это автоматические программы, настроенные для ответа на запросы или предоставления нужных пользователю данных.</span><span class="sxs-lookup"><span data-stu-id="23316-104">Bots are automated programs that are set up to respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="23316-105">Они позволяют пользователю взаимодействовать с облачными службами, предназначенными, например, для управления задачами, планирования и опросов, через беседы чата в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="23316-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="23316-106">Боты для Microsoft Teams основаны на [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370), поэтому боты, разработанные с помощью этой платформы, легко адаптировать для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="23316-106">Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) and the bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span>

<span data-ttu-id="23316-107">Сейчас Microsoft Teams поддерживает боты в приватных чатах и каналах внутри команды.</span><span class="sxs-lookup"><span data-stu-id="23316-107">Currently, Microsoft Teams support bots in private chats and channels within a team.</span></span> <span data-ttu-id="23316-108">Администраторы могут разрешить или запретить боты в клиенте Office 365.<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="23316-108">Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="23316-109">В Microsoft Teams можно использовать боты, разработанные сообществом.</span><span class="sxs-lookup"><span data-stu-id="23316-109">Bots developed by the community and are made available, can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="23316-110">Для работы пользовательских ботов требуется включить боты и их загрузку на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="23316-110">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="23316-111">Боты можно использовать в приватных чатах или каналах.</span><span class="sxs-lookup"><span data-stu-id="23316-111">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="23316-112">В последних боты могут добавлять участники или владельцы команды.</span><span class="sxs-lookup"><span data-stu-id="23316-112">For channels, team owners or members can add bots.</span></span>

<a name="add-bots-for-private-chat-and-channels"></a><span data-ttu-id="23316-113">Добавление ботов для приватного чата и каналов</span><span class="sxs-lookup"><span data-stu-id="23316-113">Add bots for Private Chat and channels</span></span>
--------------------------------------

<span data-ttu-id="23316-114">Интегрировать бот для приватных чатов или каналов можно двумя способами.</span><span class="sxs-lookup"><span data-stu-id="23316-114">There are two ways to integrate a bot for private chats and channels:</span></span>

1.  <span data-ttu-id="23316-115">Установите общедоступный бот для **приватного чата** или **каналов**</span><span class="sxs-lookup"><span data-stu-id="23316-115">Install publicly available bots for **private chat** or **channels**.</span></span> <span data-ttu-id="23316-116">(первый способ).</span><span class="sxs-lookup"><span data-stu-id="23316-116">(This is the first option.)</span></span>

2.  <span data-ttu-id="23316-117">Найдите боты, перейдите в раздел **Чат**, найдите **контакт** и выберите элемент **Найти приложения.**</span><span class="sxs-lookup"><span data-stu-id="23316-117">Alternatively, to find bots, navigate to **Chat**, search for a **contact,** and click **Discover apps.**</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="23316-118">Выберите **бот**, с которым требуется открыть беседу, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="23316-118">Select which **Bot** you want to have a conversation with, as shown below.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image2.png)

4.  <span data-ttu-id="23316-119">Предоставьте выбранному боту **разрешения** и укажите, требуется ли использовать бот **в приватном чате** либо в конкретной **команде**.</span><span class="sxs-lookup"><span data-stu-id="23316-119">Once selected, provide the bot **permissions,** and select whether you want to use **bots in a private chat** or select a **Team** to use it in.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image3.png)

5.  <span data-ttu-id="23316-120">Кроме того, бот можно использовать в канале команды, просто выбрав **Просмотреть команду > Боты**.</span><span class="sxs-lookup"><span data-stu-id="23316-120">Alternatively, to use a bot within a channel of a team, simply click **View Team and Bots**.</span></span> <span data-ttu-id="23316-121">В открывшемся окне можно найти дополнительные боты.</span><span class="sxs-lookup"><span data-stu-id="23316-121">Here you can Discover additional bots.</span></span>

6.  <span data-ttu-id="23316-122">Бот можно удалить из команды в любое время.</span><span class="sxs-lookup"><span data-stu-id="23316-122">At any time, a bot can be removed from the team.</span></span> <span data-ttu-id="23316-123">Просто щелкните **Просмотреть команду > Боты**, чтобы отобразить все боты и затем **удалить** нужный.</span><span class="sxs-lookup"><span data-stu-id="23316-123">Simply click **View Team and Bots,** to see all bots and then **remove** the one you’d like.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image4.png)

<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="23316-124">Создание пользовательских ботов для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="23316-124">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="23316-125">С помощью Microsoft Bot Framework вы можете легко создать бот, интегрирующийся с вашими бизнес-приложениями.</span><span class="sxs-lookup"><span data-stu-id="23316-125">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework.</span></span> <span data-ttu-id="23316-126">Сведения о разработке и публикации своих ботов см. в руководстве [Создание и тестирование бота для Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371).</span><span class="sxs-lookup"><span data-stu-id="23316-126">Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="23316-127">При создании бота и его регистрации в Bot Framework вы можете указать, требуется ли его публиковать.</span><span class="sxs-lookup"><span data-stu-id="23316-127">When you create a bot and register it with the Bot Framework, you can choose to publish it or not.</span></span> <span data-ttu-id="23316-128">Без публикации бот остается частным.</span><span class="sxs-lookup"><span data-stu-id="23316-128">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="23316-129">Вы также можете потребовать, чтобы перед работой с ботом пользователи входили в систему.</span><span class="sxs-lookup"><span data-stu-id="23316-129">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="23316-130">Такой обязательный вход позволяет предоставить доступ к боту только сотрудникам вашей организации, даже если станет известен его идентификатор приложения.</span><span class="sxs-lookup"><span data-stu-id="23316-130">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="23316-131">В описании [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) на сайте GitHub приведен пример кода для проверки подлинности пользователей в Active Directory с помощью ботов.</span><span class="sxs-lookup"><span data-stu-id="23316-131">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="23316-132">Перед развертыванием в Teams боты можно тестировать с помощью [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373).</span><span class="sxs-lookup"><span data-stu-id="23316-132">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="23316-133">Загрузка собственного неопубликованного бота для приватного чата</span><span class="sxs-lookup"><span data-stu-id="23316-133">Side load your own bot for private chat</span></span>
---------------------------------------

1.  <span data-ttu-id="23316-134">Создав бот, перейдите на его [страницу](https://go.microsoft.com/fwlink/?linkid=854374) **Bot Dashboard** (Панель мониторинга бота) и скопируйте **Microsoft App ID** (ИД приложения Майкрософт) в области **Details** (Сведения).</span><span class="sxs-lookup"><span data-stu-id="23316-134">Once you have created your Bot, navigate to the **Bot Dashboard** [page](https://go.microsoft.com/fwlink/?linkid=854374) for the bot you developed, and under **Details**, copy the **Microsoft App ID**.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  <span data-ttu-id="23316-135">В области **Чат** Microsoft Teams выберите **значок добавления чата**.</span><span class="sxs-lookup"><span data-stu-id="23316-135">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="23316-136">В поле **Кому:** вставьте **ИД приложения Майкрософт** своего бота.</span><span class="sxs-lookup"><span data-stu-id="23316-136">For **To:,** paste your bot's **Microsoft app ID**.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3.  <span data-ttu-id="23316-137">Идентификатор разрешается в **имя бота**, после чего вы можете запустить беседу с этим ботом.</span><span class="sxs-lookup"><span data-stu-id="23316-137">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>
