---
title: 'Lync Server 2013: Афиша: ключевые индикаторы работоспособности'
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
ms.openlocfilehash: d6db6a701c98a44b042d9ee36d0a749bf6363bd2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513386"
---
# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="21ebc-102">Ключевые индикаторы работоспособности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21ebc-102">Key Health Indicators in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21ebc-103">_**Последнее изменение темы:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="21ebc-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="21ebc-104">Эта статья является вспомогательной для [ключевых индикаторов работоспособности: фундамента для ведения работоспособного афиши Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) , которую можно загрузить из центра загрузки.</span><span class="sxs-lookup"><span data-stu-id="21ebc-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="21ebc-105">![Плакат, описывающий устранение неполадок с помощью данных KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Плакат, описывающий устранение неполадок с помощью данных KHI")</span><span class="sxs-lookup"><span data-stu-id="21ebc-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="21ebc-106">С помощью этого афиши вы узнаете о ключевых индикаторах работоспособности (Кхис), счетчиках производительности с пороговыми значениями, направленными на устранение проблем с работой пользователей.</span><span class="sxs-lookup"><span data-stu-id="21ebc-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="21ebc-107">Сбор данных KHI обычно является первым этапом реализации методологии качества вызовов (CQM), который фокусируется на обеспечении качества звука для пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="21ebc-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="21ebc-108">Если у вас возникнут вопросы об использовании CQM, вы можете отдать свои вопросы в cqmfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="21ebc-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="21ebc-109">В афише рассматриваются следующие темы:</span><span class="sxs-lookup"><span data-stu-id="21ebc-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="21ebc-110">Что представляют собой ключевые индикаторы работоспособности?</span><span class="sxs-lookup"><span data-stu-id="21ebc-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="21ebc-111">Сбор данных KHI</span><span class="sxs-lookup"><span data-stu-id="21ebc-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="21ebc-112">Процесс исправления для всех ролей сервера</span><span class="sxs-lookup"><span data-stu-id="21ebc-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="21ebc-113">Глоссарий</span><span class="sxs-lookup"><span data-stu-id="21ebc-113">Glossary</span></span>

  - <span data-ttu-id="21ebc-114">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="21ebc-114">Front-end Servers</span></span>

  - <span data-ttu-id="21ebc-115">Внутренние серверы SQL Server</span><span class="sxs-lookup"><span data-stu-id="21ebc-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="21ebc-116">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="21ebc-116">Mediation Servers</span></span>

  - <span data-ttu-id="21ebc-117">Пограничные серверы</span><span class="sxs-lookup"><span data-stu-id="21ebc-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="21ebc-118">Что представляют собой ключевые индикаторы работоспособности?</span><span class="sxs-lookup"><span data-stu-id="21ebc-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="21ebc-119">Ключевые индикаторы работоспособности представляют собой счетчики производительности с пороговыми значениями, предназначенными для выявления проблем с работой пользователей.</span><span class="sxs-lookup"><span data-stu-id="21ebc-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="21ebc-120">Сбор данных KHI обычно является первым этапом реализации методологии качества вызовов (CQM), который фокусируется на обеспечении качества звука для пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="21ebc-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="21ebc-121">Кхис используются в дополнение к стандартным решениям для мониторинга Lync (например, System Center Operations Manager, синтетические транзакции, мониторингу сервера), а не к этим решениям.</span><span class="sxs-lookup"><span data-stu-id="21ebc-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="21ebc-122">Соберите счетчики производительности KHI и заполните электронную таблицу KHI, сопровождающую электронное руководство по работе с сетью, чтобы создать систему показателей, которая поможет вам определить работоспособность развертывания Lync на сервере.</span><span class="sxs-lookup"><span data-stu-id="21ebc-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="21ebc-123">После заполнения он поможет восстановить среду и предоставит дополнительные сведения другим заинтересованным сторонам.</span><span class="sxs-lookup"><span data-stu-id="21ebc-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="21ebc-124">Оцените Кхис на месячном уровне и внедрите их в действующие рабочие процессы развертывания.</span><span class="sxs-lookup"><span data-stu-id="21ebc-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="21ebc-125">Скачайте электронное [руководство по сетевым подключениям Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677) , чтобы просмотреть полный список кхис и получить связанные электронные таблицы.</span><span class="sxs-lookup"><span data-stu-id="21ebc-125">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="21ebc-126">Сбор данных KHI</span><span class="sxs-lookup"><span data-stu-id="21ebc-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="21ebc-127">Запустите сценарий KHI, включенный в сетевое руководство Lync Server на каждом сервере Lync.</span><span class="sxs-lookup"><span data-stu-id="21ebc-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="21ebc-128">При этом сборщик данных будет создан в системном мониторе с именем KHI.</span><span class="sxs-lookup"><span data-stu-id="21ebc-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="21ebc-129">По умолчанию данные будут опрашиваться каждые 15 секунд.</span><span class="sxs-lookup"><span data-stu-id="21ebc-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="21ebc-130">Прежде чем начать рабочий день компании, перейдите на каждый сервер Lync Server и запустите сборщик данных KHI.</span><span class="sxs-lookup"><span data-stu-id="21ebc-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="21ebc-131">В конце этого дня остановите сборщик данных KHI и скопируйте данные в центральное расположение.</span><span class="sxs-lookup"><span data-stu-id="21ebc-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="21ebc-132">После использования системного монитора для заполнения электронной таблицы KHI, включенной в загрузку сетевого руководства Lync Server, Сравните результаты с рекомендуемыми целями.</span><span class="sxs-lookup"><span data-stu-id="21ebc-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="21ebc-133">Процесс исправления для всех ролей сервера</span><span class="sxs-lookup"><span data-stu-id="21ebc-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="21ebc-134">Для каждого сервера в реализации Lync Начните с проверки работоспособности компонентов сервера и производительности системы на требуемом уровне.</span><span class="sxs-lookup"><span data-stu-id="21ebc-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="21ebc-135">Только после этого необходимо просмотреть индикаторы, связанные с ролью сервера, в общей реализации Lync.</span><span class="sxs-lookup"><span data-stu-id="21ebc-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="21ebc-136">Начните с сбора данных о производительности KHI для всех серверов.</span><span class="sxs-lookup"><span data-stu-id="21ebc-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="21ebc-137">Для каждой из системных ролей (сведения, обсуждаемые далее в этом документе) определяют, удовлетворяют ли основные компоненты системы рекомендуемым целям.</span><span class="sxs-lookup"><span data-stu-id="21ebc-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="21ebc-138">Если это не так, устраните производительность системы и повторно Соберите данные KHI и обеспечьте работоспособность системы перед просмотром метрик, относящихся к роли сервера в реализации Lync.</span><span class="sxs-lookup"><span data-stu-id="21ebc-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="21ebc-139">Работоспособность компонентов для всех ролей определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="21ebc-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="21ebc-140">Загрузка ЦП \< 80%</span><span class="sxs-lookup"><span data-stu-id="21ebc-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="21ebc-141">Средний объем записи на диск \< 10 мс</span><span class="sxs-lookup"><span data-stu-id="21ebc-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="21ebc-142">Средний объем чтения с диска ( \< 10 мс)</span><span class="sxs-lookup"><span data-stu-id="21ebc-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="21ebc-143">Доступная память \> 20% всего МБ</span><span class="sxs-lookup"><span data-stu-id="21ebc-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="21ebc-144">Длина очереди сети \< 2</span><span class="sxs-lookup"><span data-stu-id="21ebc-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="21ebc-145">Отброшенные пакеты (входящие и исходящие) = 0</span><span class="sxs-lookup"><span data-stu-id="21ebc-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="21ebc-146">Глоссарий</span><span class="sxs-lookup"><span data-stu-id="21ebc-146">Glossary</span></span>

