---
title: Управление политиками собраний для общего доступа к содержимому
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: Узнайте, как управлять настройками политики собраний в Teams для общего доступа к содержимому.
ms.openlocfilehash: 7b318ad0025d6c68b041c65d8fbb78cbfbc87723
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598773"
---
# <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="26edb-103">Параметры политики собраний — общий доступ к содержимому</span><span class="sxs-lookup"><span data-stu-id="26edb-103">Meeting policy settings - Content sharing</span></span>

<span data-ttu-id="26edb-104"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="26edb-104"><a name="bkcontentsharing"> </a></span></span>

<span data-ttu-id="26edb-105">В этой статье описаны следующие параметры политики собраний, связанные с совместным использованием содержимого:</span><span class="sxs-lookup"><span data-stu-id="26edb-105">This article describes the following meeting policy settings related to content sharing:</span></span>

- [<span data-ttu-id="26edb-106">Режим демонстрации экрана</span><span class="sxs-lookup"><span data-stu-id="26edb-106">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="26edb-107">Разрешение участнику предоставить или запросить управление</span><span class="sxs-lookup"><span data-stu-id="26edb-107">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="26edb-108">Разрешение внешнему участнику предоставить или запросить управление</span><span class="sxs-lookup"><span data-stu-id="26edb-108">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="26edb-109">Разрешить общий доступ в PowerPoint</span><span class="sxs-lookup"><span data-stu-id="26edb-109">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="26edb-110">Разрешить доску</span><span class="sxs-lookup"><span data-stu-id="26edb-110">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="26edb-111">Разрешение общих заметок</span><span class="sxs-lookup"><span data-stu-id="26edb-111">Allow shared notes</span></span>](#allow-shared-notes)

## <a name="screen-sharing-mode"></a><span data-ttu-id="26edb-112">Режим демонстрации экрана</span><span class="sxs-lookup"><span data-stu-id="26edb-112">Screen sharing mode</span></span>

<span data-ttu-id="26edb-113">Этот параметр является сочетанием политик "на пользователя" и "на пользователя".</span><span class="sxs-lookup"><span data-stu-id="26edb-113">This setting is a combination of a per-organizer and per-user policies.</span></span> <span data-ttu-id="26edb-114">Этот параметр позволяет разрешить совместный доступ к рабочему столу и окну во время собрания пользователя.</span><span class="sxs-lookup"><span data-stu-id="26edb-114">This setting controls whether desktop and window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="26edb-115">Политики организатора собрания наследуются от участников собрания, которым не назначены политики (например, анонимные, гостенные, B2B и федераированные участники).</span><span class="sxs-lookup"><span data-stu-id="26edb-115">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="26edb-116">Значение параметра</span><span class="sxs-lookup"><span data-stu-id="26edb-116">Setting value</span></span> |<span data-ttu-id="26edb-117">Поведение</span><span class="sxs-lookup"><span data-stu-id="26edb-117">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="26edb-118">**Весь экран**</span><span class="sxs-lookup"><span data-stu-id="26edb-118">**Entire screen**</span></span>    | <span data-ttu-id="26edb-119">На собрании разрешен полный общий доступ к рабочему столу и приложениям</span><span class="sxs-lookup"><span data-stu-id="26edb-119">Full desktop sharing and application sharing are allowed in the meeting</span></span> |
|<span data-ttu-id="26edb-120">**Одно приложение**</span><span class="sxs-lookup"><span data-stu-id="26edb-120">**Single application**</span></span>   | <span data-ttu-id="26edb-121">На собрании разрешен общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="26edb-121">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="26edb-122">**Отключено**</span><span class="sxs-lookup"><span data-stu-id="26edb-122">**Disabled**</span></span>     |<span data-ttu-id="26edb-123">На собрании отключены общий доступ к экрану и общий доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="26edb-123">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="26edb-124">Рассмотрим пример.</span><span class="sxs-lookup"><span data-stu-id="26edb-124">Let's look at the following example.</span></span>

|<span data-ttu-id="26edb-125">Пользователь</span><span class="sxs-lookup"><span data-stu-id="26edb-125">User</span></span> |<span data-ttu-id="26edb-126">Политика встречи</span><span class="sxs-lookup"><span data-stu-id="26edb-126">Meeting policy</span></span> |<span data-ttu-id="26edb-127">Режим демонстрации экрана</span><span class="sxs-lookup"><span data-stu-id="26edb-127">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="26edb-128">Даниля</span><span class="sxs-lookup"><span data-stu-id="26edb-128">Daniela</span></span>  | <span data-ttu-id="26edb-129">Глобальный</span><span class="sxs-lookup"><span data-stu-id="26edb-129">Global</span></span>   | <span data-ttu-id="26edb-130">Весь экран</span><span class="sxs-lookup"><span data-stu-id="26edb-130">Entire screen</span></span> |
|<span data-ttu-id="26edb-131">Аманда</span><span class="sxs-lookup"><span data-stu-id="26edb-131">Amanda</span></span>   | <span data-ttu-id="26edb-132">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="26edb-132">Location1MeetingPolicy</span></span>  | <span data-ttu-id="26edb-133">Отключено</span><span class="sxs-lookup"><span data-stu-id="26edb-133">Disabled</span></span> |

<span data-ttu-id="26edb-134">Собрания, которые организатор может проводить Светлана, позволяют участникам собрания делиться своим экраном или конкретным приложением.</span><span class="sxs-lookup"><span data-stu-id="26edb-134">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="26edb-135">Если Аманда присоединится к собранию Алексея, она не сможет делиться своим экраном или конкретным приложением, так как ее параметр политики отключен.</span><span class="sxs-lookup"><span data-stu-id="26edb-135">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="26edb-136">В собраниях, которые проводить Компания Amanda, никто не может делиться своим экраном или одним приложением независимо от назначенной им политики режима общего доступа к экрану.</span><span class="sxs-lookup"><span data-stu-id="26edb-136">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span>  <span data-ttu-id="26edb-137">Поэтому Алексей не может делиться своим экраном или одним приложением на собраниях Амбаны.</span><span class="sxs-lookup"><span data-stu-id="26edb-137">Consequently, Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="26edb-138">В настоящее время пользователи не могут играть в видео или делиться своим экраном на собрании Teams, если они используют Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="26edb-138">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

## <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="26edb-139">Разрешение участнику предоставить или запросить управление</span><span class="sxs-lookup"><span data-stu-id="26edb-139">Allow a participant to give or request control</span></span>

<span data-ttu-id="26edb-140">Этот параметр настраивается как политика для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="26edb-140">This setting is a per-user policy.</span></span> <span data-ttu-id="26edb-141">Этот параметр управляет возможностью пользователя предоставить управление рабочим столом или окном другим участникам собрания.</span><span class="sxs-lookup"><span data-stu-id="26edb-141">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="26edb-142">Чтобы предоставить управление, наведите курсор на верхнюю часть экрана.</span><span class="sxs-lookup"><span data-stu-id="26edb-142">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="26edb-143">Если этот параметр включен для пользователя, на верхней панели сеанса совместного доступа отображается параметр "Предоставить управление". </span><span class="sxs-lookup"><span data-stu-id="26edb-143">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![Снимок экрана: параметр "Предоставить управление"](media/meeting-policies-give-control.png)

<span data-ttu-id="26edb-145">Если этот параметр отключен для пользователя, параметр "Предоставить управление" будет не доступен. </span><span class="sxs-lookup"><span data-stu-id="26edb-145">If the setting is turned off for the user, the **Give Control** option isn't available.</span></span>

![Снимок экрана: параметр "Предоставить управление" не доступен](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="26edb-147">Рассмотрим пример.</span><span class="sxs-lookup"><span data-stu-id="26edb-147">Let's look at the following example.</span></span>

|<span data-ttu-id="26edb-148">Пользователь</span><span class="sxs-lookup"><span data-stu-id="26edb-148">User</span></span> |<span data-ttu-id="26edb-149">Политика встречи</span><span class="sxs-lookup"><span data-stu-id="26edb-149">Meeting policy</span></span>  |<span data-ttu-id="26edb-150">Разрешить участнику предоставить или запросить управление</span><span class="sxs-lookup"><span data-stu-id="26edb-150">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="26edb-151">Даниля</span><span class="sxs-lookup"><span data-stu-id="26edb-151">Daniela</span></span>   | <span data-ttu-id="26edb-152">Глобальный</span><span class="sxs-lookup"><span data-stu-id="26edb-152">Global</span></span>   | <span data-ttu-id="26edb-153">Вкл.</span><span class="sxs-lookup"><span data-stu-id="26edb-153">On</span></span>       |
|<span data-ttu-id="26edb-154">Бабек</span><span class="sxs-lookup"><span data-stu-id="26edb-154">Babek</span></span>    | <span data-ttu-id="26edb-155">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="26edb-155">Location1MeetingPolicy</span></span>        | <span data-ttu-id="26edb-156">Выкл.</span><span class="sxs-lookup"><span data-stu-id="26edb-156">Off</span></span>   |

<span data-ttu-id="26edb-157">Дарья может предоставить управление рабочим столом или окном другим участникам собрания, организованного Дарьей.</span><span class="sxs-lookup"><span data-stu-id="26edb-157">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek.</span></span> <span data-ttu-id="26edb-158">Тем не менее, Он не может предоставить управление другим участникам.</span><span class="sxs-lookup"><span data-stu-id="26edb-158">However, Babek can't give control to other participants.</span></span>

<span data-ttu-id="26edb-159">Чтобы управлять тем, кто может управлять и принимать запросы на управление, используйте для этого cmdlet AllowParticipantGiveRequestControl.</span><span class="sxs-lookup"><span data-stu-id="26edb-159">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="26edb-160">Чтобы предоставить общий контент во время общего доступа и получить контроль над им, обе стороны должны использовать клиент Teams для настольных пк.</span><span class="sxs-lookup"><span data-stu-id="26edb-160">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="26edb-161">Управление не поддерживается, если одна из сторон использует Teams в браузере.</span><span class="sxs-lookup"><span data-stu-id="26edb-161">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="26edb-162">Это связано с техническим ограничением, которое мы планируем устранить.</span><span class="sxs-lookup"><span data-stu-id="26edb-162">This is due to a technical limitation that we're planning to fix.</span></span>

## <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="26edb-163">Разрешение внешнему участнику предоставить или запросить управление</span><span class="sxs-lookup"><span data-stu-id="26edb-163">Allow an external participant to give or request control</span></span>

<span data-ttu-id="26edb-164">Этот параметр настраивается как политика для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="26edb-164">This setting is a per-user policy.</span></span> <span data-ttu-id="26edb-165">Если в организации настроена эта политика для пользователя, то какие действия могут делать внешние участники, независимо от заданной организатором собрания.</span><span class="sxs-lookup"><span data-stu-id="26edb-165">Whether an organization has set this policy for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="26edb-166">Этот параметр управляет возможностью управления внешними участниками или запросом управления экраном sharer (в зависимости от того, что он установил в политиках собраний организации).</span><span class="sxs-lookup"><span data-stu-id="26edb-166">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="26edb-167">Внешние участники собраний Teams можно классифицизировать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="26edb-167">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="26edb-168">Анонимный пользователь</span><span class="sxs-lookup"><span data-stu-id="26edb-168">Anonymous user</span></span>
- <span data-ttu-id="26edb-169">Гостевые пользователи</span><span class="sxs-lookup"><span data-stu-id="26edb-169">Guest users</span></span>  
- <span data-ttu-id="26edb-170">Пользователь B2B</span><span class="sxs-lookup"><span data-stu-id="26edb-170">B2B user</span></span>
- <span data-ttu-id="26edb-171">Федераированный пользователь</span><span class="sxs-lookup"><span data-stu-id="26edb-171">Federated user</span></span>  

<span data-ttu-id="26edb-172">Могут ли федераированные пользователи управлять внешними пользователями  при совместном доступе, управляет ли внешний участник разрешением на управление или запрос на управление в организации.</span><span class="sxs-lookup"><span data-stu-id="26edb-172">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="26edb-173">Чтобы с помощью PowerShell контролировать, могут ли внешние участники предоставить управление или принять запросы на управление, используйте cmdlet AllowExternalParticipantGiveRequestControl.</span><span class="sxs-lookup"><span data-stu-id="26edb-173">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="26edb-174">Разрешить общий доступ в PowerPoint</span><span class="sxs-lookup"><span data-stu-id="26edb-174">Allow PowerPoint sharing</span></span>

<span data-ttu-id="26edb-175">Это политика для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="26edb-175">This is a per-user policy.</span></span> <span data-ttu-id="26edb-176">Этот параметр управляет тем, может ли пользователь делиться презентациями слайдов PowerPoint на собрании.</span><span class="sxs-lookup"><span data-stu-id="26edb-176">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="26edb-177">Внешние пользователи, включая анонимных, гостевых и федеранных пользователей, наследуют политику организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="26edb-177">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="26edb-178">Рассмотрим пример.</span><span class="sxs-lookup"><span data-stu-id="26edb-178">Let's look at the following example.</span></span>

|<span data-ttu-id="26edb-179">Пользователь</span><span class="sxs-lookup"><span data-stu-id="26edb-179">User</span></span> |<span data-ttu-id="26edb-180">Политика встречи</span><span class="sxs-lookup"><span data-stu-id="26edb-180">Meeting policy</span></span>  |<span data-ttu-id="26edb-181">Разрешить общий доступ в PowerPoint</span><span class="sxs-lookup"><span data-stu-id="26edb-181">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="26edb-182">Даниля</span><span class="sxs-lookup"><span data-stu-id="26edb-182">Daniela</span></span>   | <span data-ttu-id="26edb-183">Глобальный</span><span class="sxs-lookup"><span data-stu-id="26edb-183">Global</span></span>   | <span data-ttu-id="26edb-184">Вкл.</span><span class="sxs-lookup"><span data-stu-id="26edb-184">On</span></span>       |
|<span data-ttu-id="26edb-185">Аманда</span><span class="sxs-lookup"><span data-stu-id="26edb-185">Amanda</span></span>   | <span data-ttu-id="26edb-186">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="26edb-186">Location1MeetingPolicy</span></span>        | <span data-ttu-id="26edb-187">Выкл.</span><span class="sxs-lookup"><span data-stu-id="26edb-187">Off</span></span>   |

<span data-ttu-id="26edb-188">Аманда не может делиться презентациями слайдов PowerPoint на собраниях, даже если она является организатором собрания.</span><span class="sxs-lookup"><span data-stu-id="26edb-188">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="26edb-189">Алексей может делиться презентациями слайдов PowerPoint, даже если собрание организовано Амандой.</span><span class="sxs-lookup"><span data-stu-id="26edb-189">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="26edb-190">Аманда может просматривать презентации PowerPoint, доступ к которые получили другие люди на собрании, несмотря на то, что не может делиться ими.</span><span class="sxs-lookup"><span data-stu-id="26edb-190">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

## <a name="allow-whiteboard"></a><span data-ttu-id="26edb-191">Разрешить доску</span><span class="sxs-lookup"><span data-stu-id="26edb-191">Allow whiteboard</span></span>

<span data-ttu-id="26edb-192">Этот параметр настраивается как политика для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="26edb-192">This setting is a per-user policy.</span></span> <span data-ttu-id="26edb-193">Этот параметр управляет тем, может ли пользователь делиться доской на собрании.</span><span class="sxs-lookup"><span data-stu-id="26edb-193">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="26edb-194">Внешние пользователи, в том числе анонимные, B2B и федераированные пользователи, наследуют политику организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="26edb-194">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="26edb-195">Рассмотрим пример.</span><span class="sxs-lookup"><span data-stu-id="26edb-195">Let's look at the following example.</span></span>

|<span data-ttu-id="26edb-196">Пользователь</span><span class="sxs-lookup"><span data-stu-id="26edb-196">User</span></span> |<span data-ttu-id="26edb-197">Политика встречи</span><span class="sxs-lookup"><span data-stu-id="26edb-197">Meeting policy</span></span>  |<span data-ttu-id="26edb-198">Разрешить доску</span><span class="sxs-lookup"><span data-stu-id="26edb-198">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="26edb-199">Даниля</span><span class="sxs-lookup"><span data-stu-id="26edb-199">Daniela</span></span>   | <span data-ttu-id="26edb-200">Глобальный</span><span class="sxs-lookup"><span data-stu-id="26edb-200">Global</span></span>   | <span data-ttu-id="26edb-201">Вкл.</span><span class="sxs-lookup"><span data-stu-id="26edb-201">On</span></span>       |
|<span data-ttu-id="26edb-202">Аманда</span><span class="sxs-lookup"><span data-stu-id="26edb-202">Amanda</span></span>   | <span data-ttu-id="26edb-203">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="26edb-203">Location1MeetingPolicy</span></span>        | <span data-ttu-id="26edb-204">Выкл.</span><span class="sxs-lookup"><span data-stu-id="26edb-204">Off</span></span>   |

<span data-ttu-id="26edb-205">Алина не может поделиться доской на собрании, даже если она является организатором собрания.</span><span class="sxs-lookup"><span data-stu-id="26edb-205">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="26edb-206">Светлана может поделиться доской, даже если собрание организовано Амандой.</span><span class="sxs-lookup"><span data-stu-id="26edb-206">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

## <a name="allow-shared-notes"></a><span data-ttu-id="26edb-207">Разрешение общих заметок</span><span class="sxs-lookup"><span data-stu-id="26edb-207">Allow shared notes</span></span>

<span data-ttu-id="26edb-208">Этот параметр настраивается как политика для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="26edb-208">This setting is a per-user policy.</span></span> <span data-ttu-id="26edb-209">Этот параметр управляет возможностью создания заметок и обмена ими во время собрания.</span><span class="sxs-lookup"><span data-stu-id="26edb-209">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="26edb-210">Внешние пользователи, в том числе анонимные, B2B и федераированные пользователи, наследуют политику организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="26edb-210">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="26edb-211">Вкладка **"Заметки** к собранию" в настоящее время поддерживается только для собраний, где менее 20 участников.</span><span class="sxs-lookup"><span data-stu-id="26edb-211">The **Meeting Notes** tab is currently only supported in meetings that have fewer than 20 participants.</span></span>

<span data-ttu-id="26edb-212">Рассмотрим пример.</span><span class="sxs-lookup"><span data-stu-id="26edb-212">Let's look at the following example.</span></span>

|<span data-ttu-id="26edb-213">Пользователь</span><span class="sxs-lookup"><span data-stu-id="26edb-213">User</span></span> |<span data-ttu-id="26edb-214">Политика встречи</span><span class="sxs-lookup"><span data-stu-id="26edb-214">Meeting policy</span></span>  |<span data-ttu-id="26edb-215">Разрешение общих заметок</span><span class="sxs-lookup"><span data-stu-id="26edb-215">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="26edb-216">Даниля</span><span class="sxs-lookup"><span data-stu-id="26edb-216">Daniela</span></span>   | <span data-ttu-id="26edb-217">Глобальный</span><span class="sxs-lookup"><span data-stu-id="26edb-217">Global</span></span>   | <span data-ttu-id="26edb-218">Вкл.</span><span class="sxs-lookup"><span data-stu-id="26edb-218">On</span></span>       |
|<span data-ttu-id="26edb-219">Аманда</span><span class="sxs-lookup"><span data-stu-id="26edb-219">Amanda</span></span>   | <span data-ttu-id="26edb-220">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="26edb-220">Location1MeetingPolicy</span></span> | <span data-ttu-id="26edb-221">Выкл.</span><span class="sxs-lookup"><span data-stu-id="26edb-221">Off</span></span> |

<span data-ttu-id="26edb-222">Даниля может делать заметки на собраниях Амбаны, а Аманда не может делать заметки во время собраний.</span><span class="sxs-lookup"><span data-stu-id="26edb-222">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>




## <a name="related-topics"></a><span data-ttu-id="26edb-223">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="26edb-223">Related topics</span></span>

- [<span data-ttu-id="26edb-224">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="26edb-224">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="26edb-225">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="26edb-225">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="26edb-226">Удаление политики собраний RestrictedAnonymousAccess Teams для пользователей</span><span class="sxs-lookup"><span data-stu-id="26edb-226">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
