---
title: Ответ на звонки автосекретарей и очередей звонков непосредственно из Teams
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: В этой статье описываются автоматические ассистенты и очереди звонков, а также объясняется, как можно ответить на эти звонки в Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 855029001863b6603548c865d5f7bfb039261a18
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494834"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="c22a9-103">Ответ на звонки автосекретарей и очередей звонков непосредственно из Teams</span><span class="sxs-lookup"><span data-stu-id="c22a9-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="c22a9-104">Пользователи Teams могут получать и отвечать на звонки из облачных автосекретарей и из очереди звонков непосредственно из клиента Teams.</span><span class="sxs-lookup"><span data-stu-id="c22a9-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span> <span data-ttu-id="c22a9-105">Для пользователей Teams Функция автосекретаря теперь доступна, и в предварительной версии доступна функция очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="c22a9-105">For Teams users, the auto attendant feature is now generally available, and the call queue capability is in preview.</span></span> 

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="c22a9-106">Что такое автоматические ассистенты и очереди звонков?</span><span class="sxs-lookup"><span data-stu-id="c22a9-106">What are auto attendants and call queues?</span></span>

<span data-ttu-id="c22a9-107">Облачные автоматические ассистенты предоставляют ряд голосовых запросов или звуковые файлы, которые абоненты могут слышать, а не сотруднику, когда они позвони в организацию.</span><span class="sxs-lookup"><span data-stu-id="c22a9-107">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="c22a9-108">Автосекретарь позволяет звонящим перемещаться по системе меню, звонить или находить пользователей, используя клавиатуру телефона (DTMF) или входные данные голосовой связи с помощью функции распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="c22a9-108">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="c22a9-109">Очереди облачных вызовов включают приветствия, которые используются при звонках на номер телефона для вашей организации, возможность автоматически помещать звонки на удержание и возможность поиска следующего доступного агента звонков для обработки звонка во время звонка. Прослушивание музыки на удержании.</span><span class="sxs-lookup"><span data-stu-id="c22a9-109">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="c22a9-110">Вы можете создать для своей организации одну или несколько очередей вызовов.</span><span class="sxs-lookup"><span data-stu-id="c22a9-110">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="c22a9-111">Работа с автосекретарем и звонком из очереди звонков</span><span class="sxs-lookup"><span data-stu-id="c22a9-111">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="c22a9-112">Пользователи смогут отличать входящие звонки от автосекретаря или из очереди звонков перед тем, как они будут отвечать на звонок.</span><span class="sxs-lookup"><span data-stu-id="c22a9-112">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="c22a9-113">Вместе с именем и (или) номером вызывающего абонента каждый из них будет включать информацию о том, кто пытается связаться с вызывающим абонентом, давая пользователям лучший контекст для адресации вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="c22a9-113">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="c22a9-114">На приведенном ниже рисунке показано, как входящий звонок от автосекретаря или очереди звонков будет отображаться для пользователя.</span><span class="sxs-lookup"><span data-stu-id="c22a9-114">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Снимок экрана с уведомлением о входящем звонке](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="c22a9-116">После получения ответа на вызов автосекретаря или очереди звонков пользователь может обработать звонок, как любой другой звонок _Амп_ # x2014; они могут добавлять или проводить конференции другого пользователя или передавать Звонок другой стороне.</span><span class="sxs-lookup"><span data-stu-id="c22a9-116">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="c22a9-117">Кроме того, звонки автосекретаря будут переадресованы на основе конфигурации пользователя.</span><span class="sxs-lookup"><span data-stu-id="c22a9-117">Also, auto attendant calls will be forwarded based on the user’s configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="c22a9-118">Звонки из очереди звонков не пересылаются на основе конфигурации пользователя.</span><span class="sxs-lookup"><span data-stu-id="c22a9-118">Call queue calls are not forwarded based on the user’s configuration.</span></span> <span data-ttu-id="c22a9-119">Это необходимо для того, чтобы вызывающие объекты оставались в очереди, пока агент не сможет ответить на звонок, и вызывающий абонент не будет переадресован.</span><span class="sxs-lookup"><span data-stu-id="c22a9-119">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn’t forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="c22a9-120">Поддерживаемые клиенты</span><span class="sxs-lookup"><span data-stu-id="c22a9-120">Supported clients</span></span>

<span data-ttu-id="c22a9-121">Поддержка автосекретаря и звонков из очереди звонков доступна на следующих клиентах:</span><span class="sxs-lookup"><span data-stu-id="c22a9-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-   <span data-ttu-id="c22a9-122">Клиент Microsoft Teams Windows (32- и 64-разрядные версии)</span><span class="sxs-lookup"><span data-stu-id="c22a9-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-   <span data-ttu-id="c22a9-123">Клиент Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="c22a9-123">Microsoft Teams Mac client</span></span>
-   <span data-ttu-id="c22a9-124">Приложение Microsoft Teams для iPhone</span><span class="sxs-lookup"><span data-stu-id="c22a9-124">Microsoft Teams iPhone app</span></span>
-   <span data-ttu-id="c22a9-125">Приложение Microsoft Teams для Android</span><span class="sxs-lookup"><span data-stu-id="c22a9-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="c22a9-126">Настройка поддержки автосекретаря и очереди звонков для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c22a9-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="c22a9-127">Чтобы получать автосекретаря и звонки из очереди звонков в Microsoft Teams, необходимо настроить политику взаимодействия и политику обновления.</span><span class="sxs-lookup"><span data-stu-id="c22a9-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="c22a9-128">Пожалуйста, просматривайте [миграцию и взаимодействие для организаций, использующих Teams вместе со Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="c22a9-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="c22a9-129">Если вы не обладаете автосекретарем и (или) очередью звонков, и это нужно сделать, ознакомьтесь со сведениями о [настройке автоматического ассистента в облаке](create-a-phone-system-auto-attendant.md) и [создании очереди облачных звонков](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="c22a9-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c22a9-130">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c22a9-130">Related topics</span></span>

-   [<span data-ttu-id="c22a9-131">Что такое телефонная система в Office 365</span><span class="sxs-lookup"><span data-stu-id="c22a9-131">What is Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
-   [<span data-ttu-id="c22a9-132">Создание облачной очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="c22a9-132">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-   [<span data-ttu-id="c22a9-133">Что представляют собой облачные автосекретари?</span><span class="sxs-lookup"><span data-stu-id="c22a9-133">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-   [<span data-ttu-id="c22a9-134">Настройка облачного автосекретаря</span><span class="sxs-lookup"><span data-stu-id="c22a9-134">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

