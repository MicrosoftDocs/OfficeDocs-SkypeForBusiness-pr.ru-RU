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
description: Обзор использования автоспутника Cloud в Skype для бизнеса Server 2019.
ms.openlocfilehash: 62731691f4e56c923d2dd8fa6057f244776ec65b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110495"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="95005-103">Планирование очередей звонков в облаке</span><span class="sxs-lookup"><span data-stu-id="95005-103">Plan Cloud call queues</span></span>

<span data-ttu-id="95005-104">Облачная очередь вызовов — это служба, которая принимает вызовы клиентов, воспроизводит приветствие, а затем помещает эти вызовы в очередь ожидания при поиске предварительно настроенного списка агентов для ответа на эти вызовы.</span><span class="sxs-lookup"><span data-stu-id="95005-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="95005-105">Набор агентов можно определить в списках рассылки с поддержкой почты или группах безопасности.</span><span class="sxs-lookup"><span data-stu-id="95005-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="95005-106">В организации может быть одна или несколько очередей вызовов.</span><span class="sxs-lookup"><span data-stu-id="95005-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="95005-107">Очереди вызовов обычно используются в сочетании с автоспутниками.</span><span class="sxs-lookup"><span data-stu-id="95005-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="95005-108">Кроме того, в облачных очередях вызовов могут быть:</span><span class="sxs-lookup"><span data-stu-id="95005-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="95005-109">Музыка, пока звонят в ожидании удержания</span><span class="sxs-lookup"><span data-stu-id="95005-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="95005-110">Настраиваемые параметры максимального размера очереди вызовов, времени ожидания и параметров обработки вызовов</span><span class="sxs-lookup"><span data-stu-id="95005-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="95005-111">Каждой очереди вызовов  назначена учетная запись ресурса (см. в статью [Настройка](configure-onprem-ra.md)учетных записей ресурсов) в системе Skype для бизнеса Server 2019, которая будет напрямую привязана к очереди вызовов в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="95005-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="95005-112">Дополнительные [подробности](/MicrosoftTeams/create-a-phone-system-call-queue) о том, какие очереди вызовов существуют и какие существуют параметры и возможности для очередей вызовов, см. в дополнительных подробностях.</span><span class="sxs-lookup"><span data-stu-id="95005-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="95005-113">Вы можете назначить несколько номеров телефонов очереди вызовов, но это должны быть номера служб Майкрософт, номера прямой маршрутной маршрутки или гибридные номера.</span><span class="sxs-lookup"><span data-stu-id="95005-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers, Direct Routing numbers, or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="95005-114">Требования</span><span class="sxs-lookup"><span data-stu-id="95005-114">Requirements</span></span>

<span data-ttu-id="95005-115">Следующие требования предполагают, что skype для бизнеса Server 2019 уже развернут в поддерживаемой топологии.</span><span class="sxs-lookup"><span data-stu-id="95005-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="95005-116">Ваши требования зависят от сценария:</span><span class="sxs-lookup"><span data-stu-id="95005-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="95005-117">Для новой конфигурации очередей вызовов Cloud выполните действия, описанные в [настройках учетных](configure-onprem-ra.md)записей ресурсов.</span><span class="sxs-lookup"><span data-stu-id="95005-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="95005-118">Вам потребуется создать учетные записи ресурсов либо в Интернете, либо в Skype для бизнеса Server 2019, а также может потребоваться связать номер телефона с очередей вызовов.</span><span class="sxs-lookup"><span data-stu-id="95005-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="95005-119">В дополнение к вышеуказанным требованиям необходимо настроить ниже требования для подключения к службе очереди вызовов Microsoft Cloud:</span><span class="sxs-lookup"><span data-stu-id="95005-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="95005-120">Гибридное подключение.</span><span class="sxs-lookup"><span data-stu-id="95005-120">Hybrid connectivity.</span></span> <span data-ttu-id="95005-121">Если у вас уже развернут Skype для бизнес-сервера и вы хотите включить очереди облачных вызовов для локального пользователя, необходимо убедиться, что между локальной и онлайн-средой установлено гибридное подключение.</span><span class="sxs-lookup"><span data-stu-id="95005-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="95005-122">Иногда это называется разделенной конфигурацией домена.</span><span class="sxs-lookup"><span data-stu-id="95005-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="95005-123">Дополнительные сведения см. в веб-сайте Plan [hybrid connectivity between Skype for Business Server и Microsoft 365 или Office 365,](plan-hybrid-connectivity.md) а также настройка гибридного подключения между Skype для бизнеса Server и [Microsoft 365 или Office 365.](configure-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="95005-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="95005-124">Если вы назначаете номер телефона учетной записи ресурса, теперь вы можете использовать бесплатную лицензию виртуального пользователя системы телефонов.</span><span class="sxs-lookup"><span data-stu-id="95005-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="95005-125">Это обеспечивает возможности телефонной системы для телефонных номеров на организационном уровне и позволяет создавать возможности автовласти и очереди на вызовы.</span><span class="sxs-lookup"><span data-stu-id="95005-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="95005-126">Создайте учетную запись локального [ресурса для](configure-onprem-ra.md) каждой очереди вызовов и при необходимости назначьте лицензию и номер телефона.</span><span class="sxs-lookup"><span data-stu-id="95005-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

<span data-ttu-id="95005-127">Если у вас есть твердая структура, которая отвечает вашим потребностям, и скрипт, который эффективно направляет клиентов, перенастройте учетные записи [ресурсов.](configure-onprem-ra.md)</span><span class="sxs-lookup"><span data-stu-id="95005-127">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="95005-128">См. также</span><span class="sxs-lookup"><span data-stu-id="95005-128">See Also</span></span>

[<span data-ttu-id="95005-129">Настройка учетных записей ресурсов</span><span class="sxs-lookup"><span data-stu-id="95005-129">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="95005-130">Включение записи настраиваемых приглашений с помощью телефонного интерфейса пользователя</span><span class="sxs-lookup"><span data-stu-id="95005-130">Enable custom prompt recording using the telephone user interface</span></span>](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="95005-131">Что представляют собой облачные автосекретари?</span><span class="sxs-lookup"><span data-stu-id="95005-131">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="95005-132">Настройка облачного автосекретаря</span><span class="sxs-lookup"><span data-stu-id="95005-132">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="95005-133">Планирование гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="95005-133">Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="95005-134">Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="95005-134">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="95005-135">Управление учетными записями ресурсов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="95005-135">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)