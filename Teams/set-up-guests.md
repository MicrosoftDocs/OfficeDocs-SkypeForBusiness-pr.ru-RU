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
ms.openlocfilehash: aaf37fda456f0e48d441e78f785a3ce450f1f42c
ms.sourcegitcommit: def4b475b785a7b963f499cf9a1044e842ff66a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2021
ms.locfileid: "49786781"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="519c1-103">Включение и отключение гостевого доступа для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="519c1-103">Turn on or turn off guest access to Microsoft Teams</span></span>

> [!Note]

> <span data-ttu-id="519c1-104">До **февраля 2021 г.** гостевой доступ по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="519c1-104">Until **February 2021**, guest access is turned off by default.</span></span> <span data-ttu-id="519c1-105">Вы должны включить гостевой доступ для Teams до того, как администраторы или владельцы группы начнут добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="519c1-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span> <span data-ttu-id="519c1-106">После того как вы включит гостевой доступ, на вступления изменений в силу может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="519c1-106">After you turn on guest access, it might take a few hours for the changes to take effect.</span></span> <span data-ttu-id="519c1-107">Если при попытке  добавить гостя в команду пользователи видят сообщение "Обратитесь к администратору", скорее всего, гостевой доступ не включен или параметры еще не эффективны.</span><span class="sxs-lookup"><span data-stu-id="519c1-107">If users see the message **Contact your administrator** when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span> 

