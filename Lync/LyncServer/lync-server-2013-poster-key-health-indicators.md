---
title: 'Lync Server 2013: Афиша: ключевые индикаторы работоспособности'
description: 'Lync Server 2013: Афиша: ключевые индикаторы работоспособности.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9962d1764d5d2c664bb8415261344d9b48c81149
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566345"
---
# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="2fb93-103">Ключевые индикаторы работоспособности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fb93-103">Key Health Indicators in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fb93-104">_**Последнее изменение темы:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="2fb93-104">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="2fb93-105">Эта статья является вспомогательной для [ключевых индикаторов работоспособности: фундамента для ведения работоспособного афиши Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) , которую можно загрузить из центра загрузки.</span><span class="sxs-lookup"><span data-stu-id="2fb93-105">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="2fb93-106">![Плакат, описывающий устранение неполадок с помощью данных KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Плакат, описывающий устранение неполадок с помощью данных KHI")</span><span class="sxs-lookup"><span data-stu-id="2fb93-106">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="2fb93-107">С помощью этого афиши вы узнаете о ключевых индикаторах работоспособности (Кхис), счетчиках производительности с пороговыми значениями, направленными на устранение проблем с работой пользователей.</span><span class="sxs-lookup"><span data-stu-id="2fb93-107">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="2fb93-108">Сбор данных KHI обычно является первым этапом реализации методологии качества вызовов (CQM), который фокусируется на обеспечении качества звука для пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="2fb93-108">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="2fb93-109">Если у вас возникнут вопросы об использовании CQM, вы можете отдать свои вопросы в cqmfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2fb93-109">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="2fb93-110">В афише рассматриваются следующие темы:</span><span class="sxs-lookup"><span data-stu-id="2fb93-110">The poster explains the following areas:</span></span>

  - <span data-ttu-id="2fb93-111">Что представляют собой ключевые индикаторы работоспособности?</span><span class="sxs-lookup"><span data-stu-id="2fb93-111">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="2fb93-112">Сбор данных KHI</span><span class="sxs-lookup"><span data-stu-id="2fb93-112">To Collect KHI Data</span></span>

  - <span data-ttu-id="2fb93-113">Процесс исправления для всех ролей сервера</span><span class="sxs-lookup"><span data-stu-id="2fb93-113">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="2fb93-114">Глоссарий</span><span class="sxs-lookup"><span data-stu-id="2fb93-114">Glossary</span></span>

  - <span data-ttu-id="2fb93-115">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="2fb93-115">Front-end Servers</span></span>

  - <span data-ttu-id="2fb93-116">Внутренние серверы SQL Server</span><span class="sxs-lookup"><span data-stu-id="2fb93-116">Backend SQL Servers</span></span>

  - <span data-ttu-id="2fb93-117">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="2fb93-117">Mediation Servers</span></span>

  - <span data-ttu-id="2fb93-118">Пограничные серверы</span><span class="sxs-lookup"><span data-stu-id="2fb93-118">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="2fb93-119">Что представляют собой ключевые индикаторы работоспособности?</span><span class="sxs-lookup"><span data-stu-id="2fb93-119">What are Key Health Indicators?</span></span>

