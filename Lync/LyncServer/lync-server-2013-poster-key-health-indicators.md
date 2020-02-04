---
title: 'Lync Server 2013: Афиша: Индикаторы работоспособности ключа'
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
ms.openlocfilehash: 812ce68c84f86250fd25cc646bbcd5faddf0e566
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="ea40e-102">Индикаторы работоспособности ключа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea40e-102">Key Health Indicators in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea40e-103">_**Тема последнего изменения:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="ea40e-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="ea40e-104">Эта статья является дополнением к [основным индикаторам работоспособности: основанием для поддержки работоспособности](http://go.microsoft.com/fwlink/?linkid=391838) выводятся на рабочем фрагменте Lync Servers, которое можно скачать из центра загрузки.</span><span class="sxs-lookup"><span data-stu-id="ea40e-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](http://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="ea40e-105">![Афиша с описанием устранения неполадок с помощью данных КХИ](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Афиша с описанием устранения неполадок с помощью данных КХИ")</span><span class="sxs-lookup"><span data-stu-id="ea40e-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="ea40e-106">Вы можете использовать этот плакат, чтобы узнать о индикаторах работоспособности ключа (Кхис), о счетчиках производительности с пороговыми значениями, направленных на устранение проблем взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="ea40e-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="ea40e-107">Сбор данных КХИ обычно является первым этапом реализации методологии качества связи (ККМ), что сосредоточено на обеспечении качества звука для пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="ea40e-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="ea40e-108">Если у вас возникли вопросы о том, как использовать ККМ, вы можете отправлять свои вопросы в cqmfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="ea40e-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="ea40e-109">Афиша содержит сведения о следующих областях:</span><span class="sxs-lookup"><span data-stu-id="ea40e-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="ea40e-110">Что такое индикаторы работоспособности ключа?</span><span class="sxs-lookup"><span data-stu-id="ea40e-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="ea40e-111">Сбор данных КХИ</span><span class="sxs-lookup"><span data-stu-id="ea40e-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="ea40e-112">Поток исправлений для всех ролей сервера</span><span class="sxs-lookup"><span data-stu-id="ea40e-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="ea40e-113">Глоссарий</span><span class="sxs-lookup"><span data-stu-id="ea40e-113">Glossary</span></span>

  - <span data-ttu-id="ea40e-114">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ea40e-114">Front-end Servers</span></span>

  - <span data-ttu-id="ea40e-115">Внутренние серверы SQL Server</span><span class="sxs-lookup"><span data-stu-id="ea40e-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="ea40e-116">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="ea40e-116">Mediation Servers</span></span>

  - <span data-ttu-id="ea40e-117">пограничные серверы</span><span class="sxs-lookup"><span data-stu-id="ea40e-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="ea40e-118">Что такое индикаторы работоспособности ключа?</span><span class="sxs-lookup"><span data-stu-id="ea40e-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="ea40e-119">Ключевые показатели работоспособности — это счетчики производительности с пороговыми значениями, направленными на выявление проблем с производительностью пользователей.</span><span class="sxs-lookup"><span data-stu-id="ea40e-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="ea40e-120">Сбор данных КХИ обычно является первым этапом реализации методологии качества связи (ККМ), что сосредоточено на обеспечении качества звука для пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="ea40e-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="ea40e-121">Кхис используются в дополнение к стандартным решениям для мониторинга Lync (например, System Center Operations Manager, Синтетическым транзакциям, сервер мониторинга), а не к этим решениям.</span><span class="sxs-lookup"><span data-stu-id="ea40e-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="ea40e-122">Соберите данные о счетчиках производительности КХИ и заполните электронную таблицу КХИ, в которой находится руководство по сети, для создания системы показателей, которая поможет вам определить работоспособность развертывания Lync на сервере.</span><span class="sxs-lookup"><span data-stu-id="ea40e-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="ea40e-123">После заполнения она поможет вам восстановить среду и предоставит дополнительные советы другим заинтересованным сторонам.</span><span class="sxs-lookup"><span data-stu-id="ea40e-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="ea40e-124">Вычислите Кхис на ежемесячной основе и внедрите их в выполняющиеся рабочие процессы развертывания.</span><span class="sxs-lookup"><span data-stu-id="ea40e-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="ea40e-125">Загрузите [сетевое руководство по Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677) , чтобы просмотреть полный список кхис и загрузить соответствующие электронные таблицы.</span><span class="sxs-lookup"><span data-stu-id="ea40e-125">Download the [Lync Server Networking Guide](http://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="ea40e-126">Сбор данных КХИ</span><span class="sxs-lookup"><span data-stu-id="ea40e-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="ea40e-127">Запустите сценарий КХИ, который входит в руководство по сети Lync Server на каждом сервере Lync.</span><span class="sxs-lookup"><span data-stu-id="ea40e-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="ea40e-128">Это приведет к созданию сборщика данных в мониторе производительности и назовите его КХИ.</span><span class="sxs-lookup"><span data-stu-id="ea40e-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="ea40e-129">По умолчанию данные будут опрашиваться каждые 15 секунд.</span><span class="sxs-lookup"><span data-stu-id="ea40e-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="ea40e-130">Перед началом рабочего дня компании перейдите на каждый сервер Lync и запустите сборщик данных КХИ.</span><span class="sxs-lookup"><span data-stu-id="ea40e-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="ea40e-131">В конце этого дня остановите сборщик данных КХИ и скопируйте данные в центральное расположение.</span><span class="sxs-lookup"><span data-stu-id="ea40e-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="ea40e-132">После использования системного монитора для заполнения электронной таблицы КХИ, включенной в загрузку сетевого руководства Lync Server, Сравните результаты с рекомендованными целями.</span><span class="sxs-lookup"><span data-stu-id="ea40e-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="ea40e-133">Поток исправлений для всех ролей сервера</span><span class="sxs-lookup"><span data-stu-id="ea40e-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="ea40e-134">Для каждого сервера в реализации Lync Начните с проверки работоспособности компонента сервера и производительности системы на нужном уровне.</span><span class="sxs-lookup"><span data-stu-id="ea40e-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="ea40e-135">Только после этого вы должны ознакомиться с индикаторами, относящимися к роли сервера в общей реализации Lync.</span><span class="sxs-lookup"><span data-stu-id="ea40e-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="ea40e-136">Начните с сбора данных о производительности КХИ для всех серверов.</span><span class="sxs-lookup"><span data-stu-id="ea40e-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="ea40e-137">Для каждой роли системы (сведения, обсуждаемые ниже в этом документе) определяют, соответствуют ли базовые системные компоненты рекомендуемым целям.</span><span class="sxs-lookup"><span data-stu-id="ea40e-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="ea40e-138">Если это не так, устраните производительность системы, а затем заново соберите данные КХИ и обеспечьте работоспособность системы перед просмотром метрик, специфических для роли сервера в реализации Lync.</span><span class="sxs-lookup"><span data-stu-id="ea40e-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="ea40e-139">Работоспособность компонента для всех ролей определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ea40e-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="ea40e-140">Загрузка ЦП \< 80%</span><span class="sxs-lookup"><span data-stu-id="ea40e-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="ea40e-141">СР. объем записи \< на диск (10 мс)</span><span class="sxs-lookup"><span data-stu-id="ea40e-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="ea40e-142">СР. объем чтения \< на диске: 10 мс</span><span class="sxs-lookup"><span data-stu-id="ea40e-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="ea40e-143">Доступная \>память 20% всего системы (МБ)</span><span class="sxs-lookup"><span data-stu-id="ea40e-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="ea40e-144">Сетевая очередь \< , длина 2</span><span class="sxs-lookup"><span data-stu-id="ea40e-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="ea40e-145">Отброшенные пакеты (входящие и исходящие) = 0</span><span class="sxs-lookup"><span data-stu-id="ea40e-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="ea40e-146">Глоссарий</span><span class="sxs-lookup"><span data-stu-id="ea40e-146">Glossary</span></span>

<span data-ttu-id="ea40e-147">В этом афише используются следующие термины и аббревиатуры.</span><span class="sxs-lookup"><span data-stu-id="ea40e-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="ea40e-148">КАК MCU = одноэлементный управляющий блок с общим доступом к приложениям</span><span class="sxs-lookup"><span data-stu-id="ea40e-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="ea40e-149">AV MCU = аудио/видео MCU</span><span class="sxs-lookup"><span data-stu-id="ea40e-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="ea40e-150">МГНОВЕНные сообщения MCU = MCU мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="ea40e-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="ea40e-151">УКВА = веб-API единой системы обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="ea40e-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="ea40e-152">AV Edge = прохождение аудио-или видеоизображения по краю</span><span class="sxs-lookup"><span data-stu-id="ea40e-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="ea40e-153">Проверка подлинности AV = аудио/видео</span><span class="sxs-lookup"><span data-stu-id="ea40e-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="ea40e-154">Стек SIP = включает основную реализацию SIP в Lync</span><span class="sxs-lookup"><span data-stu-id="ea40e-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="ea40e-155">Прокси-сервер данных = используется для проведения пограничного конференции</span><span class="sxs-lookup"><span data-stu-id="ea40e-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="ea40e-156">Лисс = служба хранилища Lync</span><span class="sxs-lookup"><span data-stu-id="ea40e-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="ea40e-157">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ea40e-157">Front-end Servers</span></span>

<span data-ttu-id="ea40e-158">Ниже приведены рекомендуемые целевые объекты КХИ, специфичные для серверов переднего плана в дополнение к основным компонентам работоспособности.</span><span class="sxs-lookup"><span data-stu-id="ea40e-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea40e-159">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="ea40e-159">Functional area</span></span></th>
<th><span data-ttu-id="ea40e-160">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="ea40e-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea40e-161">AS/AV/MCU ДЛЯ ОБМЕНА МГНОВЕННЫМИ СООБЩЕНИЯМИ</span><span class="sxs-lookup"><span data-stu-id="ea40e-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="ea40e-162">Состояние &lt;работоспособности MCU 2</span><span class="sxs-lookup"><span data-stu-id="ea40e-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea40e-163">Веб-компоненты</span><span class="sxs-lookup"><span data-stu-id="ea40e-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="ea40e-164">Превышено время ожидания рекламы &lt;для расширения списка рассылки 0</span><span class="sxs-lookup"><span data-stu-id="ea40e-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="ea40e-165">Ошибки АБВК = 0</span><span class="sxs-lookup"><span data-stu-id="ea40e-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="ea40e-166">Ошибки LIS = 0</span><span class="sxs-lookup"><span data-stu-id="ea40e-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="ea40e-167">Ошибки &lt; проверки подлинности 1/с</span><span class="sxs-lookup"><span data-stu-id="ea40e-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="ea40e-168">Отвергнуто запросов ASP.NET V4 = 0</span><span class="sxs-lookup"><span data-stu-id="ea40e-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea40e-169">Стек SIP</span><span class="sxs-lookup"><span data-stu-id="ea40e-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="ea40e-170">СР. Обработка &lt; входящих сообщений 1 с</span><span class="sxs-lookup"><span data-stu-id="ea40e-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="ea40e-171">Отброшено &lt; входящих ответов 1 из-за &lt; отброшенных входящих запросов (1 за секунду)</span><span class="sxs-lookup"><span data-stu-id="ea40e-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="ea40e-172">Задержка &lt; очереди 100 мсек</span><span class="sxs-lookup"><span data-stu-id="ea40e-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="ea40e-173">Спрок задержка &lt; 100 мсек</span><span class="sxs-lookup"><span data-stu-id="ea40e-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="ea40e-174">Регулируемые запросы = 0</span><span class="sxs-lookup"><span data-stu-id="ea40e-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="ea40e-175">Ошибки &lt; проверки подлинности 1/с</span><span class="sxs-lookup"><span data-stu-id="ea40e-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="ea40e-176">Превышение времени ожидания &lt; для входящих сообщений 2</span><span class="sxs-lookup"><span data-stu-id="ea40e-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="ea40e-177">Среднее входящее сообщение на хранение &lt; (1 с)</span><span class="sxs-lookup"><span data-stu-id="ea40e-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="ea40e-178">Соединения &lt; с управляемым потоком 2</span><span class="sxs-lookup"><span data-stu-id="ea40e-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="ea40e-179">Средняя задержка &lt; очереди исходящих сообщений 2 сек</span><span class="sxs-lookup"><span data-stu-id="ea40e-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea40e-180">лисс</span><span class="sxs-lookup"><span data-stu-id="ea40e-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="ea40e-181">% места, занятого базой &lt; данных службы хранилища 80</span><span class="sxs-lookup"><span data-stu-id="ea40e-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="ea40e-182">#ошибки репликации реплики = 0</span><span class="sxs-lookup"><span data-stu-id="ea40e-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="ea40e-183">#событий потери данных = 0</span><span class="sxs-lookup"><span data-stu-id="ea40e-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea40e-184">Microsoft</span><span class="sxs-lookup"><span data-stu-id="ea40e-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="ea40e-185">Ожидаемый срок жизни &gt; страницы 300 сек.</span><span class="sxs-lookup"><span data-stu-id="ea40e-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="ea40e-186">Пакетных запросов в &lt; секунду 2500</span><span class="sxs-lookup"><span data-stu-id="ea40e-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="ea40e-187">Внутренние серверы SQL Server</span><span class="sxs-lookup"><span data-stu-id="ea40e-187">Backend SQL Servers</span></span>

<span data-ttu-id="ea40e-188">Ниже приведены рекомендуемые целевые объекты КХИ, специфичные для серверов SQL Server, в дополнение к основным компонентам работоспособности.</span><span class="sxs-lookup"><span data-stu-id="ea40e-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea40e-189">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="ea40e-189">Functional area</span></span></th>
<th><span data-ttu-id="ea40e-190">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="ea40e-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea40e-191">Microsoft</span><span class="sxs-lookup"><span data-stu-id="ea40e-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="ea40e-192">Ожидаемый срок жизни &gt; страницы 300 сек.</span><span class="sxs-lookup"><span data-stu-id="ea40e-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="ea40e-193">Пакетных запросов в &lt; секунду 2500</span><span class="sxs-lookup"><span data-stu-id="ea40e-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="ea40e-194">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="ea40e-194">Mediation Servers</span></span>

<span data-ttu-id="ea40e-195">Следующие целевые объекты КХИ относятся к серверам для устранения проблем в дополнение к основным работоспособности компонентов:</span><span class="sxs-lookup"><span data-stu-id="ea40e-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea40e-196">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="ea40e-196">Functional area</span></span></th>
<th><span data-ttu-id="ea40e-197">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="ea40e-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea40e-198">Служба сервера обновлений</span><span class="sxs-lookup"><span data-stu-id="ea40e-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="ea40e-199">Индекс сбоя при загрузке = 0</span><span class="sxs-lookup"><span data-stu-id="ea40e-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="ea40e-200">Неудачные вызовы из &lt;-за прокси-сервера 10</span><span class="sxs-lookup"><span data-stu-id="ea40e-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="ea40e-201">Неудачные звонки из &lt;-за шлюза 10</span><span class="sxs-lookup"><span data-stu-id="ea40e-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="ea40e-202">Отвергнуто звонков (входящих и исходящим) = 0</span><span class="sxs-lookup"><span data-stu-id="ea40e-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="ea40e-203">Отсутствующие кандидаты на мультимедиа = 0</span><span class="sxs-lookup"><span data-stu-id="ea40e-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="ea40e-204">Ошибки проверки подключения к мультимедиа = 0</span><span class="sxs-lookup"><span data-stu-id="ea40e-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="ea40e-205">пограничные серверы</span><span class="sxs-lookup"><span data-stu-id="ea40e-205">Edge Servers</span></span>

<span data-ttu-id="ea40e-206">Ниже приведены рекомендованные целевые объекты КХИ, специфичные для пограничного сервера, помимо базовой работоспособности компонентов.</span><span class="sxs-lookup"><span data-stu-id="ea40e-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea40e-207">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="ea40e-207">Functional area</span></span></th>
<th><span data-ttu-id="ea40e-208">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="ea40e-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea40e-209">Проверка подлинности AV</span><span class="sxs-lookup"><span data-stu-id="ea40e-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="ea40e-210">Недопустимых запросов &lt; 20/сек</span><span class="sxs-lookup"><span data-stu-id="ea40e-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea40e-211">Край AV</span><span class="sxs-lookup"><span data-stu-id="ea40e-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="ea40e-212">Проверка подлинности: &lt;20 за секунду</span><span class="sxs-lookup"><span data-stu-id="ea40e-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="ea40e-213">Ошибок &lt;выделения 20/с</span><span class="sxs-lookup"><span data-stu-id="ea40e-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="ea40e-214">Отброшено &lt;пакетов 300/сек</span><span class="sxs-lookup"><span data-stu-id="ea40e-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea40e-215">Прокси-сервер данных</span><span class="sxs-lookup"><span data-stu-id="ea40e-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="ea40e-216">Отрегулированные соединения &lt; с сервером 3</span><span class="sxs-lookup"><span data-stu-id="ea40e-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="ea40e-217">Система регулирует &lt;1</span><span class="sxs-lookup"><span data-stu-id="ea40e-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea40e-218">Стек SIP</span><span class="sxs-lookup"><span data-stu-id="ea40e-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="ea40e-219">Число подключений, отброшенных &lt; до 1</span><span class="sxs-lookup"><span data-stu-id="ea40e-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="ea40e-220">Отправляет время ожидания &lt;в течение 10</span><span class="sxs-lookup"><span data-stu-id="ea40e-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="ea40e-221">Подключения &lt;, управляемые потоком 100</span><span class="sxs-lookup"><span data-stu-id="ea40e-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="ea40e-222">Отброшено &lt; входящих запросов (1 за секунду)</span><span class="sxs-lookup"><span data-stu-id="ea40e-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="ea40e-223">СР. Обработка &lt; сообщений 3 с</span><span class="sxs-lookup"><span data-stu-id="ea40e-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ea40e-224">См. также</span><span class="sxs-lookup"><span data-stu-id="ea40e-224">See Also</span></span>


[<span data-ttu-id="ea40e-225">Сетевое руководство по Lync Server</span><span class="sxs-lookup"><span data-stu-id="ea40e-225">Lync Server Networking Guide</span></span>](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="ea40e-226">Индикаторы работоспособности ключа: основы обслуживания работоспособных серверов Lync</span><span class="sxs-lookup"><span data-stu-id="ea40e-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](http://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="ea40e-227">Методология качества звонков Lync</span><span class="sxs-lookup"><span data-stu-id="ea40e-227">Lync Call Quality Methodology</span></span>](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

