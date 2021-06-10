---
title: Управление Skype для бизнеса параметров в центре Microsoft Teams администрирования
author: cichur
ms.author: v-cichur
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
description: Узнайте, как управлять настройками Skype для бизнеса в Центре Microsoft Teams администрирования.
ms.openlocfilehash: 6e1052b4f4a0e85d4d18123b3c0a0f051f6065f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117007"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="9db98-103">Управление Skype для бизнеса параметров в центре Microsoft Teams администрирования</span><span class="sxs-lookup"><span data-stu-id="9db98-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="9db98-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="9db98-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="9db98-105">В Центре администрирования Microsoft Teams управление функциями Skype для бизнеса пользователями Skype для бизнеса организации.</span><span class="sxs-lookup"><span data-stu-id="9db98-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="9db98-106">Вы можете управлять [](#manage-skype-for-business-settings-for-your-organization) настройками для своей организации на странице [](#manage-skype-for-business-settings-for-individual-users) Skype для бизнеса **и**  настройками для отдельных пользователей на вкладке Skype для бизнеса страниц с подробными пользователями.</span><span class="sxs-lookup"><span data-stu-id="9db98-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="9db98-107">Вы увидите страницу Skype для бизнеса **только** в том случае, если в режиме совместной работы организации установлен не только Teams **.**</span><span class="sxs-lookup"><span data-stu-id="9db98-107">You'll only see the **Skype for Business** page if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="9db98-108">Кроме того, вкладка Skype для бизнеса  для пользователя будет видна только в том случае, если режим совместной работы пользователя **Teams.**</span><span class="sxs-lookup"><span data-stu-id="9db98-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="9db98-109">Дополнительные информацию о режимах сосуществования см. в Teams и [Skype для бизнеса"](teams-and-skypeforbusiness-coexistence-and-interoperability.md) и "Настройка параметров сосуществования и [обновления".](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9db98-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9db98-110">Skype для бизнеса ранее находились на портале **устаревших Microsoft Teams** администрирования.</span><span class="sxs-lookup"><span data-stu-id="9db98-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="9db98-111">После того как устаревший портал был перенесен, мы перенаправлены в эти новые расположения в Центре администрирования Teams для Skype для бизнеса управления.</span><span class="sxs-lookup"><span data-stu-id="9db98-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

<span data-ttu-id="9db98-112">Чтобы управлять функциями Skype для бизнеса Microsoft Teams в Центре администрирования azure [AD,](/azure/active-directory/roles/permissions-reference) вам должна быть назначена роль глобального администратора или администратора Skype для бизнеса администратора.</span><span class="sxs-lookup"><span data-stu-id="9db98-112">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Microsoft Teams admin center.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="9db98-113">Управление Skype для бизнеса параметров организации</span><span class="sxs-lookup"><span data-stu-id="9db98-113">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="9db98-114">В левой области навигации Центра Microsoft Teams администрирования перейдите в параметры для  >  **всей организации Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="9db98-114">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="9db98-115">Здесь вы можете настроить и управлять Skype трансляцией собраний, конфиденциальностью присутствия и уведомлениями о присутствии для всех Skype для бизнеса пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="9db98-115">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="9db98-116">Трансляция собрания Skype</span><span class="sxs-lookup"><span data-stu-id="9db98-116">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="9db98-117"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="9db98-117"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="9db98-118">Используйте следующие параметры для управления Skype [трансляцией собраний](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) в организации.</span><span class="sxs-lookup"><span data-stu-id="9db98-118">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Снимок экрана: Skype параметров трансляции собраний в Центре администрирования":::

