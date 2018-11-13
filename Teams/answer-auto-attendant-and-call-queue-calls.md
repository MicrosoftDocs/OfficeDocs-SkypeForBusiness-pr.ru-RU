---
title: Ответ автосекретаря и вызвать очереди звонки непосредственно из рабочих групп
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: article
ms.service: msteams
description: Описание автосекретари телефонной системой и очереди вызовов и объясняется, как можно отвечать на звонки, эти в группах.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b176131cd8c491916f8b934daa763e62a9bf2a8
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294707"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="4e1e1-103">Ответ автосекретаря и вызвать очереди звонки непосредственно из рабочих групп</span><span class="sxs-lookup"><span data-stu-id="4e1e1-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="4e1e1-104">Группы Пользователи могут получить и отвечать на звонки от Скайп для бизнеса в Интернет, принимаемые автосекретарем и вызовите очередей непосредственно из клиента по группам.</span><span class="sxs-lookup"><span data-stu-id="4e1e1-104">Teams users can receive and answer calls from Skype for Business Online auto attendant and call queues directly from their Teams client.</span></span> <span data-ttu-id="4e1e1-105">Для пользователей, групп функцию автоматического attendant теперь доступен обычно и является возможность вызова очереди в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="4e1e1-105">For Teams users, the auto attendant feature is now generally available, and the call queue capability is in preview.</span></span> 

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="4e1e1-106">Что такое автосекретари и вызвать очереди?</span><span class="sxs-lookup"><span data-stu-id="4e1e1-106">What are auto attendants and call queues?</span></span>

<span data-ttu-id="4e1e1-107">Автосекретари телефонной системы предоставляют ряд голосовых запросов или звукового файла, который абоненты прослушивают вместо человеческого оператор, когда он совершает вызов к организации.</span><span class="sxs-lookup"><span data-stu-id="4e1e1-107">Phone System auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="4e1e1-108">Автосекретарь позволяет абонентов перемещения по системе меню, звонки, или выберите пользователей с помощью клавиатуры телефона (DTMF) или голосовых входные данные с помощью распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="4e1e1-108">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="4e1e1-109">Телефонный звонок системы очередей включают приветствие, используемые при получении звонка на номер телефона для вашей организации, возможность автоматически переводить звонки в режим удержания и возможность поиска для следующего агента доступные вызова для обработки вызова при людей, вызов прослушивают музыку при удержании.</span><span class="sxs-lookup"><span data-stu-id="4e1e1-109">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="4e1e1-110">Вы можете создать для своей организации одну или несколько очередей вызовов.</span><span class="sxs-lookup"><span data-stu-id="4e1e1-110">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="4e1e1-111">Обработка вызова auto attendant или звонок очереди</span><span class="sxs-lookup"><span data-stu-id="4e1e1-111">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="4e1e1-112">Пользователи будут иметь возможность различать входящие звонки из очереди auto attendant или звонок, прежде чем они ответить на звонок.</span><span class="sxs-lookup"><span data-stu-id="4e1e1-112">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="4e1e1-113">А также имя или номер вызывающего абонента каждого вызова будут включены сведения о пользователей, которые вызывающего абонента пытается получить доступ, предоставляя пользователям лучше контекста для адресации вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="4e1e1-113">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="4e1e1-114">Ниже показано, как будет выглядеть входящего звонка из очереди auto attendant или звонок пользователю.</span><span class="sxs-lookup"><span data-stu-id="4e1e1-114">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Уведомление о входящем звонке](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="4e1e1-116">После был дан ответ на звонок auto attendant или звонок очереди, пользователь может обработать вызов, например других вызовов & #x 2014 г.; они могут добавлять или конференции в другой пользователь или переключить звонок на другой стороны.</span><span class="sxs-lookup"><span data-stu-id="4e1e1-116">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="4e1e1-117">Кроме того auto attendant будет необходимо перенаправлять неотвеченные звонки на основе конфигурации пользователя.</span><span class="sxs-lookup"><span data-stu-id="4e1e1-117">Also, auto attendant calls will be forwarded based on the user’s configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="4e1e1-118">Звонок звонки очереди не перенаправляются на основе конфигурации пользователя.</span><span class="sxs-lookup"><span data-stu-id="4e1e1-118">Call queue calls are not forwarded based on the user’s configuration.</span></span> <span data-ttu-id="4e1e1-119">Это гарантирует абонентов остаются в очереди, пока агент может ответить на звонок и неожиданно не будет перенаправлять звонящего.</span><span class="sxs-lookup"><span data-stu-id="4e1e1-119">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn’t forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="4e1e1-120">Поддерживаемые клиенты</span><span class="sxs-lookup"><span data-stu-id="4e1e1-120">Supported clients</span></span>

<span data-ttu-id="4e1e1-121">Поддержка auto attendant и вызова очереди звонков доступна в следующих клиентов:</span><span class="sxs-lookup"><span data-stu-id="4e1e1-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-   <span data-ttu-id="4e1e1-122">Клиент Microsoft Teams Windows (32- и 64-разрядные версии)</span><span class="sxs-lookup"><span data-stu-id="4e1e1-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-   <span data-ttu-id="4e1e1-123">Клиент Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="4e1e1-123">Microsoft Teams Mac client</span></span>
-   <span data-ttu-id="4e1e1-124">Группами Майкрософт для iPhone</span><span class="sxs-lookup"><span data-stu-id="4e1e1-124">Microsoft Teams iPhone app</span></span>
-   <span data-ttu-id="4e1e1-125">Приложения для Android группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4e1e1-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="4e1e1-126">Настройка auto attendant и вызова поддержки очереди для групп Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4e1e1-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="4e1e1-127">Для получения автосекретаря и вызов очереди вызовов на группами Майкрософт, необходимых для настройки политики взаимодействия и обновление политики.</span><span class="sxs-lookup"><span data-stu-id="4e1e1-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="4e1e1-128">Ознакомьтесь с [миграции и взаимодействия для организаций, с помощью команды Скайп для бизнеса](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="4e1e1-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="4e1e1-129">У вас нет автосекретаря и/или очереди вызовов настроена и вы хотите этого, в статье [Настройка автосекретаря телефонной системой](https://docs.microsoft.com/en-us/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) и [Создание очереди вызовов с телефонной системой](https://docs.microsoft.com/en-us/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).</span><span class="sxs-lookup"><span data-stu-id="4e1e1-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Phone System auto attendant](https://docs.microsoft.com/en-us/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) and [Create a Phone System call queue](https://docs.microsoft.com/en-us/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4e1e1-130">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="4e1e1-130">Related topics</span></span>

-   [<span data-ttu-id="4e1e1-131">Что такое телефонной системой в Office 365</span><span class="sxs-lookup"><span data-stu-id="4e1e1-131">What is Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
-   [<span data-ttu-id="4e1e1-132">Создание очереди звонков в телефонной системе</span><span class="sxs-lookup"><span data-stu-id="4e1e1-132">Create a Phone System call queue</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)
-   [<span data-ttu-id="4e1e1-133">Что такое автосекретари телефонной системы?</span><span class="sxs-lookup"><span data-stu-id="4e1e1-133">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-   [<span data-ttu-id="4e1e1-134">Настройка автосекретаря телефонной системы</span><span class="sxs-lookup"><span data-stu-id="4e1e1-134">Set up a Phone System auto attendant</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

