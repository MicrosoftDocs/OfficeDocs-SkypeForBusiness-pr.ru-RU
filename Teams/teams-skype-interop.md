---
title: Взаимодействие Teams и Skype
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: Узнайте о возможностях взаимодействия между пользователями Teams в Организации и пользователями Skype (потребителем).
localization_priority: Normal
ms.openlocfilehash: 9bb38fa33e7ef3692f5946fef4769bb45f782f1a
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030975"
---
# <a name="teams-and-skype-interoperability"></a><span data-ttu-id="0e2c6-103">Взаимодействие Teams и Skype</span><span class="sxs-lookup"><span data-stu-id="0e2c6-103">Teams and Skype interoperability</span></span>

<span data-ttu-id="0e2c6-104">В этой статье представлены общие сведения о возможностях взаимодействия между Microsoft Teams и Skype (потребителем).</span><span class="sxs-lookup"><span data-stu-id="0e2c6-104">This article gives you an overview of the interoperability capabilities between Microsoft Teams and Skype (Consumer).</span></span> <span data-ttu-id="0e2c6-105">Сведения о том, как пользователи Teams и пользователи Skype могут общаться через разговоры, звонки и элементы управления для администраторов, которые применяются.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-105">Learn how Teams users and Skype users can communicate through chats and calls and the admin controls that apply.</span></span>

<span data-ttu-id="0e2c6-106">Пользователи Teams в организации могут общаться с пользователями Skype и набирать их с помощью адреса электронной почты и наоборот.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-106">Teams users in your organization can chat with and call Skype users by using their email address and vice versa.</span></span>

- <span data-ttu-id="0e2c6-107">Пользователи Teams могут искать текстовую беседу, предназначенную только для одного пользователя, а также выполнять голосовые и видеозвонки с помощью Skype.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-107">Teams users can search for and start a one-on-one text-only conversation or an audio/video call with a Skype user.</span></span>
- <span data-ttu-id="0e2c6-108">Пользователи Skype могут искать текстовую беседу, которая доступна только в одной строке, а также выполнять голосовые и видеозвонки с помощью пользователей Teams.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-108">Skype users can search for and start a one-on-one text-only conversation or an audio/video call with a Teams user.</span></span>

<span data-ttu-id="0e2c6-109">Эти возможности доступны в клиентах для настольных систем, веб-сайтов и мобильных устройств (Android и iOS) как в Teams, так и в Skype.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-109">These capabilities are available on the desktop, web, and mobile (Android and iOS) clients for both Teams and Skype.</span></span> <span data-ttu-id="0e2c6-110">Для оптимальной работы мы рекомендуем использовать Skype версии 8,58 и более поздней.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-110">For an optimal experience, we recommend Skype version 8.58 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="0e2c6-111">Возможности взаимодействия с приложениями Teams и Skype, описанные в этой статье, не поддерживаются в развертываниях GCC, GCC High или DOD или в частных облачных средах.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-111">The Teams and Skype interop capabilities discussed in this article aren't available in GCC, GCC High, or DOD deployments, or in private cloud environments.</span></span>

## <a name="chat-and-calling-experience"></a><span data-ttu-id="0e2c6-112">Чат и работа с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="0e2c6-112">Chat and calling experience</span></span>

<span data-ttu-id="0e2c6-113">Ознакомьтесь с обзором общения и звонков.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-113">Here's an overview of the chat and calling experience.</span></span>

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a><span data-ttu-id="0e2c6-114">Пользователи Teams начинают чат или звоните с помощью пользователя Skype</span><span class="sxs-lookup"><span data-stu-id="0e2c6-114">Teams user starts a chat or call with a Skype user</span></span>

<span data-ttu-id="0e2c6-115">Пользователи Teams могут найти пользователя Skype, введя его адрес электронной почты в новом чате или на строке поиска.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-115">Teams users can search for a Skype user by typing their email address in a new chat or in the search bar.</span></span>  <span data-ttu-id="0e2c6-116">После этого пользователь Teams сможет выбрать пользователя Skype в результатах поиска, чтобы начать чат или позвонить вместе с ним.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-116">The Teams user can then select the Skype user in the search results to start a chat or call with them.</span></span>

