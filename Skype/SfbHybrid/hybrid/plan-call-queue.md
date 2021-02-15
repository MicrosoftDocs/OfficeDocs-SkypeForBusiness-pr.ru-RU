---
title: Планирование очереди вызовов в облаке
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Обзор использования облачного автоотвода со Skype для бизнеса Server 2019.
ms.openlocfilehash: 629c28e752b7316a3d2e7fda0acf7f457788d6a8
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918745"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="51207-103">Планирование очередей звонков в облаке</span><span class="sxs-lookup"><span data-stu-id="51207-103">Plan Cloud call queues</span></span>

<span data-ttu-id="51207-104">Очередь облачных звонков — это служба, которая принимает вызовы клиентов, воспроизводит приветствие, а затем помещает эти вызовы в очередь ожидания при поиске предварительно настроенного списка агентов для ответа на эти вызовы.</span><span class="sxs-lookup"><span data-stu-id="51207-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="51207-105">Вы можете определить набор агентов в списках рассылки или группах безопасности с включенной поддержкой почты.</span><span class="sxs-lookup"><span data-stu-id="51207-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="51207-106">В организации может быть одна или несколько очередей вызовов.</span><span class="sxs-lookup"><span data-stu-id="51207-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="51207-107">Очереди вызовов обычно используются в сочетании с автоспутниками.</span><span class="sxs-lookup"><span data-stu-id="51207-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="51207-108">Кроме того, облачные очереди вызовов могут предоставлять:</span><span class="sxs-lookup"><span data-stu-id="51207-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="51207-109">Музыка, в то время как звонив в ожидании удержания</span><span class="sxs-lookup"><span data-stu-id="51207-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="51207-110">Настраиваемые параметры максимального размера очереди вызовов, времени ожидания и параметров обработки вызовов</span><span class="sxs-lookup"><span data-stu-id="51207-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="51207-111">Каждой очереди звонков  назначена учетная запись ресурса (см. "Настройка учетных записей [ресурсов")](configure-onprem-ra.md)в системе Skype для бизнеса Server 2019, которая будет связана непосредственно с очередью звонков в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="51207-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="51207-112">Дополнительные [вопросы о](/MicrosoftTeams/create-a-phone-system-call-queue) том, что такое очереди вызовов и какие параметры и функции существуют для очередей вызовов, см. в подстройки "Создание облачной очереди вызовов".</span><span class="sxs-lookup"><span data-stu-id="51207-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="51207-113">Очереди звонков можно назначить несколько телефонных номеров, но они должны быть номерами служб Майкрософт, номерами прямой маршрутки или гибридными номерами.</span><span class="sxs-lookup"><span data-stu-id="51207-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers, Direct Routing numbers, or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="51207-114">Requirements</span><span class="sxs-lookup"><span data-stu-id="51207-114">Requirements</span></span>

<span data-ttu-id="51207-115">В следующих требованиях предполагается, что skype для бизнеса Server 2019 уже развернут в поддерживаемой топологии.</span><span class="sxs-lookup"><span data-stu-id="51207-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="51207-116">Ваши требования зависят от сценария:</span><span class="sxs-lookup"><span data-stu-id="51207-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="51207-117">Для новой конфигурации очередей вызовов в облаке выполните действия, описанные в настройке учетных записей [ресурсов.](configure-onprem-ra.md)</span><span class="sxs-lookup"><span data-stu-id="51207-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="51207-118">Вам потребуется создать учетные записи ресурсов в Сети или в Skype для бизнеса Server 2019, а также связать номер телефона с очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="51207-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="51207-119">Помимо перечисленных выше требований, для подключения к службе очереди вызовов Microsoft Cloud необходимо настроить перечисленные ниже требования.</span><span class="sxs-lookup"><span data-stu-id="51207-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="51207-120">Гибридное подключение.</span><span class="sxs-lookup"><span data-stu-id="51207-120">Hybrid connectivity.</span></span> <span data-ttu-id="51207-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span><span class="sxs-lookup"><span data-stu-id="51207-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="51207-122">Такая конфигурация иногда называется конфигурацией разделенного домена.</span><span class="sxs-lookup"><span data-stu-id="51207-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="51207-123">Дополнительные сведения см. в сведениях о планировании гибридного подключения между Skype для бизнеса Server и [Microsoft 365 или Office 365](plan-hybrid-connectivity.md) и настройке гибридного подключения между Skype для бизнеса Server и [Microsoft 365 или Office 365.](configure-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="51207-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="51207-124">Если вы назначаете номер телефона учетной записи ресурса, вы можете использовать бесплатную лицензию виртуального пользователя телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="51207-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="51207-125">Это обеспечивает возможности телефонной системы для телефонных номеров на уровне организации и позволяет создавать функции автоотправления и очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="51207-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="51207-126">Создайте учетную запись локального [ресурса](configure-onprem-ra.md) для каждой очереди вызовов и при необходимости назначьте лицензию и номер телефона.</span><span class="sxs-lookup"><span data-stu-id="51207-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

<span data-ttu-id="51207-127">Если у вас есть надстройка, которая соответствует вашим потребностям, и сценарий, который эффективно направляет клиентов, переходите к настройке учетных записей [ресурсов.](configure-onprem-ra.md)</span><span class="sxs-lookup"><span data-stu-id="51207-127">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="51207-128">См. также</span><span class="sxs-lookup"><span data-stu-id="51207-128">See Also</span></span>

[<span data-ttu-id="51207-129">Настройка учетных записей ресурсов</span><span class="sxs-lookup"><span data-stu-id="51207-129">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="51207-130">Включение записи настраиваемых приглашений с помощью телефонного интерфейса пользователя</span><span class="sxs-lookup"><span data-stu-id="51207-130">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="51207-131">Что представляют собой облачные автосекретари?</span><span class="sxs-lookup"><span data-stu-id="51207-131">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="51207-132">Настройка облачного автосекретаря</span><span class="sxs-lookup"><span data-stu-id="51207-132">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="51207-133">Планирование гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="51207-133">Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="51207-134">Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="51207-134">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="51207-135">Управление учетными записями ресурсов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="51207-135">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)
