---
title: Использование отчета о прямой маршрутизации CQD PSTN
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies, fan.fan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Используйте для мониторинга и устранения неполадок, связанных с телефонным подключением PSTN в Microsoft Teams, использование панели мониторинга качества звонков Microsoft Teams (CQD)).
ms.openlocfilehash: 0987ae30c9bb0b428a4d46bf036c2de938c555f0
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085345"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="60b0b-103">Использование отчета о прямой маршрутизации CQD PSTN</span><span class="sxs-lookup"><span data-stu-id="60b0b-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="60b0b-104">Новая версия в марте 2020. Мы добавили в [шаблоны запросов на поддержку Power BI](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)на панели мониторинга качества обзвона Microsoft Teams (CQD) по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="60b0b-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="60b0b-105">Отчет о прямой маршрутизации CQD КТСОП (CQD КТСОП Direct Routing Reporting) поможет вам понять принципы использования и качество обслуживания PSTN.</span><span class="sxs-lookup"><span data-stu-id="60b0b-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="60b0b-106">Этот отчет служит для наблюдения за использованием службы, сведениями о контроллере границ сеанса (SBC), службе телефонии, параметрах сети и коэффициентах эффективности сети.</span><span class="sxs-lookup"><span data-stu-id="60b0b-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="60b0b-107">Эти сведения помогут вам определить проблемы, в том числе причину прерванных звонков.</span><span class="sxs-lookup"><span data-stu-id="60b0b-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="60b0b-108">Например, вы сможете видеть, когда вы снижаете уровень громкости, а также о том, сколько звонков будет затронуто и по какой причине.</span><span class="sxs-lookup"><span data-stu-id="60b0b-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="60b0b-109">В отчете о маршрутизации CQD PSTN есть четыре раздела:</span><span class="sxs-lookup"><span data-stu-id="60b0b-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="60b0b-110">Общие сведения о PSTN</span><span class="sxs-lookup"><span data-stu-id="60b0b-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="60b0b-111">Сведения о службе</span><span class="sxs-lookup"><span data-stu-id="60b0b-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="60b0b-112">Коэффициент эффективности сети</span><span class="sxs-lookup"><span data-stu-id="60b0b-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="60b0b-113">Сетевые параметры</span><span class="sxs-lookup"><span data-stu-id="60b0b-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="60b0b-114">Освещает</span><span class="sxs-lookup"><span data-stu-id="60b0b-114">Highlights</span></span>

1. <span data-ttu-id="60b0b-115">Анализ по типу звонка, SBC, стране вызывающего абонента и абоненту</span><span class="sxs-lookup"><span data-stu-id="60b0b-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="60b0b-116">В отчете об использовании прямой маршрутизации CQD КТСОП объединяются показатели надежности и использования для всех SBCs в клиенте за последние 7, 30 и 180 дней (6 месяцев).</span><span class="sxs-lookup"><span data-stu-id="60b0b-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="60b0b-117">Вы можете проанализировать данные по типу вызова, SBC, стране вызывающего абонента и абоненту.</span><span class="sxs-lookup"><span data-stu-id="60b0b-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="60b0b-118">Если вы заинтересованы в определенном SBC или стране, вы сможете определять изменения в тенденциях за выбранный диапазон времени.</span><span class="sxs-lookup"><span data-stu-id="60b0b-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Снимок экрана: фильтры, доступные в отчете CQD КТСОП Direct Routing":::
   
2. <span data-ttu-id="60b0b-120">Отслеживание тенденций</span><span class="sxs-lookup"><span data-stu-id="60b0b-120">Track trends</span></span>

    <span data-ttu-id="60b0b-121">Анализ тенденций важен при попытке понять использование и надежность служб.</span><span class="sxs-lookup"><span data-stu-id="60b0b-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="60b0b-122">Почасовые тенденции обеспечивают более близкую производительность, которая помогает выявить происшествия в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="60b0b-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="60b0b-123">Ежедневные тенденции позволяют видеть работоспособность службы с долгосрочной перспективе.</span><span class="sxs-lookup"><span data-stu-id="60b0b-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="60b0b-124">Важно иметь возможность смены между этими двумя режимами с соответствующей детализацией данных.</span><span class="sxs-lookup"><span data-stu-id="60b0b-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="60b0b-125">Отчет о маршрутизации CQD PSTN обеспечивает общие сведения о тенденциях в течение 6 месяцев, ежедневных и 30-дневных тенденций, а также почасовые тенденции, позволяющие анализировать производительность на каждом уровне.</span><span class="sxs-lookup"><span data-stu-id="60b0b-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Снимок экрана: диаграммы тенденций в отчете о маршрутизации CQD PSTN":::

