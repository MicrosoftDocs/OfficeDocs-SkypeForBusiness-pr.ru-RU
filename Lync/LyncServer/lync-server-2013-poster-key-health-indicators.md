---
title: 'Lync Server 2013: Афиша: Индикаторы работоспособности ключа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9454197642ac87f5d8bc0d768795854d792f9a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="3b8d5-102">Индикаторы работоспособности ключа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b8d5-102">Key Health Indicators in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b8d5-103">_**Тема последнего изменения:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="3b8d5-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="3b8d5-104">Эта статья является дополнением к [основным индикаторам работоспособности: основанием для поддержки работоспособности](http://go.microsoft.com/fwlink/?linkid=391838) выводятся на рабочем фрагменте Lync Servers, которое можно скачать из центра загрузки.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](http://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="3b8d5-105">![Афиша с описанием устранения неполадок с помощью данных КХИ] (images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Афиша с описанием устранения неполадок с помощью данных КХИ")</span><span class="sxs-lookup"><span data-stu-id="3b8d5-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="3b8d5-106">Вы можете использовать этот плакат, чтобы узнать о индикаторах работоспособности ключа (Кхис), о счетчиках производительности с пороговыми значениями, направленных на устранение проблем взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="3b8d5-107">Сбор данных КХИ обычно является первым этапом реализации методологии качества связи (ККМ), что сосредоточено на обеспечении качества звука для пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="3b8d5-108">Если у вас возникли вопросы о том, как использовать ККМ, вы можете отправлять свои вопросы в cqmfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="3b8d5-109">Афиша содержит сведения о следующих областях:</span><span class="sxs-lookup"><span data-stu-id="3b8d5-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="3b8d5-110">Что такое индикаторы работоспособности ключа?</span><span class="sxs-lookup"><span data-stu-id="3b8d5-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="3b8d5-111">Сбор данных КХИ</span><span class="sxs-lookup"><span data-stu-id="3b8d5-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="3b8d5-112">Поток исправлений для всех ролей сервера</span><span class="sxs-lookup"><span data-stu-id="3b8d5-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="3b8d5-113">Глоссарий</span><span class="sxs-lookup"><span data-stu-id="3b8d5-113">Glossary</span></span>

  - <span data-ttu-id="3b8d5-114">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="3b8d5-114">Front-end Servers</span></span>

  - <span data-ttu-id="3b8d5-115">Внутренние серверы SQL Server</span><span class="sxs-lookup"><span data-stu-id="3b8d5-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="3b8d5-116">посредники</span><span class="sxs-lookup"><span data-stu-id="3b8d5-116">Mediation Servers</span></span>

  - <span data-ttu-id="3b8d5-117">пограничные серверы</span><span class="sxs-lookup"><span data-stu-id="3b8d5-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="3b8d5-118">Что такое индикаторы работоспособности ключа?</span><span class="sxs-lookup"><span data-stu-id="3b8d5-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="3b8d5-119">Ключевые показатели работоспособности — это счетчики производительности с пороговыми значениями, направленными на выявление проблем с производительностью пользователей.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="3b8d5-120">Сбор данных КХИ обычно является первым этапом реализации методологии качества связи (ККМ), что сосредоточено на обеспечении качества звука для пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="3b8d5-121">Кхис используются в дополнение к стандартным решениям для мониторинга Lync (например, System Center Operations Manager, Синтетическым транзакциям, сервер мониторинга), а не к этим решениям.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="3b8d5-122">Соберите данные о счетчиках производительности КХИ и заполните электронную таблицу КХИ, в которой находится руководство по сети, для создания системы показателей, которая поможет вам определить работоспособность развертывания Lync на сервере.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="3b8d5-123">После заполнения она поможет вам восстановить среду и предоставит дополнительные советы другим заинтересованным сторонам.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="3b8d5-124">Вычислите Кхис на ежемесячной основе и внедрите их в выполняющиеся рабочие процессы развертывания.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="3b8d5-125">Загрузите [сетевое руководство по Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677) , чтобы просмотреть полный список кхис и загрузить соответствующие электронные таблицы.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-125">Download the [Lync Server Networking Guide](http://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="3b8d5-126">Сбор данных КХИ</span><span class="sxs-lookup"><span data-stu-id="3b8d5-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="3b8d5-127">Запустите сценарий КХИ, который входит в руководство по сети Lync Server на каждом сервере Lync.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="3b8d5-128">Это приведет к созданию сборщика данных в мониторе производительности и назовите его КХИ.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="3b8d5-129">По умолчанию данные будут опрашиваться каждые 15 секунд.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="3b8d5-130">Перед началом рабочего дня компании перейдите на каждый сервер Lync и запустите сборщик данных КХИ.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="3b8d5-131">В конце этого дня остановите сборщик данных КХИ и скопируйте данные в центральное расположение.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="3b8d5-132">После использования системного монитора для заполнения электронной таблицы КХИ, включенной в загрузку сетевого руководства Lync Server, Сравните результаты с рекомендованными целями.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="3b8d5-133">Поток исправлений для всех ролей сервера</span><span class="sxs-lookup"><span data-stu-id="3b8d5-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="3b8d5-134">Для каждого сервера в реализации Lync Начните с проверки работоспособности компонента сервера и производительности системы на нужном уровне.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="3b8d5-135">Только после этого вы должны ознакомиться с индикаторами, относящимися к роли сервера в общей реализации Lync.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="3b8d5-136">Начните с сбора данных о производительности КХИ для всех серверов.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="3b8d5-137">Для каждой роли системы (сведения, обсуждаемые ниже в этом документе) определяют, соответствуют ли базовые системные компоненты рекомендуемым целям.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="3b8d5-138">Если это не так, устраните производительность системы, а затем заново соберите данные КХИ и обеспечьте работоспособность системы перед просмотром метрик, специфических для роли сервера в реализации Lync.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="3b8d5-139">Работоспособность компонента для всех ролей определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3b8d5-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="3b8d5-140">Загрузка ЦП \< 80%</span><span class="sxs-lookup"><span data-stu-id="3b8d5-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="3b8d5-141">СР. объем записи \< на диск (10 мс)</span><span class="sxs-lookup"><span data-stu-id="3b8d5-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="3b8d5-142">СР. объем чтения \< на диске: 10 мс</span><span class="sxs-lookup"><span data-stu-id="3b8d5-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="3b8d5-143">Доступная \>память 20% всего системы (МБ)</span><span class="sxs-lookup"><span data-stu-id="3b8d5-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="3b8d5-144">Сетевая очередь \< , длина 2</span><span class="sxs-lookup"><span data-stu-id="3b8d5-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="3b8d5-145">Отброшенные пакеты (входящие и исходящие) = 0</span><span class="sxs-lookup"><span data-stu-id="3b8d5-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="3b8d5-146">Глоссарий</span><span class="sxs-lookup"><span data-stu-id="3b8d5-146">Glossary</span></span>

