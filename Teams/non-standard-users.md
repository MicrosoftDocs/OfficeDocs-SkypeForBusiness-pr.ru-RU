---
title: Teams для нестандартных пользователей
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Узнайте, как приложения Microsoft Teams для пользователей нестандартных типов.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 23551c102ec8fc0684a979bf85717a02d82e5142
ms.sourcegitcommit: 5c68298474d1782e69bde8c0940be7150cb93f6e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096273"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="36ae2-103">Microsoft Teams для нестандартных пользователей</span><span class="sxs-lookup"><span data-stu-id="36ae2-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="36ae2-104">В этой статье описано поведение приложений в Teams, когда гостевых, внешних (федеранных) и анонимных пользователей присутствуют в Teams контексте.</span><span class="sxs-lookup"><span data-stu-id="36ae2-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="36ae2-105">Гость **— это** человек, который не является сотрудником, студентом или сотрудником вашей организации.</span><span class="sxs-lookup"><span data-stu-id="36ae2-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="36ae2-106">У него нет учебной или рабочей учетной записи, предоставленной вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="36ae2-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="36ae2-107">Внешний **(федераированный) пользователь** принадлежит к другому домену и не имеет доступа к командам или ресурсам группы вашей организации.</span><span class="sxs-lookup"><span data-stu-id="36ae2-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

  > [!Note]
  > <span data-ttu-id="36ae2-108">Более подробное сравнение гостевых и внешних пользователей см. в описании общения [с пользователями из других организаций.](./communicate-with-users-from-other-organizations.md)</span><span class="sxs-lookup"><span data-stu-id="36ae2-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="36ae2-109">Анонимный **пользователь** — это понятие Teams собраний, на которых пользователь присоединился к собранию по ссылке.</span><span class="sxs-lookup"><span data-stu-id="36ae2-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="36ae2-110">Пользователь не вошел в систему со своей учетной записью Майкрософт или организации.</span><span class="sxs-lookup"><span data-stu-id="36ae2-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-users"></a><span data-ttu-id="36ae2-111">Гостевые пользователи</span><span class="sxs-lookup"><span data-stu-id="36ae2-111">Guest users</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="36ae2-112">Установка, обновление и удаление для гостевых пользователей</span><span class="sxs-lookup"><span data-stu-id="36ae2-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="36ae2-113">Гости не могут устанавливать, обновлять и удалять приложения в общем контексте, например в чате, канале или собрании, но могут использовать расширения сообщений и прямые ссылки.</span><span class="sxs-lookup"><span data-stu-id="36ae2-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting, but they can to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="36ae2-114">Гости не имеют доступа к магазину приложений Teams из Teams, но могут получить доступ к нему по прямой ссылке.</span><span class="sxs-lookup"><span data-stu-id="36ae2-114">Guests don't have access to the Teams app store from the Teams desktop application, but they can access it with a direct link.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="36ae2-115">Поведение использования и политика для гостевых пользователей</span><span class="sxs-lookup"><span data-stu-id="36ae2-115">Usage behavior and policy for guest users</span></span> 

<span data-ttu-id="36ae2-116">Гости могут использовать приложение, если приложение было установлено пользователем.</span><span class="sxs-lookup"><span data-stu-id="36ae2-116">Guests can use an app if the app was installed by a native user.</span></span>

#### <a name="bots-installed-to-a-channel"></a><span data-ttu-id="36ae2-117">Боты, установленные на канале</span><span class="sxs-lookup"><span data-stu-id="36ae2-117">Bots installed to a channel</span></span>

<span data-ttu-id="36ae2-118">Боты могут заблаговременно отправлять гостю сообщения, но гости не могут взаимодействовать с ботом.</span><span class="sxs-lookup"><span data-stu-id="36ae2-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="36ae2-119">Гости не могут отправить сообщение боту один к одному, упомянуть бота или использовать адаптивные карточки, которые общаются с ботом.</span><span class="sxs-lookup"><span data-stu-id="36ae2-119">Guests can't message the bot one-to-one, mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

#### <a name="personal-bots-installed-with-policies"></a><span data-ttu-id="36ae2-120">Личные боты, установленные с политиками</span><span class="sxs-lookup"><span data-stu-id="36ae2-120">Personal bots installed with policies</span></span>

- <span data-ttu-id="36ae2-121">Гости будут соблюдать глобальные и все политики разрешений, установленные для клиента хоста для любого приложения.</span><span class="sxs-lookup"><span data-stu-id="36ae2-121">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="36ae2-122">Если приложение заблокировано для всей организации хоста, гости также не могут использовать его.</span><span class="sxs-lookup"><span data-stu-id="36ae2-122">If an app is blocked for the whole host organization, then guests can't use the app either.</span></span>
- <span data-ttu-id="36ae2-123">Любой бот, включенный в глобальную политику настройки приложений по умолчанию, также будет установлен для гостей.</span><span class="sxs-lookup"><span data-stu-id="36ae2-123">Any bot included in the global default app setup policy will also be installed for guests.</span></span>
- <span data-ttu-id="36ae2-124">После установки бота боты могут заблаговременно общаться с гостями, а гости могут общаться с ботами.</span><span class="sxs-lookup"><span data-stu-id="36ae2-124">After a bot is installed, bots can proactively communicate with guests and guests can communicate back with bots.</span></span>
- <span data-ttu-id="36ae2-125">Вы не можете удалить гостя из глобальной политики настройки приложений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="36ae2-125">You can't remove a guest from the global default app setup policy.</span></span>
- <span data-ttu-id="36ae2-126">Чтобы предотвратить доступ гостей к ботам, вы можете создать дополнительные политики настройки приложений, назначить их внутренним пользователям и установить боты с помощью настраиваемой политики.</span><span class="sxs-lookup"><span data-stu-id="36ae2-126">To avoid guest from accessing bots, you can create more app setup policies, assign them to internal users, and install bots with the custom policies.</span></span>

