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
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786098"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="13c0d-103">Исследование успеха Contoso: телефонная система</span><span class="sxs-lookup"><span data-stu-id="13c0d-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="13c0d-104">В зависимости от географического местоположения и других факторов компания Contoso содержала офисы, использующие следующие решения для телефонной связи:</span><span class="sxs-lookup"><span data-stu-id="13c0d-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="13c0d-105">Тип сайта а: голосовой связи Skype для бизнеса (корпоративный)</span><span class="sxs-lookup"><span data-stu-id="13c0d-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="13c0d-106">Тип сайта B: традиционные старые системы телефонии</span><span class="sxs-lookup"><span data-stu-id="13c0d-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="13c0d-107">Тип сайта C: сочетание голосовой связи в Skype для бизнеса для предприятий и традиционных стандартных телефонных систем</span><span class="sxs-lookup"><span data-stu-id="13c0d-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="13c0d-108">Для реализации решения Microsoft Phone System для всей Организации компания Contoso приходила определить &mdash; для каждого из типов сайтов, &mdash; какие из указанных ниже вариантов будут использоваться в телефонной сети для подключения к общественной коммутируемой телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="13c0d-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="13c0d-109">Телефонная система с планом звонков</span><span class="sxs-lookup"><span data-stu-id="13c0d-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="13c0d-110">Телефонная система с собственной несущей для КОММУТИРУЕМой связи через прямую маршрутизацию</span><span class="sxs-lookup"><span data-stu-id="13c0d-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="13c0d-111">Сочетание телефонной системы с планом звонков и телефонной системой с помощью прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="13c0d-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="13c0d-112">Чтобы определить подходящего решения для своей организации, Contoso использует [решения Microsoft для телефонной связи](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) и сеанс Ignite 2019 [в Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="13c0d-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="13c0d-113">Тип сайта а: голосовой связи Skype для бизнеса (корпоративный)</span><span class="sxs-lookup"><span data-stu-id="13c0d-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="13c0d-114">Голосовая связь Contoso Skype для бизнеса Enterprise была настроена в качестве основного и резервного.</span><span class="sxs-lookup"><span data-stu-id="13c0d-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="13c0d-115">В регионе, который обеспечивает подключение к сети PSTN для пользователей голосовой связи Skype для бизнеса в стране, есть центральное место, в котором поддерживается шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="13c0d-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="13c0d-116">Часто в этих вспомогательных офисах нет собственного выхода в Интернет.</span><span class="sxs-lookup"><span data-stu-id="13c0d-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="13c0d-117">Номера для этих пользователей находились на магистральной магистрали SIP, соединяющей с существующим SBC.</span><span class="sxs-lookup"><span data-stu-id="13c0d-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="13c0d-118">Чтобы определить, является ли уже развернутый SBC, сертифицированный для прямой маршрутизации и пропуска мультимедиа, компания Contoso проверила [список контроллеров границ сеанса, сертифицированных для прямого маршрутизации](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="13c0d-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="13c0d-119">Пользователь должен набрать пользователя в устаревшей системе телефонной связи с помощью расширения, даже если у пользователя есть клиент Skype для бизнеса, доступный для однорангового звука.</span><span class="sxs-lookup"><span data-stu-id="13c0d-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="13c0d-120">В соответствии со своими решениями для Contoso на следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="13c0d-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="13c0d-121">Стоит.</span><span class="sxs-lookup"><span data-stu-id="13c0d-121">Q.</span></span> <span data-ttu-id="13c0d-122">Нужно ли сохранять функциональные возможности, предоставляемые нашим локальным развертыванием?</span><span class="sxs-lookup"><span data-stu-id="13c0d-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="13c0d-123">Помощью.</span><span class="sxs-lookup"><span data-stu-id="13c0d-123">A.</span></span> <span data-ttu-id="13c0d-124">Нет</span><span class="sxs-lookup"><span data-stu-id="13c0d-124">No</span></span> 

- <span data-ttu-id="13c0d-125">Стоит.</span><span class="sxs-lookup"><span data-stu-id="13c0d-125">Q.</span></span> <span data-ttu-id="13c0d-126">Требуется ли взаимодействие со сторонними системами УАТС и другим оборудованием телефонной связи?</span><span class="sxs-lookup"><span data-stu-id="13c0d-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="13c0d-127">Помощью.</span><span class="sxs-lookup"><span data-stu-id="13c0d-127">A.</span></span> <span data-ttu-id="13c0d-128">Нет</span><span class="sxs-lookup"><span data-stu-id="13c0d-128">No</span></span> 

- <span data-ttu-id="13c0d-129">Стоит.</span><span class="sxs-lookup"><span data-stu-id="13c0d-129">Q.</span></span> <span data-ttu-id="13c0d-130">Нужно ли хранить текущую стороннюю несущую версию?</span><span class="sxs-lookup"><span data-stu-id="13c0d-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="13c0d-131">A. Да (регулируемые страны) и без</span><span class="sxs-lookup"><span data-stu-id="13c0d-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="13c0d-132">Стоит.</span><span class="sxs-lookup"><span data-stu-id="13c0d-132">Q.</span></span> <span data-ttu-id="13c0d-133">Требуется ли получить коэффициент окупаемости инвестиций для развернутого SBCs?</span><span class="sxs-lookup"><span data-stu-id="13c0d-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="13c0d-134">A. Да и нет</span><span class="sxs-lookup"><span data-stu-id="13c0d-134">A. Yes and No</span></span>  

- <span data-ttu-id="13c0d-135">Стоит.</span><span class="sxs-lookup"><span data-stu-id="13c0d-135">Q.</span></span> <span data-ttu-id="13c0d-136">Доступны ли в этом регионе планы звонков по Microsoft PSTN?</span><span class="sxs-lookup"><span data-stu-id="13c0d-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="13c0d-137">A. Да и нет</span><span class="sxs-lookup"><span data-stu-id="13c0d-137">A. Yes and No</span></span> 

<span data-ttu-id="13c0d-138">В соответствии с ответами на вопросы компания Contoso решила:</span><span class="sxs-lookup"><span data-stu-id="13c0d-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="13c0d-139">Перемещайте пользователей, которые находятся в регионе, где планы звонков по КОММУТИРУЕМой телефонной линии доступны для телефонных систем с тарифными планами.</span><span class="sxs-lookup"><span data-stu-id="13c0d-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="13c0d-140">Перемещайте пользователей, которых нет в регионе, где доступны планы по КОММУТИРУЕМой телефонной сети, пользователи, находящиеся на сайте, где коэффициент окупаемости не соблюдается, и пользователи, которые находились в стране, в которой есть правила для телефонной системы с прямой маршрутизацией.</span><span class="sxs-lookup"><span data-stu-id="13c0d-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="13c0d-141">На приведенной ниже схеме показана первоначальная настройка голосовой связи в Skype для бизнеса Enterprise и способ переноса этого развертывания на планы звонков и прямую маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="13c0d-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![Диаграмма, показывающая состояние "до" и "после"](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="13c0d-143">Тип сайта B: традиционные старые системы телефонии</span><span class="sxs-lookup"><span data-stu-id="13c0d-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="13c0d-144">В компании Contoso уже много офисов, использующих старые системы телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="13c0d-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="13c0d-145">У меня есть подмножество пользователей с 1.64ным номером телефона, а у других — только расширение.</span><span class="sxs-lookup"><span data-stu-id="13c0d-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="13c0d-146">Эти номера находились на магистральной магистрали TDM с шлюзом PSTN.</span><span class="sxs-lookup"><span data-stu-id="13c0d-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="13c0d-147">Внутренний набор номера находился с помощью кода сайта перед расширением, чтобы определить, куда перенаправляться звонок.</span><span class="sxs-lookup"><span data-stu-id="13c0d-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="13c0d-148">Пользователи должны набрать номер, чтобы звонить по расширению.</span><span class="sxs-lookup"><span data-stu-id="13c0d-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="13c0d-149">В соответствии со своими решениями для Contoso на следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="13c0d-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="13c0d-150">Стоит.</span><span class="sxs-lookup"><span data-stu-id="13c0d-150">Q.</span></span> <span data-ttu-id="13c0d-151">Нужно ли сохранять функциональные возможности, предоставляемые нашим локальным развертыванием?</span><span class="sxs-lookup"><span data-stu-id="13c0d-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="13c0d-152">Помощью.</span><span class="sxs-lookup"><span data-stu-id="13c0d-152">A.</span></span> <span data-ttu-id="13c0d-153">Нет</span><span class="sxs-lookup"><span data-stu-id="13c0d-153">No</span></span> 

- <span data-ttu-id="13c0d-154">Стоит.</span><span class="sxs-lookup"><span data-stu-id="13c0d-154">Q.</span></span> <span data-ttu-id="13c0d-155">Требуется ли взаимодействие со сторонними системами УАТС и другим оборудованием телефонной связи?</span><span class="sxs-lookup"><span data-stu-id="13c0d-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="13c0d-156">О. Да</span><span class="sxs-lookup"><span data-stu-id="13c0d-156">A. Yes</span></span>

- <span data-ttu-id="13c0d-157">Стоит.</span><span class="sxs-lookup"><span data-stu-id="13c0d-157">Q.</span></span> <span data-ttu-id="13c0d-158">Нужно ли хранить текущую стороннюю несущую версию?</span><span class="sxs-lookup"><span data-stu-id="13c0d-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="13c0d-159">А.</span><span class="sxs-lookup"><span data-stu-id="13c0d-159">A. No</span></span> 

- <span data-ttu-id="13c0d-160">Стоит.</span><span class="sxs-lookup"><span data-stu-id="13c0d-160">Q.</span></span> <span data-ttu-id="13c0d-161">Доступно ли в нашем регионе план звонков по Microsoft PSTN?</span><span class="sxs-lookup"><span data-stu-id="13c0d-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="13c0d-162">A. Да и нет</span><span class="sxs-lookup"><span data-stu-id="13c0d-162">A. Yes and No</span></span> 

<span data-ttu-id="13c0d-163">В соответствии с ответами на вопросы компания Contoso решила:</span><span class="sxs-lookup"><span data-stu-id="13c0d-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="13c0d-164">Перемещайте пользователей, которые находятся в регионе, где планы звонков по КОММУТИРУЕМой телефонной линии доступны для телефонных систем с тарифными планами.</span><span class="sxs-lookup"><span data-stu-id="13c0d-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="13c0d-165">Переместить пользователей, которые не находятся в регионе, где планы звонков по КОММУТИРУЕМой телефонной линии доступны для прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="13c0d-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="13c0d-166">Поддерживать PSTN-связь с важнейшими аналоговыми устройствами для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="13c0d-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="13c0d-167">На приведенных ниже схемах показано первоначальное развертывание старой системы с удаленными сайтами и миграция на прямую подписку с помощью локальной оптимизации файлов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="13c0d-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="13c0d-168">**Исходное развертывание**  
 ![ в старом формате Диаграмма, показывающая состояние "до" и "после"](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="13c0d-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="13c0d-169">**Развертывание с прямой маршрутизацией**</span><span class="sxs-lookup"><span data-stu-id="13c0d-169">**Deployment with Direct Routing**</span></span>

![Диаграмма, показывающая состояние "до" и "после"](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="13c0d-171">Тип сайта C: сочетание голосовой связи в Skype для бизнеса (корпоративный) и традиционных стандартных телефонных систем</span><span class="sxs-lookup"><span data-stu-id="13c0d-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="13c0d-172">Номера пользователей Skype для бизнеса для предприятий голосовой связи (Contoso) размещаются на магистралье SIP на SBC из несущей частоты.</span><span class="sxs-lookup"><span data-stu-id="13c0d-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="13c0d-173">Номера традиционных телефонных систем, находились на магистральной магистрали TDM на шлюзе PSTN.</span><span class="sxs-lookup"><span data-stu-id="13c0d-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="13c0d-174">В соответствии со своими решениями для Contoso на следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="13c0d-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="13c0d-175">Стоит.</span><span class="sxs-lookup"><span data-stu-id="13c0d-175">Q.</span></span> <span data-ttu-id="13c0d-176">Нужно ли сохранять функциональные возможности, предоставляемые нашим локальным развертыванием?</span><span class="sxs-lookup"><span data-stu-id="13c0d-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="13c0d-177">Помощью.</span><span class="sxs-lookup"><span data-stu-id="13c0d-177">A.</span></span> <span data-ttu-id="13c0d-178">Нет</span><span class="sxs-lookup"><span data-stu-id="13c0d-178">No</span></span> 

- <span data-ttu-id="13c0d-179">Стоит.</span><span class="sxs-lookup"><span data-stu-id="13c0d-179">Q.</span></span> <span data-ttu-id="13c0d-180">Требуется ли взаимодействие со сторонними системами УАТС и другим оборудованием телефонной связи?</span><span class="sxs-lookup"><span data-stu-id="13c0d-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="13c0d-181">А.</span><span class="sxs-lookup"><span data-stu-id="13c0d-181">A. No</span></span> 

- <span data-ttu-id="13c0d-182">Стоит.</span><span class="sxs-lookup"><span data-stu-id="13c0d-182">Q.</span></span> <span data-ttu-id="13c0d-183">Нужно ли хранить текущую стороннюю несущую версию?</span><span class="sxs-lookup"><span data-stu-id="13c0d-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="13c0d-184">А.</span><span class="sxs-lookup"><span data-stu-id="13c0d-184">A. No</span></span> 

- <span data-ttu-id="13c0d-185">Стоит.</span><span class="sxs-lookup"><span data-stu-id="13c0d-185">Q.</span></span> <span data-ttu-id="13c0d-186">Требуется ли получить коэффициент окупаемости инвестиций для развернутого SBCs?</span><span class="sxs-lookup"><span data-stu-id="13c0d-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="13c0d-187">A. Да и нет</span><span class="sxs-lookup"><span data-stu-id="13c0d-187">A. Yes and No</span></span>  

- <span data-ttu-id="13c0d-188">Стоит.</span><span class="sxs-lookup"><span data-stu-id="13c0d-188">Q.</span></span> <span data-ttu-id="13c0d-189">Доступно ли в этом регионе тарифный план по КОММУТИРУЕМой телефонной связи Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="13c0d-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="13c0d-190">А.</span><span class="sxs-lookup"><span data-stu-id="13c0d-190">A. No</span></span> 

<span data-ttu-id="13c0d-191">В соответствии с ответами на вопросы компания Contoso решила следующее:</span><span class="sxs-lookup"><span data-stu-id="13c0d-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="13c0d-192">Для устаревших пользователей телефонной связи, которые будут включены для прямой маршрутизации, компания Contoso переносит номера из магистральной TDM на магистраль SIP для SBC, так как SBC сертифицирован для прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="13c0d-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="13c0d-193">Для поддержки подмножества пользователей, переходящих в телефонную систему и возможной непрерывной маршрутизации в устаревшей системе, устаревшая система телефонии была настроена как следующий прыжок для SBC.</span><span class="sxs-lookup"><span data-stu-id="13c0d-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="13c0d-194">Кроме того, для включения режима поведения пользователей и удаления зависимости для набора номера между сайтами, предоставленного компанией Contoso, для использования Teams во всех внутренних звонках.</span><span class="sxs-lookup"><span data-stu-id="13c0d-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="13c0d-195">На приведенных ниже схемах показана исходная версия Skype для бизнеса Enterprise и устаревшая система телефонной связи, а также миграция в смешанное развертывание с помощью Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="13c0d-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="13c0d-196">**Исходное смешанное развертывание** 
 ![ Схема, показывающая состояние Before](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="13c0d-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="13c0d-197">**Смешанное развертывание с прямой маршрутизацией** 
 ![ Схема, показывающая состояние Before](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="13c0d-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="13c0d-198">Планы звонков</span><span class="sxs-lookup"><span data-stu-id="13c0d-198">Calling Plans</span></span>

<span data-ttu-id="13c0d-199">Чтобы определить требования к конфигурации для планов звонков, компания Contoso проверила [основные решения по развертыванию плана звонков](calling-plan-landing-page.md#core-deployment-decisions).</span><span class="sxs-lookup"><span data-stu-id="13c0d-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="13c0d-200">Полученные решения выполнены:</span><span class="sxs-lookup"><span data-stu-id="13c0d-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="13c0d-201">Стоит.</span><span class="sxs-lookup"><span data-stu-id="13c0d-201">Q.</span></span> <span data-ttu-id="13c0d-202">Нужно ли пользователям использовать международные звонки?</span><span class="sxs-lookup"><span data-stu-id="13c0d-202">Do my users need international calling?</span></span><br> <span data-ttu-id="13c0d-203">О. Да</span><span class="sxs-lookup"><span data-stu-id="13c0d-203">A. Yes</span></span> 

- <span data-ttu-id="13c0d-204">Стоит.</span><span class="sxs-lookup"><span data-stu-id="13c0d-204">Q.</span></span> <span data-ttu-id="13c0d-205">Есть ли у моих пользователей прямой телефонный номер?</span><span class="sxs-lookup"><span data-stu-id="13c0d-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="13c0d-206">А. не сегодня.</span><span class="sxs-lookup"><span data-stu-id="13c0d-206">A. Not today.</span></span> <span data-ttu-id="13c0d-207">Все включенные пользователи получат сообщение о том, что это сделал.</span><span class="sxs-lookup"><span data-stu-id="13c0d-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="13c0d-208">Стоит.</span><span class="sxs-lookup"><span data-stu-id="13c0d-208">Q.</span></span> <span data-ttu-id="13c0d-209">Нужно ли маскировать или отключать идентификатор вызывающего абонента?</span><span class="sxs-lookup"><span data-stu-id="13c0d-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="13c0d-210">О. идентификатор вызывающего абонента для пользователя будет маскироваться на местный номер для contoso.</span><span class="sxs-lookup"><span data-stu-id="13c0d-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="13c0d-211">Прямая маршрутизация</span><span class="sxs-lookup"><span data-stu-id="13c0d-211">Direct Routing</span></span>

<span data-ttu-id="13c0d-212">Компания Contoso проIgniteа в Skype все возможности Office 365, в том числе те, которые доступны в телефонной системе и прямом маршруте.</span><span class="sxs-lookup"><span data-stu-id="13c0d-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="13c0d-213">Технические лидеры и архитекторы использовали руководство, предоставленное в Ignite 2019, чтобы определить их направление.</span><span class="sxs-lookup"><span data-stu-id="13c0d-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="13c0d-214">Использованные сеансы с ключом:</span><span class="sxs-lookup"><span data-stu-id="13c0d-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="13c0d-215">Планирование успеха в Microsoft Teams Direct Routing</span><span class="sxs-lookup"><span data-stu-id="13c0d-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="13c0d-216">Обновления для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="13c0d-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="13c0d-217">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="13c0d-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="13c0d-218">Сайты планов звонков</span><span class="sxs-lookup"><span data-stu-id="13c0d-218">Calling Plans sites</span></span>

<span data-ttu-id="13c0d-219">Чтобы получить лицензии и назначить номера телефонов пользователям, компания Contoso продемонстрирует действия, описанные в разделе [Настройка планов звонков](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="13c0d-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="13c0d-220">Из-за количества пользователей, которым необходимо назначить номера телефонов, компания Contoso решила использовать PowerShell для назначения номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="13c0d-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="13c0d-221">Чтобы научиться назначать номера с помощью PowerShell, &mdash; а также других параметров &mdash; компания Contoso использовала [Общие сведения о Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="13c0d-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="13c0d-222">Прямые сайты маршрутизации</span><span class="sxs-lookup"><span data-stu-id="13c0d-222">Direct Routing sites</span></span>

<span data-ttu-id="13c0d-223">Чтобы подключить локальную инфраструктуру телефонной связи Contoso к Microsoft Teams, администратор Contoso проверил инструкции по [настройке Direct Routing](direct-routing-configure.md) и проверки маршрутизации видеорассылки [в Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) .</span><span class="sxs-lookup"><span data-stu-id="13c0d-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="13c0d-224">Компания Contoso также ссылалась на документацию по развертыванию прямой маршрутизации, предоставленную поставщиком SBC.</span><span class="sxs-lookup"><span data-stu-id="13c0d-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="13c0d-225">После того, как настроена прямая маршрутизация между SBC и телефонной системой Microsoft, для Contoso требуется проверка конфигурации.</span><span class="sxs-lookup"><span data-stu-id="13c0d-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="13c0d-226">Для этого администраторы Contoso использовали клиент тестеров SIP, который был описан в разделе [обновления для прямого маршрутизации сеансов на Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="13c0d-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="13c0d-227">Клиентский сценарий и документация тестера SIP скачаны из сценария PowerShell, чтобы протестировать соединения с контроллером границ для однонаправленных сеансов маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="13c0d-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="13c0d-228">Оптимизация локальных файлов мультимедиа</span><span class="sxs-lookup"><span data-stu-id="13c0d-228">Local Media Optimization</span></span>

<span data-ttu-id="13c0d-229">Компания Contoso высмотрела возможность использовать локальную оптимизацию мультимедиа в разных регионах земного шара.</span><span class="sxs-lookup"><span data-stu-id="13c0d-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="13c0d-230">Поддерживаемые сценарии для Contoso описаны в разделе [Оптимизация локальных файлов мультимедиа для прямой маршрутизации](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="13c0d-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="13c0d-231">Настройка оптимизации локальных файлов мультимедиа была выполнена с помощью руководства, полученного от поставщика SBC и от корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="13c0d-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="13c0d-232">Ниже приведены этапы настройки для локальной оптимизации мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="13c0d-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="13c0d-233">Настройка пользователей и сайтов SBC</span><span class="sxs-lookup"><span data-stu-id="13c0d-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="13c0d-234">Настройка SBC в соответствии с спецификацией поставщика SBC</span><span class="sxs-lookup"><span data-stu-id="13c0d-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="13c0d-235">Добавление внешних надежных IP-адресов к каждому сайту, используемому для оптимизации локального мультимедиа</span><span class="sxs-lookup"><span data-stu-id="13c0d-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="13c0d-236">Определение топологии сети</span><span class="sxs-lookup"><span data-stu-id="13c0d-236">Define the network topology</span></span> 

- <span data-ttu-id="13c0d-237">Определение топологии виртуальной сети</span><span class="sxs-lookup"><span data-stu-id="13c0d-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="13c0d-238">Определение режима: всегда обходить или только для локальных пользователей</span><span class="sxs-lookup"><span data-stu-id="13c0d-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="13c0d-239">Вопросы работы в сети</span><span class="sxs-lookup"><span data-stu-id="13c0d-239">Networking considerations</span></span>

<span data-ttu-id="13c0d-240">В компании Contoso существовало несколько пользователей, которым требовалось работать в течение длительного периода времени после включения телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="13c0d-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="13c0d-241">Пользователи, использующие VPN для доступа к определенным строкам бизнес-приложений.</span><span class="sxs-lookup"><span data-stu-id="13c0d-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="13c0d-242">В сети VPN пользователи телефонной системы попытались снизить качество связи.</span><span class="sxs-lookup"><span data-stu-id="13c0d-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="13c0d-243">Для устранения проблемы с качеством компания Contoso реализовала разделение VPN, которая разрешила трафик Office 365 для прохождения через Интернет, пока подключение к внутренним приложениям осталось в сети VPN.</span><span class="sxs-lookup"><span data-stu-id="13c0d-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="13c0d-244">Для реализации разделения с разделением VPN компания Contoso применяет руководство по [реализации разделения VPN-туннелей для Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span><span class="sxs-lookup"><span data-stu-id="13c0d-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

 





