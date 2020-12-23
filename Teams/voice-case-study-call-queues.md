---
title: Пример дела с голосовой почтой Contoso в Teams
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
description: Пример голосовой работы Teams для многоязычной корпорации
appliesto:
- Microsoft Teams
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786095"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="6d3e6-103">Пример: автоотетары и очереди вызовов в Contoso</span><span class="sxs-lookup"><span data-stu-id="6d3e6-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="6d3e6-104">Компания Contoso знакома с автоотетарями и очередями звонков из локального развертывания Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="6d3e6-105">Чтобы понять, как настроить автозаполнение, [](what-are-phone-system-auto-attendants.md) они проанализировали, что такое автозаполнение, и пример для малого бизнеса— настройка учебника автозаполнение. [](tutorial-org-aa.yml)</span><span class="sxs-lookup"><span data-stu-id="6d3e6-105">To understand how to set up Cloud auto attendants, they reviewed [What are Cloud auto attendants?](what-are-phone-system-auto-attendants.md) and [Small business  example - Set up auto attendant tutorial](tutorial-org-aa.yml).</span></span> <span data-ttu-id="6d3e6-106">Чтобы узнать о параметрах, доступных для настройки очередей параметров, Contoso просмотрел отзыв о создании [очереди параметров в облаке.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="6d3e6-106">To learn about the options available to set up call queues, Contoso reviewed [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="6d3e6-107">Требования в зависимости от типа сайта</span><span class="sxs-lookup"><span data-stu-id="6d3e6-107">Requirements depending on site type</span></span>

<span data-ttu-id="6d3e6-108">В зависимости от типа сайта у Contoso были следующие потребности:</span><span class="sxs-lookup"><span data-stu-id="6d3e6-108">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="6d3e6-109">Тип сайта A. Традиционные устаревшие системы телефонии</span><span class="sxs-lookup"><span data-stu-id="6d3e6-109">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="6d3e6-110">Тип сайта A требуется для сохраняемого номера телефона, связанного с регистратором, с номером для автозавода.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-110">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="6d3e6-111">Ключевые отделы для каждого из этих сайтов будут иметь собственные очереди вызовов, которые будут маршрутизовы для участников группы.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-111">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="6d3e6-112">На всех сайтах использовались телефонная система с прямой маршрутизов и телефонная система со планами звонков.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-112">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="6d3e6-113">Тип сайта B. Skype для Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="6d3e6-113">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="6d3e6-114">В типе сайта B были существующие автоотетары и очереди вызовов, необходимые для миграции в Teams.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-114">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="6d3e6-115">Contoso требовался для сохраняемого номера телефонов, связанных с автозаводом.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-115">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="6d3e6-116">Компания Contoso переместила большинство этих сайтов в телефонную систему с планами звонков.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-116">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="6d3e6-117">Но в некоторых расположениях, где планы звонков были недоступны, Contoso перенесли эти сайты в конфигурацию "Прямая маршрутия".</span><span class="sxs-lookup"><span data-stu-id="6d3e6-117">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="6d3e6-118">Тип сайта C. Skype для Корпоративная голосовая связь & традиционной телефонной системы</span><span class="sxs-lookup"><span data-stu-id="6d3e6-118">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="6d3e6-119">В типе сайта C находились автоотетары, находились в традиционной устаревшей телефонной системе.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-119">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="6d3e6-120">Решения и конфигурации для этого сайта были те же, что и для типа сайта А.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-120">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="6d3e6-121">Для всех типов сайтов Contoso задавал следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="6d3e6-121">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="6d3e6-122">Вопрос. Будут ли мы использовать новые или существующие номера?</span><span class="sxs-lookup"><span data-stu-id="6d3e6-122">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="6d3e6-123">А. Компания Contoso решила использовать существующие номера телефонов, которые будут назначены учетной записи службы для автозачета.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-123">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="6d3e6-124">Вопрос. Когда автоответ будет доступен для входящих звонков?</span><span class="sxs-lookup"><span data-stu-id="6d3e6-124">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="6d3e6-125">Ответ. Компания Contoso решила настроить часы работы и перенаправлять звонки, которые перенаправляются автоответщику в нечасовом режиме.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-125">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="6d3e6-126">Вопрос. Как звонки будут перенанаться участникам очереди звонков: помощнику, последовательной или круговой маршрутике?</span><span class="sxs-lookup"><span data-stu-id="6d3e6-126">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="6d3e6-127">А. Решение Contoso использовать маршрутику Attendant,</span><span class="sxs-lookup"><span data-stu-id="6d3e6-127">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="6d3e6-128">Вопрос. Как определить, когда нужно или не следует звонить пользователю?</span><span class="sxs-lookup"><span data-stu-id="6d3e6-128">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="6d3e6-129">А. Компания Contoso решила использовать параметры обработки вызовов, чтобы определить, доступен ли агент: маршруты на основе присутствия.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-129">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="6d3e6-130">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="6d3e6-130">Configuration</span></span>

<span data-ttu-id="6d3e6-131">Ниже описаны действия по настройкам автозачета и очереди вызовов, описанные в области "Управление учетными [данными ресурсов".](manage-resource-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="6d3e6-131">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="6d3e6-132">Получите номер службы.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-132">Obtain a service number.</span></span> 

2. <span data-ttu-id="6d3e6-133">Получите бесплатную телефонную систему — лицензию виртуального пользователя или платную телефонную систему для использования с учетной записью ресурса или лицензией телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-133">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="6d3e6-134">Создайте учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-134">Create the resource account.</span></span> <span data-ttu-id="6d3e6-135">Для использования связанной учетной записи ресурса требуется автострада или очередь вызовов.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-135">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="6d3e6-136">Назначьте учетной записи ресурса телефонную систему или телефонную систему — лицензию виртуального пользователя.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-136">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="6d3e6-137">Дополнительные сведения см. в [лицензии "Телефонная система Microsoft 365 — виртуальный пользователь".](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)</span><span class="sxs-lookup"><span data-stu-id="6d3e6-137">For more information, see [Microsoft 365 Phone System – Virtual User license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span></span>

5. <span data-ttu-id="6d3e6-138">Назначьте номер телефона службы учетной записи ресурса, назначенной лицензиям.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-138">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="6d3e6-139">Создание очереди звонков в телефонной системе или автозавода</span><span class="sxs-lookup"><span data-stu-id="6d3e6-139">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="6d3e6-140">Связывать учетную запись ресурса с очередью вызовов или автозаводом.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-140">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="6d3e6-141">Сайты с телефонной системой с прямой маршрутией</span><span class="sxs-lookup"><span data-stu-id="6d3e6-141">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="6d3e6-142">Компании Contoso пришлось настроить номер телефона, предоставленный местным оператором, в качестве номера службы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-142">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="6d3e6-143">Чтобы настроить номер телефона, доступный в прямой маршрутке, Contoso следует инструкциям в области "Управление учетной записью [ресурса".](manage-resource-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="6d3e6-143">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="6d3e6-144">Так как office 365 не знает о номерах телефонов для локального использования, Contoso использовал PowerShell для завершения настройки.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-144">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="6d3e6-145">Чтобы настроить автофигуру в облаке, Компания Contoso, как описано в описании настройки автозаметки в облаке, придерживается [действий,](create-a-phone-system-auto-attendant.md)описанных в этой области.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-145">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="6d3e6-146">Чтобы настроить очередь звонка в облаке, contoso, как описано в описании очереди зов [в облаке, следовал за действиями, описанными в этой теме.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="6d3e6-146">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="6d3e6-147">Сайты с телефонной системой с планом звонков</span><span class="sxs-lookup"><span data-stu-id="6d3e6-147">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="6d3e6-148">В Contoso номер телефона, который использовался для skype для бизнеса Корпоративная голосовая связь, в телефонную систему Office 365.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-148">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="6d3e6-149">Это позволяет использовать этот номер в качестве номера службы для использования в качестве автозавода.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-149">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="6d3e6-150">Чтобы перенести номер телефона, компания Contoso, вы следовать инструкциям по переносу номеров телефонов в [Teams,](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) а также получить дополнительные рекомендации по управлению номерами телефонов [для вашей организации.](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="6d3e6-150">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) and obtained additional guidance at [Manage phone numbers for your organization](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span></span>

- <span data-ttu-id="6d3e6-151">Чтобы настроить автофигуру в облаке, Компания Contoso следовала за действиями, описанными в описании настройки автозаметки в [облаке.](create-a-phone-system-auto-attendant.md)</span><span class="sxs-lookup"><span data-stu-id="6d3e6-151">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="6d3e6-152">Чтобы настроить очередь вызовов в облаке, компания Contoso, как описано в описании этой очереди, придерживается описанных в этой [теме действий.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="6d3e6-152">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

 