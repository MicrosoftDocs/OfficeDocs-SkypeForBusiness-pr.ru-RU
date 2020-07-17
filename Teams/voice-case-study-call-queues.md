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
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786095"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="b3259-103">Исследование успеха Contoso: автосекретарей и очереди звонков</span><span class="sxs-lookup"><span data-stu-id="b3259-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="b3259-104">Компания Contoso была знакома с автосекретарем и очередью звонков из локального развертывания Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b3259-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="b3259-105">Сведения о том, как настраивать автоматические ассистенты в облаке, изменялись ли [облачные](what-are-phone-system-auto-attendants.md) автосекретарьы? и [пример для малого бизнеса — руководство по настройке автосекретаря](tutorial-org-aa.yml).</span><span class="sxs-lookup"><span data-stu-id="b3259-105">To understand how to set up Cloud auto attendants, they reviewed [What are Cloud auto attendants?](what-are-phone-system-auto-attendants.md) and [Small business  example - Set up auto attendant tutorial](tutorial-org-aa.yml).</span></span> <span data-ttu-id="b3259-106">Чтобы узнать о параметрах, доступных для настройки очередей звонков, компания Contoso смотрела [Создание очереди облачных звонков](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="b3259-106">To learn about the options available to set up call queues, Contoso reviewed [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="b3259-107">Требования в зависимости от типа сайта</span><span class="sxs-lookup"><span data-stu-id="b3259-107">Requirements depending on site type</span></span>

<span data-ttu-id="b3259-108">В зависимости от типа сайта компания Contoso имела следующие требования:</span><span class="sxs-lookup"><span data-stu-id="b3259-108">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="b3259-109">Тип сайта а: традиционные стандартные системы телефонии</span><span class="sxs-lookup"><span data-stu-id="b3259-109">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="b3259-110">Тип сайта, необходимый для сохранения того же номера телефона, который связан с receptionist, в качестве номера для своих автосекретарей.</span><span class="sxs-lookup"><span data-stu-id="b3259-110">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="b3259-111">У подотделов для каждого из этих сайтов будут свои собственные очереди звонков, которые будут маршрутизироваться к участникам команды.</span><span class="sxs-lookup"><span data-stu-id="b3259-111">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="b3259-112">На веб-сайте, на котором установлена прямая маршрутизация и телефонная система, существовало множество сайтов, которые используют планы звонков.</span><span class="sxs-lookup"><span data-stu-id="b3259-112">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="b3259-113">Тип сайта B: голосовая связь Skype для бизнеса (корпоративный)</span><span class="sxs-lookup"><span data-stu-id="b3259-113">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="b3259-114">У типа сайта B есть существующие автоматические ассистенты и очереди звонков, необходимые для миграции в Teams.</span><span class="sxs-lookup"><span data-stu-id="b3259-114">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="b3259-115">Компании Contoso требуется сохранить номера телефонов, связанные с автоматическими ассистентами.</span><span class="sxs-lookup"><span data-stu-id="b3259-115">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="b3259-116">Компания Contoso переместила большую часть этих сайтов в телефонную систему с помощью планов звонков.</span><span class="sxs-lookup"><span data-stu-id="b3259-116">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="b3259-117">Однако в нескольких местах, в которых планы звонков недоступны, компания Contoso переместила эти сайты в конфигурацию Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="b3259-117">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="b3259-118">Тип сайта C: Skype для бизнеса Enterprise & традиционная устаревшая система телефонной связи</span><span class="sxs-lookup"><span data-stu-id="b3259-118">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="b3259-119">В типе сайта C есть автоматические ассистенты, которые находятся в традиционной старой системе телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="b3259-119">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="b3259-120">Решения и конфигурации для этого сайта совпадают с типом сайта "а".</span><span class="sxs-lookup"><span data-stu-id="b3259-120">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="b3259-121">Для всех типов сайтов компания Contoso запросит указанные ниже вопросы.</span><span class="sxs-lookup"><span data-stu-id="b3259-121">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="b3259-122">Вопрос: будут ли мы использовать новые или существующие номера?</span><span class="sxs-lookup"><span data-stu-id="b3259-122">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="b3259-123">A: компания Contoso решила использовать существующие номера телефонов для присвоения учетной записи службы для автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="b3259-123">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="b3259-124">Вопрос: когда автоматически будет доступен автосекретарь для приема входящих звонков?</span><span class="sxs-lookup"><span data-stu-id="b3259-124">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="b3259-125">A: компания Contoso решила установить рабочие часы и получала звонки после того, как рабочие часы перенаправлялись на автосекретарь "после времени".</span><span class="sxs-lookup"><span data-stu-id="b3259-125">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="b3259-126">Вопрос: как будут перенаправляться звонки участникам в очереди звонков: для участников, последовательного или циклического перенаправления?</span><span class="sxs-lookup"><span data-stu-id="b3259-126">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="b3259-127">A: компания Contoso решила использовать маршрут участника по подведению,</span><span class="sxs-lookup"><span data-stu-id="b3259-127">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="b3259-128">Вопрос: как определить, когда пользователь должен или должен не получать Звонок?</span><span class="sxs-lookup"><span data-stu-id="b3259-128">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="b3259-129">A: компания Contoso решила использовать параметры обработки звонков, чтобы определить, доступен ли агент. Маршрутизация на основе присутствия.</span><span class="sxs-lookup"><span data-stu-id="b3259-129">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="b3259-130">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="b3259-130">Configuration</span></span>

<span data-ttu-id="b3259-131">Для настройки автосекретаря и очереди звонков необходимо выполнить указанные ниже действия, описанные в разделе [Управление учетными записями ресурсов](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="b3259-131">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="b3259-132">Получить номер Услуги.</span><span class="sxs-lookup"><span data-stu-id="b3259-132">Obtain a service number.</span></span> 

2. <span data-ttu-id="b3259-133">Получите бесплатную лицензию на виртуальную или платную телефонную систему для использования с учетной записью ресурса или лицензией на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="b3259-133">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="b3259-134">Создайте учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="b3259-134">Create the resource account.</span></span> <span data-ttu-id="b3259-135">Для связи между автосекретарем и очередью звонков требуется соответствующая учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="b3259-135">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="b3259-136">Назначьте телефонную систему или лицензию виртуальных пользователей для учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="b3259-136">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="b3259-137">Дополнительные сведения можно найти в разделе [Microsoft 365 Phone System — лицензия виртуальных пользователей](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span><span class="sxs-lookup"><span data-stu-id="b3259-137">For more information, see [Microsoft 365 Phone System – Virtual User license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span></span>

5. <span data-ttu-id="b3259-138">Назначьте номер телефона для учетной записи ресурса, которой вы назначили лицензии.</span><span class="sxs-lookup"><span data-stu-id="b3259-138">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="b3259-139">Создание очереди звонков телефонной системы или автосекретаря</span><span class="sxs-lookup"><span data-stu-id="b3259-139">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="b3259-140">Свяжите учетную запись ресурса с очередью звонков или автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="b3259-140">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="b3259-141">Сайты с телефонной системой с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="b3259-141">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="b3259-142">Компании Contoso пришлось настроить телефонный номер, предоставленный местным перевозчиком в качестве номера службы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="b3259-142">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="b3259-143">Чтобы настроить телефонный номер, который будет доступен через прямую маршрутизацию, компания Contoso пройдет инструкции, расположенные в разделе [Управление учетными записями ресурсов](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="b3259-143">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="b3259-144">Поскольку в Office 365 не сознаются локальные номера телефонов, компания Contoso использовала PowerShell для завершения настройки.</span><span class="sxs-lookup"><span data-stu-id="b3259-144">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="b3259-145">Чтобы настроить автосекретарь облачной функции, компания Contoso предвыполнила шаги, описанные в разделе [Настройка автоматического секретаря облачных](create-a-phone-system-auto-attendant.md)параметров.</span><span class="sxs-lookup"><span data-stu-id="b3259-145">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="b3259-146">Чтобы настроить очередь звонков в облаке, компания Contoso представит шаги, описанные в разделе [Создание очереди облачных звонков](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="b3259-146">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="b3259-147">Сайты с телефонной системой с тарифным планом</span><span class="sxs-lookup"><span data-stu-id="b3259-147">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="b3259-148">Компании Contoso пришлось перенести номер телефона, который использовался для автоматической голосовой Подсекретаря Skype для бизнеса, в телефонную систему Office 365.</span><span class="sxs-lookup"><span data-stu-id="b3259-148">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="b3259-149">Это позволило тому же номеру назначаться в качестве номера службы для использования в качестве автоматического ассистента.</span><span class="sxs-lookup"><span data-stu-id="b3259-149">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="b3259-150">Чтобы перенести номер телефона, компания Contoso просопровождает инструкции по [переносу телефонных номеров в Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) и получила дополнительные рекомендации по [управлению номерами телефонов для вашей организации](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="b3259-150">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) and obtained additional guidance at [Manage phone numbers for your organization](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span></span>

- <span data-ttu-id="b3259-151">Для настройки автосекретаря облачных задач компания Contoso предварят шаги, описанные в разделе [Настройка автоматического секретаря облачных облаков](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="b3259-151">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="b3259-152">Чтобы настроить очередь звонков в облаке, компания Contoso представит шаги, описанные в разделе [Создание очереди облачных звонков](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="b3259-152">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

 