<span data-ttu-id="2fb93-120">Ключевые индикаторы работоспособности представляют собой счетчики производительности с пороговыми значениями, предназначенными для выявления проблем с работой пользователей.</span><span class="sxs-lookup"><span data-stu-id="2fb93-120">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="2fb93-121">Сбор данных KHI обычно является первым этапом реализации методологии качества вызовов (CQM), который фокусируется на обеспечении качества звука для пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="2fb93-121">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="2fb93-122">Кхис используются в дополнение к стандартным решениям для мониторинга Lync (например, System Center Operations Manager, синтетические транзакции, мониторингу сервера), а не к этим решениям.</span><span class="sxs-lookup"><span data-stu-id="2fb93-122">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="2fb93-123">Соберите счетчики производительности KHI и заполните электронную таблицу KHI, сопровождающую электронное руководство по работе с сетью, чтобы создать систему показателей, которая поможет вам определить работоспособность развертывания Lync на сервере.</span><span class="sxs-lookup"><span data-stu-id="2fb93-123">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="2fb93-124">После заполнения он поможет восстановить среду и предоставит дополнительные сведения другим заинтересованным сторонам.</span><span class="sxs-lookup"><span data-stu-id="2fb93-124">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="2fb93-125">Оцените Кхис на месячном уровне и внедрите их в действующие рабочие процессы развертывания.</span><span class="sxs-lookup"><span data-stu-id="2fb93-125">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="2fb93-126">Скачайте электронное [руководство по сетевым подключениям Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677) , чтобы просмотреть полный список кхис и получить связанные электронные таблицы.</span><span class="sxs-lookup"><span data-stu-id="2fb93-126">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="2fb93-127">Сбор данных KHI</span><span class="sxs-lookup"><span data-stu-id="2fb93-127">To Collect KHI Data</span></span>

1.  <span data-ttu-id="2fb93-128">Запустите сценарий KHI, включенный в сетевое руководство Lync Server на каждом сервере Lync.</span><span class="sxs-lookup"><span data-stu-id="2fb93-128">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="2fb93-129">При этом сборщик данных будет создан в системном мониторе с именем KHI.</span><span class="sxs-lookup"><span data-stu-id="2fb93-129">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="2fb93-130">По умолчанию данные будут опрашиваться каждые 15 секунд.</span><span class="sxs-lookup"><span data-stu-id="2fb93-130">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="2fb93-131">Прежде чем начать рабочий день компании, перейдите на каждый сервер Lync Server и запустите сборщик данных KHI.</span><span class="sxs-lookup"><span data-stu-id="2fb93-131">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="2fb93-132">В конце этого дня остановите сборщик данных KHI и скопируйте данные в центральное расположение.</span><span class="sxs-lookup"><span data-stu-id="2fb93-132">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="2fb93-133">После использования системного монитора для заполнения электронной таблицы KHI, включенной в загрузку сетевого руководства Lync Server, Сравните результаты с рекомендуемыми целями.</span><span class="sxs-lookup"><span data-stu-id="2fb93-133">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="2fb93-134">Процесс исправления для всех ролей сервера</span><span class="sxs-lookup"><span data-stu-id="2fb93-134">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="2fb93-135">Для каждого сервера в реализации Lync Начните с проверки работоспособности компонентов сервера и производительности системы на требуемом уровне.</span><span class="sxs-lookup"><span data-stu-id="2fb93-135">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="2fb93-136">Только после этого необходимо просмотреть индикаторы, связанные с ролью сервера, в общей реализации Lync.</span><span class="sxs-lookup"><span data-stu-id="2fb93-136">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="2fb93-137">Начните с сбора данных о производительности KHI для всех серверов.</span><span class="sxs-lookup"><span data-stu-id="2fb93-137">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="2fb93-138">Для каждой из системных ролей (сведения, обсуждаемые далее в этом документе) определяют, удовлетворяют ли основные компоненты системы рекомендуемым целям.</span><span class="sxs-lookup"><span data-stu-id="2fb93-138">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="2fb93-139">Если это не так, устраните производительность системы и повторно Соберите данные KHI и обеспечьте работоспособность системы перед просмотром метрик, относящихся к роли сервера в реализации Lync.</span><span class="sxs-lookup"><span data-stu-id="2fb93-139">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="2fb93-140">Работоспособность компонентов для всех ролей определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2fb93-140">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="2fb93-141">Загрузка ЦП \< 80%</span><span class="sxs-lookup"><span data-stu-id="2fb93-141">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="2fb93-142">Средний объем записи на диск \< 10 мс</span><span class="sxs-lookup"><span data-stu-id="2fb93-142">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="2fb93-143">Средний объем чтения с диска ( \< 10 мс)</span><span class="sxs-lookup"><span data-stu-id="2fb93-143">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="2fb93-144">Доступная память \> 20% всего МБ</span><span class="sxs-lookup"><span data-stu-id="2fb93-144">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="2fb93-145">Длина очереди сети \< 2</span><span class="sxs-lookup"><span data-stu-id="2fb93-145">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="2fb93-146">Отброшенные пакеты (входящие и исходящие) = 0</span><span class="sxs-lookup"><span data-stu-id="2fb93-146">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="2fb93-147">Глоссарий</span><span class="sxs-lookup"><span data-stu-id="2fb93-147">Glossary</span></span>

