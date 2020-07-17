---
title: Исследование успеха в голосовых сообщениях в Teams contoso
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
description: Исследование вариантов голосовой связи в среде Teams для международной Организации
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786103"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="b8dee-103">Исследование успеха Contoso: вызов экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="b8dee-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="b8dee-104">Сведения о доступности и терминологии, связанные с экстренным звонком &mdash; , местом, местом хранения для экстренного реагирования и зарегистрированным адресом &mdash; компании Contoso проверено [Управление вызовом экстренной](what-are-emergency-locations-addresses-and-call-routing.md) помощи, [планирование и Настройка динамического вызова экстренной](configure-dynamic-emergency-calling.md)помощи.</span><span class="sxs-lookup"><span data-stu-id="b8dee-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="b8dee-105">В Office 365 пользователь плана звонков автоматически включается для вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="b8dee-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="b8dee-106">Но только пользователи плана звонков в США могут использовать динамические места для маршрутизации экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="b8dee-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="b8dee-107">Для прямой маршрутизации компания Contoso узнали, что требуется дополнительная настройка маршрутизации для экстренных вызовов и, возможно, для подключения партнеров.</span><span class="sxs-lookup"><span data-stu-id="b8dee-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="b8dee-108">Администратор должен настроить подключение к поставщику услуг маршрутизации экстренной помощи (ERSP) (США) или настроить контроллер границ сеанса (SBC) для приложения идентификационного номера расположения экстренной помощи (ELIN).</span><span class="sxs-lookup"><span data-stu-id="b8dee-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="b8dee-109">Компания Contoso имеет офисы в США и за пределами США.</span><span class="sxs-lookup"><span data-stu-id="b8dee-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="b8dee-110">В США в плане абонентов Contoso пользователи могут использовать динамические места для маршрутизации экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="b8dee-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="b8dee-111">За пределами Соединенных Штатов компания Contoso имеет некоторые сайты, которые используют планы звонков и некоторые сайты, подключенные к телефонной системе с помощью прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="b8dee-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="b8dee-112">Варианты использования для экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="b8dee-112">Emergency calling use cases</span></span>

