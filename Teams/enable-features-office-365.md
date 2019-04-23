---
title: Управление параметрами Microsoft Teams в организации
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/18/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: Узнайте, как включить или отключить параметры Microsoft Teams для всей организации, включая приложения, внешний доступ, гостевой доступ, параметры Teams и настройки обновления Teams.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a61a9e31e2c1ba7c33da3a09d213e1ab0339756b
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "31959270"
---
# <a name="manage-microsoft-teams-settings-for-your-organization"></a><span data-ttu-id="ec156-103">Управление параметрами Microsoft Teams в организации</span><span class="sxs-lookup"><span data-stu-id="ec156-103">Manage Microsoft Teams settings for your organization</span></span>

<span data-ttu-id="ec156-p101">В скором времени все настройки Teams будут перенесены в новый Центр администрирования Microsoft Teams. Единственным компонентом Teams, который управляется в Центре администрирования Microsoft 365, остаются "Приложения".</span><span class="sxs-lookup"><span data-stu-id="ec156-p101">All Teams settings will soon be migrated to the new Microsoft Teams admin center. The only Teams feature that's managed in the Microsoft 365 admin center is Apps.</span></span> 

<span data-ttu-id="ec156-106">Если не указано иное, по умолчанию параметры имеют значение **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="ec156-106">Unless otherwise noted, the default value for an option is **On**.</span></span>

## <a name="tenant-wide-settings-in-the-microsoft-365-admin-center"></a><span data-ttu-id="ec156-107">Параметры на уровне клиента в Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ec156-107">You can turn off or turn on apps for Teams in Tenant-wide settings in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="ec156-108">Вы можете включать и отключать приложения для Teams в разделе **Параметры на уровне клиента** в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec156-108">You can turn off or turn on apps for Teams in **Tenant-wide settings** in the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="ec156-p102">Чтобы изменить **Параметры на уровне клиента** для Teams, войдите в Центр администрирования Microsoft 365 и выберите **Параметры** > **Службы и надстройки** > **Microsoft Teams**. Если вы вошли с правами администратора Office 365, воспользуйтесь ссылкой:</span><span class="sxs-lookup"><span data-stu-id="ec156-p102">To edit **Tenant-wide settings** for Teams, go to the Microsoft 365 admin center, choose **Settings** > **Services & add-ins** > **Microsoft Teams**. If you're signed in as an Office 365 admin, this link should take you there:</span></span> 

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a><span data-ttu-id="ec156-111">Приложения</span><span class="sxs-lookup"><span data-stu-id="ec156-111">Apps</span></span>

<span data-ttu-id="ec156-p103">Приложения — это вкладки, соединители, боты или любое их сочетание, предоставляемые Teams (основные приложения, называемые приложениями по умолчанию) или сторонними поставщиками (внешние приложения). Раздел **Приложения** позволяет вам включать и отключать приложения по умолчанию, а также настраивать параметры для управления внешними приложениями. Дополнительные сведения о развертывании приложений, ботов, соединителей и вкладок в Teams см. в статье (Приложения, боты и соединители)[deploy-apps-microsoft-teams-landing-page.md].</span><span class="sxs-lookup"><span data-stu-id="ec156-p103">Apps are tabs, connectors, bots, or any combination of these three, provided by Teams (first-party apps, also known as default apps) or by a third-party (also known as external apps). Under **Apps**, you can enable and disable default apps and configure settings to control external apps. To learn about rolling out apps, bots, connectors, and tabs in Teams, read (Apps, bots, & connectors)[deploy-apps-microsoft-teams-landing-page.md].</span></span>

#### <a name="default-apps"></a><span data-ttu-id="ec156-115">Приложения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="ec156-115">Default apps</span></span>

<span data-ttu-id="ec156-116">Это такие приложения, как "Планировщик", "Благодарность" и "Погода", предоставляемые Teams.</span><span class="sxs-lookup"><span data-stu-id="ec156-116">These apps, such as Planner, Praise, and Weather, are provided by Teams.</span></span> <span data-ttu-id="ec156-117">Чтобы включить приложение, установите для него флажок.</span><span class="sxs-lookup"><span data-stu-id="ec156-117">To turn on an app, select the check box for that app.</span></span> <span data-ttu-id="ec156-118">Снимите флажок, чтобы отключить приложение.</span><span class="sxs-lookup"><span data-stu-id="ec156-118">To turn off an app, clear the check box.</span></span> 