<span data-ttu-id="2fb93-148">В этом плакате используются следующие термины и акронимы:</span><span class="sxs-lookup"><span data-stu-id="2fb93-148">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="2fb93-149">AS MCU = единица управления общим доступом к приложениям с поддержкой нескольких точек</span><span class="sxs-lookup"><span data-stu-id="2fb93-149">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="2fb93-150">AV MCU = аудио/видео MCU</span><span class="sxs-lookup"><span data-stu-id="2fb93-150">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="2fb93-151">IM MCU = MCU обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="2fb93-151">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="2fb93-152">UCWA = веб-API единой системы обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="2fb93-152">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="2fb93-153">AV Edge = обход звука/видео через пограничный</span><span class="sxs-lookup"><span data-stu-id="2fb93-153">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="2fb93-154">Проверка подлинности AV = проверка подлинности звука и видео</span><span class="sxs-lookup"><span data-stu-id="2fb93-154">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="2fb93-155">Stack SIP = содержит основную реализацию SIP Lync</span><span class="sxs-lookup"><span data-stu-id="2fb93-155">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="2fb93-156">Прокси-сервер данных = используется для пограничного конференц-связи</span><span class="sxs-lookup"><span data-stu-id="2fb93-156">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="2fb93-157">LySS = служба хранилища Lync</span><span class="sxs-lookup"><span data-stu-id="2fb93-157">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="2fb93-158">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="2fb93-158">Front-end Servers</span></span>

