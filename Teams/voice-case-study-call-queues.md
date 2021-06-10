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
ms.openlocfilehash: 0cb8029a8f4e979a76afe069ee9b22e7be897913
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121297"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="f0b5e-103">Пример работы с Contoso: автоотводники и очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="f0b5e-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="f0b5e-104">Компания Contoso знакома с автоотводами и очередями вызовов из локальной Skype для бизнеса развертывания.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="f0b5e-105">Чтобы понять, как настроить облачные автозаполнение и очереди вызовов, они просмотрели планирование для автозаполнение Teams и очередей [вызовов.](plan-auto-attendant-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="f0b5e-105">To understand how to set up Cloud auto attendants and call queues, they reviewed [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md).</span></span>

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="f0b5e-106">Требования в зависимости от типа сайта</span><span class="sxs-lookup"><span data-stu-id="f0b5e-106">Requirements depending on site type</span></span>

<span data-ttu-id="f0b5e-107">В зависимости от типа сайта у Contoso были следующие потребности:</span><span class="sxs-lookup"><span data-stu-id="f0b5e-107">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="f0b5e-108">Тип сайта A. Традиционные устаревшие системы телефонии</span><span class="sxs-lookup"><span data-stu-id="f0b5e-108">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="f0b5e-109">Тип сайта A требуется для сохраняемого номера телефона, связанного с регистратором, с номером для автосохранеников.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-109">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="f0b5e-110">В ключевых отделах для каждого из этих сайтов должны быть собственные очереди вызовов, которые будут маршрутизовы для участников группы.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-110">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="f0b5e-111">В планах звонков использовалось несколько сайтов телефонная система маршрутизов и телефонная система с планами звонков.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-111">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="f0b5e-112">Тип сайта B: Skype для бизнеса Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="f0b5e-112">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="f0b5e-113">В типе Б были существующие автозаводцы и очереди вызовов, которые необходимо было перенести в Teams.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-113">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="f0b5e-114">Contoso требовалось сохранить телефонные номера, связанные с автоотессылами.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-114">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="f0b5e-115">Contoso переместил большинство этих сайтов на телефонная система с помощью планов звонков.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-115">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="f0b5e-116">Однако в некоторых расположениях, где планы звонков были недоступны, Contoso переместил эти сайты в конфигурацию Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-116">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="f0b5e-117">Тип сайта C: Skype для бизнеса Корпоративная голосовая связь & традиционной телефонной системы</span><span class="sxs-lookup"><span data-stu-id="f0b5e-117">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="f0b5e-118">В типе C сайта были существующие автозаводцы, которые находились в традиционной устаревшей телефонной системе.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-118">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="f0b5e-119">Решения и конфигурации для этого сайта были те же, что и для типа сайта A.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-119">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="f0b5e-120">Для всех типов сайтов Contoso задал следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="f0b5e-120">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="f0b5e-121">Вопрос. Будут ли мы использовать новые или существующие числа?</span><span class="sxs-lookup"><span data-stu-id="f0b5e-121">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="f0b5e-122">А. Компания Contoso решила использовать существующие телефонные номера, которые будут назначены учетной записи службы для автозавода.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-122">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="f0b5e-123">Вопрос. Когда автоответ может принимать входящие звонки?</span><span class="sxs-lookup"><span data-stu-id="f0b5e-123">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="f0b5e-124">Ответ. Компания Contoso решила настроить часы работы и перенаправлять звонки в нее автоответщику.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-124">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="f0b5e-125">Вопрос. Как звонки будут перенаться участникам в очереди звонков: помощнику, серийному или округлному маршруту?</span><span class="sxs-lookup"><span data-stu-id="f0b5e-125">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="f0b5e-126">А. Contoso решил использовать маршрутику Attendant,</span><span class="sxs-lookup"><span data-stu-id="f0b5e-126">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="f0b5e-127">Вопрос. Как определить, когда следует или не следует звонить пользователю?</span><span class="sxs-lookup"><span data-stu-id="f0b5e-127">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="f0b5e-128">А. Компания Contoso решила использовать параметры обработки звонка, чтобы определить, доступен ли агент: маршруты на основе присутствия.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-128">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="f0b5e-129">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="f0b5e-129">Configuration</span></span>

<span data-ttu-id="f0b5e-130">Ниже описаны действия по настройкам автозавода и очереди вызовов, описанные в области Управление учетными [записями ресурсов.](manage-resource-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="f0b5e-130">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="f0b5e-131">Получите номер службы.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-131">Obtain a service number.</span></span> 

2. <span data-ttu-id="f0b5e-132">Получите бесплатную телефонная система — лицензию виртуального пользователя или платную телефонная система для использования с учетной записью ресурса или телефонная система лицензией.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-132">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="f0b5e-133">Создайте учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-133">Create the resource account.</span></span> <span data-ttu-id="f0b5e-134">Для использования связанной учетной записи ресурса требуется автоотекатарь или очередь вызовов.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-134">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="f0b5e-135">Назначьте учетной телефонная система или лицензию телефонная система — виртуальный пользователь.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-135">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="f0b5e-136">Дополнительные сведения см. в [Microsoft 365 телефонная система — лицензия виртуального пользователя.](./teams-add-on-licensing/virtual-user.md)</span><span class="sxs-lookup"><span data-stu-id="f0b5e-136">For more information, see [Microsoft 365 Phone System – Virtual User license](./teams-add-on-licensing/virtual-user.md).</span></span>

5. <span data-ttu-id="f0b5e-137">Назначьте номер телефона службы учетной записи ресурса, назначенной лицензиям.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-137">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="f0b5e-138">Создание очереди телефонная система вызовов или автозавода</span><span class="sxs-lookup"><span data-stu-id="f0b5e-138">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="f0b5e-139">Связывать учетную запись ресурса с очередью вызовов или автоотехом.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-139">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="f0b5e-140">Сайты с телефонная система с прямой маршрутией</span><span class="sxs-lookup"><span data-stu-id="f0b5e-140">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="f0b5e-141">Contoso пришлось настроить номер телефона, предоставленный местным оператором связи в качестве номера службы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-141">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="f0b5e-142">Чтобы настроить номер телефона, доступный в прямой маршрутике, Contoso следует инструкциям из области Управление учетной записью [ресурсов.](manage-resource-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="f0b5e-142">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="f0b5e-143">Так Office 365 не знают о номерах телефонов, используемых в локальной сети, contoso использовал PowerShell для завершения настройки.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-143">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="f0b5e-144">Чтобы настроить облачный автозаводщик, Contoso следовала шагам, описанным в окте Настройка автозаметки в [облаке.](create-a-phone-system-auto-attendant.md)</span><span class="sxs-lookup"><span data-stu-id="f0b5e-144">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="f0b5e-145">Чтобы настроить очередь вызовов в облаке, Contoso, как описано в описании в окте Создание очереди вызовов [в облаке.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="f0b5e-145">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="f0b5e-146">Сайты с телефонная система с планом звонков</span><span class="sxs-lookup"><span data-stu-id="f0b5e-146">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="f0b5e-147">Contoso пришлось портить номер телефона, который использовался для Skype для бизнеса Корпоративная голосовая связь автоотетаря, в Телефонная система Office 365.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-147">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="f0b5e-148">Это позволило на назначении того же номера в качестве номера службы для использования в качестве автоотехника.</span><span class="sxs-lookup"><span data-stu-id="f0b5e-148">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="f0b5e-149">Чтобы перенести номер телефона, Компания Contoso, вы следовать инструкциям в области Перенос номеров телефонов в Teams а также получить дополнительные инструкции в области Управление номерами телефонов [для организации.](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) [](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f0b5e-149">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) and obtained additional guidance at [Manage phone numbers for your organization](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

- <span data-ttu-id="f0b5e-150">Чтобы настроить облачный автозаводщик, Компания Contoso следовала шагам, описанным в окте Настройка автозаметки в [облаке.](create-a-phone-system-auto-attendant.md)</span><span class="sxs-lookup"><span data-stu-id="f0b5e-150">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="f0b5e-151">Чтобы настроить очередь вызовов в облаке, Contoso, как описано в описании в окте Создание очереди вызовов [в облаке.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="f0b5e-151">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

