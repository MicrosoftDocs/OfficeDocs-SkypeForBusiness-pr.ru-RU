---
title: Использование отчета "CQD Direct Routing" (Прямая маршрутная маршрутка по ННР)
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
description: Используйте отчет о прямой маршрутке ЗВОНКОВ по ЗВОНКОВ (CQD) Microsoft Teams для отслеживания и устранения неполадок со звонками по СТАНП в Microsoft Teams.
ms.openlocfilehash: e4662d80dbba88c1049c7ef98569dae408ca9ba0
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583106"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="38320-103">Использование отчета "CQD Direct Routing" (Прямая маршрутная маршрутка по ННР)</span><span class="sxs-lookup"><span data-stu-id="38320-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="38320-104">В марте 2020 г. мы добавили в шаблоны запросов Power BI для [CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)отчет о прямой маршрутке по STN Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="38320-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="38320-105">Отчет CQD Direct Routing PSTN (CQD Direct Routing Report.pbit) поможет вам понять схемы использования и качество служб ННР.</span><span class="sxs-lookup"><span data-stu-id="38320-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="38320-106">Используйте этот отчет для отслеживания использования служб, сведений о контроллере границы сеанса (SBC), телефонной службе, параметрах сети и данных о коэффициентах эффективности сети.</span><span class="sxs-lookup"><span data-stu-id="38320-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="38320-107">Эти сведения помогут вам выявить проблемы, в том числе причину перепада звонков.</span><span class="sxs-lookup"><span data-stu-id="38320-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="38320-108">Например, вы сможете видеть, когда пропадает громкость и сколько звонков затронуты и по какой причине.</span><span class="sxs-lookup"><span data-stu-id="38320-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="38320-109">Отчет CQD Direct Routing через ДНР имеет четыре раздела:</span><span class="sxs-lookup"><span data-stu-id="38320-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="38320-110">Общие сведения о ОКП</span><span class="sxs-lookup"><span data-stu-id="38320-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="38320-111">Сведения о службе</span><span class="sxs-lookup"><span data-stu-id="38320-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="38320-112">Коэффициент эффективности сети</span><span class="sxs-lookup"><span data-stu-id="38320-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="38320-113">Параметры сети</span><span class="sxs-lookup"><span data-stu-id="38320-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="38320-114">Моменты</span><span class="sxs-lookup"><span data-stu-id="38320-114">Highlights</span></span>

1. <span data-ttu-id="38320-115">Анализ по типу звонка, SBC, вызываемой и вызываемой стране</span><span class="sxs-lookup"><span data-stu-id="38320-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="38320-116">В отчете CQD Direct Routing по ННР совокупно метрики надежности и использования для всех SBCs в клиенте за последние 7, 30 или 180 дней (6 месяцев).</span><span class="sxs-lookup"><span data-stu-id="38320-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="38320-117">Данные можно анализировать по типу звонка, SBC, вызываемой и вызываемой стране.</span><span class="sxs-lookup"><span data-stu-id="38320-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="38320-118">Если вас интересует определенная SBC или страна, вы сможете выявлять изменения тенденций в выбранном диапазоне времени.</span><span class="sxs-lookup"><span data-stu-id="38320-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Снимок экрана: фильтры, доступные в отчете "CQD Direct Routing" службы ННР":::
   
2. <span data-ttu-id="38320-120">Отслеживание тенденций</span><span class="sxs-lookup"><span data-stu-id="38320-120">Track trends</span></span>

    <span data-ttu-id="38320-121">Анализ тенденций важен при анализе использования и надежности службы.</span><span class="sxs-lookup"><span data-stu-id="38320-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="38320-122">Почасовые тенденции дают более тщательное представление о ежедневной производительности, что помогает выявлять инциденты в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="38320-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="38320-123">Ежедневные тенденции в долгосрочной перспективе повеяют вас к состоянию работы службы.</span><span class="sxs-lookup"><span data-stu-id="38320-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="38320-124">Важно иметь возможность переключяться между этими двумя режимами с правильной детализацией данных.</span><span class="sxs-lookup"><span data-stu-id="38320-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="38320-125">Отчет CQD Direct Routing через 6 месяцев содержит обзор тенденций, тенденций за 7 и 30 дней, а также почасовые тенденции, чтобы можно было анализировать производительность на каждом уровне.</span><span class="sxs-lookup"><span data-stu-id="38320-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Снимок экрана: графики тенденций в отчете О прямой маршрутке ННР":::

