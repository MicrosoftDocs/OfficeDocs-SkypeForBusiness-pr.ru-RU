---
title: Взаимодействие с клиентом Teams и соответствие режимам сосуществования
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Узнайте о взаимодействию с клиентами Teams и совместимости с режимами сосуществования (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
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
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="09c91-103">Взаимодействие с клиентом Teams и соответствие режимам сосуществования</span><span class="sxs-lookup"><span data-stu-id="09c91-103">Teams client experience and conformance to coexistence modes</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="09c91-104">Цель режимов сосуществования Skype для бизнеса (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) – это простой и предсказуемый опыт конечных пользователей в том, что в Организации переход с Skype для бизнеса на Teams.</span><span class="sxs-lookup"><span data-stu-id="09c91-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="09c91-105">Для Организации, перемещающейся в Teams, режим " **только для Teams** " является конечным пунктом для каждого пользователя, хотя не всем пользователям должны быть назначены **только команды** (или любой другой режим) одновременно.</span><span class="sxs-lookup"><span data-stu-id="09c91-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="09c91-106">Перед тем как пользователи приходили в режим TeamsOnly, организации могут использовать любой из режимов сосуществования Skype для бизнеса, чтобы обеспечить предсказуемую связь между пользователями, которые не являются **участниками** , и тем, кто еще не в состоянии.</span><span class="sxs-lookup"><span data-stu-id="09c91-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren't yet.</span></span> 

<span data-ttu-id="09c91-107">Когда пользователь входит в любой из режимов Skype для бизнеса, все входящие разговоры и звонки перенаправляются клиенту Skype для бизнеса пользователя.</span><span class="sxs-lookup"><span data-stu-id="09c91-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="09c91-108">Чтобы избежать путаницы и удостовериться в том, что функция маршрутизации, вызов и чат в клиенте Teams отключена, когда пользователь входит в любой из режимов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="09c91-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="09c91-109">Аналогичным образом планирование собраний в Teams явным образом отключается, если пользователи находятся в режимах SfBOnly или SfBWithTeamsCollab, и явно включаются, когда пользователь находится в режиме SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="09c91-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="09c91-110">Так как присутствие является индикатором доступности в чате и звонке, то при отключении чата и звонков в Teams также отображается самообнаружение в группах (то есть отображается собственное состояние присутствия в клиенте Teams на рисунке пользователя).</span><span class="sxs-lookup"><span data-stu-id="09c91-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one's own presence in the Teams client in the user's picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="09c91-111">Изменение доступных функциональных возможностей клиента Teams в зависимости от режима</span><span class="sxs-lookup"><span data-stu-id="09c91-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="09c91-112">Доступные функции в Teams зависят от режима сосуществования пользователя, который задается с помощью TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="09c91-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="09c91-113">В таблице ниже приведено краткое описание поведения.</span><span class="sxs-lookup"><span data-stu-id="09c91-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="09c91-114">Эффективный режим пользователя</span><span class="sxs-lookup"><span data-stu-id="09c91-114">User's effective mode</span></span>|<span data-ttu-id="09c91-115">Взаимодействие с клиентом Teams</span><span class="sxs-lookup"><span data-stu-id="09c91-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="09c91-116">Любой режим Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="09c91-116">Any Skype for Business mode</span></span>|<span data-ttu-id="09c91-117">Звонки, чат и самообнаружение отключены.</span><span class="sxs-lookup"><span data-stu-id="09c91-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="09c91-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="09c91-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="09c91-119">Доступно планирование собраний</span><span class="sxs-lookup"><span data-stu-id="09c91-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="09c91-120">SfBWithTeamsCollab или SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="09c91-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="09c91-121">Планирование собраний недоступно</span><span class="sxs-lookup"><span data-stu-id="09c91-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="09c91-122">На следующих снимках экрана показано различие между режимами " **только для Teams** ", " **острова** " и всеми другими режимами.</span><span class="sxs-lookup"><span data-stu-id="09c91-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="09c91-123">Обратите внимание на то, что значки чата и вызова по умолчанию доступны только в режиме " **только для групп** " или " **острова** " (на рисунке слева), но не в других режимах (на снимке экрана справа):</span><span class="sxs-lookup"><span data-stu-id="09c91-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Параллельное сравнение режимов групп](media/teams-mode-comparison.png)

