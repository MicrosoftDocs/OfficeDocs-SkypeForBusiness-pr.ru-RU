---
title: 'Teams голосом: пример: Contoso'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams на примере голосовой почты для многоязычной корпорации
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786103"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="33b5d-103">Пример: экстренные вызовы в Contoso</span><span class="sxs-lookup"><span data-stu-id="33b5d-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="33b5d-104">Чтобы понять доступность экстренных вызовов и терминов, связанных с адресом, местоположением, местоположением для экстренного вызова и зарегистрированным адресом, &mdash; &mdash; Contoso, [](what-are-emergency-locations-addresses-and-call-routing.md) [](configure-dynamic-emergency-calling.md)мы рассмотрели управление экстренными вызовами и планирование и настройку динамических экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="33b5d-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="33b5d-105">В Office 365 для пользователя плана звонков автоматически включены экстренные вызовы.</span><span class="sxs-lookup"><span data-stu-id="33b5d-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="33b5d-106">Но только пользователи плана звонков в США могут использовать динамические расположения для маршрутации экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="33b5d-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="33b5d-107">При прямой маршрутике Contoso узнал, что для маршрутации экстренных звонков и, возможно, для подключения партнеров требуется дополнительная конфигурация.</span><span class="sxs-lookup"><span data-stu-id="33b5d-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="33b5d-108">Администратор должен настроить подключение к поставщику услуг экстренных маршрутов (США) или настроить SBC для приложения ELIN для идентификационных номеров экстренных расположений.</span><span class="sxs-lookup"><span data-stu-id="33b5d-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="33b5d-109">У Contoso есть офисы в США и за пределами США:</span><span class="sxs-lookup"><span data-stu-id="33b5d-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="33b5d-110">В США пользователи плана звонков Contoso могут использовать динамические расположения для маршрутации экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="33b5d-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="33b5d-111">За пределами США в Contoso есть некоторые сайты, которые используют планы звонков, и некоторые сайты, подключенные к телефонная система прямой маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="33b5d-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="33b5d-112">Случаи использования экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="33b5d-112">Emergency calling use cases</span></span>