3. <span data-ttu-id="60b0b-127">Детализация до SBC или уровня пользователя</span><span class="sxs-lookup"><span data-stu-id="60b0b-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="60b0b-128">Мы собрались в возможности детализации на многих категориях данных в CQD, что позволяет быстро понять использование или надежность на уровне SBC или пользователя.</span><span class="sxs-lookup"><span data-stu-id="60b0b-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="60b0b-129">С помощью детализации вы можете быстро poinpoint проблемы и понять реальное воздействие на пользователей.</span><span class="sxs-lookup"><span data-stu-id="60b0b-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="60b0b-130">В отчетах по маршрутизации CQD PSTN можно детально детализировать детали обслуживания и показатели эффективности сети.</span><span class="sxs-lookup"><span data-stu-id="60b0b-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="60b0b-131">Щелкните интересующую вас точку данных, чтобы проанализировать данные на SBC или на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="60b0b-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Снимок экрана с возможностью детализации в точке данных":::


## <a name="pstn-overview"></a><span data-ttu-id="60b0b-133">Общие сведения о PSTN</span><span class="sxs-lookup"><span data-stu-id="60b0b-133">PSTN Overview</span></span>

<span data-ttu-id="60b0b-134">В отчете о маршрутизации CQD PSTN указаны следующие сведения, относящиеся к общей работоспособности службы за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="60b0b-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="60b0b-135">![Снимок экрана: отчет о PSTN CQD](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="60b0b-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="60b0b-136">Например, если вы заинтересованы в общем использовании и работоспособности всех входящих звонков, которые проходит через SBC abc.bca.adatum.biz с нами в качестве внутренней страны, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="60b0b-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="60b0b-137">**Вызовите**</span><span class="sxs-lookup"><span data-stu-id="60b0b-137">**Call Out**</span></span> | <span data-ttu-id="60b0b-138">**Описание**</span><span class="sxs-lookup"><span data-stu-id="60b0b-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="60b0b-139">1</span><span class="sxs-lookup"><span data-stu-id="60b0b-139">1</span></span>            | <span data-ttu-id="60b0b-140">Вы можете использовать фильтры в верхней части экрана для детализации и выбрать ByotIn в качестве типа звонка, abc.bca.contoso.com в качестве контроллера сеанса и в качестве внутренней страны.</span><span class="sxs-lookup"><span data-stu-id="60b0b-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="60b0b-141">2</span><span class="sxs-lookup"><span data-stu-id="60b0b-141">2</span></span>            | <span data-ttu-id="60b0b-142">Тенденция использования за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="60b0b-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="60b0b-143">Вы можете найти подробный отчет об использовании на странице сведений о службе.</span><span class="sxs-lookup"><span data-stu-id="60b0b-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="60b0b-144">3</span><span class="sxs-lookup"><span data-stu-id="60b0b-144">3</span></span>            | <span data-ttu-id="60b0b-145">Задержка набора номера, задержка, колебание и тенденция потери пакетов за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="60b0b-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="60b0b-146">Вы можете найти подробный отчет на странице Параметры сети.</span><span class="sxs-lookup"><span data-stu-id="60b0b-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="60b0b-147">4</span><span class="sxs-lookup"><span data-stu-id="60b0b-147">4</span></span>            | <span data-ttu-id="60b0b-148">Одновременный звонок и дневная активная тенденция пользователей за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="60b0b-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="60b0b-149">Эта диаграмма поможет вам понять, как это максимальный объем услуг.</span><span class="sxs-lookup"><span data-stu-id="60b0b-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="60b0b-150">5</span><span class="sxs-lookup"><span data-stu-id="60b0b-150">5</span></span>            | <span data-ttu-id="60b0b-151">Причина, по которой заканчивается качество обслуживания по верхнему краю за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="60b0b-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="60b0b-152">Вы можете найти сведения о работоспособности службы на странице коэффициент эффективности сети (NER).</span><span class="sxs-lookup"><span data-stu-id="60b0b-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="60b0b-153">Сведения о службе</span><span class="sxs-lookup"><span data-stu-id="60b0b-153">Service Details</span></span>

