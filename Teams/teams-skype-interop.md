---
title: Общение Teams и Skype
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
description: Узнайте о возможностях взаимодействия между пользователями Teams в вашей организации и пользователями Skype (для потребителей).
localization_priority: Normal
ms.openlocfilehash: 8bb6a83eddc60ff680d1a08c7266e082dd8b0188
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055651"
---
# <a name="teams-and-skype-interoperability"></a><span data-ttu-id="ee890-103">Общение Teams и Skype</span><span class="sxs-lookup"><span data-stu-id="ee890-103">Teams and Skype interoperability</span></span>

<span data-ttu-id="ee890-104">В этой статье приводится обзор возможностей взаимодействия между Microsoft Teams и Skype (для потребителей).</span><span class="sxs-lookup"><span data-stu-id="ee890-104">This article gives you an overview of the interoperability capabilities between Microsoft Teams and Skype (Consumer).</span></span> <span data-ttu-id="ee890-105">Узнайте, как пользователи Teams и Skype могут общаться с помощью чатов и звонков, а также о внося в них администрирования.</span><span class="sxs-lookup"><span data-stu-id="ee890-105">Learn how Teams users and Skype users can communicate through chats and calls and the admin controls that apply.</span></span>

<span data-ttu-id="ee890-106">Пользователи Teams в вашей организации могут общаться и звонить пользователям Skype, используя их адреса электронной почты и наоборот.</span><span class="sxs-lookup"><span data-stu-id="ee890-106">Teams users in your organization can chat with and call Skype users by using their email address and vice versa.</span></span>

- <span data-ttu-id="ee890-107">Пользователи Teams могут искать и начинать при этом при этом текстовую беседу, а также аудио- или видеозвук с пользователем Skype.</span><span class="sxs-lookup"><span data-stu-id="ee890-107">Teams users can search for and start a one-on-one text-only conversation or an audio/video call with a Skype user.</span></span>
- <span data-ttu-id="ee890-108">Пользователи Skype могут искать и начинать при этом при этом текстовую беседу, а также аудио- или видеозвук с пользователем Teams.</span><span class="sxs-lookup"><span data-stu-id="ee890-108">Skype users can search for and start a one-on-one text-only conversation or an audio/video call with a Teams user.</span></span>

<span data-ttu-id="ee890-109">Эти возможности доступны в классических, веб-версиях и клиентах Для мобильных устройств (Android и iOS) для Teams и Skype.</span><span class="sxs-lookup"><span data-stu-id="ee890-109">These capabilities are available on the desktop, web, and mobile (Android and iOS) clients for both Teams and Skype.</span></span> <span data-ttu-id="ee890-110">Для оптимальной работы мы рекомендуем Скайп версии 8.58 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="ee890-110">For an optimal experience, we recommend Skype version 8.58 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="ee890-111">Возможности между Teams и Skype, рассмотренные в этой статье, недоступны в развертываниях GCC, GCC High или DOD, а также в закрытых облачных средах.</span><span class="sxs-lookup"><span data-stu-id="ee890-111">The Teams and Skype interop capabilities discussed in this article aren't available in GCC, GCC High, or DOD deployments, or in private cloud environments.</span></span>

## <a name="chat-and-calling-experience"></a><span data-ttu-id="ee890-112">Чат и вызовы</span><span class="sxs-lookup"><span data-stu-id="ee890-112">Chat and calling experience</span></span>

<span data-ttu-id="ee890-113">Ниже представлен обзор чата и звонков.</span><span class="sxs-lookup"><span data-stu-id="ee890-113">Here's an overview of the chat and calling experience.</span></span>

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a><span data-ttu-id="ee890-114">Пользователь Teams начинает чат или звонок с пользователем Skype</span><span class="sxs-lookup"><span data-stu-id="ee890-114">Teams user starts a chat or call with a Skype user</span></span>

<span data-ttu-id="ee890-115">Пользователи Teams могут найти пользователя Skype, введя его адрес электронной почты в новой беседе или в панели поиска.</span><span class="sxs-lookup"><span data-stu-id="ee890-115">Teams users can search for a Skype user by typing their email address in a new chat or in the search bar.</span></span>  <span data-ttu-id="ee890-116">Затем пользователь Teams может выбрать пользователя Skype в результатах поиска, чтобы начать чат или позвонить с ним.</span><span class="sxs-lookup"><span data-stu-id="ee890-116">The Teams user can then select the Skype user in the search results to start a chat or call with them.</span></span>

