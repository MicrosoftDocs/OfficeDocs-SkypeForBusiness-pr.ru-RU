---
title: Оцените Мои звонка в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Сводка: Сведения о скорости личных вызова функции в Скайп для Business Server.'
ms.openlocfilehash: 737d6a71f6880139d558d601a14d8f76c61d80f2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20989065"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="ee03e-103">Оцените Мои звонка в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="ee03e-103">Rate my Call in Skype for Business Server</span></span>
 
<span data-ttu-id="ee03e-104">**Сводка:** Сведения о скорости личных вызова функции в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="ee03e-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="ee03e-105">Скорость личных звонок был компонента в Скайп для 2015 бизнеса и клиентов 2016 в Windows, который предоставляет способ получить свои отзывы и предложения от их конечных пользователей предприятия.</span><span class="sxs-lookup"><span data-stu-id="ee03e-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>
  
<span data-ttu-id="ee03e-106">Окно личных вызова скорость предлагает систему «звездочка» оценок и предустановленные токены для вызовов, аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="ee03e-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="ee03e-107">Кроме того администраторы могут разрешить настраиваемого поля оставить отзыв.</span><span class="sxs-lookup"><span data-stu-id="ee03e-107">In addition, administrators can enable a custom field to provide feedback.</span></span>
  
<span data-ttu-id="ee03e-108">Собранные данные оценки вызова в настоящее время не включаются ни в один из существующих ответов мониторинга, но имеет отдельный отчет мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ee03e-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="ee03e-109">Сбор данных в таблицах SQL, которые можно получить, запустив SQL-запросов.</span><span class="sxs-lookup"><span data-stu-id="ee03e-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>
  
## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="ee03e-110">Требования функции оценки вызова</span><span class="sxs-lookup"><span data-stu-id="ee03e-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="ee03e-111">Пользователи в вашей Скайп для развертывания Business Server может получить доступ к скорости личных вызова функциональные возможности, необходимо развернута и настроена следующего набора компонентов:</span><span class="sxs-lookup"><span data-stu-id="ee03e-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>
  
-  <span data-ttu-id="ee03e-112">Необходимо иметь Скайп для установки сервера Business (версия 9160 или выше).</span><span class="sxs-lookup"><span data-stu-id="ee03e-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>
    
- <span data-ttu-id="ee03e-113">У пользователей Установка и обновление до последней версии Скайп для бизнеса и также попросить использовать Скайп для пользовательского интерфейса бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ee03e-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>
    
- <span data-ttu-id="ee03e-114">Пользователи должны быть размещены на Скайп для пула переднего плана Business Server.</span><span class="sxs-lookup"><span data-stu-id="ee03e-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>
    
- <span data-ttu-id="ee03e-115">Необходимо иметь Скайп для сервера базы данных мониторинга развернуты и связанный вашей Скайп для пулов Business Server.</span><span class="sxs-lookup"><span data-stu-id="ee03e-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>
    
- <span data-ttu-id="ee03e-116">Рекомендуется развернуть панель мониторинга качества вызовов (CQD).</span><span class="sxs-lookup"><span data-stu-id="ee03e-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>
    
## <a name="configure-rate-my-call"></a><span data-ttu-id="ee03e-117">Настройка функции оценки вызова</span><span class="sxs-lookup"><span data-stu-id="ee03e-117">Configure Rate my Call</span></span>

<span data-ttu-id="ee03e-118">Частота личных вызова она включена по умолчанию в политике клиента со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="ee03e-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>
  
- <span data-ttu-id="ee03e-119">Оцените Мои процент отображения вызовов - 10%</span><span class="sxs-lookup"><span data-stu-id="ee03e-119">Rate My Call Display Percentage - 10%</span></span>
    
- <span data-ttu-id="ee03e-120">Оцените Мои вызова разрешить Custom отзывов и предложений — этот параметр отключен</span><span class="sxs-lookup"><span data-stu-id="ee03e-120">Rate My Call Allow Custom User Feedback - disabled</span></span>
    
<span data-ttu-id="ee03e-121">Нет никаких действий, необходимых для реализации базовой функции, тем не менее, но если требуется настраиваемых свои отзывы и предложения необходимо включить отдельно.</span><span class="sxs-lookup"><span data-stu-id="ee03e-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="ee03e-122">Следующий командлет Windows PowerShell — это пример Включение настраиваемого конечного пользователя свои отзывы и предложения и изменение интервала от 10% до 80%.</span><span class="sxs-lookup"><span data-stu-id="ee03e-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>
  
