---
title: Политики звонков в Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
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
ms.openlocfilehash: a94bf072aa4db0ba0b3f65fb5340c22ab09581e4
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43914076"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="a19b4-103">Политики звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a19b4-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="a19b4-104">В Microsoft Teams политики вызовов определяют, какие функции переадресации звонков и вызовов доступны для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a19b4-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="a19b4-105">Политики звонков определяют, может ли пользователь выполнять закрытые звонки, использовать переадресацию звонков или одновременную связь с другими пользователями или внешними телефонами, перенаправлять звонки на голосовую почту, отправлять звонки в группы звонков, использовать делегирование для входящих и исходящих вызовов и т. д.</span><span class="sxs-lookup"><span data-stu-id="a19b4-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="a19b4-106">Глобальная политика по умолчанию создается автоматически, но администраторы также могут создавать и назначать пользовательские политики вызова.</span><span class="sxs-lookup"><span data-stu-id="a19b4-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="a19b4-107">Создание политики с пользовательскими вызовами</span><span class="sxs-lookup"><span data-stu-id="a19b4-107">Create a custom calling policy</span></span>

<span data-ttu-id="a19b4-108">Выполните указанные ниже действия, чтобы создать политику настраиваемого вызова.</span><span class="sxs-lookup"><span data-stu-id="a19b4-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="a19b4-109">В центре администрирования Microsoft Teams выберите политика **голосовых** > **вызовов**.</span><span class="sxs-lookup"><span data-stu-id="a19b4-109">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="a19b4-110">Выберите пункт **создать политику**.</span><span class="sxs-lookup"><span data-stu-id="a19b4-110">Select **New policy**.</span></span>
3. <span data-ttu-id="a19b4-111">Включите функции, которые вы хотите использовать в политике звонков.</span><span class="sxs-lookup"><span data-stu-id="a19b4-111">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="a19b4-112">По умолчанию все выделенные компоненты **отключены** .</span><span class="sxs-lookup"><span data-stu-id="a19b4-112">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="a19b4-113">Чтобы указать, могут ли пользователи перенаправлять входящие звонки на голосовую почту, установите флажок **всегда включено** или **управляется пользователем**.</span><span class="sxs-lookup"><span data-stu-id="a19b4-113">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="a19b4-114">Чтобы отключить маршрутизацию на голосовую почту, установите флажок **всегда отключено**.</span><span class="sxs-lookup"><span data-stu-id="a19b4-114">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="a19b4-115">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a19b4-115">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="a19b4-116">Изменение существующей политики вызова</span><span class="sxs-lookup"><span data-stu-id="a19b4-116">Modify an existing calling policy</span></span>

<span data-ttu-id="a19b4-117">Чтобы изменить существующую политику звонков, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a19b4-117">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="a19b4-118">В центре администрирования Microsoft Teams выберите политика **голосовых** > **вызовов**.</span><span class="sxs-lookup"><span data-stu-id="a19b4-118">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="a19b4-119">Щелкните значок рядом с политикой, которую вы хотите изменить, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="a19b4-119">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="a19b4-120">Включите функции, которые вы хотите использовать в политике звонков.</span><span class="sxs-lookup"><span data-stu-id="a19b4-120">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="a19b4-121">По умолчанию все выделенные компоненты **отключены** .</span><span class="sxs-lookup"><span data-stu-id="a19b4-121">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="a19b4-122">Чтобы указать, могут ли пользователи перенаправлять входящие звонки на голосовую почту, установите флажок **всегда включено** или **управляется пользователем**.</span><span class="sxs-lookup"><span data-stu-id="a19b4-122">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="a19b4-123">Чтобы отключить маршрутизацию на голосовую почту, установите флажок **всегда отключено**.</span><span class="sxs-lookup"><span data-stu-id="a19b4-123">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="a19b4-124">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a19b4-124">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="a19b4-125">Назначение пользователю политики звонков</span><span class="sxs-lookup"><span data-stu-id="a19b4-125">Assign a calling policy to a user</span></span>

<span data-ttu-id="a19b4-126">Выполните указанные ниже действия, чтобы назначить пользователю специальную политику звонков.</span><span class="sxs-lookup"><span data-stu-id="a19b4-126">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="a19b4-127">В центре администрирования Microsoft Teams выберите политика **голосовых** > **вызовов**.</span><span class="sxs-lookup"><span data-stu-id="a19b4-127">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="a19b4-128">Щелкните значок рядом с именем политики, чтобы выбрать его, а затем выберите пункт **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="a19b4-128">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="a19b4-129">В области **Manage Users (Управление пользователями** ) найдите имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="a19b4-129">In the **Manage users** pane, search for the user's name.</span></span> <span data-ttu-id="a19b4-130">(Необходимо ввести не менее трех знаков.)</span><span class="sxs-lookup"><span data-stu-id="a19b4-130">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="a19b4-131">Выберите имя пользователя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a19b4-131">Select the user's name, and then select **Add**.</span></span>
5. <span data-ttu-id="a19b4-132">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a19b4-132">Select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="a19b4-133">Параметры политики вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="a19b4-133">Calling policy settings</span></span>

<span data-ttu-id="a19b4-134">Используйте указанные ниже параметры для создания политики с пользовательскими вызовами.</span><span class="sxs-lookup"><span data-stu-id="a19b4-134">Use the following settings to create a custom calling policy.</span></span>

### <a name="user-can-make-private-calls"></a><span data-ttu-id="a19b4-135">Пользователь может совершать закрытые звонки</span><span class="sxs-lookup"><span data-stu-id="a19b4-135">User can make private calls</span></span>

