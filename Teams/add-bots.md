---
title: Добавление ботов для приватных чатов и каналов в Microsoft Teams
author: LolaJacobsen, DamienDoumer
ms.author: lolaj, Damien
manager: serdars
ms.date: 12/05/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras
description: Сведения о добавлении ботов для приватного чата и каналов в Microsoft Teams, создании пользовательских ботов и загрузке собственного неопубликованного бота для приватного чата.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a4e921ea668fc59b520fdb068355db82bfe24481
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400540"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="91fca-103">Добавление ботов для приватных чатов и каналов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="91fca-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="91fca-104">Боты — это автоматические программы, которые отвечают на запросы или предоставляют интересующие пользователя уведомления и данные.</span><span class="sxs-lookup"><span data-stu-id="91fca-104">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="91fca-105">Они позволяют пользователю взаимодействовать с облачными службами, предназначенными, например, для управления задачами, планирования и опросов, через беседы чата в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="91fca-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="91fca-106">Боты для Microsoft Teams создаются на платформе [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span><span class="sxs-lookup"><span data-stu-id="91fca-106">Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span></span> <span data-ttu-id="91fca-107">Поэтому для Microsoft Teams можно легко адаптировать любые боты, разработанные на этой платформе.</span><span class="sxs-lookup"><span data-stu-id="91fca-107">The bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span> <span data-ttu-id="91fca-108">Дополнительные сведения см. в статье [Управление параметрами Microsoft Teams в организации](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="91fca-108">For more information, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="91fca-109">Сейчас Microsoft Teams поддерживает боты в приватных чатах и каналах внутри команды.</span><span class="sxs-lookup"><span data-stu-id="91fca-109">Currently, Microsoft Teams support bots in private chats and channels within a team.</span></span> <span data-ttu-id="91fca-110">Администраторы могут разрешить или запретить боты в клиенте Office 365.<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="91fca-110">Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="91fca-111">Microsoft Teams позволяет использовать боты, разработанные сообществом.</span><span class="sxs-lookup"><span data-stu-id="91fca-111">Bots developed by the community can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="91fca-112">Для работы пользовательских ботов требуется включить боты и их загрузку на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="91fca-112">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="91fca-113">Боты можно использовать в приватных чатах или каналах.</span><span class="sxs-lookup"><span data-stu-id="91fca-113">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="91fca-114">В последних боты могут добавлять участники или владельцы команды.</span><span class="sxs-lookup"><span data-stu-id="91fca-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="91fca-115">Дополнительные сведения см. в статье Using Bots (Использование ботов) раздела [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) (приложения и службы).</span><span class="sxs-lookup"><span data-stu-id="91fca-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 




<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="91fca-116">Создание пользовательских ботов для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="91fca-116">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="91fca-117">С помощью Microsoft Bot Framework вы можете легко создать бот, интегрирующийся с вашими бизнес-приложениями.</span><span class="sxs-lookup"><span data-stu-id="91fca-117">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework.</span></span> <span data-ttu-id="91fca-118">Сведения о разработке и публикации своих ботов см. в руководстве [Создание и тестирование бота для Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371).</span><span class="sxs-lookup"><span data-stu-id="91fca-118">Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="91fca-119">Создавая и регистрируя бот в Bot Framework, вы также можете опубликовать его.</span><span class="sxs-lookup"><span data-stu-id="91fca-119">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="91fca-120">Без публикации бот остается частным.</span><span class="sxs-lookup"><span data-stu-id="91fca-120">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="91fca-121">Вы также можете потребовать, чтобы перед работой с ботом пользователи входили в систему.</span><span class="sxs-lookup"><span data-stu-id="91fca-121">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="91fca-122">Такой обязательный вход позволяет предоставить доступ к боту только сотрудникам вашей организации, даже если станет известен его идентификатор приложения.</span><span class="sxs-lookup"><span data-stu-id="91fca-122">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="91fca-123">В описании [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) на сайте GitHub приведен пример кода для проверки подлинности пользователей в Active Directory с помощью ботов.</span><span class="sxs-lookup"><span data-stu-id="91fca-123">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="91fca-124">Перед развертыванием в Teams боты можно тестировать с помощью [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373).</span><span class="sxs-lookup"><span data-stu-id="91fca-124">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="91fca-125">Загрузка собственного неопубликованного бота для приватного чата</span><span class="sxs-lookup"><span data-stu-id="91fca-125">Side load your own bot for private chat</span></span>
---------------------------------------