<span data-ttu-id="21ebc-147">В этом плакате используются следующие термины и акронимы:</span><span class="sxs-lookup"><span data-stu-id="21ebc-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="21ebc-148">AS MCU = единица управления общим доступом к приложениям с поддержкой нескольких точек</span><span class="sxs-lookup"><span data-stu-id="21ebc-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="21ebc-149">AV MCU = аудио/видео MCU</span><span class="sxs-lookup"><span data-stu-id="21ebc-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="21ebc-150">IM MCU = MCU обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="21ebc-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="21ebc-151">UCWA = веб-API единой системы обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="21ebc-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="21ebc-152">AV Edge = обход звука/видео через пограничный</span><span class="sxs-lookup"><span data-stu-id="21ebc-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="21ebc-153">Проверка подлинности AV = проверка подлинности звука и видео</span><span class="sxs-lookup"><span data-stu-id="21ebc-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="21ebc-154">Stack SIP = содержит основную реализацию SIP Lync</span><span class="sxs-lookup"><span data-stu-id="21ebc-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="21ebc-155">Прокси-сервер данных = используется для пограничного конференц-связи</span><span class="sxs-lookup"><span data-stu-id="21ebc-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="21ebc-156">LySS = служба хранилища Lync</span><span class="sxs-lookup"><span data-stu-id="21ebc-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="21ebc-157">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="21ebc-157">Front-end Servers</span></span>

