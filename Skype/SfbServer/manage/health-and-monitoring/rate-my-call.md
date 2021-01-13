---
title: Rate my Call in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: Сводка. Сведения о функции "Оценить мой звонок" в Skype для бизнеса Server.
ms.openlocfilehash: 597a8213576e7aa2316ace68ed91288475df2a0d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814339"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="293ca-103">Rate my Call in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="293ca-103">Rate my Call in Skype for Business Server</span></span>

<span data-ttu-id="293ca-104">**Сводка:** Learn about the Rate My Call feature in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="293ca-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>

<span data-ttu-id="293ca-105">Функция оценки моего звонка — это новая функция в клиентах Skype для бизнеса 2015 и 2016 в Windows, которая позволяет предприятиям получать отзывы от своих конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="293ca-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>

<span data-ttu-id="293ca-106">Окно оценки моего звонка предлагает систему оценки "звездочка" и предопределенные маркеры для аудио- и видеозвонков.</span><span class="sxs-lookup"><span data-stu-id="293ca-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="293ca-107">Кроме того, администраторы могут включить настраиваемые поля для предоставления отзывов.</span><span class="sxs-lookup"><span data-stu-id="293ca-107">In addition, administrators can enable a custom field to provide feedback.</span></span>

<span data-ttu-id="293ca-108">Собранные данные о скорости моего звонка в настоящее время не включаются ни в один из существующих отчетов мониторинга, но они содержат отдельный отчет мониторинга.</span><span class="sxs-lookup"><span data-stu-id="293ca-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="293ca-109">Данные собираются в SQL таблицах, к ним можно получить доступ с помощью SQL запросов.</span><span class="sxs-lookup"><span data-stu-id="293ca-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>

## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="293ca-110">Оцените необходимые условия для вызова</span><span class="sxs-lookup"><span data-stu-id="293ca-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="293ca-111">Прежде чем пользователи в развертывании Skype для бизнеса Server смогут получить доступ к функциям "Оценить мой звонок", необходимо развернуть и настроить следующий набор компонентов:</span><span class="sxs-lookup"><span data-stu-id="293ca-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>

-  <span data-ttu-id="293ca-112">Необходимо установить Skype для бизнеса Server (версия 9160 или выше).</span><span class="sxs-lookup"><span data-stu-id="293ca-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>

- <span data-ttu-id="293ca-113">Попросите пользователей установить и обновить skype для бизнеса до последней версии, а также попросить их использовать пользовательский интерфейс Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="293ca-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>

- <span data-ttu-id="293ca-114">Пользователи должны быть в пуле переднего сервера Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="293ca-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>

- <span data-ttu-id="293ca-115">База данных мониторинга Skype для бизнеса Server должна быть развернута и связана с пулами Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="293ca-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>

- <span data-ttu-id="293ca-116">Рекомендуется развернуть панель мониторинга качества вызовов (CQD).</span><span class="sxs-lookup"><span data-stu-id="293ca-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>

## <a name="configure-rate-my-call"></a><span data-ttu-id="293ca-117">Настройка скорости звонка</span><span class="sxs-lookup"><span data-stu-id="293ca-117">Configure Rate my Call</span></span>

<span data-ttu-id="293ca-118">Функция "Оценить мой звонок" включена по умолчанию в политике клиента со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="293ca-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>

- <span data-ttu-id="293ca-119">Rate My Call Display Percentage - 10%</span><span class="sxs-lookup"><span data-stu-id="293ca-119">Rate My Call Display Percentage - 10%</span></span>

- <span data-ttu-id="293ca-120">Оценить мой звонок, разрешить настраиваемый отзыв пользователя — отключено</span><span class="sxs-lookup"><span data-stu-id="293ca-120">Rate My Call Allow Custom User Feedback - disabled</span></span>

