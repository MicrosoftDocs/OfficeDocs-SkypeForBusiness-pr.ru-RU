---
title: Поведение приложений Teams для нестандартных пользователей
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Узнайте, как приложения в Microsoft Teams работают для нестандартных пользователей.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc4f4f53262127355afa573b0fc2abec6b05e64
ms.sourcegitcommit: 3861d661d32f507bd8479509ed09b1cfcf0b214f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2021
ms.locfileid: "51607521"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="4a36d-103">Поведение приложений Microsoft Teams для нестандартных пользователей</span><span class="sxs-lookup"><span data-stu-id="4a36d-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="4a36d-104">В этой статье описано поведение приложений в Teams, когда в контексте Teams присутствуют гости, внешние (федераированные) и анонимные пользователи.</span><span class="sxs-lookup"><span data-stu-id="4a36d-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="4a36d-105">Гостевой **пользователь** — это человек, который не является работником, студентом или сотрудником вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4a36d-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="4a36d-106">У него нет учебной или рабочей учетной записи, предоставленной вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="4a36d-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="4a36d-107">Внешний **(федераированный)** пользователь принадлежит к другому домену и не имеет доступа к командам или ресурсам группы вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4a36d-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

>[!Note]
> <span data-ttu-id="4a36d-108">Более подробное сравнение гостевых и внешних пользователей см. в описании взаимодействия [с пользователями из других организаций.](./communicate-with-users-from-other-organizations.md)</span><span class="sxs-lookup"><span data-stu-id="4a36d-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="4a36d-109">Анонимный **пользователь —** это понятие в собраниях Teams, где пользователь присоединяется к собранию по ссылке.</span><span class="sxs-lookup"><span data-stu-id="4a36d-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="4a36d-110">Пользователь не вошел в систему с учетной записью Майкрософт или организации.</span><span class="sxs-lookup"><span data-stu-id="4a36d-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-user-access"></a><span data-ttu-id="4a36d-111">Гостевой доступ</span><span class="sxs-lookup"><span data-stu-id="4a36d-111">Guest user access</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="4a36d-112">Установка, обновление и удаление для гостевых пользователей</span><span class="sxs-lookup"><span data-stu-id="4a36d-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="4a36d-113">Гости не могут устанавливать, обновлять или удалять приложения в общем контексте, например в чате, канале или собрании.</span><span class="sxs-lookup"><span data-stu-id="4a36d-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting.</span></span> <span data-ttu-id="4a36d-114">Они могут устанавливать, обновлять и удалять приложения в своей личной области с помощью расширений сообщений и прямых ссылок.</span><span class="sxs-lookup"><span data-stu-id="4a36d-114">They can install, update, or delete apps to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="4a36d-115">Гости не имеют доступа к магазину приложений Teams.</span><span class="sxs-lookup"><span data-stu-id="4a36d-115">Guests don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="4a36d-116">Поведение использования и политика для гостевых пользователей</span><span class="sxs-lookup"><span data-stu-id="4a36d-116">Usage behavior and policy for guest users</span></span>

<span data-ttu-id="4a36d-117">Гости могут использовать приложение, если приложение было установлено пользователем.</span><span class="sxs-lookup"><span data-stu-id="4a36d-117">Guests can use an app if the app was installed by a native user.</span></span>

<span data-ttu-id="4a36d-118">Боты могут заблаговременно отправлять гостю сообщения, но они не могут взаимодействовать с ботом.</span><span class="sxs-lookup"><span data-stu-id="4a36d-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="4a36d-119">Гости не могут отправить боту сообщение 1:1, @упомянуть его или использовать адаптивные карточки, которые общаются с ботом.</span><span class="sxs-lookup"><span data-stu-id="4a36d-119">Guests can't message the bot 1:1, @ mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

<span data-ttu-id="4a36d-120">Гости будут соблюдать глобальные и групповые политики разрешений, установленные для клиента хоста для любого приложения.</span><span class="sxs-lookup"><span data-stu-id="4a36d-120">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="4a36d-121">Другими словами, если приложение заблокировано для всей организации,то гости также не могут использовать его.</span><span class="sxs-lookup"><span data-stu-id="4a36d-121">In other words, if an app is blocked for the whole host organization, then guests can't use the app either.</span></span>

