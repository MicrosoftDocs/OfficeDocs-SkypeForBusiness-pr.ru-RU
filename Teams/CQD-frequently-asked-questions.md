---
title: Панель мониторинга качества звонка (CQD) — вопросы и ответы
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Ознакомьтесь с часто задаваемой информационной панелью качества звонка (CQD) и ответами на часто задаваемые вопросы о Microsoft Teams.
ms.openlocfilehash: 8ad0a1745799194ec11284f8f7aaabd76bd30d05
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584028"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a><span data-ttu-id="96019-103">Панель мониторинга качества звонка (CQD) — вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="96019-103">Call Quality Dashboard (CQD) Frequently asked questions (FAQ)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="96019-104">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="96019-104">Frequently asked questions</span></span>

[<span data-ttu-id="96019-105">Почему CQD пометит звонок как "Хороший", если одному или одному или несколько участников собрания не понственно?</span><span class="sxs-lookup"><span data-stu-id="96019-105">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[<span data-ttu-id="96019-106">Почему при звонках и подсчете пользователей между показателями и для получения наиболее точных объемов разницы между звонками и пользователями может быть до 0,2%? </span><span class="sxs-lookup"><span data-stu-id="96019-106">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes? </span></span>](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[<span data-ttu-id="96019-107">Почему данные CQD из Skype для бизнеса отличаются от данных CQD в Teams? </span><span class="sxs-lookup"><span data-stu-id="96019-107">Why is CQD data from Skype for Business different than CQD data from Teams? </span></span>](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[<span data-ttu-id="96019-108">Почему я не вижу EUII в CQD?</span><span class="sxs-lookup"><span data-stu-id="96019-108">Why can't I see EUII in CQD?</span></span>](#why-cant-i-see-euii-in-cqd)

[<span data-ttu-id="96019-109">Почему при фильтрации только по Teams я вижу сведения о Skype для бизнеса в CQD?</span><span class="sxs-lookup"><span data-stu-id="96019-109">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a><span data-ttu-id="96019-110">Почему CQD пометит звонок как "Хороший", если одному или одному или несколько участников собрания не понственно?</span><span class="sxs-lookup"><span data-stu-id="96019-110">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>

<span data-ttu-id="96019-111">Ознакомьтесь с правилами классификации потоков, которые используются В CQD. [](stream-classification-in-call-quality-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="96019-111">Check out the rules CQD uses for [stream classification](stream-classification-in-call-quality-dashboard.md).</span></span>
 
<span data-ttu-id="96019-112">Для аудиопотоков любой из 5 классификаторов, которые рассчитываются для среднего значения длительности звонка, может быть задан в "хороших" параметрах.</span><span class="sxs-lookup"><span data-stu-id="96019-112">For audio streams, any of the 5 classifiers, which are calculated for the average based on the length of the call, could all be within "good" parameters.</span></span> <span data-ttu-id="96019-113">Это не значит, что пользователи не озвучили проблемы со снижением качества звука, статическим сбоем или его возникновением.</span><span class="sxs-lookup"><span data-stu-id="96019-113">It doesn't mean the users didn't experience something that contributed to an audio drop out, static, or glitch.</span></span> 

<span data-ttu-id="96019-114">Чтобы определить, была ли проблема с сетью, взгляните на разнотую разницу между средними значениями сеанса и максимальными значениями.</span><span class="sxs-lookup"><span data-stu-id="96019-114">To determine if it was a network problem, look at the delta between the average values for the session and the max values.</span></span> <span data-ttu-id="96019-115">Максимальные значения — это максимальное количество обнаруженных и отчитаных в течение сеанса.</span><span class="sxs-lookup"><span data-stu-id="96019-115">Max values are the maximum detected and reported during the session.</span></span>
 
<span data-ttu-id="96019-116">Вот пример того, как устранить эту ситуацию.</span><span class="sxs-lookup"><span data-stu-id="96019-116">Here's an example of how to troubleshoot this situation.</span></span> <span data-ttu-id="96019-117">Предположим, что во время звонка ведется сетевой трассировка, и за первые 20 минут пакеты не теряются, но в результате пакеты будут просуммом в 1,5 секунды, что хорошо для остальной части звонка.</span><span class="sxs-lookup"><span data-stu-id="96019-117">Let's say you take a network trace during a call and the first 20 minutes there are no lost packets but then you have a gap of 1.5 seconds of packets and then good for the remainder of the call.</span></span> <span data-ttu-id="96019-118">Среднее значение потери пакетов будет <10 % (0,1) даже при анализе RTP трассировки Wireshark.</span><span class="sxs-lookup"><span data-stu-id="96019-118">The average is going to be <10% (0.1) Packet loss even in a Wireshark trace RTP analysis.</span></span> <span data-ttu-id="96019-119">Какова максимальная потеря пакетов?</span><span class="sxs-lookup"><span data-stu-id="96019-119">What was the Max Packet Loss?</span></span> <span data-ttu-id="96019-120">1,5 секунды в 5-секундных периодах будут иметь 30 % (0,3).</span><span class="sxs-lookup"><span data-stu-id="96019-120">1.5 Seconds in a 5-second period would be 30% (0.3).</span></span> <span data-ttu-id="96019-121">Произошло ли это в течение пяти второго периода выборки (возможно, они могут быть разделены по периодам выборки)?</span><span class="sxs-lookup"><span data-stu-id="96019-121">Did that occur within the five second sampling period (maybe or it could be split over the sampling period)?</span></span>
 
<span data-ttu-id="96019-122">Если метрик сети хорошо смотрятся в средних и максимальных значениях, взгляните на другие данные телеметрии:</span><span class="sxs-lookup"><span data-stu-id="96019-122">If network metrics look good in the averages and max values, then look to other telemetry data:</span></span> 
- <span data-ttu-id="96019-123">Проверьте нехватку ресурсов ЦП и неудовлетворительного качества ресурсов ЦП.</span><span class="sxs-lookup"><span data-stu-id="96019-123">Check CPU Insufficient Event Ratio to see if the detected CPU resources available were insufficient and caused poor quality.</span></span> 
- <span data-ttu-id="96019-124">Было ли звуковое устройство в полудуплексном режиме запретить отзыв из-за микрофонов, которые находятся рядом с динамиками?</span><span class="sxs-lookup"><span data-stu-id="96019-124">Was the audio device in Half Duplex mode to prevent feedback due to microphones that are to close to speakers?</span></span> 
- <span data-ttu-id="96019-125">Проверьте коэффициенты событий AEC для устройства Half Duplex.</span><span class="sxs-lookup"><span data-stu-id="96019-125">Check the Device Half Duplex AEC Event Ratio.</span></span> <span data-ttu-id="96019-126">Были ли сбои устройства или сбои микрофона, которые вводили шум или статический из-за отключении USB-звука при подключении к концентратору или док-станции:</span><span class="sxs-lookup"><span data-stu-id="96019-126">Was the device glitching or the microphone glitching introducing noise or static due to USB Audio Drop outs when plugged into a Hub or Docking Station:</span></span>  
- <span data-ttu-id="96019-127">Проверьте временные сбои и сбои микрофона.</span><span class="sxs-lookup"><span data-stu-id="96019-127">Check the Device Glitches and Microphone glitches event ratios.</span></span> <span data-ttu-id="96019-128">Правильно ли работает само устройство?</span><span class="sxs-lookup"><span data-stu-id="96019-128">Was the device itself functioning properly?</span></span>  
- <span data-ttu-id="96019-129">Проверьте пропорции функций устройства захвата и отрисовки.</span><span class="sxs-lookup"><span data-stu-id="96019-129">Check the Capture and Render Device Not Functioning Event Ratios.</span></span>


<span data-ttu-id="96019-130">Для получения дополнительных измерений и мер, доступных в телеметрии CQD, ознакомьтесь с измерениями и измерениями, доступными на панели [мониторинга качества звонка.](dimensions-and-measures-available-in-call-quality-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="96019-130">For more on dimensions and measures available in CQD telemetry, read [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>

<span data-ttu-id="96019-131">Чтобы узнать продолжительность отключения звука участников, проверьте соотношение фонового шума.</span><span class="sxs-lookup"><span data-stu-id="96019-131">For background noise, check mute event ratio to see the length of time participants were muted.</span></span>
 
<span data-ttu-id="96019-132">Создавайте подробные отчеты в CQD и фильтруйте по его ИД, чтобы посмотреть всех пользователей и потоки на собрании и добавить интересуют вас поля.</span><span class="sxs-lookup"><span data-stu-id="96019-132">Create detailed reports in CQD and filter on Meeting ID to look at all users and streams in a meeting and add the fields you are interested in.</span></span> <span data-ttu-id="96019-133">Пользователь, сообщая о проблеме, может не сообщать о проблеме.</span><span class="sxs-lookup"><span data-stu-id="96019-133">A user reporting the issue may not be the one that was having the issue.</span></span> <span data-ttu-id="96019-134">Они просто сообщают о них.</span><span class="sxs-lookup"><span data-stu-id="96019-134">They are just reporting the experience.</span></span>
 
<span data-ttu-id="96019-135">В телеметрии проблема не обязательно будет выявиться, но поможет понять, где искать и сообщать о принятых решениях.</span><span class="sxs-lookup"><span data-stu-id="96019-135">The telemetry will not necessarily call out the issue, but it can help you better understand where to look and inform your decisions.</span></span> <span data-ttu-id="96019-136">Является ли это обновлением сети, устройства, драйвера или микропрограммы, использованием или пользователем?</span><span class="sxs-lookup"><span data-stu-id="96019-136">Is it network, device, driver or firmware updates, usage, or user?</span></span>

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a><span data-ttu-id="96019-137">Почему при звонках и подсчете пользователей между показателями и для получения наиболее точных объемов разницы между звонками и пользователями может быть до 0,2%?</span><span class="sxs-lookup"><span data-stu-id="96019-137">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes?</span></span> 
<span data-ttu-id="96019-138">Для вычисления подсчета вызовов и подсчета пользователей выполняется отдельная операция подсчета для звонка или идентификаторов пользователей в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="96019-138">To compute call count and user count measures, a distinct countif operation is performed against the call or user identifiers in the data set.</span></span> <span data-ttu-id="96019-139">При работе с большими наборами данных количество ошибок, присущих определенной операции счётефа, составляет 0,2 %.</span><span class="sxs-lookup"><span data-stu-id="96019-139">On large data sets, there is an up to 0.2% error inherent with the distinct countif operation.</span></span> <span data-ttu-id="96019-140">Для наиболее точного объема следует полагаться на показатели подсчета потока, так как они не зависят от отдельной операции счётефа.</span><span class="sxs-lookup"><span data-stu-id="96019-140">For the most accurate volume, you should rely on stream count measures since they do not rely on this distinct countif operation.</span></span> <span data-ttu-id="96019-141">Фильтрация для уменьшения громкости данных может снизить ошибку, но не устранят этот источник ошибок в отдельных звонках и подсчетах пользователей.</span><span class="sxs-lookup"><span data-stu-id="96019-141">Filtering to reduce the data volume may reduce the error but may not eliminate this source of error in distinct call and user counts.</span></span> <span data-ttu-id="96019-142">Обратитесь [к измерениям и измерениям, доступным на](dimensions-and-measures-available-in-call-quality-dashboard.md) панели мониторинга качества звонка, на которые влияют меры.</span><span class="sxs-lookup"><span data-stu-id="96019-142">Refer to [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for which measures are impacted.</span></span>


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a><span data-ttu-id="96019-143">Почему данные CQD из Skype для бизнеса отличаются от данных CQD в Teams?</span><span class="sxs-lookup"><span data-stu-id="96019-143">Why is CQD data from Skype for Business different than CQD data from Teams?</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="96019-144">С 1 июля 2020 г. в более старой версии CQD (CQD.lync.com) используются данные из последней версии CQD. Teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="96019-144">As of July 1, 2020, the older CQD (CQD.lync.com) uses data from the latest CQD (CQD.Teams.microsoft.com).</span></span> <span data-ttu-id="96019-145">Более старые данные CQD больше недоступны, и вы не можете экспортировать данные о здании или отчете.</span><span class="sxs-lookup"><span data-stu-id="96019-145">The older CQD data is no longer available, and you can't export your building or report data.</span></span> <span data-ttu-id="96019-146">Вы по-прежнему CQD.lync.com приложение (доступно в Центре администрирования Skype для бизнеса), но в ближайшее время доступ к CQD.lync.com будет отключен, поэтому вам следует перейти на CQD. Teams.microsoft.com, если вы еще не сделали этого.</span><span class="sxs-lookup"><span data-stu-id="96019-146">You can still use CQD.lync.com (available from the Skype for Business admin center), but we'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>


<span data-ttu-id="96019-147">Если вы пытаетесь сравнить данные между устаревшим CQD-адресом Skype для бизнеса (cqd.lync.com) и последней версией CQD из Центра администрирования Teams (cqd.teams.microsoft.com), вы сразу заметите, что данные не совпадают.</span><span class="sxs-lookup"><span data-stu-id="96019-147">If you're trying to compare data between the older CQD from the Skype for Business legacy portal (cqd.lync.com) and the latest CQD from the Teams admin center (cqd.teams.microsoft.com), you'll quickly notice that the data doesn't match.</span></span> <span data-ttu-id="96019-148">Это происходит потому, что последняя версия CQD отчетов о многих дополнительных сценариях звонков.</span><span class="sxs-lookup"><span data-stu-id="96019-148">That's because the latest CQD reports on many additional calling scenarios.</span></span> <span data-ttu-id="96019-149">Если вы по-прежнему используете отчеты, полученные из более старой CQD, прокомпретируете эти отчеты в этой статье: панель мониторинга качества звонков для [Skype для бизнеса Server.](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)</span><span class="sxs-lookup"><span data-stu-id="96019-149">If you're still using reports from the older CQD, use this article to help you interpret those reports: [Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).</span></span>


  
### <a name="why-cant-i-see-euii-in-cqd"></a><span data-ttu-id="96019-150">Почему я не вижу EUII в CQD?</span><span class="sxs-lookup"><span data-stu-id="96019-150">Why can't I see EUII in CQD?</span></span>

<span data-ttu-id="96019-151">Эти роли администраторов могут получать доступ к CQD, но не могут просматривать EUII (зависимые от пользователя сведения):</span><span class="sxs-lookup"><span data-stu-id="96019-151">These admin roles can access CQD, but they can't view EUII (end-user identifiable information):</span></span>
- <span data-ttu-id="96019-152">Читатель отчетов Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="96019-152">Microsoft 365 Reports Reader</span></span>
- <span data-ttu-id="96019-153">Специалист по поддержке связи в Teams</span><span class="sxs-lookup"><span data-stu-id="96019-153">Teams Communications Support Specialist</span></span>

<span data-ttu-id="96019-154">Чтобы узнать больше о ролях, которые могут получать доступ к CQD, в том числе EUII, ознакомьтесь с функцией назначения ролей для доступа к [CQD.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)</span><span class="sxs-lookup"><span data-stu-id="96019-154">To learn more about roles that can access CQD - including EUII - read [Assign roles for accessing CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).</span></span>

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a><span data-ttu-id="96019-155">Почему при фильтрации только по Teams я вижу сведения о Skype для бизнеса в CQD?</span><span class="sxs-lookup"><span data-stu-id="96019-155">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>

<span data-ttu-id="96019-156">При фильтрации только по отчетам CQD (isTeams = 1) фильтруется для всех вызовов, где первой конечной точкой *является* Teams.</span><span class="sxs-lookup"><span data-stu-id="96019-156">When you filter for Teams only in CQD reports (isTeams = 1), you're filtering for all calls where the *first endpoint* is Teams.</span></span> <span data-ttu-id="96019-157">Если второй *конечной точкой* является Skype для бизнеса, эти сведения будут от шоу в отчете CQD.</span><span class="sxs-lookup"><span data-stu-id="96019-157">If the *second endpoint* is Skype for Business, that information will show up in your CQD report.</span></span>

<span data-ttu-id="96019-158">В CQDv2 и CQDv3 всегда будут разные итоги, так как в CQDv3 будут новые сценарии, которые не будут иметься в CQDv2.</span><span class="sxs-lookup"><span data-stu-id="96019-158">CQDv2 and CQDv3 will always have different total counts since CQDv3 will have new scenarios that CQDv2 will not have.</span></span> <span data-ttu-id="96019-159">Поэтому для сравнения итогов и суммарных итогов без фильтров будут такие ожидаемые различия.</span><span class="sxs-lookup"><span data-stu-id="96019-159">That’s why comparing Summary Total or Aggregated all-up numbers with no filters will have these expected differences.</span></span>  

<span data-ttu-id="96019-160">В зависимости от сценария клиентов В CQDv3 будут включены вызовы из локальной службы SFB 2019 (если SFB 2019 используется с соединитетелем данных), вызовы ботов Skype (AA, CVI, VDI), трансляции и звонки по STN.</span><span class="sxs-lookup"><span data-stu-id="96019-160">Depending on Customers’ scenario, CQDv3 will include SFB 2019 on-premises calls (if SFB 2019 is used with a data connector), Skype Bot calls (AA, CVI, VDI), Live Events and PSTN calls.</span></span> <span data-ttu-id="96019-161">Сценарии и функции, доступные клиентам, но их данные не представлены в CQD V2.</span><span class="sxs-lookup"><span data-stu-id="96019-161">Scenarios/Features which are available for the customers, but their data are not in CQD V2.</span></span>

<span data-ttu-id="96019-162">Например, ожидается, что ваши клиенты увидят 200 000 аудиопотоков с 5000 сбоями в сводный отчет CQD V2. в CQD V3 вместо 300 000 аудиопотоков с 5500 сбоев (исходя из 2019 года, вызовов через CVI, вызовы через ПС и т. д.).</span><span class="sxs-lookup"><span data-stu-id="96019-162">For instance, it is expected that your customers and you will see 200,000 audio streams, with 5000 failures in CQD V2 Summary Report; versus 300,000 audio streams with 5500 failures (coming from 2019 on-prem calls, CVI calls, PSTN calls etc) in CQD V3.</span></span>

<span data-ttu-id="96019-163">Чтобы определить, есть ли непредвиденные различия, необходимо и взглянуть на различные разбивки общих данных.</span><span class="sxs-lookup"><span data-stu-id="96019-163">In order to determine, if there are any unexpected differences, you must look at various breakdowns of the overall data.</span></span>  <span data-ttu-id="96019-164">Сравнение с цельми.</span><span class="sxs-lookup"><span data-stu-id="96019-164">Compare with intent.</span></span>  <span data-ttu-id="96019-165">Одной из первых рекомендуемых является лицензия данных с помощью user Agent Category Pair.</span><span class="sxs-lookup"><span data-stu-id="96019-165">Slicing the data by User Agent Category Pair is one of the first things we recommend.</span></span>  <span data-ttu-id="96019-166">*Срезы First Product* *и Second Product* также хороши.</span><span class="sxs-lookup"><span data-stu-id="96019-166">*First Product* and *Second Product* are also good slicers.</span></span>  


## <a name="related-topics"></a><span data-ttu-id="96019-167">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="96019-167">Related topics</span></span>

[<span data-ttu-id="96019-168">Улучшение и отслеживание качества вызовов в Teams</span><span class="sxs-lookup"><span data-stu-id="96019-168">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="96019-169">Что такое CQD?</span><span class="sxs-lookup"><span data-stu-id="96019-169">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="96019-170">Настройка панели мониторинга качества звонка (CQD)</span><span class="sxs-lookup"><span data-stu-id="96019-170">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="96019-171">Отправка данных о клиенте и здании</span><span class="sxs-lookup"><span data-stu-id="96019-171">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="96019-172">Данные и отчеты CQD</span><span class="sxs-lookup"><span data-stu-id="96019-172">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="96019-173">Управление звонками и качеством собраний с помощью CQD</span><span class="sxs-lookup"><span data-stu-id="96019-173">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="96019-174">Измерения и меры, доступные в CQD</span><span class="sxs-lookup"><span data-stu-id="96019-174">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="96019-175">Классификация потоков в CQD</span><span class="sxs-lookup"><span data-stu-id="96019-175">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="96019-176">Анализ данных CQD с помощью Power BI</span><span class="sxs-lookup"><span data-stu-id="96019-176">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)

[<span data-ttu-id="96019-177">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="96019-177">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)