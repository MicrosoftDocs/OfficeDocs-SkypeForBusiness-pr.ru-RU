---
title: Teams и Skype интероперируемость
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: Узнайте о возможностях взаимодействия между Teams пользователями в организации и Skype (потребительскими).
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093959"
---
# <a name="teams-and-skype-interoperability"></a><span data-ttu-id="bf3bc-103">Teams и Skype интероперируемость</span><span class="sxs-lookup"><span data-stu-id="bf3bc-103">Teams and Skype interoperability</span></span>

<span data-ttu-id="bf3bc-104">В этой статье представлен обзор возможностей взаимодействия между Microsoft Teams и Skype (потребительские).</span><span class="sxs-lookup"><span data-stu-id="bf3bc-104">This article gives you an overview of the interoperability capabilities between Microsoft Teams and Skype (Consumer).</span></span> <span data-ttu-id="bf3bc-105">Узнайте, Teams и Skype могут общаться с помощью чатов и звонков, а также применяет администратора.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-105">Learn how Teams users and Skype users can communicate through chats and calls and the admin controls that apply.</span></span>

<span data-ttu-id="bf3bc-106">Teams пользователи в вашей организации могут общаться и звонить Skype пользователям, используя их адреса электронной почты и наоборот.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-106">Teams users in your organization can chat with and call Skype users by using their email address and vice versa.</span></span>

- <span data-ttu-id="bf3bc-107">Teams пользователи могут искать и начинать беседу, доступную только к тексту, или аудио- или видеозвук с Skype пользователем.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-107">Teams users can search for and start a one-on-one text-only conversation or an audio/video call with a Skype user.</span></span>
- <span data-ttu-id="bf3bc-108">Skype пользователи могут искать и начинать беседу, доступную только к тексту, или аудио- или видеозвук с Teams пользователем.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-108">Skype users can search for and start a one-on-one text-only conversation or an audio/video call with a Teams user.</span></span>

<span data-ttu-id="bf3bc-109">Эти возможности доступны в клиентах для настольных компьютеров, браузера и мобильных устройств (Android и iOS) Teams и Skype.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-109">These capabilities are available on the desktop, web, and mobile (Android and iOS) clients for both Teams and Skype.</span></span> <span data-ttu-id="bf3bc-110">Для оптимальной работы рекомендуется использовать Skype версии 8.58 и более поздних.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-110">For an optimal experience, we recommend Skype version 8.58 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="bf3bc-111">Возможности Teams и Skype, рассмотренные в этой статье, недоступны в развертываниях GCC, GCC high, DOD или в закрытых облачных средах.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-111">The Teams and Skype interop capabilities discussed in this article aren't available in GCC, GCC High, or DOD deployments, or in private cloud environments.</span></span>

## <a name="chat-and-calling-experience"></a><span data-ttu-id="bf3bc-112">Общение в чате и вызовы</span><span class="sxs-lookup"><span data-stu-id="bf3bc-112">Chat and calling experience</span></span>

<span data-ttu-id="bf3bc-113">Ниже представлен обзор чата и звонков.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-113">Here's an overview of the chat and calling experience.</span></span>

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a><span data-ttu-id="bf3bc-114">Teams начинает чат или звонок с Skype пользователем</span><span class="sxs-lookup"><span data-stu-id="bf3bc-114">Teams user starts a chat or call with a Skype user</span></span>

<span data-ttu-id="bf3bc-115">Teams пользователи могут найти пользователя Skype, введя его адрес электронной почты в новом чате или в панели поиска.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-115">Teams users can search for a Skype user by typing their email address in a new chat or in the search bar.</span></span>  <span data-ttu-id="bf3bc-116">Затем Teams может выбрать пользователя Skype в результатах поиска, чтобы начать чат или позвонить с ним.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-116">The Teams user can then select the Skype user in the search results to start a chat or call with them.</span></span>