<span data-ttu-id="b8dee-113">После того как вы решите, как Contoso подключится к телефонной системе, компания Contoso определила следующие варианты использования для экстренных вызовов:</span><span class="sxs-lookup"><span data-stu-id="b8dee-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="b8dee-114">Абонентский план в США</span><span class="sxs-lookup"><span data-stu-id="b8dee-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="b8dee-115">Пользователь планов звонков за пределами США</span><span class="sxs-lookup"><span data-stu-id="b8dee-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="b8dee-116">Пользователь, который подключается к телефонной системе через прямую маршрутизацию</span><span class="sxs-lookup"><span data-stu-id="b8dee-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="b8dee-117">Абонентский план в США</span><span class="sxs-lookup"><span data-stu-id="b8dee-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="b8dee-118">Существуют требования, которые необходимо выполнить, когда нужно связать номер телефона с местом для экстренного реагирования.</span><span class="sxs-lookup"><span data-stu-id="b8dee-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="b8dee-119">Сведения о требованиях, предъявляемых компанией Contoso, рассмотрены в разделе [планы звонков](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="b8dee-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="b8dee-120">Согласно этим требованиям компания Contoso решила сопоставить место с номером телефона, когда номер назначен пользователю в США.</span><span class="sxs-lookup"><span data-stu-id="b8dee-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="b8dee-121">Пользователь планов звонков за пределами США</span><span class="sxs-lookup"><span data-stu-id="b8dee-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="b8dee-122">Чтобы узнать, когда нужно связать номер телефона с местом для экстренного реагирования, ознакомьтесь с [Размышленными планами](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans), рассмотренными компанией Contoso.</span><span class="sxs-lookup"><span data-stu-id="b8dee-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="b8dee-123">Согласно требованиям компания Contoso решила следующее:</span><span class="sxs-lookup"><span data-stu-id="b8dee-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="b8dee-124">Компания Contoso свяжет место с номером телефона, когда номер назначен пользователю в Канаде.</span><span class="sxs-lookup"><span data-stu-id="b8dee-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="b8dee-125">Компания Contoso назначает место для экстренного реагирования при получении номера телефона из Office 365 или при передаче номера от другого поставщика услуг или оператора.</span><span class="sxs-lookup"><span data-stu-id="b8dee-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="b8dee-126">Пользователь, который подключается к телефонной системе через прямую маршрутизацию</span><span class="sxs-lookup"><span data-stu-id="b8dee-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="b8dee-127">Для планирования аварийной маршрутизации для этого случая использования компания Contoso проверила [рекомендации по прямой маршрутизации](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="b8dee-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="b8dee-128">Поскольку прямые пользователи маршрутизации не получают возможность вызова экстренной помощи таким же образом, как и пользователи плана звонков, компания Contoso приводила к тому, как обеспечить возможность вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="b8dee-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="b8dee-129">Прямая маршрутизация может быть подключена к поставщику услуг маршрутизации экстренной помощи (ERSP).</span><span class="sxs-lookup"><span data-stu-id="b8dee-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="b8dee-130">Кроме того, прямая маршрутизация может иметь SBC, включающий идентификационный номер расположения для экстренного реагирования (ELIN).</span><span class="sxs-lookup"><span data-stu-id="b8dee-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="b8dee-131">Вопросы о поставщике услуг маршрутизации экстренной помощи (ERSP)</span><span class="sxs-lookup"><span data-stu-id="b8dee-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="b8dee-132">Поставщики услуг маршрутизации экстренной помощи (ERSPs) могут автоматически перенаправлять экстренные вызовы в зависимости от расположения вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="b8dee-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="b8dee-133">Если поставщик услуг маршрутизации экстренной помощи интегрирован в прямое развертывание по маршрутизации, экстренные вызовы с динамически приобретенным расположением будут автоматически перенаправлены в точку ответа для общедоступной защиты (PSAP), обслуживающей это расположение.</span><span class="sxs-lookup"><span data-stu-id="b8dee-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="b8dee-134">Вызов экстренной помощи без динамически приобретенного местоположения — первый экран, чтобы определить текущее расположение пользователя, прежде чем присоединиться к соответствующему центру отправки, основываясь на обновленном расположении.</span><span class="sxs-lookup"><span data-stu-id="b8dee-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="b8dee-135">Вопросы ELIN</span><span class="sxs-lookup"><span data-stu-id="b8dee-135">ELIN considerations</span></span>

<span data-ttu-id="b8dee-136">Если приложение SBC ELIN интегрировано в прямое развертывание, необходимо выполнить дополнительные действия по настройке, чтобы связать адреса экстренного реагирования с телефонными номерами.</span><span class="sxs-lookup"><span data-stu-id="b8dee-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="b8dee-137">Компания Contoso решила использовать контроллеры границ сеансов, в том числе приложения с идентификационным номером расположения для экстренного реагирования (ELIN).</span><span class="sxs-lookup"><span data-stu-id="b8dee-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="b8dee-138">Уведомление на рабочем месте</span><span class="sxs-lookup"><span data-stu-id="b8dee-138">Security desk notification</span></span>

<span data-ttu-id="b8dee-139">Возможность уведомления службы безопасности о размещении экстренного звонка доступна как для планов звонков, так и для прямой маршрутизации телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="b8dee-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="b8dee-140">Компания Contoso проверила сведения в уведомлении о безопасности, чтобы определить, следует ли настроить его на доступ к своим офисам</span><span class="sxs-lookup"><span data-stu-id="b8dee-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="b8dee-141">Компания Contoso решила использовать уведомление на службу безопасности.</span><span class="sxs-lookup"><span data-stu-id="b8dee-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="b8dee-142">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="b8dee-142">Configuration</span></span> 

<span data-ttu-id="b8dee-143">Компания Contoso происпользовала шаги, описанные в разделе [Настройка динамического вызова экстренной](configure-dynamic-emergency-calling.md) помощи:</span><span class="sxs-lookup"><span data-stu-id="b8dee-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="b8dee-144">Назначение адресов для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="b8dee-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="b8dee-145">Настройка параметров сети</span><span class="sxs-lookup"><span data-stu-id="b8dee-145">Configure network settings</span></span> 

- <span data-ttu-id="b8dee-146">Настройка службы сведений о расположении</span><span class="sxs-lookup"><span data-stu-id="b8dee-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="b8dee-147">Настройка политик экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="b8dee-147">Configure emergency policies</span></span> 

- <span data-ttu-id="b8dee-148">Включение пользователей и сайтов</span><span class="sxs-lookup"><span data-stu-id="b8dee-148">Enable users and sites</span></span> 

- <span data-ttu-id="b8dee-149">Проверка вызова экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="b8dee-149">Test emergency calling</span></span> 

<span data-ttu-id="b8dee-150">После того как вы настроили динамическую функцию вызова экстренной помощи, Contoso требуется назначить расположение для нужного пользователя.</span><span class="sxs-lookup"><span data-stu-id="b8dee-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="b8dee-151">Чтобы добавить, изменить или удалить расположение для экстренного реагирования для вашей организации, компания Contoso продемонстрирует инструкции в статье [Добавление, изменение и удаление местоположения для экстренного реагирования для вашей организации](add-change-remove-emergency-location-organization.md) .</span><span class="sxs-lookup"><span data-stu-id="b8dee-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="b8dee-152">Чтобы создать места для зданий, этажей и офисов, компания Contoso предместит инструкции в статье [Добавление, изменение и удаление Места для экстренного](add-change-remove-emergency-place-organization.md) реагирования.</span><span class="sxs-lookup"><span data-stu-id="b8dee-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="b8dee-153">Чтобы назначить место для экстренного реагирования, компания Contoso проследует шаги в разделе [назначение или изменение расположения для экстренного реагирования для пользователя](assign-change-emergency-location-user.md).</span><span class="sxs-lookup"><span data-stu-id="b8dee-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 