<span data-ttu-id="21ebc-158">Следующие целевые объекты KHI относятся к серверам переднего плана в дополнение к основному работоспособности компонента:</span><span class="sxs-lookup"><span data-stu-id="21ebc-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21ebc-159">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="21ebc-159">Functional area</span></span></th>
<th><span data-ttu-id="21ebc-160">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="21ebc-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21ebc-161">AS/AV/IM MCU</span><span class="sxs-lookup"><span data-stu-id="21ebc-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="21ebc-162">Состояние работоспособности MCU &lt; 2</span><span class="sxs-lookup"><span data-stu-id="21ebc-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21ebc-163">Web Components</span><span class="sxs-lookup"><span data-stu-id="21ebc-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="21ebc-164">Таймаутов AD для расширения списка рассылки &lt; 0</span><span class="sxs-lookup"><span data-stu-id="21ebc-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="21ebc-165">Сбои ABWQ = 0</span><span class="sxs-lookup"><span data-stu-id="21ebc-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="21ebc-166">Ошибок LIS = 0</span><span class="sxs-lookup"><span data-stu-id="21ebc-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="21ebc-167">Ошибок проверки подлинности &lt; 1/с</span><span class="sxs-lookup"><span data-stu-id="21ebc-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="21ebc-168">Отклонено запросов ASP.NET V4 = 0</span><span class="sxs-lookup"><span data-stu-id="21ebc-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21ebc-169">Стек SIP</span><span class="sxs-lookup"><span data-stu-id="21ebc-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="21ebc-170">СР. обработка входящих сообщений &lt; 1 сек</span><span class="sxs-lookup"><span data-stu-id="21ebc-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="21ebc-171">Отброшено входящих ответов, отброшенных &lt; входящих запросов 1/с отброшенных &lt; 1/с</span><span class="sxs-lookup"><span data-stu-id="21ebc-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="21ebc-172">Задержка очереди &lt; 100 мс</span><span class="sxs-lookup"><span data-stu-id="21ebc-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="21ebc-173">Задержка спрок &lt; 100 мс</span><span class="sxs-lookup"><span data-stu-id="21ebc-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="21ebc-174">Регулируемых запросов = 0</span><span class="sxs-lookup"><span data-stu-id="21ebc-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="21ebc-175">Ошибок проверки подлинности &lt; 1/с</span><span class="sxs-lookup"><span data-stu-id="21ebc-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="21ebc-176">Исходящих сообщений с истекшим сроком ожидания &lt; 2</span><span class="sxs-lookup"><span data-stu-id="21ebc-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="21ebc-177">Среднее время хранения входящего сообщения: &lt; 1 с</span><span class="sxs-lookup"><span data-stu-id="21ebc-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="21ebc-178">Подключения с управлением обтеканием &lt; 2</span><span class="sxs-lookup"><span data-stu-id="21ebc-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="21ebc-179">Средняя задержка очереди ожидания &lt; 2 с</span><span class="sxs-lookup"><span data-stu-id="21ebc-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21ebc-180">LySS</span><span class="sxs-lookup"><span data-stu-id="21ebc-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="21ebc-181">% места, используемого в базе данных службы хранилища &lt; 80</span><span class="sxs-lookup"><span data-stu-id="21ebc-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="21ebc-182"># количество сбоев репликации реплики = 0</span><span class="sxs-lookup"><span data-stu-id="21ebc-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="21ebc-183"># событий потери данных = 0</span><span class="sxs-lookup"><span data-stu-id="21ebc-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21ebc-184">SQL</span><span class="sxs-lookup"><span data-stu-id="21ebc-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="21ebc-185">Ожидаемый срок жизни страницы &gt; 300 сек.</span><span class="sxs-lookup"><span data-stu-id="21ebc-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="21ebc-186">Запросов пакетов в секунду &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="21ebc-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="21ebc-187">Внутренние серверы SQL Server</span><span class="sxs-lookup"><span data-stu-id="21ebc-187">Backend SQL Servers</span></span>

<span data-ttu-id="21ebc-188">Следующие целевые объекты KHI относятся к серверам SQL Server в дополнение к базовому работоспособности компонента:</span><span class="sxs-lookup"><span data-stu-id="21ebc-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21ebc-189">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="21ebc-189">Functional area</span></span></th>
<th><span data-ttu-id="21ebc-190">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="21ebc-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21ebc-191">SQL</span><span class="sxs-lookup"><span data-stu-id="21ebc-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="21ebc-192">Ожидаемый срок жизни страницы &gt; 300 сек.</span><span class="sxs-lookup"><span data-stu-id="21ebc-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="21ebc-193">Запросов пакетов в секунду &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="21ebc-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="21ebc-194">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="21ebc-194">Mediation Servers</span></span>