<span data-ttu-id="2fb93-159">Следующие целевые объекты KHI относятся к серверам переднего плана в дополнение к основному работоспособности компонента:</span><span class="sxs-lookup"><span data-stu-id="2fb93-159">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2fb93-160">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="2fb93-160">Functional area</span></span></th>
<th><span data-ttu-id="2fb93-161">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="2fb93-161">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2fb93-162">AS/AV/IM MCU</span><span class="sxs-lookup"><span data-stu-id="2fb93-162">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="2fb93-163">Состояние работоспособности MCU &lt; 2</span><span class="sxs-lookup"><span data-stu-id="2fb93-163">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2fb93-164">Web Components</span><span class="sxs-lookup"><span data-stu-id="2fb93-164">Web Components</span></span></p></td>
<td><p><span data-ttu-id="2fb93-165">Таймаутов AD для расширения списка рассылки &lt; 0</span><span class="sxs-lookup"><span data-stu-id="2fb93-165">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="2fb93-166">Сбои ABWQ = 0</span><span class="sxs-lookup"><span data-stu-id="2fb93-166">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="2fb93-167">Ошибок LIS = 0</span><span class="sxs-lookup"><span data-stu-id="2fb93-167">LIS failures = 0</span></span></p>
<p><span data-ttu-id="2fb93-168">Ошибок проверки подлинности &lt; 1/с</span><span class="sxs-lookup"><span data-stu-id="2fb93-168">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="2fb93-169">Отклонено запросов ASP.NET V4 = 0</span><span class="sxs-lookup"><span data-stu-id="2fb93-169">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2fb93-170">Стек SIP</span><span class="sxs-lookup"><span data-stu-id="2fb93-170">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="2fb93-171">СР. обработка входящих сообщений &lt; 1 сек</span><span class="sxs-lookup"><span data-stu-id="2fb93-171">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="2fb93-172">Отброшено входящих ответов, отброшенных &lt; входящих запросов 1/с отброшенных &lt; 1/с</span><span class="sxs-lookup"><span data-stu-id="2fb93-172">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="2fb93-173">Задержка очереди &lt; 100 мс</span><span class="sxs-lookup"><span data-stu-id="2fb93-173">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="2fb93-174">Задержка спрок &lt; 100 мс</span><span class="sxs-lookup"><span data-stu-id="2fb93-174">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="2fb93-175">Регулируемых запросов = 0</span><span class="sxs-lookup"><span data-stu-id="2fb93-175">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="2fb93-176">Ошибок проверки подлинности &lt; 1/с</span><span class="sxs-lookup"><span data-stu-id="2fb93-176">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="2fb93-177">Исходящих сообщений с истекшим сроком ожидания &lt; 2</span><span class="sxs-lookup"><span data-stu-id="2fb93-177">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="2fb93-178">Среднее время хранения входящего сообщения: &lt; 1 с</span><span class="sxs-lookup"><span data-stu-id="2fb93-178">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="2fb93-179">Подключения с управлением обтеканием &lt; 2</span><span class="sxs-lookup"><span data-stu-id="2fb93-179">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="2fb93-180">Средняя задержка очереди ожидания &lt; 2 с</span><span class="sxs-lookup"><span data-stu-id="2fb93-180">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2fb93-181">LySS</span><span class="sxs-lookup"><span data-stu-id="2fb93-181">LySS</span></span></p></td>
<td><p><span data-ttu-id="2fb93-182">% места, используемого в базе данных службы хранилища &lt; 80</span><span class="sxs-lookup"><span data-stu-id="2fb93-182">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="2fb93-183"># количество сбоев репликации реплики = 0</span><span class="sxs-lookup"><span data-stu-id="2fb93-183"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="2fb93-184"># событий потери данных = 0</span><span class="sxs-lookup"><span data-stu-id="2fb93-184"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2fb93-185">SQL</span><span class="sxs-lookup"><span data-stu-id="2fb93-185">SQL</span></span></p></td>
<td><p><span data-ttu-id="2fb93-186">Ожидаемый срок жизни страницы &gt; 300 сек.</span><span class="sxs-lookup"><span data-stu-id="2fb93-186">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="2fb93-187">Запросов пакетов в секунду &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="2fb93-187">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="2fb93-188">Внутренние серверы SQL Server</span><span class="sxs-lookup"><span data-stu-id="2fb93-188">Backend SQL Servers</span></span>

<span data-ttu-id="2fb93-189">Следующие целевые объекты KHI относятся к серверам SQL Server в дополнение к базовому работоспособности компонента:</span><span class="sxs-lookup"><span data-stu-id="2fb93-189">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2fb93-190">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="2fb93-190">Functional area</span></span></th>
<th><span data-ttu-id="2fb93-191">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="2fb93-191">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2fb93-192">SQL</span><span class="sxs-lookup"><span data-stu-id="2fb93-192">SQL</span></span></p></td>
<td><p><span data-ttu-id="2fb93-193">Ожидаемый срок жизни страницы &gt; 300 сек.</span><span class="sxs-lookup"><span data-stu-id="2fb93-193">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="2fb93-194">Запросов пакетов в секунду &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="2fb93-194">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="2fb93-195">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="2fb93-195">Mediation Servers</span></span>

