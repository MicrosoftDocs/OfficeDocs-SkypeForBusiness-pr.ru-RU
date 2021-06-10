---
title: Использование отчета CQD PSTN Direct Routing
ms.author: serdars
author: SerdarSoysal
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
description: С помощью Microsoft Teams панели мониторинга качества звонков (CQD)) для отслеживания и устранения неполадок, вызывающих вызовы через Microsoft Teams.
ms.openlocfilehash: f2b63f991f42aa4de9e0e4474137f7f992f95c53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094983"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="0361b-103">Использование отчета CQD PSTN Direct Routing</span><span class="sxs-lookup"><span data-stu-id="0361b-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="0361b-104">В марте 2020 г. мы добавили отчет Microsoft Teams Routing Direct Routing по ПСN (CQD) в шаблоны запросов Power BI [CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="0361b-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="0361b-105">Отчет CQD PSTN Direct Routing (CQD POUTING Direct Routing Report.pbit) поможет вам понять шаблоны использования и качество служб ННП.</span><span class="sxs-lookup"><span data-stu-id="0361b-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="0361b-106">Используйте этот отчет для отслеживания использования служб, сведений о контроллере границы сеанса (SBC), телефонной службе, параметрах сети и сведениях о соотношении эффективности сети.</span><span class="sxs-lookup"><span data-stu-id="0361b-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="0361b-107">Эти сведения помогут вам выявить проблемы, в том числе причину сброшенных звонков.</span><span class="sxs-lookup"><span data-stu-id="0361b-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="0361b-108">Например, вы сможете увидеть, когда пропадает громкость или сколько звонков затронуты и по какой причине.</span><span class="sxs-lookup"><span data-stu-id="0361b-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="0361b-109">Отчет CQD PSTN Direct Routing имеет четыре раздела:</span><span class="sxs-lookup"><span data-stu-id="0361b-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="0361b-110">Общие сведения о ОКП</span><span class="sxs-lookup"><span data-stu-id="0361b-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="0361b-111">Сведения о службе</span><span class="sxs-lookup"><span data-stu-id="0361b-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="0361b-112">Отношение эффективности сети</span><span class="sxs-lookup"><span data-stu-id="0361b-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="0361b-113">Параметры сети</span><span class="sxs-lookup"><span data-stu-id="0361b-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="0361b-114">Моменты</span><span class="sxs-lookup"><span data-stu-id="0361b-114">Highlights</span></span>

1. <span data-ttu-id="0361b-115">Анализ по типу звонка, SBC, вызываемой и вызываемой стране</span><span class="sxs-lookup"><span data-stu-id="0361b-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="0361b-116">Отчет CQD PSTN Direct Routing собирает показатели надежности и использования для всех SBCs в клиенте за последние 7, 30 или 180 дней (6 месяцев).</span><span class="sxs-lookup"><span data-stu-id="0361b-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="0361b-117">Данные можно анализировать по типу звонка, SBC, вызываемой и вызываемой стране.</span><span class="sxs-lookup"><span data-stu-id="0361b-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="0361b-118">Если вас интересует определенный SBC или страна, вы сможете выявлять изменения тенденций в выбранном диапазоне времени.</span><span class="sxs-lookup"><span data-stu-id="0361b-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Снимок экрана: фильтры, доступные в отчете О прямой маршрутике по ПСПС":::
   
2. <span data-ttu-id="0361b-120">Отслеживание тенденций</span><span class="sxs-lookup"><span data-stu-id="0361b-120">Track trends</span></span>

    <span data-ttu-id="0361b-121">Анализ тенденций необходим для понимания использования и надежности служб.</span><span class="sxs-lookup"><span data-stu-id="0361b-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="0361b-122">Почасовые тенденции обеспечивают более точное представление о ежедневной производительности, что помогает выявлять инциденты в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="0361b-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="0361b-123">Ежедневные тенденции в долгосрочной перспективе повеют о ее состоянии.</span><span class="sxs-lookup"><span data-stu-id="0361b-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="0361b-124">Очень важно иметь возможность переключяться между этими двумя режимами с соответствующими детализацией данных.</span><span class="sxs-lookup"><span data-stu-id="0361b-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="0361b-125">В отчете CQD PSTN Direct Routing представлен обзор тенденций в течение 6 месяцев, 7- и 30-дневной тенденций, а также почасовые тенденции, что позволяет анализировать производительность на каждом уровне.</span><span class="sxs-lookup"><span data-stu-id="0361b-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Снимок экрана: графики тенденций в отчете "Прямая маршрутия" через ПСПС":::

3. <span data-ttu-id="0361b-127">Drill through to SBC or user level</span><span class="sxs-lookup"><span data-stu-id="0361b-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="0361b-128">Мы взламываем возможности drill-through на многих категориях данных в CQD, что позволяет быстро понять использование и надежность распространения на уровне SBC или пользователей.</span><span class="sxs-lookup"><span data-stu-id="0361b-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="0361b-129">С помощью этих упражнений можно быстро переупомехить проблемы и понять, как это повлияет на пользователей.</span><span class="sxs-lookup"><span data-stu-id="0361b-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="0361b-130">В отчете CQD PSTN Direct Routing 2016 представлены метрики "Подробные данные о службе" и "Отношение эффективности сети".</span><span class="sxs-lookup"><span data-stu-id="0361b-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="0361b-131">Щелкните интересуемую точку данных, чтобы деталижать сведения на уровне SBC или пользователя.</span><span class="sxs-lookup"><span data-stu-id="0361b-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Снимок экрана: возможность прогона в точке данных":::


## <a name="pstn-overview"></a><span data-ttu-id="0361b-133">Общие сведения о ОКП</span><span class="sxs-lookup"><span data-stu-id="0361b-133">PSTN Overview</span></span>

<span data-ttu-id="0361b-134">В отчете CQD PSTN Direct Routing (Прямая маршрутка по ПСN) данная информация связана с общим состоянием службы за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="0361b-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="0361b-135">![Снимок экрана: отчет "CQD" для ОКП ННР](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="0361b-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="0361b-136">Например, если вас интересует общее использование и состояние всех входящие звонков, которые проходят через SBC abc.bca.adatum.biz с США в качестве внутренней страны:</span><span class="sxs-lookup"><span data-stu-id="0361b-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="0361b-137">**Вызов**</span><span class="sxs-lookup"><span data-stu-id="0361b-137">**Call Out**</span></span> | <span data-ttu-id="0361b-138">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0361b-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="0361b-139">1</span><span class="sxs-lookup"><span data-stu-id="0361b-139">1</span></span>            | <span data-ttu-id="0361b-140">Вы можете использовать фильтры в верхней части, чтобы отфильтровать и выбрать ByotIn как тип вызова, abc.bca.contoso.com как контроллер session Boarder, и США как внутренняя страна.</span><span class="sxs-lookup"><span data-stu-id="0361b-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="0361b-141">2</span><span class="sxs-lookup"><span data-stu-id="0361b-141">2</span></span>            | <span data-ttu-id="0361b-142">Тенденция использования за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="0361b-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="0361b-143">Отчет об использовании можно найти на странице "Подробные данные службы".</span><span class="sxs-lookup"><span data-stu-id="0361b-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="0361b-144">3</span><span class="sxs-lookup"><span data-stu-id="0361b-144">3</span></span>            | <span data-ttu-id="0361b-145">Публикация тенденций задержки набора, задержки, дрожания и потери пакетов за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="0361b-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="0361b-146">Подробный отчет можно найти на странице "Параметры сети".</span><span class="sxs-lookup"><span data-stu-id="0361b-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="0361b-147">4</span><span class="sxs-lookup"><span data-stu-id="0361b-147">4</span></span>            | <span data-ttu-id="0361b-148">Тенденции одновременного звонка и ежедневного активного пользователя за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="0361b-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="0361b-149">Эта диаграмма поможет вам понять максимальный объем услуг.</span><span class="sxs-lookup"><span data-stu-id="0361b-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="0361b-150">5</span><span class="sxs-lookup"><span data-stu-id="0361b-150">5</span></span>            | <span data-ttu-id="0361b-151">Top Call End Reason affected service quality for the past 180 days.</span><span class="sxs-lookup"><span data-stu-id="0361b-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="0361b-152">Подробные о состоянии обслуживания можно найти на странице Network Effective Ratio(NER).</span><span class="sxs-lookup"><span data-stu-id="0361b-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="0361b-153">Сведения о службе</span><span class="sxs-lookup"><span data-stu-id="0361b-153">Service Details</span></span>

<span data-ttu-id="0361b-154">На этой странице вы сможете увидеть тенденции использования служб в день и разбивку отзывов пользователей по географическим регионам.</span><span class="sxs-lookup"><span data-stu-id="0361b-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="0361b-155">**Общая попытка звонков :** Общее количество звонков по попыткам в этом диапазоне времени, включая как успешные, так и сбойные вызовы</span><span class="sxs-lookup"><span data-stu-id="0361b-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="0361b-156">**Общее количество подключенных звонков —** Общее количество подключенных звонков в этом диапазоне времени</span><span class="sxs-lookup"><span data-stu-id="0361b-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="0361b-157">**Общее количество минут —** Общее использование минут в этом диапазоне времени</span><span class="sxs-lookup"><span data-stu-id="0361b-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="0361b-158">**Ежедневные активные пользователи (DAU) —** Количество ежедневно активных пользователей, которые сделали хотя бы один подключенный звонок в этот день</span><span class="sxs-lookup"><span data-stu-id="0361b-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="0361b-159">**При одновременном вызове —** Максимум одновременных активных звонков за минуту</span><span class="sxs-lookup"><span data-stu-id="0361b-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="0361b-160">**Отзывы пользователей —** Оценка "Оценка звонка" поступает от пользователя.</span><span class="sxs-lookup"><span data-stu-id="0361b-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="0361b-161">3–5 — это хороший звонок.</span><span class="sxs-lookup"><span data-stu-id="0361b-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="0361b-162">1–2 считается плохим звоном.</span><span class="sxs-lookup"><span data-stu-id="0361b-162">1-2 is considered as a bad call.</span></span>

![Снимок экрана: отчет "CQD" для ОКП ННР](media/CQD-PSTN-report2.png)

<span data-ttu-id="0361b-164">Например:</span><span class="sxs-lookup"><span data-stu-id="0361b-164">For example:</span></span>

1.  <span data-ttu-id="0361b-165">Если в 14.02.2020 вы видите, что средняя длительность звонка снижается до 0, вы можете сначала проверить, нормально ли выглядит громкость звонков и есть ли значительные различия между суммарными звонками на подключение и звонками общей попытки.</span><span class="sxs-lookup"><span data-stu-id="0361b-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="0361b-166">Затем перейдите на страницу "Коэффициенты эффективности сети", чтобы оценить причины сбоев вызовов.</span><span class="sxs-lookup"><span data-stu-id="0361b-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="0361b-167">Если на карте отзывов пользователей появилось все больше красных мест, можно перейти на страницу "Отношение эффективности сети" и "Сетевой параметр", чтобы узнать, есть ли аномалии, и с помощью службы MS Service Desk можно составить вопрос.</span><span class="sxs-lookup"><span data-stu-id="0361b-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="0361b-168">Отношение эффективности сети</span><span class="sxs-lookup"><span data-stu-id="0361b-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="0361b-169">Это та же метрика, которая отображается на панели мониторинга "Общее состояние".</span><span class="sxs-lookup"><span data-stu-id="0361b-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="0361b-170">Вы можете проверить почасовой номер NER со всеми затронутыми звонками для обоих маршрутов (входящие и исходящие) на диаграмме Почасовая эффективность сети и диаграмма конечной причины вызова ниже.</span><span class="sxs-lookup"><span data-stu-id="0361b-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="0361b-171">**NER** — возможность (%) сети для доставки звонков путем измерения количества отправленных звонков и количества звонков, доставленных получателю.</span><span class="sxs-lookup"><span data-stu-id="0361b-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="0361b-172">**Код ответа SIP:** состояние звонка указывается в трехзначном коде ответа на звонок.</span><span class="sxs-lookup"><span data-stu-id="0361b-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="0361b-173">**Код ответа Майкрософт**— код ответа, отправленный из компонента Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0361b-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="0361b-174">**Описание.** Этап причины, соответствующий коду ответа SIP и коду ответа Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0361b-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="0361b-175">**Число звонков, на** которые влияет влияние: общее количество звонков за выбранный период.</span><span class="sxs-lookup"><span data-stu-id="0361b-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Снимок экрана: отчет "CQD" для ОКП ННР](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="0361b-177">Например:</span><span class="sxs-lookup"><span data-stu-id="0361b-177">For example:</span></span>

![Снимок экрана: отчет "CQD" для ОКП ННР](media/CQD-PSTN-report4.png)

<span data-ttu-id="0361b-179">Если 05.02.2020 г. ежедневное NER ухмехает, вы можете щелкнуть дату, и другие диаграммы будут масштабироваться до этой конкретной даты.</span><span class="sxs-lookup"><span data-stu-id="0361b-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Снимок экрана: отчет "CQD" для ОКП ННР](media/CQD-PSTN-report5.png)

<span data-ttu-id="0361b-181">В ОКП "Хорошее процентное почасовая тенденция" можно обнаружить, что это происходит около 21:00.</span><span class="sxs-lookup"><span data-stu-id="0361b-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="0361b-182">Затем щелкните еще раз, чтобы увеличить масштаб до 21 часа, и проверьте сведения об эффекте звонка, чтобы узнать, сколько звонков не удалось сделать за этот час и каковы причины их окончания.</span><span class="sxs-lookup"><span data-stu-id="0361b-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="0361b-183">Если проблема не связана с SBC, вы можете начать с самостоятельного устранения проблем с SBC или сообщить о них службе Service Desk.</span><span class="sxs-lookup"><span data-stu-id="0361b-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="0361b-184">Параметры сети</span><span class="sxs-lookup"><span data-stu-id="0361b-184">Network Parameters</span></span>

<span data-ttu-id="0361b-185">Все сетевые параметры измеряются от интерфейса прямой маршрутии до контроллера границы сеанса.</span><span class="sxs-lookup"><span data-stu-id="0361b-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="0361b-186">Сведения о рекомендуемых значениях [](prepare-network.md)см. в Microsoft Teams сети организации и на сайте Customer Edge Microsoft Edge рекомендуемых значений.</span><span class="sxs-lookup"><span data-stu-id="0361b-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="0361b-187">**Дрожание** — это миллисекундный показатель разброса задержки распространения сети, вычисляемой между двумя конечными точками с помощью RTCP (RTP-протокола).</span><span class="sxs-lookup"><span data-stu-id="0361b-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="0361b-188">**Packet Loss** — это мера пакетов, которые не удалось получить; вычисляется между двумя конечными точками.</span><span class="sxs-lookup"><span data-stu-id="0361b-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="0361b-189">**Задержка** (или время кругового пути) — это время, необходимое для сигнала, а также длительность его подтверждения.</span><span class="sxs-lookup"><span data-stu-id="0361b-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="0361b-190">Эта задержка состоит из времени распространения между двумя точками сигнала.</span><span class="sxs-lookup"><span data-stu-id="0361b-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Снимок экрана: отчет "CQD" для ОКП ННР](media/CQD-PSTN-report6.png)

<span data-ttu-id="0361b-192">Например:</span><span class="sxs-lookup"><span data-stu-id="0361b-192">For example:</span></span>

<span data-ttu-id="0361b-193">Если на одной из четырех диаграмм (задержка, дрожание, коэффициент потерь пакетов, после задержки набора номера) вы видите пик задержки для определенной даты, например Задержка 14.02.2020, щелкните дату.</span><span class="sxs-lookup"><span data-stu-id="0361b-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="0361b-194">А ежечасная диаграмма тренда внизу обновиться, чтобы показать ежечасную.</span><span class="sxs-lookup"><span data-stu-id="0361b-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="0361b-195">Вы можете проверить SBCs или получить билет с помощью службы MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="0361b-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Снимок экрана: отчет "CQD" для ОКП ННР](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="0361b-197">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0361b-197">Related topics</span></span>

[<span data-ttu-id="0361b-198">Используйте Power BI для анализа данных CQD для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0361b-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="0361b-199">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="0361b-199">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)