<span data-ttu-id="0e2c6-117">Пользователь Skype может не отображаться в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-117">A Skype user may choose not to appear in search results.</span></span> <span data-ttu-id="0e2c6-118">В этом случае они не отображаются в результатах поиска в Teams и пользователи Teams не смогут найти их.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-118">In this case, they won't show up in the search results in Teams and Teams users won't be able to find them.</span></span>

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a><span data-ttu-id="0e2c6-119">Skype User — Начало чата или звонка с помощью пользователя Teams</span><span class="sxs-lookup"><span data-stu-id="0e2c6-119">Skype user starts a chat or call with a Teams user</span></span>

<span data-ttu-id="0e2c6-120">Пользователи Skype могут найти и начать чат с пользователем Teams с помощью адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-120">Skype users can search for and start a chat with a Teams user by using their email address.</span></span> <span data-ttu-id="0e2c6-121">Пользователь Teams получит уведомление о том, что у вас есть новое сообщение от пользователя Skype, и хотите сначала подтвердить сообщение, прежде чем оно сможет ответить на него.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-121">The Teams user is notified that they have a new message from a Skype user, and has to first accept the message before they can reply to it.</span></span>

- <span data-ttu-id="0e2c6-122">Если пользователь Teams выберет " **принять** ", беседа будет принята, и оба пользователя смогут общаться и позвонить друг другу.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-122">If the Teams user selects **Accept** , the conversation is accepted, and both users can chat and call each other.</span></span>
- <span data-ttu-id="0e2c6-123">Если пользователь выбирает **блок** команд, разговор блокируется, и последующие сообщения и звонки от этого пользователя Skype блокируются.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-123">If the Teams user selects **Block** , the conversation is blocked, and subsequent messages and calls from that Skype user are blocked.</span></span>
- <span data-ttu-id="0e2c6-124">Если пользователь Teams выбирает **Просмотр сообщений** , сообщение отображается в Teams, что позволяет пользователю решить, принимать ли или блокировать беседу.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-124">If the Teams user selects **View messages** , the message is displayed in Teams, which helps the user decide whether to accept or block the conversation.</span></span>

> [!NOTE]
> <span data-ttu-id="0e2c6-125">Если вы перешли из Skype для бизнеса в Teams, а ваши пользователи находятся в режиме только Teams, разговоры и звонки из Skype для пользователей Teams будут доставляться в Teams.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-125">If you upgraded from Skype for Business to Teams and your users are in Teams Only mode, chats and calls from Skype users to Teams users are delivered to Teams.</span></span> <span data-ttu-id="0e2c6-126">Если пользователи находятся в режиме острова, разговоры и звонки из Skype для пользователей Teams доставляются в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-126">If your users are in Islands mode, chats and calls from Skype users to Teams users are delivered to Skype for Business.</span></span>

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a><span data-ttu-id="0e2c6-127">Пользователь Teams блокирует или разблокирует пользователя Skype</span><span class="sxs-lookup"><span data-stu-id="0e2c6-127">Teams user blocks or unblocks a Skype user</span></span>

<span data-ttu-id="0e2c6-128">После того как пользователь Teams принимает или блокирует первоначальный запрос беседы от пользователя Skype, он может в любое время заблокировать или разблокировать этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-128">After a Teams user accepts or blocks the initial conversation request from a Skype user, they can choose to block or unblock that person at any time.</span></span> <span data-ttu-id="0e2c6-129">Это можно сделать либо в разговоре, либо в параметрах конфиденциальности в Teams.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-129">They can do this either in the conversation or in their privacy settings in Teams.</span></span> <span data-ttu-id="0e2c6-130">Пользователи Skype не знают, что они заблокированы.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-130">Skype users won't know that they've been blocked.</span></span>

<span data-ttu-id="0e2c6-131">Заблокированные пользователи Skype, а также другие люди и телефонные номера для коммутируемых коммутируемых сетей (PSTN), заблокированные пользователем Teams, указаны в списке заблокированных контактов пользователя в Teams.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-131">Blocked Skype users, along with other people and public switched telephone network (PSTN) phone numbers that a Teams user has blocked, are listed on the user's blocked contact list in Teams.</span></span>

