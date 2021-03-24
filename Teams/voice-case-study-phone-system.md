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
ms.openlocfilehash: 995b4ddf9c07dea57c8d4de9940776d5137c2d02
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101035"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="8c362-103">Пример: телефонная система</span><span class="sxs-lookup"><span data-stu-id="8c362-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="8c362-104">В зависимости от географического расположения и других факторов у contoso были офисы, использующие следующие решения телефонии:</span><span class="sxs-lookup"><span data-stu-id="8c362-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="8c362-105">Тип сайта A: Skype для Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="8c362-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="8c362-106">Тип сайта B. Традиционные устаревшие системы телефонии</span><span class="sxs-lookup"><span data-stu-id="8c362-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="8c362-107">Тип сайта C: сочетание Skype для Корпоративная голосовая связь и традиционных телефонных систем</span><span class="sxs-lookup"><span data-stu-id="8c362-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="8c362-108">Чтобы внедрить решение Microsoft Phone System для всей организации, contoso должен был определить для каждого типа сайта, какие из следующих параметров будут использоваться с телефонной системой для подключения к телефонной сети &mdash; общего звонкового &mdash; звонков (STN):</span><span class="sxs-lookup"><span data-stu-id="8c362-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="8c362-109">Телефонная система с планом звонков</span><span class="sxs-lookup"><span data-stu-id="8c362-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="8c362-110">Телефонная система с собственным оператором ЗВОНКОВ по прямой маршрутике</span><span class="sxs-lookup"><span data-stu-id="8c362-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="8c362-111">Сочетание телефонной системы с планом звонков и телефонной системой с собственным оператором ЗВОНКОВ через прямую маршрутику</span><span class="sxs-lookup"><span data-stu-id="8c362-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="8c362-112">Чтобы определить правильное решение для своей [](/SkypeForBusiness/hybrid/msft-telephony-solutions) организации, компания Contoso использовала решения для телефонных телефонов Майкрософт и сеанс Ignite 2019 [Calling в Microsoft Teams.](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="8c362-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="8c362-113">Тип сайта A: Skype для Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="8c362-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="8c362-114">Contoso Skype для Корпоративная голосовая связь была настроена как центр и беседа.</span><span class="sxs-lookup"><span data-stu-id="8c362-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="8c362-115">В регионе был централизованный шлюз ННР, который обеспечивает подключение к STN для пользователей Skype для Корпоративная голосовая связь в стране.</span><span class="sxs-lookup"><span data-stu-id="8c362-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="8c362-116">Часто у таких спутниковых офисов не было собственного интернет-регрессии.</span><span class="sxs-lookup"><span data-stu-id="8c362-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="8c362-117">Числа этих пользователей, проживающих на телефоне SIP, подключаемом к существующей SBC.</span><span class="sxs-lookup"><span data-stu-id="8c362-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="8c362-118">Чтобы определить, сертифицирована ли уже развернутая SBC для прямой маршрутирования и обхода мультимедиа, Contoso проверил список граничных контроллеров сеанса, сертифицированных для прямой [маршрутирования.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="8c362-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="8c362-119">При наборе номера пользователю в устаревшей системе телефонии нужно было набрать номер с помощью расширения, даже если у пользователя есть клиент Skype для бизнеса, доступный для одноранговых звонков.</span><span class="sxs-lookup"><span data-stu-id="8c362-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="8c362-120">Решение компании Contoso основано на следующих вопросах:</span><span class="sxs-lookup"><span data-stu-id="8c362-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="8c362-121">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="8c362-121">Q.</span></span> <span data-ttu-id="8c362-122">Нужно ли сохранять функции, предоставляемые в локальном развертывании?</span><span class="sxs-lookup"><span data-stu-id="8c362-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="8c362-123">A.</span><span class="sxs-lookup"><span data-stu-id="8c362-123">A.</span></span> <span data-ttu-id="8c362-124">Нет</span><span class="sxs-lookup"><span data-stu-id="8c362-124">No</span></span> 

- <span data-ttu-id="8c362-125">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="8c362-125">Q.</span></span> <span data-ttu-id="8c362-126">Требуется ли пересекаться со сторонними системами УАКС и другим телефонным оборудованием?</span><span class="sxs-lookup"><span data-stu-id="8c362-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="8c362-127">A.</span><span class="sxs-lookup"><span data-stu-id="8c362-127">A.</span></span> <span data-ttu-id="8c362-128">Нет</span><span class="sxs-lookup"><span data-stu-id="8c362-128">No</span></span> 

- <span data-ttu-id="8c362-129">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="8c362-129">Q.</span></span> <span data-ttu-id="8c362-130">Нужно ли сохранить текущий сторонний оператор связи?</span><span class="sxs-lookup"><span data-stu-id="8c362-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="8c362-131">A. Да (регулируемые страны) и Нет</span><span class="sxs-lookup"><span data-stu-id="8c362-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="8c362-132">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="8c362-132">Q.</span></span> <span data-ttu-id="8c362-133">Нужно ли развернуть рентабельность инвестиций на SBCs?</span><span class="sxs-lookup"><span data-stu-id="8c362-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="8c362-134">A. Да и нет</span><span class="sxs-lookup"><span data-stu-id="8c362-134">A. Yes and No</span></span>  

- <span data-ttu-id="8c362-135">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="8c362-135">Q.</span></span> <span data-ttu-id="8c362-136">Доступны ли в этом регионе планы звонков по ЗВОНКОВ Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="8c362-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="8c362-137">A. Да и нет</span><span class="sxs-lookup"><span data-stu-id="8c362-137">A. Yes and No</span></span> 

<span data-ttu-id="8c362-138">На основе ответов на их вопросы компания Contoso решила:</span><span class="sxs-lookup"><span data-stu-id="8c362-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="8c362-139">Перемещение пользователей, расположенных в регионе, где планы звонков по ЗВОНКОВ ПО доступны для телефонной системы с планами звонков.</span><span class="sxs-lookup"><span data-stu-id="8c362-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="8c362-140">Перемещение пользователей, находящихся не в регионе, в котором доступны планы звонков по ЗВОНКОВ по ННР, пользователей, расположенных на сайте, где рентабельность инвестиций на SBCs еще не завершена, и пользователей, проживающих в стране, в которой есть правила для телефонии, в телефонную систему с прямой маршрутизовкой.</span><span class="sxs-lookup"><span data-stu-id="8c362-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="8c362-141">На следующей схеме показано начальное развертывание Skype для Корпоративная голосовая связь и его перенос в планы звонков Майкрософт и прямую маршрутику.</span><span class="sxs-lookup"><span data-stu-id="8c362-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![Схема до и после состояния](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="8c362-143">Тип сайта B. Традиционные устаревшие системы телефонии</span><span class="sxs-lookup"><span data-stu-id="8c362-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="8c362-144">У Contoso было много офисов, в которые использовались устаревшие системы телефонии.</span><span class="sxs-lookup"><span data-stu-id="8c362-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="8c362-145">У нескольких пользователей был номер телефона E1.64, а у других был только дополнительный номер.</span><span class="sxs-lookup"><span data-stu-id="8c362-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="8c362-146">Эти числа находились на магистрали TDM для шлюза ННР.</span><span class="sxs-lookup"><span data-stu-id="8c362-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="8c362-147">Для настройки набора номера внутри сайта с помощью кода сайта перед расширением можно определить, куда нужно перена маршрутить звонок.</span><span class="sxs-lookup"><span data-stu-id="8c362-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="8c362-148">Привычки пользователей в наборе должны были звонить по расширениям.</span><span class="sxs-lookup"><span data-stu-id="8c362-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="8c362-149">Решение компании Contoso основано на следующих вопросах:</span><span class="sxs-lookup"><span data-stu-id="8c362-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="8c362-150">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="8c362-150">Q.</span></span> <span data-ttu-id="8c362-151">Нужно ли сохранять функции, предоставляемые в локальном развертывании?</span><span class="sxs-lookup"><span data-stu-id="8c362-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="8c362-152">A.</span><span class="sxs-lookup"><span data-stu-id="8c362-152">A.</span></span> <span data-ttu-id="8c362-153">Нет</span><span class="sxs-lookup"><span data-stu-id="8c362-153">No</span></span> 

- <span data-ttu-id="8c362-154">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="8c362-154">Q.</span></span> <span data-ttu-id="8c362-155">Требуется ли пересекаться со сторонними системами УАКС и другим телефонным оборудованием?</span><span class="sxs-lookup"><span data-stu-id="8c362-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="8c362-156">A. Да</span><span class="sxs-lookup"><span data-stu-id="8c362-156">A. Yes</span></span>

- <span data-ttu-id="8c362-157">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="8c362-157">Q.</span></span> <span data-ttu-id="8c362-158">Нужно ли сохранить текущий сторонний оператор связи?</span><span class="sxs-lookup"><span data-stu-id="8c362-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="8c362-159">A. Нет</span><span class="sxs-lookup"><span data-stu-id="8c362-159">A. No</span></span> 

- <span data-ttu-id="8c362-160">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="8c362-160">Q.</span></span> <span data-ttu-id="8c362-161">Доступен ли в нашем регионе план звонков через ПС МАЙКРОСОФТ?</span><span class="sxs-lookup"><span data-stu-id="8c362-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="8c362-162">A. Да и нет</span><span class="sxs-lookup"><span data-stu-id="8c362-162">A. Yes and No</span></span> 

<span data-ttu-id="8c362-163">На основе ответов на их вопросы компания Contoso решила:</span><span class="sxs-lookup"><span data-stu-id="8c362-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="8c362-164">Перемещение пользователей, расположенных в регионе, где планы звонков по ЗВОНКОВ ПО доступны для телефонной системы с планами звонков.</span><span class="sxs-lookup"><span data-stu-id="8c362-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="8c362-165">Перемещение пользователей, не расположенных в регионе, где для телефонной системы доступны планы звонков по ПС.</span><span class="sxs-lookup"><span data-stu-id="8c362-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="8c362-166">Поддержание подключения через STN к критически важным аналоговым устройствам.</span><span class="sxs-lookup"><span data-stu-id="8c362-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="8c362-167">На следующих схемах покажите исходное устаревшее развертывание системы с удаленными сайтами и миграцию на прямое развертывание маршрутизации с локальной оптимизацией мультимедиа:</span><span class="sxs-lookup"><span data-stu-id="8c362-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="8c362-168">**Исходное устаревшее развертывание**  
 ![ Схема до и после состояния](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="8c362-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="8c362-169">**Развертывание с прямой маршрутией**</span><span class="sxs-lookup"><span data-stu-id="8c362-169">**Deployment with Direct Routing**</span></span>

![Схема до и после состояния](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="8c362-171">Тип сайта C: сочетание Skype для Корпоративная голосовая связь и традиционных телефонных систем</span><span class="sxs-lookup"><span data-stu-id="8c362-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="8c362-172">Номера пользователей Contoso Skype для Корпоративная голосовая связь находятся на телефоне SIP оператора связи с SBC.</span><span class="sxs-lookup"><span data-stu-id="8c362-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="8c362-173">Номера традиционных систем телефонии находились на телефонной связи TDM на шлюзе СТАНП.</span><span class="sxs-lookup"><span data-stu-id="8c362-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="8c362-174">Решение компании Contoso основано на следующих вопросах:</span><span class="sxs-lookup"><span data-stu-id="8c362-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="8c362-175">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="8c362-175">Q.</span></span> <span data-ttu-id="8c362-176">Нужно ли сохранять функции, предоставляемые в локальном развертывании?</span><span class="sxs-lookup"><span data-stu-id="8c362-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="8c362-177">A.</span><span class="sxs-lookup"><span data-stu-id="8c362-177">A.</span></span> <span data-ttu-id="8c362-178">Нет</span><span class="sxs-lookup"><span data-stu-id="8c362-178">No</span></span> 

- <span data-ttu-id="8c362-179">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="8c362-179">Q.</span></span> <span data-ttu-id="8c362-180">Требуется ли пересекаться со сторонними системами УАКС и другим телефонным оборудованием?</span><span class="sxs-lookup"><span data-stu-id="8c362-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="8c362-181">A. Нет</span><span class="sxs-lookup"><span data-stu-id="8c362-181">A. No</span></span> 

- <span data-ttu-id="8c362-182">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="8c362-182">Q.</span></span> <span data-ttu-id="8c362-183">Нужно ли сохранить текущий сторонний оператор связи?</span><span class="sxs-lookup"><span data-stu-id="8c362-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="8c362-184">A. Нет</span><span class="sxs-lookup"><span data-stu-id="8c362-184">A. No</span></span> 

- <span data-ttu-id="8c362-185">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="8c362-185">Q.</span></span> <span data-ttu-id="8c362-186">Нужно ли развернуть рентабельность инвестиций на SBCs?</span><span class="sxs-lookup"><span data-stu-id="8c362-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="8c362-187">A. Да и нет</span><span class="sxs-lookup"><span data-stu-id="8c362-187">A. Yes and No</span></span>  

- <span data-ttu-id="8c362-188">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="8c362-188">Q.</span></span> <span data-ttu-id="8c362-189">Доступен ли план звонков по ПС Майкрософт в этом регионе?</span><span class="sxs-lookup"><span data-stu-id="8c362-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="8c362-190">A. Нет</span><span class="sxs-lookup"><span data-stu-id="8c362-190">A. No</span></span> 

<span data-ttu-id="8c362-191">На основе ответов на их вопросы компания Contoso решила следующее:</span><span class="sxs-lookup"><span data-stu-id="8c362-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="8c362-192">Для устаревших пользователей телефонии, которые будут использовать прямую маршрутику, contoso перетаскправил номера из линии TDM на линию SIP для SBC, поскольку SBC сертифицирован для прямой маршрутки.</span><span class="sxs-lookup"><span data-stu-id="8c362-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="8c362-193">Для поддержки подмножество пользователей, перенастроив телефонную систему и разрешив маршрутику по устаревшей системе, устаревшая система телефонии была настроена в качестве следующего перехода на SBC.</span><span class="sxs-lookup"><span data-stu-id="8c362-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="8c362-194">Кроме того, чтобы способствовать изменению поведения пользователей и удалению зависимости от набора расширений между сайтами и внутри сайта, Contoso предоставляет рекомендации по использованию Teams для всех внутренних звонков.</span><span class="sxs-lookup"><span data-stu-id="8c362-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="8c362-195">На следующих схемах приведена исходная версия skype для Корпоративная голосовая связь и устаревшая система телефонии, а также миграция в смешанное развертывание с использованием прямой маршрутации.</span><span class="sxs-lookup"><span data-stu-id="8c362-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="8c362-196">**Исходное смешанное развертывание** 
 ![ Схема до состояния](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="8c362-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="8c362-197">**Смешанное развертывание с прямой маршрутией** 
 ![ Схема до состояния](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="8c362-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="8c362-198">Планы звонков</span><span class="sxs-lookup"><span data-stu-id="8c362-198">Calling Plans</span></span>

<span data-ttu-id="8c362-199">Чтобы определить требования к конфигурации для планов звонков, компания Contoso просмотрела основные решения по развертыванию планов [звонков.](calling-plan-landing-page.md#core-deployment-decisions)</span><span class="sxs-lookup"><span data-stu-id="8c362-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="8c362-200">Приняты итоговые решения:</span><span class="sxs-lookup"><span data-stu-id="8c362-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="8c362-201">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="8c362-201">Q.</span></span> <span data-ttu-id="8c362-202">Нужны ли пользователям международные вызовы?</span><span class="sxs-lookup"><span data-stu-id="8c362-202">Do my users need international calling?</span></span><br> <span data-ttu-id="8c362-203">A. Да</span><span class="sxs-lookup"><span data-stu-id="8c362-203">A. Yes</span></span> 

- <span data-ttu-id="8c362-204">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="8c362-204">Q.</span></span> <span data-ttu-id="8c362-205">У каждого из моих пользователей есть прямой телефонный номер "ВНУТРЬ"?</span><span class="sxs-lookup"><span data-stu-id="8c362-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="8c362-206">А. Сегодня нет.</span><span class="sxs-lookup"><span data-stu-id="8c362-206">A. Not today.</span></span> <span data-ttu-id="8c362-207">Все включенные пользователи получат</span><span class="sxs-lookup"><span data-stu-id="8c362-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="8c362-208">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="8c362-208">Q.</span></span> <span data-ttu-id="8c362-209">Нужно ли скрыть или отключить ИД звоня?</span><span class="sxs-lookup"><span data-stu-id="8c362-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="8c362-210">A. ИД вызываемого пользователя будет маскироваться под локальный номер contoso.</span><span class="sxs-lookup"><span data-stu-id="8c362-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="8c362-211">Прямая маршрутия</span><span class="sxs-lookup"><span data-stu-id="8c362-211">Direct Routing</span></span>

<span data-ttu-id="8c362-212">Contoso участвовала в Ignite, чтобы всегда быть в курсе возможностей Office 365, включая те, которые доступны с телефонной системой и прямой маршрутии.</span><span class="sxs-lookup"><span data-stu-id="8c362-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="8c362-213">Технические руководство и архитекторы использовали инструкции, предоставленные во время Ignite 2019, для определения их направления.</span><span class="sxs-lookup"><span data-stu-id="8c362-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="8c362-214">Использовались основные сеансы:</span><span class="sxs-lookup"><span data-stu-id="8c362-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="8c362-215">Планирование успеха с помощью прямой маршрутки Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c362-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="8c362-216">Обновления прямой маршрутинга</span><span class="sxs-lookup"><span data-stu-id="8c362-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="8c362-217">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="8c362-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="8c362-218">Сайты планов звонков</span><span class="sxs-lookup"><span data-stu-id="8c362-218">Calling Plans sites</span></span>

<span data-ttu-id="8c362-219">Чтобы получить лицензии и назначить номера телефонов пользователям, Contoso следовал за действиями, которые были предприняты в области ["Настройка планов звонков".](set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="8c362-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="8c362-220">Из-за количества пользователей, которые должны быть назначены телефонные номера, contoso решила использовать PowerShell для назначения номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="8c362-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="8c362-221">Чтобы узнать, как назначать числа с помощью PowerShell в дополнение к другим &mdash; &mdash; настройкам, Contoso использует Обзор Команд [PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8c362-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="8c362-222">Сайты прямой маршрутии</span><span class="sxs-lookup"><span data-stu-id="8c362-222">Direct Routing sites</span></span>

<span data-ttu-id="8c362-223">Для подключения локальной инфраструктуры телефонии Contoso к Microsoft Teams администратор Contoso [](direct-routing-configure.md) следовал указаниям в окне "Настройка прямой маршрутации" и просмотрел в Microsoft Teams маршруты видео Direct [Routing.](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)</span><span class="sxs-lookup"><span data-stu-id="8c362-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="8c362-224">Компания Contoso также ссылается на документацию о прямом развертывании маршрутов от сертифицированного поставщика SBC.</span><span class="sxs-lookup"><span data-stu-id="8c362-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="8c362-225">После настройки прямой маршрутации между SBC и телефонной системой Майкрософт необходимо было проверить конфигурацию Contoso.</span><span class="sxs-lookup"><span data-stu-id="8c362-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="8c362-226">Для этого администраторы Contoso использовали клиент SIP Tester, который обсуждается в обновлении прямой маршрутии на [Ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="8c362-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="8c362-227">Сценарий клиента SIP Tester и документация были скачана из сценария PowerShell для проверки подключений граничного контроллера прямого сеанса маршрутирования.</span><span class="sxs-lookup"><span data-stu-id="8c362-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="8c362-228">Local Media Optimization</span><span class="sxs-lookup"><span data-stu-id="8c362-228">Local Media Optimization</span></span>

<span data-ttu-id="8c362-229">В компании Contoso появилась возможность использовать оптимизацию локальных мультимедиа в различных регионах мира.</span><span class="sxs-lookup"><span data-stu-id="8c362-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="8c362-230">Поддерживаемые сценарии для Contoso описаны в локальной оптимизации мультимедиа [для прямой маршрутизации.](direct-routing-media-optimization.md)</span><span class="sxs-lookup"><span data-stu-id="8c362-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="8c362-231">Настройка оптимизации локальных мультимедиа была выполнена с помощью инструкций поставщика SBC и Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8c362-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="8c362-232">Действия по настройке для локальной оптимизации мультимедиа:</span><span class="sxs-lookup"><span data-stu-id="8c362-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="8c362-233">Настройка сайтов пользователя и SBC</span><span class="sxs-lookup"><span data-stu-id="8c362-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="8c362-234">Настройте SBC в соответствии с спецификацией поставщика SBC.</span><span class="sxs-lookup"><span data-stu-id="8c362-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="8c362-235">Добавление внешних доверенных IP-адресов на каждый сайт, используемый для оптимизации локальных мультимедиа</span><span class="sxs-lookup"><span data-stu-id="8c362-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="8c362-236">Определение топологии сети</span><span class="sxs-lookup"><span data-stu-id="8c362-236">Define the network topology</span></span> 

- <span data-ttu-id="8c362-237">Определение топологии виртуальной сети</span><span class="sxs-lookup"><span data-stu-id="8c362-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="8c362-238">Определение режима: "Всегда обходить" или "Только для локальных пользователей"</span><span class="sxs-lookup"><span data-stu-id="8c362-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="8c362-239">Вопросы, которые необходимо учитывать в сети</span><span class="sxs-lookup"><span data-stu-id="8c362-239">Networking considerations</span></span>

<span data-ttu-id="8c362-240">В Contoso было несколько пользователей, которым требовалось работать удаленно в течение длительного периода после включения телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="8c362-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="8c362-241">Пользователи использовали VPN для доступа к определенным бизнес-приложениям.</span><span class="sxs-lookup"><span data-stu-id="8c362-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="8c362-242">При подсистеме VPN качество звонков в телефонной системе ухудшалось.</span><span class="sxs-lookup"><span data-stu-id="8c362-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="8c362-243">Чтобы устранить проблему с качеством, в Contoso реализована реализация раздельного туннелинга VPN, что позволяло трафику Office 365 проходить через Интернет, а подключение к внутренним приложениям остается на VPN.</span><span class="sxs-lookup"><span data-stu-id="8c362-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="8c362-244">Для реализации раздельного туннелинга VPN компания Contoso придерживается инструкций по реализации раздельного туннелинга VPN для [Office 365.](/office365/enterprise/office-365-vpn-implement-split-tunnel)</span><span class="sxs-lookup"><span data-stu-id="8c362-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