## <a name="external-federated-users"></a><span data-ttu-id="36ae2-127">Внешние (федераированные) пользователи</span><span class="sxs-lookup"><span data-stu-id="36ae2-127">External (Federated) users</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="36ae2-128">Установка, обновление и удаление для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="36ae2-128">Install, update, and delete for external users</span></span>

<span data-ttu-id="36ae2-129">Внешние пользователи не могут устанавливать, обновлять и удалять приложения в любом контексте, например в личном чате, канале или на собрании.</span><span class="sxs-lookup"><span data-stu-id="36ae2-129">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="36ae2-130">У них нет доступа к Teams магазину приложений организации размещения.</span><span class="sxs-lookup"><span data-stu-id="36ae2-130">They don't have access to the Teams app store of the hosting organization.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="36ae2-131">Поведение использования и политика для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="36ae2-131">Usage behavior and policy for external users</span></span>

- <span data-ttu-id="36ae2-132">Люди из других организаций придерживаются глобальной политики организации (по умолчанию для всей организации)</span><span class="sxs-lookup"><span data-stu-id="36ae2-132">People from other organizations adhere to the hosting organization's global (org-wide default) policy</span></span>
- <span data-ttu-id="36ae2-133">Пользователи в организации размещения могут добавлять приложения в чаты собраний с пользователями из других организаций.</span><span class="sxs-lookup"><span data-stu-id="36ae2-133">Users in the hosting organization can add apps in meeting chats with people from other organizations.</span></span> <span data-ttu-id="36ae2-134">Люди из других организаций не могут добавлять приложения в чаты собраний, но могут взаимодействовать с ботами, вкладками и расширениями сообщений, добавленными в чат.</span><span class="sxs-lookup"><span data-stu-id="36ae2-134">People from other organizations cannot add apps in meeting chats but can interact with bots, tabs and message extensions once added to the chat.</span></span>
- <span data-ttu-id="36ae2-135">После установки бота в чате собрания он может заблаговременно общаться с людьми из других организаций в этом чате, а эти люди могут общаться с ботом.</span><span class="sxs-lookup"><span data-stu-id="36ae2-135">After a bot is installed in a meeting chat, it can proactively communicate with people from other organizations in that chat and those people can communicate with bot.</span></span>
- <span data-ttu-id="36ae2-136">Применяются политики данных в организации размещения, а также правила общего доступа к данным в сторонних приложениях, совместно применяемых в организации этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="36ae2-136">The data policies of the hosting organization, as well as the data sharing practices of any third-party apps shared by that user's organization, are applied.</span></span>

## <a name="anonymous-users"></a><span data-ttu-id="36ae2-137">Анонимные пользователи</span><span class="sxs-lookup"><span data-stu-id="36ae2-137">Anonymous users</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="36ae2-138">Установка, обновление и удаление для анонимных пользователей</span><span class="sxs-lookup"><span data-stu-id="36ae2-138">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="36ae2-139">Анонимные пользователи не могут устанавливать, обновлять и удалять приложения на собраниях.</span><span class="sxs-lookup"><span data-stu-id="36ae2-139">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="36ae2-140">Поведение использования и политика для анонимных пользователей</span><span class="sxs-lookup"><span data-stu-id="36ae2-140">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="36ae2-141">Анонимные пользователи не могут напрямую использовать приложения на собраниях.</span><span class="sxs-lookup"><span data-stu-id="36ae2-141">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="36ae2-142">Если в собрании есть анонимные пользователи, пользователи могут продолжать использовать приложения для собраний.</span><span class="sxs-lookup"><span data-stu-id="36ae2-142">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="36ae2-143">Если приложение отправляет в чат адаптивную карточку, анонимные пользователи могут взаимодействовать с ней.</span><span class="sxs-lookup"><span data-stu-id="36ae2-143">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span> <span data-ttu-id="36ae2-144">Дополнительные сведения можно найти в [документе Разрешить анонимным пользователям присоединяться к собраниям.](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)</span><span class="sxs-lookup"><span data-stu-id="36ae2-144">For more information, read [Allow anonymous users to join meetings](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="36ae2-145">Анонимные пользователи наследуют глобальную политику разрешений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="36ae2-145">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="36ae2-146">Они могут взаимодействовать с приложениями Teams собраниях, если приложение включено политикой разрешений на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="36ae2-146">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="36ae2-147">Анонимные пользователи могут работать только с приложениями, которые уже доступны на собрании и не могут приобрести их или управлять ими.</span><span class="sxs-lookup"><span data-stu-id="36ae2-147">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