<span data-ttu-id="ee890-117">Пользователь Skype может не отображаться в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="ee890-117">A Skype user may choose not to appear in search results.</span></span> <span data-ttu-id="ee890-118">В этом случае они не будут показываться в результатах поиска в Teams, и пользователи Teams не смогут их найти.</span><span class="sxs-lookup"><span data-stu-id="ee890-118">In this case, they won't show up in the search results in Teams and Teams users won't be able to find them.</span></span>

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a><span data-ttu-id="ee890-119">Пользователь Skype начинает чат или звонок с пользователем Teams</span><span class="sxs-lookup"><span data-stu-id="ee890-119">Skype user starts a chat or call with a Teams user</span></span>

<span data-ttu-id="ee890-120">Пользователи Skype могут искать и начинать чат с пользователем Teams, используя свой адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ee890-120">Skype users can search for and start a chat with a Teams user by using their email address.</span></span> <span data-ttu-id="ee890-121">Пользователь Teams получает уведомление о новом сообщении от пользователя Skype и должен сначала принять его, прежде чем он сможет ответить на него.</span><span class="sxs-lookup"><span data-stu-id="ee890-121">The Teams user is notified that they have a new message from a Skype user, and has to first accept the message before they can reply to it.</span></span>

- <span data-ttu-id="ee890-122">Если пользователь Teams выберет **"Принять",** беседа будет принята, и оба пользователя смогут общаться и звонить друг другу.</span><span class="sxs-lookup"><span data-stu-id="ee890-122">If the Teams user selects **Accept**, the conversation is accepted, and both users can chat and call each other.</span></span>
- <span data-ttu-id="ee890-123">Если пользователь Teams набирает **блок,** беседа блокируется, а последующие сообщения и звонки от этого пользователя Skype блокируются.</span><span class="sxs-lookup"><span data-stu-id="ee890-123">If the Teams user selects **Block**, the conversation is blocked, and subsequent messages and calls from that Skype user are blocked.</span></span>
- <span data-ttu-id="ee890-124">Если пользователь Teams выбирает "Просмотр сообщений", сообщение отображается в Teams, что помогает пользователю принять или заблокировать беседу.</span><span class="sxs-lookup"><span data-stu-id="ee890-124">If the Teams user selects **View messages**, the message is displayed in Teams, which helps the user decide whether to accept or block the conversation.</span></span>

> [!NOTE]
> <span data-ttu-id="ee890-125">Если вы обновили Skype для бизнеса до Teams и ваши пользователи работают в режиме "Только Teams", чаты и звонки от пользователей Skype в Teams доставляются в Teams.</span><span class="sxs-lookup"><span data-stu-id="ee890-125">If you upgraded from Skype for Business to Teams and your users are in Teams Only mode, chats and calls from Skype users to Teams users are delivered to Teams.</span></span> <span data-ttu-id="ee890-126">Если ваши пользователи находятся в режиме "Острова", чаты и звонки от пользователей Skype к пользователям Teams доставляются в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ee890-126">If your users are in Islands mode, chats and calls from Skype users to Teams users are delivered to Skype for Business.</span></span>

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a><span data-ttu-id="ee890-127">Пользователь Teams блокирует или разблокирует пользователя Skype</span><span class="sxs-lookup"><span data-stu-id="ee890-127">Teams user blocks or unblocks a Skype user</span></span>

<span data-ttu-id="ee890-128">После того как пользователь Teams принимает или блокирует первоначальный запрос на беседу от пользователя Skype, он может заблокировать или разблокировать этого пользователя в любое время.</span><span class="sxs-lookup"><span data-stu-id="ee890-128">After a Teams user accepts or blocks the initial conversation request from a Skype user, they can choose to block or unblock that person at any time.</span></span> <span data-ttu-id="ee890-129">Это можно сделать в беседе или в параметрах конфиденциальности в Teams.</span><span class="sxs-lookup"><span data-stu-id="ee890-129">They can do this either in the conversation or in their privacy settings in Teams.</span></span> <span data-ttu-id="ee890-130">Пользователи Skype не знают, что они заблокированы.</span><span class="sxs-lookup"><span data-stu-id="ee890-130">Skype users won't know that they've been blocked.</span></span>

