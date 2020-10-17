---
title: 'Lync Server 2013: счетчики производительности мобильных устройств'
description: 'Lync Server 2013: счетчики производительности мобильных устройств.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 922288f6c026f088d651dc61afdcb6ba04fed30a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550535"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="54c34-103">Счетчики производительности мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54c34-103">Mobility performance counters in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54c34-104">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="54c34-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="54c34-105">В приведенных ниже таблицах перечислены имена и описания счетчиков производительности, которые можно использовать для мониторинга серверов, на которых работает веб-API объединенных коммуникаций (UCWA) и служба Mobility Server 2013 MCX Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="54c34-105">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="54c34-106">Имя категории для счетчиков в таблице UCWA — **Ls: Web — UCWA**.</span><span class="sxs-lookup"><span data-stu-id="54c34-106">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="54c34-107">Имя категории для счетчиков в таблице MCX Mobility Service — **Ls: Web — Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="54c34-107">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="54c34-108">Счетчики производительности для UCWA</span><span class="sxs-lookup"><span data-stu-id="54c34-108">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54c34-109">Счетчик</span><span class="sxs-lookup"><span data-stu-id="54c34-109">Counter</span></span></th>
<th><span data-ttu-id="54c34-110">Описание</span><span class="sxs-lookup"><span data-stu-id="54c34-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54c34-111">Число активных приложений</span><span class="sxs-lookup"><span data-stu-id="54c34-111">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="54c34-112">Текущее число приложений</span><span class="sxs-lookup"><span data-stu-id="54c34-112">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-113">Число модальностей общего доступа к приложениям</span><span class="sxs-lookup"><span data-stu-id="54c34-113">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="54c34-114">Текущее число модальностей общего доступа к приложениям</span><span class="sxs-lookup"><span data-stu-id="54c34-114">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-115">Число модальностей активных аудио</span><span class="sxs-lookup"><span data-stu-id="54c34-115">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="54c34-116">Текущее число модальностей звука</span><span class="sxs-lookup"><span data-stu-id="54c34-116">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-117">Число модальных модальностей совместной работы с данными</span><span class="sxs-lookup"><span data-stu-id="54c34-117">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="54c34-118">Текущее число модальностей совместной работы с данными</span><span class="sxs-lookup"><span data-stu-id="54c34-118">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-119">Задержка получения фотографий в службе Active Directory (МС)</span><span class="sxs-lookup"><span data-stu-id="54c34-119">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="54c34-120">Этот счетчик показывает среднее время (в миллисекундах), в течение которого извлекается фотография из Active Directory</span><span class="sxs-lookup"><span data-stu-id="54c34-120">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-121">Число модальностей активных сообщений</span><span class="sxs-lookup"><span data-stu-id="54c34-121">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="54c34-122">Текущее число модальностей обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="54c34-122">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-123">Число модальных модальностей для активного панорамного изображения</span><span class="sxs-lookup"><span data-stu-id="54c34-123">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="54c34-124">Текущее число модальностей панорамного видео</span><span class="sxs-lookup"><span data-stu-id="54c34-124">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-125">Число активных ожидающих операций получения</span><span class="sxs-lookup"><span data-stu-id="54c34-125">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="54c34-126">Число активных в настоящее время ожидающих обработки. долговременные подключения к серверу</span><span class="sxs-lookup"><span data-stu-id="54c34-126">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-127">Число активных сеансов</span><span class="sxs-lookup"><span data-stu-id="54c34-127">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="54c34-128">Текущее число конечных точек, зарегистрированных в UCWA для каждого приложения и всего</span><span class="sxs-lookup"><span data-stu-id="54c34-128">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-129">Число активных экземпляров пользователей</span><span class="sxs-lookup"><span data-stu-id="54c34-129">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="54c34-130">Текущее число пользовательских экземпляров</span><span class="sxs-lookup"><span data-stu-id="54c34-130">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-131">Активные пользовательские экземпляры без приложения</span><span class="sxs-lookup"><span data-stu-id="54c34-131">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="54c34-132">Текущее число пользовательских экземпляров без приложения</span><span class="sxs-lookup"><span data-stu-id="54c34-132">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-133">Число модальностей активного видео</span><span class="sxs-lookup"><span data-stu-id="54c34-133">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="54c34-134">Текущее число модальностей видео</span><span class="sxs-lookup"><span data-stu-id="54c34-134">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-135">Получено запросов на создание приложений/сек</span><span class="sxs-lookup"><span data-stu-id="54c34-135">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="54c34-136">Частота полученных запросов на создание приложений (в секунду)</span><span class="sxs-lookup"><span data-stu-id="54c34-136">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-137">КАК ошибки присоединения к MCU</span><span class="sxs-lookup"><span data-stu-id="54c34-137">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="54c34-138">Количество неудачных попыток присоединения к MCU</span><span class="sxs-lookup"><span data-stu-id="54c34-138">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-139">Сбои при соединении с MCU AV</span><span class="sxs-lookup"><span data-stu-id="54c34-139">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="54c34-140">Количество сбоев присоединения к AV MCU</span><span class="sxs-lookup"><span data-stu-id="54c34-140">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-141">Среднее время запуска приложения (МС)</span><span class="sxs-lookup"><span data-stu-id="54c34-141">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="54c34-142">Среднее время запуска приложения в миллисекундах</span><span class="sxs-lookup"><span data-stu-id="54c34-142">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-143">Среднее время жизни сеанса (МС)</span><span class="sxs-lookup"><span data-stu-id="54c34-143">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="54c34-144">Среднее время существования сеанса в миллисекундах (мс)</span><span class="sxs-lookup"><span data-stu-id="54c34-144">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-145">Ошибки присоединения к данным MCU</span><span class="sxs-lookup"><span data-stu-id="54c34-145">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="54c34-146">Количество сбоев присоединения к данным MCU</span><span class="sxs-lookup"><span data-stu-id="54c34-146">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-147">Задержка поиска контактов Exchange (МС)</span><span class="sxs-lookup"><span data-stu-id="54c34-147">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="54c34-148">Этот счетчик показывает среднее время (в миллисекундах) для поиска контакта в Exchange</span><span class="sxs-lookup"><span data-stu-id="54c34-148">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-149">Задержка получения фотографий в Exchange HD (МС)</span><span class="sxs-lookup"><span data-stu-id="54c34-149">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="54c34-150">Этот счетчик показывает среднее время (в миллисекундах), в течение которого извлекается фотография из Exchange</span><span class="sxs-lookup"><span data-stu-id="54c34-150">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-151">HTTP-ответов 4xx/сек</span><span class="sxs-lookup"><span data-stu-id="54c34-151">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="54c34-152">Частота ответов с кодом HTTP 4xx (в секунду)</span><span class="sxs-lookup"><span data-stu-id="54c34-152">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-153">Ответов HTTP 5xx/сек</span><span class="sxs-lookup"><span data-stu-id="54c34-153">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="54c34-154">Частота ответов с кодом HTTP 5xx на секунду</span><span class="sxs-lookup"><span data-stu-id="54c34-154">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-155">Сбои при соединении с MCU мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="54c34-155">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="54c34-156">Количество сбоев присоединения к IM MCU</span><span class="sxs-lookup"><span data-stu-id="54c34-156">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-157">Количество неудачных попыток получения фотографий Active Directory</span><span class="sxs-lookup"><span data-stu-id="54c34-157">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="54c34-158">Общее число неудачных попыток получения фотографий из Active Directory</span><span class="sxs-lookup"><span data-stu-id="54c34-158">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-159">Количество неудачных попыток поиска контактов</span><span class="sxs-lookup"><span data-stu-id="54c34-159">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="54c34-160">Общее число неудачных попыток поиска в контактах в Exchange</span><span class="sxs-lookup"><span data-stu-id="54c34-160">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-161">Количество ошибок десериализации</span><span class="sxs-lookup"><span data-stu-id="54c34-161">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="54c34-162">Общее число неудачных попыток десериализации</span><span class="sxs-lookup"><span data-stu-id="54c34-162">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-163">Количество неудачных попыток получения фотографий в формате HD</span><span class="sxs-lookup"><span data-stu-id="54c34-163">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="54c34-164">Общее число неудачных попыток получения фотографий HD из Exchange</span><span class="sxs-lookup"><span data-stu-id="54c34-164">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-165">Превышение максимального числа подписок для каждого приложения</span><span class="sxs-lookup"><span data-stu-id="54c34-165">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="54c34-166">Количество запросов на подписку, превышающих максимальное разрешенное для каждого приложения</span><span class="sxs-lookup"><span data-stu-id="54c34-166">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-167">Превышение максимального числа подписок на пакет</span><span class="sxs-lookup"><span data-stu-id="54c34-167">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="54c34-168">Количество запросов на подписку, превышающих максимально допустимое значение для пакета</span><span class="sxs-lookup"><span data-stu-id="54c34-168">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-169">Ошибки подписки на присутствие</span><span class="sxs-lookup"><span data-stu-id="54c34-169">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="54c34-170">Количество неудачных попыток подписки на присутствие</span><span class="sxs-lookup"><span data-stu-id="54c34-170">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-171">Регистрация сбоев конечной точки</span><span class="sxs-lookup"><span data-stu-id="54c34-171">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="54c34-172">Количество неудачных попыток регистрации конечных точек</span><span class="sxs-lookup"><span data-stu-id="54c34-172">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-173">Requests Received/Second (Полученных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="54c34-173">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="54c34-174">Частота полученных запросов (в секунду)</span><span class="sxs-lookup"><span data-stu-id="54c34-174">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-175">Requests Succeeded/Second (Успешных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="54c34-175">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="54c34-176">Частота успешных запросов (в секунду) (коды ответа HTTP 2xx и 3xx)</span><span class="sxs-lookup"><span data-stu-id="54c34-176">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-177">Успешных запросов на создание приложений в секунду</span><span class="sxs-lookup"><span data-stu-id="54c34-177">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="54c34-178">Частота успешных запросов на создание приложений (в секунду)</span><span class="sxs-lookup"><span data-stu-id="54c34-178">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-179">Время ожидания получения счетчика ожидания получения</span><span class="sxs-lookup"><span data-stu-id="54c34-179">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="54c34-180">Число ожидающих операций по истечении времени ожидания</span><span class="sxs-lookup"><span data-stu-id="54c34-180">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-181">Всего получено запросов на создание приложений</span><span class="sxs-lookup"><span data-stu-id="54c34-181">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="54c34-182">Общее количество запросов на создание приложений, полученных с момента запуска службы</span><span class="sxs-lookup"><span data-stu-id="54c34-182">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-183">Общее количество ответов HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="54c34-183">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="54c34-184">Общее число ответов HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="54c34-184">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-185">Всего ответов HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="54c34-185">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="54c34-186">Общее число ответов HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="54c34-186">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-187">Общее количество запросов, полученных по каналу команд</span><span class="sxs-lookup"><span data-stu-id="54c34-187">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="54c34-188">Общее число запросов, полученных по каналу управления</span><span class="sxs-lookup"><span data-stu-id="54c34-188">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-189">Total Requests Succeeded (Всего успешных запросов)</span><span class="sxs-lookup"><span data-stu-id="54c34-189">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="54c34-190">Общее число успешно выполненных запросов</span><span class="sxs-lookup"><span data-stu-id="54c34-190">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-191">Общее число инициированных сеансов</span><span class="sxs-lookup"><span data-stu-id="54c34-191">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="54c34-192">Общее количество сеансов, инициированных с момента запуска службы</span><span class="sxs-lookup"><span data-stu-id="54c34-192">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-193">Общее число сеансов, завершенных из-за превышения времени ожидания простоя</span><span class="sxs-lookup"><span data-stu-id="54c34-193">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="54c34-194">Общее число сеансов, которые были завершены из-за истечения времени ожидания в режиме бездействия пользователя</span><span class="sxs-lookup"><span data-stu-id="54c34-194">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-195">Общее количество регулируемых приложений</span><span class="sxs-lookup"><span data-stu-id="54c34-195">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="54c34-196">Количество регулируемых приложений</span><span class="sxs-lookup"><span data-stu-id="54c34-196">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="54c34-197">Счетчики производительности для службы Mobility MCX</span><span class="sxs-lookup"><span data-stu-id="54c34-197">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54c34-198">Счетчик</span><span class="sxs-lookup"><span data-stu-id="54c34-198">Counter</span></span></th>
<th><span data-ttu-id="54c34-199">Описание</span><span class="sxs-lookup"><span data-stu-id="54c34-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54c34-200">Average Lifetime for a Session in Milliseconds
 (Среднее время существования сеанса в миллисекундах)</span><span class="sxs-lookup"><span data-stu-id="54c34-200">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="54c34-201">Среднее время существования сеанса в миллисекундах (мс)</span><span class="sxs-lookup"><span data-stu-id="54c34-201">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-202">Current Push Notification Subscriptions (Текущие подписки на push-уведомления)</span><span class="sxs-lookup"><span data-stu-id="54c34-202">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="54c34-203">Текущее число подписок на push-уведомления.</span><span class="sxs-lookup"><span data-stu-id="54c34-203">The current number of push notification subscriptions.</span></span> <span data-ttu-id="54c34-204">Это число в сочетании с числом текущих активных сеансов представляет подмножество текущих активных сеансов, зарегистрированных для устройств с Windows Mobile или iPhone.</span><span class="sxs-lookup"><span data-stu-id="54c34-204">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-205">Currently Active Network Timeout Poll Count (Число текущих активных опросов времени ожидания сети)</span><span class="sxs-lookup"><span data-stu-id="54c34-205">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="54c34-206">Число опросов сети с истекшим временем ожидания</span><span class="sxs-lookup"><span data-stu-id="54c34-206">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-207">Currently Active Poll Count (Число активных опросов)</span><span class="sxs-lookup"><span data-stu-id="54c34-207">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="54c34-208">Число активных опросов (долгосрочные подключения к серверу)</span><span class="sxs-lookup"><span data-stu-id="54c34-208">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-209">Currently Active Session Count (Число текущих активных сеансов)</span><span class="sxs-lookup"><span data-stu-id="54c34-209">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="54c34-210">Текущее число конечных точек, зарегистрированных в службе Mobility Service</span><span class="sxs-lookup"><span data-stu-id="54c34-210">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-211">Currently Active Session Count with Active Presence Subscriptions (Число текущих активных сеансов с активными подписками на сведения о присутствии)</span><span class="sxs-lookup"><span data-stu-id="54c34-211">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="54c34-212">Число текущих активных сеансов с активными подписками на сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="54c34-212">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-213">Push Notification Requests Failed/Second (Неудачных запросов на push-уведомления/с)</span><span class="sxs-lookup"><span data-stu-id="54c34-213">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="54c34-214">Частота push-уведомлений, завершившихся сбоем (в секунду)</span><span class="sxs-lookup"><span data-stu-id="54c34-214">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-215">Push Notification Requests Succeeded/Second (Успешных запросов на push-уведомления/с)</span><span class="sxs-lookup"><span data-stu-id="54c34-215">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="54c34-216">Частота успешно выполненных push-уведомлений (в секунду)</span><span class="sxs-lookup"><span data-stu-id="54c34-216">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-217">Push Notification Requests Throttled/Second (Регулируемых запросов на push-уведомления/с)</span><span class="sxs-lookup"><span data-stu-id="54c34-217">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="54c34-218">Частота регулируемых push-уведомлений (в секунду)</span><span class="sxs-lookup"><span data-stu-id="54c34-218">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-219">Push Notification Requests/Second (Запросов push-уведомлений/с)</span><span class="sxs-lookup"><span data-stu-id="54c34-219">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="54c34-220">Частота отправленных push-уведомлений (в секунду)</span><span class="sxs-lookup"><span data-stu-id="54c34-220">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-221">Requests Failed/Second (Неудачных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="54c34-221">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="54c34-222">Частота запросов, завершившихся ошибками (в секунду)</span><span class="sxs-lookup"><span data-stu-id="54c34-222">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-223">Requests Received/Second (Полученных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="54c34-223">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="54c34-224">Частота полученных запросов (в секунду)</span><span class="sxs-lookup"><span data-stu-id="54c34-224">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-225">Requests Rejected/Second (Отклоненных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="54c34-225">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="54c34-226">Частота отклоненных запросов (в секунду)</span><span class="sxs-lookup"><span data-stu-id="54c34-226">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-227">Requests Succeeded/Second (Успешных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="54c34-227">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="54c34-228">Частота успешных запросов (в секунду)</span><span class="sxs-lookup"><span data-stu-id="54c34-228">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-229">Succeeded Initiate Session Requests/Second (Успешных запросов на запуск сеанса/с)</span><span class="sxs-lookup"><span data-stu-id="54c34-229">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="54c34-p102">Частота успешных запросов на получение расположения (в секунду). Запросы на запуск сеанса потребляют больше всего ресурсов ЦП на сервере. Поддерживаемая пиковая нагрузка составляет 12 сеансов в секунду. Устойчивость зависит от других нагрузок на сервере. Запуск сеанса, как правило, означает вход пользователя, с момента выхода которого из сеанса прошло довольно много времени.</span><span class="sxs-lookup"><span data-stu-id="54c34-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-235">Total Declined Inbound Voice Calls (Всего отклоненных входящих голосовых звонков)</span><span class="sxs-lookup"><span data-stu-id="54c34-235">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="54c34-236">Общее число отклоненных входящих голосовых звонков</span><span class="sxs-lookup"><span data-stu-id="54c34-236">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-237">Total Failed Inbound Voice Calls (Всего неудачных входящих голосовых звонков)</span><span class="sxs-lookup"><span data-stu-id="54c34-237">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="54c34-238">Общее число входящих голосовых звонков, завершившихся сбоем</span><span class="sxs-lookup"><span data-stu-id="54c34-238">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-239">Total Failed Outbound Voice Calls (Всего неудачных исходящих вызовов)</span><span class="sxs-lookup"><span data-stu-id="54c34-239">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="54c34-240">Общее число исходящих голосовых вызовов, завершившихся сбоем</span><span class="sxs-lookup"><span data-stu-id="54c34-240">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-241">Total number of sessions terminated by user (Общее число сеансов, завершенных пользователем)</span><span class="sxs-lookup"><span data-stu-id="54c34-241">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="54c34-242">Общее число сеансов, завершенных пользователями</span><span class="sxs-lookup"><span data-stu-id="54c34-242">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-243">Total Push Notification Requests (Всего запросов на push-уведомления)</span><span class="sxs-lookup"><span data-stu-id="54c34-243">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="54c34-244">Общее число запросов на push-уведомления</span><span class="sxs-lookup"><span data-stu-id="54c34-244">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-245">Total Push Notification Requests Failed (Всего неудачных запросов на push-уведомления)</span><span class="sxs-lookup"><span data-stu-id="54c34-245">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="54c34-246">Общее число запросов на push-уведомления, завершившихся сбоем</span><span class="sxs-lookup"><span data-stu-id="54c34-246">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-247">Total Push Notification Requests Succeeded (Всего успешных запросов на push-уведомления)</span><span class="sxs-lookup"><span data-stu-id="54c34-247">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="54c34-248">Общее число успешно выполненных запросов на push-уведомления</span><span class="sxs-lookup"><span data-stu-id="54c34-248">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-249">Total Push Notification Requests Throttled (Всего ограниченных запросов на push-уведомления)</span><span class="sxs-lookup"><span data-stu-id="54c34-249">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="54c34-250">Общее число запросов на push-уведомления, которые были ограничены</span><span class="sxs-lookup"><span data-stu-id="54c34-250">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-251">Total Requests Failed (Всего неудачных запросов)</span><span class="sxs-lookup"><span data-stu-id="54c34-251">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="54c34-252">Общее число запросов, завершившихся сбоем</span><span class="sxs-lookup"><span data-stu-id="54c34-252">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-253">Total Requests received on the Command Channel (Всего запросов, полученных по каналу управления)</span><span class="sxs-lookup"><span data-stu-id="54c34-253">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="54c34-254">Общее число запросов, полученных по каналу управления</span><span class="sxs-lookup"><span data-stu-id="54c34-254">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-255">Total Requests Rejected (Всего отклоненных запросов)</span><span class="sxs-lookup"><span data-stu-id="54c34-255">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="54c34-256">Общее число отлоненных запросов</span><span class="sxs-lookup"><span data-stu-id="54c34-256">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-257">Total Requests Succeeded (Всего успешных запросов)</span><span class="sxs-lookup"><span data-stu-id="54c34-257">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="54c34-258">ОБщее число запросов, поступивших в службу Mobility Service, которые были успешно выполнены</span><span class="sxs-lookup"><span data-stu-id="54c34-258">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-259">Total Session Initiated Count (Всего запущенных сеансов)</span><span class="sxs-lookup"><span data-stu-id="54c34-259">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="54c34-260">Общее число сеансов, запущенных с момента запуска службы Mobility Service</span><span class="sxs-lookup"><span data-stu-id="54c34-260">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-261">Total Sessions Terminated Because of User Idle Timeout (Всего сеансов, завершенных из-за таймаута бездействия пользователя)</span><span class="sxs-lookup"><span data-stu-id="54c34-261">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="54c34-262">Общее число сеансов, которые были завершены из-за истечения времени ожидания в режиме бездействия пользователя</span><span class="sxs-lookup"><span data-stu-id="54c34-262">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c34-263">Total Successful Inbound Voice Calls (Всего успешных входящих голосовых вызовов)</span><span class="sxs-lookup"><span data-stu-id="54c34-263">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="54c34-264">Общее число успешных входящих голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="54c34-264">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c34-265">Total Successful Outbound Voice Calls (Всего успешных исходящих голосовых вызовов)</span><span class="sxs-lookup"><span data-stu-id="54c34-265">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="54c34-266">Общее число успешных исходящих голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="54c34-266">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

