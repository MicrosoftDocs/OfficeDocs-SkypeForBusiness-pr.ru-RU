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
ms.openlocfilehash: 995b4ddf9c07dea57c8d4de9940776d5137c2d02
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101035"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="a3cae-103">Пример работы с Contoso: телефонная система</span><span class="sxs-lookup"><span data-stu-id="a3cae-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="a3cae-104">В зависимости от географического расположения и других факторов в contoso были офисы, использующие следующие решения для телефонии:</span><span class="sxs-lookup"><span data-stu-id="a3cae-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="a3cae-105">Тип сайта A: Skype для бизнеса Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="a3cae-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="a3cae-106">Тип сайта B. Традиционные устаревшие системы телефонии</span><span class="sxs-lookup"><span data-stu-id="a3cae-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="a3cae-107">Тип сайта C: сочетание Skype для бизнеса Корпоративная голосовая связь и традиционных устаревших систем телефонии</span><span class="sxs-lookup"><span data-stu-id="a3cae-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="a3cae-108">Чтобы внедрить решение Телефон (Майкрософт) для всей организации, contoso должен был определить для каждого типа сайта, какие из следующих параметров будут использоваться с телефонная система для подключения к ОКП. &mdash; &mdash;</span><span class="sxs-lookup"><span data-stu-id="a3cae-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="a3cae-109">телефонная система с планом звонков</span><span class="sxs-lookup"><span data-stu-id="a3cae-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="a3cae-110">телефонная система с собственным оператором STN через прямую маршрутику</span><span class="sxs-lookup"><span data-stu-id="a3cae-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="a3cae-111">Сочетание телефонная система с планом звонков и телефонная система с собственным оператором ЗВОНКОВ через прямую маршрутику</span><span class="sxs-lookup"><span data-stu-id="a3cae-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="a3cae-112">Чтобы определить правильное решение для своей организации, Contoso использовал решения для телефонии [Майкрософт](/SkypeForBusiness/hybrid/msft-telephony-solutions) и сеанс Ignite 2019 [Calling в Microsoft Teams.](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="a3cae-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="a3cae-113">Тип сайта A: Skype для бизнеса Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="a3cae-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="a3cae-114">Contoso Skype для бизнеса Корпоративная голосовая связь была настроена как центр и ора.</span><span class="sxs-lookup"><span data-stu-id="a3cae-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="a3cae-115">В регионе поддерживался шлюз ННР, который обеспечивает подключение к STN для Skype для бизнеса Корпоративная голосовая связь пользователей в стране.</span><span class="sxs-lookup"><span data-stu-id="a3cae-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="a3cae-116">Часто эти спутниковые офисы не имеют собственного доступа к Интернету.</span><span class="sxs-lookup"><span data-stu-id="a3cae-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="a3cae-117">Номера для этих пользователей находились на соединительных связях SIP с существующим SBC.</span><span class="sxs-lookup"><span data-stu-id="a3cae-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="a3cae-118">Чтобы определить, сертифицирован ли SBC для прямого обхода маршрутов и мультимедиа, Contoso проверил список контроллеров границ сеанса, сертифицированный для прямой [маршрутирования.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="a3cae-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="a3cae-119">При наборе номера пользователю нужно было набрать номер в устаревшей телефонной системе с помощью расширения, даже если у него есть клиент Skype для бизнеса для одноранговой связи.</span><span class="sxs-lookup"><span data-stu-id="a3cae-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="a3cae-120">Решение Contoso основано на следующих вопросах:</span><span class="sxs-lookup"><span data-stu-id="a3cae-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="a3cae-121">Q.</span><span class="sxs-lookup"><span data-stu-id="a3cae-121">Q.</span></span> <span data-ttu-id="a3cae-122">Нужно ли сохранять функции, предоставляемые в локальном развертывании?</span><span class="sxs-lookup"><span data-stu-id="a3cae-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="a3cae-123">А.</span><span class="sxs-lookup"><span data-stu-id="a3cae-123">A.</span></span> <span data-ttu-id="a3cae-124">Нет</span><span class="sxs-lookup"><span data-stu-id="a3cae-124">No</span></span> 

- <span data-ttu-id="a3cae-125">Q.</span><span class="sxs-lookup"><span data-stu-id="a3cae-125">Q.</span></span> <span data-ttu-id="a3cae-126">Нужно ли во время связи со сторонними системами УАКС и другим телефонным оборудованием?</span><span class="sxs-lookup"><span data-stu-id="a3cae-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="a3cae-127">А.</span><span class="sxs-lookup"><span data-stu-id="a3cae-127">A.</span></span> <span data-ttu-id="a3cae-128">Нет</span><span class="sxs-lookup"><span data-stu-id="a3cae-128">No</span></span> 

- <span data-ttu-id="a3cae-129">Q.</span><span class="sxs-lookup"><span data-stu-id="a3cae-129">Q.</span></span> <span data-ttu-id="a3cae-130">Нужно ли сохранить текущий сторонний оператор?</span><span class="sxs-lookup"><span data-stu-id="a3cae-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="a3cae-131">А. Да (регулируемые страны) и Нет</span><span class="sxs-lookup"><span data-stu-id="a3cae-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="a3cae-132">Q.</span><span class="sxs-lookup"><span data-stu-id="a3cae-132">Q.</span></span> <span data-ttu-id="a3cae-133">Нужно ли развертывать рентабельность инвестиций на SBCs?</span><span class="sxs-lookup"><span data-stu-id="a3cae-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="a3cae-134">А. Да и нет</span><span class="sxs-lookup"><span data-stu-id="a3cae-134">A. Yes and No</span></span>  

- <span data-ttu-id="a3cae-135">Q.</span><span class="sxs-lookup"><span data-stu-id="a3cae-135">Q.</span></span> <span data-ttu-id="a3cae-136">Доступны ли планы звонков по ЗВОНКОВ майкрософт в этом регионе?</span><span class="sxs-lookup"><span data-stu-id="a3cae-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="a3cae-137">А. Да и нет</span><span class="sxs-lookup"><span data-stu-id="a3cae-137">A. Yes and No</span></span> 

<span data-ttu-id="a3cae-138">На основе ответов на их вопросы компания Contoso решила:</span><span class="sxs-lookup"><span data-stu-id="a3cae-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="a3cae-139">Перемещение пользователей, расположенных в регионе, где планы звонков по ЗВОНКОВ доступны для телефонная система планов звонков.</span><span class="sxs-lookup"><span data-stu-id="a3cae-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="a3cae-140">Перемещение пользователей, которые находятся не в регионе, где доступны планы звонков по ЗВОНКОВ по ЗВОНКОВ по ННР, пользователей на сайте, где рентабельность инвестиций на УАП еще не выполнены, а пользователей, проживающих в стране с нормативными правилами телефонии, можно телефонная система прямой маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="a3cae-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="a3cae-141">На следующей схеме показано Skype для бизнеса Корпоративная голосовая связь развертывания и его переноса в планы звонков Майкрософт и прямую маршрутику.</span><span class="sxs-lookup"><span data-stu-id="a3cae-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![Схема, показывающая до и после состояния](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="a3cae-143">Тип сайта B. Традиционные устаревшие системы телефонии</span><span class="sxs-lookup"><span data-stu-id="a3cae-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="a3cae-144">В Contoso было много офисов, в которые использовались устаревшие системы телефонии.</span><span class="sxs-lookup"><span data-stu-id="a3cae-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="a3cae-145">Некоторые пользователи имели номер телефона E1.64, тогда как у других были только расширения.</span><span class="sxs-lookup"><span data-stu-id="a3cae-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="a3cae-146">Эти номера находились на магистрали TDM для шлюза STN.</span><span class="sxs-lookup"><span data-stu-id="a3cae-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="a3cae-147">Настройка набора внутри сайта с помощью кода сайта перед расширением для определения направления звонка.</span><span class="sxs-lookup"><span data-stu-id="a3cae-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="a3cae-148">Пользователям нужно было набирать номера по расширению.</span><span class="sxs-lookup"><span data-stu-id="a3cae-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="a3cae-149">Решение Contoso основано на следующих вопросах:</span><span class="sxs-lookup"><span data-stu-id="a3cae-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="a3cae-150">Q.</span><span class="sxs-lookup"><span data-stu-id="a3cae-150">Q.</span></span> <span data-ttu-id="a3cae-151">Нужно ли сохранять функции, предоставляемые в локальном развертывании?</span><span class="sxs-lookup"><span data-stu-id="a3cae-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="a3cae-152">А.</span><span class="sxs-lookup"><span data-stu-id="a3cae-152">A.</span></span> <span data-ttu-id="a3cae-153">Нет</span><span class="sxs-lookup"><span data-stu-id="a3cae-153">No</span></span> 

- <span data-ttu-id="a3cae-154">Q.</span><span class="sxs-lookup"><span data-stu-id="a3cae-154">Q.</span></span> <span data-ttu-id="a3cae-155">Нужно ли во время связи со сторонними системами УАКС и другим телефонным оборудованием?</span><span class="sxs-lookup"><span data-stu-id="a3cae-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="a3cae-156">А. Да</span><span class="sxs-lookup"><span data-stu-id="a3cae-156">A. Yes</span></span>

- <span data-ttu-id="a3cae-157">Q.</span><span class="sxs-lookup"><span data-stu-id="a3cae-157">Q.</span></span> <span data-ttu-id="a3cae-158">Нужно ли сохранить текущий сторонний оператор?</span><span class="sxs-lookup"><span data-stu-id="a3cae-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="a3cae-159">А. Нет</span><span class="sxs-lookup"><span data-stu-id="a3cae-159">A. No</span></span> 

- <span data-ttu-id="a3cae-160">Q.</span><span class="sxs-lookup"><span data-stu-id="a3cae-160">Q.</span></span> <span data-ttu-id="a3cae-161">Доступен ли в нашем регионе план звонков через ОКП Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="a3cae-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="a3cae-162">А. Да и нет</span><span class="sxs-lookup"><span data-stu-id="a3cae-162">A. Yes and No</span></span> 

<span data-ttu-id="a3cae-163">На основе ответов на их вопросы компания Contoso решила:</span><span class="sxs-lookup"><span data-stu-id="a3cae-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="a3cae-164">Перемещение пользователей, расположенных в регионе, где планы звонков по ЗВОНКОВ доступны для телефонная система планов звонков.</span><span class="sxs-lookup"><span data-stu-id="a3cae-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="a3cae-165">Перемещение пользователей, которые не находятся в регионе, где планы звонков по ЗВОНКОВ телефонная система с прямой маршрутикой.</span><span class="sxs-lookup"><span data-stu-id="a3cae-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="a3cae-166">Поддерживать подключение через STN к критически важным аналоговым устройствам.</span><span class="sxs-lookup"><span data-stu-id="a3cae-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="a3cae-167">На схемах ниже покажите исходное развертывание устаревшей системы с удаленными сайтами и миграцию на прямое развертывание маршрутизации с помощью локальной оптимизации мультимедиа:</span><span class="sxs-lookup"><span data-stu-id="a3cae-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="a3cae-168">**Исходное устаревшее развертывание**  
 ![ Схема, показывающая до и после состояния](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="a3cae-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="a3cae-169">**Развертывание с прямой маршрутией**</span><span class="sxs-lookup"><span data-stu-id="a3cae-169">**Deployment with Direct Routing**</span></span>

![Схема, показывающая до и после состояния](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="a3cae-171">Тип сайта C: сочетание Skype для бизнеса Корпоративная голосовая связь и традиционных устаревших телефонных систем</span><span class="sxs-lookup"><span data-stu-id="a3cae-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="a3cae-172">Contoso Skype для бизнеса Корпоративная голосовая связь номера пользователей находятся на телефоне SIP в SBC от оператора связи.</span><span class="sxs-lookup"><span data-stu-id="a3cae-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="a3cae-173">Номера традиционных систем телефонии находились на tDM-канале до шлюза STN.</span><span class="sxs-lookup"><span data-stu-id="a3cae-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="a3cae-174">Решение Contoso основано на следующих вопросах:</span><span class="sxs-lookup"><span data-stu-id="a3cae-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="a3cae-175">Q.</span><span class="sxs-lookup"><span data-stu-id="a3cae-175">Q.</span></span> <span data-ttu-id="a3cae-176">Нужно ли сохранять функции, предоставляемые в локальном развертывании?</span><span class="sxs-lookup"><span data-stu-id="a3cae-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="a3cae-177">А.</span><span class="sxs-lookup"><span data-stu-id="a3cae-177">A.</span></span> <span data-ttu-id="a3cae-178">Нет</span><span class="sxs-lookup"><span data-stu-id="a3cae-178">No</span></span> 

- <span data-ttu-id="a3cae-179">Q.</span><span class="sxs-lookup"><span data-stu-id="a3cae-179">Q.</span></span> <span data-ttu-id="a3cae-180">Нужно ли во время связи со сторонними системами УАКС и другим телефонным оборудованием?</span><span class="sxs-lookup"><span data-stu-id="a3cae-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="a3cae-181">А. Нет</span><span class="sxs-lookup"><span data-stu-id="a3cae-181">A. No</span></span> 

- <span data-ttu-id="a3cae-182">Q.</span><span class="sxs-lookup"><span data-stu-id="a3cae-182">Q.</span></span> <span data-ttu-id="a3cae-183">Нужно ли сохранить текущий сторонний оператор?</span><span class="sxs-lookup"><span data-stu-id="a3cae-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="a3cae-184">А. Нет</span><span class="sxs-lookup"><span data-stu-id="a3cae-184">A. No</span></span> 

- <span data-ttu-id="a3cae-185">Q.</span><span class="sxs-lookup"><span data-stu-id="a3cae-185">Q.</span></span> <span data-ttu-id="a3cae-186">Нужно ли развертывать рентабельность инвестиций на SBCs?</span><span class="sxs-lookup"><span data-stu-id="a3cae-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="a3cae-187">А. Да и нет</span><span class="sxs-lookup"><span data-stu-id="a3cae-187">A. Yes and No</span></span>  

- <span data-ttu-id="a3cae-188">Q.</span><span class="sxs-lookup"><span data-stu-id="a3cae-188">Q.</span></span> <span data-ttu-id="a3cae-189">Доступен ли план звонков по ЗВОНКОВ по ЗВОНКОВ майкрософт в этом регионе?</span><span class="sxs-lookup"><span data-stu-id="a3cae-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="a3cae-190">А. Нет</span><span class="sxs-lookup"><span data-stu-id="a3cae-190">A. No</span></span> 

<span data-ttu-id="a3cae-191">На основе ответов на их вопросы Компания Contoso решила следующее:</span><span class="sxs-lookup"><span data-stu-id="a3cae-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="a3cae-192">Для пользователей телефонии старых номеров, которые будут включены для прямой маршрутии, Contoso перенаправил номера из TDM-линии на линию SIP для SBC, так как SBC сертифицирован для прямой маршрутии.</span><span class="sxs-lookup"><span data-stu-id="a3cae-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="a3cae-193">Чтобы обеспечить поддержку подмножество пользователей, переехав на телефонная система и разрешив продолжить маршрутику по устаревшей системе, устаревшая телефонная система была настроена в качестве следующего перехода к SBC.</span><span class="sxs-lookup"><span data-stu-id="a3cae-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="a3cae-194">Кроме того, чтобы способствовать изменению поведения пользователей и удалить зависимость от набора расширений между сайтами и внутри сайта, Contoso предоставляет рекомендации по использованию Teams для всех внутренних звонков.</span><span class="sxs-lookup"><span data-stu-id="a3cae-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="a3cae-195">На схемах ниже покажите исходное развертывание Skype для бизнеса Корпоративная голосовая связь и устаревшей телефонной системы, а также миграцию в смешанное развертывание с использованием прямой маршрутации.</span><span class="sxs-lookup"><span data-stu-id="a3cae-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="a3cae-196">**Исходное смешанное развертывание** 
 ![ Схема, показанная перед состоянием](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="a3cae-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="a3cae-197">**Смешанное развертывание с прямой маршрутией** 
 ![ Схема, показанная перед состоянием](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="a3cae-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="a3cae-198">Планы звонков</span><span class="sxs-lookup"><span data-stu-id="a3cae-198">Calling Plans</span></span>

<span data-ttu-id="a3cae-199">Чтобы определить требования к конфигурации для планов звонков, Компания Contoso проанализировала основные решения по развертыванию плана [звонков.](calling-plan-landing-page.md#core-deployment-decisions)</span><span class="sxs-lookup"><span data-stu-id="a3cae-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="a3cae-200">Принимались итоговые решения:</span><span class="sxs-lookup"><span data-stu-id="a3cae-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="a3cae-201">Q.</span><span class="sxs-lookup"><span data-stu-id="a3cae-201">Q.</span></span> <span data-ttu-id="a3cae-202">Нужны ли пользователям международные вызовы?</span><span class="sxs-lookup"><span data-stu-id="a3cae-202">Do my users need international calling?</span></span><br> <span data-ttu-id="a3cae-203">А. Да</span><span class="sxs-lookup"><span data-stu-id="a3cae-203">A. Yes</span></span> 

- <span data-ttu-id="a3cae-204">Q.</span><span class="sxs-lookup"><span data-stu-id="a3cae-204">Q.</span></span> <span data-ttu-id="a3cae-205">У каждого из пользователей есть прямой номер телефона "ВНУТРЬ"?</span><span class="sxs-lookup"><span data-stu-id="a3cae-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="a3cae-206">А. Не сегодня.</span><span class="sxs-lookup"><span data-stu-id="a3cae-206">A. Not today.</span></span> <span data-ttu-id="a3cae-207">Все включенные пользователи получат did (DID).</span><span class="sxs-lookup"><span data-stu-id="a3cae-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="a3cae-208">Q.</span><span class="sxs-lookup"><span data-stu-id="a3cae-208">Q.</span></span> <span data-ttu-id="a3cae-209">Нужно ли маскировать или отключать ИД вызываемой вызовы?</span><span class="sxs-lookup"><span data-stu-id="a3cae-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="a3cae-210">А. ИД вызываемого пользователя будет маскироваться под локальный номер Contoso.</span><span class="sxs-lookup"><span data-stu-id="a3cae-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="a3cae-211">Прямая маршрутия</span><span class="sxs-lookup"><span data-stu-id="a3cae-211">Direct Routing</span></span>

<span data-ttu-id="a3cae-212">Contoso участвовала в Ignite, чтобы всегда быть в Office 365, включая те, которые доступны с Телефон системы и прямой маршрутии.</span><span class="sxs-lookup"><span data-stu-id="a3cae-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="a3cae-213">Технические руководство и архитекторы использовали инструкции, предоставленные в ignite 2019, для определения их направления.</span><span class="sxs-lookup"><span data-stu-id="a3cae-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="a3cae-214">Использовались ключевые сеансы.</span><span class="sxs-lookup"><span data-stu-id="a3cae-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="a3cae-215">Планирование успеха с Microsoft Teams прямой маршрутии</span><span class="sxs-lookup"><span data-stu-id="a3cae-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="a3cae-216">Обновления прямой маршрутии</span><span class="sxs-lookup"><span data-stu-id="a3cae-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="a3cae-217">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="a3cae-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="a3cae-218">Сайты планов звонков</span><span class="sxs-lookup"><span data-stu-id="a3cae-218">Calling Plans sites</span></span>

<span data-ttu-id="a3cae-219">Чтобы получить лицензии и назначить номера телефонов пользователям, Компания Contoso, как было поручено в области Настройка [планов звонков,](set-up-calling-plans.md)придерживается действий.</span><span class="sxs-lookup"><span data-stu-id="a3cae-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="a3cae-220">Из-за количества пользователей, которые должны быть назначены телефонные номера, Contoso решил использовать PowerShell для назначения номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="a3cae-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="a3cae-221">Чтобы узнать, как назначать числа с помощью PowerShell в дополнение к другим настройкам, Contoso использует Teams &mdash; &mdash; [PowerShell Overview](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a3cae-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="a3cae-222">Сайты прямой маршрутии</span><span class="sxs-lookup"><span data-stu-id="a3cae-222">Direct Routing sites</span></span>

<span data-ttu-id="a3cae-223">Чтобы подключить к Microsoft Teams инфраструктуру локальной телефонной связи Contoso, администратор Contoso, [](direct-routing-configure.md) вы следовать указаниям в окне Настройка прямой маршрутации, а также просмотрел видео Direct [Routing](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a3cae-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="a3cae-224">Contoso также ссылается на документацию сертифицированного поставщика SBC о прямой маршрутистике.</span><span class="sxs-lookup"><span data-stu-id="a3cae-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="a3cae-225">После настройки прямой маршрутиации между SBC и Телефон (Майкрософт) System необходимо было проверить конфигурацию contoso.</span><span class="sxs-lookup"><span data-stu-id="a3cae-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="a3cae-226">Для этого администраторы Contoso использовали клиент SIP Tester, который обсуждается в сеансе Обновления для прямой маршрутии на [ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="a3cae-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="a3cae-227">Сценарий клиента тестировщика SIP и документация были загружены из сценария PowerShell для тестирования подключений к контроллеру границы прямого сеанса маршрутирования.</span><span class="sxs-lookup"><span data-stu-id="a3cae-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="a3cae-228">Оптимизация локальных мультимедиа</span><span class="sxs-lookup"><span data-stu-id="a3cae-228">Local Media Optimization</span></span>

<span data-ttu-id="a3cae-229">Contoso видит возможность использовать оптимизацию локальных мультимедиа в разных регионах по всему миру.</span><span class="sxs-lookup"><span data-stu-id="a3cae-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="a3cae-230">Поддерживаемые сценарии для Contoso описаны в local [Media Optimization для прямой маршрутизации.](direct-routing-media-optimization.md)</span><span class="sxs-lookup"><span data-stu-id="a3cae-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="a3cae-231">Настройка оптимизации локальных мультимедиа была завершена с помощью инструкций поставщика SBC и Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a3cae-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="a3cae-232">Действия по настройке для оптимизации локальных мультимедиа:</span><span class="sxs-lookup"><span data-stu-id="a3cae-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="a3cae-233">Настройка сайтов пользователя и SBC</span><span class="sxs-lookup"><span data-stu-id="a3cae-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="a3cae-234">Настройте SBC в соответствии с спецификацией поставщика SBC,</span><span class="sxs-lookup"><span data-stu-id="a3cae-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="a3cae-235">Добавление внешних доверенных IP-адресов на каждый сайт, используемый для оптимизации локальных мультимедиа</span><span class="sxs-lookup"><span data-stu-id="a3cae-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="a3cae-236">Определение топологии сети</span><span class="sxs-lookup"><span data-stu-id="a3cae-236">Define the network topology</span></span> 

- <span data-ttu-id="a3cae-237">Определение топологии виртуальной сети</span><span class="sxs-lookup"><span data-stu-id="a3cae-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="a3cae-238">Определение режима: Всегда обходить или Только для локальных пользователей</span><span class="sxs-lookup"><span data-stu-id="a3cae-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="a3cae-239">Сетевые аспекты</span><span class="sxs-lookup"><span data-stu-id="a3cae-239">Networking considerations</span></span>

<span data-ttu-id="a3cae-240">В Contoso было несколько пользователей, которым требовалось работать удаленно в течение длительного периода времени после включения телефонная система.</span><span class="sxs-lookup"><span data-stu-id="a3cae-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="a3cae-241">Пользователи использовали VPN для доступа к определенным бизнес-приложениям.</span><span class="sxs-lookup"><span data-stu-id="a3cae-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="a3cae-242">В VPN качество телефонная система ухудшалось.</span><span class="sxs-lookup"><span data-stu-id="a3cae-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="a3cae-243">Чтобы устранить проблему с качеством, компания Contoso реализовала раздельное тунтенинг VPN, что позволило Office 365 трафику через Интернет, а подключение к внутренним приложениям оставалось на VPN.</span><span class="sxs-lookup"><span data-stu-id="a3cae-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="a3cae-244">Чтобы внедрить раздельный vpn- tunneling, Contoso следовать указаниям в реализации [vpn split tunneling для](/office365/enterprise/office-365-vpn-implement-split-tunnel)Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3cae-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

