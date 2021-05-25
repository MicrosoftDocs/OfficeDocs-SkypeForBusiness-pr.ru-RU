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
ms.openlocfilehash: c27a73928e0740eb325c269fd5ac625fa4c43086
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628928"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="5425d-103">Microsoft Teams для нестандартных пользователей</span><span class="sxs-lookup"><span data-stu-id="5425d-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="5425d-104">В этой статье описано поведение приложений в Teams, когда гостевых, внешних (федеранных) и анонимных Teams контексте.</span><span class="sxs-lookup"><span data-stu-id="5425d-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="5425d-105">Гость **— это** человек, который не является сотрудником, студентом или сотрудником вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5425d-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="5425d-106">У него нет учебной или рабочей учетной записи, предоставленной вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="5425d-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="5425d-107">Внешний **(федераированный) пользователь** принадлежит к другому домену и не имеет доступа к командам или ресурсам группы вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5425d-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

  > [!Note]
  > <span data-ttu-id="5425d-108">Более подробное сравнение гостевых и внешних пользователей см. в описании общения [с пользователями из других организаций.](./communicate-with-users-from-other-organizations.md)</span><span class="sxs-lookup"><span data-stu-id="5425d-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="5425d-109">Анонимный **пользователь** — это понятие Teams собраний, на которых пользователь присоединился к собранию по ссылке.</span><span class="sxs-lookup"><span data-stu-id="5425d-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="5425d-110">Пользователь не вошел в систему со своей учетной записью Майкрософт или организации.</span><span class="sxs-lookup"><span data-stu-id="5425d-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-users"></a><span data-ttu-id="5425d-111">Гостевые пользователи</span><span class="sxs-lookup"><span data-stu-id="5425d-111">Guest users</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="5425d-112">Установка, обновление и удаление для гостевых пользователей</span><span class="sxs-lookup"><span data-stu-id="5425d-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="5425d-113">Гости не могут устанавливать, обновлять или удалять приложения в общем контексте, например в чате, канале или собрании, но они могут использовать расширения сообщений и прямые ссылки.</span><span class="sxs-lookup"><span data-stu-id="5425d-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting, but they can to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="5425d-114">Гости не имеют доступа к магазину приложений Teams из Teams, но могут получить доступ к нему по прямой ссылке.</span><span class="sxs-lookup"><span data-stu-id="5425d-114">Guests don't have access to the Teams app store from the Teams desktop application, but they can access it with a direct link.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="5425d-115">Поведение использования и политика для гостевых пользователей</span><span class="sxs-lookup"><span data-stu-id="5425d-115">Usage behavior and policy for guest users</span></span> 

<span data-ttu-id="5425d-116">Гости могут использовать приложение, если приложение было установлено пользователем.</span><span class="sxs-lookup"><span data-stu-id="5425d-116">Guests can use an app if the app was installed by a native user.</span></span>

#### <a name="bots-installed-to-a-channel"></a><span data-ttu-id="5425d-117">Боты, установленные на канале</span><span class="sxs-lookup"><span data-stu-id="5425d-117">Bots installed to a channel</span></span>

<span data-ttu-id="5425d-118">Боты могут заблаговременно отправлять гостю сообщения, но гости не могут взаимодействовать с ботом.</span><span class="sxs-lookup"><span data-stu-id="5425d-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="5425d-119">Гости не могут отправить сообщение боту один к одному, упомянуть бота или использовать адаптивные карточки, которые общаются с ботом.</span><span class="sxs-lookup"><span data-stu-id="5425d-119">Guests can't message the bot one-to-one, mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

#### <a name="personal-bots-installed-with-policies"></a><span data-ttu-id="5425d-120">Личные боты, установленные с политиками</span><span class="sxs-lookup"><span data-stu-id="5425d-120">Personal bots installed with policies</span></span>