3. <span data-ttu-id="38320-127">Drill through to SBC or user level</span><span class="sxs-lookup"><span data-stu-id="38320-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="38320-128">В CQD мы получили возможность "drill-through", которая позволяет быстро понять, как использовать и надежно распределять данные на уровне SBC или пользователя.</span><span class="sxs-lookup"><span data-stu-id="38320-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="38320-129">С помощью этих упражнений можно быстро реагировать на проблемы и понимать влияние на пользователей.</span><span class="sxs-lookup"><span data-stu-id="38320-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="38320-130">В отчете CQD Direct Routing 995 (Прямой маршрут STN) можно подробно и подробно и без метрики "Детализация службы" и "Коэффициент эффективности сети".</span><span class="sxs-lookup"><span data-stu-id="38320-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="38320-131">Щелкните интересуемую точку данных, чтобы найти подробные сведения на уровне пользователя или SBC.</span><span class="sxs-lookup"><span data-stu-id="38320-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Снимок экрана: возможность drill-through в точке данных":::


## <a name="pstn-overview"></a><span data-ttu-id="38320-133">Общие сведения о ОКП</span><span class="sxs-lookup"><span data-stu-id="38320-133">PSTN Overview</span></span>

<span data-ttu-id="38320-134">Отчет CQD Direct Routing PSTN предоставляет следующие сведения, связанные с общим состоянием службы за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="38320-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="38320-135">![Снимок экрана: отчет CQD ННР](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="38320-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="38320-136">Например, если вас интересуют общие данные об использовании и состоянии всех входящие вызовы, которые проходят через SBC abc.bca.adatum.biz с США в качестве внутренней страны:</span><span class="sxs-lookup"><span data-stu-id="38320-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="38320-137">**Вызов**</span><span class="sxs-lookup"><span data-stu-id="38320-137">**Call Out**</span></span> | <span data-ttu-id="38320-138">**Описание**</span><span class="sxs-lookup"><span data-stu-id="38320-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="38320-139">1</span><span class="sxs-lookup"><span data-stu-id="38320-139">1</span></span>            | <span data-ttu-id="38320-140">Вы можете использовать фильтры в верхней части, чтобы отфильтровать и выбрать ByotIn в качестве типа вызова, abc.bca.contoso.com как контроллер доски сеанса, а США как внутреннюю страну.</span><span class="sxs-lookup"><span data-stu-id="38320-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="38320-141">2</span><span class="sxs-lookup"><span data-stu-id="38320-141">2</span></span>            | <span data-ttu-id="38320-142">Тенденция использования за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="38320-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="38320-143">Подробный отчет об использовании можно найти на странице "Подробности службы".</span><span class="sxs-lookup"><span data-stu-id="38320-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="38320-144">3</span><span class="sxs-lookup"><span data-stu-id="38320-144">3</span></span>            | <span data-ttu-id="38320-145">Публикация тенденций задержки набора, задержки, дрожания и потери пакетов за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="38320-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="38320-146">Подробный отчет можно найти на странице "Параметры сети".</span><span class="sxs-lookup"><span data-stu-id="38320-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="38320-147">4</span><span class="sxs-lookup"><span data-stu-id="38320-147">4</span></span>            | <span data-ttu-id="38320-148">Тенденции одновременного звонка и ежедневного активного пользователя за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="38320-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="38320-149">Эта диаграмма поможет вам понять максимальный объем услуги.</span><span class="sxs-lookup"><span data-stu-id="38320-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="38320-150">5</span><span class="sxs-lookup"><span data-stu-id="38320-150">5</span></span>            | <span data-ttu-id="38320-151">Top Call End Reason affected service quality for the past 180 days.</span><span class="sxs-lookup"><span data-stu-id="38320-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="38320-152">Подробные подробности о состоянии обслуживания можно найти на странице Network Effective Ratio(NER).</span><span class="sxs-lookup"><span data-stu-id="38320-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="38320-153">Сведения о службе</span><span class="sxs-lookup"><span data-stu-id="38320-153">Service Details</span></span>

