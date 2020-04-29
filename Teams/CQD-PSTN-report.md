---
title: Использование отчета о прямой маршрутизации CQD PSTN
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
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
description: Используйте отчет о прямой маршрутизации CQD КТСОП для контроля и устранения неполадок, связанных с использованием PSTN в Microsoft Teams.
ms.openlocfilehash: 32d91d56e51c5706c3e460029312f3b6bb6948c3
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559615"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="3ca81-103">Использование отчета о прямой маршрутизации CQD PSTN</span><span class="sxs-lookup"><span data-stu-id="3ca81-103">Using the CQD PSTN Direct Routing Report</span></span>

<span data-ttu-id="3ca81-104">Новая версия в марте 2020 добавлена в [шаблоны запросов на Power BI для CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true), CQD КТСОП Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="3ca81-104">New in March 2020, we've added a CQD PSTN Direct Routing Report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="3ca81-105">Отчет об использовании прямой маршрутизации CQD PSTN помогает клиентам понять принципы использования и качество обслуживания своих служб PSTN, а также сведения о том, что такое служба телефонной связи, параметры сети и отношение к эффективности сети и использование службы.</span><span class="sxs-lookup"><span data-stu-id="3ca81-105">The CQD PSTN Direct Routing Report helps customers to understand the usage patterns and quality of their PSTN services monitor information about your SBC, the telephony service, the network parameters, and Network Effectiveness Ratio details and usage of the service.</span></span> <span data-ttu-id="3ca81-106">Эти сведения помогут вам определить проблемы, в том числе причину прерванных звонков.</span><span class="sxs-lookup"><span data-stu-id="3ca81-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="3ca81-107">Например, вы будете знать, когда громкость снижается, сколько звонков повлияет на все причины.</span><span class="sxs-lookup"><span data-stu-id="3ca81-107">For example, you will be able to know when volume drops, how many calls get affected by what reason.</span></span>

