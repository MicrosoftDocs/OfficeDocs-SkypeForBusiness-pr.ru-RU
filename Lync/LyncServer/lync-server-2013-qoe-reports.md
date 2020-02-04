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
ms.openlocfilehash: 9eead17e9cd08267f941d80cb25460f4d456d896
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="d2784-102">QoE отчеты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2784-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2784-103">_**Тема последнего изменения:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="d2784-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="d2784-104">QoE/отчеты о тенденциях</span><span class="sxs-lookup"><span data-stu-id="d2784-104">QoE summary/trend reports</span></span>

<span data-ttu-id="d2784-105">Отчеты о сводных данных и тенденциях QoE помогают найти пиковое время использования и проанализировать качество мультимедиа в течение этого периода, чтобы убедиться в том, что сетевые ресурсы Организации достаточны.</span><span class="sxs-lookup"><span data-stu-id="d2784-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="d2784-106">В организации также могут использоваться многочисленные фильтры, доступные в отчете, чтобы изолировать номера производительности для определенных местоположений, типов клиентов и устройств и серверов.</span><span class="sxs-lookup"><span data-stu-id="d2784-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="d2784-107">QoE отчеты о тенденциях и тенденции состоят из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="d2784-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="d2784-108">Отчет о сводных данных и тенденциях UC-связи</span><span class="sxs-lookup"><span data-stu-id="d2784-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="d2784-109">Отчет о PSTN и тенденциях</span><span class="sxs-lookup"><span data-stu-id="d2784-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="d2784-110">Отчет о конференциях и тенденциях</span><span class="sxs-lookup"><span data-stu-id="d2784-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="d2784-111">Отчеты о производительности QoE</span><span class="sxs-lookup"><span data-stu-id="d2784-111">QoE performance reports</span></span>

<span data-ttu-id="d2784-112">В отчетах о производительности QoE содержатся сведения об этих трех отчетах, которые сосредоточены на QoE производительности серверов-конференций, серверах Конференции и расположениях конечных точек.</span><span class="sxs-lookup"><span data-stu-id="d2784-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="d2784-113">Отчет о производительности сервера «исправление»</span><span class="sxs-lookup"><span data-stu-id="d2784-113">Mediation server performance report</span></span>