<span data-ttu-id="3b8d5-147">В этом афише используются следующие термины и аббревиатуры.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="3b8d5-148">КАК MCU = одноэлементный управляющий блок с общим доступом к приложениям</span><span class="sxs-lookup"><span data-stu-id="3b8d5-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="3b8d5-149">AV MCU = аудио/видео MCU</span><span class="sxs-lookup"><span data-stu-id="3b8d5-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="3b8d5-150">МГНОВЕНные сообщения MCU = MCU мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="3b8d5-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="3b8d5-151">УКВА = веб-API единой системы обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="3b8d5-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="3b8d5-152">AV Edge = прохождение аудио-или видеоизображения по краю</span><span class="sxs-lookup"><span data-stu-id="3b8d5-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="3b8d5-153">Проверка подлинности AV = аудио/видео</span><span class="sxs-lookup"><span data-stu-id="3b8d5-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="3b8d5-154">Стек SIP = включает основную реализацию SIP в Lync</span><span class="sxs-lookup"><span data-stu-id="3b8d5-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="3b8d5-155">Прокси-сервер данных = используется для проведения пограничного конференции</span><span class="sxs-lookup"><span data-stu-id="3b8d5-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="3b8d5-156">Лисс = служба хранилища Lync</span><span class="sxs-lookup"><span data-stu-id="3b8d5-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="3b8d5-157">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="3b8d5-157">Front-end Servers</span></span>