<span data-ttu-id="ee890-131">Заблокированные пользователи Skype, а также другие пользователи и телефонные номера телефонной сети общего звонков (STN), заблокированные пользователем Teams, перечисляются в списке заблокированных контактов пользователя в Teams.</span><span class="sxs-lookup"><span data-stu-id="ee890-131">Blocked Skype users, along with other people and public switched telephone network (PSTN) phone numbers that a Teams user has blocked, are listed on the user's blocked contact list in Teams.</span></span>

## <a name="limitations"></a><span data-ttu-id="ee890-132">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ee890-132">Limitations</span></span>

- <span data-ttu-id="ee890-133">Беседы только в текстовом виде.</span><span class="sxs-lookup"><span data-stu-id="ee890-133">Conversations are text-only.</span></span> <span data-ttu-id="ee890-134">Это означает, что в чате Teams нет форматирования, @mentions, эмодзи и других функций [чата.](native-chat-for-external-users.md)</span><span class="sxs-lookup"><span data-stu-id="ee890-134">This means that there's no rich formatting, @mentions, emojis, or other any of the other chat features that are available in a [native Teams chat experience](native-chat-for-external-users.md).</span></span>
- <span data-ttu-id="ee890-135">Беседы при этом ются только один раз.</span><span class="sxs-lookup"><span data-stu-id="ee890-135">Conversations are one-on-one only.</span></span> <span data-ttu-id="ee890-136">Групповые чаты не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="ee890-136">Group chats aren't supported.</span></span>
- <span data-ttu-id="ee890-137">Пользователи Teams и Skype не могут видеть присутствие друг друга.</span><span class="sxs-lookup"><span data-stu-id="ee890-137">Teams users and Skype users can't see each other's presence.</span></span>
- <span data-ttu-id="ee890-138">Поиск пользователей Skype по их ID или номеру телефона не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ee890-138">Searching for Skype users by using their Skype ID or phone number isn't supported.</span></span>
- <span data-ttu-id="ee890-139">Пользователи Skype не могут звонить пользователям Teams, которые настроили переадстройку звонков на номер другого пользователя, номер делегата или номер телефонной сети общего звонков (ННР).</span><span class="sxs-lookup"><span data-stu-id="ee890-139">Skype users can't call Teams users who set up call forwarding to another user's number, a delegate's number, or a Public Switched Telephone Network (PSTN) number.</span></span>  <span data-ttu-id="ee890-140">Поддерживается только голосовая почта.</span><span class="sxs-lookup"><span data-stu-id="ee890-140">Only voicemail is supported.</span></span>
- <span data-ttu-id="ee890-141">Перегруппация, групповые звонки и собрания не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="ee890-141">Interop escalation, group calls, and meetings aren't supported.</span></span>
- <span data-ttu-id="ee890-142">Возможность представителя звонить пользователю Skype от имени пользователя Teams не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ee890-142">The ability for a delegate to call a Skype user on behalf of a Teams user isn't supported.</span></span>
- <span data-ttu-id="ee890-143">Совместный доступ к экрану в чате не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ee890-143">Screen sharing with chat isn't supported.</span></span>

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a><span data-ttu-id="ee890-144">Настройка общения пользователей Teams с пользователями Skype</span><span class="sxs-lookup"><span data-stu-id="ee890-144">Set whether Teams users can communicate with Skype users</span></span>

<span data-ttu-id="ee890-145">Как администратор вы можете использовать Центр администрирования Microsoft Teams или PowerShell для настройки параметров внешнего доступа, чтобы контролировать возможность общения пользователей Teams в организации с пользователями Skype.</span><span class="sxs-lookup"><span data-stu-id="ee890-145">As an admin, you use the Microsoft Teams admin center or PowerShell to set external access settings to control whether Teams users in your organization can communicate with Skype users.</span></span> <span data-ttu-id="ee890-146">По умолчанию эта возможность включена для новых клиентов.</span><span class="sxs-lookup"><span data-stu-id="ee890-146">By default, this capability is turned on for new tenants.</span></span> <span data-ttu-id="ee890-147">Однако необходимо, чтобы ИТ-администратор мог настроить следующую запись SRV DNS, если она еще недоступна для вашего домена, например _sipfederationtls.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ee890-147">However, there's a prerequisite that the following DNS SRV record needs to be configured by the IT Admin if not already available for your domain, for example _sipfederationtls.contoso.com.</span></span>  

