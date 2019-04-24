---
title: Взаимодействие с клиентом Teams и соответствие режимам сосуществования
author: dearbeen
ms.author: bjwhalen
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Группы взаимодействия с пользователем и comformance режимы сосуществования
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e62dd8a19e2207f6b40864cab19a3fda48d184fe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204660"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="e439c-103">Взаимодействие с клиентом Teams и соответствие режимам сосуществования</span><span class="sxs-lookup"><span data-stu-id="e439c-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="e439c-104">На этой странице описаны важно, недавно выпущенных изменения в поведение клиента групп, когда пользователи находятся в любой из Скайп для режимов Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span><span class="sxs-lookup"><span data-stu-id="e439c-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="e439c-105">Совместная работа режимы предназначен для простой, прогнозируемый работы для конечных пользователей как организаций перехода от Скайп для бизнеса группам.</span><span class="sxs-lookup"><span data-stu-id="e439c-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="e439c-106">Для перемещения групп организации режим TeamsOnly — конечному получателю для каждого пользователя, хотя не все пользователи должны быть назначены TeamsOnly (или любой другой режим) в то же время.</span><span class="sxs-lookup"><span data-stu-id="e439c-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="e439c-107">Пользователей, достигает TeamsOnly режиме организации могут использовать любой из Скайп для бизнеса режимов (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), чтобы убедиться в прогнозируемый связи между пользователями, которые TeamsOnly и тех, кто еще не.</span><span class="sxs-lookup"><span data-stu-id="e439c-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="e439c-108">Когда пользователь находится в любой из Скайп для режимов бизнеса, все входящие чаты и вызовы направляются Скайп пользователя для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="e439c-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="e439c-109">Чтобы избежать путаницы конечного пользователя и гарантировать правильную маршрутизацию, функциональные возможности телефонной и чата в клиенте группами отключена, если пользователь не во всех Скайп для режимов Business.</span><span class="sxs-lookup"><span data-stu-id="e439c-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="e439c-110">Аналогично планирования собраний в группах явным образом отключается, когда пользователи находятся в режимах SfBOnly или SfBWithTeamsCollab и явно включены, если пользователь находится в режиме SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="e439c-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="e439c-111">Как доступные функции в клиенте команд изменяется на основе режима</span><span class="sxs-lookup"><span data-stu-id="e439c-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="e439c-112">Доступные функции в группах зависит от режима совместной работы пользователя, как набор с TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="e439c-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="e439c-113">В следующей таблице описано поведение:</span><span class="sxs-lookup"><span data-stu-id="e439c-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="e439c-114">Эффективное режим пользователя</span><span class="sxs-lookup"><span data-stu-id="e439c-114">User's effective mode</span></span>|<span data-ttu-id="e439c-115">Опытом группы клиента</span><span class="sxs-lookup"><span data-stu-id="e439c-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="e439c-116">Любой Скайп для режима бизнеса</span><span class="sxs-lookup"><span data-stu-id="e439c-116">Any Skype for Business mode</span></span>|<span data-ttu-id="e439c-117">Вызов и чата отключены.</span><span class="sxs-lookup"><span data-stu-id="e439c-117">Calling and Chat are disabled.</span></span>|
|<span data-ttu-id="e439c-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="e439c-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="e439c-119">Доступно на собрания планирования</span><span class="sxs-lookup"><span data-stu-id="e439c-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="e439c-120">SfBWithTeamsCollab или SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e439c-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="e439c-121">Планирование на собрания не поддерживается</span><span class="sxs-lookup"><span data-stu-id="e439c-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="e439c-122">Следующие снимки экрана иллюстрируют различие между TeamsOnly или о-ва режим и другие режимы.</span><span class="sxs-lookup"><span data-stu-id="e439c-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="e439c-123">Обратите внимание, что значки чата и вызова доступны с TeamsOnly или о-ва режим (слева снимок экрана), но не другие режимы (правом снимок экрана):</span><span class="sxs-lookup"><span data-stu-id="e439c-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Отображает режим сравнения групп](media/teams-mode-comparison.png)


 
<span data-ttu-id="e439c-125">**Примечание:**
<sup>1</sup> в данный момент, SfBwithTeamsCollab и SfBOnly ведут себя одинаково, но цель состоит в том, для режима SfBOnly также отключить функцию каналы и файлы в группах; Тем не менее в данный момент нет параметра, обеспечивающий в группах, чтобы отключить эту функцию.</span><span class="sxs-lookup"><span data-stu-id="e439c-125">**Note:**
<sup>1</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="e439c-126">Влияние режима от других параметров политики</span><span class="sxs-lookup"><span data-stu-id="e439c-126">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="e439c-127">Как описано выше пользователя сосуществования режим воздействия функциональных возможностей доступна в клиент группы пользователя.</span><span class="sxs-lookup"><span data-stu-id="e439c-127">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="e439c-128">Это означает, что значение режима имеют приоритет над значение другие параметры политики, в зависимости от режима.</span><span class="sxs-lookup"><span data-stu-id="e439c-128">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="e439c-129">В частности режиме сосуществования влияет ли соблюдаются следующие параметры политики:</span><span class="sxs-lookup"><span data-stu-id="e439c-129">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="e439c-130">**Модальность (приложение)**</span><span class="sxs-lookup"><span data-stu-id="e439c-130">**Modality (App)**</span></span>|<span data-ttu-id="e439c-131">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="e439c-131">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="e439c-132">Chat</span><span class="sxs-lookup"><span data-stu-id="e439c-132">Chat</span></span>|<span data-ttu-id="e439c-133">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="e439c-133">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="e439c-134">Звонки</span><span class="sxs-lookup"><span data-stu-id="e439c-134">Calling</span></span>|<span data-ttu-id="e439c-135">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="e439c-135">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="e439c-136">Планирование собрания</span><span class="sxs-lookup"><span data-stu-id="e439c-136">Meeting scheduling</span></span>|<span data-ttu-id="e439c-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="e439c-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="e439c-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="e439c-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="e439c-139">Администраторы должны *не* явно задать параметры политики, когда использование режима совместная работа, но важно понимать, что эти параметры эффективно работать следующим образом для указанного режима.</span><span class="sxs-lookup"><span data-stu-id="e439c-139">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="e439c-140">Режим</span><span class="sxs-lookup"><span data-stu-id="e439c-140">Mode</span></span>|<span data-ttu-id="e439c-141">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="e439c-141">AllowUserChat</span></span>|<span data-ttu-id="e439c-142">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="e439c-142">AllowPrivateCalling</span></span>|<span data-ttu-id="e439c-143">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="e439c-143">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="e439c-144">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="e439c-144">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="e439c-145">TeamsOnly или о-ва</span><span class="sxs-lookup"><span data-stu-id="e439c-145">TeamsOnly or Islands</span></span>|<span data-ttu-id="e439c-146">Включено</span><span class="sxs-lookup"><span data-stu-id="e439c-146">Enabled</span></span>|<span data-ttu-id="e439c-147">Включено</span><span class="sxs-lookup"><span data-stu-id="e439c-147">Enabled</span></span>|<span data-ttu-id="e439c-148">Включено</span><span class="sxs-lookup"><span data-stu-id="e439c-148">Enabled</span></span>|<span data-ttu-id="e439c-149">Включено</span><span class="sxs-lookup"><span data-stu-id="e439c-149">Enabled</span></span>|
|<span data-ttu-id="e439c-150">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="e439c-150">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="e439c-151">Отключено</span><span class="sxs-lookup"><span data-stu-id="e439c-151">Disabled</span></span>|<span data-ttu-id="e439c-152">Отключено</span><span class="sxs-lookup"><span data-stu-id="e439c-152">Disabled</span></span>|<span data-ttu-id="e439c-153">Включено</span><span class="sxs-lookup"><span data-stu-id="e439c-153">Enabled</span></span>|<span data-ttu-id="e439c-154">Включено</span><span class="sxs-lookup"><span data-stu-id="e439c-154">Enabled</span></span>|
|<span data-ttu-id="e439c-155">SfBWithTeamsCollab или SfBOnly</span><span class="sxs-lookup"><span data-stu-id="e439c-155">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="e439c-156">Отключено</span><span class="sxs-lookup"><span data-stu-id="e439c-156">Disabled</span></span>|<span data-ttu-id="e439c-157">Отключено</span><span class="sxs-lookup"><span data-stu-id="e439c-157">Disabled</span></span>|<span data-ttu-id="e439c-158">Отключено</span><span class="sxs-lookup"><span data-stu-id="e439c-158">Disabled</span></span>|<span data-ttu-id="e439c-159">Отключено</span><span class="sxs-lookup"><span data-stu-id="e439c-159">Disabled</span></span>|
||||||

<span data-ttu-id="e439c-160">При использовании PowerShell, `Grant-CsTeamsUpgradePolicy` командлет проверяет конфигурацию соответствующие параметры в TeamsMessagingPolicy, TeamsCallingPolicy и TeamsMeetingPolicy для определения этих параметров будет заменен с TeamsUpgradePolicy и если да, Информационное сообщение предоставляется в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e439c-160">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="e439c-161">Как указано выше, больше не требуется задать параметры политики.</span><span class="sxs-lookup"><span data-stu-id="e439c-161">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="e439c-162">Ниже приведен пример предупреждение PowerShell выглядит как:</span><span class="sxs-lookup"><span data-stu-id="e439c-162">Below is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="e439c-163">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e439c-163">Related topics</span></span>

[<span data-ttu-id="e439c-164">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e439c-164">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