<span data-ttu-id="2fb93-196">Следующие целевые объекты KHI относятся к серверам-посредникам в дополнение к основному работоспособности компонента:</span><span class="sxs-lookup"><span data-stu-id="2fb93-196">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2fb93-197">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="2fb93-197">Functional area</span></span></th>
<th><span data-ttu-id="2fb93-198">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="2fb93-198">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2fb93-199">Служба сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="2fb93-199">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="2fb93-200">Индекс сбоя вызова при загрузке = 0</span><span class="sxs-lookup"><span data-stu-id="2fb93-200">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="2fb93-201">Неудачные вызовы из-за прокси-сервера &lt; 10</span><span class="sxs-lookup"><span data-stu-id="2fb93-201">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="2fb93-202">Неудачные вызовы из-за шлюза &lt; 10</span><span class="sxs-lookup"><span data-stu-id="2fb93-202">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="2fb93-203">Отклонено вызовов (вход или выход) = 0</span><span class="sxs-lookup"><span data-stu-id="2fb93-203">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="2fb93-204">Отсутствующие кандидаты мультимедиа = 0</span><span class="sxs-lookup"><span data-stu-id="2fb93-204">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="2fb93-205">Ошибки проверки подключения к мультимедиа = 0</span><span class="sxs-lookup"><span data-stu-id="2fb93-205">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="2fb93-206">Пограничные серверы</span><span class="sxs-lookup"><span data-stu-id="2fb93-206">Edge Servers</span></span>

<span data-ttu-id="2fb93-207">Следующие целевые цели KHI относятся к пограничным серверам в дополнение к основному работоспособности компонента:</span><span class="sxs-lookup"><span data-stu-id="2fb93-207">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2fb93-208">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="2fb93-208">Functional area</span></span></th>
<th><span data-ttu-id="2fb93-209">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="2fb93-209">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2fb93-210">Проверка подлинности AV</span><span class="sxs-lookup"><span data-stu-id="2fb93-210">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="2fb93-211">Неудачных запросов &lt; 20/с</span><span class="sxs-lookup"><span data-stu-id="2fb93-211">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2fb93-212">Пограничный сервер AV</span><span class="sxs-lookup"><span data-stu-id="2fb93-212">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="2fb93-213">Частота попыток проверки подлинности: &lt; 20/с</span><span class="sxs-lookup"><span data-stu-id="2fb93-213">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="2fb93-214">Ошибок выделения &lt; — 20/с</span><span class="sxs-lookup"><span data-stu-id="2fb93-214">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="2fb93-215">Отброшено пакетов &lt; 300/сек</span><span class="sxs-lookup"><span data-stu-id="2fb93-215">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2fb93-216">Прокси-сервер данных</span><span class="sxs-lookup"><span data-stu-id="2fb93-216">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="2fb93-217">Регулируемые подключения к серверу &lt; 3</span><span class="sxs-lookup"><span data-stu-id="2fb93-217">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="2fb93-218">Система регулирует &lt; 1</span><span class="sxs-lookup"><span data-stu-id="2fb93-218">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2fb93-219">Стек SIP</span><span class="sxs-lookup"><span data-stu-id="2fb93-219">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="2fb93-220">Подключений через лимит, отброшенных &lt; 1</span><span class="sxs-lookup"><span data-stu-id="2fb93-220">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="2fb93-221">Отправляются с истекшим сроком ожидания ( &lt; 10)</span><span class="sxs-lookup"><span data-stu-id="2fb93-221">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="2fb93-222">Подключения с управлением обтеканием &lt; 100</span><span class="sxs-lookup"><span data-stu-id="2fb93-222">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="2fb93-223">Отброшено входящих запросов &lt; 1/с</span><span class="sxs-lookup"><span data-stu-id="2fb93-223">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="2fb93-224">Средняя обработка сообщений &lt; 3 с</span><span class="sxs-lookup"><span data-stu-id="2fb93-224">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2fb93-225">См. также</span><span class="sxs-lookup"><span data-stu-id="2fb93-225">See Also</span></span>


[<span data-ttu-id="2fb93-226">Руководство по сетевым подключениям Lync Server</span><span class="sxs-lookup"><span data-stu-id="2fb93-226">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="2fb93-227">Основные индикаторы работоспособности: основа для обслуживания работоспособных серверов Lync</span><span class="sxs-lookup"><span data-stu-id="2fb93-227">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="2fb93-228">Методология качества вызовов Lync</span><span class="sxs-lookup"><span data-stu-id="2fb93-228">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