<span data-ttu-id="3b8d5-158">Ниже приведены рекомендуемые целевые объекты КХИ, специфичные для серверов переднего плана в дополнение к основным компонентам работоспособности.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b8d5-159">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="3b8d5-159">Functional area</span></span></th>
<th><span data-ttu-id="3b8d5-160">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="3b8d5-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b8d5-161">AS/AV/MCU ДЛЯ ОБМЕНА МГНОВЕННЫМИ СООБЩЕНИЯМИ</span><span class="sxs-lookup"><span data-stu-id="3b8d5-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="3b8d5-162">Состояние &lt;работоспособности MCU 2</span><span class="sxs-lookup"><span data-stu-id="3b8d5-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b8d5-163">Веб-компоненты</span><span class="sxs-lookup"><span data-stu-id="3b8d5-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="3b8d5-164">Превышено время ожидания рекламы &lt;для расширения списка рассылки 0</span><span class="sxs-lookup"><span data-stu-id="3b8d5-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="3b8d5-165">Ошибки АБВК = 0</span><span class="sxs-lookup"><span data-stu-id="3b8d5-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="3b8d5-166">Ошибки LIS = 0</span><span class="sxs-lookup"><span data-stu-id="3b8d5-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="3b8d5-167">Ошибки &lt; проверки подлинности 1/с</span><span class="sxs-lookup"><span data-stu-id="3b8d5-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="3b8d5-168">Отвергнуто запросов ASP.NET V4 = 0</span><span class="sxs-lookup"><span data-stu-id="3b8d5-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b8d5-169">Стек SIP</span><span class="sxs-lookup"><span data-stu-id="3b8d5-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="3b8d5-170">СР. Обработка &lt; входящих сообщений 1 с</span><span class="sxs-lookup"><span data-stu-id="3b8d5-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="3b8d5-171">Отброшено &lt; входящих ответов 1 из-за &lt; отброшенных входящих запросов (1 за секунду)</span><span class="sxs-lookup"><span data-stu-id="3b8d5-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="3b8d5-172">Задержка &lt; очереди 100 мсек</span><span class="sxs-lookup"><span data-stu-id="3b8d5-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="3b8d5-173">Спрок задержка &lt; 100 мсек</span><span class="sxs-lookup"><span data-stu-id="3b8d5-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="3b8d5-174">Регулируемые запросы = 0</span><span class="sxs-lookup"><span data-stu-id="3b8d5-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="3b8d5-175">Ошибки &lt; проверки подлинности 1/с</span><span class="sxs-lookup"><span data-stu-id="3b8d5-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="3b8d5-176">Превышение времени ожидания &lt; для входящих сообщений 2</span><span class="sxs-lookup"><span data-stu-id="3b8d5-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="3b8d5-177">Среднее входящее сообщение на хранение &lt; (1 с)</span><span class="sxs-lookup"><span data-stu-id="3b8d5-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="3b8d5-178">Соединения &lt; с управляемым потоком 2</span><span class="sxs-lookup"><span data-stu-id="3b8d5-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="3b8d5-179">Средняя задержка &lt; очереди исходящих сообщений 2 сек</span><span class="sxs-lookup"><span data-stu-id="3b8d5-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b8d5-180">Лисс</span><span class="sxs-lookup"><span data-stu-id="3b8d5-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="3b8d5-181">% места, занятого базой &lt; данных службы хранилища 80</span><span class="sxs-lookup"><span data-stu-id="3b8d5-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="3b8d5-182">#ошибки репликации реплики = 0</span><span class="sxs-lookup"><span data-stu-id="3b8d5-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="3b8d5-183">#событий потери данных = 0</span><span class="sxs-lookup"><span data-stu-id="3b8d5-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b8d5-184">Microsoft</span><span class="sxs-lookup"><span data-stu-id="3b8d5-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="3b8d5-185">Ожидаемый срок жизни &gt; страницы 300 сек.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="3b8d5-186">Пакетных запросов в &lt; секунду 2500</span><span class="sxs-lookup"><span data-stu-id="3b8d5-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="3b8d5-187">Внутренние серверы SQL Server</span><span class="sxs-lookup"><span data-stu-id="3b8d5-187">Backend SQL Servers</span></span>

<span data-ttu-id="3b8d5-188">Ниже приведены рекомендуемые целевые объекты КХИ, специфичные для серверов SQL Server, в дополнение к основным компонентам работоспособности.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b8d5-189">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="3b8d5-189">Functional area</span></span></th>
<th><span data-ttu-id="3b8d5-190">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="3b8d5-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b8d5-191">Microsoft</span><span class="sxs-lookup"><span data-stu-id="3b8d5-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="3b8d5-192">Ожидаемый срок жизни &gt; страницы 300 сек.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="3b8d5-193">Пакетных запросов в &lt; секунду 2500</span><span class="sxs-lookup"><span data-stu-id="3b8d5-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="3b8d5-194">посредники</span><span class="sxs-lookup"><span data-stu-id="3b8d5-194">Mediation Servers</span></span>