- <span data-ttu-id="9db98-120">**Skype трансляции собраний:** включите эту возможность, чтобы Skype трансляцию собраний для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9db98-120">**Skype Meeting Broadcasts**: Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="9db98-121">После того как вы введете эту функцию, необходимо настроить сеть для [Skype трансляции собраний.](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)</span><span class="sxs-lookup"><span data-stu-id="9db98-121">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="9db98-122">**См. функции предварительного просмотра.** Включив эту функцию, чтобы получить ранний доступ к новым функциям.</span><span class="sxs-lookup"><span data-stu-id="9db98-122">**See preview features**: Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="9db98-123">**Организаторы могут планировать** анонимные собрания. Включите эту возможность, если вы хотите разрешить организаторам создавать трансляции, позволяющие всем пользователям за пределами организации присоединяться к собраниям без необходимости вступать в собрание.</span><span class="sxs-lookup"><span data-stu-id="9db98-123">**Organizers can schedule anonymous meetings**: Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="9db98-124">**Запись Skype собраний:** включив эту возможность, чтобы организаторы и Skype могли записывать собрания.</span><span class="sxs-lookup"><span data-stu-id="9db98-124">**Record Skype Meeting Broadcast meetings**: Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="9db98-125">**URL-адрес** службы поддержки службы технической поддержки для участников. Введите URL-адрес службы поддержки вашей организации, который участники могут использовать, если им нужна помощь во время собрания.</span><span class="sxs-lookup"><span data-stu-id="9db98-125">**Helpdesk support URL for attendees**: Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="9db98-126">Уведомления о присутствии и мобильные устройства</span><span class="sxs-lookup"><span data-stu-id="9db98-126">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="9db98-127"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="9db98-127"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="9db98-128">Используйте следующие параметры для управления конфиденциальностью Skype для бизнеса присутствия и мобильными уведомлениями в организации.</span><span class="sxs-lookup"><span data-stu-id="9db98-128">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Снимок экрана: параметры присутствия в Центре администрирования":::

#### <a name="presence"></a><span data-ttu-id="9db98-130">Присутствие</span><span class="sxs-lookup"><span data-stu-id="9db98-130">Presence</span></span>

<span data-ttu-id="9db98-131">По умолчанию Skype для бизнеса могут видеть состояние присутствия (например, "В сети", "Занят" или "Нет на Skype для бизнеса").</span><span class="sxs-lookup"><span data-stu-id="9db98-131">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="9db98-132">Выберите один из следующих вариантов, чтобы выбрать, кто может видеть Skype для бизнеса пользователей.</span><span class="sxs-lookup"><span data-stu-id="9db98-132">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="9db98-133">**Автоматическое отображение** сведений о присутствии. Сведения о присутствии могут видеть все  пользователи  Skype для бизнеса организации, которые не были добавлены в список внешних или заблокированных пользователей.</span><span class="sxs-lookup"><span data-stu-id="9db98-133">**Automatically display presence information**: Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="9db98-134">**Отображение** сведений о присутствии только для контактов пользователя: сведения о присутствии могут видеть все  пользователи  Skype для бизнеса, которые не добавлены в список внешних или заблокированных пользователей.</span><span class="sxs-lookup"><span data-stu-id="9db98-134">**Display presence information only to a user's contacts**: Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="9db98-135">Пользователи могут переопрепрестить этот параметр в Skype для бизнеса, переопределив **параметры** Параметры  >    >  **Инструменты**.</span><span class="sxs-lookup"><span data-stu-id="9db98-135">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="9db98-136">Мобильные уведомления</span><span class="sxs-lookup"><span data-stu-id="9db98-136">Mobile notifications</span></span>

<span data-ttu-id="9db98-137">Вы можете настроить, будут ли Skype для бизнеса получать оповещения о входящих и пропущенных мгновенных сообщениях, сообщениях голосовой почты и пропущенных звонках с помощью службы push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="9db98-137">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="9db98-138">В зависимости от мобильных устройств, используемых в вашей организации, вы можете использовать службу push-уведомлений **Майкрософт,** службу push-уведомлений **Apple** или обе эти службы.</span><span class="sxs-lookup"><span data-stu-id="9db98-138">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service**, the **Apple Push Notification Service**, or both.</span></span>

<span data-ttu-id="9db98-139">Учитывайте следующее.</span><span class="sxs-lookup"><span data-stu-id="9db98-139">Keep the following in mind:</span></span>