```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="ee03e-123">Доступ к данным оценки вызова</span><span class="sxs-lookup"><span data-stu-id="ee03e-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="ee03e-124">Сбор данных от пользователей в двух таблиц в базе данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ee03e-124">Data from users is collected in two tables in the monitoring database.</span></span>
  
 <span data-ttu-id="ee03e-125">**[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** -в этой таблице содержатся результаты опроса маркеров конечными пользователями.</span><span class="sxs-lookup"><span data-stu-id="ee03e-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>
  
 <span data-ttu-id="ee03e-126">**[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** -в этой таблице содержится маркеров определений.</span><span class="sxs-lookup"><span data-stu-id="ee03e-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>
  
<span data-ttu-id="ee03e-127">Определения маркеров имеют следующую кодировку:</span><span class="sxs-lookup"><span data-stu-id="ee03e-127">Token definitions are coded as follows:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ee03e-128">1</span><span class="sxs-lookup"><span data-stu-id="ee03e-128">1</span></span>  <br/> |<span data-ttu-id="ee03e-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="ee03e-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="ee03e-130">2</span><span class="sxs-lookup"><span data-stu-id="ee03e-130">2</span></span>  <br/> | <span data-ttu-id="ee03e-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="ee03e-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="ee03e-132">3</span><span class="sxs-lookup"><span data-stu-id="ee03e-132">3</span></span>  <br/> | <span data-ttu-id="ee03e-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="ee03e-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="ee03e-134">4</span><span class="sxs-lookup"><span data-stu-id="ee03e-134">4</span></span>  <br/> |<span data-ttu-id="ee03e-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="ee03e-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="ee03e-136">5</span><span class="sxs-lookup"><span data-stu-id="ee03e-136">5</span></span>  <br/> |<span data-ttu-id="ee03e-137">Эхо</span><span class="sxs-lookup"><span data-stu-id="ee03e-137">Echo</span></span>  <br/> |
|<span data-ttu-id="ee03e-138">21</span><span class="sxs-lookup"><span data-stu-id="ee03e-138">21</span></span>  <br/> | <span data-ttu-id="ee03e-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="ee03e-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="ee03e-140">22</span><span class="sxs-lookup"><span data-stu-id="ee03e-140">22</span></span>  <br/> | <span data-ttu-id="ee03e-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="ee03e-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="ee03e-142">23</span><span class="sxs-lookup"><span data-stu-id="ee03e-142">23</span></span>  <br/> | <span data-ttu-id="ee03e-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="ee03e-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="ee03e-144">24</span><span class="sxs-lookup"><span data-stu-id="ee03e-144">24</span></span>  <br/> | <span data-ttu-id="ee03e-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="ee03e-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="ee03e-146">25</span><span class="sxs-lookup"><span data-stu-id="ee03e-146">25</span></span>  <br/> | <span data-ttu-id="ee03e-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="ee03e-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="ee03e-148">101</span><span class="sxs-lookup"><span data-stu-id="ee03e-148">101</span></span>  <br/> |<span data-ttu-id="ee03e-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="ee03e-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="ee03e-150">102</span><span class="sxs-lookup"><span data-stu-id="ee03e-150">102</span></span>  <br/> |<span data-ttu-id="ee03e-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="ee03e-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="ee03e-152">103</span><span class="sxs-lookup"><span data-stu-id="ee03e-152">103</span></span>  <br/> |<span data-ttu-id="ee03e-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="ee03e-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="ee03e-154">104</span><span class="sxs-lookup"><span data-stu-id="ee03e-154">104</span></span>  <br/> |<span data-ttu-id="ee03e-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="ee03e-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="ee03e-156">105</span><span class="sxs-lookup"><span data-stu-id="ee03e-156">105</span></span>  <br/> |<span data-ttu-id="ee03e-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="ee03e-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="ee03e-158">106</span><span class="sxs-lookup"><span data-stu-id="ee03e-158">106</span></span>  <br/> |<span data-ttu-id="ee03e-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="ee03e-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="ee03e-160">107</span><span class="sxs-lookup"><span data-stu-id="ee03e-160">107</span></span>  <br/> |<span data-ttu-id="ee03e-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="ee03e-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="ee03e-162">108</span><span class="sxs-lookup"><span data-stu-id="ee03e-162">108</span></span>  <br/> |<span data-ttu-id="ee03e-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="ee03e-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="ee03e-164">109</span><span class="sxs-lookup"><span data-stu-id="ee03e-164">109</span></span>  <br/> |<span data-ttu-id="ee03e-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="ee03e-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="ee03e-166">201</span><span class="sxs-lookup"><span data-stu-id="ee03e-166">201</span></span>  <br/> |<span data-ttu-id="ee03e-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="ee03e-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="ee03e-168">202</span><span class="sxs-lookup"><span data-stu-id="ee03e-168">202</span></span>  <br/> |<span data-ttu-id="ee03e-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="ee03e-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="ee03e-170">203</span><span class="sxs-lookup"><span data-stu-id="ee03e-170">203</span></span>  <br/> |<span data-ttu-id="ee03e-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="ee03e-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="ee03e-172">204</span><span class="sxs-lookup"><span data-stu-id="ee03e-172">204</span></span>  <br/> |<span data-ttu-id="ee03e-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="ee03e-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="ee03e-174">205</span><span class="sxs-lookup"><span data-stu-id="ee03e-174">205</span></span>  <br/> |<span data-ttu-id="ee03e-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="ee03e-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="ee03e-176">206</span><span class="sxs-lookup"><span data-stu-id="ee03e-176">206</span></span>  <br/> |<span data-ttu-id="ee03e-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="ee03e-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="ee03e-178">207</span><span class="sxs-lookup"><span data-stu-id="ee03e-178">207</span></span>  <br/> |<span data-ttu-id="ee03e-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="ee03e-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="ee03e-180">208</span><span class="sxs-lookup"><span data-stu-id="ee03e-180">208</span></span>  <br/> |<span data-ttu-id="ee03e-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="ee03e-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="ee03e-182">301</span><span class="sxs-lookup"><span data-stu-id="ee03e-182">301</span></span>  <br/> |<span data-ttu-id="ee03e-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="ee03e-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="ee03e-184">401</span><span class="sxs-lookup"><span data-stu-id="ee03e-184">401</span></span>  <br/> |<span data-ttu-id="ee03e-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="ee03e-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="ee03e-186">402</span><span class="sxs-lookup"><span data-stu-id="ee03e-186">402</span></span>  <br/> |<span data-ttu-id="ee03e-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="ee03e-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="ee03e-188">403</span><span class="sxs-lookup"><span data-stu-id="ee03e-188">403</span></span>  <br/> |<span data-ttu-id="ee03e-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="ee03e-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="ee03e-190">404</span><span class="sxs-lookup"><span data-stu-id="ee03e-190">404</span></span>  <br/> |<span data-ttu-id="ee03e-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="ee03e-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="ee03e-192">405</span><span class="sxs-lookup"><span data-stu-id="ee03e-192">405</span></span>  <br/> |<span data-ttu-id="ee03e-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="ee03e-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="ee03e-194">406</span><span class="sxs-lookup"><span data-stu-id="ee03e-194">406</span></span>  <br/> |<span data-ttu-id="ee03e-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="ee03e-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="ee03e-196">407</span><span class="sxs-lookup"><span data-stu-id="ee03e-196">407</span></span>  <br/> |<span data-ttu-id="ee03e-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="ee03e-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="ee03e-198">408</span><span class="sxs-lookup"><span data-stu-id="ee03e-198">408</span></span>  <br/> |<span data-ttu-id="ee03e-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="ee03e-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="ee03e-200">501</span><span class="sxs-lookup"><span data-stu-id="ee03e-200">501</span></span>  <br/> |<span data-ttu-id="ee03e-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="ee03e-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="ee03e-202">502</span><span class="sxs-lookup"><span data-stu-id="ee03e-202">502</span></span>  <br/> |<span data-ttu-id="ee03e-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="ee03e-203">Reliabilty_Invite</span></span>  <br/> |
   
 <span data-ttu-id="ee03e-204">**[QoeMetrics]. [dbo]. [CallQualityFeedback]** В этой таблице содержатся результаты опроса «Звезда» голосования и отзывы пользователей, если этот параметр включен.</span><span class="sxs-lookup"><span data-stu-id="ee03e-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>
  
<span data-ttu-id="ee03e-205">Данные из таблиц, которые могут вызываться с помощью **выберите \* из [Table.Name]** запроса или с помощью Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="ee03e-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>
  
<span data-ttu-id="ee03e-206">Можно использовать следующие запросы SQL:</span><span class="sxs-lookup"><span data-stu-id="ee03e-206">The following SQL queries can be used:</span></span>
  
 <span data-ttu-id="ee03e-207">**Аудио**</span><span class="sxs-lookup"><span data-stu-id="ee03e-207">**Audio**</span></span>
  
```
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
 
```

 <span data-ttu-id="ee03e-208">**Видео**</span><span class="sxs-lookup"><span data-stu-id="ee03e-208">**Video**</span></span>
  
```
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a><span data-ttu-id="ee03e-209">Обновление маркеров определений</span><span class="sxs-lookup"><span data-stu-id="ee03e-209">Updating Token Definitions</span></span>

<span data-ttu-id="ee03e-210">Новый маркер проблема идентификаторы сообщить о последних Скайп пользователей (\> 100), которая не может быть представлен в [QoeMetrics]. [dbo]. Таблица [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="ee03e-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="ee03e-211">Для обновления таблицы базы данных с последними маркеров определений ниже SQL команду можно выполнить на базу данных мониторинга с помощью Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="ee03e-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="ee03e-212">Эта команда будет заменен всех записей в [QoeMetrics]. [dbo]. Таблица [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="ee03e-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>
  
```
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');

```