<span data-ttu-id="09c91-125">Кроме того, самообнаружение в других режимах недоступно, как показано здесь.</span><span class="sxs-lookup"><span data-stu-id="09c91-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![Снимок экрана с самообнаружением для собраний в начале собрания](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="09c91-127">**Примечание.**
<sup>1</sup> в настоящее время поведение SfBwithTeamsCollab и SfBOnly работает одинаково, но для работы с файлами в Teams и в режиме SfBOnly также можно отключить каналы и файлы.</span><span class="sxs-lookup"><span data-stu-id="09c91-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="09c91-128">В списке временные каналы можно скрыть с помощью политики разрешений приложений.</span><span class="sxs-lookup"><span data-stu-id="09c91-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="09c91-129">Влияние режима для других параметров политики</span><span class="sxs-lookup"><span data-stu-id="09c91-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="09c91-130">Как описано выше, режим сосуществования пользователя влияет на функциональные возможности, доступные в клиенте Teams в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="09c91-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="09c91-131">Это означает, что значение Mode может иметь приоритет над значением других параметров политики, в зависимости от режима.</span><span class="sxs-lookup"><span data-stu-id="09c91-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="09c91-132">В частности, режим сосуществования влияет на то, выполняются ли следующие параметры политики.</span><span class="sxs-lookup"><span data-stu-id="09c91-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="09c91-133">**Модальность (приложение)**</span><span class="sxs-lookup"><span data-stu-id="09c91-133">**Modality (App)**</span></span>|<span data-ttu-id="09c91-134">**Политика. параметр**</span><span class="sxs-lookup"><span data-stu-id="09c91-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="09c91-135">Чат</span><span class="sxs-lookup"><span data-stu-id="09c91-135">Chat</span></span>|<span data-ttu-id="09c91-136">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="09c91-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="09c91-137">Звонки</span><span class="sxs-lookup"><span data-stu-id="09c91-137">Calling</span></span>|<span data-ttu-id="09c91-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="09c91-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="09c91-139">Планирование собраний</span><span class="sxs-lookup"><span data-stu-id="09c91-139">Meeting scheduling</span></span>|<span data-ttu-id="09c91-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="09c91-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="09c91-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="09c91-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="09c91-142">Администраторам *не* нужно явно задавать эти параметры политики при использовании режима совместного существования, но важно понимать, что эти параметры работают следующим образом для определенного режима.</span><span class="sxs-lookup"><span data-stu-id="09c91-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="09c91-143">Режиме</span><span class="sxs-lookup"><span data-stu-id="09c91-143">Mode</span></span>|<span data-ttu-id="09c91-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="09c91-144">AllowUserChat</span></span>|<span data-ttu-id="09c91-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="09c91-145">AllowPrivateCalling</span></span>|<span data-ttu-id="09c91-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="09c91-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="09c91-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="09c91-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="09c91-148">TeamsOnly или острова</span><span class="sxs-lookup"><span data-stu-id="09c91-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="09c91-149">Включено</span><span class="sxs-lookup"><span data-stu-id="09c91-149">Enabled</span></span>|<span data-ttu-id="09c91-150">Включено</span><span class="sxs-lookup"><span data-stu-id="09c91-150">Enabled</span></span>|<span data-ttu-id="09c91-151">Включено</span><span class="sxs-lookup"><span data-stu-id="09c91-151">Enabled</span></span>|<span data-ttu-id="09c91-152">Включено</span><span class="sxs-lookup"><span data-stu-id="09c91-152">Enabled</span></span>|
|<span data-ttu-id="09c91-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="09c91-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="09c91-154">Отключено</span><span class="sxs-lookup"><span data-stu-id="09c91-154">Disabled</span></span>|<span data-ttu-id="09c91-155">Отключено</span><span class="sxs-lookup"><span data-stu-id="09c91-155">Disabled</span></span>|<span data-ttu-id="09c91-156">Включено</span><span class="sxs-lookup"><span data-stu-id="09c91-156">Enabled</span></span>|<span data-ttu-id="09c91-157">Включено</span><span class="sxs-lookup"><span data-stu-id="09c91-157">Enabled</span></span>|
|<span data-ttu-id="09c91-158">SfBWithTeamsCollab или SfBOnly</span><span class="sxs-lookup"><span data-stu-id="09c91-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="09c91-159">Отключено</span><span class="sxs-lookup"><span data-stu-id="09c91-159">Disabled</span></span>|<span data-ttu-id="09c91-160">Отключено</span><span class="sxs-lookup"><span data-stu-id="09c91-160">Disabled</span></span>|<span data-ttu-id="09c91-161">Отключено</span><span class="sxs-lookup"><span data-stu-id="09c91-161">Disabled</span></span>|<span data-ttu-id="09c91-162">Отключено</span><span class="sxs-lookup"><span data-stu-id="09c91-162">Disabled</span></span>|
||||||

<span data-ttu-id="09c91-163">При использовании PowerShell `Grant-CsTeamsUpgradePolicy` командлет проверяет конфигурацию соответствующих параметров в TeamsMessagingPolicy, TeamsCallingPolicy и TeamsMeetingPolicy, чтобы определить, будут ли эти параметры заменены TeamsUpgradePolicy, и если да, то в PowerShell будет выдано информационное сообщение.</span><span class="sxs-lookup"><span data-stu-id="09c91-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="09c91-164">Как указано выше, больше не нужно настраивать эти параметры политики.</span><span class="sxs-lookup"><span data-stu-id="09c91-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="09c91-165">Ниже показано, как выглядит предупреждение PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09c91-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a><span data-ttu-id="09c91-166">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="09c91-166">Related topics</span></span>

[<span data-ttu-id="09c91-167">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="09c91-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