<span data-ttu-id="3ca81-108">В отчете о маршрутизации CQD PSTN есть четыре раздела:</span><span class="sxs-lookup"><span data-stu-id="3ca81-108">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="3ca81-109">Общие сведения о PSTN</span><span class="sxs-lookup"><span data-stu-id="3ca81-109">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="3ca81-110">Сведения о службе</span><span class="sxs-lookup"><span data-stu-id="3ca81-110">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="3ca81-111">Коэффициент эффективности сети</span><span class="sxs-lookup"><span data-stu-id="3ca81-111">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="3ca81-112">Сетевые параметры</span><span class="sxs-lookup"><span data-stu-id="3ca81-112">Network Parameters</span></span>](#network-parameters)

## <a name="pstn-overview"></a><span data-ttu-id="3ca81-113">Общие сведения о PSTN</span><span class="sxs-lookup"><span data-stu-id="3ca81-113">PSTN Overview</span></span>

<span data-ttu-id="3ca81-114">В отчете о маршрутизации CQD PSTN указаны следующие сведения, относящиеся к общей работоспособности службы за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="3ca81-114">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="3ca81-115">![Снимок экрана: отчет о PSTN CQD](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="3ca81-115">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="3ca81-116">Например, если вы заинтересованы в общем использовании и работоспособности всех входящих звонков, которые проходит через SBC abc.bca.adatum.biz с нами в качестве внутренней страны, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="3ca81-116">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="3ca81-117">**Вызовите**</span><span class="sxs-lookup"><span data-stu-id="3ca81-117">**Call Out**</span></span> | <span data-ttu-id="3ca81-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3ca81-118">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="3ca81-119">1</span><span class="sxs-lookup"><span data-stu-id="3ca81-119">1</span></span>            | <span data-ttu-id="3ca81-120">Вы можете использовать фильтры в верхней части экрана для детализации и выбрать ByotIn в качестве типа звонка, abc.bca.contoso.com в качестве контроллера сеанса и в качестве внутренней страны.</span><span class="sxs-lookup"><span data-stu-id="3ca81-120">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="3ca81-121">2</span><span class="sxs-lookup"><span data-stu-id="3ca81-121">2</span></span>            | <span data-ttu-id="3ca81-122">Тенденция использования за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="3ca81-122">Usage trend for the past 180 days.</span></span> <span data-ttu-id="3ca81-123">Вы можете найти подробный отчет об использовании на странице сведений о службе.</span><span class="sxs-lookup"><span data-stu-id="3ca81-123">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="3ca81-124">3</span><span class="sxs-lookup"><span data-stu-id="3ca81-124">3</span></span>            | <span data-ttu-id="3ca81-125">Задержка набора номера, задержка, колебание и тенденция потери пакетов за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="3ca81-125">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="3ca81-126">Вы можете найти подробный отчет на странице Параметры сети.</span><span class="sxs-lookup"><span data-stu-id="3ca81-126">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="3ca81-127">4</span><span class="sxs-lookup"><span data-stu-id="3ca81-127">4</span></span>            | <span data-ttu-id="3ca81-128">Одновременный звонок и дневная активная тенденция пользователей за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="3ca81-128">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="3ca81-129">Эта диаграмма поможет вам понять, как это максимальный объем услуг.</span><span class="sxs-lookup"><span data-stu-id="3ca81-129">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="3ca81-130">5</span><span class="sxs-lookup"><span data-stu-id="3ca81-130">5</span></span>            | <span data-ttu-id="3ca81-131">Причина, по которой заканчивается качество обслуживания по верхнему краю за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="3ca81-131">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="3ca81-132">Вы можете найти сведения о работоспособности службы на странице коэффициент эффективности сети (NER).</span><span class="sxs-lookup"><span data-stu-id="3ca81-132">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="3ca81-133">Сведения о службе</span><span class="sxs-lookup"><span data-stu-id="3ca81-133">Service Details</span></span>

<span data-ttu-id="3ca81-134">Эта страница обеспечивает тенденции использования служб за день и отзыв пользователей по географическим подразделениям.</span><span class="sxs-lookup"><span data-stu-id="3ca81-134">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="3ca81-135">**Всего попыток вызова:** Общее количество одновременных звонков в указанном диапазоне времени, включая успешные и неудачные вызовы</span><span class="sxs-lookup"><span data-stu-id="3ca81-135">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="3ca81-136">**Общее количество подключенных звонков-** Общее количество подключенных вызовов в указанном диапазоне времени</span><span class="sxs-lookup"><span data-stu-id="3ca81-136">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="3ca81-137">**Всего минут –** Общее использование минут в указанном диапазоне времени</span><span class="sxs-lookup"><span data-stu-id="3ca81-137">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="3ca81-138">**Ежедневные активные пользователи (DAU) —** Количество активных пользователей, которые выполнили по крайней мере один подключенный Звонок в этот день.</span><span class="sxs-lookup"><span data-stu-id="3ca81-138">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="3ca81-139">**Одновременные звонки:** Максимум одновременных активных звонков за минуту</span><span class="sxs-lookup"><span data-stu-id="3ca81-139">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="3ca81-140">**Отзывы пользователей:** "Оценить баллы о звонке", поступает от пользователя.</span><span class="sxs-lookup"><span data-stu-id="3ca81-140">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="3ca81-141">3-5 считается хорошим звонком.</span><span class="sxs-lookup"><span data-stu-id="3ca81-141">3-5 is considered as a good call.</span></span> <span data-ttu-id="3ca81-142">1-2 считается неправильным звонком.</span><span class="sxs-lookup"><span data-stu-id="3ca81-142">1-2 is considered as a bad call.</span></span>

![Снимок экрана: отчет о PSTN CQD](media/CQD-PSTN-report2.png)

<span data-ttu-id="3ca81-144">Например:</span><span class="sxs-lookup"><span data-stu-id="3ca81-144">For example:</span></span>

1.  <span data-ttu-id="3ca81-145">Если вы видите среднюю длительность звонка в 0 в 02/14/2020, вы можете сначала проверить, выглядит ли громкость звонка обычно, и узнать, есть ли существенные отличия между общим соединением и общим количеством одновременных звонков.</span><span class="sxs-lookup"><span data-stu-id="3ca81-145">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="3ca81-146">Затем перейдите на страницу коэффициента эффективности сети, чтобы присоединиться к причине ошибки звонка.</span><span class="sxs-lookup"><span data-stu-id="3ca81-146">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="3ca81-147">Если вы видите более красные пятна на карте отзывов пользователей, вы можете перейти на страницу коэффициента эффективности сети и сетевой параметр, чтобы проверить, есть ли какие-либо аномалии, и вы можете создать билет с помощью службы поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3ca81-147">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="3ca81-148">Коэффициент эффективности сети</span><span class="sxs-lookup"><span data-stu-id="3ca81-148">Network Effectiveness Ratio</span></span>

<span data-ttu-id="3ca81-149">Это та же метрика, которая отображается на общей информационной панели мониторинга работоспособности.</span><span class="sxs-lookup"><span data-stu-id="3ca81-149">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="3ca81-150">Вы можете проверить почасовое NER число с помощью сведений о вызываемых звонках для обоих направлений звонка (входящий/исходящий трафик) на почасовом соотношении эффективности сети и конечной причины звонка ниже.</span><span class="sxs-lookup"><span data-stu-id="3ca81-150">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="3ca81-151">**NER** — возможность (%) сети, чтобы доставлять звонки, измеряя количество отправленных звонков и количество звонков, доставленных получателю.</span><span class="sxs-lookup"><span data-stu-id="3ca81-151">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="3ca81-152">**Код ответа SIP**— трехзначный целочисленный код ответа показывает состояние вызова.</span><span class="sxs-lookup"><span data-stu-id="3ca81-152">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="3ca81-153">**Код ответа Microsoft**— код ответа, отправленный из компонента Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ca81-153">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="3ca81-154">**Описание** — этап причины, соответствующий коду ответа SIP и коду ответа Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ca81-154">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="3ca81-155">**Количество затронутых звонков** — общее количество звонков, которые были затронуты в течение выбранного интервала времени.</span><span class="sxs-lookup"><span data-stu-id="3ca81-155">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Снимок экрана: отчет о PSTN CQD](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="3ca81-157">Например:</span><span class="sxs-lookup"><span data-stu-id="3ca81-157">For example:</span></span>

![Снимок экрана: отчет о PSTN CQD](media/CQD-PSTN-report4.png)

<span data-ttu-id="3ca81-159">Если для ежедневного NER установлен DIP-значение в 02/05/2020, вы можете щелкнуть дату, и другие диаграммы будут масштабироваться до указанной даты.</span><span class="sxs-lookup"><span data-stu-id="3ca81-159">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Снимок экрана: отчет о PSTN CQD](media/CQD-PSTN-report5.png)

<span data-ttu-id="3ca81-161">С почасовой NERой процентной тенденции вы можете найти DIP, выступающей около 21:00.</span><span class="sxs-lookup"><span data-stu-id="3ca81-161">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="3ca81-162">Затем щелкните еще раз, чтобы перейти к часу 21 и проверить сведения о вызываемом звонке, чтобы узнать, сколько произошел сбой звонков в течение этого часа и каковы причины, по которым нужно закончить звонок.</span><span class="sxs-lookup"><span data-stu-id="3ca81-162">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="3ca81-163">Вы можете приступить к устранению проблем, связанных с SBC, или сообщить в службу поддержки, если проблема не связана с SBC.</span><span class="sxs-lookup"><span data-stu-id="3ca81-163">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="3ca81-164">Сетевые параметры</span><span class="sxs-lookup"><span data-stu-id="3ca81-164">Network Parameters</span></span>

<span data-ttu-id="3ca81-165">Все сетевые параметры измеряются от интерфейса Direct Routing на контроллере границ сеанса.</span><span class="sxs-lookup"><span data-stu-id="3ca81-165">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="3ca81-166">Дополнительные сведения о рекомендуемых значениях можно найти в [статье Подготовка сети организации для Microsoft Teams](prepare-network.md)и ознакомьтесь со статьей "клиент" в разделе "Рекомендуемые значения Microsoft Edge".</span><span class="sxs-lookup"><span data-stu-id="3ca81-166">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="3ca81-167">**Колебание** — это величина, которая измеряется в миллисекундах времени задержки распространения сети, вычисленной между двумя конечными точками с помощью RTCP (протокол управления RTP).</span><span class="sxs-lookup"><span data-stu-id="3ca81-167">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="3ca81-168">**Потери пакетов** — это мера пакета, который не удалось получить; Она вычисляется между двумя конечными точками.</span><span class="sxs-lookup"><span data-stu-id="3ca81-168">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="3ca81-169">**Задержка** (также известная как время кругового поездки) — продолжительность отправки сигнала и время, необходимое для подтверждения подлинности этого сигнала.</span><span class="sxs-lookup"><span data-stu-id="3ca81-169">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="3ca81-170">Это время задержки состоит из времени распространения между двумя точками сигнала.</span><span class="sxs-lookup"><span data-stu-id="3ca81-170">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Снимок экрана: отчет о PSTN CQD](media/CQD-PSTN-report6.png)

<span data-ttu-id="3ca81-172">Например:</span><span class="sxs-lookup"><span data-stu-id="3ca81-172">For example:</span></span>

<span data-ttu-id="3ca81-173">Если вы видите копилку на любой из четырех диаграмм (задержка, колебание, частота потерь пакетов, задержка набора номера) для определенной даты, например задержка в 02/14/2020, щелкните точку даты.</span><span class="sxs-lookup"><span data-stu-id="3ca81-173">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="3ca81-174">А диаграмма почасового тренда внизу будет обновлена, чтобы показать почасовое число.</span><span class="sxs-lookup"><span data-stu-id="3ca81-174">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="3ca81-175">Вы можете проверить SBCs или создать билет с помощью службы MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="3ca81-175">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Снимок экрана: отчет о PSTN CQD](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="3ca81-177">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3ca81-177">Related topics</span></span>

[<span data-ttu-id="3ca81-178">Анализ данных CQD в Microsoft Teams с помощью Power BI</span><span class="sxs-lookup"><span data-stu-id="3ca81-178">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)