<span data-ttu-id="a19b4-136">Этот параметр управляет всеми возможностями звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="a19b4-136">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="a19b4-137">Отключите этот параметр, чтобы отключить все функции звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="a19b4-137">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a><span data-ttu-id="a19b4-138">Переадресация звонков и одновременный Звонок другим пользователям</span><span class="sxs-lookup"><span data-stu-id="a19b4-138">Call forwarding and simultaneous ringing to other users</span></span>

<span data-ttu-id="a19b4-139">Этот параметр определяет, могут ли входящие звонки быть переадресованы другим пользователям или могут звонить другим абонентам одновременно.</span><span class="sxs-lookup"><span data-stu-id="a19b4-139">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="a19b4-140">Переадресация звонков и одновременные звонки на внешние телефонные номера</span><span class="sxs-lookup"><span data-stu-id="a19b4-140">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="a19b4-141">Этот параметр определяет, можно ли перенаправлять входящие звонки на внешний номер, чтобы звонить за внешний номер.</span><span class="sxs-lookup"><span data-stu-id="a19b4-141">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a><span data-ttu-id="a19b4-142">Голосовая почта доступна для маршрутизации входящих звонков пользователям</span><span class="sxs-lookup"><span data-stu-id="a19b4-142">Voicemail is available for routing inbound calls to users</span></span>

<span data-ttu-id="a19b4-143">Этот параметр позволяет отправлять входящие звонки в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="a19b4-143">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="a19b4-144">Допустимые параметры:</span><span class="sxs-lookup"><span data-stu-id="a19b4-144">Valid options are:</span></span>

   - <span data-ttu-id="a19b4-145">**Всегда включено** Голосовая почта всегда доступна для входящих звонков.</span><span class="sxs-lookup"><span data-stu-id="a19b4-145">**Always enabled** Voicemail is always available for inbound calls.</span></span> 
   - <span data-ttu-id="a19b4-146">**Всегда отключено**  Голосовая почта недоступна для входящих звонков.</span><span class="sxs-lookup"><span data-stu-id="a19b4-146">**Always disabled**  Voicemail is not available for inbound calls.</span></span> 
   - <span data-ttu-id="a19b4-147">**Управляемый пользователем**.</span><span class="sxs-lookup"><span data-stu-id="a19b4-147">**User controlled**.</span></span> <span data-ttu-id="a19b4-148">Пользователи могут определить, нужно ли использовать голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="a19b4-148">Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="a19b4-149">Входящие звонки могут перенаправляться в группы звонков</span><span class="sxs-lookup"><span data-stu-id="a19b4-149">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="a19b4-150">Этот параметр определяет, могут ли входящие звонки перенаправляться в группу звонков.</span><span class="sxs-lookup"><span data-stu-id="a19b4-150">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="a19b4-151">Разрешить делегирование входящих и исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="a19b4-151">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="a19b4-152">Этот параметр включает маршрутизацию входящих звонков в делегаты, позволяя делегатам совершать исходящие вызовы от имени пользователей, которым они делегированы разрешения.</span><span class="sxs-lookup"><span data-stu-id="a19b4-152">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="a19b4-153">Дополнительные сведения можно найти в разделе [предоставление доступа к телефонной линии представителем](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span><span class="sxs-lookup"><span data-stu-id="a19b4-153">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="a19b4-154">Запрет на прием и отправку звонков через PSTN</span><span class="sxs-lookup"><span data-stu-id="a19b4-154">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="a19b4-155">Если этот параметр **включен, звонки будут** отправляться через PSTN и взиматься плата, а не отправляются по сети и обходится платный звонок.</span><span class="sxs-lookup"><span data-stu-id="a19b4-155">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="a19b4-156">В вызове доступна занятая</span><span class="sxs-lookup"><span data-stu-id="a19b4-156">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="a19b4-157">Busy on (параметры занятости)) — это новый параметр в политиках вызова Teams, который позволяет настроить способ обработки входящих звонков, когда пользователь уже находится на звонке или конференции или покинул Звонок на удержание.</span><span class="sxs-lookup"><span data-stu-id="a19b4-157">Busy on Busy (Busy Options)) is a new setting in Teams calling policies that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="a19b4-158">Новые или входящие звонки могут быть отвергнуты с помощью сигнала "занято".</span><span class="sxs-lookup"><span data-stu-id="a19b4-158">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="a19b4-159">Вы можете включить параметры доступности на уровне клиента или на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="a19b4-159">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="a19b4-160">Независимо от того, как настроены параметры доступности, пользователи во время звонка или конференции или на удержании с помощью звонка не могут инициировать новые звонки и конференции.</span><span class="sxs-lookup"><span data-stu-id="a19b4-160">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="a19b4-161">Этот параметр отключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a19b4-161">This setting is disabled by default.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="a19b4-162">Разрешить музыку на удержании</span><span class="sxs-lookup"><span data-stu-id="a19b4-162">Allow music on hold</span></span>

<span data-ttu-id="a19b4-163">Этот параметр позволяет включить или выключить удержание музыки при помещении абонента PSTN на удержание.</span><span class="sxs-lookup"><span data-stu-id="a19b4-163">This settings allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="a19b4-164">По умолчанию она включена.</span><span class="sxs-lookup"><span data-stu-id="a19b4-164">It is turned on by default.</span></span> <span data-ttu-id="a19b4-165">Этот параметр не применяется к функциям присоединения к приостановке и делегированию для начальника, и только в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a19b4-165">This setting does not apply to call park and boss delegate features, and is only available via powershell currently.</span></span> 

## <a name="see-also"></a><span data-ttu-id="a19b4-166">См. также</span><span class="sxs-lookup"><span data-stu-id="a19b4-166">See also</span></span>

[<span data-ttu-id="a19b4-167">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="a19b4-167">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)
