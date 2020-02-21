---
title: 'Lync Server 2013: отчеты QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 353e0941f443e2cb971f8ebd037413232e21b827
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="d8027-102">Отчеты QoE в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8027-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8027-103">_**Последнее изменение темы:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="d8027-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="d8027-104">Отчеты о тенденциях и тенденциях QoE</span><span class="sxs-lookup"><span data-stu-id="d8027-104">QoE summary/trend reports</span></span>

<span data-ttu-id="d8027-105">Отчеты сводки и тенденций QoE полезны для поиска пикового времени использования и изучения качества мультимедиа в это время, чтобы обеспечить достаточные сетевые ресурсы Организации.</span><span class="sxs-lookup"><span data-stu-id="d8027-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="d8027-106">В организации также можно использовать многие фильтры, доступные в отчете, чтобы изолировать номера производительности для определенных расположений, типов клиентов и устройств, а также серверов.</span><span class="sxs-lookup"><span data-stu-id="d8027-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="d8027-107">Сводный отчет о QoE и тенденциях состоят из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="d8027-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="d8027-108">Сводный отчет по объединению Объединенных коммуникаций и тенденций</span><span class="sxs-lookup"><span data-stu-id="d8027-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="d8027-109">Сводный отчет по КТСОП/тенденции</span><span class="sxs-lookup"><span data-stu-id="d8027-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="d8027-110">Сводный отчет по конференциям/тенденцию</span><span class="sxs-lookup"><span data-stu-id="d8027-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="d8027-111">Отчеты о производительности QoE</span><span class="sxs-lookup"><span data-stu-id="d8027-111">QoE performance reports</span></span>

<span data-ttu-id="d8027-112">Отчеты о производительности QoE предоставляют подробные сведения о трех отчетах, которые сосредоточены на производительности серверов-посредников, серверов аудио-и видеоконференций и расположений конечных точек QoE.</span><span class="sxs-lookup"><span data-stu-id="d8027-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="d8027-113">Отчет о производительности сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="d8027-113">Mediation server performance report</span></span>

<span data-ttu-id="d8027-114">В отчете о производительности сервера-посредника перечислены показатели, достигнутые одним или несколькими исправлениями в течение заданного периода времени.</span><span class="sxs-lookup"><span data-stu-id="d8027-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="d8027-115">Сведения о метриках сервера единой системы обмена сообщениями (UC) и шлюза посредника между шлюзами каждого вызова указаны отдельно.</span><span class="sxs-lookup"><span data-stu-id="d8027-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="d8027-116">Используйте этот отчет для сравнения объема и производительности различных серверов-посредников вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d8027-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="d8027-117">Для каждого сервера-посредника (и для каждой стороны звонка) в отчете отображается следующее:</span><span class="sxs-lookup"><span data-stu-id="d8027-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="d8027-118">Количество вызовов</span><span class="sxs-lookup"><span data-stu-id="d8027-118">Number of calls</span></span>

  - <span data-ttu-id="d8027-119">Потеря пакетов</span><span class="sxs-lookup"><span data-stu-id="d8027-119">Packet Loss</span></span>

  - <span data-ttu-id="d8027-120">Время кругового пути</span><span class="sxs-lookup"><span data-stu-id="d8027-120">Round Trip Time</span></span>

  - <span data-ttu-id="d8027-121">Колебани</span><span class="sxs-lookup"><span data-stu-id="d8027-121">Jitter</span></span>

  - <span data-ttu-id="d8027-122">Оценка мнения общения (MOS)</span><span class="sxs-lookup"><span data-stu-id="d8027-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="d8027-123">Отправка MOS</span><span class="sxs-lookup"><span data-stu-id="d8027-123">Sending MOS</span></span>

  - <span data-ttu-id="d8027-124">Прослушивание MOS</span><span class="sxs-lookup"><span data-stu-id="d8027-124">Listening MOS</span></span>

  - <span data-ttu-id="d8027-125">Сетевые MOS</span><span class="sxs-lookup"><span data-stu-id="d8027-125">Network MOS</span></span>

  - <span data-ttu-id="d8027-126">Снижение производительности сети MOS</span><span class="sxs-lookup"><span data-stu-id="d8027-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="d8027-127">Возврат эха</span><span class="sxs-lookup"><span data-stu-id="d8027-127">Echo Return</span></span>

  - <span data-ttu-id="d8027-128">Уровень сигнала</span><span class="sxs-lookup"><span data-stu-id="d8027-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="d8027-129">Отчет о производительности сервера аудио-и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="d8027-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="d8027-130">В отчете о производительности сервера аудио-и видеоконференций представлены списки метрик, полученные одним или несколькими серверами аудио-и видеоконференций в течение заданного периода времени.</span><span class="sxs-lookup"><span data-stu-id="d8027-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="d8027-131">Этот отчет можно использовать для сравнения объема и производительности различных серверов аудио-и видеоконференций Организации.</span><span class="sxs-lookup"><span data-stu-id="d8027-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="d8027-132">В организации также можно изолировать отчет, чтобы отображался только интерфейс для определенных типов клиентов, например клиентов Lync или клиентов PSTN.</span><span class="sxs-lookup"><span data-stu-id="d8027-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="d8027-133">Для каждого сервера аудио-и видеоконференций, в отчете отображается следующее:</span><span class="sxs-lookup"><span data-stu-id="d8027-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="d8027-134">Количество конференций</span><span class="sxs-lookup"><span data-stu-id="d8027-134">Number of conferences</span></span>

  - <span data-ttu-id="d8027-135">Потеря пакетов</span><span class="sxs-lookup"><span data-stu-id="d8027-135">Packet Loss</span></span>

  - <span data-ttu-id="d8027-136">Время кругового пути</span><span class="sxs-lookup"><span data-stu-id="d8027-136">Round Trip Time</span></span>

  - <span data-ttu-id="d8027-137">Колебани</span><span class="sxs-lookup"><span data-stu-id="d8027-137">Jitter</span></span>

  - <span data-ttu-id="d8027-138">Оценка мнения общения (MOS)</span><span class="sxs-lookup"><span data-stu-id="d8027-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="d8027-139">Отправка MOS</span><span class="sxs-lookup"><span data-stu-id="d8027-139">Sending MOS</span></span>

  - <span data-ttu-id="d8027-140">Прослушивание MOS</span><span class="sxs-lookup"><span data-stu-id="d8027-140">Listening MOS</span></span>

  - <span data-ttu-id="d8027-141">Сетевые MOS</span><span class="sxs-lookup"><span data-stu-id="d8027-141">Network MOS</span></span>

  - <span data-ttu-id="d8027-142">Снижение производительности сети MOS</span><span class="sxs-lookup"><span data-stu-id="d8027-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="d8027-143">Возврат эха</span><span class="sxs-lookup"><span data-stu-id="d8027-143">Echo Return</span></span>

  - <span data-ttu-id="d8027-144">Уровень сигнала</span><span class="sxs-lookup"><span data-stu-id="d8027-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="d8027-145">Отчет о производительности на основе расположения</span><span class="sxs-lookup"><span data-stu-id="d8027-145">Location-based performance report</span></span>

