---
title: Взаимодействие с клиентом Teams и соответствие режимам сосуществования
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Узнайте о впечатлениях от работы клиентов Teams и соответствии с режимами сосуществования (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c67046128c79608f19a4a1f4474164a949f37ef
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903364"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="37cf4-103">Взаимодействие с клиентом Teams и соответствие режимам сосуществования</span><span class="sxs-lookup"><span data-stu-id="37cf4-103">Teams client experience and conformance to coexistence modes</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="37cf4-104">Режимы сосуществования Skype для бизнеса (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsColetings) обеспечивают простой и предсказуемый опыт для конечных пользователей при переходе организаций со Skype для бизнеса на Teams.</span><span class="sxs-lookup"><span data-stu-id="37cf4-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="37cf4-105">Для организации, перемещаемой в Teams, режим **"Только Teams"** является конечным пунктом назначения для каждого пользователя, хотя не всем пользователям нужно на должно быть назначено только **Teams** (или любой другой режим) одновременно.</span><span class="sxs-lookup"><span data-stu-id="37cf4-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="37cf4-106">До выхода пользователей в режим TeamsOnly организации могут использовать любой из режимов сосуществования Skype для бизнеса, чтобы обеспечить предсказуемую связь между пользователями, которые являются только **teams,** и теми, кто еще не является.</span><span class="sxs-lookup"><span data-stu-id="37cf4-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren't yet.</span></span> 

<span data-ttu-id="37cf4-107">Когда пользователь находится в любом из режимов Skype для бизнеса, все входящие чаты и звонки перенанаются его клиенту Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="37cf4-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="37cf4-108">Чтобы избежать путаницы с конечными пользователями и обеспечить правильную маршрутику, функции звонков и чата в клиенте Teams отключаются, когда пользователь находится в любом из режимов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="37cf4-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="37cf4-109">Кроме того, планирование собраний в Teams явным образом отключается, когда пользователи работают в режиме SfBOnly или SfBWithTeamsCollab, и явно включено, когда пользователь находится в режиме SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="37cf4-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="37cf4-110">Так как присутствие указывает на доступность через чат и вызовы, то при отключке чата и звонков самообнахождение в Teams (т. е. отображение собственного присутствия в клиенте Teams на изображении пользователя) также скрыто.</span><span class="sxs-lookup"><span data-stu-id="37cf4-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one's own presence in the Teams client in the user's picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="37cf4-111">Изменение доступных функций в клиенте Teams в зависимости от режима</span><span class="sxs-lookup"><span data-stu-id="37cf4-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="37cf4-112">Доступные функции в Teams зависят от режима сосуществования пользователя, настроенного командой TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="37cf4-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="37cf4-113">В следующей таблице это поведение резюмирует:</span><span class="sxs-lookup"><span data-stu-id="37cf4-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="37cf4-114">Режим действия пользователя</span><span class="sxs-lookup"><span data-stu-id="37cf4-114">User's effective mode</span></span>|<span data-ttu-id="37cf4-115">Опыт работы в клиенте Teams</span><span class="sxs-lookup"><span data-stu-id="37cf4-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="37cf4-116">Любой режим Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="37cf4-116">Any Skype for Business mode</span></span>|<span data-ttu-id="37cf4-117">Отключаются вызовы, чат и само присутствие.</span><span class="sxs-lookup"><span data-stu-id="37cf4-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="37cf4-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="37cf4-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="37cf4-119">Доступно планирование собраний</span><span class="sxs-lookup"><span data-stu-id="37cf4-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="37cf4-120">SfBWithTeamsCollab или SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="37cf4-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="37cf4-121">Планирование собраний не доступно</span><span class="sxs-lookup"><span data-stu-id="37cf4-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="37cf4-122">На снимках экрана ниже показано, чем отличаются режимы **Teams и** **"Только** острова", а также все остальные режимы.</span><span class="sxs-lookup"><span data-stu-id="37cf4-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="37cf4-123">Обратите внимание, что значки чата и  звонков по умолчанию доступны в режиме "Только **Teams"** или "Острова" (снимок слева), но не в других режимах (правый снимок экрана):</span><span class="sxs-lookup"><span data-stu-id="37cf4-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Сравнение режимов Teams](media/teams-mode-comparison.png)