<span data-ttu-id="ec156-119">![Снимок экрана раздела "Приложения по умолчанию".](media/teams-manage-features-in-office365-image1.png "Снимок экрана раздела \"Приложения по умолчанию\"")</span><span class="sxs-lookup"><span data-stu-id="ec156-119">![Screen shot of the Default Apps section.](media/teams-manage-features-in-office365-image1.png "Screen shot of the Default Apps section")</span></span>

#### <a name="external-apps"></a><span data-ttu-id="ec156-120">Внешние приложения</span><span class="sxs-lookup"><span data-stu-id="ec156-120">External apps</span></span>

<span data-ttu-id="ec156-121">Эти приложения предоставляются сторонними поставщиками.</span><span class="sxs-lookup"><span data-stu-id="ec156-121">These apps are provided by third parties.</span></span> <span data-ttu-id="ec156-122">Вы можете настроить для внешних приложений следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="ec156-122">You can configure the following settings for external apps.</span></span>

<span data-ttu-id="ec156-123">![Снимок экрана раздела "Внешние приложения".](media/teams-manage-features-in-office365-image2.png "Снимок экрана раздела \"Внешние приложения\" с включаемыми и отключаемыми параметрами")</span><span class="sxs-lookup"><span data-stu-id="ec156-123">![Screenshot of the External Apps section.](media/teams-manage-features-in-office365-image2.png "Screen shot of the External Apps section, showing settings that you can turn on and off")</span></span>

- <span data-ttu-id="ec156-124">**Разрешить внешние приложения в Microsoft Teams**. При включении этого параметра пользователи могут добавлять внешние приложения, доступные вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ec156-124">**Allow external apps in Microsoft Teams**: When this setting is turned on, users can add external apps that are available to your organization.</span></span> 

- <span data-ttu-id="ec156-125">**Разрешить загрузку неопубликованных внешних приложений**. Если вы хотите включить некоторые внешние приложения и отключить другие, отключите этот параметр и в списке внешних приложений отключите приложения, к которым у пользователей не должно быть доступа.</span><span class="sxs-lookup"><span data-stu-id="ec156-125">**Allow sideloading of external apps**: If you want to turn on some external apps and turn off others , turn off this setting, and then in the list of external apps, turn off the apps that you don't want users to access.</span></span> <span data-ttu-id="ec156-126">При включении этого параметра владельцы и участники команд, которым предоставлено разрешение, могут загружать в Teams неопубликованные приложения.</span><span class="sxs-lookup"><span data-stu-id="ec156-126">When this setting is turned on, team owners and members who are granted permission can sideload apps to Teams.</span></span> 