<span data-ttu-id="60b0b-154">Эта страница обеспечивает тенденции использования служб за день и отзыв пользователей по географическим подразделениям.</span><span class="sxs-lookup"><span data-stu-id="60b0b-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="60b0b-155">**Всего попыток вызова:** Общее количество одновременных звонков в указанном диапазоне времени, включая успешные и неудачные вызовы</span><span class="sxs-lookup"><span data-stu-id="60b0b-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="60b0b-156">**Общее количество подключенных звонков-** Общее количество подключенных вызовов в указанном диапазоне времени</span><span class="sxs-lookup"><span data-stu-id="60b0b-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="60b0b-157">**Всего минут –** Общее использование минут в указанном диапазоне времени</span><span class="sxs-lookup"><span data-stu-id="60b0b-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="60b0b-158">**Ежедневные активные пользователи (DAU) —** Количество активных пользователей, которые выполнили по крайней мере один подключенный Звонок в этот день.</span><span class="sxs-lookup"><span data-stu-id="60b0b-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="60b0b-159">**Одновременные звонки:** Максимум одновременных активных звонков за минуту</span><span class="sxs-lookup"><span data-stu-id="60b0b-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="60b0b-160">**Отзывы пользователей:** "Оценить баллы о звонке", поступает от пользователя.</span><span class="sxs-lookup"><span data-stu-id="60b0b-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="60b0b-161">3-5 считается хорошим звонком.</span><span class="sxs-lookup"><span data-stu-id="60b0b-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="60b0b-162">1-2 считается неправильным звонком.</span><span class="sxs-lookup"><span data-stu-id="60b0b-162">1-2 is considered as a bad call.</span></span>

![Снимок экрана: отчет о PSTN CQD](media/CQD-PSTN-report2.png)

<span data-ttu-id="60b0b-164">Например:</span><span class="sxs-lookup"><span data-stu-id="60b0b-164">For example:</span></span>

1.  <span data-ttu-id="60b0b-165">Если вы видите среднюю длительность звонка в 0 в 02/14/2020, вы можете сначала проверить, выглядит ли громкость звонка обычно, и узнать, есть ли существенные отличия между общим соединением и общим количеством одновременных звонков.</span><span class="sxs-lookup"><span data-stu-id="60b0b-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="60b0b-166">Затем перейдите на страницу коэффициента эффективности сети, чтобы присоединиться к причине ошибки звонка.</span><span class="sxs-lookup"><span data-stu-id="60b0b-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="60b0b-167">Если вы видите более красные пятна на карте отзывов пользователей, вы можете перейти на страницу коэффициента эффективности сети и сетевой параметр, чтобы проверить, есть ли какие-либо аномалии, и вы можете создать билет с помощью службы поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="60b0b-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="60b0b-168">Коэффициент эффективности сети</span><span class="sxs-lookup"><span data-stu-id="60b0b-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="60b0b-169">Это та же метрика, которая отображается на общей информационной панели мониторинга работоспособности.</span><span class="sxs-lookup"><span data-stu-id="60b0b-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="60b0b-170">Вы можете проверить почасовое NER число с помощью сведений о вызываемых звонках для обоих направлений звонка (входящий/исходящий трафик) на почасовом соотношении эффективности сети и конечной причины звонка ниже.</span><span class="sxs-lookup"><span data-stu-id="60b0b-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="60b0b-171">**NER** — возможность (%) сети, чтобы доставлять звонки, измеряя количество отправленных звонков и количество звонков, доставленных получателю.</span><span class="sxs-lookup"><span data-stu-id="60b0b-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="60b0b-172">**Код ответа SIP**— трехзначный целочисленный код ответа показывает состояние вызова.</span><span class="sxs-lookup"><span data-stu-id="60b0b-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="60b0b-173">**Код ответа Microsoft**— код ответа, отправленный из компонента Microsoft.</span><span class="sxs-lookup"><span data-stu-id="60b0b-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="60b0b-174">**Описание** — этап причины, соответствующий коду ответа SIP и коду ответа Microsoft.</span><span class="sxs-lookup"><span data-stu-id="60b0b-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="60b0b-175">**Количество затронутых звонков** — общее количество звонков, которые были затронуты в течение выбранного интервала времени.</span><span class="sxs-lookup"><span data-stu-id="60b0b-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Снимок экрана: отчет о PSTN CQD](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="60b0b-177">Например:</span><span class="sxs-lookup"><span data-stu-id="60b0b-177">For example:</span></span>

