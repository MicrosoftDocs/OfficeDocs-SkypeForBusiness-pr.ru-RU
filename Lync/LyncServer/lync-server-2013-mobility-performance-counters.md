---
title: 'Lync Server 2013: счетчики производительности мобильных устройств'
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
ms.openlocfilehash: a0f0d9170b4526c443b88c9227af8f2c55dae4b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="10e37-102">Счетчики производительности мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10e37-102">Mobility performance counters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10e37-103">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="10e37-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="10e37-104">В приведенных ниже таблицах перечислены имена и описания счетчиков производительности, которые можно использовать для мониторинга серверов, на которых работает веб-API объединенных коммуникаций (UCWA) и служба Mobility Server 2013 MCX Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="10e37-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="10e37-105">Имя категории для счетчиков в таблице UCWA — **Ls: Web — UCWA**.</span><span class="sxs-lookup"><span data-stu-id="10e37-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="10e37-106">Имя категории для счетчиков в таблице MCX Mobility Service — **Ls: Web — Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="10e37-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="10e37-107">Счетчики производительности для UCWA</span><span class="sxs-lookup"><span data-stu-id="10e37-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10e37-108">Счетчик</span><span class="sxs-lookup"><span data-stu-id="10e37-108">Counter</span></span></th>
<th><span data-ttu-id="10e37-109">Описание</span><span class="sxs-lookup"><span data-stu-id="10e37-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10e37-110">Число активных приложений</span><span class="sxs-lookup"><span data-stu-id="10e37-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="10e37-111">Текущее число приложений</span><span class="sxs-lookup"><span data-stu-id="10e37-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-112">Число модальностей общего доступа к приложениям</span><span class="sxs-lookup"><span data-stu-id="10e37-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="10e37-113">Текущее число модальностей общего доступа к приложениям</span><span class="sxs-lookup"><span data-stu-id="10e37-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-114">Число модальностей активных аудио</span><span class="sxs-lookup"><span data-stu-id="10e37-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="10e37-115">Текущее число модальностей звука</span><span class="sxs-lookup"><span data-stu-id="10e37-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-116">Число модальных модальностей совместной работы с данными</span><span class="sxs-lookup"><span data-stu-id="10e37-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="10e37-117">Текущее число модальностей совместной работы с данными</span><span class="sxs-lookup"><span data-stu-id="10e37-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-118">Задержка получения фотографий в службе Active Directory (МС)</span><span class="sxs-lookup"><span data-stu-id="10e37-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="10e37-119">Этот счетчик показывает среднее время (в миллисекундах), в течение которого извлекается фотография из Active Directory</span><span class="sxs-lookup"><span data-stu-id="10e37-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-120">Число модальностей активных сообщений</span><span class="sxs-lookup"><span data-stu-id="10e37-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="10e37-121">Текущее число модальностей обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="10e37-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-122">Число модальных модальностей для активного панорамного изображения</span><span class="sxs-lookup"><span data-stu-id="10e37-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="10e37-123">Текущее число модальностей панорамного видео</span><span class="sxs-lookup"><span data-stu-id="10e37-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-124">Число активных ожидающих операций получения</span><span class="sxs-lookup"><span data-stu-id="10e37-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="10e37-125">Число активных в настоящее время ожидающих обработки. долговременные подключения к серверу</span><span class="sxs-lookup"><span data-stu-id="10e37-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-126">Число активных сеансов</span><span class="sxs-lookup"><span data-stu-id="10e37-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="10e37-127">Текущее число конечных точек, зарегистрированных в UCWA для каждого приложения и всего</span><span class="sxs-lookup"><span data-stu-id="10e37-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-128">Число активных экземпляров пользователей</span><span class="sxs-lookup"><span data-stu-id="10e37-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="10e37-129">Текущее число пользовательских экземпляров</span><span class="sxs-lookup"><span data-stu-id="10e37-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-130">Активные пользовательские экземпляры без приложения</span><span class="sxs-lookup"><span data-stu-id="10e37-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="10e37-131">Текущее число пользовательских экземпляров без приложения</span><span class="sxs-lookup"><span data-stu-id="10e37-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-132">Число модальностей активного видео</span><span class="sxs-lookup"><span data-stu-id="10e37-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="10e37-133">Текущее число модальностей видео</span><span class="sxs-lookup"><span data-stu-id="10e37-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-134">Получено запросов на создание приложений/сек</span><span class="sxs-lookup"><span data-stu-id="10e37-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="10e37-135">Частота полученных запросов на создание приложений (в секунду)</span><span class="sxs-lookup"><span data-stu-id="10e37-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-136">КАК ошибки присоединения к MCU</span><span class="sxs-lookup"><span data-stu-id="10e37-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="10e37-137">Количество неудачных попыток присоединения к MCU</span><span class="sxs-lookup"><span data-stu-id="10e37-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-138">Сбои при соединении с MCU AV</span><span class="sxs-lookup"><span data-stu-id="10e37-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="10e37-139">Количество сбоев присоединения к AV MCU</span><span class="sxs-lookup"><span data-stu-id="10e37-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-140">Среднее время запуска приложения (МС)</span><span class="sxs-lookup"><span data-stu-id="10e37-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="10e37-141">Среднее время запуска приложения в миллисекундах</span><span class="sxs-lookup"><span data-stu-id="10e37-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-142">Среднее время жизни сеанса (МС)</span><span class="sxs-lookup"><span data-stu-id="10e37-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="10e37-143">Среднее время существования сеанса в миллисекундах (мс)</span><span class="sxs-lookup"><span data-stu-id="10e37-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-144">Ошибки присоединения к данным MCU</span><span class="sxs-lookup"><span data-stu-id="10e37-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="10e37-145">Количество сбоев присоединения к данным MCU</span><span class="sxs-lookup"><span data-stu-id="10e37-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-146">Задержка поиска контактов Exchange (МС)</span><span class="sxs-lookup"><span data-stu-id="10e37-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="10e37-147">Этот счетчик показывает среднее время (в миллисекундах) для поиска контакта в Exchange</span><span class="sxs-lookup"><span data-stu-id="10e37-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-148">Задержка получения фотографий в Exchange HD (МС)</span><span class="sxs-lookup"><span data-stu-id="10e37-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="10e37-149">Этот счетчик показывает среднее время (в миллисекундах), в течение которого извлекается фотография из Exchange</span><span class="sxs-lookup"><span data-stu-id="10e37-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-150">HTTP-ответов 4xx/сек</span><span class="sxs-lookup"><span data-stu-id="10e37-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="10e37-151">Частота ответов с кодом HTTP 4xx (в секунду)</span><span class="sxs-lookup"><span data-stu-id="10e37-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-152">Ответов HTTP 5xx/сек</span><span class="sxs-lookup"><span data-stu-id="10e37-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="10e37-153">Частота ответов с кодом HTTP 5xx на секунду</span><span class="sxs-lookup"><span data-stu-id="10e37-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-154">Сбои при соединении с MCU мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="10e37-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="10e37-155">Количество сбоев присоединения к IM MCU</span><span class="sxs-lookup"><span data-stu-id="10e37-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-156">Количество неудачных попыток получения фотографий Active Directory</span><span class="sxs-lookup"><span data-stu-id="10e37-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="10e37-157">Общее число неудачных попыток получения фотографий из Active Directory</span><span class="sxs-lookup"><span data-stu-id="10e37-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-158">Количество неудачных попыток поиска контактов</span><span class="sxs-lookup"><span data-stu-id="10e37-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="10e37-159">Общее число неудачных попыток поиска в контактах в Exchange</span><span class="sxs-lookup"><span data-stu-id="10e37-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-160">Количество ошибок десериализации</span><span class="sxs-lookup"><span data-stu-id="10e37-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="10e37-161">Общее число неудачных попыток десериализации</span><span class="sxs-lookup"><span data-stu-id="10e37-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-162">Количество неудачных попыток получения фотографий в формате HD</span><span class="sxs-lookup"><span data-stu-id="10e37-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="10e37-163">Общее число неудачных попыток получения фотографий HD из Exchange</span><span class="sxs-lookup"><span data-stu-id="10e37-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-164">Превышение максимального числа подписок для каждого приложения</span><span class="sxs-lookup"><span data-stu-id="10e37-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="10e37-165">Количество запросов на подписку, превышающих максимальное разрешенное для каждого приложения</span><span class="sxs-lookup"><span data-stu-id="10e37-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-166">Превышение максимального числа подписок на пакет</span><span class="sxs-lookup"><span data-stu-id="10e37-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="10e37-167">Количество запросов на подписку, превышающих максимально допустимое значение для пакета</span><span class="sxs-lookup"><span data-stu-id="10e37-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-168">Ошибки подписки на присутствие</span><span class="sxs-lookup"><span data-stu-id="10e37-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="10e37-169">Количество неудачных попыток подписки на присутствие</span><span class="sxs-lookup"><span data-stu-id="10e37-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-170">Регистрация сбоев конечной точки</span><span class="sxs-lookup"><span data-stu-id="10e37-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="10e37-171">Количество неудачных попыток регистрации конечных точек</span><span class="sxs-lookup"><span data-stu-id="10e37-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-172">Requests Received/Second (Полученных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="10e37-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="10e37-173">Частота полученных запросов (в секунду)</span><span class="sxs-lookup"><span data-stu-id="10e37-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-174">Requests Succeeded/Second (Успешных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="10e37-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="10e37-175">Частота успешных запросов (в секунду) (коды ответа HTTP 2xx и 3xx)</span><span class="sxs-lookup"><span data-stu-id="10e37-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-176">Успешных запросов на создание приложений в секунду</span><span class="sxs-lookup"><span data-stu-id="10e37-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="10e37-177">Частота успешных запросов на создание приложений (в секунду)</span><span class="sxs-lookup"><span data-stu-id="10e37-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-178">Время ожидания получения счетчика ожидания получения</span><span class="sxs-lookup"><span data-stu-id="10e37-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="10e37-179">Число ожидающих операций по истечении времени ожидания</span><span class="sxs-lookup"><span data-stu-id="10e37-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-180">Всего получено запросов на создание приложений</span><span class="sxs-lookup"><span data-stu-id="10e37-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="10e37-181">Общее количество запросов на создание приложений, полученных с момента запуска службы</span><span class="sxs-lookup"><span data-stu-id="10e37-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-182">Общее количество ответов HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="10e37-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="10e37-183">Общее число ответов HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="10e37-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-184">Всего ответов HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="10e37-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="10e37-185">Общее число ответов HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="10e37-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-186">Общее количество запросов, полученных по каналу команд</span><span class="sxs-lookup"><span data-stu-id="10e37-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="10e37-187">Общее число запросов, полученных по каналу управления</span><span class="sxs-lookup"><span data-stu-id="10e37-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-188">Total Requests Succeeded (Всего успешных запросов)</span><span class="sxs-lookup"><span data-stu-id="10e37-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="10e37-189">Общее число успешно выполненных запросов</span><span class="sxs-lookup"><span data-stu-id="10e37-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-190">Общее число инициированных сеансов</span><span class="sxs-lookup"><span data-stu-id="10e37-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="10e37-191">Общее количество сеансов, инициированных с момента запуска службы</span><span class="sxs-lookup"><span data-stu-id="10e37-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-192">Общее число сеансов, завершенных из-за превышения времени ожидания простоя</span><span class="sxs-lookup"><span data-stu-id="10e37-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="10e37-193">Общее число сеансов, которые были завершены из-за истечения времени ожидания в режиме бездействия пользователя</span><span class="sxs-lookup"><span data-stu-id="10e37-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-194">Общее количество регулируемых приложений</span><span class="sxs-lookup"><span data-stu-id="10e37-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="10e37-195">Количество регулируемых приложений</span><span class="sxs-lookup"><span data-stu-id="10e37-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="10e37-196">Счетчики производительности для службы Mobility MCX</span><span class="sxs-lookup"><span data-stu-id="10e37-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10e37-197">Счетчик</span><span class="sxs-lookup"><span data-stu-id="10e37-197">Counter</span></span></th>
<th><span data-ttu-id="10e37-198">Описание</span><span class="sxs-lookup"><span data-stu-id="10e37-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10e37-199">Average Lifetime for a Session in Milliseconds
 (Среднее время существования сеанса в миллисекундах)</span><span class="sxs-lookup"><span data-stu-id="10e37-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="10e37-200">Среднее время существования сеанса в миллисекундах (мс)</span><span class="sxs-lookup"><span data-stu-id="10e37-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-201">Current Push Notification Subscriptions (Текущие подписки на push-уведомления)</span><span class="sxs-lookup"><span data-stu-id="10e37-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="10e37-202">Текущее число подписок на push-уведомления.</span><span class="sxs-lookup"><span data-stu-id="10e37-202">The current number of push notification subscriptions.</span></span> <span data-ttu-id="10e37-203">Это число в сочетании с числом текущих активных сеансов представляет подмножество текущих активных сеансов, зарегистрированных для устройств с Windows Mobile или iPhone.</span><span class="sxs-lookup"><span data-stu-id="10e37-203">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-204">Currently Active Network Timeout Poll Count (Число текущих активных опросов времени ожидания сети)</span><span class="sxs-lookup"><span data-stu-id="10e37-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="10e37-205">Число опросов сети с истекшим временем ожидания</span><span class="sxs-lookup"><span data-stu-id="10e37-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-206">Currently Active Poll Count (Число активных опросов)</span><span class="sxs-lookup"><span data-stu-id="10e37-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="10e37-207">Число активных опросов (долгосрочные подключения к серверу)</span><span class="sxs-lookup"><span data-stu-id="10e37-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-208">Currently Active Session Count (Число текущих активных сеансов)</span><span class="sxs-lookup"><span data-stu-id="10e37-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="10e37-209">Текущее число конечных точек, зарегистрированных в службе Mobility Service</span><span class="sxs-lookup"><span data-stu-id="10e37-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-210">Currently Active Session Count with Active Presence Subscriptions (Число текущих активных сеансов с активными подписками на сведения о присутствии)</span><span class="sxs-lookup"><span data-stu-id="10e37-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="10e37-211">Число текущих активных сеансов с активными подписками на сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="10e37-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-212">Push Notification Requests Failed/Second (Неудачных запросов на push-уведомления/с)</span><span class="sxs-lookup"><span data-stu-id="10e37-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="10e37-213">Частота push-уведомлений, завершившихся сбоем (в секунду)</span><span class="sxs-lookup"><span data-stu-id="10e37-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-214">Push Notification Requests Succeeded/Second (Успешных запросов на push-уведомления/с)</span><span class="sxs-lookup"><span data-stu-id="10e37-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="10e37-215">Частота успешно выполненных push-уведомлений (в секунду)</span><span class="sxs-lookup"><span data-stu-id="10e37-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-216">Push Notification Requests Throttled/Second (Регулируемых запросов на push-уведомления/с)</span><span class="sxs-lookup"><span data-stu-id="10e37-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="10e37-217">Частота регулируемых push-уведомлений (в секунду)</span><span class="sxs-lookup"><span data-stu-id="10e37-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-218">Push Notification Requests/Second (Запросов push-уведомлений/с)</span><span class="sxs-lookup"><span data-stu-id="10e37-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="10e37-219">Частота отправленных push-уведомлений (в секунду)</span><span class="sxs-lookup"><span data-stu-id="10e37-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-220">Requests Failed/Second (Неудачных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="10e37-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="10e37-221">Частота запросов, завершившихся ошибками (в секунду)</span><span class="sxs-lookup"><span data-stu-id="10e37-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-222">Requests Received/Second (Полученных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="10e37-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="10e37-223">Частота полученных запросов (в секунду)</span><span class="sxs-lookup"><span data-stu-id="10e37-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-224">Requests Rejected/Second (Отклоненных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="10e37-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="10e37-225">Частота отклоненных запросов (в секунду)</span><span class="sxs-lookup"><span data-stu-id="10e37-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-226">Requests Succeeded/Second (Успешных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="10e37-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="10e37-227">Частота успешных запросов (в секунду)</span><span class="sxs-lookup"><span data-stu-id="10e37-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-228">Succeeded Initiate Session Requests/Second (Успешных запросов на запуск сеанса/с)</span><span class="sxs-lookup"><span data-stu-id="10e37-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="10e37-p102">Частота успешных запросов на получение расположения (в секунду). Запросы на запуск сеанса потребляют больше всего ресурсов ЦП на сервере. Поддерживаемая пиковая нагрузка составляет 12 сеансов в секунду. Устойчивость зависит от других нагрузок на сервере. Запуск сеанса, как правило, означает вход пользователя, с момента выхода которого из сеанса прошло довольно много времени.</span><span class="sxs-lookup"><span data-stu-id="10e37-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-234">Total Declined Inbound Voice Calls (Всего отклоненных входящих голосовых звонков)</span><span class="sxs-lookup"><span data-stu-id="10e37-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="10e37-235">Общее число отклоненных входящих голосовых звонков</span><span class="sxs-lookup"><span data-stu-id="10e37-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-236">Total Failed Inbound Voice Calls (Всего неудачных входящих голосовых звонков)</span><span class="sxs-lookup"><span data-stu-id="10e37-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="10e37-237">Общее число входящих голосовых звонков, завершившихся сбоем</span><span class="sxs-lookup"><span data-stu-id="10e37-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-238">Total Failed Outbound Voice Calls (Всего неудачных исходящих вызовов)</span><span class="sxs-lookup"><span data-stu-id="10e37-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="10e37-239">Общее число исходящих голосовых вызовов, завершившихся сбоем</span><span class="sxs-lookup"><span data-stu-id="10e37-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-240">Total number of sessions terminated by user (Общее число сеансов, завершенных пользователем)</span><span class="sxs-lookup"><span data-stu-id="10e37-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="10e37-241">Общее число сеансов, завершенных пользователями</span><span class="sxs-lookup"><span data-stu-id="10e37-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-242">Total Push Notification Requests (Всего запросов на push-уведомления)</span><span class="sxs-lookup"><span data-stu-id="10e37-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="10e37-243">Общее число запросов на push-уведомления</span><span class="sxs-lookup"><span data-stu-id="10e37-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-244">Total Push Notification Requests Failed (Всего неудачных запросов на push-уведомления)</span><span class="sxs-lookup"><span data-stu-id="10e37-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="10e37-245">Общее число запросов на push-уведомления, завершившихся сбоем</span><span class="sxs-lookup"><span data-stu-id="10e37-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-246">Total Push Notification Requests Succeeded (Всего успешных запросов на push-уведомления)</span><span class="sxs-lookup"><span data-stu-id="10e37-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="10e37-247">Общее число успешно выполненных запросов на push-уведомления</span><span class="sxs-lookup"><span data-stu-id="10e37-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-248">Total Push Notification Requests Throttled (Всего ограниченных запросов на push-уведомления)</span><span class="sxs-lookup"><span data-stu-id="10e37-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="10e37-249">Общее число запросов на push-уведомления, которые были ограничены</span><span class="sxs-lookup"><span data-stu-id="10e37-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-250">Total Requests Failed (Всего неудачных запросов)</span><span class="sxs-lookup"><span data-stu-id="10e37-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="10e37-251">Общее число запросов, завершившихся сбоем</span><span class="sxs-lookup"><span data-stu-id="10e37-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-252">Total Requests received on the Command Channel (Всего запросов, полученных по каналу управления)</span><span class="sxs-lookup"><span data-stu-id="10e37-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="10e37-253">Общее число запросов, полученных по каналу управления</span><span class="sxs-lookup"><span data-stu-id="10e37-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-254">Total Requests Rejected (Всего отклоненных запросов)</span><span class="sxs-lookup"><span data-stu-id="10e37-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="10e37-255">Общее число отлоненных запросов</span><span class="sxs-lookup"><span data-stu-id="10e37-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-256">Total Requests Succeeded (Всего успешных запросов)</span><span class="sxs-lookup"><span data-stu-id="10e37-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="10e37-257">ОБщее число запросов, поступивших в службу Mobility Service, которые были успешно выполнены</span><span class="sxs-lookup"><span data-stu-id="10e37-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-258">Total Session Initiated Count (Всего запущенных сеансов)</span><span class="sxs-lookup"><span data-stu-id="10e37-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="10e37-259">Общее число сеансов, запущенных с момента запуска службы Mobility Service</span><span class="sxs-lookup"><span data-stu-id="10e37-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-260">Total Sessions Terminated Because of User Idle Timeout (Всего сеансов, завершенных из-за таймаута бездействия пользователя)</span><span class="sxs-lookup"><span data-stu-id="10e37-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="10e37-261">Общее число сеансов, которые были завершены из-за истечения времени ожидания в режиме бездействия пользователя</span><span class="sxs-lookup"><span data-stu-id="10e37-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10e37-262">Total Successful Inbound Voice Calls (Всего успешных входящих голосовых вызовов)</span><span class="sxs-lookup"><span data-stu-id="10e37-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="10e37-263">Общее число успешных входящих голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="10e37-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10e37-264">Total Successful Outbound Voice Calls (Всего успешных исходящих голосовых вызовов)</span><span class="sxs-lookup"><span data-stu-id="10e37-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="10e37-265">Общее число успешных исходящих голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="10e37-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

