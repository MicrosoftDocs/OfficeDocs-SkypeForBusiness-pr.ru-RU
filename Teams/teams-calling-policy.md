---
title: Политики звонков в Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Сведения о том, как создавать, изменять и добавлять пользователей в пользовательские политики звонков в Microsoft Teams, а также различные параметры политики вызова.
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 030be626574e7acd3aa2116595acaba757eaa5af
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "44942040"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="7dc3b-103">Политики звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7dc3b-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="7dc3b-104">В Microsoft Teams политики вызовов определяют, какие функции переадресации звонков и вызовов доступны для пользователей.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="7dc3b-105">Политики звонков определяют, может ли пользователь выполнять закрытые звонки, использовать переадресацию звонков или одновременную связь с другими пользователями или внешними телефонами, перенаправлять звонки на голосовую почту, отправлять звонки в группы звонков, использовать делегирование для входящих и исходящих вызовов и т. д.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to call groups, use delegation for inbound and outbound calls, and so on.</span></span>

<span data-ttu-id="7dc3b-106">Вы можете использовать глобальную политику (по умолчанию для всей организации), созданную автоматически, а также создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-106">You can use the global (Org-wide default) policy that's created automatically or create and assign custom policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="7dc3b-107">Создание политики с пользовательскими вызовами</span><span class="sxs-lookup"><span data-stu-id="7dc3b-107">Create a custom calling policy</span></span>

<span data-ttu-id="7dc3b-108">Выполните указанные ниже действия, чтобы создать политику настраиваемого вызова.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="7dc3b-109">В левой области навигации центра администрирования Microsoft Teams перейдите на вкладку политики **голосовых**  >  **вызовов**.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="7dc3b-110">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-110">Select **Add**.</span></span>
3. <span data-ttu-id="7dc3b-111">Включите или отключите функции, которые вы хотите использовать в политике звонков.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="7dc3b-112">Чтобы указать, могут ли пользователи перенаправлять входящие звонки на голосовую почту, выберите параметр **включена** или **управляемая пользователем**.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="7dc3b-113">Чтобы отключить маршрутизацию на голосовую почту, выберите **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="7dc3b-114">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-114">Select **Save**.</span></span>

## <a name="edit-a-calling-policy"></a><span data-ttu-id="7dc3b-115">Изменение политики вызова</span><span class="sxs-lookup"><span data-stu-id="7dc3b-115">Edit a calling policy</span></span>

<span data-ttu-id="7dc3b-116">Чтобы изменить существующую политику звонков, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-116">Follow these steps to edit an existing calling policy.</span></span>

1. <span data-ttu-id="7dc3b-117">В левой области навигации центра администрирования Microsoft Teams выберите политики **голосовых**  >  **вызовов**.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="7dc3b-118">Щелкните значок рядом с политикой, которую вы хотите изменить, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="7dc3b-119">Внесите нужные изменения и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="7dc3b-120">Назначение пользователям политики звонков</span><span class="sxs-lookup"><span data-stu-id="7dc3b-120">Assign a custom calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a><span data-ttu-id="7dc3b-121">Параметры политики вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="7dc3b-121">Calling policy settings</span></span>

<span data-ttu-id="7dc3b-122">Ниже приведены параметры, которые можно настроить для политик звонков.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-122">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="7dc3b-123">Совершение приватных звонков</span><span class="sxs-lookup"><span data-stu-id="7dc3b-123">Make private calls</span></span>

<span data-ttu-id="7dc3b-124">Этот параметр управляет всеми возможностями звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-124">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="7dc3b-125">Отключите этот параметр, чтобы отключить все функции звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-125">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="7dc3b-126">Переадресация звонков и одновременный Звонок людям из вашей организации</span><span class="sxs-lookup"><span data-stu-id="7dc3b-126">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="7dc3b-127">Этот параметр определяет, могут ли входящие звонки быть переадресованы другим пользователям или могут звонить другим абонентам одновременно.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-127">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="7dc3b-128">Переадресация звонков и одновременные звонки на внешние телефонные номера</span><span class="sxs-lookup"><span data-stu-id="7dc3b-128">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="7dc3b-129">Этот параметр определяет, можно ли перенаправлять входящие звонки на внешний номер, чтобы звонить за внешний номер.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-129">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="7dc3b-130">Голосовая почта доступна для маршрутизации входящих звонков</span><span class="sxs-lookup"><span data-stu-id="7dc3b-130">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="7dc3b-131">Этот параметр позволяет отправлять входящие звонки в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-131">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="7dc3b-132">Допустимые параметры:</span><span class="sxs-lookup"><span data-stu-id="7dc3b-132">Valid options are:</span></span>