- <span data-ttu-id="ec156-127">**Разрешать новые внешние приложения по умолчанию**. При включении этого параметра пользователи могут активировать новые приложения сразу после их добавления в каталог приложений Teams.</span><span class="sxs-lookup"><span data-stu-id="ec156-127">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="ec156-128">Если вы хотите контролировать новые приложения, отключите этот параметр.</span><span class="sxs-lookup"><span data-stu-id="ec156-128">Turn off this switch if you want to control new apps.</span></span> <span data-ttu-id="ec156-129">В этом случае не забывайте периодически просматривать новые доступные приложения, чтобы ваша организация не пропустила появление интересных программ.</span><span class="sxs-lookup"><span data-stu-id="ec156-129">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="ec156-130">Дополнительные сведения см. в статье [Параметры администратора для приложений в Teams](admin-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ec156-130">To learn more, see [Admin settings for apps in Teams](admin-settings.md).</span></span> 

## <a name="teams-org-wide-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="ec156-131">Параметры Teams на уровне организации в Центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec156-131">Teams org-wide settings in the Microsoft Teams admin center</span></span>
<span data-ttu-id="ec156-p108">Вы можете управлять параметрами пользователя для всей организации в Центре администрирования Microsoft Teams. Чтобы изменить параметры для всей организации, перейдите в Центр администрирования Microsoft Teams и выберите **Параметры для всей организации**. Вы можете настроить перечисленные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="ec156-p108">You can control organization-wide user settings in the Microsoft Teams admin center. To edit org-wide settings, go to the Microsoft Teams admin center, and then select **Org-wide settings**. You can configure the following settings.</span></span>

### <a name="external-access"></a><span data-ttu-id="ec156-135">Внешний доступ</span><span class="sxs-lookup"><span data-stu-id="ec156-135">External access</span></span>

<span data-ttu-id="ec156-p109">**Внешний доступ** позволяет пользователям Teams и Skype для бизнеса взаимодействовать с внешними контактами за пределами вашей организации. Сведения о настройке внешнего доступа см. в статье об [активации чата и взаимодействия с пользователями Teams из другой организации](let-your-teams-users-communicate-with-other-people.md).</span><span class="sxs-lookup"><span data-stu-id="ec156-p109">**External access** lets your Teams and Skype for Business users communicate with users who are outside of your organization. To configure external access, go to [Let your Teams users chat and communicate with users in another Teams organization](let-your-teams-users-communicate-with-other-people.md).</span></span>

<span data-ttu-id="ec156-138">Чтобы добавить или заблокировать домен:</span><span class="sxs-lookup"><span data-stu-id="ec156-138">To add or block a domain:</span></span>

1. <span data-ttu-id="ec156-139">Выберите пункт **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="ec156-139">Select **Add a language**.</span></span>
2. <span data-ttu-id="ec156-140">В области "Добавление домена" введите имя домена и нажмите клавишу ПРОБЕЛ, чтобы сохранить имя.</span><span class="sxs-lookup"><span data-stu-id="ec156-140">In the Add a domain pane, enter the domain name, and click the space bar to save the name.</span></span>
3. <span data-ttu-id="ec156-141">Выберите параметр **Разрешен** или **Заблокирован**.</span><span class="sxs-lookup"><span data-stu-id="ec156-141">Select **Allowed** or **Blocked**.</span></span>
4. <span data-ttu-id="ec156-142">Нажмите **Готово**, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="ec156-142">Select **Done** to save your changes.</span></span> 

### <a name="guest-access"></a><span data-ttu-id="ec156-143">Гостевой доступ</span><span class="sxs-lookup"><span data-stu-id="ec156-143">Guest access</span></span>

<span data-ttu-id="ec156-p110">**Гостевой доступ** в Microsoft Teams позволяет командам в вашей организации взаимодействовать с людьми, которые в нее не входят, предоставляя им доступ к командам и каналам. Любой пользователь с корпоративной или потребительской учетной записью Outlook, Gmail или других служб может участвовать в Teams в качестве гостя с полным доступом к командным чатам, собраниям и файлам. Дополнительные сведения см. в разделе [Гостевой доступ в Microsoft Teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="ec156-p110">**Guest access** in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels. Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files. For more information, see [Guest access in Microsoft Teams](guest-access.md).</span></span>

### <a name="teams-settings"></a><span data-ttu-id="ec156-147">Параметры Teams</span><span class="sxs-lookup"><span data-stu-id="ec156-147">Teams settings</span></span>

<span data-ttu-id="ec156-148">**Параметры Teams** позволяют интегрировать электронную почту, выбрать облачные хранилища, организовать взаимодействие со Skype для бизнеса и настроить ваши устройства.</span><span class="sxs-lookup"><span data-stu-id="ec156-148">In **Teams settings**, you can set up email integration, cloud storage options, Skype for Business interoperability, and devices.</span></span>

#### <a name="email-integration"></a><span data-ttu-id="ec156-149">Интеграция с электронной почтой</span><span class="sxs-lookup"><span data-stu-id="ec156-149">Email integration</span></span>

<span data-ttu-id="ec156-p111">Включите эту функцию, чтобы пользователи могли отправлять письма на электронный адрес канала в Teams. Это будет доступно для любого канала принадлежащей им команды. Кроме того, пользователи могут отправлять электронные письма в любые каналы команд, участникам которых разрешено добавлять соединители. Чтобы включить интеграцию электронной почты, установите для параметра **Разрешить пользователям отправлять письма на электронный адрес канала** значение **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="ec156-p111">Turn on this feature so users can send email to a channel in Teams, using the channel email address. Users can do this for any channel belonging to a team they own. Users can also send emails to any channel in a team that has adding connectors turned on for team members. To turn on email integration, make sure that **Allow users to send emails to a channel email address** is **On**.</span></span> 

#### <a name="files"></a><span data-ttu-id="ec156-154">Файлы</span><span class="sxs-lookup"><span data-stu-id="ec156-154">Files</span></span>

<span data-ttu-id="ec156-155">Здесь вы можете включать и отключать параметры обмена файлами и облачного файлового хранилища.</span><span class="sxs-lookup"><span data-stu-id="ec156-155">Here you can turn on or turn off file sharing and cloud file storage options.</span></span> 

<span data-ttu-id="ec156-p112">Пользователи могут загружать и отправлять друг другу файлы из облачных служб хранения в каналах и чатах Teams. В качестве облачного хранилища Teams сейчас поддерживает ShareFile, Dropbox, Box и Google Диск. Установите переключатель напротив поставщиков услуг облачного хранения, которые нужно использовать в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ec156-p112">Users can upload and share files from cloud storage services in Teams channels and chats. Cloud storage options in Teams currently include ShareFile, Dropbox, Box, and Google Drive. Turn on the switch for the cloud storage providers that your organization wants to use.</span></span>

#### <a name="organization"></a><span data-ttu-id="ec156-159">Организация</span><span class="sxs-lookup"><span data-stu-id="ec156-159">Organization</span></span>

<span data-ttu-id="ec156-p113">Здесь вы можете включить вкладку **Организация**, где отображается подробная организационная диаграмма компании пользователя. Дополнительные сведения см. в разделе [Использование вкладки "Организация" в Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).</span><span class="sxs-lookup"><span data-stu-id="ec156-p113">Here you can turn on the **Organization** tab, which shows the detailed organizational chart for the user’s organization. For more information, see [Use the organization tab in Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).</span></span>

#### <a name="devices"></a><span data-ttu-id="ec156-162">Устройства</span><span class="sxs-lookup"><span data-stu-id="ec156-162">Devices</span></span>

<span data-ttu-id="ec156-p114">Эти параметры управляют работой учетных записей ресурсов на устройствах Surface Hub, используемых в собраниях Microsoft Teams. Они позволяют настраивать требования проверки подлинности и ПИН-коды доступа к контенту, а также включать учетные записи ресурсов Surface Hub для отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="ec156-p114">These settings control resource account behavior for Surface Hub devices attending Microsoft Teams meetings. Use these settings to configure authentication requirements, require a content PIN, and turn on Surface Hub resource accounts to send messages.</span></span>

- <span data-ttu-id="ec156-165">**Требовать дополнительную форму проверки подлинности для доступа к содержимому собрания** — используется для выбора уровня доступа, который получат пользователи при вводе ПИН-кода контента.</span><span class="sxs-lookup"><span data-stu-id="ec156-165">**Require a secondary form of authentication to access meeting content** – Select the level of access that users have when they enter the content PIN.</span></span>
- <span data-ttu-id="ec156-p115">**Задать ПИН-код контента** — требовать, чтобы пользователи вводили этот ПИН-код, для предотвращения несанкционированного доступа к документам. Это позволяет не допускать неправомочных пользователей к участию в собраниях и просмотру их материалов.</span><span class="sxs-lookup"><span data-stu-id="ec156-p115">**Set content PIN** – Require users to enter this PIN to prevent unauthorized access to documents. This prevents an unauthorized user from joining upcoming meetings and browsing attachments.</span></span>
- <span data-ttu-id="ec156-168">**Разрешить учетным записям ресурсов отправлять сообщения** — установите для этого параметра значение **Вкл**, чтобы разрешить отправку сообщений из учетной записи ресурса Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ec156-168">**Resource accounts can send messages** – Turn this setting **On** to allow messages to be sent from the Surface Hub resource account.</span></span>

#### <a name="search-by-name"></a><span data-ttu-id="ec156-169">Поиск по имени</span><span class="sxs-lookup"><span data-stu-id="ec156-169">Search by name</span></span>

<span data-ttu-id="ec156-p116">Microsoft Teams позволяет организациям назначать политику адресных книг Exchange для поиска только в определенных областях каталога: таким образом они могут задавать пользователям внутри компании виртуальные границы для поиска и взаимодействия друг с другом. Поиск в области каталога будет целесообразен, к примеру, в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="ec156-p116">Microsoft Teams scoped directory search uses Exchange address book policy (APB) to allow organizations to create virtual boundaries that control how users can find and communicate with other users in their organization. You might want to use a scoped directory search in situations like these:</span></span>

- <span data-ttu-id="ec156-172">В рамках клиента организации существует множество компаний, которые должны быть независимы друг от друга.</span><span class="sxs-lookup"><span data-stu-id="ec156-172">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="ec156-173">В учебном заведении требуется ограничить возможности общения преподавателей с учащимися в чатах.</span><span class="sxs-lookup"><span data-stu-id="ec156-173">Your school wants to limit chats between faculty and students.</span></span> 

<span data-ttu-id="ec156-174">Установите параметр в значение **Вкл**, чтобы активировать функции поиска в области каталога.</span><span class="sxs-lookup"><span data-stu-id="ec156-174">Switch this setting **On** to turn on scoped directory searches.</span></span>

### <a name="teams-upgrade"></a><span data-ttu-id="ec156-175">Переход на Teams</span><span class="sxs-lookup"><span data-stu-id="ec156-175">Teams upgrade</span></span>

<span data-ttu-id="ec156-176">Эти параметры можно использовать для настройки перехода пользователей со Skype для бизнеса на Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ec156-176">You can use these settings to configure how your users will be upgraded from Skype for Business to Microsoft Teams.</span></span> 

#### <a name="coexistence-mode"></a><span data-ttu-id="ec156-177">Режим сосуществования</span><span class="sxs-lookup"><span data-stu-id="ec156-177">Coexistence mode</span></span>
<span data-ttu-id="ec156-p117">Можно указать следующие режимы сосуществования: **Только Teams**, **Острова** (сосуществование Teams и Skype для бизнеса) или **Только Skype для бизнеса**. Выбранный режим определяет маршрутизацию входящих звонков и чатов, а также пользовательское приложение, применяемое для инициации чатов и звонков или для планирования собраний. Дополнительные сведения см. в статье о [сосуществовании и взаимодействии Microsoft Teams и Skype для бизнеса](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="ec156-p117">You can specify a coexistence mode: **Teams only**, **Islands** (Teams and Skype for Business will coexist), or **Skype for Business only**. The Coexistence mode you choose determines the routing of incoming calls and chats and the app that is used by the user to initiate chats and calls or to schedule meetings. For more information about coexistence modes, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="app-preferences"></a><span data-ttu-id="ec156-181">Настройки приложений</span><span class="sxs-lookup"><span data-stu-id="ec156-181">App preferences</span></span>

<span data-ttu-id="ec156-p118">Здесь вы можете выбрать приложение, в котором пользователи будут присоединяться к собраниям Skype для бизнеса (Skype для бизнеса или [приложение "Собрания Скайпа"](https://support.office.com/ru-RU/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Этот параметр не зависит от настройки режима сосуществования.</span><span class="sxs-lookup"><span data-stu-id="ec156-p118">Here you can choose the app that users will use to join Skype for Business meetings (Skype for Business or the [Skype Meetings App](https://support.office.com/ru-RU/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). This setting isn't dependent on the coexistence mode setting.</span></span>

## <a name="how-can-i-tell-which-features-are-available"></a><span data-ttu-id="ec156-184">Как узнать, какие функции доступны?</span><span class="sxs-lookup"><span data-stu-id="ec156-184">How can I tell which features are available?</span></span>

<span data-ttu-id="ec156-p119">Сведения о новых функциях Teams см. на странице [Стратегия развития Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams). Для получения дополнительных сведений о новых и планируемых функциях Teams см. страницу [Новые возможности](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) и [блог Tech Community, посвященный Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531).</span><span class="sxs-lookup"><span data-stu-id="ec156-p119">See the [Microsoft 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) for information about new Teams features. For more information about new and upcoming features, see the Teams [What's New](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) page and the [Tech Community Microsoft Teams blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531) for Teams.</span></span> 

## <a name="more-information"></a><span data-ttu-id="ec156-187">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ec156-187">More information</span></span>

<span data-ttu-id="ec156-188">Сведения о том, какие роли могут выполнять функции администратора, см. в статье [Управление Microsoft Teams с ролями администратора](using-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ec156-188">For information about which roles can perform admin functions, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>