<span data-ttu-id="d2784-114">В отчете "производительность сервера исправлений" перечислены метрики, достигнутые одним или несколькими исправлениями за указанный период времени.</span><span class="sxs-lookup"><span data-stu-id="d2784-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="d2784-115">Метрики сервера единой системы обмена сообщениями (UC), а также сведения о том, как перенаправляться между шлюзами, выводятся отдельно для каждого звонка.</span><span class="sxs-lookup"><span data-stu-id="d2784-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="d2784-116">С помощью этого отчета вы можете сравнить объем и производительность различных серверов-посредников вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d2784-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="d2784-117">Для каждого сервера-посредника (и для каждого участка звонка) в отчете выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="d2784-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="d2784-118">Число звонков</span><span class="sxs-lookup"><span data-stu-id="d2784-118">Number of calls</span></span>

  - <span data-ttu-id="d2784-119">Packet Loss (Потеря пакетов)</span><span class="sxs-lookup"><span data-stu-id="d2784-119">Packet Loss</span></span>

  - <span data-ttu-id="d2784-120">Время круга</span><span class="sxs-lookup"><span data-stu-id="d2784-120">Round Trip Time</span></span>

  - <span data-ttu-id="d2784-121">Искажение</span><span class="sxs-lookup"><span data-stu-id="d2784-121">Jitter</span></span>

  - <span data-ttu-id="d2784-122">Предметный балл — Оценка вашего мнения (MOS)</span><span class="sxs-lookup"><span data-stu-id="d2784-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="d2784-123">Отправка MOS</span><span class="sxs-lookup"><span data-stu-id="d2784-123">Sending MOS</span></span>

  - <span data-ttu-id="d2784-124">Прослушивание MOS</span><span class="sxs-lookup"><span data-stu-id="d2784-124">Listening MOS</span></span>

  - <span data-ttu-id="d2784-125">Сетевые MOS</span><span class="sxs-lookup"><span data-stu-id="d2784-125">Network MOS</span></span>

  - <span data-ttu-id="d2784-126">Сетевое MOS падение</span><span class="sxs-lookup"><span data-stu-id="d2784-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="d2784-127">Echo Return</span><span class="sxs-lookup"><span data-stu-id="d2784-127">Echo Return</span></span>

  - <span data-ttu-id="d2784-128">Уровень сигнала</span><span class="sxs-lookup"><span data-stu-id="d2784-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="d2784-129">Отчет о производительности сервера конференций/V</span><span class="sxs-lookup"><span data-stu-id="d2784-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="d2784-130">Отчет о производительности сервера конференц-связи "A/V" предоставляет списки метрик, достигнутые одним или несколькими серверами конференц-связи в течение заданного периода времени.</span><span class="sxs-lookup"><span data-stu-id="d2784-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="d2784-131">Этот отчет можно использовать для сравнения объема и производительности различных серверов конференц-связи в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d2784-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="d2784-132">В организации также можно изолировать отчет, чтобы отображались только сведения о конкретных типах клиентов, например клиентах Lync и клиентах PSTN.</span><span class="sxs-lookup"><span data-stu-id="d2784-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="d2784-133">Для каждого сервера конференций/V в отчете выводятся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d2784-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="d2784-134">Количество конференций</span><span class="sxs-lookup"><span data-stu-id="d2784-134">Number of conferences</span></span>

  - <span data-ttu-id="d2784-135">Packet Loss (Потеря пакетов)</span><span class="sxs-lookup"><span data-stu-id="d2784-135">Packet Loss</span></span>

  - <span data-ttu-id="d2784-136">Время круга</span><span class="sxs-lookup"><span data-stu-id="d2784-136">Round Trip Time</span></span>

  - <span data-ttu-id="d2784-137">Искажение</span><span class="sxs-lookup"><span data-stu-id="d2784-137">Jitter</span></span>

  - <span data-ttu-id="d2784-138">Предметный балл — Оценка вашего мнения (MOS)</span><span class="sxs-lookup"><span data-stu-id="d2784-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="d2784-139">Отправка MOS</span><span class="sxs-lookup"><span data-stu-id="d2784-139">Sending MOS</span></span>

  - <span data-ttu-id="d2784-140">Прослушивание MOS</span><span class="sxs-lookup"><span data-stu-id="d2784-140">Listening MOS</span></span>

  - <span data-ttu-id="d2784-141">Сетевые MOS</span><span class="sxs-lookup"><span data-stu-id="d2784-141">Network MOS</span></span>

  - <span data-ttu-id="d2784-142">Сетевое MOS падение</span><span class="sxs-lookup"><span data-stu-id="d2784-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="d2784-143">Echo Return</span><span class="sxs-lookup"><span data-stu-id="d2784-143">Echo Return</span></span>

  - <span data-ttu-id="d2784-144">Уровень сигнала</span><span class="sxs-lookup"><span data-stu-id="d2784-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="d2784-145">Отчет о производительности на основе местоположения</span><span class="sxs-lookup"><span data-stu-id="d2784-145">Location-based performance report</span></span>

<span data-ttu-id="d2784-146">Отчет о производительности на основе местоположения содержит список сетевых расположений и для каждого местоположения показывает количество звонков в каждый предварительно определенный диапазон качества.</span><span class="sxs-lookup"><span data-stu-id="d2784-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="d2784-147">Цель этого отчета — обеспечить более подробное представление о том, как достичь большого количества телефонных звонков в вашей организации для различных местоположений, чтобы вы могли выявлять некачественные места и просматривать различные оценки качества мультимедиа в вашей организации разных местоположений.</span><span class="sxs-lookup"><span data-stu-id="d2784-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="d2784-148">При отображении отчета появятся различные таблицы метрик — по одной таблице для каждой метрики, на которую вы решаете сообщить в Организации.</span><span class="sxs-lookup"><span data-stu-id="d2784-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="d2784-149">Для этого отчета можно выбрать следующие метрики:</span><span class="sxs-lookup"><span data-stu-id="d2784-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="d2784-150">Предметный балл — Оценка вашего мнения (MOS)</span><span class="sxs-lookup"><span data-stu-id="d2784-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="d2784-151">Сетевые MOS</span><span class="sxs-lookup"><span data-stu-id="d2784-151">Network MOS</span></span>

  - <span data-ttu-id="d2784-152">Сетевое MOS падение</span><span class="sxs-lookup"><span data-stu-id="d2784-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="d2784-153">Отправка MOS</span><span class="sxs-lookup"><span data-stu-id="d2784-153">Sending MOS</span></span>

  - <span data-ttu-id="d2784-154">Прослушивание MOS</span><span class="sxs-lookup"><span data-stu-id="d2784-154">Listening MOS</span></span>

  - <span data-ttu-id="d2784-155">Packet Loss (Потеря пакетов)</span><span class="sxs-lookup"><span data-stu-id="d2784-155">Packet Loss</span></span>

  - <span data-ttu-id="d2784-156">Искажение</span><span class="sxs-lookup"><span data-stu-id="d2784-156">Jitter</span></span>

  - <span data-ttu-id="d2784-157">Задержка</span><span class="sxs-lookup"><span data-stu-id="d2784-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