## <a name="limitations"></a><span data-ttu-id="0e2c6-132">Предел</span><span class="sxs-lookup"><span data-stu-id="0e2c6-132">Limitations</span></span>

- <span data-ttu-id="0e2c6-133">Беседы — это только текст.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-133">Conversations are text-only.</span></span> <span data-ttu-id="0e2c6-134">Это означает, что вы не можете использовать форматированный формат, @mentions, эмодзи и другие функции чата, доступные в [чате для общения с родными группами](native-chat-for-external-users.md).</span><span class="sxs-lookup"><span data-stu-id="0e2c6-134">This means that there's no rich formatting, @mentions, emojis, or other any of the other chat features that are available in a [native Teams chat experience](native-chat-for-external-users.md).</span></span>
- <span data-ttu-id="0e2c6-135">Беседы работают только один на один.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-135">Conversations are one-on-one only.</span></span> <span data-ttu-id="0e2c6-136">Групповая беседа не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-136">Group chats aren't supported.</span></span>
- <span data-ttu-id="0e2c6-137">Пользователи Teams и пользователи Skype не могут видеть состояние присутствия друг друга.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-137">Teams users and Skype users can't see each other's presence.</span></span>
- <span data-ttu-id="0e2c6-138">Поиск пользователей Skype с помощью идентификатора Skype или номера телефона не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-138">Searching for Skype users by using their Skype ID or phone number isn't supported.</span></span>
- <span data-ttu-id="0e2c6-139">Пользователи Skype не могут вызвать пользователей Teams, которые настроили переадресацию звонков на другой номер пользователя, номер представителя или номер КОММУТИРУЕМой телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-139">Skype users can't call Teams users who set up call forwarding to another user's number, a delegate's number, or a Public Switched Telephone Network (PSTN) number.</span></span>  <span data-ttu-id="0e2c6-140">Поддерживается только Голосовая почта.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-140">Only voicemail is supported.</span></span>
- <span data-ttu-id="0e2c6-141">Эскалация взаимодействия, групповые вызовы и собрания не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-141">Interop escalation, group calls, and meetings aren't supported.</span></span>
- <span data-ttu-id="0e2c6-142">Возможность представителю вызвать пользователя Skype от имени пользователя Teams не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-142">The ability for a delegate to call a Skype user on behalf of a Teams user isn't supported.</span></span>
- <span data-ttu-id="0e2c6-143">Демонстрация экрана с помощью чата не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-143">Screen sharing with chat isn't supported.</span></span>

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a><span data-ttu-id="0e2c6-144">Укажите, могут ли пользователи Teams общаться с пользователями Skype</span><span class="sxs-lookup"><span data-stu-id="0e2c6-144">Set whether Teams users can communicate with Skype users</span></span>

<span data-ttu-id="0e2c6-145">Как администратор вы используете центр администрирования Microsoft Teams или PowerShell для настройки параметров внешнего доступа, чтобы управлять тем, могут ли пользователи Teams в Организации общаться с пользователями Skype.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-145">As an admin, you use the Microsoft Teams admin center or PowerShell to set external access settings to control whether Teams users in your organization can communicate with Skype users.</span></span> <span data-ttu-id="0e2c6-146">По умолчанию эта возможность включена для новых клиентов.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-146">By default, this capability is turned on for new tenants.</span></span> <span data-ttu-id="0e2c6-147">Тем не менее, в случае, если для вашего домена, например _sipfederationtls. contoso. com, должна быть настроена служба ИТ-администратором, необходимо, чтобы следующая запись DNS SRV не была доступна.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-147">However, there's a prerequisite that the following DNS SRV record needs to be configured by the IT Admin if not already available for your domain, for example _sipfederationtls.contoso.com.</span></span>  

