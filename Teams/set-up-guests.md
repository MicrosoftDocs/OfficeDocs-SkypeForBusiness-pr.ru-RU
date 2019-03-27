---
title: Включение и отключение гостевого доступа для Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
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
ms.openlocfilehash: 6a4b0013e3e3ca31baea21e4e733a9606f3765c6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885285"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="2d7be-103">Включение и отключение гостевого доступа для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2d7be-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="2d7be-104">Являясь администратором Office 365, вы должны включить функцию гостевого доступа, прежде чем вы или пользователи вашей организации (в частности, владельцы команд) смогут добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="2d7be-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="2d7be-105">Параметры гостей задаются в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2d7be-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="2d7be-106">Чтобы эти изменения вступили в силу в рамках всей организации Office 365, требуется от 2 до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="2d7be-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="2d7be-107">Если появляется сообщение об «Обратитесь к администратору» при попытке добавить гостя в свои группы, вероятнее всего, что функция гостя не включена или параметры еще не эффективной.</span><span class="sxs-lookup"><span data-stu-id="2d7be-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d7be-108">Чтобы полностью включить все возможности гостевого доступа, важно понять основную зависимость между Microsoft Teams, Azure Active Directory и Office 365.</span><span class="sxs-lookup"><span data-stu-id="2d7be-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="2d7be-109">Дополнительные сведения см. в статье [Авторизация гостевого доступа в Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="2d7be-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="2d7be-110">Доступ в качестве гостя и внешнего доступа (федерации)</span><span class="sxs-lookup"><span data-stu-id="2d7be-110">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="2d7be-111">Настройка доступа в центре администрирования группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="2d7be-111">Configure guest access in the Microsoft Teams admin center</span></span>

1.  <span data-ttu-id="2d7be-112">Войдите Центр администрирования группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2d7be-112">Sign in to the Microsoft Teams admin center.</span></span>

2.  <span data-ttu-id="2d7be-113">Выберите пункт **Параметры масштабе организации** > **доступ в качестве гостя**.</span><span class="sxs-lookup"><span data-stu-id="2d7be-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="2d7be-114">Значение переключатель **Разрешить доступ гостя в группах Microsoft** **на**.</span><span class="sxs-lookup"><span data-stu-id="2d7be-114">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="2d7be-115">Разрешить переключатель доступа гостя значение на</span><span class="sxs-lookup"><span data-stu-id="2d7be-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="2d7be-116">Задайте переключение в разделе **вызов**, **собрания**и **системы обмена сообщениями** значение **включено** или **отключено**, в зависимости от функциональные возможности, которые необходимо разрешить пользователям гостевой.</span><span class="sxs-lookup"><span data-stu-id="2d7be-116">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="2d7be-117">**Выполнять вызовы частных** – включить этот параметр **на** разрешить Гости выполнять вызовы peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="2d7be-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="2d7be-118">**Разрешить IP-адрес видео** - включите этот параметр, этот параметр **на** разрешить Гости использование видео в их звонков и собрания.</span><span class="sxs-lookup"><span data-stu-id="2d7be-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="2d7be-119">**Совместное использование рабочего стола режим** — этот параметр управляет доступность общего доступа для пользователей гостевой экрана.</span><span class="sxs-lookup"><span data-stu-id="2d7be-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="2d7be-120">Включите этот параметр, чтобы **отключено** , чтобы запретить для Гости для совместного использования их экранов в группах.</span><span class="sxs-lookup"><span data-stu-id="2d7be-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="2d7be-121">Включите этот параметр, чтобы **одно приложение** , чтобы разрешить общий доступ к отдельным приложениям.</span><span class="sxs-lookup"><span data-stu-id="2d7be-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="2d7be-122">Включите этот параметр, чтобы **весь экран** , чтобы разрешить общий доступ к завершена.</span><span class="sxs-lookup"><span data-stu-id="2d7be-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="2d7be-123">**Разрешить провести собрание** — включить этот параметр **на** разрешить Гости для использования функции провести собрание в группах Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2d7be-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="2d7be-124">**Правка отправленных сообщений** — включить этот параметр **на** разрешить Гости для изменения сообщений они ранее отправленных.</span><span class="sxs-lookup"><span data-stu-id="2d7be-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="2d7be-125">**Гости могут удалять отправленных сообщений** — включить этот параметр **на** разрешить Гости для удаления сообщений они ранее отправленных.</span><span class="sxs-lookup"><span data-stu-id="2d7be-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="2d7be-126">**Чата** — включите этот параметр, этот параметр **на** предоставление guests возможность использования чата в группах.</span><span class="sxs-lookup"><span data-stu-id="2d7be-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="2d7be-127">**Используйте Giphys в беседах** – включить этот параметр **на** позволяет использовать Giphys в беседах с гостевым.</span><span class="sxs-lookup"><span data-stu-id="2d7be-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="2d7be-128">Giphy является online базы данных и модуль поиска, который позволяет пользователям выполнять поиск и совместное использование анимационной файлы в формате GIF.</span><span class="sxs-lookup"><span data-stu-id="2d7be-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="2d7be-129">Каждый Giphy назначается оценки содержимого.</span><span class="sxs-lookup"><span data-stu-id="2d7be-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="2d7be-130">**Оценки содержимого Giphy** — Выбор оценки из раскрывающегося списка:</span><span class="sxs-lookup"><span data-stu-id="2d7be-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="2d7be-131">**Разрешать все содержимое** - Гости смогут для вставки всех Giphys в беседах, вне зависимости от оценки содержимого.</span><span class="sxs-lookup"><span data-stu-id="2d7be-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="2d7be-132">**Средняя** - Гости смогут вставлять Giphys в беседах, но будет средней полномочий на содержимое для взрослых.</span><span class="sxs-lookup"><span data-stu-id="2d7be-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="2d7be-133">**Строгий** – гостевым будет иметь возможность вставить Giphys в беседах, но будет строго полномочий на их вставка содержимое для взрослых.</span><span class="sxs-lookup"><span data-stu-id="2d7be-133">**Strict** – Guests will be able to insert Giphys in chats, but will be strictly restricted from inserting adult content.</span></span>
    - <span data-ttu-id="2d7be-134">**Используйте Memes в беседах** - включите этот параметр, этот параметр **на** разрешить использование Memes в беседах с гостевым.</span><span class="sxs-lookup"><span data-stu-id="2d7be-134">**Use Memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="2d7be-135">**Использовать наклейки в беседах** – включить этот параметр **на** чтобы разрешить использование наклейки в беседах с гостевым.</span><span class="sxs-lookup"><span data-stu-id="2d7be-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="2d7be-136">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2d7be-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="2d7be-137">Чтобы включить доступ в качестве гостя или отключить с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d7be-137">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="2d7be-138">Загрузить Скайп для модуля Business Online PowerShell изhttps://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="2d7be-138">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="2d7be-139">Подключите сеанс PowerShell Скайп для бизнеса в Интернет конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2d7be-139">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="2d7be-140">Проверьте конфигурацию и, если `AllowGuestUser` — это `$False`, используйте командлет [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) Установка для `$True`.</span><span class="sxs-lookup"><span data-stu-id="2d7be-140">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

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
<span data-ttu-id="2d7be-141">Теперь можно создать гостевых пользователей в группах для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2d7be-141">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="2d7be-142">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="2d7be-142">More information</span></span>

<span data-ttu-id="2d7be-143">В следующем видео для получения дополнительных сведений о доступ в качестве гостя.</span><span class="sxs-lookup"><span data-stu-id="2d7be-143">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="2d7be-144">Добавление гостей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2d7be-144">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