<span data-ttu-id="37cf4-125">Кроме того, в других режимах присутствие самообнаправления недоступно, как показано здесь.</span><span class="sxs-lookup"><span data-stu-id="37cf4-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![Снимок экрана: самообнахождение на первом собрании](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="37cf4-127">**Примечание.** 
 <sup>1</sup> В настоящее время SfBwithTeamsCollab и SfBOnly работают одинаково, но цель состоит в том, чтобы режим SfBOnly также отключил функции каналов и файлов в Teams.</span><span class="sxs-lookup"><span data-stu-id="37cf4-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="37cf4-128">Промежуточным решением является скрытие каналов с помощью политики разрешений приложений.</span><span class="sxs-lookup"><span data-stu-id="37cf4-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="37cf4-129">Влияние режима на другие параметры политики</span><span class="sxs-lookup"><span data-stu-id="37cf4-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="37cf4-130">Как описано выше, режим сосуществования влияет на функции, доступные в клиенте Teams пользователя.</span><span class="sxs-lookup"><span data-stu-id="37cf4-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="37cf4-131">Это означает, что значение режима может иметь приоритет над значением других параметров политики в зависимости от режима.</span><span class="sxs-lookup"><span data-stu-id="37cf4-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="37cf4-132">В частности, режим сосуществования влияет на то, будут ли соблюдаться следующие параметры политики:</span><span class="sxs-lookup"><span data-stu-id="37cf4-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="37cf4-133">**Modality (App)**</span><span class="sxs-lookup"><span data-stu-id="37cf4-133">**Modality (App)**</span></span>|<span data-ttu-id="37cf4-134">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="37cf4-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="37cf4-135">Чат</span><span class="sxs-lookup"><span data-stu-id="37cf4-135">Chat</span></span>|<span data-ttu-id="37cf4-136">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="37cf4-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="37cf4-137">Звонки</span><span class="sxs-lookup"><span data-stu-id="37cf4-137">Calling</span></span>|<span data-ttu-id="37cf4-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="37cf4-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="37cf4-139">Планирование собраний</span><span class="sxs-lookup"><span data-stu-id="37cf4-139">Meeting scheduling</span></span>|<span data-ttu-id="37cf4-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="37cf4-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="37cf4-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="37cf4-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="37cf4-142">Администраторам  не требуется явно настраивать эти параметры политики в режиме совместной работы, но важно понимать, что эти параметры правильно настроены в определенном режиме.</span><span class="sxs-lookup"><span data-stu-id="37cf4-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="37cf4-143">Режим</span><span class="sxs-lookup"><span data-stu-id="37cf4-143">Mode</span></span>|<span data-ttu-id="37cf4-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="37cf4-144">AllowUserChat</span></span>|<span data-ttu-id="37cf4-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="37cf4-145">AllowPrivateCalling</span></span>|<span data-ttu-id="37cf4-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="37cf4-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="37cf4-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="37cf4-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="37cf4-148">TeamsOnly или Islands</span><span class="sxs-lookup"><span data-stu-id="37cf4-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="37cf4-149">Включено</span><span class="sxs-lookup"><span data-stu-id="37cf4-149">Enabled</span></span>|<span data-ttu-id="37cf4-150">Включено</span><span class="sxs-lookup"><span data-stu-id="37cf4-150">Enabled</span></span>|<span data-ttu-id="37cf4-151">Включено</span><span class="sxs-lookup"><span data-stu-id="37cf4-151">Enabled</span></span>|<span data-ttu-id="37cf4-152">Включено</span><span class="sxs-lookup"><span data-stu-id="37cf4-152">Enabled</span></span>|
|<span data-ttu-id="37cf4-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="37cf4-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="37cf4-154">Отключено</span><span class="sxs-lookup"><span data-stu-id="37cf4-154">Disabled</span></span>|<span data-ttu-id="37cf4-155">Отключено</span><span class="sxs-lookup"><span data-stu-id="37cf4-155">Disabled</span></span>|<span data-ttu-id="37cf4-156">Включено</span><span class="sxs-lookup"><span data-stu-id="37cf4-156">Enabled</span></span>|<span data-ttu-id="37cf4-157">Включено</span><span class="sxs-lookup"><span data-stu-id="37cf4-157">Enabled</span></span>|
|<span data-ttu-id="37cf4-158">SfBWithTeamsCollab или SfBOnly</span><span class="sxs-lookup"><span data-stu-id="37cf4-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="37cf4-159">Отключено</span><span class="sxs-lookup"><span data-stu-id="37cf4-159">Disabled</span></span>|<span data-ttu-id="37cf4-160">Отключено</span><span class="sxs-lookup"><span data-stu-id="37cf4-160">Disabled</span></span>|<span data-ttu-id="37cf4-161">Отключено</span><span class="sxs-lookup"><span data-stu-id="37cf4-161">Disabled</span></span>|<span data-ttu-id="37cf4-162">Отключено</span><span class="sxs-lookup"><span data-stu-id="37cf4-162">Disabled</span></span>|
||||||

<span data-ttu-id="37cf4-163">При использовании PowerShell командлет проверяет конфигурацию соответствующих параметров `Grant-CsTeamsUpgradePolicy` в TeamsMessagingPolicy, TeamsCallingPolicy и TeamsMeetingPolicy, чтобы определить, будут ли эти параметры переопределяться TeamsUpgradePolicy и, если да, в PowerShell выведется информационное сообщение.</span><span class="sxs-lookup"><span data-stu-id="37cf4-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="37cf4-164">Как было отмечено выше, больше не нужно настраивать эти другие параметры политики.</span><span class="sxs-lookup"><span data-stu-id="37cf4-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="37cf4-165">Ниже приводится пример того, как выглядит предупреждение PowerShell:</span><span class="sxs-lookup"><span data-stu-id="37cf4-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a><span data-ttu-id="37cf4-166">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="37cf4-166">Related topics</span></span>

[<span data-ttu-id="37cf4-167">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="37cf4-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




