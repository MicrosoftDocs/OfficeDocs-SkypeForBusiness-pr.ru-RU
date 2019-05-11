---
title: Взаимодействие с клиентом Teams и соответствие режимам сосуществования
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: 91a67c7fb9afb5633494815129d141d5a08708d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930344"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="b6aa2-103">Взаимодействие с клиентом Teams и соответствие режимам сосуществования</span><span class="sxs-lookup"><span data-stu-id="b6aa2-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="b6aa2-104">На этой странице описаны важно, недавно выпущенных изменения в поведение клиента групп, когда пользователи находятся в любой из Скайп для режимов Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span><span class="sxs-lookup"><span data-stu-id="b6aa2-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="b6aa2-105">Совместная работа режимы предназначен для простой, прогнозируемый работы для конечных пользователей как организаций перехода от Скайп для бизнеса группам.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="b6aa2-106">Для перемещения групп организации режим TeamsOnly — конечному получателю для каждого пользователя, хотя не все пользователи должны быть назначены TeamsOnly (или любой другой режим) в то же время.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="b6aa2-107">Пользователей, достигает TeamsOnly режиме организации могут использовать любой из Скайп для бизнеса режимов (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), чтобы убедиться в прогнозируемый связи между пользователями, которые TeamsOnly и тех, кто еще не.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="b6aa2-108">Когда пользователь находится в любой из Скайп для режимов бизнеса, все входящие чаты и вызовы направляются Скайп пользователя для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="b6aa2-109">Чтобы избежать путаницы конечного пользователя и гарантировать правильную маршрутизацию, функциональные возможности телефонной и чата в клиенте группами отключена, если пользователь не во всех Скайп для режимов Business.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="b6aa2-110">Аналогично планирования собраний в группах явным образом отключается, когда пользователи находятся в режимах SfBOnly или SfBWithTeamsCollab и явно включены, если пользователь находится в режиме SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="b6aa2-111">Как доступные функции в клиенте команд изменяется на основе режима</span><span class="sxs-lookup"><span data-stu-id="b6aa2-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="b6aa2-112">Доступные функции в группах зависит от режима совместной работы пользователя, как набор с TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="b6aa2-113">В следующей таблице описано поведение:</span><span class="sxs-lookup"><span data-stu-id="b6aa2-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="b6aa2-114">Эффективное режим пользователя</span><span class="sxs-lookup"><span data-stu-id="b6aa2-114">User's effective mode</span></span>|<span data-ttu-id="b6aa2-115">Опытом группы клиента</span><span class="sxs-lookup"><span data-stu-id="b6aa2-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="b6aa2-116">Любой Скайп для режима бизнеса</span><span class="sxs-lookup"><span data-stu-id="b6aa2-116">Any Skype for Business mode</span></span>|<span data-ttu-id="b6aa2-117">Вызов и чата отключены.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-117">Calling and Chat are disabled.</span></span>|
|<span data-ttu-id="b6aa2-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="b6aa2-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="b6aa2-119">Доступно на собрания планирования</span><span class="sxs-lookup"><span data-stu-id="b6aa2-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="b6aa2-120">SfBWithTeamsCollab или SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b6aa2-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="b6aa2-121">Планирование на собрания не поддерживается</span><span class="sxs-lookup"><span data-stu-id="b6aa2-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="b6aa2-122">Следующие снимки экрана иллюстрируют различие между TeamsOnly или о-ва режим и другие режимы.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="b6aa2-123">Обратите внимание, что значки чата и вызова доступны с TeamsOnly или о-ва режим (слева снимок экрана), но не другие режимы (правом снимок экрана):</span><span class="sxs-lookup"><span data-stu-id="b6aa2-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Отображает режим сравнения групп](media/teams-mode-comparison.png)


 
<span data-ttu-id="b6aa2-125">**Примечание:**
<sup>1</sup> в данный момент, SfBwithTeamsCollab и SfBOnly ведут себя одинаково, но цель состоит в том, для режима SfBOnly также отключить функцию каналы и файлы в группах; Тем не менее в данный момент нет параметра, обеспечивающий в группах, чтобы отключить эту функцию.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-125">**Note:**
<sup>1</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="b6aa2-126">Влияние режима от других параметров политики</span><span class="sxs-lookup"><span data-stu-id="b6aa2-126">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="b6aa2-127">Как описано выше пользователя сосуществования режим воздействия функциональных возможностей доступна в клиент группы пользователя.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-127">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="b6aa2-128">Это означает, что значение режима имеют приоритет над значение другие параметры политики, в зависимости от режима.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-128">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="b6aa2-129">В частности режиме сосуществования влияет ли соблюдаются следующие параметры политики:</span><span class="sxs-lookup"><span data-stu-id="b6aa2-129">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="b6aa2-130">**Модальность (приложение)**</span><span class="sxs-lookup"><span data-stu-id="b6aa2-130">**Modality (App)**</span></span>|<span data-ttu-id="b6aa2-131">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="b6aa2-131">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="b6aa2-132">Chat</span><span class="sxs-lookup"><span data-stu-id="b6aa2-132">Chat</span></span>|<span data-ttu-id="b6aa2-133">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="b6aa2-133">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="b6aa2-134">Звонки</span><span class="sxs-lookup"><span data-stu-id="b6aa2-134">Calling</span></span>|<span data-ttu-id="b6aa2-135">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="b6aa2-135">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="b6aa2-136">Планирование собрания</span><span class="sxs-lookup"><span data-stu-id="b6aa2-136">Meeting scheduling</span></span>|<span data-ttu-id="b6aa2-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="b6aa2-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="b6aa2-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="b6aa2-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="b6aa2-139">Администраторы должны *не* явно задать параметры политики, когда использование режима совместная работа, но важно понимать, что эти параметры эффективно работать следующим образом для указанного режима.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-139">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="b6aa2-140">Режим</span><span class="sxs-lookup"><span data-stu-id="b6aa2-140">Mode</span></span>|<span data-ttu-id="b6aa2-141">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="b6aa2-141">AllowUserChat</span></span>|<span data-ttu-id="b6aa2-142">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="b6aa2-142">AllowPrivateCalling</span></span>|<span data-ttu-id="b6aa2-143">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="b6aa2-143">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="b6aa2-144">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="b6aa2-144">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="b6aa2-145">TeamsOnly или о-ва</span><span class="sxs-lookup"><span data-stu-id="b6aa2-145">TeamsOnly or Islands</span></span>|<span data-ttu-id="b6aa2-146">Включено</span><span class="sxs-lookup"><span data-stu-id="b6aa2-146">Enabled</span></span>|<span data-ttu-id="b6aa2-147">Включено</span><span class="sxs-lookup"><span data-stu-id="b6aa2-147">Enabled</span></span>|<span data-ttu-id="b6aa2-148">Включено</span><span class="sxs-lookup"><span data-stu-id="b6aa2-148">Enabled</span></span>|<span data-ttu-id="b6aa2-149">Включено</span><span class="sxs-lookup"><span data-stu-id="b6aa2-149">Enabled</span></span>|
|<span data-ttu-id="b6aa2-150">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="b6aa2-150">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="b6aa2-151">Отключено</span><span class="sxs-lookup"><span data-stu-id="b6aa2-151">Disabled</span></span>|<span data-ttu-id="b6aa2-152">Отключено</span><span class="sxs-lookup"><span data-stu-id="b6aa2-152">Disabled</span></span>|<span data-ttu-id="b6aa2-153">Включено</span><span class="sxs-lookup"><span data-stu-id="b6aa2-153">Enabled</span></span>|<span data-ttu-id="b6aa2-154">Включено</span><span class="sxs-lookup"><span data-stu-id="b6aa2-154">Enabled</span></span>|
|<span data-ttu-id="b6aa2-155">SfBWithTeamsCollab или SfBOnly</span><span class="sxs-lookup"><span data-stu-id="b6aa2-155">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="b6aa2-156">Отключено</span><span class="sxs-lookup"><span data-stu-id="b6aa2-156">Disabled</span></span>|<span data-ttu-id="b6aa2-157">Отключено</span><span class="sxs-lookup"><span data-stu-id="b6aa2-157">Disabled</span></span>|<span data-ttu-id="b6aa2-158">Отключено</span><span class="sxs-lookup"><span data-stu-id="b6aa2-158">Disabled</span></span>|<span data-ttu-id="b6aa2-159">Отключено</span><span class="sxs-lookup"><span data-stu-id="b6aa2-159">Disabled</span></span>|
||||||

<span data-ttu-id="b6aa2-160">При использовании PowerShell, `Grant-CsTeamsUpgradePolicy` командлет проверяет конфигурацию соответствующие параметры в TeamsMessagingPolicy, TeamsCallingPolicy и TeamsMeetingPolicy для определения этих параметров будет заменен с TeamsUpgradePolicy и если да, Информационное сообщение предоставляется в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-160">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="b6aa2-161">Как указано выше, больше не требуется задать параметры политики.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-161">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="b6aa2-162">Ниже приведен пример предупреждение PowerShell выглядит как:</span><span class="sxs-lookup"><span data-stu-id="b6aa2-162">Below is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="b6aa2-163">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b6aa2-163">Related topics</span></span>

[<span data-ttu-id="b6aa2-164">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b6aa2-164">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