<span data-ttu-id="bf3bc-117">Пользователь Skype не отображаться в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-117">A Skype user may choose not to appear in search results.</span></span> <span data-ttu-id="bf3bc-118">В этом случае они не будут показываться в результатах поиска в Teams и Teams пользователи не смогут их найти.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-118">In this case, they won't show up in the search results in Teams and Teams users won't be able to find them.</span></span>

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a><span data-ttu-id="bf3bc-119">Skype начинает чат или звонок с Teams пользователем</span><span class="sxs-lookup"><span data-stu-id="bf3bc-119">Skype user starts a chat or call with a Teams user</span></span>

<span data-ttu-id="bf3bc-120">Skype пользователи могут искать и начинать чат с другими Teams помощью своих адресов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-120">Skype users can search for and start a chat with a Teams user by using their email address.</span></span> <span data-ttu-id="bf3bc-121">Пользователь Teams получает уведомление о новом сообщении от Skype и должен сначала принять его, прежде чем ответить на него.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-121">The Teams user is notified that they have a new message from a Skype user, and has to first accept the message before they can reply to it.</span></span>

- <span data-ttu-id="bf3bc-122">Если пользователь Teams **принять,** беседа будет принята, и оба пользователя смогут общаться и звонить друг другу.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-122">If the Teams user selects **Accept**, the conversation is accepted, and both users can chat and call each other.</span></span>
- <span data-ttu-id="bf3bc-123">Если Teams **заблокировать,** беседа будет заблокирована, а последующие сообщения и звонки от этого пользователя Skype заблокированы.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-123">If the Teams user selects **Block**, the conversation is blocked, and subsequent messages and calls from that Skype user are blocked.</span></span>
- <span data-ttu-id="bf3bc-124">Если пользователь Teams просмотр **сообщений,** сообщение отображается в Teams, что помогает пользователю решить, принимать или блокировать беседу.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-124">If the Teams user selects **View messages**, the message is displayed in Teams, which helps the user decide whether to accept or block the conversation.</span></span>

> [!NOTE]
> <span data-ttu-id="bf3bc-125">Если вы обновили Skype для бизнеса до Teams и ваши пользователи находятся в режиме Teams, чаты и звонки от Skype пользователей Teams пользователей доставляются в Teams.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-125">If you upgraded from Skype for Business to Teams and your users are in Teams Only mode, chats and calls from Skype users to Teams users are delivered to Teams.</span></span> <span data-ttu-id="bf3bc-126">Если ваши пользователи находятся в режиме "О-ва", чаты и звонки от Skype пользователей Teams пользователям доставляются в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-126">If your users are in Islands mode, chats and calls from Skype users to Teams users are delivered to Skype for Business.</span></span>

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a><span data-ttu-id="bf3bc-127">Teams блокирует или разблокирует Skype пользователя</span><span class="sxs-lookup"><span data-stu-id="bf3bc-127">Teams user blocks or unblocks a Skype user</span></span>

<span data-ttu-id="bf3bc-128">После того Teams пользователь принимает или блокирует первоначальный запрос на беседу от Skype пользователя, он может заблокировать или разблокировать этого пользователя в любое время.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-128">After a Teams user accepts or blocks the initial conversation request from a Skype user, they can choose to block or unblock that person at any time.</span></span> <span data-ttu-id="bf3bc-129">Это можно сделать в беседе или в параметрах конфиденциальности в Teams.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-129">They can do this either in the conversation or in their privacy settings in Teams.</span></span> <span data-ttu-id="bf3bc-130">Skype пользователи не будут знать, что они заблокированы.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-130">Skype users won't know that they've been blocked.</span></span>

<span data-ttu-id="bf3bc-131">Заблокированные Skype, а также другие пользователи и телефонные номера телефонов Teams, заблокированные пользователем Teams, перечисляются в списке заблокированных контактов в Teams.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-131">Blocked Skype users, along with other people and public switched telephone network (PSTN) phone numbers that a Teams user has blocked, are listed on the user's blocked contact list in Teams.</span></span>