1. <span data-ttu-id="91fca-126">После создания вашего программа-робот, перейдите в раздел **Параметров приложения** для программы-робота, который вы создали, затем в разделе **Параметры приложения**, скопируйте значение параметра **MicrosoftAppId** . ![Страницы параметров снимок экрана приложения для программы-робота с Идентификатором приложения Microsoft с выделением.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="91fca-126">After you have created your bot, go to the **Application Settings** for the bot you developed, then under **App settings**, copy the value of the **MicrosoftAppId** setting.![Screenshot of Application Settings page for a bot with the Microsoft App ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span>



2.  <span data-ttu-id="91fca-127">В области **Чат** Microsoft Teams выберите **значок добавления чата**.</span><span class="sxs-lookup"><span data-stu-id="91fca-127">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="91fca-128">В поле **Кому** вставьте **идентификатор приложения Майкрософт** своего бота.</span><span class="sxs-lookup"><span data-stu-id="91fca-128">For **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="91fca-129">![Снимок экрана с областью чата, где находится значок добавления чата и строка "Кому", а также выделен идентификатор приложения Майкрософт.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="91fca-129">![Screenshot of a chat pane with the icon for Add chat and the To line with the Microsoft app ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="91fca-130">Идентификатор разрешается в **имя бота**, после чего вы можете запустить беседу с этим ботом.</span><span class="sxs-lookup"><span data-stu-id="91fca-130">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>

<a name="side-load-your-bot-for-channels"></a><span data-ttu-id="91fca-131">Со стороны загрузить вашей программа-робот для каналов</span><span class="sxs-lookup"><span data-stu-id="91fca-131">Side load your bot for channels</span></span>
-----------------------------------

<span data-ttu-id="91fca-132">Если требуется предоставить общий доступ к программа-робот с коллегами, здесь — это способ добавления каналам разными группами:</span><span class="sxs-lookup"><span data-stu-id="91fca-132">If you want to share your bot with your colleagues, here's how to add it to channels of different teams:</span></span>

1. <span data-ttu-id="91fca-133">После того как [создан пакет приложения для вашей программы-робота](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)откройте групп и перейдите в группу, в которой вы будете со стороны загрузки робот.</span><span class="sxs-lookup"><span data-stu-id="91fca-133">After you have [created an app package for your bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), open Teams and browse to the team in which you'll be side-loading the bot.</span></span>
2. <span data-ttu-id="91fca-134">Добавьте **[Studio приложения](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, приложения для групп Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="91fca-134">Add **[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, app to Microsoft Teams.</span></span>
3. <span data-ttu-id="91fca-135">В приложении Studio выберите вкладку **Редактор манифеста** ![снимок экрана вкладки редактор манифеста.](media/Adding_Bot_To_Teams.png)</span><span class="sxs-lookup"><span data-stu-id="91fca-135">In App Studio, select the **Manifest Editor** Tab. ![Manifest Editor Tab Screenshot.](media/Adding_Bot_To_Teams.png)</span></span>
4. <span data-ttu-id="91fca-136">Чтобы добавить робота, в возможности, выберите программы-робота и было добавлено существующей программы-робота, а затем будет необходимо выбрать существующие программы-робота параметр из раскрывающегося или введите идентификатор одного из существующих роботов.</span><span class="sxs-lookup"><span data-stu-id="91fca-136">To add your bot, In capabilities, select bot and chose to add an existing bot, then you will have the option to chose an existing bot from a drop or enter the Id of one of your existing bots.</span></span>
<span data-ttu-id="91fca-137">![Выберите вашей программа-робот уже созданы.](media/Select_Existing_Bot.png)</span><span class="sxs-lookup"><span data-stu-id="91fca-137">![Select your bot you already created.](media/Select_Existing_Bot.png)</span></span>
5. <span data-ttu-id="91fca-138">Перейдите к папке пакет вашего приложения, выберите его и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="91fca-138">Browse to the location of your app package, select it, and then click **Open**.</span></span>
6. <span data-ttu-id="91fca-139">Выберите имя вашего программа-робот (не забудьте установите флажок «Группа» в разделе область)</span><span class="sxs-lookup"><span data-stu-id="91fca-139">Select your bot's name (Don't forget to check the "Team" checkbox under the scope section)</span></span>
7. <span data-ttu-id="91fca-140">Выберите тест и распространения параметр.</span><span class="sxs-lookup"><span data-stu-id="91fca-140">Select the Test and distribute option.</span></span>
8. <span data-ttu-id="91fca-141">Выберите группу, которую вы хотите подключиться вашей программа-робот для в диалоговом окне Всплывающая.</span><span class="sxs-lookup"><span data-stu-id="91fca-141">Select the team where you wish to connect your bot to in the dialog which pops up.</span></span>

<span data-ttu-id="91fca-142">С этого вашей программа-робот будут доступны в группы группы разработчиков Microsoft.</span><span class="sxs-lookup"><span data-stu-id="91fca-142">With this, your bot will be available in your Microsoft Team's team.</span></span>