- <span data-ttu-id="7dc3b-133">**Enabled (включено** ) Голосовая почта всегда доступна для входящих звонков.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-133">**Enabled** Voicemail is always available for inbound calls.</span></span>
- <span data-ttu-id="7dc3b-134">**Отключено**  Голосовая почта недоступна для входящих звонков.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-134">**Disabled**  Voicemail is not available for inbound calls.</span></span>
- <span data-ttu-id="7dc3b-135">**Управляемый пользователем** Пользователи могут определить, нужно ли использовать голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-135">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="7dc3b-136">Входящие звонки могут перенаправляться в группы звонков</span><span class="sxs-lookup"><span data-stu-id="7dc3b-136">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="7dc3b-137">Этот параметр определяет, могут ли входящие звонки перенаправляться в группу звонков.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-137">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="7dc3b-138">Разрешить делегирование входящих и исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="7dc3b-138">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="7dc3b-139">Этот параметр включает маршрутизацию входящих звонков в делегаты, позволяя делегатам совершать исходящие вызовы от имени пользователей, которым они делегированы разрешения.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-139">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="7dc3b-140">Дополнительные сведения можно найти в разделе [предоставление доступа к телефонной линии представителем](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span><span class="sxs-lookup"><span data-stu-id="7dc3b-140">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="7dc3b-141">Запрет на прием и отправку звонков через PSTN</span><span class="sxs-lookup"><span data-stu-id="7dc3b-141">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="7dc3b-142">Если этот параметр **включен, звонки будут** отправляться через PSTN и взиматься плата, а не отправляются по сети и обходится платный звонок.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-142">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="7dc3b-143">В вызове доступна занятая</span><span class="sxs-lookup"><span data-stu-id="7dc3b-143">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="7dc3b-144">Busy (параметры доступности) — это новый параметр, который позволяет настроить способ обработки входящих звонков, когда пользователь уже находится на звонке или конференции или покинул Звонок на удержание.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-144">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="7dc3b-145">Новые или входящие звонки могут быть отвергнуты с помощью сигнала "занято".</span><span class="sxs-lookup"><span data-stu-id="7dc3b-145">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="7dc3b-146">Вы можете включить параметры доступности на уровне клиента или на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-146">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="7dc3b-147">Независимо от того, как настроены параметры доступности, пользователи во время звонка или конференции или на удержании с помощью звонка не могут инициировать новые звонки и конференции.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-147">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="7dc3b-148">Этот параметр отключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-148">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="7dc3b-149">Разрешить звонки через Интернет-КТСОП</span><span class="sxs-lookup"><span data-stu-id="7dc3b-149">Allow web PSTN calling</span></span>

<span data-ttu-id="7dc3b-150">Этот параметр позволяет пользователям вызывать номера PSTN с помощью веб-клиента Teams.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-150">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="7dc3b-151">Разрешить музыку на удержании</span><span class="sxs-lookup"><span data-stu-id="7dc3b-151">Allow music on hold</span></span>

<span data-ttu-id="7dc3b-152">Этот параметр позволяет включить или выключить удержание музыки при помещении абонента PSTN на удержание.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-152">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="7dc3b-153">По умолчанию она включена.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-153">It's turned on by default.</span></span> <span data-ttu-id="7dc3b-154">Этот параметр не применяется к функциям подсоединения для подсоединения и переначальника, и в настоящее время доступна только через PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7dc3b-154">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7dc3b-155">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7dc3b-155">Related topics</span></span>

[<span data-ttu-id="7dc3b-156">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="7dc3b-156">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[<span data-ttu-id="7dc3b-157">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="7dc3b-157">Assign policies to your users in Teams</span></span>](assign-policies.md)