<span data-ttu-id="d8027-146">В отчете о производительности на основе расположения представлен список сетевых расположений и для каждого местоположения отображается количество вызовов в каждом предварительно определенном диапазоне качества.</span><span class="sxs-lookup"><span data-stu-id="d8027-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="d8027-147">Цель этого отчета заключается в том, чтобы узнать, как получить сведения о качестве массовых телефонных звонков в Организации для различных расположений, чтобы можно было определить неплохо выполняемые расположения и посмотреть различные оценки качества мультимедиа в Организации разных расположениях.</span><span class="sxs-lookup"><span data-stu-id="d8027-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="d8027-148">При отображении отчета отображаются различные таблицы метрики — по одной таблице для каждой метрики, на которую Организация решает отчитываться.</span><span class="sxs-lookup"><span data-stu-id="d8027-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="d8027-149">Для этого отчета можно выбрать один из следующих показателей:</span><span class="sxs-lookup"><span data-stu-id="d8027-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="d8027-150">Оценка мнения общения (MOS)</span><span class="sxs-lookup"><span data-stu-id="d8027-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="d8027-151">Сетевые MOS</span><span class="sxs-lookup"><span data-stu-id="d8027-151">Network MOS</span></span>

  - <span data-ttu-id="d8027-152">Снижение производительности сети MOS</span><span class="sxs-lookup"><span data-stu-id="d8027-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="d8027-153">Отправка MOS</span><span class="sxs-lookup"><span data-stu-id="d8027-153">Sending MOS</span></span>

  - <span data-ttu-id="d8027-154">Прослушивание MOS</span><span class="sxs-lookup"><span data-stu-id="d8027-154">Listening MOS</span></span>

  - <span data-ttu-id="d8027-155">Потеря пакетов</span><span class="sxs-lookup"><span data-stu-id="d8027-155">Packet Loss</span></span>

  - <span data-ttu-id="d8027-156">Колебани</span><span class="sxs-lookup"><span data-stu-id="d8027-156">Jitter</span></span>

  - <span data-ttu-id="d8027-157">Задержка</span><span class="sxs-lookup"><span data-stu-id="d8027-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