![Снимок экрана: отчет о PSTN CQD](media/CQD-PSTN-report4.png)

<span data-ttu-id="60b0b-179">Если для ежедневного NER установлен DIP-значение в 02/05/2020, вы можете щелкнуть дату, и другие диаграммы будут масштабироваться до указанной даты.</span><span class="sxs-lookup"><span data-stu-id="60b0b-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Снимок экрана: отчет о PSTN CQD](media/CQD-PSTN-report5.png)

<span data-ttu-id="60b0b-181">С почасовой NERой процентной тенденции вы можете найти DIP, выступающей около 21:00.</span><span class="sxs-lookup"><span data-stu-id="60b0b-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="60b0b-182">Затем щелкните еще раз, чтобы перейти к часу 21 и проверить сведения о вызываемом звонке, чтобы узнать, сколько произошел сбой звонков в течение этого часа и каковы причины, по которым нужно закончить звонок.</span><span class="sxs-lookup"><span data-stu-id="60b0b-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="60b0b-183">Вы можете приступить к устранению проблем, связанных с SBC, или сообщить в службу поддержки, если проблема не связана с SBC.</span><span class="sxs-lookup"><span data-stu-id="60b0b-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="60b0b-184">Сетевые параметры</span><span class="sxs-lookup"><span data-stu-id="60b0b-184">Network Parameters</span></span>

<span data-ttu-id="60b0b-185">Все сетевые параметры измеряются от интерфейса Direct Routing на контроллере границ сеанса.</span><span class="sxs-lookup"><span data-stu-id="60b0b-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="60b0b-186">Дополнительные сведения о рекомендуемых значениях можно найти в [статье Подготовка сети организации для Microsoft Teams](prepare-network.md)и ознакомьтесь со статьей "клиент" в разделе "Рекомендуемые значения Microsoft Edge".</span><span class="sxs-lookup"><span data-stu-id="60b0b-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="60b0b-187">**Колебание** — это величина, которая измеряется в миллисекундах времени задержки распространения сети, вычисленной между двумя конечными точками с помощью RTCP (протокол управления RTP).</span><span class="sxs-lookup"><span data-stu-id="60b0b-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="60b0b-188">**Потери пакетов** — это мера пакета, который не удалось получить; Она вычисляется между двумя конечными точками.</span><span class="sxs-lookup"><span data-stu-id="60b0b-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="60b0b-189">**Задержка** (также известная как время кругового поездки) — продолжительность отправки сигнала и время, необходимое для подтверждения подлинности этого сигнала.</span><span class="sxs-lookup"><span data-stu-id="60b0b-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="60b0b-190">Это время задержки состоит из времени распространения между двумя точками сигнала.</span><span class="sxs-lookup"><span data-stu-id="60b0b-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Снимок экрана: отчет о PSTN CQD](media/CQD-PSTN-report6.png)

<span data-ttu-id="60b0b-192">Например:</span><span class="sxs-lookup"><span data-stu-id="60b0b-192">For example:</span></span>

<span data-ttu-id="60b0b-193">Если вы видите копилку на любой из четырех диаграмм (задержка, колебание, частота потерь пакетов, задержка набора номера) для определенной даты, например задержка в 02/14/2020, щелкните точку даты.</span><span class="sxs-lookup"><span data-stu-id="60b0b-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="60b0b-194">А диаграмма почасового тренда внизу будет обновлена, чтобы показать почасовое число.</span><span class="sxs-lookup"><span data-stu-id="60b0b-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="60b0b-195">Вы можете проверить SBCs или создать билет с помощью службы MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="60b0b-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Снимок экрана: отчет о PSTN CQD](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="60b0b-197">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="60b0b-197">Related topics</span></span>

[<span data-ttu-id="60b0b-198">Анализ данных CQD в Microsoft Teams с помощью Power BI</span><span class="sxs-lookup"><span data-stu-id="60b0b-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="60b0b-199">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="60b0b-199">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)