---
title: Планирование очереди облачных звонков
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
description: Общие сведения об использовании автосекретаря для облачных приложений в Skype для бизнеса Server 2019.
ms.openlocfilehash: 2186909b3ec905d6ec6d387bcea172d8fb80287c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221309"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="f0aa4-103">Планирование очередей облачных вызовов</span><span class="sxs-lookup"><span data-stu-id="f0aa4-103">Plan Cloud call queues</span></span>

<span data-ttu-id="f0aa4-104">"Очередь облачных вызовов" — это служба, которая принимает звонки клиентов, воспроизводит сообщение приветствия, а затем помещает эти вызовы в очередь ожидания, а затем выполняет поиск предварительно настроенного списка агентов для ответа на эти вызовы.</span><span class="sxs-lookup"><span data-stu-id="f0aa4-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="f0aa4-105">Вы можете определить набор агентов в списках рассылки или группах безопасности, поддерживающих почту.</span><span class="sxs-lookup"><span data-stu-id="f0aa4-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="f0aa4-106">Организация может иметь одну или несколько очередей звонков.</span><span class="sxs-lookup"><span data-stu-id="f0aa4-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="f0aa4-107">Очереди вызовов обычно используются в сочетании с автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="f0aa4-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="f0aa4-108">Кроме того, очереди облачных вызовов могут предоставлять следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="f0aa4-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="f0aa4-109">Музыка, когда звонящие ожидают удержания</span><span class="sxs-lookup"><span data-stu-id="f0aa4-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="f0aa4-110">Настройки параметров для максимального размера, времени ожидания и обработки звонков в очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="f0aa4-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="f0aa4-111">Каждой очереди звонков назначается **учетная запись ресурса** (см. [Настройка учетных записей ресурсов](configure-onprem-ra.md)) в системе Skype для бизнеса Server 2019, которая будет связана непосредственно с очередью звонков в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f0aa4-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="f0aa4-112">Дополнительные сведения о том, что представляют собой очереди вызовов и какие параметры и функции существуют для очередей вызовов, можно найти в разделе [Create a Cloud Queue Queue](/MicrosoftTeams/create-a-phone-system-call-queue) .</span><span class="sxs-lookup"><span data-stu-id="f0aa4-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="f0aa4-113">Очереди звонков можно назначить несколько телефонных номеров, но они должны быть номерами службы Майкрософт, прямыми номерами маршрутизации или гибридными номерами.</span><span class="sxs-lookup"><span data-stu-id="f0aa4-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers, Direct Routing numbers, or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="f0aa4-114">Requirements</span><span class="sxs-lookup"><span data-stu-id="f0aa4-114">Requirements</span></span>

<span data-ttu-id="f0aa4-115">В приведенных ниже требованиях предполагается, что у вас уже развернут Skype для бизнеса Server 2019 в поддерживаемой топологии.</span><span class="sxs-lookup"><span data-stu-id="f0aa4-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="f0aa4-116">Требования зависят от вашего сценария:</span><span class="sxs-lookup"><span data-stu-id="f0aa4-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="f0aa4-117">Чтобы создать новую конфигурацию очередей облачных вызовов, выполните действия, описанные в разделе [Настройка учетных записей ресурсов](configure-onprem-ra.md).</span><span class="sxs-lookup"><span data-stu-id="f0aa4-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="f0aa4-118">Вам потребуется создать учетные записи ресурсов как в Интернете, так и в Skype для бизнеса Server 2019, а также может потребоваться связать номер телефона с очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="f0aa4-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="f0aa4-119">В дополнение к приведенным выше требованиям необходимо настроить следующие требования для подключения к службе очереди звонков Microsoft Cloud:</span><span class="sxs-lookup"><span data-stu-id="f0aa4-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="f0aa4-120">Гибридное подключение.</span><span class="sxs-lookup"><span data-stu-id="f0aa4-120">Hybrid connectivity.</span></span> <span data-ttu-id="f0aa4-121">Если вы уже развернули Skype для бизнеса Server и хотите включить очереди облачных вызовов для локальных пользователей, необходимо убедиться в том, что гибридное подключение настроено между локальной средой и интернет-средой.</span><span class="sxs-lookup"><span data-stu-id="f0aa4-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="f0aa4-122">Иногда это называется разделенной конфигурацией домена.</span><span class="sxs-lookup"><span data-stu-id="f0aa4-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="f0aa4-123">Для получения дополнительных сведений ознакомьтесь [со статьей Планирование гибридного подключения между Skype для бизнеса Server и microsoft 365 или Office 365](plan-hybrid-connectivity.md) и [Настройка гибридного подключения между Skype для бизнеса server и Microsoft 365 или Office 365](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="f0aa4-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="f0aa4-124">Если вы назначаете номер телефона для учетной записи ресурса, вы можете использовать лицензию на виртуальную машину с свободной стоимостью для телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="f0aa4-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="f0aa4-125">Это обеспечивает возможности телефонной системы для телефонных номеров на уровне Организации, а также позволяет создавать автосекретарь и возможности очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="f0aa4-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="f0aa4-126">Создайте локальную [учетную запись ресурса](configure-onprem-ra.md) для каждой очереди звонков и при необходимости назначьте ей лицензию и номер телефона.</span><span class="sxs-lookup"><span data-stu-id="f0aa4-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

## <a name="additional-planning-resources"></a><span data-ttu-id="f0aa4-127">Дополнительные ресурсы по планированию</span><span class="sxs-lookup"><span data-stu-id="f0aa4-127">Additional planning resources</span></span>

<span data-ttu-id="f0aa4-128">В руководстве под названием " [малый бизнес" — Настройка автосекретаря —](/microsoftteams/tutorial-org-aa) это процесс сбора сведений о потребностях пользователей, планирование структуры автосекретарей и пользователей (и, возможно, вызовов очередей), написание приглашений меню и внедрение плана в центр администрирования в Интернете.</span><span class="sxs-lookup"><span data-stu-id="f0aa4-128">The tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) goes through the process of gathering information about user needs, planning a structure of auto attendants and users (and possibly call queues), writing the menu prompts, and implementing the plan in the Online Admin center.</span></span> <span data-ttu-id="f0aa4-129">Изучите руководство и используйте упражнения, чтобы создать свой план.</span><span class="sxs-lookup"><span data-stu-id="f0aa4-129">review the tutorial and use the exercises there t create your plan.</span></span>

<span data-ttu-id="f0aa4-130">Если у вас есть сплошная структура, соответствующая вашим потребностям, и сценарий, который эффективно проводит клиентов, перейдите к разделу [Настройка учетных записей ресурсов](configure-onprem-ra.md).</span><span class="sxs-lookup"><span data-stu-id="f0aa4-130">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0aa4-131">См. также</span><span class="sxs-lookup"><span data-stu-id="f0aa4-131">See Also</span></span>

[<span data-ttu-id="f0aa4-132">Настройка учетных записей ресурсов</span><span class="sxs-lookup"><span data-stu-id="f0aa4-132">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="f0aa4-133">Включение записи настраиваемых приглашений с помощью телефонного интерфейса пользователя</span><span class="sxs-lookup"><span data-stu-id="f0aa4-133">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="f0aa4-134">Что представляют собой облачные автосекретари?</span><span class="sxs-lookup"><span data-stu-id="f0aa4-134">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="f0aa4-135">Настройка облачного автосекретаря</span><span class="sxs-lookup"><span data-stu-id="f0aa4-135">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="f0aa4-136">Планирование гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="f0aa4-136">Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="f0aa4-137">Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="f0aa4-137">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="f0aa4-138">Управление учетными записями ресурсов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f0aa4-138">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)
