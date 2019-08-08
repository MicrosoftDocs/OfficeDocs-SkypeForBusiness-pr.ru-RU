---
title: Управление параметрами Microsoft Teams в организации
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ritikag
search.appverid: MET150
description: Узнайте, как включить или отключить параметры Microsoft Teams для всей организации, включая приложения, внешний доступ, гостевой доступ, параметры Teams и настройки обновления Teams.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 596c3a3df6fc29706eea083859c65e1b1381e9ea
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235352"
---
# <a name="manage-microsoft-teams-settings-for-your-organization"></a><span data-ttu-id="265ab-103">Управление параметрами Microsoft Teams в организации</span><span class="sxs-lookup"><span data-stu-id="265ab-103">Manage Microsoft Teams settings for your organization</span></span>

## <a name="teams-apps-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="265ab-104">Параметры приложений Teams в Центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="265ab-104">Teams org-wide settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="265ab-105">Вы управляете приложениями для организации в разделе **Приложения Teams** в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="265ab-105">You manage apps for your organization in **Teams apps** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="265ab-106">Например, вы можете задать политики, чтобы определять, какие приложения будут доступны на уровне организации или для конкретных пользователей Teams, а также настроить Teams, закрепив наиболее важные приложения для пользователей.</span><span class="sxs-lookup"><span data-stu-id="265ab-106">For example, you can set policies to control what apps are available org-wide or to specific Teams users and you can customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="265ab-107">Дополнительные сведения см. в статье [Параметры администратора для приложений в Teams](admin-settings.md).</span><span class="sxs-lookup"><span data-stu-id="265ab-107">To learn more, see [Admin settings for apps in Teams](admin-settings.md).</span></span>  

## <a name="teams-org-wide-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="265ab-108">Параметры Teams на уровне организации в Центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="265ab-108">Teams org-wide settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="265ab-p102">Вы можете управлять параметрами пользователя для всей организации в Центре администрирования Microsoft Teams. Чтобы изменить параметры для всей организации, перейдите в Центр администрирования Microsoft Teams и выберите **Параметры для всей организации**. Вы можете настроить перечисленные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="265ab-p102">You can control organization-wide user settings in the Microsoft Teams admin center. To edit org-wide settings, go to the Microsoft Teams admin center, and then select **Org-wide settings**. You can configure the following settings.</span></span>

### <a name="external-access"></a><span data-ttu-id="265ab-112">Внешний доступ</span><span class="sxs-lookup"><span data-stu-id="265ab-112">External access</span></span>

<span data-ttu-id="265ab-113">Благодаря **внешнему доступу** пользователи Teams и Skype для бизнеса могут общаться с внешними контактами за пределами вашей организации или домена.</span><span class="sxs-lookup"><span data-stu-id="265ab-113">External access (formerly known as federation) lets your Teams and Skype for Business users communicate with users who are outside of your organization.</span></span> <span data-ttu-id="265ab-114">Сведения о настройке внешнего доступа см. в статье о [предоставлении пользователям Teams возможности общаться в чате и взаимодействовать с пользователями из другой организации](let-your-teams-users-communicate-with-other-people.md).</span><span class="sxs-lookup"><span data-stu-id="265ab-114">To turn on external access, see  [Let your Teams users chat and communicate with users in another Teams organization](let-your-teams-users-communicate-with-other-people.md).</span></span>

<span data-ttu-id="265ab-115">Чтобы добавить или заблокировать домен:</span><span class="sxs-lookup"><span data-stu-id="265ab-115">To add or block a domain:</span></span>

1. <span data-ttu-id="265ab-116">Выберите пункт **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="265ab-116">Select **Add a domain**.</span></span>
2. <span data-ttu-id="265ab-117">В области "Добавление домена" введите имя домена и нажмите клавишу ПРОБЕЛ, чтобы сохранить имя.</span><span class="sxs-lookup"><span data-stu-id="265ab-117">In the Add a domain pane, enter the domain name, and click the space bar to save the name.</span></span>
3. <span data-ttu-id="265ab-118">Выберите параметр **Разрешен** или **Заблокирован**.</span><span class="sxs-lookup"><span data-stu-id="265ab-118">Select **Allowed** or **Blocked**.</span></span>
4. <span data-ttu-id="265ab-119">Нажмите **Готово**, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="265ab-119">Select **Done** to save your changes.</span></span> 

### <a name="guest-access"></a><span data-ttu-id="265ab-120">Гостевой доступ</span><span class="sxs-lookup"><span data-stu-id="265ab-120">Guest access</span></span>

