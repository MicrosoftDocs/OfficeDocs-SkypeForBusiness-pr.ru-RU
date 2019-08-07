---
title: Включение и отключение гостевого доступа к Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Включение и отключение гостевого доступа в Microsoft Teams
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240e93d5f6329090940e6bf49cb2d6a4ee46ce2f
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2019
ms.locfileid: "35221453"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="4e61f-103">Включение и отключение гостевого доступа к Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e61f-103">Turn on or turn off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="4e61f-104">Являясь администратором Office 365, вы должны включить функцию гостевого доступа, прежде чем вы или пользователи вашей организации (в частности, владельцы команд) смогут добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="4e61f-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span>

<span data-ttu-id="4e61f-105">Параметры гостей задаются в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4e61f-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="4e61f-106">Чтобы эти изменения вступили в силу в рамках всей организации Office 365, требуется от 2 до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="4e61f-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="4e61f-107">Если пользователь видит сообщение "обратитесь к администратору" при попытке добавить гостя в группу, возможно, что функция "гость" не включена или параметры еще не вступают в силу.</span><span class="sxs-lookup"><span data-stu-id="4e61f-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e61f-108">Чтобы полностью включить все возможности гостевого доступа, важно понять основную зависимость между Microsoft Teams, Azure Active Directory и Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e61f-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="4e61f-109">Дополнительные сведения см. в статье [Авторизация гостевого доступа в Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="4e61f-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="4e61f-110">Гостевой доступ и внешний доступ (Федерация)</span><span class="sxs-lookup"><span data-stu-id="4e61f-110">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="4e61f-111">Настройка гостевого доступа в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e61f-111">Configure guest access in the Microsoft Teams admin center</span></span>

1.  <span data-ttu-id="4e61f-112">Войдите в центр администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4e61f-112">Sign in to the Microsoft Teams admin center.</span></span>

2.  <span data-ttu-id="4e61f-113">Выберите **Параметры** > "**гостевой доступ**" в параметрах Организации.</span><span class="sxs-lookup"><span data-stu-id="4e61f-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="4e61f-114">Установите переключатель **Разрешить гостевой доступ в Microsoft Teams** и переключитесь на **On (вкл**.).</span><span class="sxs-lookup"><span data-stu-id="4e61f-114">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="4e61f-115">Установка переключателя "разрешить гостевой доступ"</span><span class="sxs-lookup"><span data-stu-id="4e61f-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="4e61f-116">Установите переключатель в положение **звонки**, **собрания**и **Обмен сообщениями** в \*\*\*\* зависимости от \*\*\*\* того, какие возможности вы хотите разрешить для гостевых пользователей.</span><span class="sxs-lookup"><span data-stu-id="4e61f-116">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="4e61f-117">**Делайте закрытые звонки** – включите этот \*\*\*\* параметр, чтобы разрешить гостям одноранговые звонки.</span><span class="sxs-lookup"><span data-stu-id="4e61f-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="4e61f-118">**Разрешить IP-видео** . Включите этот \*\*\*\* параметр, чтобы разрешить гостям использовать видео в своих звонках и собраниях.</span><span class="sxs-lookup"><span data-stu-id="4e61f-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="4e61f-119">**Режим демонстрации экрана** — этот параметр определяет доступность демонстрации экрана для гостевых пользователей.</span><span class="sxs-lookup"><span data-stu-id="4e61f-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="4e61f-120">Отключите этот параметр, \*\*\*\* чтобы отключить возможность общего доступа гостей к экранам в Teams.</span><span class="sxs-lookup"><span data-stu-id="4e61f-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="4e61f-121">Чтобы разрешить общий доступ к отдельным приложениям, включите этот параметр в **единое приложение** .</span><span class="sxs-lookup"><span data-stu-id="4e61f-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="4e61f-122">Включите этот параметр на **весь экран** , чтобы предоставить полный доступ к экрану.</span><span class="sxs-lookup"><span data-stu-id="4e61f-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="4e61f-123">**Разрешить собрание сейчас** – включите этот параметр \*\*\*\* , чтобы разрешить гостям использовать функцию "начать собрание" в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4e61f-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="4e61f-124">**Изменить отправленные сообщения** . Включите этот \*\*\*\* параметр, чтобы разрешить гостям редактировать сообщения, отправленные ранее.</span><span class="sxs-lookup"><span data-stu-id="4e61f-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="4e61f-125">**Гости могут удалять отправленные сообщения** – включите этот \*\*\*\* параметр, чтобы разрешить гостям удалять сообщения, которые они ранее отправили.</span><span class="sxs-lookup"><span data-stu-id="4e61f-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="4e61f-126">**Чат** : Включите этот параметр \*\*\*\* , чтобы предоставить гостям возможность использовать чат в Teams.</span><span class="sxs-lookup"><span data-stu-id="4e61f-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="4e61f-127">**Используйте giphy в беседах** – включите этот \*\*\*\* параметр, чтобы разрешить гостям использовать giphy в беседах.</span><span class="sxs-lookup"><span data-stu-id="4e61f-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="4e61f-128">GIF — это Интернет-база данных и поисковая система, с помощью которой пользователи могут искать и совместно использовать анимированные GIF-файлы.</span><span class="sxs-lookup"><span data-stu-id="4e61f-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="4e61f-129">Каждому Gifу назначается рейтинг контента.</span><span class="sxs-lookup"><span data-stu-id="4e61f-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="4e61f-130">**Оценка содержимого GIF** — выберите оценку из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="4e61f-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="4e61f-131">**Разрешить всем содержимому** – гости смогут вставлять все giphy в чате, независимо от их рейтинга.</span><span class="sxs-lookup"><span data-stu-id="4e61f-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="4e61f-132">**Умеренный** — гости смогут вставлять giphy в чате, но это будет умеренно ограничено содержимым для взрослых.</span><span class="sxs-lookup"><span data-stu-id="4e61f-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="4e61f-133">**Strict** – гости смогут вставлять giphy в беседы, но они не смогут вставить содержимое для взрослых.</span><span class="sxs-lookup"><span data-stu-id="4e61f-133">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
    - <span data-ttu-id="4e61f-134">**Используйте мемов в беседах** -включите этот \*\*\*\* параметр, чтобы разрешить гостям использовать мемов в беседах.</span><span class="sxs-lookup"><span data-stu-id="4e61f-134">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="4e61f-135">**Используйте наклейки в беседах** – включите этот \*\*\*\* параметр, чтобы разрешить гостям использовать наклейки в беседах.</span><span class="sxs-lookup"><span data-stu-id="4e61f-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="4e61f-136">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4e61f-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="4e61f-137">Включение и отключение гостевого доступа с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e61f-137">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="4e61f-138">Скачайте модуль PowerShell Skype для бизнеса Online изhttps://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="4e61f-138">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="4e61f-139">Подключите сеанс PowerShell к конечной точке Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="4e61f-139">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="4e61f-140">Проверьте конфигурацию и, если `AllowGuestUser` это `$False`так, используйте командлет [Set-кстеамсклиентконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) , чтобы установить его `$True`.</span><span class="sxs-lookup"><span data-stu-id="4e61f-140">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="4e61f-141">Теперь вы можете использовать гостевых пользователей в Teams для Организации.</span><span class="sxs-lookup"><span data-stu-id="4e61f-141">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="4e61f-142">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="4e61f-142">More information</span></span>

<span data-ttu-id="4e61f-143">Дополнительные сведения о гостевой службе доступа смотрите в следующем видеоролике.</span><span class="sxs-lookup"><span data-stu-id="4e61f-143">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="4e61f-144">Добавление гостей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e61f-144">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