## <a name="limitations"></a><span data-ttu-id="bf3bc-132">Ограничения</span><span class="sxs-lookup"><span data-stu-id="bf3bc-132">Limitations</span></span>

- <span data-ttu-id="bf3bc-133">Беседы — это только текст.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-133">Conversations are text-only.</span></span> <span data-ttu-id="bf3bc-134">Это означает, что в чате нет форматирования, @mentions, эмодзи и других функций чата, доступных в Teams [чате.](native-chat-for-external-users.md)</span><span class="sxs-lookup"><span data-stu-id="bf3bc-134">This means that there's no rich formatting, @mentions, emojis, or other any of the other chat features that are available in a [native Teams chat experience](native-chat-for-external-users.md).</span></span>
- <span data-ttu-id="bf3bc-135">Беседы — только один на один.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-135">Conversations are one-on-one only.</span></span> <span data-ttu-id="bf3bc-136">Групповые чаты не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-136">Group chats aren't supported.</span></span>
- <span data-ttu-id="bf3bc-137">Teams и Skype не могут видеть присутствие друг друга.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-137">Teams users and Skype users can't see each other's presence.</span></span>
- <span data-ttu-id="bf3bc-138">Поиск Skype с помощью Skype или номера телефона не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-138">Searching for Skype users by using their Skype ID or phone number isn't supported.</span></span>
- <span data-ttu-id="bf3bc-139">Skype пользователи не могут звонить Teams, которые настроили переадпорансирование звонка на номер другого пользователя, номер делегата или номер телефонной сети общего перейти на другой телефон.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-139">Skype users can't call Teams users who set up call forwarding to another user's number, a delegate's number, or a Public Switched Telephone Network (PSTN) number.</span></span>  <span data-ttu-id="bf3bc-140">Поддерживается только голосовая почта.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-140">Only voicemail is supported.</span></span>
- <span data-ttu-id="bf3bc-141">Перегруппиация, групповые звонки и собрания не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-141">Interop escalation, group calls, and meetings aren't supported.</span></span>
- <span data-ttu-id="bf3bc-142">Возможность представителя звонить Skype от имени Teams не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-142">The ability for a delegate to call a Skype user on behalf of a Teams user isn't supported.</span></span>
- <span data-ttu-id="bf3bc-143">Общий доступ к экрану в чате не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-143">Screen sharing with chat isn't supported.</span></span>

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a><span data-ttu-id="bf3bc-144">Настройка того, Teams могут ли пользователи общаться с Skype пользователями</span><span class="sxs-lookup"><span data-stu-id="bf3bc-144">Set whether Teams users can communicate with Skype users</span></span>

<span data-ttu-id="bf3bc-145">Администраторы могут использовать центр администрирования Microsoft Teams или PowerShell для настройки параметров внешнего доступа, чтобы управлять возможностью Teams пользователей в организации с другими Skype пользователями.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-145">As an admin, you use the Microsoft Teams admin center or PowerShell to set external access settings to control whether Teams users in your organization can communicate with Skype users.</span></span> <span data-ttu-id="bf3bc-146">По умолчанию эта возможность включена для новых клиентов.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-146">By default, this capability is turned on for new tenants.</span></span> <span data-ttu-id="bf3bc-147">Однако необходимо, чтобы ИТ-администратор должен настроить следующую запись SRV DNS, если она еще не доступна для вашего домена, например _sipfederationtls.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-147">However, there's a prerequisite that the following DNS SRV record needs to be configured by the IT Admin if not already available for your domain, for example _sipfederationtls.contoso.com.</span></span>  