<span data-ttu-id="21ebc-195">Следующие целевые объекты KHI относятся к серверам-посредникам в дополнение к основному работоспособности компонента:</span><span class="sxs-lookup"><span data-stu-id="21ebc-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21ebc-196">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="21ebc-196">Functional area</span></span></th>
<th><span data-ttu-id="21ebc-197">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="21ebc-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21ebc-198">Служба сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="21ebc-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="21ebc-199">Индекс сбоя вызова при загрузке = 0</span><span class="sxs-lookup"><span data-stu-id="21ebc-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="21ebc-200">Неудачные вызовы из-за прокси-сервера &lt; 10</span><span class="sxs-lookup"><span data-stu-id="21ebc-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="21ebc-201">Неудачные вызовы из-за шлюза &lt; 10</span><span class="sxs-lookup"><span data-stu-id="21ebc-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="21ebc-202">Отклонено вызовов (вход или выход) = 0</span><span class="sxs-lookup"><span data-stu-id="21ebc-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="21ebc-203">Отсутствующие кандидаты мультимедиа = 0</span><span class="sxs-lookup"><span data-stu-id="21ebc-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="21ebc-204">Ошибки проверки подключения к мультимедиа = 0</span><span class="sxs-lookup"><span data-stu-id="21ebc-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="21ebc-205">Пограничные серверы</span><span class="sxs-lookup"><span data-stu-id="21ebc-205">Edge Servers</span></span>

<span data-ttu-id="21ebc-206">Следующие целевые цели KHI относятся к пограничным серверам в дополнение к основному работоспособности компонента:</span><span class="sxs-lookup"><span data-stu-id="21ebc-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21ebc-207">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="21ebc-207">Functional area</span></span></th>
<th><span data-ttu-id="21ebc-208">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="21ebc-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21ebc-209">Проверка подлинности AV</span><span class="sxs-lookup"><span data-stu-id="21ebc-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="21ebc-210">Неудачных запросов &lt; 20/с</span><span class="sxs-lookup"><span data-stu-id="21ebc-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21ebc-211">Пограничный сервер AV</span><span class="sxs-lookup"><span data-stu-id="21ebc-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="21ebc-212">Частота попыток проверки подлинности: &lt; 20/с</span><span class="sxs-lookup"><span data-stu-id="21ebc-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="21ebc-213">Ошибок выделения &lt; — 20/с</span><span class="sxs-lookup"><span data-stu-id="21ebc-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="21ebc-214">Отброшено пакетов &lt; 300/сек</span><span class="sxs-lookup"><span data-stu-id="21ebc-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21ebc-215">Прокси-сервер данных</span><span class="sxs-lookup"><span data-stu-id="21ebc-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="21ebc-216">Регулируемые подключения к серверу &lt; 3</span><span class="sxs-lookup"><span data-stu-id="21ebc-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="21ebc-217">Система регулирует &lt; 1</span><span class="sxs-lookup"><span data-stu-id="21ebc-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21ebc-218">Стек SIP</span><span class="sxs-lookup"><span data-stu-id="21ebc-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="21ebc-219">Подключений через лимит, отброшенных &lt; 1</span><span class="sxs-lookup"><span data-stu-id="21ebc-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="21ebc-220">Отправляются с истекшим сроком ожидания ( &lt; 10)</span><span class="sxs-lookup"><span data-stu-id="21ebc-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="21ebc-221">Подключения с управлением обтеканием &lt; 100</span><span class="sxs-lookup"><span data-stu-id="21ebc-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="21ebc-222">Отброшено входящих запросов &lt; 1/с</span><span class="sxs-lookup"><span data-stu-id="21ebc-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="21ebc-223">Средняя обработка сообщений &lt; 3 с</span><span class="sxs-lookup"><span data-stu-id="21ebc-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="21ebc-224">См. также</span><span class="sxs-lookup"><span data-stu-id="21ebc-224">See Also</span></span>


[<span data-ttu-id="21ebc-225">Руководство по сетевым подключениям Lync Server</span><span class="sxs-lookup"><span data-stu-id="21ebc-225">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="21ebc-226">Основные индикаторы работоспособности: основа для обслуживания работоспособных серверов Lync</span><span class="sxs-lookup"><span data-stu-id="21ebc-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="21ebc-227">Методология качества вызовов Lync</span><span class="sxs-lookup"><span data-stu-id="21ebc-227">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