<span data-ttu-id="3b8d5-195">Следующие целевые объекты КХИ относятся к серверам для устранения проблем в дополнение к основным работоспособности компонентов:</span><span class="sxs-lookup"><span data-stu-id="3b8d5-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b8d5-196">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="3b8d5-196">Functional area</span></span></th>
<th><span data-ttu-id="3b8d5-197">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="3b8d5-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b8d5-198">Служба сервера обновлений</span><span class="sxs-lookup"><span data-stu-id="3b8d5-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="3b8d5-199">Индекс сбоя при загрузке = 0</span><span class="sxs-lookup"><span data-stu-id="3b8d5-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="3b8d5-200">Неудачные вызовы из &lt;-за прокси-сервера 10</span><span class="sxs-lookup"><span data-stu-id="3b8d5-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="3b8d5-201">Неудачные звонки из &lt;-за шлюза 10</span><span class="sxs-lookup"><span data-stu-id="3b8d5-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="3b8d5-202">Отвергнуто звонков (входящих и исходящим) = 0</span><span class="sxs-lookup"><span data-stu-id="3b8d5-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="3b8d5-203">Отсутствующие кандидаты на мультимедиа = 0</span><span class="sxs-lookup"><span data-stu-id="3b8d5-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="3b8d5-204">Ошибки проверки подключения к мультимедиа = 0</span><span class="sxs-lookup"><span data-stu-id="3b8d5-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="3b8d5-205">пограничные серверы</span><span class="sxs-lookup"><span data-stu-id="3b8d5-205">Edge Servers</span></span>

<span data-ttu-id="3b8d5-206">Ниже приведены рекомендованные целевые объекты КХИ, специфичные для пограничного сервера, помимо базовой работоспособности компонентов.</span><span class="sxs-lookup"><span data-stu-id="3b8d5-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b8d5-207">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="3b8d5-207">Functional area</span></span></th>
<th><span data-ttu-id="3b8d5-208">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="3b8d5-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b8d5-209">Проверка подлинности AV</span><span class="sxs-lookup"><span data-stu-id="3b8d5-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="3b8d5-210">Недопустимых запросов &lt; 20/сек</span><span class="sxs-lookup"><span data-stu-id="3b8d5-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b8d5-211">Край AV</span><span class="sxs-lookup"><span data-stu-id="3b8d5-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="3b8d5-212">Проверка подлинности: &lt;20 за секунду</span><span class="sxs-lookup"><span data-stu-id="3b8d5-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="3b8d5-213">Ошибок &lt;выделения 20/с</span><span class="sxs-lookup"><span data-stu-id="3b8d5-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="3b8d5-214">Отброшено &lt;пакетов 300/сек</span><span class="sxs-lookup"><span data-stu-id="3b8d5-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b8d5-215">Прокси-сервер данных</span><span class="sxs-lookup"><span data-stu-id="3b8d5-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="3b8d5-216">Отрегулированные соединения &lt; с сервером 3</span><span class="sxs-lookup"><span data-stu-id="3b8d5-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="3b8d5-217">Система регулирует &lt;1</span><span class="sxs-lookup"><span data-stu-id="3b8d5-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b8d5-218">Стек SIP</span><span class="sxs-lookup"><span data-stu-id="3b8d5-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="3b8d5-219">Число подключений, отброшенных &lt; до 1</span><span class="sxs-lookup"><span data-stu-id="3b8d5-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="3b8d5-220">Отправляет время ожидания &lt;в течение 10</span><span class="sxs-lookup"><span data-stu-id="3b8d5-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="3b8d5-221">Подключения &lt;, управляемые потоком 100</span><span class="sxs-lookup"><span data-stu-id="3b8d5-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="3b8d5-222">Отброшено &lt; входящих запросов (1 за секунду)</span><span class="sxs-lookup"><span data-stu-id="3b8d5-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="3b8d5-223">СР. Обработка &lt; сообщений 3 с</span><span class="sxs-lookup"><span data-stu-id="3b8d5-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3b8d5-224">См. также</span><span class="sxs-lookup"><span data-stu-id="3b8d5-224">See Also</span></span>


[<span data-ttu-id="3b8d5-225">Сетевое руководство по Lync Server</span><span class="sxs-lookup"><span data-stu-id="3b8d5-225">Lync Server Networking Guide</span></span>](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="3b8d5-226">Индикаторы работоспособности ключа: основы обслуживания работоспособных серверов Lync</span><span class="sxs-lookup"><span data-stu-id="3b8d5-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](http://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="3b8d5-227">Методология качества звонков Lync</span><span class="sxs-lookup"><span data-stu-id="3b8d5-227">Lync Call Quality Methodology</span></span>](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