<span data-ttu-id="38320-154">На этой странице представлена разбивка отзывов пользователей по географическим регионам, а также тенденции использования служб в день.</span><span class="sxs-lookup"><span data-stu-id="38320-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="38320-155">**Общая попытка звонков —** Общее количество звонков в диапазоне времени, включая как успешные, так и сбойные вызовы</span><span class="sxs-lookup"><span data-stu-id="38320-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="38320-156">**Общее количество подключенных звонков —** Общее количество подключенных звонков за этот диапазон времени</span><span class="sxs-lookup"><span data-stu-id="38320-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="38320-157">**Общее количество минут —** Общее использование минут в этом диапазоне времени</span><span class="sxs-lookup"><span data-stu-id="38320-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="38320-158">**Ежедневные активные пользователи (DAU) —** Количество ежедневно активных пользователей, которые сделали хотя бы один подключенный звонок в этот день</span><span class="sxs-lookup"><span data-stu-id="38320-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="38320-159">**Одновременное звонки —** Максимальное количество одновременных активных звонков за минуту</span><span class="sxs-lookup"><span data-stu-id="38320-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="38320-160">**Отзывы пользователей —** Оценка "Оценить мой звонок" поступает от пользователя.</span><span class="sxs-lookup"><span data-stu-id="38320-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="38320-161">3–5 считается хорошим звонбом.</span><span class="sxs-lookup"><span data-stu-id="38320-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="38320-162">1–2 считается плохим звоном.</span><span class="sxs-lookup"><span data-stu-id="38320-162">1-2 is considered as a bad call.</span></span>

![Снимок экрана: отчет CQD ННР](media/CQD-PSTN-report2.png)

<span data-ttu-id="38320-164">Например:</span><span class="sxs-lookup"><span data-stu-id="38320-164">For example:</span></span>

1.  <span data-ttu-id="38320-165">Если вы видите, что средняя длительность звонка снижается до 0 в 14.02.2020, вы можете сначала проверить, выглядит ли громкость звонка нормальной, и посмотрите, не слишком ли общее количество звонков и общее количество попыток звонков.</span><span class="sxs-lookup"><span data-stu-id="38320-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="38320-166">Затем перейдите на страницу "Коэффициент эффективности сети", чтобы оценить причины сбоя звонка.</span><span class="sxs-lookup"><span data-stu-id="38320-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="38320-167">Если на карте отзывов пользователей есть все чаще и больше красных мест, можно перейти на страницу "Коэффициент эффективности сети" и "Параметр сети", чтобы узнать, есть ли аномалии, и с помощью службы MS Service Desk можно получить вопрос.</span><span class="sxs-lookup"><span data-stu-id="38320-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="38320-168">Коэффициент эффективности сети</span><span class="sxs-lookup"><span data-stu-id="38320-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="38320-169">Это та же метрика, которая отображается на панели мониторинга "Общее состояние".</span><span class="sxs-lookup"><span data-stu-id="38320-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="38320-170">Вы можете проверить почасовой номер NER с подробными подробностями о звонках для обоих направлений (входящие и исходящие) на основе соотношения эффективности сети с почасовой эффективностью и конечной причины звонков ниже.</span><span class="sxs-lookup"><span data-stu-id="38320-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="38320-171">**NER** — возможность (%) в сети для доставки звонков путем определения количества отправленных звонков и числа звонков, доставленных получателю.</span><span class="sxs-lookup"><span data-stu-id="38320-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="38320-172">**Код ответа SIP:** трехзначный код ответа с цифрой в три цифры показывает состояние звонка.</span><span class="sxs-lookup"><span data-stu-id="38320-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="38320-173">**Код ответа Майкрософт**— код ответа, отправленный из компонента Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="38320-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="38320-174">**Описание** — этап причины, соответствующий коду ответа SIP и коду ответа Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="38320-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="38320-175">**Число звонков,** на которые влияет влияние: общее количество звонков за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="38320-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Снимок экрана: отчет CQD ННР](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="38320-177">Например:</span><span class="sxs-lookup"><span data-stu-id="38320-177">For example:</span></span>

