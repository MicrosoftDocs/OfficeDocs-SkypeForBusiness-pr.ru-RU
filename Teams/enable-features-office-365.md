---
title: "Включение функций Microsoft Teams в организации Office 365 | Служба поддержки Майкрософт"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения обо всех функциях Microsoft Teams, которые вы можете использовать в своей организации Office 365, включая параметры на уровне клиента, интеграции электронной почты, приложения, облачное хранилище и многое другое."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: e2235756e77c3e27c1eeee9fd22decb5e0e4e062
ms.sourcegitcommit: db47b9f4955150859bc35ab9d078fa3ab66b5faa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2017
---
<a name="enable-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="934da-103">Включение функций Microsoft Teams в организации Office 365</span><span class="sxs-lookup"><span data-stu-id="934da-103">Enable Microsoft Teams features in your Office 365 organization</span></span>
======================================================

<span data-ttu-id="934da-104">Система Microsoft Teams содержит несколько параметров, которые можно включить или отключить на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="934da-104">Microsoft Teams has multiple settings that can be enabled or disabled at the tenant level.</span></span> <span data-ttu-id="934da-105">Когда продукт Microsoft Teams включен для клиента, любой пользователь, у которого включен Microsoft Teams, наследует эти параметры уровня клиента.</span><span class="sxs-lookup"><span data-stu-id="934da-105">With Teams enabled for the tenant, any user that is also enabled for Teams will inherit the settings from the tenant level.</span></span>

<span data-ttu-id="934da-106">Ниже представлен список функций, которые администратор Office 365 может включить или отключить в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="934da-106">Below is the list of features an Office 365 administrator can choose to enable or disable in Teams.</span></span>

<span data-ttu-id="934da-107">Если не указано иное, по умолчанию для параметра установлено значение "Включено".</span><span class="sxs-lookup"><span data-stu-id="934da-107">Unless otherwise noted, the default value for an option is On.</span></span>

> [!NOTE]
> <span data-ttu-id="934da-108">Администратор Office 365 в любое время может отключить Microsoft Teams с помощью Центра администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="934da-108">An Office 365 admin can turn off Microsoft Teams at any time in the Office 365 Admin center.</span></span> <span data-ttu-id="934da-109">Помните о том, что пользователи с активными лицензиями на Microsoft Teams продолжат видеть плитку приложения Microsoft Teams, даже если вы его отключите.</span><span class="sxs-lookup"><span data-stu-id="934da-109">Be aware that users with active Microsoft Teams licenses will continue to see the Teams app tile even if you turn off Teams.</span></span> <span data-ttu-id="934da-110">Дополнительные сведения об удалении лицензий пользователей см. в статье [Управление доступом пользователей к Microsoft Teams](user-access.md)</span><span class="sxs-lookup"><span data-stu-id="934da-110">For details about how to remove licenses from users, see [Manage user access to Microsoft Teams](user-access.md).</span></span> <span data-ttu-id="934da-111">После отключения Microsoft Teams доступ из клиента блокируется, но данные, предоставляемые через другие клиенты и службы, остаются доступными, например файлы в SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="934da-111">After Teams is disabled, access from the Teams client is blocked, but data available through other clients and services is still available, such as files via SharePoint and OneDrive.</span></span> <span data-ttu-id="934da-112">Все данные остаются на месте, если только не производится явное удаление команд.</span><span class="sxs-lookup"><span data-stu-id="934da-112">All data remains in place unless the teams are explicitly deleted.</span></span>

<a name="tenant-wide-settings"></a><span data-ttu-id="934da-113">Параметры на уровне клиента</span><span class="sxs-lookup"><span data-stu-id="934da-113">Tenant-wide settings</span></span> 
---------------------

<span data-ttu-id="934da-114">В **области параметров на уровне клиента** можно включить или отключить общие параметры, параметры для интеграции электронной почты, приложений и настраиваемого облачного хранилища.</span><span class="sxs-lookup"><span data-stu-id="934da-114">In **Tenant-wide settings**, you can turn on or turn off options in General, Email integration, Apps, and Custom cloud storage.</span></span>

### <a name="general"></a><span data-ttu-id="934da-115">Общие</span><span class="sxs-lookup"><span data-stu-id="934da-115">General</span></span>

<span data-ttu-id="934da-116">В разделе "Общие" можно настроить для своей организации следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="934da-116">The General section lets you configure the following settings for your organization:</span></span>