<span data-ttu-id="0e2c6-148">**Служба** : sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="0e2c6-148">**Service** : sipfederationtls</span></span><br/>
<span data-ttu-id="0e2c6-149">**Протокол** : TCP</span><span class="sxs-lookup"><span data-stu-id="0e2c6-149">**Protocol** : TCP</span></span><br/>
<span data-ttu-id="0e2c6-150">**Priority (приоритет** ): 100</span><span class="sxs-lookup"><span data-stu-id="0e2c6-150">**Priority** : 100</span></span><br/>
<span data-ttu-id="0e2c6-151">**Вес** : 1</span><span class="sxs-lookup"><span data-stu-id="0e2c6-151">**Weight** : 1</span></span><br/>
<span data-ttu-id="0e2c6-152">**Порт** : 5061</span><span class="sxs-lookup"><span data-stu-id="0e2c6-152">**Port** : 5061</span></span><br/>
<span data-ttu-id="0e2c6-153">**Target (назначение** ): sipfed.Online.Lync.com</span><span class="sxs-lookup"><span data-stu-id="0e2c6-153">**Target** : sipfed.online.lync.com</span></span>

<span data-ttu-id="0e2c6-154">Если вы перешли с Skype для бизнеса на Teams, в Teams будут перенесены параметры внешней связи, настроенные в центре администрирования Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-154">If you upgraded from Skype for Business to Teams, the external communications settings that you configured in the Skype for Business admin center are migrated to Teams.</span></span>

### <a name="in-the-microsoft-teams-admin-center"></a><span data-ttu-id="0e2c6-155">В центре администрирования Microsoft Teams </span><span class="sxs-lookup"><span data-stu-id="0e2c6-155">In the Microsoft Teams admin center</span></span>

<span data-ttu-id="0e2c6-156">В центре администрирования Microsoft Teams перейдите к **параметрам уровня Организации**  >  **внешний доступ** , а затем включите пользователей для **общения с пользователями Skype**.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-156">In the Microsoft Teams admin center, go to **Org-wide settings** > **External access** , and then turn on **Users can communicate with Skype users**.</span></span> <span data-ttu-id="0e2c6-157">Пошаговое руководство по настройке этого и других параметров внешнего доступа можно найти [в разделе Управление внешним доступом в Teams](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains).</span><span class="sxs-lookup"><span data-stu-id="0e2c6-157">For step-by-step guidance on how to configure this and other external access settings, see [Manage external access in Teams](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0e2c6-158">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e2c6-158">Using PowerShell</span></span>

<span data-ttu-id="0e2c6-159">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-159">Do the following:</span></span> 
1. <span data-ttu-id="0e2c6-160">Используйте командлет [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) вместе с ```EnablePublicCloudAccess``` параметром, чтобы управлять тем, могут ли пользователи Teams общаться с пользователями Skype.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-160">Use the [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) cmdlet together with the ```EnablePublicCloudAccess``` parameter to control whether Teams users can communicate with Skype users.</span></span> <span data-ttu-id="0e2c6-161">Задать параметр, чтобы ```true``` Разрешить пользователям команды общаться с пользователями Skype.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-161">Setting the parameter to ```true``` allows Teams users to communicate with Skype users.</span></span> <span data-ttu-id="0e2c6-162">Вы можете использовать этот ```EnablePublicCloudAudioVideoAccess``` параметр, чтобы включить или отключить голосовые и видеозвонки.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-162">You can use the ```EnablePublicCloudAudioVideoAccess``` parameter to enable/disable audio/video calls.</span></span>

2. <span data-ttu-id="0e2c6-163">Используйте командлет [Set-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) вместе с ```Provider``` параметром Set, чтобы ```"WindowsLive"``` Пользователи Teams могли общаться с пользователями Skype.</span><span class="sxs-lookup"><span data-stu-id="0e2c6-163">Use the [Set-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet together with the ```Provider``` parameter set to ```"WindowsLive"``` so that Teams users can communicate with Skype users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0e2c6-164">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0e2c6-164">Related topics</span></span>

- [<span data-ttu-id="0e2c6-165">Управление внешним доступом в Teams</span><span class="sxs-lookup"><span data-stu-id="0e2c6-165">Manage external access in Teams</span></span>](manage-external-access.md)
- [<span data-ttu-id="0e2c6-166">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="0e2c6-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
