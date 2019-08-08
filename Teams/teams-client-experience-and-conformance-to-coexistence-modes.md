---
title: Взаимодействие с клиентом Teams и соответствие режимам сосуществования
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Взаимодействие с клиентами Teams и комформанце с режимами сосуществования
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 85f74b63f465bd0004e8b9a2ef93c79b00196495
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243909"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="9949a-103">Взаимодействие с клиентом Teams и соответствие режимам сосуществования</span><span class="sxs-lookup"><span data-stu-id="9949a-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="9949a-104">На этой странице описаны важные и недавно использованные изменения поведения клиента Teams, когда пользователи находятся в любых режимах Skype для бизнеса (Сфбонли, Сфбвистеамсколлаб, Сфбвистеамсколлабандмитингс).</span><span class="sxs-lookup"><span data-stu-id="9949a-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="9949a-105">Цель режима совместного существования состоит в том, чтобы предоставить пользователям простой и предсказуемый опыт для конечных пользователей в том случае, если Организация переходит из Skype для бизнеса в Teams.</span><span class="sxs-lookup"><span data-stu-id="9949a-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="9949a-106">Для Организации, перемещающейся в Teams, режим Теамсонли является конечным пунктом для каждого пользователя, хотя ему не нужно назначать Теамсонли (или любой другой режим) одновременно.</span><span class="sxs-lookup"><span data-stu-id="9949a-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="9949a-107">Перед тем как пользователи приходили к режиму Теамсонли, организации могут использовать любой из режимов Skype для бизнеса (Сфбонли, Сфбвистеамсколлаб, Сфбвистеамсколлабандмитингс), чтобы обеспечить предсказуемую связь между пользователями, которые еще не являются Теамсонли.</span><span class="sxs-lookup"><span data-stu-id="9949a-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="9949a-108">Когда пользователь входит в любой из режимов Skype для бизнеса, все входящие разговоры и звонки перенаправляются клиенту Skype для бизнеса пользователя.</span><span class="sxs-lookup"><span data-stu-id="9949a-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="9949a-109">Чтобы избежать путаницы и удостовериться в том, что функция маршрутизации, вызов и чат в клиенте Teams отключена, когда пользователь входит в любой из режимов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9949a-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="9949a-110">Аналогичным образом планирование собраний в Teams явным образом отключается, если пользователи находятся в режимах Сфбонли или Сфбвистеамсколлаб, и явно включаются, когда пользователь находится в режиме Сфбвистеамсколлабандмитингс.</span><span class="sxs-lookup"><span data-stu-id="9949a-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="9949a-111">Изменение доступных функциональных возможностей клиента Teams в зависимости от режима</span><span class="sxs-lookup"><span data-stu-id="9949a-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="9949a-112">Доступные функции в Teams зависят от режима сосуществования пользователя, который задается с помощью Теамсупградеполици.</span><span class="sxs-lookup"><span data-stu-id="9949a-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="9949a-113">В приведенной ниже таблице показано, как это происходит.</span><span class="sxs-lookup"><span data-stu-id="9949a-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="9949a-114">Эффективный режим пользователя</span><span class="sxs-lookup"><span data-stu-id="9949a-114">User's effective mode</span></span>|<span data-ttu-id="9949a-115">Взаимодействие с клиентом Teams</span><span class="sxs-lookup"><span data-stu-id="9949a-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="9949a-116">Любой режим Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9949a-116">Any Skype for Business mode</span></span>|<span data-ttu-id="9949a-117">Звонки и чат отключены.</span><span class="sxs-lookup"><span data-stu-id="9949a-117">Calling and Chat are disabled.</span></span>|
|<span data-ttu-id="9949a-118">сфбвистеамсколлабандмитингс</span><span class="sxs-lookup"><span data-stu-id="9949a-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="9949a-119">Доступно планирование собраний</span><span class="sxs-lookup"><span data-stu-id="9949a-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="9949a-120">Сфбвистеамсколлаб или Сфбонли<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9949a-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="9949a-121">Планирование собраний недоступно</span><span class="sxs-lookup"><span data-stu-id="9949a-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="9949a-122">На следующих снимках экрана показано различие между режимами Теамсонли и острова и всеми остальными режимами.</span><span class="sxs-lookup"><span data-stu-id="9949a-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="9949a-123">Обратите внимание на то, что значки чата и вызова доступны в режиме "Теамсонли" или "острова" (на рисунке слева), но не в других режимах (на снимке экрана справа):</span><span class="sxs-lookup"><span data-stu-id="9949a-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Параллельное сравнение режимов групп](media/teams-mode-comparison.png)


 
<span data-ttu-id="9949a-125">**Примечание.**
<sup>1</sup> в настоящее время поведение сфбвистеамсколлаб и сфбонли работает одинаково, но в режиме сфбонли также можно отключить поддержку каналов и файлов в Teams; Однако в настоящее время нет параметра, который позволяет отключить эту функцию в Teams.</span><span class="sxs-lookup"><span data-stu-id="9949a-125">**Note:**
<sup>1</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="9949a-126">Влияние режима для других параметров политики</span><span class="sxs-lookup"><span data-stu-id="9949a-126">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="9949a-127">Как описано выше, режим сосуществования пользователя влияет на функциональные возможности, доступные в клиенте Teams в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="9949a-127">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="9949a-128">Это означает, что значение Mode может иметь приоритет над значением других параметров политики, в зависимости от режима.</span><span class="sxs-lookup"><span data-stu-id="9949a-128">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="9949a-129">В частности, режим сосуществования влияет на то, выполняются ли следующие параметры политики.</span><span class="sxs-lookup"><span data-stu-id="9949a-129">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="9949a-130">**Модальность (приложение)**</span><span class="sxs-lookup"><span data-stu-id="9949a-130">**Modality (App)**</span></span>|<span data-ttu-id="9949a-131">**Политика. параметр**</span><span class="sxs-lookup"><span data-stu-id="9949a-131">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="9949a-132">Chat</span><span class="sxs-lookup"><span data-stu-id="9949a-132">Chat</span></span>|<span data-ttu-id="9949a-133">Теамсмессагингполици. Алловусерчат</span><span class="sxs-lookup"><span data-stu-id="9949a-133">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="9949a-134">Звонки</span><span class="sxs-lookup"><span data-stu-id="9949a-134">Calling</span></span>|<span data-ttu-id="9949a-135">Теамскаллингполици. Алловприватекаллинг</span><span class="sxs-lookup"><span data-stu-id="9949a-135">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="9949a-136">Планирование собраний</span><span class="sxs-lookup"><span data-stu-id="9949a-136">Meeting scheduling</span></span>|<span data-ttu-id="9949a-137">Теамсмитингполици. Алловприватемитингсчедулинг</span><span class="sxs-lookup"><span data-stu-id="9949a-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="9949a-138">Теамсмитингполици. Алловчаннелмитингсчедулинг</span><span class="sxs-lookup"><span data-stu-id="9949a-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="9949a-139">Администраторам *не* нужно явно задавать эти параметры политики при использовании режима совместного существования, но важно понимать, что эти параметры работают следующим образом для определенного режима.</span><span class="sxs-lookup"><span data-stu-id="9949a-139">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="9949a-140">Режиме</span><span class="sxs-lookup"><span data-stu-id="9949a-140">Mode</span></span>|<span data-ttu-id="9949a-141">алловусерчат</span><span class="sxs-lookup"><span data-stu-id="9949a-141">AllowUserChat</span></span>|<span data-ttu-id="9949a-142">алловприватекаллинг</span><span class="sxs-lookup"><span data-stu-id="9949a-142">AllowPrivateCalling</span></span>|<span data-ttu-id="9949a-143">алловприватемитингсчедулинг</span><span class="sxs-lookup"><span data-stu-id="9949a-143">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="9949a-144">алловчаннелмитингсчедулинг</span><span class="sxs-lookup"><span data-stu-id="9949a-144">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="9949a-145">Теамсонли или острова</span><span class="sxs-lookup"><span data-stu-id="9949a-145">TeamsOnly or Islands</span></span>|<span data-ttu-id="9949a-146">Включено</span><span class="sxs-lookup"><span data-stu-id="9949a-146">Enabled</span></span>|<span data-ttu-id="9949a-147">Включено</span><span class="sxs-lookup"><span data-stu-id="9949a-147">Enabled</span></span>|<span data-ttu-id="9949a-148">Включено</span><span class="sxs-lookup"><span data-stu-id="9949a-148">Enabled</span></span>|<span data-ttu-id="9949a-149">Включено</span><span class="sxs-lookup"><span data-stu-id="9949a-149">Enabled</span></span>|
|<span data-ttu-id="9949a-150">сфбвистеамсколлабандмитингс</span><span class="sxs-lookup"><span data-stu-id="9949a-150">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="9949a-151">Отключено</span><span class="sxs-lookup"><span data-stu-id="9949a-151">Disabled</span></span>|<span data-ttu-id="9949a-152">Отключено</span><span class="sxs-lookup"><span data-stu-id="9949a-152">Disabled</span></span>|<span data-ttu-id="9949a-153">Включено</span><span class="sxs-lookup"><span data-stu-id="9949a-153">Enabled</span></span>|<span data-ttu-id="9949a-154">Включено</span><span class="sxs-lookup"><span data-stu-id="9949a-154">Enabled</span></span>|
|<span data-ttu-id="9949a-155">Сфбвистеамсколлаб или Сфбонли</span><span class="sxs-lookup"><span data-stu-id="9949a-155">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="9949a-156">Отключено</span><span class="sxs-lookup"><span data-stu-id="9949a-156">Disabled</span></span>|<span data-ttu-id="9949a-157">Отключено</span><span class="sxs-lookup"><span data-stu-id="9949a-157">Disabled</span></span>|<span data-ttu-id="9949a-158">Отключено</span><span class="sxs-lookup"><span data-stu-id="9949a-158">Disabled</span></span>|<span data-ttu-id="9949a-159">Отключено</span><span class="sxs-lookup"><span data-stu-id="9949a-159">Disabled</span></span>|
||||||

<span data-ttu-id="9949a-160">При использовании PowerShell `Grant-CsTeamsUpgradePolicy` командлет проверяет конфигурацию соответствующих параметров в Теамсмессагингполици, Теамскаллингполици и теамсмитингполици, чтобы определить, будут ли эти параметры заменены теамсупградеполици и, если да, Информационное сообщение предоставляется в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9949a-160">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="9949a-161">Как указано выше, больше не нужно настраивать эти параметры политики.</span><span class="sxs-lookup"><span data-stu-id="9949a-161">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="9949a-162">Ниже показано, как выглядит предупреждение PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9949a-162">Below is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="9949a-163">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9949a-163">Related topics</span></span>

[<span data-ttu-id="9949a-164">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9949a-164">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