- <span data-ttu-id="9db98-140">Если вы отключите push-уведомления, пользователи получат все оповещения при следующем запуске Skype для бизнеса мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="9db98-140">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="9db98-141">По умолчанию push-уведомления включены.</span><span class="sxs-lookup"><span data-stu-id="9db98-141">By default, push notifications are turned on.</span></span> <span data-ttu-id="9db98-142">Отдельные пользователи могут отключить их в Skype для бизнеса на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="9db98-142">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="9db98-143">После отключения push-уведомлений пользователи не смогут снова включить их.</span><span class="sxs-lookup"><span data-stu-id="9db98-143">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="9db98-144">Корпорация Майкрософт использует другие компании для предоставления уведомлений Skype для бизнеса в режиме реального времени для Windows Phone, iPhone и iPad пользователей.</span><span class="sxs-lookup"><span data-stu-id="9db98-144">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="9db98-145">См. это [заявление о конфиденциальности.](https://go.microsoft.com/fwlink/p/?linkid=247732)</span><span class="sxs-lookup"><span data-stu-id="9db98-145">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="9db98-146">Управление Skype для бизнеса отдельными пользователями</span><span class="sxs-lookup"><span data-stu-id="9db98-146">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="9db98-147"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="9db98-147"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="9db98-148">Чтобы управлять Skype для бизнеса отдельными пользователями, в левой области навигации Центра администрирования Teams перейдите в меню Пользователи **,** щелкните отображаемого  имени пользователя, чтобы открыть страницу сведений о пользователе, а затем откройте вкладку Параметры Skype для бизнеса. Здесь можно настроить внешний доступ и параметры собраний для пользователя.</span><span class="sxs-lookup"><span data-stu-id="9db98-148">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users**, click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Снимок экрана: Skype для бизнеса на странице сведений о пользователе":::

### <a name="external-access-settings"></a><span data-ttu-id="9db98-150">Параметры внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="9db98-150">External access settings</span></span>

<span data-ttu-id="9db98-151">Вы можете выборочно разрешить или заблокировать возможность общения пользователя с пользователями за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9db98-151">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="9db98-152">**Внешние Skype для бизнеса** пользователей: включим эту возможность, если вы хотите разрешить пользователям общаться с Skype для бизнеса федератными доменами.</span><span class="sxs-lookup"><span data-stu-id="9db98-152">**External Skype for Business users**: Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="9db98-153">**Внешние Skype:** включим эту возможность, если вы хотите разрешить пользователям общаться с Skype пользователями.</span><span class="sxs-lookup"><span data-stu-id="9db98-153">**External Skype users**: Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="9db98-154">Параметры собрания</span><span class="sxs-lookup"><span data-stu-id="9db98-154">Meeting settings</span></span>

<span data-ttu-id="9db98-155">Вы можете настроить для пользователя следующие параметры собрания:</span><span class="sxs-lookup"><span data-stu-id="9db98-155">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="9db98-156">**Аудио & видео:** выберите один из следующих параметров звука и видео:</span><span class="sxs-lookup"><span data-stu-id="9db98-156">**Audio & Video**: Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="9db98-157">**Нет:** пользователь не может использовать звук или видео.</span><span class="sxs-lookup"><span data-stu-id="9db98-157">**None**: User can't use audio or video.</span></span>
    - <span data-ttu-id="9db98-158">**Только звук:** пользователь может использовать звук, но не видео.</span><span class="sxs-lookup"><span data-stu-id="9db98-158">**Audio only**: User can use audio but not video.</span></span>
    - <span data-ttu-id="9db98-159">**Аудио и видео.** Пользователь может использовать звук и видео.</span><span class="sxs-lookup"><span data-stu-id="9db98-159">**Audio and video**: User can use audio and video.</span></span>
    - <span data-ttu-id="9db98-160">**Аудио и видео (HD):** пользователь может использовать звук и видео высокой четкости.</span><span class="sxs-lookup"><span data-stu-id="9db98-160">**Audio and video (HD)**: User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="9db98-161">**Запись бесед & собраний:** включив эту возможность, пользователь сможет записывать беседы и собрания.</span><span class="sxs-lookup"><span data-stu-id="9db98-161">**Record conversations & meetings**: Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="9db98-162">**Соответствие** требованиям. Включите эту возможность, если вам требуется хранить в электронном виде данные, хранимые в электронном виде.</span><span class="sxs-lookup"><span data-stu-id="9db98-162">**Compliance**: Turn this on if you're legally required to retain electronically stored information.</span></span>