> ![Снимок экрана с общим разделом в параметрах на уровне клиента.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   <span data-ttu-id="934da-118">**Show organizational chart in personal profile (Показать организационную диаграмму в личном профиле).** Когда этот параметр включен, в карточке контакта пользователя отображается значок организационной диаграммы. При его выборе отображается подробная организационная диаграмма.</span><span class="sxs-lookup"><span data-stu-id="934da-118">**Show organizational chart in personal profile:** When this setting is enabled, it shows the organizational chart icon in the user’s contact card and when clicked, it displays the detailed organizational chart.</span></span>

    ![Снимок экрана со значком организационной диаграммы в карточке контакта пользователя.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![Снимок экрана с организационной диаграммой.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-   <span data-ttu-id="934da-121">**Use Skype for Business for recipients who don’t have Microsoft Teams (Использовать Skype для бизнеса для получателей без Microsoft Teams).** Когда этот параметр включен, пользователям Microsoft Teams разрешено общаться с другими пользователями в организации, для которых не была включена поддержка Microsoft Teams через Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="934da-121">**Use Skype for Business for recipients who don’t have Microsoft Teams:** When this setting is enabled, it allows Microsoft Teams users to contact other users in the organization that are not enabled for Microsoft Teams via Skype for Business.</span></span>

-   <span data-ttu-id="934da-122">**Allow T-bot proactive help messages (Разрешить справку П-бота).** Когда этот параметр включен, П-бот открывает с пользователями сеанс приватного чата, чтобы помочь им с использованием Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="934da-122">**Allow T-bot proactive help messages:** When this setting is enabled, T-bot will initiate a private chat session with users to guide them in using Microsoft Teams.</span></span>

    ![Снимок экрана с разделом П-бота в интерфейсе Microsoft Teams.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a><span data-ttu-id="934da-124">Интеграция электронной почты</span><span class="sxs-lookup"><span data-stu-id="934da-124">Email integration</span></span>
-----------------

<span data-ttu-id="934da-125">Включите параметр "Email integration" (Интеграция электронной почты), чтобы пользователи могли отправить сообщение электронной почты по адресу канала в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="934da-125">Turn this feature on so that users can send an email to a channel in Microsoft Teams, using the channel email address.</span></span> <span data-ttu-id="934da-126">Подобную операцию пользователи могут выполнить для любого канала, относящегося к принадлежащей им команде.</span><span class="sxs-lookup"><span data-stu-id="934da-126">Users can do this for any channel belonging to a team they own.</span></span> <span data-ttu-id="934da-127">Кроме того, пользователи могут отправлять сообщения электронной почты в любой канал в команде, где для участников включены соединители добавления.</span><span class="sxs-lookup"><span data-stu-id="934da-127">Users can also send emails to any channel in a team that has adding connectors enabled for team members.</span></span> <span data-ttu-id="934da-128">И даже если у пользователя нет разрешений на создание адреса электронной почты для канала, когда кто-либо с подобными правами создает такой адрес, пользователь может обратиться к нему с помощью меню \<значка "Дополнительно"\> этого канала.</span><span class="sxs-lookup"><span data-stu-id="934da-128">And, even if a user doesn’t have permission to create a channel email address, if someone who does have permission creates that address, the user can access it from the \<more icon\> menu for that channel.</span></span>

<span data-ttu-id="934da-129">В разделе "Email integration" (Интеграция электронной почты) можно настроить для своей организации следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="934da-129">The Email integration section lets you configure the following settings for your organization:</span></span>

   ![Снимок экрана с разделом интеграции электронной почты в параметрах на уровне клиента.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image5.png)

-   <span data-ttu-id="934da-131">**Allow users to send emails to channels (Разрешить пользователям отправлять сообщения электронной почты в каналы).** Когда этот параметр включен, активируются обработчики почты, и пользователи могут публиковать сообщения в канале, отправляя сообщения электронной почты на адрес канала Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="934da-131">**Allow users to send emails to channels:** When enabled, mail hooks are enabled, and users can post messages to a channel by sending an email to the email address of Microsoft Teams channel.</span></span>

> <span data-ttu-id="934da-132">Чтобы найти адрес электронной почты канала, щелкните элемент **Дополнительные параметры** рядом с именем канала и выберите **Получить адрес эл. почты**.</span><span class="sxs-lookup"><span data-stu-id="934da-132">To find the channel’s e-mail address, click **More options** next to the channel name and then select **Get email address**.</span></span>

-   <span data-ttu-id="934da-133">**Restricted Senders List (Ограниченный список отправителей).** Параметр позволяет дополнительно ограничить домены отправителей, разрешив отправку сообщений электронной почты в каналы Microsoft Teams только из доменов SMTP.</span><span class="sxs-lookup"><span data-stu-id="934da-133">**Restricted Senders List:** Senders domains can be further restricted to ensure that only allowed SMTP domains can send emails to the Microsoft Teams channels.</span></span>

<a name="apps"></a><span data-ttu-id="934da-134">Приложения</span><span class="sxs-lookup"><span data-stu-id="934da-134">Apps</span></span>
----

<span data-ttu-id="934da-135">Приложения в Microsoft Teams отлично подходят для интеграции средств и служб, необходимых вашей команде, прямо в любой канал или чат.</span><span class="sxs-lookup"><span data-stu-id="934da-135">Apps in Microsoft Teams are a terrific way to integrate the tools and services your team cares about, right into any channel or chat.</span></span>

<span data-ttu-id="934da-136">В разделе **Приложения** можно настроить для своей организации следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="934da-136">The **Apps** section lets you configure the following settings for your organization:</span></span>

![Снимок экрана с разделом приложений.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

-   <span data-ttu-id="934da-138">**Allow external apps in Microsoft Teams (Разрешить внешние приложения в Microsoft Teams).** Когда этот параметр включен, пользователи могут добавлять доступные вкладки и боты для клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="934da-138">**Allow external apps in Microsoft Teams:** When enabled, users can add tabs and bots that are available to the Office 365 tenant.</span></span>
<span data-ttu-id="934da-139">![Снимок экрана с параметром "Allow external apps control" (Разрешить управление внешними приложениями) в разделе приложений.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)</span><span class="sxs-lookup"><span data-stu-id="934da-139">![Screenshot of the Allow external apps control in the Apps section.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)</span></span>

-   <span data-ttu-id="934da-140">**Allow sideloading of external apps (Разрешить загрузку неопубликованных внешних приложений).** Когда этот параметр включен, пользователи могут устанавливать и активировать настраиваемые вкладки и боты.</span><span class="sxs-lookup"><span data-stu-id="934da-140">**Allow sideloading of external apps:** When enabled, users can install and enable custom bots and tabs.</span></span>

<a name="custom-cloud-storage"></a><span data-ttu-id="934da-141">Настраиваемое облачное хранилище</span><span class="sxs-lookup"><span data-stu-id="934da-141">Custom cloud storage</span></span>
--------------------

<span data-ttu-id="934da-142">Сейчас параметры облачного хранилища в Microsoft Teams включают Box, Dropbox, Google Диск и ShareFile.</span><span class="sxs-lookup"><span data-stu-id="934da-142">Cloud storage options in Microsoft Teams currently include Box, Dropbox, Google Drive, and ShareFile.</span></span> <span data-ttu-id="934da-143">Пользователи могут отправлять и совместно использовать файлы из служб облачного хранилища в каналах и чатах Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="934da-143">Users can upload and share files from cloud storage services in Microsoft Teams channels and chats.</span></span> <span data-ttu-id="934da-144">Щелкните или нажмите переключатель рядом с поставщиками облачных хранилищ, которые нужно использовать в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="934da-144">Click or tap the toggle switch next to the cloud storage providers that your organization wants to use.</span></span>

![Снимок экрана с разделом настраиваемого облачного хранилища.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="user-settings-by-license"></a><span data-ttu-id="934da-146">Параметры пользователей по лицензии</span><span class="sxs-lookup"><span data-stu-id="934da-146">User settings by license</span></span>
------------------------

<span data-ttu-id="934da-147">В области **User settings by license** (Параметры пользователей по лицензии) вы можете включить или отключить параметры для команд и каналов, звонков и собраний, а также обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="934da-147">In **User settings by license**, you can turn on or turn off options in Teams and channels, Calls and meetings, and Messaging.</span></span>

<a name="teams-and-channels"></a><span data-ttu-id="934da-148">Команды и каналы</span><span class="sxs-lookup"><span data-stu-id="934da-148">Teams and channels</span></span>
------------------

<span data-ttu-id="934da-149">Команда предназначена для объединения группы людей, которые тесно сотрудничают друг с другом для выполнения поставленных задач.</span><span class="sxs-lookup"><span data-stu-id="934da-149">A team is designed to bring together a group of people who work closely to get things done.</span></span> <span data-ttu-id="934da-150">Команды могут динамически формироваться под конкретные проекты (например, выпуск продукта на рынок или организация цифрового конференц-зала).</span><span class="sxs-lookup"><span data-stu-id="934da-150">Teams can be dynamic for project-based work (for example, launching a product or creating a digital war room).</span></span> <span data-ttu-id="934da-151">Кроме того, команды могут быть оперативными для отражения внутренней структуры организации.</span><span class="sxs-lookup"><span data-stu-id="934da-151">Or, teams can be ongoing, to reflect the internal structure of your organization.</span></span>

<span data-ttu-id="934da-152">Являясь администратором, вы можете управлять владельцами и участниками команд с помощью панели мониторинга "Группы" на портале Центра администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="934da-152">As an admin, you can manage team owners and members by using the Groups dashboard in the Office 365 admin center portal.</span></span> <span data-ttu-id="934da-153">В разделе "Команды и каналы" щелкните ссылку **Use the Groups dashboard in the Office 365 admin center to manage teams** (Использовать панель мониторинга "Группы" Центре администрирования Office 365 для управления командами).</span><span class="sxs-lookup"><span data-stu-id="934da-153">In the Teams and channels section, click the link for **Use the Groups dashboard in the Office 365 admin center to manage teams**.</span></span>

<span data-ttu-id="934da-154">Вы можете контролировать, кто из пользователей организации может создавать команды в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="934da-154">You can control which users in your organization can create teams in Microsoft Teams.</span></span> <span data-ttu-id="934da-155">Определенные в группах Office 365 параметры создания применяются и к Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="934da-155">The same creation settings defined by Office 365 groups apply to Microsoft Teams.</span></span> <span data-ttu-id="934da-156">Дополнительные сведения об управлении группами Office 365 см. в статьях [Создание групп Office 365](https://support.office.com/en-us/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) и [Управление правами на создание групп Office 365](https://support.office.com/en-us/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="934da-156">For more information about managing Office 365 groups, see [Create Office 365 groups](https://support.office.com/en-us/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) and [Control who can create Office 365 Groups](https://support.office.com/en-us/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

<span data-ttu-id="934da-157">Примечание. Вы не можете создавать команды из панели мониторинга "Группы".</span><span class="sxs-lookup"><span data-stu-id="934da-157">NOTE: You can't create teams from the Groups dashboard.</span></span> <span data-ttu-id="934da-158">Для этого нужно использовать классический или веб-клиент Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="934da-158">Teams must be created by using the Microsoft Teams desktop client or web app.</span></span>

<span data-ttu-id="934da-159">По умолчанию создать команду или группу может любой пользователь.</span><span class="sxs-lookup"><span data-stu-id="934da-159">By default, every user can create a team or group.</span></span> <span data-ttu-id="934da-160">Пользователи могут создавать команды, выбрав пункт "Команды" в левой части клиента Microsoft Teams (классического или веб-приложения) и затем пункт "Создать команду" в нижней части окна, под списком команд.</span><span class="sxs-lookup"><span data-stu-id="934da-160">Users can create teams by choosing Teams on the left side in the Microsoft Teams client (desktop client or web app), and then choosing Create team at the bottom of the client, below the team list.</span></span>

<span data-ttu-id="934da-161">Сейчас максимальное число команд, которые может иметь клиент Office 365, по умолчанию равно 500 000.</span><span class="sxs-lookup"><span data-stu-id="934da-161">The default maximum number of teams that an Office 365 tenant can have is currently 500,000.</span></span> <span data-ttu-id="934da-162">Глобальный администратор может создать любое число команд.</span><span class="sxs-lookup"><span data-stu-id="934da-162">A global admin can create an unlimited number of teams.</span></span> <span data-ttu-id="934da-163">Пользователь может создать 250 команд.</span><span class="sxs-lookup"><span data-stu-id="934da-163">A user can create 250 teams.</span></span> <span data-ttu-id="934da-164">Владелец команды может добавить в нее 2500 участников.</span><span class="sxs-lookup"><span data-stu-id="934da-164">A team owner can add 2500 members to a team.</span></span>

![Снимок экрана с разделом параметров пользователей по лицензии.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

<span data-ttu-id="934da-166">Каналы являются подкатегориями команд.</span><span class="sxs-lookup"><span data-stu-id="934da-166">Channels are subcategories of teams.</span></span> <span data-ttu-id="934da-167">Любой участник команды может добавить канал и участвовать в беседах канала.</span><span class="sxs-lookup"><span data-stu-id="934da-167">Anyone on the team can add a channel and participate in the conversations in a channel.</span></span> <span data-ttu-id="934da-168">Канал можно создать для действия или для отдела.</span><span class="sxs-lookup"><span data-stu-id="934da-168">You might create a channel for an activity or for a department.</span></span> <span data-ttu-id="934da-169">Беседы, файлы и вики-страницы относятся к конкретному каналу, но просматривать их могут все участники команды.</span><span class="sxs-lookup"><span data-stu-id="934da-169">Conversations, files, and wikis are specific to each channel, but all members of the team can see them.</span></span>

### <a name="calls-and-meetings"></a><span data-ttu-id="934da-170">Звонки и собрания</span><span class="sxs-lookup"><span data-stu-id="934da-170">Calls and meetings</span></span>

<span data-ttu-id="934da-171">В разделе **Звонки и собрания** можно настроить для своей организации следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="934da-171">The **Calls and meetings** section lets you configure the following settings for your organization:</span></span>

> ![Снимок экрана с разделом звонков и собраний.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

-   <span data-ttu-id="934da-173">**Allow scheduling for private meetings (Разрешить планирование для частных собраний):** Когда параметр включен, пользователи могут планировать частные собрания, не указанные ни в одном из каналов.</span><span class="sxs-lookup"><span data-stu-id="934da-173">**Allow scheduling for private meetings:** When enabled, users can schedule private meetings that are not listed in any channel.</span></span>

-   <span data-ttu-id="934da-174">**Allow ad-hoc channel meetup (Разрешить специальную встречу в канале).**</span><span class="sxs-lookup"><span data-stu-id="934da-174">**Allow ad-hoc channel meetup:**</span></span>

-   <span data-ttu-id="934da-175">**Allow scheduling for channel meetings (Разрешить планирование для собраний канала).** Когда параметр включен, пользователи могут планировать собрание для канала, к которому все участники этого канала могут присоединиться одним щелчком.</span><span class="sxs-lookup"><span data-stu-id="934da-175">**Allow scheduling for channel meetings:** When enabled, users can schedule a meeting for a channel that all channel members can easily join with a single click.</span></span>

-   <span data-ttu-id="934da-176">**Allow videos in meetings (Разрешить видео на собраниях).** Указывает, разрешено ли использовать видео на собраниях.</span><span class="sxs-lookup"><span data-stu-id="934da-176">**Allow videos in meetings:** Specifies whether the use of video is allowed within the meetings.</span></span>

-   <span data-ttu-id="934da-177">**Allow screen sharing in meetings (Разрешить демонстрацию экрана на собраниях).** Указывает, разрешено ли использовать демонстрацию экрана на собраниях.</span><span class="sxs-lookup"><span data-stu-id="934da-177">**Allow screen sharing in meetings:** Specifies whether screen sharing is allowed within the meetings.</span></span>

-   <span data-ttu-id="934da-178">**Allow private calling (Разрешить частные звонки).** Когда параметр включен, пользователи могут совершать частные звонки.</span><span class="sxs-lookup"><span data-stu-id="934da-178">**Allow private calling:** When enabled, users can make private calls.</span></span>

<span data-ttu-id="934da-179">Максимальное число людей на собрании равно 80.</span><span class="sxs-lookup"><span data-stu-id="934da-179">The maximum number of people in a meeting is 80.</span></span> <span data-ttu-id="934da-180">В приватном чате могут участвовать 20 человек, включая создавшего его пользователя.</span><span class="sxs-lookup"><span data-stu-id="934da-180">There can be 20 members in a private chat, including the user who created the chat.</span></span>

### <a name="messaging"></a><span data-ttu-id="934da-181">Обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="934da-181">Messaging</span></span> 

<span data-ttu-id="934da-182">В разделе "Обмен сообщениями" можно настроить для своей организации следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="934da-182">The Messaging section lets you configure the following settings for your organization:</span></span>

![Снимок экрана с разделом сообщений.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   <span data-ttu-id="934da-184">**Enable Giphy so users can add gifs to conversations (Включить Giphy, чтобы пользователи могли добавлять в беседы GIF-файлы).** Когда параметр включен, пользователи могут добавлять рисунки с анимацией во время бесед.</span><span class="sxs-lookup"><span data-stu-id="934da-184">**Enable Giphy so users can add gifs to conversations:** When enabled, users can use animated pictures within the conversations.</span></span>

    -   <span data-ttu-id="934da-185">**Content Rating (Рейтинг контента).** Если включены рисунки с анимацией, можно применить рейтинг контента для ограничения типов подобных изображений, которые разрешено отображать в беседах.</span><span class="sxs-lookup"><span data-stu-id="934da-185">**Content Rating:** When animated images are turned on, content rating can be applied to restrict the type of animated images that can be displayed in conversations.</span></span> <span data-ttu-id="934da-186">Доступны следующие варианты рейтинга контента:</span><span class="sxs-lookup"><span data-stu-id="934da-186">Available content rating options are:</span></span>

        -   <span data-ttu-id="934da-187">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="934da-187">No restriction</span></span>

        -   <span data-ttu-id="934da-188">Средний (значение по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="934da-188">Moderate (the default value)</span></span>

        -   <span data-ttu-id="934da-189">Строгий</span><span class="sxs-lookup"><span data-stu-id="934da-189">Strict</span></span>

-   <span data-ttu-id="934da-190">**Enable memes that users can edit and add to conversations (Включить мемы, которые пользователи могут изменять и добавлять в беседы).** Когда параметр включен, можно использовать интернет-мемы для придания публикациям шутливого оттенка.</span><span class="sxs-lookup"><span data-stu-id="934da-190">**Enable memes that users can edit and add to conversations:** When enabled, users can use internet memes to make humorous posts.</span></span>

-   <span data-ttu-id="934da-191">**Enable stickers that users can edit and add to conversations (Включить стикеры, которые пользователи могут изменять и добавлять в беседы).** Когда параметр включен, пользователи могут публиковать изображения с редактируемым текстом для привлечения внимания участников канала.</span><span class="sxs-lookup"><span data-stu-id="934da-191">**Enable stickers that users can edit and add to conversations:** When enabled, users can post images with editable text to get channel members attention.</span></span>

-   <span data-ttu-id="934da-192">**Allow owners to delete all messages (Разрешить владельцам удалить все изображения).** Когда параметр включен, владелец канала может удалить все сообщения в нем.</span><span class="sxs-lookup"><span data-stu-id="934da-192">**Allow owners to delete all messages:** When enabled, channel owners can remove all messages in a channel.</span></span>

-   <span data-ttu-id="934da-193">**Allow users to edit their own messages (Разрешить пользователям редактировать свои сообщения).** Когда параметр включен, пользователи могут редактировать свои сообщения.</span><span class="sxs-lookup"><span data-stu-id="934da-193">**Allow users to edit their own messages:** When enabled, users can edit their own messages.</span></span>

-   <span data-ttu-id="934da-194">**Allow users to delete their own messages (Разрешить пользователям удалять свои сообщения).** Когда параметр включен, пользователи могут удалять свои сообщения.</span><span class="sxs-lookup"><span data-stu-id="934da-194">**Allow users to delete their own messages:** When enabled, users can delete their own messages.</span></span>

-   <span data-ttu-id="934da-195">**Allow users to chat privately (Разрешить пользователям приватный чат).** Когда параметр включен, пользователи могут открывать приватный чат, видимый только его участникам, а не всем людям в команде.</span><span class="sxs-lookup"><span data-stu-id="934da-195">**Allow users to chat privately:** When enabled, users can engage in private chats that are visible only to the people in the chat, instead of everyone on the team.</span></span>


| |  |  |
|---------|---------|---------|
|![Значок для точки принятия решений.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |<span data-ttu-id="934da-197">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="934da-197">Decision Point</span></span>         |<span data-ttu-id="934da-198">Какие параметры Microsoft Teams включит ваша организация?</span><span class="sxs-lookup"><span data-stu-id="934da-198">What settings for Microsoft Teams will your organization enable?</span></span>         |
|![Значок дальнейших действий.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |<span data-ttu-id="934da-200">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="934da-200">Next Steps</span></span>        |<span data-ttu-id="934da-201">Занесите эти решения в таблицу в статье [Назначение ролей и разрешений в Microsoft Teams](assign-roles-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="934da-201">Document these decisions in the table in [Assign roles and permissions in Microsoft Teams](assign-roles-permissions.md).</span></span>         |

