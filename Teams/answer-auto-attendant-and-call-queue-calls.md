---
title: Ответ на автоответы и вызовы очереди звонков
ms.reviewer: colongma
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: В этой статье описаны автоответы и очереди звонков в облаке, а также объясняется, как можно отвечать на эти звонки в Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3e1656af8ee457cb4c112d229c2dee03d2590ece
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856378"
---
# <a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="a4547-103">Ответ на звонки автосекретарей и очередей вызовов непосредственно из Teams</span><span class="sxs-lookup"><span data-stu-id="a4547-103">Answer auto attendant and call queue calls directly from Teams</span></span>

<span data-ttu-id="a4547-104">Teams пользователи могут принимать звонки и отвечать на них от автоответников и очередей звонков в облаке непосредственно из Teams клиента.</span><span class="sxs-lookup"><span data-stu-id="a4547-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span>

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="a4547-105">Что такое автозаводы и очереди вызовов?</span><span class="sxs-lookup"><span data-stu-id="a4547-105">What are auto attendants and call queues?</span></span>

<span data-ttu-id="a4547-106">Автозавершающие в облаке предоставляют ряд голосовых подсказок или аудиофайл, которые звонят вызывающие участники, а не операторы, когда звонят в организацию.</span><span class="sxs-lookup"><span data-stu-id="a4547-106">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="a4547-107">Автоответчик может перемещаться по системе меню, размещать звонки или находить пользователей с помощью клавиатурной панели телефона (DTMF) или голосового ввода с помощью распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="a4547-107">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="a4547-108">В очередях облачных звонков есть приветствия, которые используются, когда кто-то звонит на номер телефона вашей организации, возможность автоматически помещать звонки на удержание, а также возможность поиска следующего доступного агента для обработки звонка, когда вызывавший звонок прослушивает музыку на удержании.</span><span class="sxs-lookup"><span data-stu-id="a4547-108">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="a4547-109">Вы можете создать для своей организации одну или несколько очередей вызовов.</span><span class="sxs-lookup"><span data-stu-id="a4547-109">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="a4547-110">Обработка вызова автозаправщика или очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="a4547-110">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="a4547-111">Пользователи смогут различать входящие звонки от автозавода или очереди звонков, прежде чем отвечать на звонок.</span><span class="sxs-lookup"><span data-stu-id="a4547-111">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="a4547-112">Вместе с именем и (или) номером вызываемого звонка в каждый звонок включается информация о том, с кем вызывался звонок, что позволяет улучшить контекст для связи с звонившего.</span><span class="sxs-lookup"><span data-stu-id="a4547-112">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="a4547-113">На следующем рисунке показано, как будет выглядеть входящий звонок от автозавода или очереди вызовов для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a4547-113">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Снимок экрана: уведомление о входящих звонках](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="a4547-115">После ответа автозаводщика или вызова в очереди звонка пользователь может обработать звонок так же, как и любой другой звонок &#x2014; добавить или на конференцию другого пользователя или передать звонок другой стороне.</span><span class="sxs-lookup"><span data-stu-id="a4547-115">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="a4547-116">Кроме того, звонки автоответа будут перенакладываться в зависимости от конфигурации пользователя.</span><span class="sxs-lookup"><span data-stu-id="a4547-116">Also, auto attendant calls will be forwarded based on the user's configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="a4547-117">Звонки из очереди звонков не переадваровыются в зависимости от конфигурации пользователя.</span><span class="sxs-lookup"><span data-stu-id="a4547-117">Call queue calls are not forwarded based on the user's configuration.</span></span> <span data-ttu-id="a4547-118">Это необходимо для того, чтобы звонки оставались в очереди до тех пор, пока агент не сможет ответить на звонок и не будет неожиданно переададант.</span><span class="sxs-lookup"><span data-stu-id="a4547-118">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn't forwarded unexpectedly.</span></span>

> <span data-ttu-id="a4547-119">Агенты будут уведомлены о пропущенных звонках или голосовых сообщениях для звонков в очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="a4547-119">Agents are not notified of any missed calls or voicemails for call queue calls.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="a4547-120">Поддерживаемые клиенты</span><span class="sxs-lookup"><span data-stu-id="a4547-120">Supported clients</span></span>

<span data-ttu-id="a4547-121">Поддержка автоответов и звонков в очереди звонков доступна в следующих клиентах:</span><span class="sxs-lookup"><span data-stu-id="a4547-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-    <span data-ttu-id="a4547-122">Клиент Microsoft Teams Windows (32- и 64-разрядные версии)</span><span class="sxs-lookup"><span data-stu-id="a4547-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-    <span data-ttu-id="a4547-123">Клиент Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="a4547-123">Microsoft Teams Mac client</span></span>
-    <span data-ttu-id="a4547-124">Microsoft Teams iPhone приложение</span><span class="sxs-lookup"><span data-stu-id="a4547-124">Microsoft Teams iPhone app</span></span>
-    <span data-ttu-id="a4547-125">Microsoft Teams Приложение для Android</span><span class="sxs-lookup"><span data-stu-id="a4547-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="a4547-126">Настройка поддержки автоотетаря и очереди вызовов для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a4547-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="a4547-127">Чтобы получать автоответы и вызовы очереди звонков Microsoft Teams, необходимо настроить политику interoperability и политику обновления.</span><span class="sxs-lookup"><span data-stu-id="a4547-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="a4547-128">Проверьте [миграцию и возможности совместной работы](migration-interop-guidance-for-teams-with-skype.md)для организаций, использующих Teams вместе с Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a4547-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="a4547-129">Если вы не настроили автоотвод или очередь вызовов [](create-a-phone-system-auto-attendant.md) и хотите сделать это, см. настройки автозавода в облаке и Создание очереди вызовов [в облаке.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="a4547-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="a4547-130">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a4547-130">Known Issues</span></span>

<span data-ttu-id="a4547-131">Когда операторы очереди звонков получают звонок на мобильном устройстве, звонки могут переходить на удержание, если устройство заблокировано.</span><span class="sxs-lookup"><span data-stu-id="a4547-131">When a call queue agents receives a call on their mobile device, calls may go on hold if the device is locked.</span></span> <span data-ttu-id="a4547-132">Пользователь должен сначала разблокировать устройство, а затем ответить на звонок.</span><span class="sxs-lookup"><span data-stu-id="a4547-132">User must unlock device first and then answer the call.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a4547-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a4547-133">Related topics</span></span>

-    [<span data-ttu-id="a4547-134">Что телефонная система в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="a4547-134">What is Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
-    [<span data-ttu-id="a4547-135">Создание облачной очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="a4547-135">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-    [<span data-ttu-id="a4547-136">Что представляют собой облачные автосекретари?</span><span class="sxs-lookup"><span data-stu-id="a4547-136">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-    [<span data-ttu-id="a4547-137">Настройка облачного автосекретаря</span><span class="sxs-lookup"><span data-stu-id="a4547-137">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

