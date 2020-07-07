---
title: Включение и отключение гостевого доступа для Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Узнайте, как включить или отключить функцию гостевой доступа в Microsoft Teams в качестве администратора Office 365.
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 297a101389de2e1609697ffa2c30a2a8b7a84080
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2020
ms.locfileid: "45042781"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="2d7c3-103">Включение и отключение гостевого доступа для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2d7c3-103">Turn on or turn off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="2d7c3-104">По умолчанию гостевой доступ отключен.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-104">By default, guest access is turned off.</span></span> <span data-ttu-id="2d7c3-105">Как администратор Microsoft 365 или Office 365 вы должны включить гостевой доступ для Teams, прежде чем администратор или владелец группы смогут добавить гостей.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-105">As the Microsoft 365 or Office 365 admin, you must turn on guest access for Teams before the admin or team owners can add guests.</span></span> <span data-ttu-id="2d7c3-106">Чтобы включить гостевой доступ, используйте [Контрольный список гостевой доступа](guest-access-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="2d7c3-106">To turn on guest access, use the [Guest access checklist](guest-access-checklist.md).</span></span> 

<span data-ttu-id="2d7c3-107">После включения гостевого доступа может пройти несколько часов, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-107">After you turn on guest access, it may take a few hours for the changes to take effect.</span></span> <span data-ttu-id="2d7c3-108">Если пользователь попытается добавить в группу гостя сообщение "обратитесь к своему администратору", возможно, что гостевой доступ не включен или параметры еще не вступают в силу.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-108">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d7c3-109">Включение гостевого доступа зависит от параметров в Azure Active Directory, Microsoft 365 или Office 365, SharePoint Online и Teams.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-109">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365 or Office 365, SharePoint Online, and Teams.</span></span> <span data-ttu-id="2d7c3-110">Дополнительные сведения можно найти [в разделе Авторизация гостевой доступа в Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="2d7c3-110">For more information, see [Authorize guest access in Teams](Teams-dependencies.md).</span></span>



## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="2d7c3-111">Настройка гостевого доступа в центре администрирования Teams</span><span class="sxs-lookup"><span data-stu-id="2d7c3-111">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="2d7c3-112">Войдите в Центр администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-112">Sign in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="2d7c3-113">Выберите **Параметры на уровне организации** > **Гостевой доступ**.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="2d7c3-114">Установите параметр **Разрешить гостевой доступ в Microsoft Teams** **в.**</span><span class="sxs-lookup"><span data-stu-id="2d7c3-114">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="2d7c3-115">Переключатель "Разрешить гостевой доступ в Teams", установленный в положение "Вкл"</span><span class="sxs-lookup"><span data-stu-id="2d7c3-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="2d7c3-116">В разделе **звонки**, **собрания**и **Обмен сообщениями**в зависимости от того, что вы хотите разрешить для гостевых пользователей, установите переключатель **включить** или **выключить** для каждой возможности.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-116">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="2d7c3-117">**Приватные звонки**. **Включите** этот параметр, чтобы разрешить гостям одноранговые звонки.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="2d7c3-118">**Разрешить видео по IP**. **Включите** этот параметр, чтобы разрешить гостям использовать видео в своих звонках и собраниях.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="2d7c3-119">**Режим демонстрации экрана**. Этот параметр управляет возможностью демонстрации экрана для гостевых пользователей.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
          - <span data-ttu-id="2d7c3-120">Присвойте ему значение **Отключено**, чтобы запретить гостям демонстрировать свои экраны в Teams.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
          - <span data-ttu-id="2d7c3-121">Присвойте ему значение **Одно приложение**, чтобы разрешить демонстрацию отдельных приложений.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
          - <span data-ttu-id="2d7c3-122">Присвойте ему значение **Весь экран**, чтобы разрешить полную демонстрацию экрана.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="2d7c3-123">**Разрешить функцию "Начать собрание"**. **Включите** этот параметр, чтобы разрешить гостям использовать функцию "Начать собрание" в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="2d7c3-124">**Редактирование отправленных сообщений**. **Включите** этот параметр, чтобы разрешить гостям редактировать ранее отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="2d7c3-125">**Удаление отправленных сообщений гостями**. **Включите** этот параметр, чтобы разрешить гостям удалять ранее отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="2d7c3-126">**Чат**. **Включите** этот параметр, чтобы предоставить гостям возможность использовать чат в Teams.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="2d7c3-127">**Использование Giphy в беседах**. **Включите** этот параметр, чтобы разрешить гостям использовать Giphy в беседах.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="2d7c3-128">Giphy — это сетевая база данных и поисковая система, позволяющая пользователям искать и обмениваться анимированными GIF-файлами.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="2d7c3-129">Каждому Giphy присваивается рейтинг контента.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-129">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="2d7c3-130">**Рейтинг контента Giphy**. Выберите рейтинг из раскрывающегося списка:</span><span class="sxs-lookup"><span data-stu-id="2d7c3-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="2d7c3-131">**Разрешить весь контент**. Гости смогут вставлять все Giphy в беседы, независимо от рейтинга контента.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="2d7c3-132">**Умеренно**. Гости смогут вставлять Giphy в беседы, при этом будет применяться умеренное ограничение в отношении контента для взрослых. </span><span class="sxs-lookup"><span data-stu-id="2d7c3-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="2d7c3-133">**Строго**. Гости смогут вставлять Giphy в беседы, но будет запрещено вставлять контент для взрослых. </span><span class="sxs-lookup"><span data-stu-id="2d7c3-133">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="2d7c3-134">**Использование мемов в беседах**. **Включите** этот параметр, чтобы разрешить гостям использовать мемы в беседах.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-134">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="2d7c3-135">**Использование стикеров в беседах**. **Включите** этот параметр, чтобы разрешить гостям использовать стикеры в беседах.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 

5. <span data-ttu-id="2d7c3-136">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2d7c3-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="2d7c3-137">Включение и отключение гостевого доступа с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d7c3-137">Use PowerShell to turn guest access on or off</span></span>

<span data-ttu-id="2d7c3-138">Чтение [Использование PowerShell для включения и отключения гостевого доступа](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)</span><span class="sxs-lookup"><span data-stu-id="2d7c3-138">Read [Use PowerShell to turn guest access on or off](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)</span></span>


## <a name="video-adding-guests-in-teams"></a><span data-ttu-id="2d7c3-139">Видео: Добавление гостей в Teams</span><span class="sxs-lookup"><span data-stu-id="2d7c3-139">Video: Adding guests in Teams</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="2d7c3-140">Добавление гостей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2d7c3-140">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 


## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="2d7c3-141">Сравнение внешнего (федерация) и гостевого доступа</span><span class="sxs-lookup"><span data-stu-id="2d7c3-141">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]