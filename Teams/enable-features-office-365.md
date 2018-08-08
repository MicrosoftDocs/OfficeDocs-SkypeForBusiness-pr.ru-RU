---
title: Управление группами Майкрософт возможностями в организации Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Узнайте обо всех функциях Microsoft Teams, которые вы можете использовать в своей организации Office 365, включая параметры на уровне клиентов, интеграцию электронной почты, приложения, облачное хранилище и многое другое.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50650d852e87cb885beae4403022464fafb57373
ms.sourcegitcommit: 8c3dcfc564c489f4d33bd5f391a5a66b99ded07e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "20265949"
---
<a name="manage-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="31248-103">Управление группами Майкрософт возможностями в организации Office 365</span><span class="sxs-lookup"><span data-stu-id="31248-103">Manage Microsoft Teams features in your Office 365 organization</span></span>
======================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="31248-104">Teams содержит множество параметров, которые можно включать и отключать на уровне клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="31248-104">Teams has multiple settings that can be turned on or turned off at the Office 365 tenant level.</span></span> <span data-ttu-id="31248-105">С командами включен любой пользователь, который также включены для групп наследуют параметры на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="31248-105">With Teams enabled, any user that is also enabled for Teams will inherit the settings from the tenant level.</span></span>

<span data-ttu-id="31248-106">Ниже представлен список функций, которые администратор Office 365 может включить или отключить в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="31248-106">Below is the list of features an Office 365 administrator can turn on or turn off in Teams.</span></span> 

<span data-ttu-id="31248-107">Если не указано иное, по умолчанию для параметра установлено значение "Включено".</span><span class="sxs-lookup"><span data-stu-id="31248-107">Unless otherwise noted, the default value for an option is On.</span></span>

> [!NOTE] 
> <span data-ttu-id="31248-108">Настройки администрирования для Microsoft Teams находятся в Центре администрирования Office 365 в разделе **Параметры**  >  **Службы и надстройки** > **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="31248-108">To manage admin settings for Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="31248-109">Если вы вошли как администратор Office 365, воспользуйтесь ссылкой</span><span class="sxs-lookup"><span data-stu-id="31248-109">If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

> [!IMPORTANT]
> <span data-ttu-id="31248-110">Администратор Office 365 может в любое время отключить Microsoft Teams с помощью Центра администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="31248-110">An Office 365 admin can turn off Microsoft Teams at any time in the Office 365 admin center.</span></span> <span data-ttu-id="31248-111">Помните о том, что пользователи с активными лицензиями на Microsoft Teams продолжат видеть плитку приложения Microsoft Teams, даже если вы его отключите.</span><span class="sxs-lookup"><span data-stu-id="31248-111">Be aware that users with active Microsoft Teams licenses will continue to see the Teams app tile even if you turn off Teams.</span></span> <span data-ttu-id="31248-112">Дополнительные сведения об удалении лицензий пользователей см. в статье [Управление доступом пользователей к Microsoft Teams](user-access.md)</span><span class="sxs-lookup"><span data-stu-id="31248-112">For details about how to remove licenses from users, see [Manage user access to Microsoft Teams](user-access.md).</span></span> <span data-ttu-id="31248-113">После отключения Microsoft Teams доступ из клиента блокируется, но данные, предоставляемые через другие клиенты и службы, остаются доступными, например файлы в SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="31248-113">After Teams is disabled, access from the Teams client is blocked, but data available through other clients and services is still available, such as files via SharePoint and OneDrive.</span></span> <span data-ttu-id="31248-114">Все данные остаются на месте, если только не производится явное удаление команд.</span><span class="sxs-lookup"><span data-stu-id="31248-114">All data remains in place unless the teams are explicitly deleted.</span></span>

<a name="office-365-tenant-wide-settings"></a><span data-ttu-id="31248-115">Параметры Office 365 на уровне клиента</span><span class="sxs-lookup"><span data-stu-id="31248-115">Office 365 tenant-wide settings</span></span> 
---------------------

<span data-ttu-id="31248-116">В **области параметров на уровне клиента** можно включить или отключить общие параметры, параметры для интеграции электронной почты, приложений и настраиваемого облачного хранилища.</span><span class="sxs-lookup"><span data-stu-id="31248-116">In **Tenant-wide settings**, you can turn on or turn off options in General, Email integration, Apps, and Custom cloud storage.</span></span>

