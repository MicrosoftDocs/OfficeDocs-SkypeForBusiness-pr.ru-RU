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
ms.openlocfilehash: 439c179476c89de8a5245e80e26586d42f4f6e3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="53586-102">Счетчики производительности мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53586-102">Mobility performance counters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53586-103">_**Тема последнего изменения:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="53586-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="53586-104">В следующих таблицах перечислены имена и описания счетчиков производительности, которые можно использовать для мониторинга серверов, использующих веб-API единой системы обмена сообщениями (УКВА) и службы Lync Server 2013 МККС Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="53586-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="53586-105">Имя категории для счетчиков в таблице UCWA — **LS:WEB — UCWA**.</span><span class="sxs-lookup"><span data-stu-id="53586-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="53586-106">Имя категории для счетчиков в таблице службы Mcx Mobility Service — **LS:WEB — Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="53586-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="53586-107">Счетчики производительности для UCWA</span><span class="sxs-lookup"><span data-stu-id="53586-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53586-108">Счетчик</span><span class="sxs-lookup"><span data-stu-id="53586-108">Counter</span></span></th>
<th><span data-ttu-id="53586-109">Описание</span><span class="sxs-lookup"><span data-stu-id="53586-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53586-110">Active Application Count (Число активных приложений)</span><span class="sxs-lookup"><span data-stu-id="53586-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="53586-111">Текущее число приложений</span><span class="sxs-lookup"><span data-stu-id="53586-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-112">Active Application Sharing Modality Count (Число активных модальностей общего доступа к приложениям)</span><span class="sxs-lookup"><span data-stu-id="53586-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="53586-113">Текущее число модальностей общего доступа к приложениям</span><span class="sxs-lookup"><span data-stu-id="53586-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-114">Active Audio Modality Count (Число активных модальностей звука)</span><span class="sxs-lookup"><span data-stu-id="53586-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="53586-115">Текущее число модальностей звука</span><span class="sxs-lookup"><span data-stu-id="53586-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-116">Active Data Collaboration Modality Count (Число активных модальностей совместной работы с данными)</span><span class="sxs-lookup"><span data-stu-id="53586-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="53586-117">Текущее число модальностей совместной работы с данными</span><span class="sxs-lookup"><span data-stu-id="53586-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-118">Active Directory Photo Get Latency (ms) (Задержка получения фотографий из Active Directory (мс))</span><span class="sxs-lookup"><span data-stu-id="53586-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="53586-119">Этот счетчик показывает среднее время (в миллисекундах), необходимое для получения фотографии из каталога Аctive Directory.</span><span class="sxs-lookup"><span data-stu-id="53586-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-120">Active Messaging Modality Count (Число активных модальностей обмена сообщениями)</span><span class="sxs-lookup"><span data-stu-id="53586-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="53586-121">Текущее число модальностей обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="53586-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-122">Active Panoramic Video Modality Count (Число активных модальностей панорамного видео)</span><span class="sxs-lookup"><span data-stu-id="53586-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="53586-123">Текущее число модальностей панорамного видео</span><span class="sxs-lookup"><span data-stu-id="53586-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-124">Active Pending Get Count (Число активных операций ожидания получения)</span><span class="sxs-lookup"><span data-stu-id="53586-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="53586-125">Число активных операций ожидания получения; долгосрочные подключения к серверу</span><span class="sxs-lookup"><span data-stu-id="53586-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-126">Active Session Count (Число активных сеансов)</span><span class="sxs-lookup"><span data-stu-id="53586-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="53586-127">Текущее число конечных точек, зарегистрированных в интерфейсе UCWA, на приложение и общее число</span><span class="sxs-lookup"><span data-stu-id="53586-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-128">Active User Instance Count (Число активных экземпляров пользователей)</span><span class="sxs-lookup"><span data-stu-id="53586-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="53586-129">Текущее число экземпляров пользователей</span><span class="sxs-lookup"><span data-stu-id="53586-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-130">Active User Instances without Application (Активные экземпляры пользователей без приложения)</span><span class="sxs-lookup"><span data-stu-id="53586-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="53586-131">Текущее число экземпляров пользователей без приложения</span><span class="sxs-lookup"><span data-stu-id="53586-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-132">Active Video Modality Count (Число активных модальностей видео)</span><span class="sxs-lookup"><span data-stu-id="53586-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="53586-133">Текущее число модальностей видео</span><span class="sxs-lookup"><span data-stu-id="53586-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-134">Application Creation Requests Received/Second (Получено запросов на создание приложения/с)</span><span class="sxs-lookup"><span data-stu-id="53586-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="53586-135">Частота полученных запросов (в секунду) на создание приложения</span><span class="sxs-lookup"><span data-stu-id="53586-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-136">AS MCU Join Failures (Сбои присоединения MCU AS)</span><span class="sxs-lookup"><span data-stu-id="53586-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="53586-137">Число неудачных попыток присоединения блоков MCU AS</span><span class="sxs-lookup"><span data-stu-id="53586-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-138">AV MCU Join Failures (Сбои присоединения MCU AV)</span><span class="sxs-lookup"><span data-stu-id="53586-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="53586-139">Число неудачных попыток присоединения блоков MCU (AV)</span><span class="sxs-lookup"><span data-stu-id="53586-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-140">Average Application Startup Time (ms) (Среднее время загрузки приложения (мс))</span><span class="sxs-lookup"><span data-stu-id="53586-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="53586-141">Среднее время загрузки приложения в миллисекундах</span><span class="sxs-lookup"><span data-stu-id="53586-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-142">Average Lifetime for Session (ms) (Среднее время существования сеанса (мс))</span><span class="sxs-lookup"><span data-stu-id="53586-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="53586-143">Среднее время существования сеанса в миллисекундах (мс)</span><span class="sxs-lookup"><span data-stu-id="53586-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-144">Data MCU Join Failures (Сбои присоединения MCU данных)</span><span class="sxs-lookup"><span data-stu-id="53586-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="53586-145">Число неудачных попыток присоединения блоков MCU данных</span><span class="sxs-lookup"><span data-stu-id="53586-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-146">Exchange Contact Search Latency (ms) (Задержка поиска контакта в Exchange (мс))</span><span class="sxs-lookup"><span data-stu-id="53586-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="53586-147">Этот счетчик показывает среднее время (в миллисекундах), затрачиваемое на поиск контакта Exchange.</span><span class="sxs-lookup"><span data-stu-id="53586-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-148">Задержка получения фотографий в формате HD из Exchange (мс)</span><span class="sxs-lookup"><span data-stu-id="53586-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="53586-149">Этот счетчик показывает среднее время (в миллисекундах), затрачиваемое на получение фотографии с сервера Exchange.</span><span class="sxs-lookup"><span data-stu-id="53586-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-150">Ответов HTTP 4xx/с</span><span class="sxs-lookup"><span data-stu-id="53586-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="53586-151">Частота ответов с кодом HTTP 4xx (в секунду)</span><span class="sxs-lookup"><span data-stu-id="53586-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-152">Ответов HTTP 5xx/с</span><span class="sxs-lookup"><span data-stu-id="53586-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="53586-153">Частота ответов с кодом HTTP 5xx (в секунду)</span><span class="sxs-lookup"><span data-stu-id="53586-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-154">IM MCU Join Failures (Сбои присоединения MCU IM)</span><span class="sxs-lookup"><span data-stu-id="53586-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="53586-155">Число неудачных попыток присоединения блоков MCU IM</span><span class="sxs-lookup"><span data-stu-id="53586-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-156">Number of Active Directory Photo Get Failures (Число сбоев получения фотографий из Active Directory)</span><span class="sxs-lookup"><span data-stu-id="53586-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="53586-157">Общее число неудачных попыток получения фотографий из Active Directory</span><span class="sxs-lookup"><span data-stu-id="53586-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-158">Number of Contact Search failures (Число сбоев поиска контактов)</span><span class="sxs-lookup"><span data-stu-id="53586-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="53586-159">Общее число неудачных попыток поиска контактов в Exchange</span><span class="sxs-lookup"><span data-stu-id="53586-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-160">Number of Deserialization Failures (Число сбоев десериализации)</span><span class="sxs-lookup"><span data-stu-id="53586-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="53586-161">Общее число неудачных попыток десериализации</span><span class="sxs-lookup"><span data-stu-id="53586-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-162">Количество сбоев при получении фотографий HD</span><span class="sxs-lookup"><span data-stu-id="53586-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="53586-163">Общее число неудачных попыток получения фотографий в формате HD с сервера Exchange</span><span class="sxs-lookup"><span data-stu-id="53586-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-164">Over The Maximum Subscriptions Per Application (Превышение максимального числа подписок на приложение)</span><span class="sxs-lookup"><span data-stu-id="53586-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="53586-165">Число запросов на подписку, превышающих максимальное значение для приложения</span><span class="sxs-lookup"><span data-stu-id="53586-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-166">Over The Maximum Subscriptions Per Batch (Превышение максимального числа подписок на пакет)</span><span class="sxs-lookup"><span data-stu-id="53586-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="53586-167">Число запросов на подписку, превышающих максимальное значение для пакета</span><span class="sxs-lookup"><span data-stu-id="53586-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-168">Presence Subscription Failures (Сбои подписок отслеживания присутствия)</span><span class="sxs-lookup"><span data-stu-id="53586-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="53586-169">Число неудачных попыток подписаться на сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="53586-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-170">Registering Endpoint Failures (Сбои регистрации конечных точек)</span><span class="sxs-lookup"><span data-stu-id="53586-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="53586-171">Число сбоев регистрации конечных точек</span><span class="sxs-lookup"><span data-stu-id="53586-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-172">Requests Received/Second (Полученных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="53586-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="53586-173">Частота полученных запросов (в секунду)</span><span class="sxs-lookup"><span data-stu-id="53586-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-174">Requests Succeeded/Second (Успешных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="53586-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="53586-175">Частота успешных запросов (в секунду) (коды ответов HTTP 2xx/3xx)</span><span class="sxs-lookup"><span data-stu-id="53586-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-176">Succeeded Create Application Requests/Second (Успешных запросов на создание приложений/с)</span><span class="sxs-lookup"><span data-stu-id="53586-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="53586-177">Частота успешных запросов (в секунду) на создание приложения</span><span class="sxs-lookup"><span data-stu-id="53586-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-178">Timed Out Pending Get Count (Число ожидающих операций получения с истекшим временем ожидания)</span><span class="sxs-lookup"><span data-stu-id="53586-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="53586-179">Число ожидающих операций получения с истекшим временем ожидания</span><span class="sxs-lookup"><span data-stu-id="53586-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-180">Total Application Creation Requests Received (Всего полученных запросов на создание приложений)</span><span class="sxs-lookup"><span data-stu-id="53586-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="53586-181">Общее число запросов на создание приложений, полученных с момента запуска службы</span><span class="sxs-lookup"><span data-stu-id="53586-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-182">Всего ответов HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="53586-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="53586-183">Общее число ответов HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="53586-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-184">Всего отчетов HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="53586-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="53586-185">Общее число ответов HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="53586-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-186">Total Requests received on the Command Channel (Всего запросов, полученных по каналу управления)</span><span class="sxs-lookup"><span data-stu-id="53586-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="53586-187">Общее число запросов, полученных по каналу управления</span><span class="sxs-lookup"><span data-stu-id="53586-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-188">Total Requests Succeeded (Всего успешных запросов)</span><span class="sxs-lookup"><span data-stu-id="53586-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="53586-189">Общее число успешных запросов</span><span class="sxs-lookup"><span data-stu-id="53586-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-190">Total Sessions Initiated (Всего запущенных сеансов)</span><span class="sxs-lookup"><span data-stu-id="53586-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="53586-191">Общее число сеансов, запущенных с момента запуска службы</span><span class="sxs-lookup"><span data-stu-id="53586-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-192">Total Sessions Terminated Because of User Idle Timeout (Всего сеансов, завершенных из-за таймаута бездействия)</span><span class="sxs-lookup"><span data-stu-id="53586-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="53586-193">Общее число сеансов, которые были завершены из-за истечения времени ожидания в режиме бездействия пользователя</span><span class="sxs-lookup"><span data-stu-id="53586-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-194">Total Throttled Applications (Всего приложений, к которым применяется регулирование)</span><span class="sxs-lookup"><span data-stu-id="53586-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="53586-195">Число приложений, к которым применяется регулирование</span><span class="sxs-lookup"><span data-stu-id="53586-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="53586-196">Счетчики производительности для службы Mcx Mobility Service</span><span class="sxs-lookup"><span data-stu-id="53586-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53586-197">Счетчик</span><span class="sxs-lookup"><span data-stu-id="53586-197">Counter</span></span></th>
<th><span data-ttu-id="53586-198">Описание</span><span class="sxs-lookup"><span data-stu-id="53586-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53586-199">Average Lifetime for a Session in Milliseconds (Среднее время существования сеанса в миллисекундах)</span><span class="sxs-lookup"><span data-stu-id="53586-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="53586-200">Среднее время существования сеанса в миллисекундах (мс)</span><span class="sxs-lookup"><span data-stu-id="53586-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-201">Current Push Notification Subscriptions (Текущие подписки на push-уведомления)</span><span class="sxs-lookup"><span data-stu-id="53586-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="53586-p101">Текущее число подписок на push-уведомления. Это число вместе с счетчиком текущих активных сеансов представляет подмножество текущих активных сеансов, зарегистрированных для устройств Windows Mobile или iPhone.</span><span class="sxs-lookup"><span data-stu-id="53586-p101">The current number of push notification subscriptions. This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-204">Currently Active Network Timeout Poll Count (Число текущих активных опросов времени ожидания сети)</span><span class="sxs-lookup"><span data-stu-id="53586-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="53586-205">Число опросов сети с истекшим временем ожидания</span><span class="sxs-lookup"><span data-stu-id="53586-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-206">Currently Active Poll Count (Число активных опросов)</span><span class="sxs-lookup"><span data-stu-id="53586-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="53586-207">Число активных опросов (долгосрочные подключения к серверу)</span><span class="sxs-lookup"><span data-stu-id="53586-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-208">Currently Active Session Count (Число текущих активных сеансов)</span><span class="sxs-lookup"><span data-stu-id="53586-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="53586-209">Текущее число конечных точек, зарегистрированных в службе Mobility Service</span><span class="sxs-lookup"><span data-stu-id="53586-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-210">Currently Active Session Count with Active Presence Subscriptions (Число текущих активных сеансов с активными подписками на сведения о присутствии)</span><span class="sxs-lookup"><span data-stu-id="53586-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="53586-211">Число текущих активных сеансов с активными подписками на сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="53586-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-212">Push Notification Requests Failed/Second (Неудачных запросов на push-уведомления/с)</span><span class="sxs-lookup"><span data-stu-id="53586-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="53586-213">Частота push-уведомлений, завершившихся сбоем (в секунду)</span><span class="sxs-lookup"><span data-stu-id="53586-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-214">Push Notification Requests Succeeded/Second (Успешных запросов на push-уведомления/с)</span><span class="sxs-lookup"><span data-stu-id="53586-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="53586-215">Частота успешно выполненных push-уведомлений (в секунду)</span><span class="sxs-lookup"><span data-stu-id="53586-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-216">Push Notification Requests Throttled/Second (Регулируемых запросов на push-уведомления/с)</span><span class="sxs-lookup"><span data-stu-id="53586-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="53586-217">Частота регулируемых push-уведомлений (в секунду)</span><span class="sxs-lookup"><span data-stu-id="53586-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-218">Push Notification Requests/Second (Запросов push-уведомлений/с)</span><span class="sxs-lookup"><span data-stu-id="53586-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="53586-219">Частота отправленных push-уведомлений (в секунду)</span><span class="sxs-lookup"><span data-stu-id="53586-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-220">Requests Failed/Second (Неудачных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="53586-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="53586-221">Частота запросов, завершившихся ошибками (в секунду)</span><span class="sxs-lookup"><span data-stu-id="53586-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-222">Requests Received/Second (Полученных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="53586-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="53586-223">Частота полученных запросов (в секунду)</span><span class="sxs-lookup"><span data-stu-id="53586-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-224">Requests Rejected/Second (Отклоненных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="53586-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="53586-225">Частота отклоненных запросов (в секунду)</span><span class="sxs-lookup"><span data-stu-id="53586-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-226">Requests Succeeded/Second (Успешных запросов/с)</span><span class="sxs-lookup"><span data-stu-id="53586-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="53586-227">Частота успешных запросов (в секунду)</span><span class="sxs-lookup"><span data-stu-id="53586-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-228">Succeeded Initiate Session Requests/Second (Успешных запросов на запуск сеанса/с)</span><span class="sxs-lookup"><span data-stu-id="53586-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="53586-p102">Частота успешных запросов на получение расположения (в секунду). Запросы на запуск сеанса потребляют больше всего ресурсов ЦП на сервере. Поддерживаемая пиковая нагрузка составляет 12 сеансов в секунду. Устойчивость зависит от других нагрузок на сервере. Запуск сеанса, как правило, означает вход пользователя, с момента выхода которого из сеанса прошло довольно много времени.</span><span class="sxs-lookup"><span data-stu-id="53586-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-234">Total Declined Inbound Voice Calls (Всего отклоненных входящих голосовых звонков)</span><span class="sxs-lookup"><span data-stu-id="53586-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="53586-235">Общее число отклоненных входящих голосовых звонков</span><span class="sxs-lookup"><span data-stu-id="53586-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-236">Total Failed Inbound Voice Calls (Всего неудачных входящих голосовых звонков)</span><span class="sxs-lookup"><span data-stu-id="53586-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="53586-237">Общее число входящих голосовых звонков, завершившихся сбоем</span><span class="sxs-lookup"><span data-stu-id="53586-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-238">Total Failed Outbound Voice Calls (Всего неудачных исходящих вызовов)</span><span class="sxs-lookup"><span data-stu-id="53586-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="53586-239">Общее число исходящих голосовых вызовов, завершившихся сбоем</span><span class="sxs-lookup"><span data-stu-id="53586-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-240">Total number of sessions terminated by user (Общее число сеансов, завершенных пользователем)</span><span class="sxs-lookup"><span data-stu-id="53586-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="53586-241">Общее число сеансов, завершенных пользователями</span><span class="sxs-lookup"><span data-stu-id="53586-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-242">Total Push Notification Requests (Всего запросов на push-уведомления)</span><span class="sxs-lookup"><span data-stu-id="53586-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="53586-243">Общее число запросов на push-уведомления</span><span class="sxs-lookup"><span data-stu-id="53586-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-244">Total Push Notification Requests Failed (Всего неудачных запросов на push-уведомления)</span><span class="sxs-lookup"><span data-stu-id="53586-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="53586-245">Общее число запросов на push-уведомления, завершившихся сбоем</span><span class="sxs-lookup"><span data-stu-id="53586-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-246">Total Push Notification Requests Succeeded (Всего успешных запросов на push-уведомления)</span><span class="sxs-lookup"><span data-stu-id="53586-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="53586-247">Общее число успешно выполненных запросов на push-уведомления</span><span class="sxs-lookup"><span data-stu-id="53586-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-248">Total Push Notification Requests Throttled (Всего ограниченных запросов на push-уведомления)</span><span class="sxs-lookup"><span data-stu-id="53586-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="53586-249">Общее число запросов на push-уведомления, которые были ограничены</span><span class="sxs-lookup"><span data-stu-id="53586-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-250">Total Requests Failed (Всего неудачных запросов)</span><span class="sxs-lookup"><span data-stu-id="53586-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="53586-251">Общее число запросов, завершившихся сбоем</span><span class="sxs-lookup"><span data-stu-id="53586-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-252">Total Requests received on the Command Channel (Всего запросов, полученных по каналу управления)</span><span class="sxs-lookup"><span data-stu-id="53586-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="53586-253">Общее число запросов, полученных по каналу управления</span><span class="sxs-lookup"><span data-stu-id="53586-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-254">Total Requests Rejected (Всего отклоненных запросов)</span><span class="sxs-lookup"><span data-stu-id="53586-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="53586-255">Общее число отклоненных запросов</span><span class="sxs-lookup"><span data-stu-id="53586-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-256">Total Requests Succeeded (Всего успешных запросов)</span><span class="sxs-lookup"><span data-stu-id="53586-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="53586-257">Общее число запросов, поступивших в службу Mobility Service, которые были успешно выполнены</span><span class="sxs-lookup"><span data-stu-id="53586-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-258">Total Session Initiated Count (Всего запущенных сеансов)</span><span class="sxs-lookup"><span data-stu-id="53586-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="53586-259">Общее число сеансов, запущенных с момента запуска службы Mobility Service</span><span class="sxs-lookup"><span data-stu-id="53586-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-260">Total Sessions Terminated Because of User Idle Timeout (Всего сеансов, завершенных из-за таймаута бездействия пользователя)</span><span class="sxs-lookup"><span data-stu-id="53586-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="53586-261">Общее число сеансов, которые были завершены из-за истечения времени ожидания в режиме бездействия пользователя</span><span class="sxs-lookup"><span data-stu-id="53586-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53586-262">Total Successful Inbound Voice Calls (Всего успешных входящих голосовых вызовов)</span><span class="sxs-lookup"><span data-stu-id="53586-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="53586-263">Общее число успешных входящих голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="53586-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53586-264">Total Successful Outbound Voice Calls (Всего успешных исходящих голосовых вызовов)</span><span class="sxs-lookup"><span data-stu-id="53586-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="53586-265">Общее число успешных исходящих голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="53586-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