<span data-ttu-id="4a36d-122">Политики настройки не применяются к гостевых пользователей.</span><span class="sxs-lookup"><span data-stu-id="4a36d-122">Setup policies don't apply to guest users.</span></span> <span data-ttu-id="4a36d-123">Это означает, что закрепленное администратором приложение из политики по умолчанию не влияет на гостевых пользователей.</span><span class="sxs-lookup"><span data-stu-id="4a36d-123">This means admin pinned app from the default policy doesn't affect guest users.</span></span>

## <a name="external-federated-user-access"></a><span data-ttu-id="4a36d-124">Доступ внешних (федераированных) пользователей</span><span class="sxs-lookup"><span data-stu-id="4a36d-124">External (Federated) user access</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="4a36d-125">Установка, обновление и удаление для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="4a36d-125">Install, update, and delete for external users</span></span>

<span data-ttu-id="4a36d-126">Внешние пользователи не могут устанавливать, обновлять или удалять приложения в любом контексте, например в личных беседах, каналах или собраниях.</span><span class="sxs-lookup"><span data-stu-id="4a36d-126">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="4a36d-127">У них нет доступа к магазину приложений Teams.</span><span class="sxs-lookup"><span data-stu-id="4a36d-127">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="4a36d-128">Поведение использования и политика для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="4a36d-128">Usage behavior and policy for external users</span></span>

<span data-ttu-id="4a36d-129">Внешние пользователи не могут использовать приложения Teams, а при добавлении внешнего пользователя в контекст со своими пользователями все пользователи (как внутренних, так и внешних) больше не могут использовать приложения.</span><span class="sxs-lookup"><span data-stu-id="4a36d-129">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>

<span data-ttu-id="4a36d-130">Политики приложений не влияют на внешних пользователей, так как они не могут использовать приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="4a36d-130">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-user-in-meetings-access"></a><span data-ttu-id="4a36d-131">Анонимный пользователь в доступе к собраниям</span><span class="sxs-lookup"><span data-stu-id="4a36d-131">Anonymous user in meetings access</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="4a36d-132">Установка, обновление и удаление для анонимных пользователей</span><span class="sxs-lookup"><span data-stu-id="4a36d-132">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="4a36d-133">Анонимные пользователи не могут устанавливать, обновлять и удалять приложения на собраниях.</span><span class="sxs-lookup"><span data-stu-id="4a36d-133">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="4a36d-134">Поведение использования и политика для анонимных пользователей</span><span class="sxs-lookup"><span data-stu-id="4a36d-134">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="4a36d-135">Анонимные пользователи не могут напрямую использовать приложения на собраниях.</span><span class="sxs-lookup"><span data-stu-id="4a36d-135">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="4a36d-136">При этом пользователи, которые являются анонимными, могут продолжать использовать приложения для собраний.</span><span class="sxs-lookup"><span data-stu-id="4a36d-136">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="4a36d-137">Если приложение отправляет в чат адаптивную карточку, анонимные пользователи могут взаимодействовать с ней для получения дополнительных сведений. См. статью "Разрешить анонимным пользователям присоединяться к [собраниям".](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)</span><span class="sxs-lookup"><span data-stu-id="4a36d-137">If an app sends an adaptive card in the chat, anonymous users can interact with the card For more information, see [Allow anonymous users to join meetings](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="4a36d-138">Анонимные пользователи наследуют глобальную политику разрешений по умолчанию на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="4a36d-138">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="4a36d-139">Они могут взаимодействовать с приложениями в собраниях Teams, если приложение включено политикой разрешений на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="4a36d-139">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="4a36d-140">Анонимные пользователи могут работать только с приложениями, которые уже доступны на собрании и не могут приобрести эти приложения или управлять ими.</span><span class="sxs-lookup"><span data-stu-id="4a36d-140">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
