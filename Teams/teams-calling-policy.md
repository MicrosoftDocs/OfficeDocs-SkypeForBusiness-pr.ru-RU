---
title: Политики звонков в Microsoft Teams
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Узнайте, как создавать, изменять и добавлять пользователей к настраиваемой политике звонков в Microsoft Teams, а также различные параметры политики звонков.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5e3cc466d855f55f63f34e798443fb285dc36c9e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162681"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="e4309-103">Политики звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e4309-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="e4309-104">В Microsoft Teams политики звонков контролируют, какие функции переадваровки звонков и звонков доступны пользователям.</span><span class="sxs-lookup"><span data-stu-id="e4309-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="e4309-105">Политики звонков определяют, может ли пользователь делать частные звонки, использовать переадружение звонков или одновременные звонки другим пользователям или внешним телефонным номерам, перенаправка звонков на голосовую почту, отправка звонков группам звонков, делегирования для входящие и исходящие звонки и так далее.</span><span class="sxs-lookup"><span data-stu-id="e4309-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to call groups, use delegation for inbound and outbound calls, and so on.</span></span>

<span data-ttu-id="e4309-106">Вы можете использовать глобальную (по умолчанию в организации) политику, созданную автоматически, или создать и назначить настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="e4309-106">You can use the global (Org-wide default) policy that's created automatically or create and assign custom policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="e4309-107">Создание настраиваемой политики звонков</span><span class="sxs-lookup"><span data-stu-id="e4309-107">Create a custom calling policy</span></span>

<span data-ttu-id="e4309-108">Чтобы создать настраиваемую политику звонков, выполните указанные здесь действия.</span><span class="sxs-lookup"><span data-stu-id="e4309-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="e4309-109">В левой области навигации Центра администрирования Microsoft Teams перейдите **к** политикам  >  **голосовых звонков.**</span><span class="sxs-lookup"><span data-stu-id="e4309-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="e4309-110">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e4309-110">Select **Add**.</span></span>
3. <span data-ttu-id="e4309-111">Включите или отключите функции, которые вы хотите использовать в политике звонков.</span><span class="sxs-lookup"><span data-stu-id="e4309-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="e4309-112">Чтобы управлять возможностью перенаправляемых звонков  на голосовую почту, выберите "Включено" или **"Пользователь".**</span><span class="sxs-lookup"><span data-stu-id="e4309-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="e4309-113">Чтобы запретить маршрутику в голосовую почту, выберите **"Отключено".**</span><span class="sxs-lookup"><span data-stu-id="e4309-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="e4309-114">Выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="e4309-114">Select **Save**.</span></span>

## <a name="edit-a-calling-policy"></a><span data-ttu-id="e4309-115">Изменение политики звонков</span><span class="sxs-lookup"><span data-stu-id="e4309-115">Edit a calling policy</span></span>

<span data-ttu-id="e4309-116">Чтобы изменить существующую политику звонков, выполните указанные здесь действия.</span><span class="sxs-lookup"><span data-stu-id="e4309-116">Follow these steps to edit an existing calling policy.</span></span>

1. <span data-ttu-id="e4309-117">В левой области навигации Центра администрирования Microsoft Teams выберите **политики**  >  **голосовых звонков.**</span><span class="sxs-lookup"><span data-stu-id="e4309-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="e4309-118">Щелкните рядом с политикой, которую вы хотите изменить, и выберите **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="e4309-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="e4309-119">Внести нужные изменения и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="e4309-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="e4309-120">Назначение пользовательской политики звонков пользователям</span><span class="sxs-lookup"><span data-stu-id="e4309-120">Assign a custom calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a><span data-ttu-id="e4309-121">Параметры политики звонков</span><span class="sxs-lookup"><span data-stu-id="e4309-121">Calling policy settings</span></span>

<span data-ttu-id="e4309-122">Ниже параметров, которые можно настроить для политик звонков.</span><span class="sxs-lookup"><span data-stu-id="e4309-122">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="e4309-123">Совершение приватных звонков</span><span class="sxs-lookup"><span data-stu-id="e4309-123">Make private calls</span></span>

<span data-ttu-id="e4309-124">Этот параметр контролирует все возможности звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="e4309-124">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="e4309-125">Отключите эту функцию, чтобы отключить все функции звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="e4309-125">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="e4309-126">Переад вызовы и одновременные вызовы для людей в организации</span><span class="sxs-lookup"><span data-stu-id="e4309-126">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="e4309-127">Этот параметр управляет возможностью переадваровки входящих звонков другим пользователям или одновременного звонка другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="e4309-127">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="e4309-128">Переадружение звонков и одновременные звонки на внешние номера телефонов</span><span class="sxs-lookup"><span data-stu-id="e4309-128">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="e4309-129">Этот параметр управляет возможностью переадваровки входящих звонков на внешний номер или одновременного звонка на внешний номер.</span><span class="sxs-lookup"><span data-stu-id="e4309-129">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="e4309-130">Голосовая почта доступна для маршрутинга входящие вызовы</span><span class="sxs-lookup"><span data-stu-id="e4309-130">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="e4309-131">Этот параметр позволяет перенаправить входящие звонки на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="e4309-131">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="e4309-132">Возможные варианты:</span><span class="sxs-lookup"><span data-stu-id="e4309-132">Valid options are:</span></span>