<span data-ttu-id="293ca-121">Для принятия базовых функций не требуется никаких действий, но если вы хотите получить обратную связь, ее необходимо включить отдельно.</span><span class="sxs-lookup"><span data-stu-id="293ca-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="293ca-122">Следующий Windows PowerShell является примером включения настраиваемой обратной связи конечного пользователя и изменения интервала с 10 % до 80 %.</span><span class="sxs-lookup"><span data-stu-id="293ca-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="293ca-123">Доступ к данным о скорости моего звонка</span><span class="sxs-lookup"><span data-stu-id="293ca-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="293ca-124">Данные пользователей собираются в двух таблицах базы данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="293ca-124">Data from users is collected in two tables in the monitoring database.</span></span>

 <span data-ttu-id="293ca-125">**[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** - Эта таблица содержит результаты опроса маркеров конечными пользователями.</span><span class="sxs-lookup"><span data-stu-id="293ca-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>

 <span data-ttu-id="293ca-126">**[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** — эта таблица содержит определения маркеров.</span><span class="sxs-lookup"><span data-stu-id="293ca-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>

<span data-ttu-id="293ca-127">Определения маркеров кодироваться следующим образом:</span><span class="sxs-lookup"><span data-stu-id="293ca-127">Token definitions are coded as follows:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="293ca-128">1 </span><span class="sxs-lookup"><span data-stu-id="293ca-128">1</span></span>  <br/> |<span data-ttu-id="293ca-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="293ca-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="293ca-130">2 </span><span class="sxs-lookup"><span data-stu-id="293ca-130">2</span></span>  <br/> | <span data-ttu-id="293ca-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="293ca-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="293ca-132">3 </span><span class="sxs-lookup"><span data-stu-id="293ca-132">3</span></span>  <br/> | <span data-ttu-id="293ca-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="293ca-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="293ca-134">4 </span><span class="sxs-lookup"><span data-stu-id="293ca-134">4</span></span>  <br/> |<span data-ttu-id="293ca-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="293ca-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="293ca-136">5 </span><span class="sxs-lookup"><span data-stu-id="293ca-136">5</span></span>  <br/> |<span data-ttu-id="293ca-137">Эхо</span><span class="sxs-lookup"><span data-stu-id="293ca-137">Echo</span></span>  <br/> |
|<span data-ttu-id="293ca-138">21</span><span class="sxs-lookup"><span data-stu-id="293ca-138">21</span></span>  <br/> | <span data-ttu-id="293ca-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="293ca-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="293ca-140">22</span><span class="sxs-lookup"><span data-stu-id="293ca-140">22</span></span>  <br/> | <span data-ttu-id="293ca-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="293ca-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="293ca-142">23</span><span class="sxs-lookup"><span data-stu-id="293ca-142">23</span></span>  <br/> | <span data-ttu-id="293ca-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="293ca-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="293ca-144">24</span><span class="sxs-lookup"><span data-stu-id="293ca-144">24</span></span>  <br/> | <span data-ttu-id="293ca-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="293ca-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="293ca-146">25</span><span class="sxs-lookup"><span data-stu-id="293ca-146">25</span></span>  <br/> | <span data-ttu-id="293ca-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="293ca-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="293ca-148">101</span><span class="sxs-lookup"><span data-stu-id="293ca-148">101</span></span>  <br/> |<span data-ttu-id="293ca-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="293ca-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="293ca-150">102</span><span class="sxs-lookup"><span data-stu-id="293ca-150">102</span></span>  <br/> |<span data-ttu-id="293ca-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="293ca-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="293ca-152">103</span><span class="sxs-lookup"><span data-stu-id="293ca-152">103</span></span>  <br/> |<span data-ttu-id="293ca-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="293ca-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="293ca-154">104</span><span class="sxs-lookup"><span data-stu-id="293ca-154">104</span></span>  <br/> |<span data-ttu-id="293ca-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="293ca-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="293ca-156">105</span><span class="sxs-lookup"><span data-stu-id="293ca-156">105</span></span>  <br/> |<span data-ttu-id="293ca-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="293ca-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="293ca-158">106</span><span class="sxs-lookup"><span data-stu-id="293ca-158">106</span></span>  <br/> |<span data-ttu-id="293ca-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="293ca-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="293ca-160">107</span><span class="sxs-lookup"><span data-stu-id="293ca-160">107</span></span>  <br/> |<span data-ttu-id="293ca-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="293ca-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="293ca-162">108</span><span class="sxs-lookup"><span data-stu-id="293ca-162">108</span></span>  <br/> |<span data-ttu-id="293ca-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="293ca-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="293ca-164">109</span><span class="sxs-lookup"><span data-stu-id="293ca-164">109</span></span>  <br/> |<span data-ttu-id="293ca-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="293ca-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="293ca-166">201</span><span class="sxs-lookup"><span data-stu-id="293ca-166">201</span></span>  <br/> |<span data-ttu-id="293ca-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="293ca-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="293ca-168">202</span><span class="sxs-lookup"><span data-stu-id="293ca-168">202</span></span>  <br/> |<span data-ttu-id="293ca-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="293ca-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="293ca-170">203</span><span class="sxs-lookup"><span data-stu-id="293ca-170">203</span></span>  <br/> |<span data-ttu-id="293ca-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="293ca-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="293ca-172">204</span><span class="sxs-lookup"><span data-stu-id="293ca-172">204</span></span>  <br/> |<span data-ttu-id="293ca-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="293ca-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="293ca-174">205</span><span class="sxs-lookup"><span data-stu-id="293ca-174">205</span></span>  <br/> |<span data-ttu-id="293ca-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="293ca-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="293ca-176">206</span><span class="sxs-lookup"><span data-stu-id="293ca-176">206</span></span>  <br/> |<span data-ttu-id="293ca-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="293ca-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="293ca-178">207</span><span class="sxs-lookup"><span data-stu-id="293ca-178">207</span></span>  <br/> |<span data-ttu-id="293ca-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="293ca-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="293ca-180">208</span><span class="sxs-lookup"><span data-stu-id="293ca-180">208</span></span>  <br/> |<span data-ttu-id="293ca-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="293ca-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="293ca-182">301</span><span class="sxs-lookup"><span data-stu-id="293ca-182">301</span></span>  <br/> |<span data-ttu-id="293ca-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="293ca-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="293ca-184">401</span><span class="sxs-lookup"><span data-stu-id="293ca-184">401</span></span>  <br/> |<span data-ttu-id="293ca-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="293ca-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="293ca-186">402</span><span class="sxs-lookup"><span data-stu-id="293ca-186">402</span></span>  <br/> |<span data-ttu-id="293ca-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="293ca-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="293ca-188">403</span><span class="sxs-lookup"><span data-stu-id="293ca-188">403</span></span>  <br/> |<span data-ttu-id="293ca-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="293ca-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="293ca-190">404</span><span class="sxs-lookup"><span data-stu-id="293ca-190">404</span></span>  <br/> |<span data-ttu-id="293ca-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="293ca-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="293ca-192">405</span><span class="sxs-lookup"><span data-stu-id="293ca-192">405</span></span>  <br/> |<span data-ttu-id="293ca-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="293ca-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="293ca-194">406</span><span class="sxs-lookup"><span data-stu-id="293ca-194">406</span></span>  <br/> |<span data-ttu-id="293ca-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="293ca-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="293ca-196">407</span><span class="sxs-lookup"><span data-stu-id="293ca-196">407</span></span>  <br/> |<span data-ttu-id="293ca-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="293ca-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="293ca-198">408</span><span class="sxs-lookup"><span data-stu-id="293ca-198">408</span></span>  <br/> |<span data-ttu-id="293ca-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="293ca-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="293ca-200">501</span><span class="sxs-lookup"><span data-stu-id="293ca-200">501</span></span>  <br/> |<span data-ttu-id="293ca-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="293ca-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="293ca-202">502</span><span class="sxs-lookup"><span data-stu-id="293ca-202">502</span></span>  <br/> |<span data-ttu-id="293ca-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="293ca-203">Reliabilty_Invite</span></span>  <br/> |

 <span data-ttu-id="293ca-204">**[QoeMetrics]. [dbo]. [CallQualityFeedback]** В этой таблице содержатся результаты опроса по результатам голосования "Star" и отзывы клиентов, если они включены.</span><span class="sxs-lookup"><span data-stu-id="293ca-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>

<span data-ttu-id="293ca-205">Данные из таблиц могут быть вызваны с помощью запроса **\* select from [Table.Name]** или с помощью Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="293ca-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>

<span data-ttu-id="293ca-206">Можно использовать SQL следующие запросы:</span><span class="sxs-lookup"><span data-stu-id="293ca-206">The following SQL queries can be used:</span></span>

 <span data-ttu-id="293ca-207">**Audio**</span><span class="sxs-lookup"><span data-stu-id="293ca-207">**Audio**</span></span>

```SQL
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

 <span data-ttu-id="293ca-208">**Video**</span><span class="sxs-lookup"><span data-stu-id="293ca-208">**Video**</span></span>

```SQL
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

## <a name="updating-token-definitions"></a><span data-ttu-id="293ca-209">Обновление определений маркеров</span><span class="sxs-lookup"><span data-stu-id="293ca-209">Updating Token Definitions</span></span>

<span data-ttu-id="293ca-210">Последние клиенты Skype для бизнеса сообщают новые коды маркеров проблем (100), которые могут не присутствовать в \> вашем [QoeMetrics].[ dbo]. Таблица [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="293ca-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="293ca-211">Чтобы обновить таблицу базы данных с использованием последних определений маркеров, приведенную ниже SQL можно выполнить в базе данных мониторинга с помощью Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="293ca-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="293ca-212">Эта команда заменит все записи в [QoeMetrics]. [dbo]. Таблица [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="293ca-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>

```SQL
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