- <span data-ttu-id="5425d-121">Гости будут соблюдать глобальные и все политики разрешений для клиента хоста для любого приложения.</span><span class="sxs-lookup"><span data-stu-id="5425d-121">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="5425d-122">Если приложение заблокировано для всей организации хоста, гости также не могут использовать его.</span><span class="sxs-lookup"><span data-stu-id="5425d-122">If an app is blocked for the whole host organization, then guests can't use the app either.</span></span>
- <span data-ttu-id="5425d-123">Любой бот, включенный в глобальную политику настройки приложений по умолчанию, также будет установлен для гостей.</span><span class="sxs-lookup"><span data-stu-id="5425d-123">Any bot included in the global default app setup policy will also be installed for guests.</span></span>
- <span data-ttu-id="5425d-124">После установки бота боты могут заблаговременно общаться с гостями, а гости могут общаться с ботами.</span><span class="sxs-lookup"><span data-stu-id="5425d-124">After a bot is installed, bots can proactively communicate with guests and guests can communicate back with bots.</span></span>
- <span data-ttu-id="5425d-125">Вы не можете удалить гостя из глобальной политики настройки приложений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5425d-125">You can't remove a guest from the global default app setup policy.</span></span>
- <span data-ttu-id="5425d-126">Чтобы предотвратить доступ гостей к ботам, вы можете создать дополнительные политики настройки приложений, назначить их внутренним пользователям и установить боты с помощью настраиваемой политики.</span><span class="sxs-lookup"><span data-stu-id="5425d-126">To avoid guest from accessing bots, you can create more app setup policies, assign them to internal users, and install bots with the custom policies.</span></span>

## <a name="external-federated-users"></a><span data-ttu-id="5425d-127">Внешние (федераированные) пользователи</span><span class="sxs-lookup"><span data-stu-id="5425d-127">External (Federated) users</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="5425d-128">Установка, обновление и удаление для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="5425d-128">Install, update, and delete for external users</span></span>

<span data-ttu-id="5425d-129">Внешние пользователи не могут устанавливать, обновлять и удалять приложения в любом контексте, например в личном чате, канале или на собрании.</span><span class="sxs-lookup"><span data-stu-id="5425d-129">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="5425d-130">У них нет доступа к магазину Teams приложений.</span><span class="sxs-lookup"><span data-stu-id="5425d-130">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="5425d-131">Поведение использования и политика для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="5425d-131">Usage behavior and policy for external users</span></span>

- <span data-ttu-id="5425d-132">Внешние пользователи не могут использовать приложения Teams, а при добавлении внешнего пользователя в контекст со своими пользователями все пользователи (как внешние, так и внешние) больше не могут использовать приложения.</span><span class="sxs-lookup"><span data-stu-id="5425d-132">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>
- <span data-ttu-id="5425d-133">Политики приложений не влияют на внешних пользователей, так как они не могут использовать Teams приложения.</span><span class="sxs-lookup"><span data-stu-id="5425d-133">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-users"></a><span data-ttu-id="5425d-134">Анонимные пользователи</span><span class="sxs-lookup"><span data-stu-id="5425d-134">Anonymous users</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="5425d-135">Установка, обновление и удаление для анонимных пользователей</span><span class="sxs-lookup"><span data-stu-id="5425d-135">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="5425d-136">Анонимные пользователи не могут устанавливать, обновлять и удалять приложения на собраниях.</span><span class="sxs-lookup"><span data-stu-id="5425d-136">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="5425d-137">Поведение использования и политика для анонимных пользователей</span><span class="sxs-lookup"><span data-stu-id="5425d-137">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="5425d-138">Анонимные пользователи не могут напрямую использовать приложения на собраниях.</span><span class="sxs-lookup"><span data-stu-id="5425d-138">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="5425d-139">Если в собрании есть анонимные пользователи, пользователи могут продолжать использовать приложения для собраний.</span><span class="sxs-lookup"><span data-stu-id="5425d-139">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="5425d-140">Если приложение отправляет в чат адаптивную карточку, анонимные пользователи могут взаимодействовать с ней.</span><span class="sxs-lookup"><span data-stu-id="5425d-140">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span> <span data-ttu-id="5425d-141">Дополнительные сведения можно найти в [документе Разрешение анонимным пользователям присоединяться к собраниям.](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)</span><span class="sxs-lookup"><span data-stu-id="5425d-141">For more information, read [Allow anonymous users to join meetings](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="5425d-142">Анонимные пользователи наследуют глобальную политику разрешений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5425d-142">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="5425d-143">Они могут взаимодействовать с приложениями Teams собраниях, если это включено политикой разрешений на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="5425d-143">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="5425d-144">Анонимные пользователи могут работать только с приложениями, которые уже доступны на собрании и не могут приобрести их или управлять ими.</span><span class="sxs-lookup"><span data-stu-id="5425d-144">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