- <span data-ttu-id="e4309-133">**Включено** Голосовая почта всегда доступна для входящие звонков.</span><span class="sxs-lookup"><span data-stu-id="e4309-133">**Enabled** Voicemail is always available for inbound calls.</span></span>
- <span data-ttu-id="e4309-134">**Отключено**  Голосовая почта недоступна для входящие звонков.</span><span class="sxs-lookup"><span data-stu-id="e4309-134">**Disabled**  Voicemail is not available for inbound calls.</span></span>
- <span data-ttu-id="e4309-135">**Пользователь, контролируемый пользователем** Пользователи могут определять, нужна ли им голосовая почта.</span><span class="sxs-lookup"><span data-stu-id="e4309-135">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="e4309-136">Входящие звонки можно перена маршрутизовы в группы звонков</span><span class="sxs-lookup"><span data-stu-id="e4309-136">Inbound calls can be routed to call groups</span></span> 

<span data-ttu-id="e4309-137">Этот параметр управляет возможностью переадваровки входящих звонков в группу звонков.</span><span class="sxs-lookup"><span data-stu-id="e4309-137">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="e4309-138">Разрешение делегирования для входящие и исходящие звонки</span><span class="sxs-lookup"><span data-stu-id="e4309-138">Allow delegation for inbound and outbound calls</span></span>

<span data-ttu-id="e4309-139">Этот параметр позволяет перена маршрутировать входящие звонки делегатам, позволяя делегатам делать исходящие звонки от имени пользователей, которым они делегируют разрешения.</span><span class="sxs-lookup"><span data-stu-id="e4309-139">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="e4309-140">Дополнительные сведения см. в сведениях о том, как поделиться [телефонной линией с делегатом.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span><span class="sxs-lookup"><span data-stu-id="e4309-140">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="e4309-141">Предотвращение обхода платных звонков и отправка звонков через ПС</span><span class="sxs-lookup"><span data-stu-id="e4309-141">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="e4309-142">Если этот параметр установить этот параметр для параметра **"В** сети", звонки будут отправляться через ПСО и с вас взимается плата, а не через сеть и не обходить платные тарифы.</span><span class="sxs-lookup"><span data-stu-id="e4309-142">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="e4309-143">Занят в занятости, пока вы звоните</span><span class="sxs-lookup"><span data-stu-id="e4309-143">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="e4309-144">Занят (параметры занятости) — это новый параметр, который позволяет настроить обработку входящих звонков, когда пользователь уже находится в звонке или конференции или помещен на удержание.</span><span class="sxs-lookup"><span data-stu-id="e4309-144">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="e4309-145">Новые или входящие вызовы могут быть отклонены с сигналом занятости.</span><span class="sxs-lookup"><span data-stu-id="e4309-145">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="e4309-146">Вы можете включить параметры занятости на уровне клиента или на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="e4309-146">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="e4309-147">Независимо от настройки параметров занятости, пользователям в звонках и конференциях или звонках на удержание не помешает проведение новых звонков или конференций.</span><span class="sxs-lookup"><span data-stu-id="e4309-147">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="e4309-148">По умолчанию этот параметр отключен.</span><span class="sxs-lookup"><span data-stu-id="e4309-148">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="e4309-149">Разрешить вызовы через ДНР через Интернет</span><span class="sxs-lookup"><span data-stu-id="e4309-149">Allow web PSTN calling</span></span>

<span data-ttu-id="e4309-150">Этот параметр позволяет пользователям звонить на номера ННР с помощью веб-клиента Teams.</span><span class="sxs-lookup"><span data-stu-id="e4309-150">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="e4309-151">"Разрешить музыку на удержании"</span><span class="sxs-lookup"><span data-stu-id="e4309-151">Allow music on hold</span></span>

<span data-ttu-id="e4309-152">Этот параметр позволяет включить или отключить музыку на удержании, когда звонок по STN поставлен на удержание.</span><span class="sxs-lookup"><span data-stu-id="e4309-152">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="e4309-153">По умолчанию этот режим включен.</span><span class="sxs-lookup"><span data-stu-id="e4309-153">It's turned on by default.</span></span> <span data-ttu-id="e4309-154">Этот параметр не относится к функциям делегатов в call park и boss, и в настоящее время доступен только с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4309-154">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e4309-155">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e4309-155">Related topics</span></span>

[<span data-ttu-id="e4309-156">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="e4309-156">Set-CSTeamsCallingPolicy</span></span>](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[<span data-ttu-id="e4309-157">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="e4309-157">Assign policies to your users in Teams</span></span>](assign-policies.md)