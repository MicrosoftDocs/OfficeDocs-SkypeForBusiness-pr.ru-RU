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
# <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="f3d4e-103">Параметры политик собраний — отправка контента</span><span class="sxs-lookup"><span data-stu-id="f3d4e-103">Meeting policy settings - Content sharing</span></span>

<span data-ttu-id="f3d4e-104"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="f3d4e-104"><a name="bkcontentsharing"> </a></span></span>

<span data-ttu-id="f3d4e-105">В этой статье описаны следующие параметры политики собраний, связанные с совместным доступом к содержимому:</span><span class="sxs-lookup"><span data-stu-id="f3d4e-105">This article describes the following meeting policy settings related to content sharing:</span></span>

- [<span data-ttu-id="f3d4e-106">Режим демонстрации экрана</span><span class="sxs-lookup"><span data-stu-id="f3d4e-106">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="f3d4e-107">Разрешить участникам предоставлять или запрашивать управление</span><span class="sxs-lookup"><span data-stu-id="f3d4e-107">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="f3d4e-108">Разрешить внешним участникам предоставлять или запрашивать управление</span><span class="sxs-lookup"><span data-stu-id="f3d4e-108">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="f3d4e-109">Разрешить демонстрацию PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f3d4e-109">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="f3d4e-110">Разрешить доски</span><span class="sxs-lookup"><span data-stu-id="f3d4e-110">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="f3d4e-111">Разрешить общие заметки</span><span class="sxs-lookup"><span data-stu-id="f3d4e-111">Allow shared notes</span></span>](#allow-shared-notes)

## <a name="screen-sharing-mode"></a><span data-ttu-id="f3d4e-112">Режим демонстрации экрана</span><span class="sxs-lookup"><span data-stu-id="f3d4e-112">Screen sharing mode</span></span>

<span data-ttu-id="f3d4e-113">Этот параметр является сочетанием политик "на пользователя" и "на пользователя".</span><span class="sxs-lookup"><span data-stu-id="f3d4e-113">This setting is a combination of a per-organizer and per-user policies.</span></span> <span data-ttu-id="f3d4e-114">Этот параметр позволяет разрешить совместный доступ к рабочему столу и окну на собрании пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-114">This setting controls whether desktop and window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="f3d4e-115">Участники собрания, которым не назначены политики (например, анонимные, гостевые, B2B и федеративные участники), наследуют политику организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-115">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="f3d4e-116">Значение параметра</span><span class="sxs-lookup"><span data-stu-id="f3d4e-116">Setting value</span></span> |<span data-ttu-id="f3d4e-117">Поведение</span><span class="sxs-lookup"><span data-stu-id="f3d4e-117">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="f3d4e-118">**Весь экран**</span><span class="sxs-lookup"><span data-stu-id="f3d4e-118">**Entire screen**</span></span>    | <span data-ttu-id="f3d4e-119">На собрании разрешена демонстрация всего рабочего стола и демонстрация приложений</span><span class="sxs-lookup"><span data-stu-id="f3d4e-119">Full desktop sharing and application sharing are allowed in the meeting</span></span> |
|<span data-ttu-id="f3d4e-120">**Одно приложение**</span><span class="sxs-lookup"><span data-stu-id="f3d4e-120">**Single application**</span></span>   | <span data-ttu-id="f3d4e-121">На собрании разрешена демонстрация приложения</span><span class="sxs-lookup"><span data-stu-id="f3d4e-121">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="f3d4e-122">**Отключено**</span><span class="sxs-lookup"><span data-stu-id="f3d4e-122">**Disabled**</span></span>     |<span data-ttu-id="f3d4e-123">Демонстрация экрана и приложений отключена на собрании.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-123">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="f3d4e-124">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-124">Let's look at the following example.</span></span>

|<span data-ttu-id="f3d4e-125">Пользователь</span><span class="sxs-lookup"><span data-stu-id="f3d4e-125">User</span></span> |<span data-ttu-id="f3d4e-126">Политика собраний</span><span class="sxs-lookup"><span data-stu-id="f3d4e-126">Meeting policy</span></span> |<span data-ttu-id="f3d4e-127">Режим демонстрации экрана</span><span class="sxs-lookup"><span data-stu-id="f3d4e-127">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f3d4e-128">Лина</span><span class="sxs-lookup"><span data-stu-id="f3d4e-128">Daniela</span></span>  | <span data-ttu-id="f3d4e-129">Глобальная</span><span class="sxs-lookup"><span data-stu-id="f3d4e-129">Global</span></span>   | <span data-ttu-id="f3d4e-130">Весь экран</span><span class="sxs-lookup"><span data-stu-id="f3d4e-130">Entire screen</span></span> |
|<span data-ttu-id="f3d4e-131">Оксана</span><span class="sxs-lookup"><span data-stu-id="f3d4e-131">Amanda</span></span>   | <span data-ttu-id="f3d4e-132">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="f3d4e-132">Location1MeetingPolicy</span></span>  | <span data-ttu-id="f3d4e-133">Отключено</span><span class="sxs-lookup"><span data-stu-id="f3d4e-133">Disabled</span></span> |

<span data-ttu-id="f3d4e-134">Собрания, проводимые Линой, позволяют участникам собрания демонстрировать весь свой экран или конкретное приложение.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-134">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="f3d4e-135">Если Оксана присоединяется к собранию Лины, Оксана не может демонстрировать свой экран или определенное приложение, так как ее параметр политики отключен.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-135">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="f3d4e-136">На собраниях, проводимых Оксаной, никто не может демонстрировать свой экран или отдельное приложение, независимо от назначенной им политики режима демонстрации экрана.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-136">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span>  <span data-ttu-id="f3d4e-137">Поэтому Светлана не может делиться своим экраном или одним приложением на собраниях Аманды.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-137">Consequently, Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="f3d4e-138">В настоящее время пользователи не могут воспроизводить видео или делиться своим экраном на собрании Teams, если они используют Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-138">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

## <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="f3d4e-139">Разрешить участникам предоставлять или запрашивать управление</span><span class="sxs-lookup"><span data-stu-id="f3d4e-139">Allow a participant to give or request control</span></span>

<span data-ttu-id="f3d4e-140">Этот параметр является политикой на пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-140">This setting is a per-user policy.</span></span> <span data-ttu-id="f3d4e-141">Этот параметр определяет, может ли пользователь предоставить управление демонстрируемым рабочим столом или окном другим участникам собрания.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-141">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="f3d4e-142">Чтобы предоставить управление, наведите курсор на верхнюю часть экрана.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-142">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="f3d4e-143">Если этот параметр включен для пользователя, на верхней панели сеанса демонстрации отображается параметр **Предоставить управление**.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-143">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![Снимок экрана: параметр "Предоставить управление"](media/meeting-policies-give-control.png)

<span data-ttu-id="f3d4e-145">Если этот параметр отключен для пользователя, параметр **Предоставить управление** недоступен.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-145">If the setting is turned off for the user, the **Give Control** option isn't available.</span></span>

![Снимок экрана: параметр "Предоставить управление" недоступен](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="f3d4e-147">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-147">Let's look at the following example.</span></span>

|<span data-ttu-id="f3d4e-148">Пользователь</span><span class="sxs-lookup"><span data-stu-id="f3d4e-148">User</span></span> |<span data-ttu-id="f3d4e-149">Политика собраний</span><span class="sxs-lookup"><span data-stu-id="f3d4e-149">Meeting policy</span></span>  |<span data-ttu-id="f3d4e-150">Разрешить участникам предоставлять или запрашивать управление</span><span class="sxs-lookup"><span data-stu-id="f3d4e-150">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f3d4e-151">Лина</span><span class="sxs-lookup"><span data-stu-id="f3d4e-151">Daniela</span></span>   | <span data-ttu-id="f3d4e-152">Глобальная</span><span class="sxs-lookup"><span data-stu-id="f3d4e-152">Global</span></span>   | <span data-ttu-id="f3d4e-153">Вкл</span><span class="sxs-lookup"><span data-stu-id="f3d4e-153">On</span></span>       |
|<span data-ttu-id="f3d4e-154">Виктор</span><span class="sxs-lookup"><span data-stu-id="f3d4e-154">Babek</span></span>    | <span data-ttu-id="f3d4e-155">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="f3d4e-155">Location1MeetingPolicy</span></span>        | <span data-ttu-id="f3d4e-156">Выкл</span><span class="sxs-lookup"><span data-stu-id="f3d4e-156">Off</span></span>   |

<span data-ttu-id="f3d4e-157">Дарья может предоставить управление рабочим столом или окном другим участникам собрания, организованного Дарьей.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-157">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek.</span></span> <span data-ttu-id="f3d4e-158">Однако Он не может предоставить управление другим участникам.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-158">However, Babek can't give control to other participants.</span></span>

<span data-ttu-id="f3d4e-159">Чтобы с помощью PowerShell определить, кто может предоставлять управление или принимать запросы на управление, используйте командлет AllowParticipantGiveRequestControl.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-159">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="f3d4e-160">Чтобы предоставлять и принимать управление общим контентом во время демонстрации, обе стороны должны применять классический клиент Teams.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-160">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="f3d4e-161">Управление не поддерживается, если одна из сторон использует Teams в браузере.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-161">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="f3d4e-162">Это связано с техническим ограничением, которое мы планируем устранить.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-162">This is due to a technical limitation that we're planning to fix.</span></span>

## <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="f3d4e-163">Разрешить внешним участникам предоставлять или запрашивать управление</span><span class="sxs-lookup"><span data-stu-id="f3d4e-163">Allow an external participant to give or request control</span></span>

<span data-ttu-id="f3d4e-164">Этот параметр является политикой на пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-164">This setting is a per-user policy.</span></span> <span data-ttu-id="f3d4e-165">Если в организации настроена эта политика для пользователя, то какие действия могут делать внешние участники, независимо от заданной организатором собрания.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-165">Whether an organization has set this policy for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="f3d4e-166">Этот параметр определяет, могут ли внешние участники предоставлять или запрашивать управление экраном пользователя, предоставившего общий доступ, в зависимости от того, что этот пользователь настроил в политиках собраний своей организации.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-166">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="f3d4e-167">Внешних участников собраний Teams можно классифицировать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-167">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="f3d4e-168">Анонимный пользователь</span><span class="sxs-lookup"><span data-stu-id="f3d4e-168">Anonymous user</span></span>
- <span data-ttu-id="f3d4e-169">Гостевые пользователи</span><span class="sxs-lookup"><span data-stu-id="f3d4e-169">Guest users</span></span>  
- <span data-ttu-id="f3d4e-170">Пользователь B2B</span><span class="sxs-lookup"><span data-stu-id="f3d4e-170">B2B user</span></span>
- <span data-ttu-id="f3d4e-171">Федеративный пользователь</span><span class="sxs-lookup"><span data-stu-id="f3d4e-171">Federated user</span></span>  

<span data-ttu-id="f3d4e-172">Возможность предоставления федеративными пользователями управления внешним пользователям при общем доступе управляется параметром **Разрешить внешним участникам предоставлять или запрашивать управление** в их организации.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-172">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="f3d4e-173">Чтобы с помощью PowerShell определить, могут ли внешние участники предоставлять управление или принимать запросы на управление, используйте командлет AllowExternalParticipantGiveRequestControl.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-173">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="f3d4e-174">Разрешить демонстрацию PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f3d4e-174">Allow PowerPoint sharing</span></span>

<span data-ttu-id="f3d4e-175">Это политика для пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-175">This is a per-user policy.</span></span> <span data-ttu-id="f3d4e-176">Этот параметр определяет, может ли пользователь демонстрировать презентации PowerPoint на собрании.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-176">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="f3d4e-177">Внешние пользователи, включая анонимных, гостевых и федеративных, наследуют политику организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-177">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="f3d4e-178">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-178">Let's look at the following example.</span></span>

|<span data-ttu-id="f3d4e-179">Пользователь</span><span class="sxs-lookup"><span data-stu-id="f3d4e-179">User</span></span> |<span data-ttu-id="f3d4e-180">Политика собраний</span><span class="sxs-lookup"><span data-stu-id="f3d4e-180">Meeting policy</span></span>  |<span data-ttu-id="f3d4e-181">Разрешить демонстрацию PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f3d4e-181">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f3d4e-182">Лина</span><span class="sxs-lookup"><span data-stu-id="f3d4e-182">Daniela</span></span>   | <span data-ttu-id="f3d4e-183">Глобальная</span><span class="sxs-lookup"><span data-stu-id="f3d4e-183">Global</span></span>   | <span data-ttu-id="f3d4e-184">Вкл</span><span class="sxs-lookup"><span data-stu-id="f3d4e-184">On</span></span>       |
|<span data-ttu-id="f3d4e-185">Оксана</span><span class="sxs-lookup"><span data-stu-id="f3d4e-185">Amanda</span></span>   | <span data-ttu-id="f3d4e-186">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="f3d4e-186">Location1MeetingPolicy</span></span>        | <span data-ttu-id="f3d4e-187">Выкл</span><span class="sxs-lookup"><span data-stu-id="f3d4e-187">Off</span></span>   |

<span data-ttu-id="f3d4e-188">Оксана не может демонстрировать презентации PowerPoint на собраниях, даже если она является организатором собрания.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-188">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="f3d4e-189">Лина может демонстрировать презентации PowerPoint, даже если собрание организовано Оксаной.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-189">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="f3d4e-190">Оксана может просматривать презентации PowerPoint, демонстрируемые другими людьми на собрании, хотя она и не может демонстрировать презентации PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-190">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

## <a name="allow-whiteboard"></a><span data-ttu-id="f3d4e-191">Разрешить доски</span><span class="sxs-lookup"><span data-stu-id="f3d4e-191">Allow whiteboard</span></span>

<span data-ttu-id="f3d4e-192">Этот параметр является политикой на пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-192">This setting is a per-user policy.</span></span> <span data-ttu-id="f3d4e-193">Этот параметр определяет, может ли пользователь демонстрировать доску на собрании.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-193">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="f3d4e-194">Внешние пользователи, включая анонимных, B2B и федеративных, наследуют политику организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-194">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="f3d4e-195">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-195">Let's look at the following example.</span></span>

|<span data-ttu-id="f3d4e-196">Пользователь</span><span class="sxs-lookup"><span data-stu-id="f3d4e-196">User</span></span> |<span data-ttu-id="f3d4e-197">Политика собраний</span><span class="sxs-lookup"><span data-stu-id="f3d4e-197">Meeting policy</span></span>  |<span data-ttu-id="f3d4e-198">Разрешить доски</span><span class="sxs-lookup"><span data-stu-id="f3d4e-198">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="f3d4e-199">Лина</span><span class="sxs-lookup"><span data-stu-id="f3d4e-199">Daniela</span></span>   | <span data-ttu-id="f3d4e-200">Глобальная</span><span class="sxs-lookup"><span data-stu-id="f3d4e-200">Global</span></span>   | <span data-ttu-id="f3d4e-201">Вкл</span><span class="sxs-lookup"><span data-stu-id="f3d4e-201">On</span></span>       |
|<span data-ttu-id="f3d4e-202">Оксана</span><span class="sxs-lookup"><span data-stu-id="f3d4e-202">Amanda</span></span>   | <span data-ttu-id="f3d4e-203">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="f3d4e-203">Location1MeetingPolicy</span></span>        | <span data-ttu-id="f3d4e-204">Выкл</span><span class="sxs-lookup"><span data-stu-id="f3d4e-204">Off</span></span>   |

<span data-ttu-id="f3d4e-205">Оксана не может демонстрировать доску на собрании, даже если она является организатором собрания.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-205">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="f3d4e-206">Лина может демонстрировать доску, даже если собрание организовано Оксаной.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-206">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

## <a name="allow-shared-notes"></a><span data-ttu-id="f3d4e-207">Разрешить общие заметки</span><span class="sxs-lookup"><span data-stu-id="f3d4e-207">Allow shared notes</span></span>

<span data-ttu-id="f3d4e-208">Этот параметр является политикой на пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-208">This setting is a per-user policy.</span></span> <span data-ttu-id="f3d4e-209">Этот параметр определяет, может ли пользователь создавать заметки и делиться ими на собрании.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-209">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="f3d4e-210">Внешние пользователи, включая анонимных, B2B и федеративных, наследуют политику организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-210">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="f3d4e-211">Вкладка **Заметки** к собранию в настоящее время поддерживается только для собраний, в которые не более 20 участников.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-211">The **Meeting Notes** tab is currently only supported in meetings that have fewer than 20 participants.</span></span>

<span data-ttu-id="f3d4e-212">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-212">Let's look at the following example.</span></span>

|<span data-ttu-id="f3d4e-213">Пользователь</span><span class="sxs-lookup"><span data-stu-id="f3d4e-213">User</span></span> |<span data-ttu-id="f3d4e-214">Политика собраний</span><span class="sxs-lookup"><span data-stu-id="f3d4e-214">Meeting policy</span></span>  |<span data-ttu-id="f3d4e-215">Разрешить общие заметки</span><span class="sxs-lookup"><span data-stu-id="f3d4e-215">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f3d4e-216">Лина</span><span class="sxs-lookup"><span data-stu-id="f3d4e-216">Daniela</span></span>   | <span data-ttu-id="f3d4e-217">Глобальная</span><span class="sxs-lookup"><span data-stu-id="f3d4e-217">Global</span></span>   | <span data-ttu-id="f3d4e-218">Вкл</span><span class="sxs-lookup"><span data-stu-id="f3d4e-218">On</span></span>       |
|<span data-ttu-id="f3d4e-219">Оксана</span><span class="sxs-lookup"><span data-stu-id="f3d4e-219">Amanda</span></span>   | <span data-ttu-id="f3d4e-220">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="f3d4e-220">Location1MeetingPolicy</span></span> | <span data-ttu-id="f3d4e-221">Выкл</span><span class="sxs-lookup"><span data-stu-id="f3d4e-221">Off</span></span> |

<span data-ttu-id="f3d4e-222">Лина может создавать заметки на собраниях Оксаны, а Оксане ведение заметок недоступно на любых собраниях.</span><span class="sxs-lookup"><span data-stu-id="f3d4e-222">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>




## <a name="related-topics"></a><span data-ttu-id="f3d4e-223">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f3d4e-223">Related topics</span></span>

- [<span data-ttu-id="f3d4e-224">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="f3d4e-224">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="f3d4e-225">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="f3d4e-225">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="f3d4e-226">Удаление политики собраний Teams RestrictedAnonymousAccess для пользователей</span><span class="sxs-lookup"><span data-stu-id="f3d4e-226">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
