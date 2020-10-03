---
title: Включение и отключение гостевого доступа для Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Узнайте, как включить или отключить функцию гостевой доступа в Microsoft Teams в качестве администратора Office 365.
ms.openlocfilehash: aa4530979054efc5a1aeb2c8fe0afa622b893f9d
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346330"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="e4f4c-103">Включение и отключение гостевого доступа для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e4f4c-103">Turn on or turn off guest access to Microsoft Teams</span></span>

<span data-ttu-id="e4f4c-104">По умолчанию гостевой доступ отключен.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-104">By default, guest access is turned off.</span></span> <span data-ttu-id="e4f4c-105">Вы должны включить гостевой доступ для Teams, прежде чем администраторы или владельцы групп смогут добавить гостей.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span>

<span data-ttu-id="e4f4c-106">После включения гостевого доступа может пройти несколько часов, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-106">After you turn on guest access, it may take a few hours for the changes to take effect.</span></span> <span data-ttu-id="e4f4c-107">Если пользователь попытается добавить в группу гостя сообщение "обратитесь к своему администратору", возможно, что гостевой доступ не включен или параметры еще не вступают в силу.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4f4c-108">Включение гостевого доступа зависит от параметров в Azure Active Directory, Microsoft 365, SharePoint и Teams.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-108">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="e4f4c-109">Дополнительные сведения можно найти [в разделе совместная работа с гостями в группе](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="e4f4c-109">For more information, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="e4f4c-110">Настройка гостевого доступа в центре администрирования Teams</span><span class="sxs-lookup"><span data-stu-id="e4f4c-110">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="e4f4c-111">Войдите в [центр администрирования Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="e4f4c-111">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="e4f4c-112">Выберите **Параметры на уровне организации** > **Гостевой доступ**.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="e4f4c-113">Установите параметр **Разрешить гостевой доступ в Microsoft Teams** **в.**</span><span class="sxs-lookup"><span data-stu-id="e4f4c-113">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="e4f4c-114">Переключатель "Разрешить гостевой доступ в Teams", установленный в положение "Вкл"</span><span class="sxs-lookup"><span data-stu-id="e4f4c-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="e4f4c-115">В разделе **звонки**, **собрания**и **Обмен сообщениями**в зависимости от того, что вы хотите разрешить для гостевых пользователей, установите переключатель **включить** или **выключить** для каждой возможности.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-115">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="e4f4c-116">**Приватные звонки**. **Включите** этот параметр, чтобы разрешить гостям одноранговые звонки.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-116">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="e4f4c-117">**Разрешить видео по IP**. **Включите** этот параметр, чтобы разрешить гостям использовать видео в своих звонках и собраниях.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-117">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="e4f4c-118">**Режим демонстрации экрана**. Этот параметр управляет возможностью демонстрации экрана для гостевых пользователей.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-118">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
          - <span data-ttu-id="e4f4c-119">Присвойте ему значение **Отключено**, чтобы запретить гостям демонстрировать свои экраны в Teams.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-119">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
          - <span data-ttu-id="e4f4c-120">Присвойте ему значение **Одно приложение**, чтобы разрешить демонстрацию отдельных приложений.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-120">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
          - <span data-ttu-id="e4f4c-121">Присвойте ему значение **Весь экран**, чтобы разрешить полную демонстрацию экрана.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-121">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="e4f4c-122">**Разрешить функцию "Начать собрание"**. **Включите** этот параметр, чтобы разрешить гостям использовать функцию "Начать собрание" в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-122">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="e4f4c-123">**Редактирование отправленных сообщений**. **Включите** этот параметр, чтобы разрешить гостям редактировать ранее отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-123">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="e4f4c-124">**Удаление отправленных сообщений гостями**. **Включите** этот параметр, чтобы разрешить гостям удалять ранее отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-124">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="e4f4c-125">**Чат**. **Включите** этот параметр, чтобы предоставить гостям возможность использовать чат в Teams.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-125">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="e4f4c-126">**Использование Giphy в беседах**. **Включите** этот параметр, чтобы разрешить гостям использовать Giphy в беседах.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-126">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="e4f4c-127">Giphy — это сетевая база данных и поисковая система, позволяющая пользователям искать и обмениваться анимированными GIF-файлами.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-127">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="e4f4c-128">Каждому Giphy присваивается рейтинг контента.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-128">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="e4f4c-129">**Рейтинг контента Giphy**. Выберите рейтинг из раскрывающегося списка:</span><span class="sxs-lookup"><span data-stu-id="e4f4c-129">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="e4f4c-130">**Разрешить весь контент**. Гости смогут вставлять все Giphy в беседы, независимо от рейтинга контента.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-130">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="e4f4c-131">**Умеренно**. Гости смогут вставлять Giphy в беседы, при этом будет применяться умеренное ограничение в отношении контента для взрослых. </span><span class="sxs-lookup"><span data-stu-id="e4f4c-131">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="e4f4c-132">**Строго**. Гости смогут вставлять Giphy в беседы, но будет запрещено вставлять контент для взрослых. </span><span class="sxs-lookup"><span data-stu-id="e4f4c-132">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="e4f4c-133">**Использование мемов в беседах**. **Включите** этот параметр, чтобы разрешить гостям использовать мемы в беседах.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-133">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="e4f4c-134">**Использование стикеров в беседах**. **Включите** этот параметр, чтобы разрешить гостям использовать стикеры в беседах.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-134">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 

    ![Параметры разрешений гостя в Teams](media/manage-guest-access-image1.png)

5. <span data-ttu-id="e4f4c-136">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-136">Click **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="e4f4c-137">Сравнение внешнего (федерация) и гостевого доступа</span><span class="sxs-lookup"><span data-stu-id="e4f4c-137">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="e4f4c-138">См. также</span><span class="sxs-lookup"><span data-stu-id="e4f4c-138">See also</span></span>

[<span data-ttu-id="e4f4c-139">Настройка безопасной совместной работы с помощью Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e4f4c-139">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="e4f4c-140">Блокировка гостевых пользователей для определенной команды</span><span class="sxs-lookup"><span data-stu-id="e4f4c-140">Block guest users from a specific team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="e4f4c-141">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="e4f4c-141">Set-CsTeamsClientConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)