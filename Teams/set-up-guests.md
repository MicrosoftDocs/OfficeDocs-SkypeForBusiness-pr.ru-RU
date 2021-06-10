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
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Узнайте подробнее о том, как в качестве администратора Office 365 включить или отключить гостевой доступ в Microsoft Teams.
ms.openlocfilehash: 34759e601f5c0cd232bcd6227ff5c7d1fef1d3fe
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107405"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="bad83-103">Включение и отключение гостевого доступа для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bad83-103">Turn on or turn off guest access to Microsoft Teams</span></span>

> [!Note]

> <span data-ttu-id="bad83-104">До **февраля 2021 г.** гостевой доступ по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="bad83-104">Until **February 2021**, guest access is turned off by default.</span></span> <span data-ttu-id="bad83-105">Вы должны включить гостевой доступ для Teams до того, как администраторы или владельцы группы начнут добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="bad83-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span> <span data-ttu-id="bad83-106">После того как вы включит гостевой доступ, может потребоваться несколько часов, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="bad83-106">After you turn on guest access, it might take a few hours for the changes to take effect.</span></span> <span data-ttu-id="bad83-107">Если пользователи видят  сообщение Обратитесь к администратору при попытке добавить гостя в свою команду, вероятно, гостевой доступ не включен или параметры еще не эффективны.</span><span class="sxs-lookup"><span data-stu-id="bad83-107">If users see the message **Contact your administrator** when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> <span data-ttu-id="bad83-108">После **февраля 2021** г. гостевой доступ в Microsoft Teams будет по умолчанию включен для новых & клиентов, которые не настроили этот параметр.</span><span class="sxs-lookup"><span data-stu-id="bad83-108">After **February 2021**, guest access in Microsoft Teams will be turned on by default for new customers & existing customers who haven't configured this setting.</span></span> <span data-ttu-id="bad83-109">Если вы еще не настроили гостевой доступ в Microsoft Teams, то после реализации этого изменения она будет включена в вашем клиенте.</span><span class="sxs-lookup"><span data-stu-id="bad83-109">When this change is implemented, if you've not already configured guest access capability in Microsoft Teams, that capability will be enabled in your tenant.</span></span> <span data-ttu-id="bad83-110">Если вы хотите, чтобы гостевой доступ остался отключенным для вашей организации,  необходимо подтвердить, что параметр гостевого доступа отключен, а не служба по **умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="bad83-110">If you want guest access to remain disabled for your organization, you'll need to confirm that the guest access setting is set to **Off** instead of **Service default**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bad83-111">Включение гостевого доступа зависит от параметров в Azure Active Directory, Microsoft 365, SharePoint и Teams.</span><span class="sxs-lookup"><span data-stu-id="bad83-111">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="bad83-112">Дополнительные сведения приведены в статье [Совместная работа с гостями в команде](/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="bad83-112">For more information, see [Collaborate with guests in a team](/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="bad83-113">Настройка гостевого доступа в Центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bad83-113">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="bad83-114">Войдите в [Центр администрирования Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="bad83-114">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="bad83-115">Выберите **Параметры на уровне организации** > **Гостевой доступ**.</span><span class="sxs-lookup"><span data-stu-id="bad83-115">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="bad83-116">Установите переключатель **Разрешить гостевой доступ в Microsoft Teams** в положение **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="bad83-116">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="bad83-117">Переключатель "Разрешить гостевой доступ в Teams", установленный в положение "Вкл"</span><span class="sxs-lookup"><span data-stu-id="bad83-117">Allow guest access switch set to On</span></span> ](media/guest-access-setting.png)

4. <span data-ttu-id="bad83-118">Переведите переключатели в разделах **Звонки**, **Собрание** и **Сообщения** в положение **Вкл** или **Выкл** для каждой возможности, в зависимости от того, что необходимо предоставить гостевым пользователям.</span><span class="sxs-lookup"><span data-stu-id="bad83-118">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="bad83-119">**Приватные звонки**. **Включите** этот параметр, чтобы разрешить гостям одноранговые звонки.</span><span class="sxs-lookup"><span data-stu-id="bad83-119">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="bad83-120">**Разрешить видео по IP**. **Включите** этот параметр, чтобы разрешить гостям использовать видео в своих звонках и собраниях.</span><span class="sxs-lookup"><span data-stu-id="bad83-120">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="bad83-121">**Режим демонстрации экрана**. Этот параметр управляет возможностью демонстрации экрана для гостевых пользователей.</span><span class="sxs-lookup"><span data-stu-id="bad83-121">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span>
          - <span data-ttu-id="bad83-122">Присвойте ему значение **Отключено**, чтобы запретить гостям демонстрировать свои экраны в Teams.</span><span class="sxs-lookup"><span data-stu-id="bad83-122">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span>
          - <span data-ttu-id="bad83-123">Присвойте ему значение **Одно приложение**, чтобы разрешить демонстрацию отдельных приложений.</span><span class="sxs-lookup"><span data-stu-id="bad83-123">Turn this setting to **Single application** to allow sharing of individual applications.</span></span>
          - <span data-ttu-id="bad83-124">Присвойте ему значение **Весь экран**, чтобы разрешить полную демонстрацию экрана.</span><span class="sxs-lookup"><span data-stu-id="bad83-124">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="bad83-125">**Разрешить функцию "Начать собрание"**. **Включите** этот параметр, чтобы разрешить гостям использовать функцию "Начать собрание" в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bad83-125">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="bad83-126">**Редактирование отправленных сообщений**. **Включите** этот параметр, чтобы разрешить гостям редактировать ранее отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="bad83-126">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="bad83-127">**Удаление отправленных сообщений гостями**. **Включите** этот параметр, чтобы разрешить гостям удалять ранее отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="bad83-127">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="bad83-128">**Чат**. **Включите** этот параметр, чтобы предоставить гостям возможность использовать чат в Teams.</span><span class="sxs-lookup"><span data-stu-id="bad83-128">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="bad83-129">**Использование Giphy в беседах**. **Включите** этот параметр, чтобы разрешить гостям использовать Giphy в беседах.</span><span class="sxs-lookup"><span data-stu-id="bad83-129">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="bad83-130">Giphy — это сетевая база данных и поисковая система, позволяющая пользователям искать и обмениваться анимированными GIF-файлами.</span><span class="sxs-lookup"><span data-stu-id="bad83-130">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="bad83-131">Каждому Giphy присваивается рейтинг контента.</span><span class="sxs-lookup"><span data-stu-id="bad83-131">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="bad83-132">**Рейтинг контента Giphy**. Выберите рейтинг из раскрывающегося списка:</span><span class="sxs-lookup"><span data-stu-id="bad83-132">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="bad83-133">**Разрешить весь контент**. Гости смогут вставлять все Giphy в беседы, независимо от рейтинга контента.</span><span class="sxs-lookup"><span data-stu-id="bad83-133">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="bad83-134">**Умеренно**. Гости смогут вставлять Giphy в беседы, при этом будет применяться умеренное ограничение в отношении контента для взрослых. </span><span class="sxs-lookup"><span data-stu-id="bad83-134">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="bad83-135">**Строго:** гости могут вставлять Giphy в чаты, но не могут вставлять содержимое для взрослых.</span><span class="sxs-lookup"><span data-stu-id="bad83-135">**Strict** – Guests can insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="bad83-136">**Использование мемов в беседах**. **Включите** этот параметр, чтобы разрешить гостям использовать мемы в беседах.</span><span class="sxs-lookup"><span data-stu-id="bad83-136">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="bad83-137">**Использование стикеров в беседах**. **Включите** этот параметр, чтобы разрешить гостям использовать стикеры в беседах.</span><span class="sxs-lookup"><span data-stu-id="bad83-137">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span>

    ![Параметры гостевых разрешений в Teams](media/manage-guest-access-image1.png)

5. <span data-ttu-id="bad83-139">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="bad83-139">Select **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="bad83-140">Сравнение внешнего (федерация) и гостевого доступа</span><span class="sxs-lookup"><span data-stu-id="bad83-140">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="bad83-141">См. также</span><span class="sxs-lookup"><span data-stu-id="bad83-141">See also</span></span>

[<span data-ttu-id="bad83-142">Настройка безопасной совместной работы с помощью Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bad83-142">Set up secure collaboration with Microsoft 365</span></span>](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="bad83-143">Блокирование гостевых пользователей в определенных группах</span><span class="sxs-lookup"><span data-stu-id="bad83-143">Block guest users from a specific team</span></span>](/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="bad83-144">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="bad83-144">Set-CsTeamsClientConfiguration</span></span>](/powershell/module/skype/set-csteamsclientconfiguration)