<span data-ttu-id="ee890-148">**Service**: sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="ee890-148">**Service**: sipfederationtls</span></span><br/>
<span data-ttu-id="ee890-149">**Протокол**: TCP</span><span class="sxs-lookup"><span data-stu-id="ee890-149">**Protocol**: TCP</span></span><br/>
<span data-ttu-id="ee890-150">**Приоритет:** 100</span><span class="sxs-lookup"><span data-stu-id="ee890-150">**Priority**: 100</span></span><br/>
<span data-ttu-id="ee890-151">**Вес:** 1</span><span class="sxs-lookup"><span data-stu-id="ee890-151">**Weight**: 1</span></span><br/>
<span data-ttu-id="ee890-152">**Порт:** 5061</span><span class="sxs-lookup"><span data-stu-id="ee890-152">**Port**: 5061</span></span><br/>
<span data-ttu-id="ee890-153">**Target**: sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ee890-153">**Target**: sipfed.online.lync.com</span></span>

<span data-ttu-id="ee890-154">Если вы обновили Skype для бизнеса до Teams, параметры внешней связи, настроенные в Центре администрирования Skype для бизнеса, будут перенесены в Teams.</span><span class="sxs-lookup"><span data-stu-id="ee890-154">If you upgraded from Skype for Business to Teams, the external communications settings that you configured in the Skype for Business admin center are migrated to Teams.</span></span>

### <a name="in-the-microsoft-teams-admin-center"></a><span data-ttu-id="ee890-155">В центре администрирования Microsoft Teams </span><span class="sxs-lookup"><span data-stu-id="ee890-155">In the Microsoft Teams admin center</span></span>

<span data-ttu-id="ee890-156">В Центре администрирования Microsoft Teams перейдите к настройкам внешнего доступа для всей организации, а затем включите параметр "Пользователи могут общаться с пользователями  >   **Skype".**</span><span class="sxs-lookup"><span data-stu-id="ee890-156">In the Microsoft Teams admin center, go to **Org-wide settings** > **External access**, and then turn on **Users can communicate with Skype users**.</span></span> <span data-ttu-id="ee890-157">Пошаговую инструкцию по настройке этого и других параметров внешнего доступа см. в руководстве "Управление внешним [доступом в Teams".](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains)</span><span class="sxs-lookup"><span data-stu-id="ee890-157">For step-by-step guidance on how to configure this and other external access settings, see [Manage external access in Teams](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ee890-158">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee890-158">Using PowerShell</span></span>

<span data-ttu-id="ee890-159">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ee890-159">Do the following:</span></span> 
1. <span data-ttu-id="ee890-160">Используйте [командлет Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) вместе с параметром, чтобы контролировать возможность общения пользователей Teams с ```EnablePublicCloudAccess``` пользователями Skype.</span><span class="sxs-lookup"><span data-stu-id="ee890-160">Use the [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) cmdlet together with the ```EnablePublicCloudAccess``` parameter to control whether Teams users can communicate with Skype users.</span></span> <span data-ttu-id="ee890-161">Настройка параметра, ```true``` который позволяет пользователям Teams общаться с пользователями Skype.</span><span class="sxs-lookup"><span data-stu-id="ee890-161">Setting the parameter to ```true``` allows Teams users to communicate with Skype users.</span></span> <span data-ttu-id="ee890-162">С помощью этого ```EnablePublicCloudAudioVideoAccess``` параметра можно включить или отключить аудио- и видеозвук.</span><span class="sxs-lookup"><span data-stu-id="ee890-162">You can use the ```EnablePublicCloudAudioVideoAccess``` parameter to enable/disable audio/video calls.</span></span>

2. <span data-ttu-id="ee890-163">Используйте [командлет Set-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) вместе с параметром, чтобы пользователи Teams могли общаться ```Provider``` ```"WindowsLive"``` с пользователями Skype.</span><span class="sxs-lookup"><span data-stu-id="ee890-163">Use the [Set-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet together with the ```Provider``` parameter set to ```"WindowsLive"``` so that Teams users can communicate with Skype users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ee890-164">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ee890-164">Related topics</span></span>

- [<span data-ttu-id="ee890-165">Управление внешним доступом в Teams</span><span class="sxs-lookup"><span data-stu-id="ee890-165">Manage external access in Teams</span></span>](manage-external-access.md)
- [<span data-ttu-id="ee890-166">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="ee890-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