> <span data-ttu-id="519c1-108">После **февраля 2021** г. гостевой доступ в Microsoft Teams будет по умолчанию включен для новых клиентов, & существующих клиентов, которые не настроили этот параметр.</span><span class="sxs-lookup"><span data-stu-id="519c1-108">After **February 2021**, guest access in Microsoft Teams will be turned on by default for new customers & existing customers who haven't configured this setting.</span></span> <span data-ttu-id="519c1-109">После реализации этого изменения эта возможность будет включена в вашем клиенте, если вы еще не настроили гостевой доступ в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="519c1-109">When this change is implemented, if you've not already configured guest access capability in Microsoft Teams, that capability will be enabled in your tenant.</span></span> <span data-ttu-id="519c1-110">Если вы хотите, чтобы гостевой доступ для вашей организации остался отключенным,  необходимо подтвердить отключение гостевого доступа, а не службу по **умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="519c1-110">If you want guest access to remain disabled for your organization, you'll need to confirm that the guest access setting is set to **Off** instead of **Service default**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="519c1-111">Включение гостевого доступа зависит от параметров в Azure Active Directory, Microsoft 365, SharePoint и Teams.</span><span class="sxs-lookup"><span data-stu-id="519c1-111">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="519c1-112">Дополнительные сведения приведены в статье [Совместная работа с гостями в команде](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="519c1-112">For more information, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="519c1-113">Настройка гостевого доступа в Центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="519c1-113">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="519c1-114">Войдите в [Центр администрирования Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="519c1-114">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="519c1-115">Выберите **Параметры на уровне организации** > **Гостевой доступ**.</span><span class="sxs-lookup"><span data-stu-id="519c1-115">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="519c1-116">Установите переключатель **Разрешить гостевой доступ в Microsoft Teams** в положение **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="519c1-116">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="519c1-117">Переключатель "Разрешить гостевой доступ в Teams", установленный в положение "Вкл"</span><span class="sxs-lookup"><span data-stu-id="519c1-117">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="519c1-118">Переведите переключатели в разделах **Звонки**, **Собрание** и **Сообщения** в положение **Вкл** или **Выкл** для каждой возможности, в зависимости от того, что необходимо предоставить гостевым пользователям.</span><span class="sxs-lookup"><span data-stu-id="519c1-118">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="519c1-119">**Приватные звонки**. **Включите** этот параметр, чтобы разрешить гостям одноранговые звонки.</span><span class="sxs-lookup"><span data-stu-id="519c1-119">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="519c1-120">**Разрешить видео по IP**. **Включите** этот параметр, чтобы разрешить гостям использовать видео в своих звонках и собраниях.</span><span class="sxs-lookup"><span data-stu-id="519c1-120">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="519c1-121">**Режим демонстрации экрана**. Этот параметр управляет возможностью демонстрации экрана для гостевых пользователей.</span><span class="sxs-lookup"><span data-stu-id="519c1-121">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span>
          - <span data-ttu-id="519c1-122">Присвойте ему значение **Отключено**, чтобы запретить гостям демонстрировать свои экраны в Teams.</span><span class="sxs-lookup"><span data-stu-id="519c1-122">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span>
          - <span data-ttu-id="519c1-123">Присвойте ему значение **Одно приложение**, чтобы разрешить демонстрацию отдельных приложений.</span><span class="sxs-lookup"><span data-stu-id="519c1-123">Turn this setting to **Single application** to allow sharing of individual applications.</span></span>
          - <span data-ttu-id="519c1-124">Присвойте ему значение **Весь экран**, чтобы разрешить полную демонстрацию экрана.</span><span class="sxs-lookup"><span data-stu-id="519c1-124">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="519c1-125">**Разрешить функцию "Начать собрание"**. **Включите** этот параметр, чтобы разрешить гостям использовать функцию "Начать собрание" в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="519c1-125">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="519c1-126">**Редактирование отправленных сообщений**. **Включите** этот параметр, чтобы разрешить гостям редактировать ранее отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="519c1-126">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="519c1-127">**Удаление отправленных сообщений гостями**. **Включите** этот параметр, чтобы разрешить гостям удалять ранее отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="519c1-127">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="519c1-128">**Чат**. **Включите** этот параметр, чтобы предоставить гостям возможность использовать чат в Teams.</span><span class="sxs-lookup"><span data-stu-id="519c1-128">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="519c1-129">**Использование Giphy в беседах**. **Включите** этот параметр, чтобы разрешить гостям использовать Giphy в беседах.</span><span class="sxs-lookup"><span data-stu-id="519c1-129">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="519c1-130">Giphy — это сетевая база данных и поисковая система, позволяющая пользователям искать и обмениваться анимированными GIF-файлами.</span><span class="sxs-lookup"><span data-stu-id="519c1-130">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="519c1-131">Каждому Giphy присваивается рейтинг контента.</span><span class="sxs-lookup"><span data-stu-id="519c1-131">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="519c1-132">**Рейтинг контента Giphy**. Выберите рейтинг из раскрывающегося списка:</span><span class="sxs-lookup"><span data-stu-id="519c1-132">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="519c1-133">**Разрешить весь контент**. Гости смогут вставлять все Giphy в беседы, независимо от рейтинга контента.</span><span class="sxs-lookup"><span data-stu-id="519c1-133">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="519c1-134">**Умеренно**. Гости смогут вставлять Giphy в беседы, при этом будет применяться умеренное ограничение в отношении контента для взрослых. </span><span class="sxs-lookup"><span data-stu-id="519c1-134">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="519c1-135">**"Строгий":** гости могут вставлять giphys в чаты, но их вставка будет ограничена.</span><span class="sxs-lookup"><span data-stu-id="519c1-135">**Strict** – Guests can insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="519c1-136">**Использование мемов в беседах**. **Включите** этот параметр, чтобы разрешить гостям использовать мемы в беседах.</span><span class="sxs-lookup"><span data-stu-id="519c1-136">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="519c1-137">**Использование стикеров в беседах**. **Включите** этот параметр, чтобы разрешить гостям использовать стикеры в беседах.</span><span class="sxs-lookup"><span data-stu-id="519c1-137">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span>

    ![Параметры гостевых разрешений в Teams](media/manage-guest-access-image1.png)

5. <span data-ttu-id="519c1-139">Выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="519c1-139">Select **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="519c1-140">Сравнение внешнего (федерация) и гостевого доступа</span><span class="sxs-lookup"><span data-stu-id="519c1-140">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="519c1-141">См. также</span><span class="sxs-lookup"><span data-stu-id="519c1-141">See also</span></span>

[<span data-ttu-id="519c1-142">Настройка безопасной совместной работы с помощью Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="519c1-142">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="519c1-143">Блокирование гостевых пользователей в определенных группах</span><span class="sxs-lookup"><span data-stu-id="519c1-143">Block guest users from a specific team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="519c1-144">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="519c1-144">Set-CsTeamsClientConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)