<span data-ttu-id="265ab-p104">**Гостевой доступ** в Microsoft Teams позволяет командам в вашей организации взаимодействовать с людьми, которые в нее не входят, предоставляя им доступ к командам и каналам. Любой пользователь с корпоративной или потребительской учетной записью Outlook, Gmail или других служб может участвовать в Teams в качестве гостя с полным доступом к командным чатам, собраниям и файлам. Дополнительные сведения см. в разделе [Гостевой доступ в Microsoft Teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="265ab-p104">**Guest access** in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels. Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files. For more information, see [Guest access in Microsoft Teams](guest-access.md).</span></span>

### <a name="teams-settings"></a><span data-ttu-id="265ab-124">Параметры Teams</span><span class="sxs-lookup"><span data-stu-id="265ab-124">Teams settings</span></span>

<span data-ttu-id="265ab-125">**Параметры Teams** позволяют интегрировать электронную почту, выбрать облачные хранилища, организовать взаимодействие со Skype для бизнеса и настроить ваши устройства.</span><span class="sxs-lookup"><span data-stu-id="265ab-125">In **Teams settings**, you can set up email integration, cloud storage options, Skype for Business interoperability, and devices.</span></span>

#### <a name="email-integration"></a><span data-ttu-id="265ab-126">Интеграция с электронной почтой</span><span class="sxs-lookup"><span data-stu-id="265ab-126">Email integration</span></span>

<span data-ttu-id="265ab-p105">Включите эту функцию, чтобы пользователи могли отправлять письма на электронный адрес канала в Teams. Это будет доступно для любого канала принадлежащей им команды. Кроме того, пользователи могут отправлять электронные письма в любые каналы команд, участникам которых разрешено добавлять соединители. Чтобы включить интеграцию электронной почты, установите для параметра **Разрешить пользователям отправлять письма на электронный адрес канала** значение **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="265ab-p105">Turn on this feature so users can send email to a channel in Teams, using the channel email address. Users can do this for any channel belonging to a team they own. Users can also send emails to any channel in a team that has adding connectors turned on for team members. To turn on email integration, make sure that **Allow users to send emails to a channel email address** is **On**.</span></span> 

#### <a name="files"></a><span data-ttu-id="265ab-131">Файлы</span><span class="sxs-lookup"><span data-stu-id="265ab-131">Files</span></span>

<span data-ttu-id="265ab-132">Здесь вы можете включать и отключать параметры обмена файлами и облачного файлового хранилища.</span><span class="sxs-lookup"><span data-stu-id="265ab-132">Here you can turn on or turn off file sharing and cloud file storage options.</span></span> 

<span data-ttu-id="265ab-p106">Пользователи могут загружать и отправлять друг другу файлы из облачных служб хранения в каналах и чатах Teams. В качестве облачного хранилища Teams сейчас поддерживает ShareFile, Dropbox, Box и Google Диск. Установите переключатель напротив поставщиков услуг облачного хранения, которые нужно использовать в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="265ab-p106">Users can upload and share files from cloud storage services in Teams channels and chats. Cloud storage options in Teams currently include ShareFile, Dropbox, Box, and Google Drive. Turn on the switch for the cloud storage providers that your organization wants to use.</span></span>

#### <a name="organization"></a><span data-ttu-id="265ab-136">Организация</span><span class="sxs-lookup"><span data-stu-id="265ab-136">Organization</span></span>

<span data-ttu-id="265ab-p107">Здесь вы можете включить вкладку **Организация**, где отображается подробная организационная диаграмма компании пользователя. Дополнительные сведения см. в разделе [Использование вкладки "Организация" в Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).</span><span class="sxs-lookup"><span data-stu-id="265ab-p107">Here you can turn on the **Organization** tab, which shows the detailed organizational chart for the user’s organization. For more information, see [Use the organization tab in Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).</span></span>

#### <a name="devices"></a><span data-ttu-id="265ab-139">Устройства</span><span class="sxs-lookup"><span data-stu-id="265ab-139">Devices</span></span>

<span data-ttu-id="265ab-p108">Эти параметры управляют работой учетных записей ресурсов на устройствах Surface Hub, используемых в собраниях Microsoft Teams. Они позволяют настраивать требования проверки подлинности и ПИН-коды доступа к контенту, а также включать учетные записи ресурсов Surface Hub для отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="265ab-p108">These settings control resource account behavior for Surface Hub devices attending Microsoft Teams meetings. Use these settings to configure authentication requirements, require a content PIN, and turn on Surface Hub resource accounts to send messages.</span></span>

- <span data-ttu-id="265ab-142">**Требовать дополнительную форму проверки подлинности для доступа к содержимому собрания** — используется для выбора уровня доступа, который получат пользователи при вводе ПИН-кода контента.</span><span class="sxs-lookup"><span data-stu-id="265ab-142">**Require a secondary form of authentication to access meeting content** – Select the level of access that users have when they enter the content PIN.</span></span>
- <span data-ttu-id="265ab-p109">**Задать ПИН-код контента** — требовать, чтобы пользователи вводили этот ПИН-код, для предотвращения несанкционированного доступа к документам. Это позволяет не допускать неправомочных пользователей к участию в собраниях и просмотру их материалов.</span><span class="sxs-lookup"><span data-stu-id="265ab-p109">**Set content PIN** – Require users to enter this PIN to prevent unauthorized access to documents. This prevents an unauthorized user from joining upcoming meetings and browsing attachments.</span></span>
- <span data-ttu-id="265ab-145">**Разрешить учетным записям ресурсов отправлять сообщения** — установите для этого параметра значение **Вкл**, чтобы разрешить отправку сообщений из учетной записи ресурса Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="265ab-145">**Resource accounts can send messages** – Turn this setting **On** to allow messages to be sent from the Surface Hub resource account.</span></span>

#### <a name="search-by-name"></a><span data-ttu-id="265ab-146">Поиск по имени</span><span class="sxs-lookup"><span data-stu-id="265ab-146">Search by name</span></span>

<span data-ttu-id="265ab-p110">Microsoft Teams позволяет организациям назначать политику адресных книг Exchange для поиска только в определенных областях каталога: таким образом они могут задавать пользователям внутри компании виртуальные границы для поиска и взаимодействия друг с другом. Поиск в области каталога будет целесообразен, к примеру, в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="265ab-p110">Microsoft Teams scoped directory search uses Exchange address book policy (APB) to allow organizations to create virtual boundaries that control how users can find and communicate with other users in their organization. You might want to use a scoped directory search in situations like these:</span></span>

- <span data-ttu-id="265ab-149">В рамках клиента организации существует множество компаний, которые должны быть независимы друг от друга.</span><span class="sxs-lookup"><span data-stu-id="265ab-149">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="265ab-150">В учебном заведении требуется ограничить возможности общения преподавателей с учащимися в чатах.</span><span class="sxs-lookup"><span data-stu-id="265ab-150">Your school wants to limit chats between faculty and students.</span></span> 

<span data-ttu-id="265ab-151">Установите параметр в значение **Вкл**, чтобы активировать функции поиска в области каталога.</span><span class="sxs-lookup"><span data-stu-id="265ab-151">Switch this setting **On** to turn on scoped directory searches.</span></span>

### <a name="teams-upgrade"></a><span data-ttu-id="265ab-152">Переход на Teams</span><span class="sxs-lookup"><span data-stu-id="265ab-152">Teams upgrade</span></span>

<span data-ttu-id="265ab-153">Эти параметры можно использовать для настройки перехода пользователей со Skype для бизнеса на Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="265ab-153">You can use these settings to configure how your users will be upgraded from Skype for Business to Microsoft Teams.</span></span> 

#### <a name="coexistence-mode"></a><span data-ttu-id="265ab-154">Режим сосуществования</span><span class="sxs-lookup"><span data-stu-id="265ab-154">Coexistence mode</span></span>
<span data-ttu-id="265ab-155">Можно указать следующий режим сосуществования: **Только Teams**, **Острова** (сосуществование Teams и Skype для бизнеса) или **Только Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="265ab-155">You can specify a coexistence mode: **Teams only**, **Islands** (Teams and Skype for Business will coexist), or **Skype for Business only**.</span></span> <span data-ttu-id="265ab-156">Выбранный режим определяет маршрутизацию входящих звонков и чатов, а также приложение, используемое для инициации чатов и звонков или для планирования собраний.</span><span class="sxs-lookup"><span data-stu-id="265ab-156">The coexistence mode you choose determines the routing of incoming calls and chats and the app that is used by the user to initiate chats and calls or to schedule meetings.</span></span> <span data-ttu-id="265ab-157">Дополнительные сведения см. в статье о [сосуществовании и взаимодействии Microsoft Teams и Skype для бизнеса](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="265ab-157">For more information about coexistence modes, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="app-preferences"></a><span data-ttu-id="265ab-158">Настройки приложений</span><span class="sxs-lookup"><span data-stu-id="265ab-158">App preferences</span></span>

<span data-ttu-id="265ab-p112">Здесь вы можете выбрать приложение, в котором пользователи будут присоединяться к собраниям Skype для бизнеса (Skype для бизнеса или [приложение "Собрания Скайпа"](https://support.office.com/ru-RU/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Этот параметр не зависит от настройки режима сосуществования.</span><span class="sxs-lookup"><span data-stu-id="265ab-p112">Here you can choose the app that users will use to join Skype for Business meetings (Skype for Business or the [Skype Meetings App](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). This setting isn't dependent on the coexistence mode setting.</span></span>

## <a name="how-can-i-tell-which-features-are-available"></a><span data-ttu-id="265ab-161">Как узнать, какие функции доступны?</span><span class="sxs-lookup"><span data-stu-id="265ab-161">How can I tell which features are available?</span></span>

<span data-ttu-id="265ab-p113">Сведения о новых функциях Teams см. на странице [Стратегия развития Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams). Для получения дополнительных сведений о новых и планируемых функциях Teams см. страницу [Новые возможности](https://support.office.com/ru-RU/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) и [блог Tech Community, посвященный Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531).</span><span class="sxs-lookup"><span data-stu-id="265ab-p113">See the [Microsoft 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) for information about new Teams features. For more information about new and upcoming features, see the Teams [What's New](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) page and the [Tech Community Microsoft Teams blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531) for Teams.</span></span> 

## <a name="more-information"></a><span data-ttu-id="265ab-164">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="265ab-164">More information</span></span>

<span data-ttu-id="265ab-165">Сведения о том, какие роли могут выполнять функции администратора, см. в статье [Управление Microsoft Teams с ролями администратора](using-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="265ab-165">For information about which roles can perform admin functions, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>
