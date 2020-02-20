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
ms.openlocfilehash: 2710e85eced76241f4946ef2746e544d07be941f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="1f97f-102">Ключевые индикаторы работоспособности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f97f-102">Key Health Indicators in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f97f-103">_**Последнее изменение темы:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="1f97f-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="1f97f-104">Эта статья является вспомогательной для [ключевых индикаторов работоспособности: фундамента для ведения работоспособного афиши Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) , которую можно загрузить из центра загрузки.</span><span class="sxs-lookup"><span data-stu-id="1f97f-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="1f97f-105">![Плакат, описывающий устранение неполадок с помощью данных KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Плакат, описывающий устранение неполадок с помощью данных KHI")</span><span class="sxs-lookup"><span data-stu-id="1f97f-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="1f97f-106">С помощью этого афиши вы узнаете о ключевых индикаторах работоспособности (Кхис), счетчиках производительности с пороговыми значениями, направленными на устранение проблем с работой пользователей.</span><span class="sxs-lookup"><span data-stu-id="1f97f-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="1f97f-107">Сбор данных KHI обычно является первым этапом реализации методологии качества вызовов (CQM), который фокусируется на обеспечении качества звука для пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="1f97f-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="1f97f-108">Если у вас возникнут вопросы об использовании CQM, вы можете отдать свои вопросы в cqmfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1f97f-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="1f97f-109">В афише рассматриваются следующие темы:</span><span class="sxs-lookup"><span data-stu-id="1f97f-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="1f97f-110">Что представляют собой ключевые индикаторы работоспособности?</span><span class="sxs-lookup"><span data-stu-id="1f97f-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="1f97f-111">Сбор данных KHI</span><span class="sxs-lookup"><span data-stu-id="1f97f-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="1f97f-112">Процесс исправления для всех ролей сервера</span><span class="sxs-lookup"><span data-stu-id="1f97f-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="1f97f-113">Глоссарий</span><span class="sxs-lookup"><span data-stu-id="1f97f-113">Glossary</span></span>

  - <span data-ttu-id="1f97f-114">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="1f97f-114">Front-end Servers</span></span>

  - <span data-ttu-id="1f97f-115">Внутренние серверы SQL Server</span><span class="sxs-lookup"><span data-stu-id="1f97f-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="1f97f-116">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="1f97f-116">Mediation Servers</span></span>

  - <span data-ttu-id="1f97f-117">Пограничные серверы</span><span class="sxs-lookup"><span data-stu-id="1f97f-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="1f97f-118">Что представляют собой ключевые индикаторы работоспособности?</span><span class="sxs-lookup"><span data-stu-id="1f97f-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="1f97f-119">Ключевые индикаторы работоспособности представляют собой счетчики производительности с пороговыми значениями, предназначенными для выявления проблем с работой пользователей.</span><span class="sxs-lookup"><span data-stu-id="1f97f-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="1f97f-120">Сбор данных KHI обычно является первым этапом реализации методологии качества вызовов (CQM), который фокусируется на обеспечении качества звука для пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="1f97f-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="1f97f-121">Кхис используются в дополнение к стандартным решениям для мониторинга Lync (например, System Center Operations Manager, синтетические транзакции, мониторингу сервера), а не к этим решениям.</span><span class="sxs-lookup"><span data-stu-id="1f97f-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="1f97f-122">Соберите счетчики производительности KHI и заполните электронную таблицу KHI, сопровождающую электронное руководство по работе с сетью, чтобы создать систему показателей, которая поможет вам определить работоспособность развертывания Lync на сервере.</span><span class="sxs-lookup"><span data-stu-id="1f97f-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="1f97f-123">После заполнения он поможет восстановить среду и предоставит дополнительные сведения другим заинтересованным сторонам.</span><span class="sxs-lookup"><span data-stu-id="1f97f-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="1f97f-124">Оцените Кхис на месячном уровне и внедрите их в действующие рабочие процессы развертывания.</span><span class="sxs-lookup"><span data-stu-id="1f97f-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="1f97f-125">Скачайте электронное [руководство по сетевым подключениям Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677) , чтобы просмотреть полный список кхис и получить связанные электронные таблицы.</span><span class="sxs-lookup"><span data-stu-id="1f97f-125">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="1f97f-126">Сбор данных KHI</span><span class="sxs-lookup"><span data-stu-id="1f97f-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="1f97f-127">Запустите сценарий KHI, включенный в сетевое руководство Lync Server на каждом сервере Lync.</span><span class="sxs-lookup"><span data-stu-id="1f97f-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="1f97f-128">При этом сборщик данных будет создан в системном мониторе с именем KHI.</span><span class="sxs-lookup"><span data-stu-id="1f97f-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="1f97f-129">По умолчанию данные будут опрашиваться каждые 15 секунд.</span><span class="sxs-lookup"><span data-stu-id="1f97f-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="1f97f-130">Прежде чем начать рабочий день компании, перейдите на каждый сервер Lync Server и запустите сборщик данных KHI.</span><span class="sxs-lookup"><span data-stu-id="1f97f-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="1f97f-131">В конце этого дня остановите сборщик данных KHI и скопируйте данные в центральное расположение.</span><span class="sxs-lookup"><span data-stu-id="1f97f-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="1f97f-132">После использования системного монитора для заполнения электронной таблицы KHI, включенной в загрузку сетевого руководства Lync Server, Сравните результаты с рекомендуемыми целями.</span><span class="sxs-lookup"><span data-stu-id="1f97f-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="1f97f-133">Процесс исправления для всех ролей сервера</span><span class="sxs-lookup"><span data-stu-id="1f97f-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="1f97f-134">Для каждого сервера в реализации Lync Начните с проверки работоспособности компонентов сервера и производительности системы на требуемом уровне.</span><span class="sxs-lookup"><span data-stu-id="1f97f-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="1f97f-135">Только после этого необходимо просмотреть индикаторы, связанные с ролью сервера, в общей реализации Lync.</span><span class="sxs-lookup"><span data-stu-id="1f97f-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="1f97f-136">Начните с сбора данных о производительности KHI для всех серверов.</span><span class="sxs-lookup"><span data-stu-id="1f97f-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="1f97f-137">Для каждой из системных ролей (сведения, обсуждаемые далее в этом документе) определяют, удовлетворяют ли основные компоненты системы рекомендуемым целям.</span><span class="sxs-lookup"><span data-stu-id="1f97f-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="1f97f-138">Если это не так, устраните производительность системы и повторно Соберите данные KHI и обеспечьте работоспособность системы перед просмотром метрик, относящихся к роли сервера в реализации Lync.</span><span class="sxs-lookup"><span data-stu-id="1f97f-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="1f97f-139">Работоспособность компонентов для всех ролей определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1f97f-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="1f97f-140">Загрузка \< ЦП 80%</span><span class="sxs-lookup"><span data-stu-id="1f97f-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="1f97f-141">Средний объем записи \< на диск 10 мс</span><span class="sxs-lookup"><span data-stu-id="1f97f-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="1f97f-142">Средний объем чтения \< с диска (10 мс)</span><span class="sxs-lookup"><span data-stu-id="1f97f-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="1f97f-143">Доступная \>память 20% всего МБ</span><span class="sxs-lookup"><span data-stu-id="1f97f-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="1f97f-144">Длина \< очереди сети 2</span><span class="sxs-lookup"><span data-stu-id="1f97f-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="1f97f-145">Отброшенные пакеты (входящие и исходящие) = 0</span><span class="sxs-lookup"><span data-stu-id="1f97f-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="1f97f-146">Глоссарий</span><span class="sxs-lookup"><span data-stu-id="1f97f-146">Glossary</span></span>

<span data-ttu-id="1f97f-147">В этом плакате используются следующие термины и акронимы:</span><span class="sxs-lookup"><span data-stu-id="1f97f-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="1f97f-148">AS MCU = единица управления общим доступом к приложениям с поддержкой нескольких точек</span><span class="sxs-lookup"><span data-stu-id="1f97f-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="1f97f-149">AV MCU = аудио/видео MCU</span><span class="sxs-lookup"><span data-stu-id="1f97f-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="1f97f-150">IM MCU = MCU обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="1f97f-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="1f97f-151">UCWA = веб-API единой системы обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="1f97f-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="1f97f-152">AV Edge = обход звука/видео через пограничный</span><span class="sxs-lookup"><span data-stu-id="1f97f-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="1f97f-153">Проверка подлинности AV = проверка подлинности звука и видео</span><span class="sxs-lookup"><span data-stu-id="1f97f-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="1f97f-154">Stack SIP = содержит основную реализацию SIP Lync</span><span class="sxs-lookup"><span data-stu-id="1f97f-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="1f97f-155">Прокси-сервер данных = используется для пограничного конференц-связи</span><span class="sxs-lookup"><span data-stu-id="1f97f-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="1f97f-156">LySS = служба хранилища Lync</span><span class="sxs-lookup"><span data-stu-id="1f97f-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="1f97f-157">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="1f97f-157">Front-end Servers</span></span>

<span data-ttu-id="1f97f-158">Следующие целевые объекты KHI относятся к серверам переднего плана в дополнение к основному работоспособности компонента:</span><span class="sxs-lookup"><span data-stu-id="1f97f-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f97f-159">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="1f97f-159">Functional area</span></span></th>
<th><span data-ttu-id="1f97f-160">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="1f97f-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f97f-161">AS/AV/IM MCU</span><span class="sxs-lookup"><span data-stu-id="1f97f-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="1f97f-162">Состояние &lt;работоспособности MCU 2</span><span class="sxs-lookup"><span data-stu-id="1f97f-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f97f-163">Веб-компоненты</span><span class="sxs-lookup"><span data-stu-id="1f97f-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="1f97f-164">Таймаутов AD для расширения списка &lt;рассылки 0</span><span class="sxs-lookup"><span data-stu-id="1f97f-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="1f97f-165">Сбои ABWQ = 0</span><span class="sxs-lookup"><span data-stu-id="1f97f-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="1f97f-166">Ошибок LIS = 0</span><span class="sxs-lookup"><span data-stu-id="1f97f-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="1f97f-167">Ошибок &lt; проверки подлинности 1/с</span><span class="sxs-lookup"><span data-stu-id="1f97f-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="1f97f-168">Отклонено запросов ASP.NET V4 = 0</span><span class="sxs-lookup"><span data-stu-id="1f97f-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f97f-169">Стек SIP</span><span class="sxs-lookup"><span data-stu-id="1f97f-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="1f97f-170">СР. Обработка &lt; входящих сообщений 1 сек</span><span class="sxs-lookup"><span data-stu-id="1f97f-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="1f97f-171">Отброшено &lt; входящих ответов, отброшенных &lt; входящих запросов 1/с отброшенных 1/с</span><span class="sxs-lookup"><span data-stu-id="1f97f-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="1f97f-172">Задержка &lt; очереди 100 мс</span><span class="sxs-lookup"><span data-stu-id="1f97f-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="1f97f-173">Задержка &lt; спрок 100 мс</span><span class="sxs-lookup"><span data-stu-id="1f97f-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="1f97f-174">Регулируемых запросов = 0</span><span class="sxs-lookup"><span data-stu-id="1f97f-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="1f97f-175">Ошибок &lt; проверки подлинности 1/с</span><span class="sxs-lookup"><span data-stu-id="1f97f-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="1f97f-176">Исходящих &lt; сообщений с истекшим сроком ожидания 2</span><span class="sxs-lookup"><span data-stu-id="1f97f-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="1f97f-177">Среднее время хранения &lt; входящего сообщения: 1 с</span><span class="sxs-lookup"><span data-stu-id="1f97f-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="1f97f-178">Подключения &lt; с управлением обтеканием 2</span><span class="sxs-lookup"><span data-stu-id="1f97f-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="1f97f-179">Средняя задержка &lt; очереди ожидания 2 с</span><span class="sxs-lookup"><span data-stu-id="1f97f-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f97f-180">LySS</span><span class="sxs-lookup"><span data-stu-id="1f97f-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="1f97f-181">% места, используемого в базе данных &lt; службы хранилища 80</span><span class="sxs-lookup"><span data-stu-id="1f97f-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="1f97f-182">#количество сбоев репликации реплики = 0</span><span class="sxs-lookup"><span data-stu-id="1f97f-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="1f97f-183">#событий потери данных = 0</span><span class="sxs-lookup"><span data-stu-id="1f97f-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f97f-184">SQL</span><span class="sxs-lookup"><span data-stu-id="1f97f-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="1f97f-185">Ожидаемый срок жизни &gt; страницы 300 сек.</span><span class="sxs-lookup"><span data-stu-id="1f97f-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="1f97f-186">Запросов пакетов в секунду &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="1f97f-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="1f97f-187">Внутренние серверы SQL Server</span><span class="sxs-lookup"><span data-stu-id="1f97f-187">Backend SQL Servers</span></span>

<span data-ttu-id="1f97f-188">Следующие целевые объекты KHI относятся к серверам SQL Server в дополнение к базовому работоспособности компонента:</span><span class="sxs-lookup"><span data-stu-id="1f97f-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f97f-189">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="1f97f-189">Functional area</span></span></th>
<th><span data-ttu-id="1f97f-190">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="1f97f-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f97f-191">SQL</span><span class="sxs-lookup"><span data-stu-id="1f97f-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="1f97f-192">Ожидаемый срок жизни &gt; страницы 300 сек.</span><span class="sxs-lookup"><span data-stu-id="1f97f-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="1f97f-193">Запросов пакетов в секунду &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="1f97f-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="1f97f-194">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="1f97f-194">Mediation Servers</span></span>

<span data-ttu-id="1f97f-195">Следующие целевые объекты KHI относятся к серверам-посредникам в дополнение к основному работоспособности компонента:</span><span class="sxs-lookup"><span data-stu-id="1f97f-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f97f-196">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="1f97f-196">Functional area</span></span></th>
<th><span data-ttu-id="1f97f-197">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="1f97f-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f97f-198">Служба сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="1f97f-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="1f97f-199">Индекс сбоя вызова при загрузке = 0</span><span class="sxs-lookup"><span data-stu-id="1f97f-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="1f97f-200">Неудачные вызовы из &lt;-за прокси-сервера 10</span><span class="sxs-lookup"><span data-stu-id="1f97f-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="1f97f-201">Неудачные вызовы из &lt;-за шлюза 10</span><span class="sxs-lookup"><span data-stu-id="1f97f-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="1f97f-202">Отклонено вызовов (вход или выход) = 0</span><span class="sxs-lookup"><span data-stu-id="1f97f-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="1f97f-203">Отсутствующие кандидаты мультимедиа = 0</span><span class="sxs-lookup"><span data-stu-id="1f97f-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="1f97f-204">Ошибки проверки подключения к мультимедиа = 0</span><span class="sxs-lookup"><span data-stu-id="1f97f-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="1f97f-205">Пограничные серверы</span><span class="sxs-lookup"><span data-stu-id="1f97f-205">Edge Servers</span></span>

<span data-ttu-id="1f97f-206">Следующие целевые цели KHI относятся к пограничным серверам в дополнение к основному работоспособности компонента:</span><span class="sxs-lookup"><span data-stu-id="1f97f-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f97f-207">Функциональная область</span><span class="sxs-lookup"><span data-stu-id="1f97f-207">Functional area</span></span></th>
<th><span data-ttu-id="1f97f-208">Целевые показатели</span><span class="sxs-lookup"><span data-stu-id="1f97f-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f97f-209">Проверка подлинности AV</span><span class="sxs-lookup"><span data-stu-id="1f97f-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="1f97f-210">Неудачных запросов &lt; 20/с</span><span class="sxs-lookup"><span data-stu-id="1f97f-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f97f-211">Пограничный сервер AV</span><span class="sxs-lookup"><span data-stu-id="1f97f-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="1f97f-212">Частота попыток &lt;проверки подлинности: 20/с</span><span class="sxs-lookup"><span data-stu-id="1f97f-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="1f97f-213">Ошибок &lt;выделения — 20/с</span><span class="sxs-lookup"><span data-stu-id="1f97f-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="1f97f-214">Отброшено &lt;пакетов 300/сек</span><span class="sxs-lookup"><span data-stu-id="1f97f-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f97f-215">Прокси-сервер данных</span><span class="sxs-lookup"><span data-stu-id="1f97f-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="1f97f-216">Регулируемые подключения &lt; к серверу 3</span><span class="sxs-lookup"><span data-stu-id="1f97f-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="1f97f-217">Система регулирует &lt;1</span><span class="sxs-lookup"><span data-stu-id="1f97f-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f97f-218">Стек SIP</span><span class="sxs-lookup"><span data-stu-id="1f97f-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="1f97f-219">Подключений через лимит, &lt; отброшенных 1</span><span class="sxs-lookup"><span data-stu-id="1f97f-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="1f97f-220">Отправляются с &lt;истекшим сроком ожидания (10)</span><span class="sxs-lookup"><span data-stu-id="1f97f-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="1f97f-221">Подключения &lt;с управлением обтеканием 100</span><span class="sxs-lookup"><span data-stu-id="1f97f-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="1f97f-222">Отброшено &lt; входящих запросов 1/с</span><span class="sxs-lookup"><span data-stu-id="1f97f-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="1f97f-223">Средняя обработка &lt; сообщений 3 с</span><span class="sxs-lookup"><span data-stu-id="1f97f-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1f97f-224">См. также</span><span class="sxs-lookup"><span data-stu-id="1f97f-224">See Also</span></span>


[<span data-ttu-id="1f97f-225">Руководство по сетевым подключениям Lync Server</span><span class="sxs-lookup"><span data-stu-id="1f97f-225">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="1f97f-226">Основные индикаторы работоспособности: основа для обслуживания работоспособных серверов Lync</span><span class="sxs-lookup"><span data-stu-id="1f97f-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="1f97f-227">Методология качества вызовов Lync</span><span class="sxs-lookup"><span data-stu-id="1f97f-227">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