<span data-ttu-id="33b5d-113">После принятия решения о том, как Contoso будет подключаться к Телефон, Contoso определил следующие случаи использования экстренных вызовов:</span><span class="sxs-lookup"><span data-stu-id="33b5d-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="33b5d-114">Пользователь плана звонков в США</span><span class="sxs-lookup"><span data-stu-id="33b5d-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="33b5d-115">Пользователь плана звонков за пределами США</span><span class="sxs-lookup"><span data-stu-id="33b5d-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="33b5d-116">Пользователь, подключающийся к телефонная система прямой маршрутике</span><span class="sxs-lookup"><span data-stu-id="33b5d-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="33b5d-117">Пользователь плана звонков в США</span><span class="sxs-lookup"><span data-stu-id="33b5d-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="33b5d-118">Существуют требования, когда номер телефона должен быть связан с местоположением для экстренного ситуация.</span><span class="sxs-lookup"><span data-stu-id="33b5d-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="33b5d-119">Чтобы понять эти требования, компания Contoso просмотрела отзывы о планах [звонков.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="33b5d-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="33b5d-120">На основе этих требований компания Contoso решила связать расположение с номером телефона, когда номер назначен пользователю в США.</span><span class="sxs-lookup"><span data-stu-id="33b5d-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="33b5d-121">Пользователь плана звонков за пределами США</span><span class="sxs-lookup"><span data-stu-id="33b5d-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="33b5d-122">Чтобы понять, когда номер телефона должен быть связан с местоположением для экстренного вызова, компания Contoso просмотрела статью Обзоры [планов звонков.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="33b5d-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="33b5d-123">С учетом требований Компания Contoso решила следующее:</span><span class="sxs-lookup"><span data-stu-id="33b5d-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="33b5d-124">Contoso связывает расположение с номером телефона, когда номер назначен пользователю в Канаде.</span><span class="sxs-lookup"><span data-stu-id="33b5d-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="33b5d-125">Contoso назначает местоположение для экстренного ситуация, когда номер телефона приобретается у компании Office 365 или при перенаправлении номера от другого поставщика услуг или оператора связи.</span><span class="sxs-lookup"><span data-stu-id="33b5d-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="33b5d-126">Пользователь, подключающийся к телефонная система прямой маршрутии</span><span class="sxs-lookup"><span data-stu-id="33b5d-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="33b5d-127">Чтобы спланировать экстренную маршрутику для этого случая использования, в Contoso рассмотрены вопросы [прямой маршрутии.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="33b5d-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="33b5d-128">Так как пользователи прямой маршрутизов не получают экстренные вызовы так же, как пользователи плана звонков, Contoso должен был решить, как предоставлять экстренные вызовы.</span><span class="sxs-lookup"><span data-stu-id="33b5d-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="33b5d-129">Прямая маршрутная маршрутия может быть подключена к поставщику услуг экстренных маршрутов .</span><span class="sxs-lookup"><span data-stu-id="33b5d-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="33b5d-130">Прямая маршрутия также может иметь код SBC, включающий идентификационный номер местоположения для экстренного местоположения (ELIN).</span><span class="sxs-lookup"><span data-stu-id="33b5d-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="33b5d-131">Вопросы поставщика услуг экстренных маршрутов (ERSP)</span><span class="sxs-lookup"><span data-stu-id="33b5d-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="33b5d-132">Поставщики услуг экстренных маршрутов (ERSP) могут автоматически маршрутизовать экстренные вызовы в зависимости от расположения вызываемого.</span><span class="sxs-lookup"><span data-stu-id="33b5d-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="33b5d-133">Если поставщик услуг экстренных маршрутов интегрирован в развертывание Direct Routing, экстренные вызовы с динамически приобретенным местоположением автоматически перенаправляются в точку ответа на общедоступный доступ (PSAP), обслуживающий это расположение.</span><span class="sxs-lookup"><span data-stu-id="33b5d-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="33b5d-134">Экстренные вызовы без динамического расположения сначала по экрану определяют текущее расположение пользователя, прежде чем подключаться к соответствующему диспетчеру на основе обновленного расположения.</span><span class="sxs-lookup"><span data-stu-id="33b5d-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="33b5d-135">Аспекты ELIN</span><span class="sxs-lookup"><span data-stu-id="33b5d-135">ELIN considerations</span></span>

<span data-ttu-id="33b5d-136">Если приложение ELIN SBC интегрировано в развертывание Direct Routing, необходимо предпринять дополнительные действия по настройке, чтобы связать адреса для экстренного обращения с телефонными номерами.</span><span class="sxs-lookup"><span data-stu-id="33b5d-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="33b5d-137">Компания Contoso решила использовать контроллеры границ сеанса, включающие приложения ELIN для идентификации местоположения в экстренных службах.</span><span class="sxs-lookup"><span data-stu-id="33b5d-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="33b5d-138">Уведомление службы безопасности</span><span class="sxs-lookup"><span data-stu-id="33b5d-138">Security desk notification</span></span>

<span data-ttu-id="33b5d-139">Возможность уведомления службы безопасности при размещении экстренных вызовов доступна как для планов звонков Майкрософт, так и для телефонная система прямой маршрутики.</span><span class="sxs-lookup"><span data-stu-id="33b5d-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="33b5d-140">Компания Contoso просмотрела сведения в уведомлении службы безопасности, чтобы определить, следует ли настроить эту настройку в их офисах</span><span class="sxs-lookup"><span data-stu-id="33b5d-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="33b5d-141">Contoso решил использовать уведомление службы безопасности.</span><span class="sxs-lookup"><span data-stu-id="33b5d-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="33b5d-142">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="33b5d-142">Configuration</span></span> 

<span data-ttu-id="33b5d-143">Contoso: настройка [](configure-dynamic-emergency-calling.md) динамических экстренных вызовов:</span><span class="sxs-lookup"><span data-stu-id="33b5d-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="33b5d-144">Назначение адресов для экстренного обращения</span><span class="sxs-lookup"><span data-stu-id="33b5d-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="33b5d-145">Настройка параметров сети</span><span class="sxs-lookup"><span data-stu-id="33b5d-145">Configure network settings</span></span> 

- <span data-ttu-id="33b5d-146">Настройка службы сведений о расположении</span><span class="sxs-lookup"><span data-stu-id="33b5d-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="33b5d-147">Настройка политик для экстренного срочная ситуация</span><span class="sxs-lookup"><span data-stu-id="33b5d-147">Configure emergency policies</span></span> 

- <span data-ttu-id="33b5d-148">Включить пользователей и сайты</span><span class="sxs-lookup"><span data-stu-id="33b5d-148">Enable users and sites</span></span> 

- <span data-ttu-id="33b5d-149">Проверка экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="33b5d-149">Test emergency calling</span></span> 

<span data-ttu-id="33b5d-150">После настройки динамических экстренных вызовов Contoso необходимо назначить расположение соответствующему пользователю.</span><span class="sxs-lookup"><span data-stu-id="33b5d-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="33b5d-151">Чтобы добавить, изменить или удалить местоположение для экстренного устранения экстренных служб для организации, Contoso вы можете добавить, изменить или удалить местоположение для экстренного [устранения.](add-change-remove-emergency-location-organization.md)</span><span class="sxs-lookup"><span data-stu-id="33b5d-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="33b5d-152">Чтобы создать места для зданий, этажей и офисов, Компания Contoso, выполнив действия, которые можно найти в области Добавление, изменение и удаление места для экстренного [размещения.](add-change-remove-emergency-place-organization.md)</span><span class="sxs-lookup"><span data-stu-id="33b5d-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="33b5d-153">Чтобы назначить местоположение для экстренного ситуация, Компания Contoso, как было поручить или изменить местоположение для экстренного экстренного ситуация для пользователя, придерживалась [действий,](assign-change-emergency-location-user.md)принятых в этой области.</span><span class="sxs-lookup"><span data-stu-id="33b5d-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 