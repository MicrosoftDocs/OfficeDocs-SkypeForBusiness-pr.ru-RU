---
title: Управление параметрами Skype для бизнеса в центре администрирования Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как управлять параметрами функций Skype для бизнеса в центре администрирования Microsoft Teams.
ms.openlocfilehash: 0a74b2586fa706dc8fe9db73c58b7d938eae59ee
ms.sourcegitcommit: 54e685b07d1c23100951d46913480989f046d534
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2020
ms.locfileid: "48827763"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="9a8ca-103">Управление параметрами Skype для бизнеса в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a8ca-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="9a8ca-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="9a8ca-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="9a8ca-105">Как администратор, центр администрирования Microsoft Teams — это область, в которой вы управляете функциями Skype для бизнеса для пользователей Skype для бизнеса в Организации.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="9a8ca-106">Вы можете управлять параметрами [Организации](#manage-skype-for-business-settings-for-your-organization) на странице **Skype для бизнеса** и параметрами [отдельных пользователей](#manage-skype-for-business-settings-for-individual-users) на вкладке **Skype для бизнеса** на страницах сведений о пользователях.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="9a8ca-107">Вы увидите страницу **Skype для бизнеса** только в том случае, если режим сосуществования для вашей организации не задан **только для Teams**.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-107">You'll only see the **Skype for Business** page if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="9a8ca-108">Аналогичным образом вкладка " **Skype для бизнеса** " отображается только в том случае, если режим сосуществования пользователя не **только Teams**.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="9a8ca-109">Чтобы узнать больше о режимах сосуществования, ознакомьтесь со статьей общие сведения о [взаимодействии групп и Skype для бизнеса](teams-and-skypeforbusiness-coexistence-and-interoperability.md) и [Настройте параметры сосуществования и обновления](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="9a8ca-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9a8ca-110">Настройки Skype для бизнеса ранее находились в **устаревшем портале** в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="9a8ca-111">После выхода из устаревшего портала вы переводили параметры в эти новые места в центре администрирования для управления Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

<span data-ttu-id="9a8ca-112">Для управления функциями Skype для бизнеса в центре администрирования Microsoft Teams необходимо назначить [роль администратора Azure Active Directory](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) для администратора глобального администратора или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-112">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Microsoft Teams admin center.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="9a8ca-113">Управление параметрами Skype для бизнеса в Организации</span><span class="sxs-lookup"><span data-stu-id="9a8ca-113">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="9a8ca-114">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Параметры организации** в  >  **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-114">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="9a8ca-115">Отсюда вы можете настраивать трансляции собраний Skype, а также уведомления о присутствии и мобильное устройство для всех пользователей Skype для бизнеса в вашей организации и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-115">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="9a8ca-116">Трансляция собрания Skype</span><span class="sxs-lookup"><span data-stu-id="9a8ca-116">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="9a8ca-117"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="9a8ca-117"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="9a8ca-118">Используйте указанные ниже параметры для управления [широковещательным показом собраний Skype](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) в Организации.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-118">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Снимок экрана: параметры трансляции собраний Skype в центре администрирования":::

- <span data-ttu-id="9a8ca-120">**Трансляции собраний Skype** : Включите этот параметр, чтобы включить трансляцию собраний Skype для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-120">**Skype Meeting Broadcasts** : Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="9a8ca-121">После включения этой функции необходимо [настроить сеть для трансляции собраний Skype](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span><span class="sxs-lookup"><span data-stu-id="9a8ca-121">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="9a8ca-122">**Дополнительные** возможности: Установите этот флажок, чтобы получать более ранний доступ к новым функциям.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-122">**See preview features** : Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="9a8ca-123">**Организаторов может планировать анонимные собрания** : Включите этот параметр, если вы хотите разрешить организаторов создавать события широковещательного показа, позволяющие любому пользователю за пределами вашей организации присоединиться, не входя в Skype.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-123">**Organizers can schedule anonymous meetings** : Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="9a8ca-124">**Запись собраний по трансляции собраний Skype** : Включите этот параметр, чтобы разрешить организаторов и выступающим записывать собрания.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-124">**Record Skype Meeting Broadcast meetings** : Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="9a8ca-125">**URL-адрес поддержки службы поддержки для участников** : введите URL-адрес своей организации, который может использовать участники собрания, если им нужна помощь во время собрания.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-125">**Helpdesk support URL for attendees** : Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="9a8ca-126">Уведомления о присутствии и мобильном телефоне</span><span class="sxs-lookup"><span data-stu-id="9a8ca-126">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="9a8ca-127"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="9a8ca-127"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="9a8ca-128">Используйте указанные ниже параметры, чтобы управлять конфиденциальностью и мобильными уведомлениями о присутствии в Skype для бизнеса в Организации.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-128">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Снимок экрана: параметры присутствия в центре администрирования":::

#### <a name="presence"></a><span data-ttu-id="9a8ca-130">Присутствие</span><span class="sxs-lookup"><span data-stu-id="9a8ca-130">Presence</span></span>

<span data-ttu-id="9a8ca-131">По умолчанию пользователи Skype для бизнеса в организации могут видеть состояние присутствия (например, "доступно", "занят" или "нет на месте") других пользователей Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-131">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="9a8ca-132">Выберите один из указанных ниже вариантов, чтобы указать, кто может видеть наличие пользователей Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-132">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="9a8ca-133">**Автоматически отображать сведения о присутствии** : любой пользователь Skype для бизнеса в вашей организации, который не был добавлен в **внешний** или **заблокированный** список пользователя, может видеть его присутствие.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-133">**Automatically display presence information** : Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="9a8ca-134">**Отображать сведения о присутствии только для контактов пользователя** : любой пользователь Skype для бизнеса в списке контактов пользователя, который не добавлен в свой **внешний** или **заблокированный** список, может видеть присутствие этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-134">**Display presence information only to a user's contacts** : Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="9a8ca-135">Пользователи могут переопределить этот параметр в Skype для бизнеса, перейдя **Settings** в  >  **Tools**  >  **Параметры** средств настройки.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-135">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="9a8ca-136">Мобильные уведомления</span><span class="sxs-lookup"><span data-stu-id="9a8ca-136">Mobile notifications</span></span>

<span data-ttu-id="9a8ca-137">Вы можете указать, будут ли пользователи Skype для бизнеса Mobile получать уведомления о входящих и пропущенных мгновенных сообщениях, голосовых сообщениях и пропущенных звонках через службу push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-137">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="9a8ca-138">В зависимости от того, какие мобильные устройства используются в вашей организации, вы можете использовать **службу push-уведомлений (Майкрософт** ), **службу push-уведомлений Apple** или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-138">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service** , the **Apple Push Notification Service** , or both.</span></span>

<span data-ttu-id="9a8ca-139">Учитывайте следующее.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-139">Keep the following in mind:</span></span>

- <span data-ttu-id="9a8ca-140">Если вы отключите push-уведомления, пользователи получат все оповещения при следующем запуске Skype для бизнеса на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-140">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="9a8ca-141">По умолчанию push-уведомления включены.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-141">By default, push notifications are turned on.</span></span> <span data-ttu-id="9a8ca-142">Отдельные пользователи могут отключить их в Skype для бизнеса на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-142">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="9a8ca-143">Если вы отключите push-уведомления, пользователи не смогут снова включить их.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-143">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="9a8ca-144">Корпорация Майкрософт использует другие компании для получения уведомлений о Skype для бизнеса в реальном времени для пользователей Windows Phone, iPhone и iPad.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-144">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="9a8ca-145">Ознакомьтесь с этим заявлением [о конфиденциальности](https://go.microsoft.com/fwlink/p/?linkid=247732).</span><span class="sxs-lookup"><span data-stu-id="9a8ca-145">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="9a8ca-146">Управление параметрами Skype для бизнеса для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="9a8ca-146">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="9a8ca-147"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="9a8ca-147"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="9a8ca-148">Чтобы настроить параметры Skype для бизнеса для отдельных пользователей, в левой области навигации центра администрирования Teams перейдите в раздел **Пользователи** , щелкните отображаемое имя пользователя, чтобы открыть страницу сведений о пользователе, а затем откройте вкладку **Параметры Skype для бизнеса** . Здесь вы можете настроить внешний доступ и параметры собрания для пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-148">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users** , click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Снимок экрана: вкладка "Skype для бизнеса" на странице "сведения о пользователе"":::

### <a name="external-access-settings"></a><span data-ttu-id="9a8ca-150">Параметры внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="9a8ca-150">External access settings</span></span>

<span data-ttu-id="9a8ca-151">Вы можете включить или отключить возможность общения с пользователями за пределами Организации.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-151">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="9a8ca-152">**Внешние пользователи Skype для бизнеса** : Включите этот параметр, если вы хотите разрешить пользователю общаться с пользователями Skype для бизнеса в федеративных доменах.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-152">**External Skype for Business users** : Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="9a8ca-153">**Внешние пользователи Skype** : Включите этот параметр, если вы хотите разрешить пользователю общаться с пользователями Skype.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-153">**External Skype users** : Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="9a8ca-154">Параметры собрания</span><span class="sxs-lookup"><span data-stu-id="9a8ca-154">Meeting settings</span></span>

<span data-ttu-id="9a8ca-155">Вы можете настроить указанные ниже параметры собрания для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-155">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="9a8ca-156">**Аудио & видео** : выберите один из следующих параметров звука и видео.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-156">**Audio & Video** : Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="9a8ca-157">**Нет** : пользователь не может использовать аудио или видео.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-157">**None** : User can't use audio or video.</span></span>
    - <span data-ttu-id="9a8ca-158">**Только звук** : пользователь может использовать звук, но не видео.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-158">**Audio only** : User can use audio but not video.</span></span>
    - <span data-ttu-id="9a8ca-159">**Аудио и видео** : пользователь может использовать звук и видео.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-159">**Audio and video** : User can use audio and video.</span></span>
    - <span data-ttu-id="9a8ca-160">**Аудио-и видеофайлы (HD)** : пользователь может использовать звук и видео с высокой четкостью определения.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-160">**Audio and video (HD)** : User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="9a8ca-161">**Запись бесед & собрания** : Включите этот параметр, чтобы разрешить пользователям записывать беседы и собрания.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-161">**Record conversations & meetings** : Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="9a8ca-162">**Соответствие** : Включите этот параметр, если вы обязаны хранить данные, хранящиеся в электронном виде.</span><span class="sxs-lookup"><span data-stu-id="9a8ca-162">**Compliance** : Turn this on if you're legally required to retain electronically stored information.</span></span> 