<span data-ttu-id="31248-117">Чтобы изменить в Teams **параметры уровня клиента**, зайдите в Центр администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="31248-117">To edit **Tenant-wide settings** for Teams, go to the Office 365 admin center.</span></span> <span data-ttu-id="31248-118">Выберите **Settings (Параметры)** > **Services & add-ins (Службы и надстройки)** > **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="31248-118">Choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span>

### <a name="general"></a><span data-ttu-id="31248-119">Общие</span><span class="sxs-lookup"><span data-stu-id="31248-119">General</span></span>

<span data-ttu-id="31248-120">В разделе "Общие" можно настроить для своей организации следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="31248-120">The General section lets you configure the following settings for your organization:</span></span>

> ![Снимок экрана с общим разделом в параметрах на уровне клиента.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   <span data-ttu-id="31248-122">**Show organizational chart in personal profile** (Показать организационную диаграмму в личном профиле). Когда этот параметр включен, в карточке контакта пользователя отображается значок организационной диаграммы. При его выборе отображается подробная организационная диаграмма.</span><span class="sxs-lookup"><span data-stu-id="31248-122">**Show organizational chart in personal profile:** When this setting is turned on, it shows the organizational chart icon in the user’s contact card, and when clicked, it displays the detailed organizational chart.</span></span>

    ![Снимок экрана со значком организационной диаграммы в карточке контакта пользователя.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![Снимок экрана с организационной диаграммой.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-  <span data-ttu-id="31248-125">**Use Skype for Business for recipients who don’t have Microsoft Teams** (Использовать Skype для бизнеса для получателей без Microsoft Teams). Когда этот параметр включен, беседы Microsoft Teams автоматически отображаются в Skype для бизнеса для тех пользователей, у которых нет доступа к Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="31248-125">**Use Skype for Business for recipients who don’t have Teams:** When this setting is turned on, Teams conversations automatically show up in Skype for Business for users that aren't enabled for Teams.</span></span>  

-   <span data-ttu-id="31248-126">**Allow T-bot proactive help messages** (Разрешить справочные сообщения T-бота). Когда этот параметр включен,T-бот открывает с пользователями сеанс приватного чата, чтобы помочь им в работе с Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="31248-126">**Allow T-bot proactive help messages:** When this setting is turned on, T-bot will initiate a private chat session with users to help them use Teams.</span></span>

    ![Снимок экрана с разделом П-бота в интерфейсе Teams.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a><span data-ttu-id="31248-128">Интеграция электронной почты</span><span class="sxs-lookup"><span data-stu-id="31248-128">Email integration</span></span>
-----------------

<span data-ttu-id="31248-129">Включите этот параметр, чтобы пользователи могли отправлять сообщения электронной почты на адрес канала в Teams.</span><span class="sxs-lookup"><span data-stu-id="31248-129">Turn on this feature so users can send email to a channel in Teams, using the channel email address.</span></span> <span data-ttu-id="31248-130">Подобную операцию пользователи могут выполнить для любого канала, относящегося к принадлежащей им команде.</span><span class="sxs-lookup"><span data-stu-id="31248-130">Users can do this for any channel belonging to a team they own.</span></span> <span data-ttu-id="31248-131">Кроме того, пользователи могут отправлять сообщения электронной почты в любой канал в команде, где для участников включены соединители добавления.</span><span class="sxs-lookup"><span data-stu-id="31248-131">Users can also send emails to any channel in a team that has adding connectors enabled for team members.</span></span> <span data-ttu-id="31248-132">И даже если у пользователя нет разрешений на создание адреса электронной почты для канала, когда кто-либо с подобными правами создает такой адрес, пользователь может обратиться к нему с помощью меню **More options** (Дополнительные параметры) этого канала.</span><span class="sxs-lookup"><span data-stu-id="31248-132">And, even if a user doesn’t have permission to create a channel email address, if someone who does have permission creates that address, the user can access it from the **More options** menu for that channel.</span></span>

<span data-ttu-id="31248-133">Настройте для своей организации следующие параметры **интеграции электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="31248-133">Configure the following **Email integration** settings for your organization:</span></span> 

   ![Снимок экрана с разделом интеграции электронной почты в параметрах на уровне клиента.](media/QS-edu-email-integration.png)


-   <span data-ttu-id="31248-135">**Allow users to send emails to channels** (Разрешить пользователям отправлять сообщения электронной почты в каналы). Когда этот параметр включен, активируются обработчики почты и пользователи могут публиковать в канале Microsoft Teams сообщения, отправляя электронные письма на адрес канала.</span><span class="sxs-lookup"><span data-stu-id="31248-135">**Allow users to send emails to channels:** When turned on, mail hooks are enabled, and users can post messages to a channel by sending an email to the email address of Teams channel.</span></span> 

    <span data-ttu-id="31248-136">Чтобы найти адрес электронной почты канала, выберите пункт **More options** (Дополнительные параметры) рядом с именем канала и затем **Get email address** (Получить адрес электронной почты).</span><span class="sxs-lookup"><span data-stu-id="31248-136">To find the email address for a channel, click the **More options** menu for the channel and then select **Get email address**.</span></span> 

-   <span data-ttu-id="31248-137">**Restricted Senders List (Ограниченный список отправителей).** Параметр позволяет дополнительно ограничить домены отправителей, разрешив отправку сообщений электронной почты в каналы Teams только из доменов SMTP.</span><span class="sxs-lookup"><span data-stu-id="31248-137">**Restricted Senders List:** Senders domains can be further restricted to ensure that only allowed SMTP domains can send emails to the Teams channels.</span></span>

<a name="apps"></a><span data-ttu-id="31248-138">Приложения</span><span class="sxs-lookup"><span data-stu-id="31248-138">Apps</span></span>
----

<span data-ttu-id="31248-139">Приложения — это предоставляемые сторонними службами вкладки, соединители, боты или любое их сочетание.</span><span class="sxs-lookup"><span data-stu-id="31248-139">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="31248-140">Центр администрирования Office 365 позволяет настроить политики администрирования Microsoft Teams, которые определяют разрешенные внешние сторонние приложения.</span><span class="sxs-lookup"><span data-stu-id="31248-140">There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed.</span></span> <span data-ttu-id="31248-141">В них вы можете указать, какие программы следует разрешать, а какие — блокировать, как работать с новыми внешними приложениями и можно ли загружать неопубликованные приложения.</span><span class="sxs-lookup"><span data-stu-id="31248-141">These policies let you specify which apps are allowed and disallowed, new external App behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="31248-142">В разделе **Приложения** вы можете настроить для своей организации следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="31248-142">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![Снимок экрана с разделом приложений.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="31248-144">**Allow external apps in Microsoft Teams** (Разрешить внешние приложения в Microsoft Teams). Когда этот параметр включен, пользователи могут добавлять вкладки и боты, доступные для клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="31248-144">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![Снимок экрана с параметром "Allow external apps control" (Разрешить управление внешними приложениями) в разделе приложений.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="31248-146">**Enable new external apps by default** (Включить новые внешние приложения по умолчанию). Если этот параметр включен, пользователи могут активировать новые приложения сразу после их добавления в каталог приложений Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="31248-146">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="31248-147">Если вы хотите контролировать новые приложения, отключите этот параметр.</span><span class="sxs-lookup"><span data-stu-id="31248-147">Turn off this switch if you want to control new apps.</span></span> <span data-ttu-id="31248-148">В этом случае не забывайте периодически просматривать новые приложения, чтобы ваша организация не пропустила появление новых интересных программ.</span><span class="sxs-lookup"><span data-stu-id="31248-148">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="31248-149">**Allow sideloading of external apps** (Разрешить загрузку неопубликованных внешних приложений). Когда этот параметр включен, пользователи могут устанавливать и активировать настраиваемые вкладки и боты.</span><span class="sxs-lookup"><span data-stu-id="31248-149">**Allow sideloading of external apps**: When this switch is turned on, users can install and enable custom bots and tabs.</span></span> 

<span data-ttu-id="31248-150">Подробнее см. в статье [Параметры администратора для приложений в Microsoft Teams](admin-settings.md).</span><span class="sxs-lookup"><span data-stu-id="31248-150">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 



<a name="custom-cloud-storage"></a><span data-ttu-id="31248-151">Настраиваемое облачное хранилище</span><span class="sxs-lookup"><span data-stu-id="31248-151">Custom cloud storage</span></span>
--------------------

<span data-ttu-id="31248-152">В качестве облачного хранилища Teams сейчас поддерживает Box, Dropbox, Google Диск и ShareFile.</span><span class="sxs-lookup"><span data-stu-id="31248-152">Cloud storage options in Teams currently include Box, Dropbox, Google Drive, and ShareFile.</span></span> <span data-ttu-id="31248-153">Пользователи могут загружать и отправлять друг другу файлы из облачных служб хранения в каналах и чатах Teams.</span><span class="sxs-lookup"><span data-stu-id="31248-153">Users can upload and share files from cloud storage services in Teams channels and chats.</span></span> <span data-ttu-id="31248-154">Выберите переключатель рядом с поставщиками услуг облачного хранения, которые нужно использовать в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="31248-154">Turn on the switch for the cloud storage providers that your organization wants to use.</span></span> 

![Снимок экрана с разделом настраиваемого облачного хранилища.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="settings-by-userlicense-type"></a><span data-ttu-id="31248-156">Введите параметры пользователя и лицензии</span><span class="sxs-lookup"><span data-stu-id="31248-156">Settings by user/license type</span></span>
------------------------
<span data-ttu-id="31248-157">При настройке групп Майкрософт для вашей организации изначально, который использовался раскрывающееся меню **параметров по типу лицензии пользователя** для выбора типа лицензии и затем включена групп для всех пользователей этого типа лицензии.</span><span class="sxs-lookup"><span data-stu-id="31248-157">When you set up Microsoft Teams for your organization initially, you used the the **Settings by user/license type** drop-down menu to select a license type and then turned Teams on for all users of that license type.</span></span>

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

 <span data-ttu-id="31248-158">Некоторые примеры типов пользователей/лицензии, **и крупный бизнес** и **гостя**.</span><span class="sxs-lookup"><span data-stu-id="31248-158">Some examples of user/license types are **Business & Enterprise** and **Guest**.</span></span> <span data-ttu-id="31248-159">(Если у вас есть лицензии Education SKU, **Education - преподавателей и персонала** и **образования - учебы** доступны.) ![Элемента управления для набора пользовательской лицензии](media/enable-microsoft-teams-features-in-your-office-365-organization-image13.png)</span><span class="sxs-lookup"><span data-stu-id="31248-159">(If you have an Education SKU license, **Education - Faculty and Staff** or **Education - Student** are available.)![Control for Set user license](media/enable-microsoft-teams-features-in-your-office-365-organization-image13.png)</span></span>

<span data-ttu-id="31248-160">Вы можете иметь несколько типов лицензий из вашей организации, к примеру, так **и крупный бизнес** и **гостевой**.</span><span class="sxs-lookup"><span data-stu-id="31248-160">You can you have multiple license types within your organization, for example, both **Business & Enterprise** and **Guest**.</span></span> <span data-ttu-id="31248-161">Группами Майкрософт только может различать пользователей на основании лицензий, которые вы назначили их.</span><span class="sxs-lookup"><span data-stu-id="31248-161">Microsoft Teams can only differentiate users based on the licenses you've assigned them.</span></span> <span data-ttu-id="31248-162">Можно включить или отключить параметры для этих пользователей в **группы и каналы**, **звонков и собраний**и **системы обмена сообщениями**.</span><span class="sxs-lookup"><span data-stu-id="31248-162">You can turn on or turn off options for these users in **Teams and channels**, **Calls and meetings**, and **Messaging**.</span></span> <span data-ttu-id="31248-163">Если вы используете только один лицензию, рассмотрите возможность параметры как параметры на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="31248-163">If you use only one license type, consider the settings here as tenant-wide settings.</span></span>
> [!NOTE]
> <span data-ttu-id="31248-164">Для получения дополнительных сведений о доступ в качестве гостя видеть [Включение и отключение гостевой доступ к группами Майкрософт](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="31248-164">For more details about guest access, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

<a name="teams-and-channels"></a><span data-ttu-id="31248-165">Команды и каналы</span><span class="sxs-lookup"><span data-stu-id="31248-165">Teams and channels</span></span>
------------------

<span data-ttu-id="31248-166">Команда предназначена для объединения группы людей, которые тесно сотрудничают друг с другом для выполнения поставленных задач.</span><span class="sxs-lookup"><span data-stu-id="31248-166">A team is designed to bring together a group of people who work closely to get things done.</span></span> <span data-ttu-id="31248-167">Команды могут динамически формироваться под конкретные проекты (например, выпуск продукта на рынок или организация цифрового конференц-зала).</span><span class="sxs-lookup"><span data-stu-id="31248-167">Teams can be dynamic for project-based work (for example, launching a product or creating a digital war room).</span></span> <span data-ttu-id="31248-168">Кроме того, команды могут быть оперативными для отражения внутренней структуры организации.</span><span class="sxs-lookup"><span data-stu-id="31248-168">Or, teams can be ongoing, to reflect the internal structure of your organization.</span></span>

<span data-ttu-id="31248-169">Клиент Office 365 сейчас может иметь максимум 500 000 команд.</span><span class="sxs-lookup"><span data-stu-id="31248-169">The maximum number of teams that an Office 365 tenant can have is currently 500,000.</span></span> <span data-ttu-id="31248-170">Глобальный администратор может создать любое число команд.</span><span class="sxs-lookup"><span data-stu-id="31248-170">A global admin can create an unlimited number of teams.</span></span> <span data-ttu-id="31248-171">Пользователь может создать 250 команд.</span><span class="sxs-lookup"><span data-stu-id="31248-171">A user can create 250 teams.</span></span> <span data-ttu-id="31248-172">Владелец команды может добавить в нее 2500 участников.</span><span class="sxs-lookup"><span data-stu-id="31248-172">A team owner can add 2500 members to a team.</span></span>

<span data-ttu-id="31248-173">Будучи администратором, вы можете управлять владельцами и участниками команд с помощью панели мониторинга "Группы" в Центре администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="31248-173">As an admin, you can manage team owners and members by using the Groups dashboard in the Office 365 admin center.</span></span> <span data-ttu-id="31248-174">Чтобы получить дополнительные сведения, щелкните **Use the Groups dashboard in the Office 365 admin center to manage Microsoft Teams** (Использовать панель мониторинга "Группы" в Центре администрирования Office 365 для управления командами) в разделе **Teams and channels** (Команды и каналы).</span><span class="sxs-lookup"><span data-stu-id="31248-174">To learn more, click **Use the Groups dashboard in the Office 365 admin center to manage teams** under **Teams and channels**.</span></span>

<span data-ttu-id="31248-175">Вы можете контролировать, кто из пользователей организации может создавать команды в Teams.</span><span class="sxs-lookup"><span data-stu-id="31248-175">You can control which users in your organization can create teams in Teams.</span></span> <span data-ttu-id="31248-176">Для Teams действуют те же параметры создания, что заданы в группах Office 365.</span><span class="sxs-lookup"><span data-stu-id="31248-176">The same creation settings defined by Office 365 groups apply to Teams.</span></span> <span data-ttu-id="31248-177">Дополнительные сведения об управлении группами Office 365 см. в статьях [Создание групп Office 365](https://support.office.com/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) и [Управление правами на создание групп Office 365](https://support.office.com/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="31248-177">For more information about managing Office 365 groups, see [Create Office 365 groups](https://support.office.com/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) and [Control who can create Office 365 Groups](https://support.office.com/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

> [!NOTE]
> <span data-ttu-id="31248-178">Вы не можете создавать команды из панели мониторинга "Группы".</span><span class="sxs-lookup"><span data-stu-id="31248-178">You can't create teams from the Groups dashboard.</span></span> <span data-ttu-id="31248-179">Для этого нужно использовать классический или веб-клиент Teams.</span><span class="sxs-lookup"><span data-stu-id="31248-179">Teams must be created by using the Teams desktop client or web app.</span></span>

<span data-ttu-id="31248-180">По умолчанию создать команду или группу может любой пользователь.</span><span class="sxs-lookup"><span data-stu-id="31248-180">By default, every user can create a team or group.</span></span> <span data-ttu-id="31248-181">Выберите **Команды** в левой части классического или веб-клиента Teams, а затем внизу клиента под списком команд выберите **Create and join team** (Создать команду и присоединиться к ней).</span><span class="sxs-lookup"><span data-stu-id="31248-181">Choose **Teams** on the left side in the Teams client (desktop client or web app), then choose **Create and join team** at the bottom of the client, below the team list.</span></span>

![Снимок экрана с разделом параметров пользователей по лицензии.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

<span data-ttu-id="31248-183">Каналы являются подкатегориями команд.</span><span class="sxs-lookup"><span data-stu-id="31248-183">Channels are subcategories of teams.</span></span> <span data-ttu-id="31248-184">Любой участник команды может добавить канал и участвовать в беседах канала.</span><span class="sxs-lookup"><span data-stu-id="31248-184">Anyone on the team can add a channel and participate in the conversations in a channel.</span></span> <span data-ttu-id="31248-185">Канал можно создать для действия или для отдела.</span><span class="sxs-lookup"><span data-stu-id="31248-185">You might create a channel for an activity or for a department.</span></span> <span data-ttu-id="31248-186">Беседы, файлы и вики-страницы относятся к конкретному каналу, но просматривать их могут все участники команды.</span><span class="sxs-lookup"><span data-stu-id="31248-186">Conversations, files, and wikis are specific to each channel, but all members of the team can see them.</span></span>

## <a name="calls-and-meetings"></a><span data-ttu-id="31248-187">Звонки и собрания</span><span class="sxs-lookup"><span data-stu-id="31248-187">Calls and meetings</span></span>

<span data-ttu-id="31248-188">Настройте для своей организации следующие параметры **звонков и собраний**:</span><span class="sxs-lookup"><span data-stu-id="31248-188">Configure the following **Calls and meetings** settings for your organization:</span></span>

![Снимок экрана с разделом звонков и собраний.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

<span data-ttu-id="31248-190">Максимальное число людей на собрании равно 80.</span><span class="sxs-lookup"><span data-stu-id="31248-190">The maximum number of people in a meeting is 80.</span></span> <span data-ttu-id="31248-191">В приватном чате могут участвовать 20 человек, включая создавшего его пользователя.</span><span class="sxs-lookup"><span data-stu-id="31248-191">There can be 20 members in a private chat, including the user who created the chat.</span></span>

-   <span data-ttu-id="31248-192">**Allow scheduling for private meetings** (Разрешить планирование для частных собраний). Когда этот параметр включен, пользователи могут планировать частные собрания, не указанные ни в одном из каналов.</span><span class="sxs-lookup"><span data-stu-id="31248-192">**Allow scheduling for private meetings**: When turned on, users can schedule private meetings that are not listed in any channel.</span></span>

-   <span data-ttu-id="31248-193">**Allow ad-hoc channel meetup** (Разрешить незапланированные собрания на канале). Когда этот параметр включен, пользователи могут быстро начинать на канале собрания по каким-то особым или срочным задачам.</span><span class="sxs-lookup"><span data-stu-id="31248-193">**Allow ad-hoc channel meetup**: When turned on, users can quickly start a meeting for a channel that has been created for an immediate or specific purpose.</span></span>

-   <span data-ttu-id="31248-194">**Allow scheduling for channel meetings** (Разрешить планирование для собраний канала). Когда этот параметр включен, пользователи могут запланировать для канала собрание, к которому одним щелчком могут присоединиться все участники этого канала.</span><span class="sxs-lookup"><span data-stu-id="31248-194">**Allow scheduling for channel meetings**: When turned on, users can schedule a meeting for a channel that all channel members can easily join with a single click.</span></span>

-   <span data-ttu-id="31248-195">**Allow videos in meeting** (Разрешить в собраниях видео). Указывает, разрешено ли использовать видео во время собраний.</span><span class="sxs-lookup"><span data-stu-id="31248-195">**Allow videos in meetings:** Specifies whether the use of video is allowed in meetings.</span></span>

-   <span data-ttu-id="31248-196">**Allow screen sharing in meetings** (Разрешить в собраниях демонстрацию экрана). Указывает, разрешено ли использовать демонстрацию экрана во время собраний.</span><span class="sxs-lookup"><span data-stu-id="31248-196">**Allow screen sharing in meetings**: Specifies whether screen sharing is allowed in meetings.</span></span>

-   <span data-ttu-id="31248-197">**Allow private calling** (Разрешить частные звонки). Когда этот параметр включен, пользователи могут совершать частные звонки.</span><span class="sxs-lookup"><span data-stu-id="31248-197">**Allow private calling**: When turned on, users can make private calls.</span></span>

## <a name="messaging"></a><span data-ttu-id="31248-198">Обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="31248-198">Messaging</span></span> 

<span data-ttu-id="31248-199">В разделе "Обмен сообщениями" можно настроить для своей организации следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="31248-199">The Messaging section lets you configure the following settings for your organization:</span></span>

![Снимок экрана с разделом сообщений.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   <span data-ttu-id="31248-201">**Enable Giphy so users can add gifs to conversations** (Включить Giphy, чтобы пользователи могли добавлять в беседы GIF-файлы). Когда этот параметр включен, пользователи могут добавлять в беседы рисунки с анимацией.</span><span class="sxs-lookup"><span data-stu-id="31248-201">**Enable Giphy so users can add gifs to conversations**: When turned on, users can use animated pictures within the conversations.</span></span>

-   <span data-ttu-id="31248-202">**Content Rating** (Оценка содержимого). Если включены рисунки с анимацией, вы можете включить оценку содержимого, чтобы ограничить типы подобных изображений, которые разрешено отображать в беседах.</span><span class="sxs-lookup"><span data-stu-id="31248-202">**Content Rating**: When animated images are turned on, content rating can be applied to restrict the type of animated images that can be displayed in conversations.</span></span> <span data-ttu-id="31248-203">Доступны следующие варианты рейтинга контента:</span><span class="sxs-lookup"><span data-stu-id="31248-203">Available content rating options are:</span></span>

    -   <span data-ttu-id="31248-204">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="31248-204">No restriction</span></span>
    -   <span data-ttu-id="31248-205">Средний (значение по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="31248-205">Moderate (the default value)</span></span>
    -   <span data-ttu-id="31248-206">Строгий</span><span class="sxs-lookup"><span data-stu-id="31248-206">Strict</span></span>

-   <span data-ttu-id="31248-207">**Enable memes that users can edit and add to conversations** (Включить мемы, которые пользователи могут изменять и добавлять в беседы). Когда этот параметр включен, пользователи могут публиковать шутки с интернет-мемами.</span><span class="sxs-lookup"><span data-stu-id="31248-207">**Enable memes that users can edit and add to conversations**: When turned on, users can use internet memes to make humorous posts.</span></span>

-   <span data-ttu-id="31248-208">**Enable stickers that users can edit and add to conversations** (Включить стикеры, которые пользователи могут изменять и добавлять в беседы). Когда этот параметр включен, пользователи могут публиковать изображения с редактируемым текстом для привлечения внимания участников канала.</span><span class="sxs-lookup"><span data-stu-id="31248-208">**Enable stickers that users can edit and add to conversations**: When turned on, users can post images with editable text to get channel members attention.</span></span>

-   <span data-ttu-id="31248-209">**Allow owners to delete all messages** (Разрешить владельцам удалять все сообщения). Когда этот параметр включен, владелец канала может удалить в нем все сообщения.</span><span class="sxs-lookup"><span data-stu-id="31248-209">**Allow owners to delete all messages**: When turned on, channel owners can remove all messages in a channel.</span></span>

-   <span data-ttu-id="31248-210">**Allow users to edit their own messages** (Разрешить пользователям редактировать свои сообщения). Когда этот параметр включен, пользователи могут редактировать свои сообщения.</span><span class="sxs-lookup"><span data-stu-id="31248-210">**Allow users to edit their own messages**: When turned on, users can edit their own messages.</span></span>

-   <span data-ttu-id="31248-211">**Allow users to delete their own messages** (Разрешить пользователям удалять свои сообщения). Когда этот параметр включен, пользователи могут удалять свои сообщения.</span><span class="sxs-lookup"><span data-stu-id="31248-211">**Allow users to delete their own messages**: When turned on, users can delete their own messages.</span></span>

-   <span data-ttu-id="31248-212">**Allow users to chat privately** (Разрешить пользователям приватный чат). Когда этот параметр включен, пользователи могут общаться в приватном чате, видимом только его участникам, а не всем членам команды.</span><span class="sxs-lookup"><span data-stu-id="31248-212">**Allow users to chat privately**: When turned on, users can engage in private chats that are visible only to the people in the chat, instead of everyone on the team.</span></span>


| |  |  |
|---------|---------|---------|
|![Значок для точки принятия решений.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |<span data-ttu-id="31248-214">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="31248-214">Decision Point</span></span>         |<span data-ttu-id="31248-215">Какие параметры Microsoft Teams включит ваша организация?</span><span class="sxs-lookup"><span data-stu-id="31248-215">What settings for Microsoft Teams will your organization enable?</span></span>         |
|![Значок дальнейших действий.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |<span data-ttu-id="31248-217">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="31248-217">Next Steps</span></span>        |<span data-ttu-id="31248-218">Занесите эти решения в таблицу в статье [Назначение ролей и разрешений в Microsoft Teams](assign-roles-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="31248-218">Document these decisions in the table in [Assign roles and permissions in Microsoft Teams](assign-roles-permissions.md).</span></span>         |