<span data-ttu-id="bf3bc-148">**Service**: sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="bf3bc-148">**Service**: sipfederationtls</span></span><br/>
<span data-ttu-id="bf3bc-149">**Протокол:** TCP</span><span class="sxs-lookup"><span data-stu-id="bf3bc-149">**Protocol**: TCP</span></span><br/>
<span data-ttu-id="bf3bc-150">**Приоритет:** 100</span><span class="sxs-lookup"><span data-stu-id="bf3bc-150">**Priority**: 100</span></span><br/>
<span data-ttu-id="bf3bc-151">**Вес:** 1</span><span class="sxs-lookup"><span data-stu-id="bf3bc-151">**Weight**: 1</span></span><br/>
<span data-ttu-id="bf3bc-152">**Порт:** 5061</span><span class="sxs-lookup"><span data-stu-id="bf3bc-152">**Port**: 5061</span></span><br/>
<span data-ttu-id="bf3bc-153">**Целевое sipfed.online.lync.com**</span><span class="sxs-lookup"><span data-stu-id="bf3bc-153">**Target**: sipfed.online.lync.com</span></span>

<span data-ttu-id="bf3bc-154">Если вы обновили Skype для бизнеса до Teams, параметры внешней связи, настроенные в Центре администрирования Skype для бизнеса, будут перенесены в Teams.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-154">If you upgraded from Skype for Business to Teams, the external communications settings that you configured in the Skype for Business admin center are migrated to Teams.</span></span>

### <a name="in-the-microsoft-teams-admin-center"></a><span data-ttu-id="bf3bc-155">В центре администрирования Microsoft Teams </span><span class="sxs-lookup"><span data-stu-id="bf3bc-155">In the Microsoft Teams admin center</span></span>

<span data-ttu-id="bf3bc-156">В Центре Microsoft Teams администрирования перейдите в параметры внешнего доступа для всей организации и включите параметр Пользователи могут общаться Skype  >   **пользователями**.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-156">In the Microsoft Teams admin center, go to **Org-wide settings** > **External access**, and then turn on **Users can communicate with Skype users**.</span></span> <span data-ttu-id="bf3bc-157">Пошаговая инструкция по настройке этого и других параметров внешнего доступа см. в [Teams.](./manage-external-access.md#allow-or-block-domains)</span><span class="sxs-lookup"><span data-stu-id="bf3bc-157">For step-by-step guidance on how to configure this and other external access settings, see [Manage external access in Teams](./manage-external-access.md#allow-or-block-domains).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="bf3bc-158">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf3bc-158">Using PowerShell</span></span>

<span data-ttu-id="bf3bc-159">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-159">Do the following:</span></span> 
1. <span data-ttu-id="bf3bc-160">Используйте [вместе с параметром set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) Teams возможность общения с Skype ```EnablePublicCloudAccess``` пользователями.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-160">Use the [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) cmdlet together with the ```EnablePublicCloudAccess``` parameter to control whether Teams users can communicate with Skype users.</span></span> <span data-ttu-id="bf3bc-161">Настройка параметра, ```true``` который позволяет Teams общаться с Skype пользователями.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-161">Setting the parameter to ```true``` allows Teams users to communicate with Skype users.</span></span> <span data-ttu-id="bf3bc-162">С помощью этого параметра можно включить или отключить ```EnablePublicCloudAudioVideoAccess``` звуковые и видеозвуки.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-162">You can use the ```EnablePublicCloudAudioVideoAccess``` parameter to enable/disable audio/video calls.</span></span>

2. <span data-ttu-id="bf3bc-163">Используйте [вместе с параметром set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) Teams, чтобы пользователи могли общаться Skype ```Provider``` ```"WindowsLive"``` пользователями.</span><span class="sxs-lookup"><span data-stu-id="bf3bc-163">Use the [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet together with the ```Provider``` parameter set to ```"WindowsLive"``` so that Teams users can communicate with Skype users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bf3bc-164">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="bf3bc-164">Related topics</span></span>

- [<span data-ttu-id="bf3bc-165">Управление внешним доступом в Teams</span><span class="sxs-lookup"><span data-stu-id="bf3bc-165">Manage external access in Teams</span></span>](manage-external-access.md)
- [<span data-ttu-id="bf3bc-166">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="bf3bc-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)