![Снимок экрана: отчет CQD ННР](media/CQD-PSTN-report4.png)

<span data-ttu-id="38320-179">Если 05.02.2020 у сотрудников NER что-то не так, вы можете щелкнуть дату, и другие диаграммы будут масштабироваться до этой даты.</span><span class="sxs-lookup"><span data-stu-id="38320-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Снимок экрана: отчет CQD ННР](media/CQD-PSTN-report5.png)

<span data-ttu-id="38320-181">С хорошим процентным трендом NER можно увидеть, что падение происходит около 21:00.</span><span class="sxs-lookup"><span data-stu-id="38320-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="38320-182">Затем щелкните еще раз, чтобы увеличить масштаб до 21 часа, и проверьте сведения об эффекте звонков, чтобы узнать, сколько звонков не удалось сделать в этот час и каковы причины окончания звонка.</span><span class="sxs-lookup"><span data-stu-id="38320-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="38320-183">Если проблема не связана с SBC, вы можете не беспокоиться о проблемах или отчетах в службе service Desk.</span><span class="sxs-lookup"><span data-stu-id="38320-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="38320-184">Параметры сети</span><span class="sxs-lookup"><span data-stu-id="38320-184">Network Parameters</span></span>

<span data-ttu-id="38320-185">Все параметры сети измеряется от интерфейса прямой маршрутки до граничного геймпада сеанса.</span><span class="sxs-lookup"><span data-stu-id="38320-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="38320-186">Сведения о рекомендуемых значениях см. в подготовке сети организации для [Microsoft Teams](prepare-network.md)и рекомендуемых значениях в microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="38320-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="38320-187">**Jitter** — это миллисекундный показатель разброса времени распространения по сети, вычисляемого между двумя конечными точками с помощью RTCP (протокола управления RTP).</span><span class="sxs-lookup"><span data-stu-id="38320-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="38320-188">**Packet Loss** — это показатель пакета, который не удалось получить; вычисляется между двумя конечными точками.</span><span class="sxs-lookup"><span data-stu-id="38320-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="38320-189">**Задержка (также** называется время кругового пути) — это время, необходимое для сигнала, а также время его подтверждения.</span><span class="sxs-lookup"><span data-stu-id="38320-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="38320-190">Это время задержки представляет собой время распространения между двумя точками сигнала.</span><span class="sxs-lookup"><span data-stu-id="38320-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Снимок экрана: отчет CQD ННР](media/CQD-PSTN-report6.png)

<span data-ttu-id="38320-192">Например:</span><span class="sxs-lookup"><span data-stu-id="38320-192">For example:</span></span>

<span data-ttu-id="38320-193">Если в какой-либо из четырех диаграмм (например, 14.02.2020) вы видите пик задержку (задержку, дрожание, коэффициент потерь пакетов, задержка после набора номеров) для определенной даты, щелкните дату.</span><span class="sxs-lookup"><span data-stu-id="38320-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="38320-194">При этом ежечасная диаграмма тренда внизу обновиться, чтобы показать ее ежечасно.</span><span class="sxs-lookup"><span data-stu-id="38320-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="38320-195">Вы можете проверить SBCs или собрать вопрос в службе ms Service Desk.</span><span class="sxs-lookup"><span data-stu-id="38320-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Снимок экрана: отчет CQD ННР](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="38320-197">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="38320-197">Related topics</span></span>

[<span data-ttu-id="38320-198">Анализ данных CQD для Microsoft Teams с помощью Power BI</span><span class="sxs-lookup"><span data-stu-id="38320-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="38320-199">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="38320-199">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)