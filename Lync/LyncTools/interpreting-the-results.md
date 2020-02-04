---
title: Интерпретация результатов
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dcb1d84392cf9f56f2996281eb53e798690ba1e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="00bb9-102">Интерпретация результатов</span><span class="sxs-lookup"><span data-stu-id="00bb9-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00bb9-103">_**Тема последнего изменения:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="00bb9-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="00bb9-104">В средстве нагрузки и производительности Lync Server 2013 (Линкперфтул. exe) есть множество счетчиков, которые можно использовать для понимания того, что делает клиент и при возникновении проблем.</span><span class="sxs-lookup"><span data-stu-id="00bb9-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="00bb9-105">Счетчики клиента</span><span class="sxs-lookup"><span data-stu-id="00bb9-105">Client Counters</span></span>

<span data-ttu-id="00bb9-106">У каждого запущенного экземпляра Линкперфтул. exe есть отдельный экземпляр счетчиков.</span><span class="sxs-lookup"><span data-stu-id="00bb9-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="00bb9-107">Каждый экземпляр именуется ИДЕНТИФИКАТОРом процесса.</span><span class="sxs-lookup"><span data-stu-id="00bb9-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="00bb9-108">Если клиенты перегружены, могут возникать проблемы.</span><span class="sxs-lookup"><span data-stu-id="00bb9-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="00bb9-109">Чтобы предотвратить эти проблемы, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="00bb9-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="00bb9-110">Отслеживайте ресурсы ЦП и использование памяти на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="00bb9-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="00bb9-111">Если ЦП постоянно превышает 90%, сократите количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="00bb9-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="00bb9-112">Если объем памяти велик, вы можете столкнуться с проблемами, если файл подкачки слишком мал.</span><span class="sxs-lookup"><span data-stu-id="00bb9-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="00bb9-113">Убедитесь, что зарядка фиксации не достигнута на компьютере.</span><span class="sxs-lookup"><span data-stu-id="00bb9-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="00bb9-114">Если вы используете ограничения памяти, рекомендуем увеличить размер файла подкачки или уменьшить количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="00bb9-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="00bb9-115">В приведенных ниже таблицах перечислены ключевые счетчики производительности Линкперфтул.</span><span class="sxs-lookup"><span data-stu-id="00bb9-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="00bb9-116">**Общие сведения**</span><span class="sxs-lookup"><span data-stu-id="00bb9-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00bb9-117"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="00bb9-118"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-119">Время, потраченное на минуты</span><span class="sxs-lookup"><span data-stu-id="00bb9-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="00bb9-120">Время, потраченное с момента запуска процесса.</span><span class="sxs-lookup"><span data-stu-id="00bb9-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-121">Активные конечные точки</span><span class="sxs-lookup"><span data-stu-id="00bb9-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="00bb9-122">Количество конечных точек, которые в настоящее время подключены к серверу.</span><span class="sxs-lookup"><span data-stu-id="00bb9-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-123">Неудачные попытки входа</span><span class="sxs-lookup"><span data-stu-id="00bb9-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="00bb9-124">Общее количество ошибок входа в конечную точку.</span><span class="sxs-lookup"><span data-stu-id="00bb9-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-125">Попытки входа</span><span class="sxs-lookup"><span data-stu-id="00bb9-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="00bb9-126">Общее количество попыток входа в конечную точку.</span><span class="sxs-lookup"><span data-stu-id="00bb9-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-127">Конечные точки отключены</span><span class="sxs-lookup"><span data-stu-id="00bb9-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="00bb9-128">Общее количество отключенных конечных точек.</span><span class="sxs-lookup"><span data-stu-id="00bb9-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="00bb9-129">**Сведения о присутствии**</span><span class="sxs-lookup"><span data-stu-id="00bb9-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00bb9-130"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="00bb9-131"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-132">Звонки Сетпресенце</span><span class="sxs-lookup"><span data-stu-id="00bb9-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="00bb9-133">Общее количество попыток изменения присутствия.</span><span class="sxs-lookup"><span data-stu-id="00bb9-133">Total number of presence change attempts.</span></span> <span data-ttu-id="00bb9-134">Сведения о различных типах изменений присутствия можно найти в разделе Сетпресенце (тип присутствия), который вызывает счетчик производительности.</span><span class="sxs-lookup"><span data-stu-id="00bb9-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-135">NNN ответов для Сетпресенце</span><span class="sxs-lookup"><span data-stu-id="00bb9-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="00bb9-136">Общее количество кодов ответов NNN, полученных с сервера.</span><span class="sxs-lookup"><span data-stu-id="00bb9-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-137">Вызовы при присутствии</span><span class="sxs-lookup"><span data-stu-id="00bb9-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="00bb9-138">Общее количество попыток получения запросов на присутствие.</span><span class="sxs-lookup"><span data-stu-id="00bb9-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-139">NNN ответов для воздля присутствия</span><span class="sxs-lookup"><span data-stu-id="00bb9-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="00bb9-140">Общее количество кодов ответов NNN, полученных с сервера.</span><span class="sxs-lookup"><span data-stu-id="00bb9-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="00bb9-141">**Сведения о службе адресной книги**</span><span class="sxs-lookup"><span data-stu-id="00bb9-141">**Address Book service Information**</span></span>

<span data-ttu-id="00bb9-142">В этой категории содержатся счетчики, которые используются для отслеживания файлов и запросов службы веб-книги (ABS) и запроса на обслуживание адресной книги.</span><span class="sxs-lookup"><span data-stu-id="00bb9-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00bb9-143"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="00bb9-144"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-145">Попытка скачивания файлов с полными и дельта-файлами (ABS)</span><span class="sxs-lookup"><span data-stu-id="00bb9-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="00bb9-146">Общее количество попыток полных или Дельта запросов на скачивание файлов.</span><span class="sxs-lookup"><span data-stu-id="00bb9-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-147">Успешное скачивание полных и дельта-файлов в формате ABS</span><span class="sxs-lookup"><span data-stu-id="00bb9-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="00bb9-148">Общее количество попыток полных или Дельта запросов на скачивание файлов.</span><span class="sxs-lookup"><span data-stu-id="00bb9-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-149">Счетчики, связанные со службами веб-запросов в адресной книге</span><span class="sxs-lookup"><span data-stu-id="00bb9-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="00bb9-150">Счетчики, связанные с загрузкой файлов в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="00bb9-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-151">Попытка обращения к службе ABS</span><span class="sxs-lookup"><span data-stu-id="00bb9-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="00bb9-152">Общее количество попыток запросов службы веб-запросов в адресную книгу.</span><span class="sxs-lookup"><span data-stu-id="00bb9-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-153">Успешные вызовы ABS WS</span><span class="sxs-lookup"><span data-stu-id="00bb9-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="00bb9-154">Общее количество запросов на веб-службу адресной книги, которые возвращали успешный код ответа.</span><span class="sxs-lookup"><span data-stu-id="00bb9-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-155">Сбой вызовов ABS WS</span><span class="sxs-lookup"><span data-stu-id="00bb9-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="00bb9-156">Общее количество запросов на веб-службу адресной книги, которые возвращали код ответа об ошибке.</span><span class="sxs-lookup"><span data-stu-id="00bb9-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="00bb9-157">**Сведения о списке рассылки (DL)**</span><span class="sxs-lookup"><span data-stu-id="00bb9-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00bb9-158"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="00bb9-159"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-160">Попытки звонков</span><span class="sxs-lookup"><span data-stu-id="00bb9-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="00bb9-161">Общее количество предпроизведенных запросов на веб-службу расширения списка рассылки (ДЛКС).</span><span class="sxs-lookup"><span data-stu-id="00bb9-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-162">Успешные звонки</span><span class="sxs-lookup"><span data-stu-id="00bb9-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="00bb9-163">Общее количество запросов веб-службы ДЛКС, которые возвращали успешный код ответа.</span><span class="sxs-lookup"><span data-stu-id="00bb9-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-164">Не удалось выполнить звонки</span><span class="sxs-lookup"><span data-stu-id="00bb9-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="00bb9-165">Общее количество запросов веб-службы ДЛКС, которые возвращали код ответа об ошибке.</span><span class="sxs-lookup"><span data-stu-id="00bb9-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="00bb9-166">**Основные сведения о VoIP**</span><span class="sxs-lookup"><span data-stu-id="00bb9-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="00bb9-167">Счетчики производительности, указанные ниже, указаны в разделе "номера отчетов" для всех звонков по протоколу голосовой связи (VoIP), в том числе для звонков на сервер-посредник, сервер конференции, пограничный сервер, приложение группы ответа и автосекретарь конференции, если эти сценарии включены.</span><span class="sxs-lookup"><span data-stu-id="00bb9-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00bb9-168"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="00bb9-169"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-170">Активных звонков</span><span class="sxs-lookup"><span data-stu-id="00bb9-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="00bb9-171">Общее количество текущих и входящих и исходящих голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="00bb9-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-172">Прерванные звонки</span><span class="sxs-lookup"><span data-stu-id="00bb9-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="00bb9-173">Общее количество входящих и исходящих голосовых вызовов, которые уже были прерваны.</span><span class="sxs-lookup"><span data-stu-id="00bb9-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-174">Отклоненные звонки</span><span class="sxs-lookup"><span data-stu-id="00bb9-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="00bb9-175">Общее количество отклоненных входящих голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="00bb9-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-176">Попыток входящих и исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="00bb9-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="00bb9-177">Общее количество попыток входящих и исходящих голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="00bb9-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-178">Входящие и исходящие вызовы установлены</span><span class="sxs-lookup"><span data-stu-id="00bb9-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="00bb9-179">Общее количество установленных входящих и исходящих голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="00bb9-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-180">Получено звонков NNN</span><span class="sxs-lookup"><span data-stu-id="00bb9-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="00bb9-181">Общее количество кодов ответов NNN, полученных с сервера.</span><span class="sxs-lookup"><span data-stu-id="00bb9-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-182">Доля успешных похождения в VoIP (%)</span><span class="sxs-lookup"><span data-stu-id="00bb9-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="00bb9-183">Общее количество попыток установленного/общего количества звонков.</span><span class="sxs-lookup"><span data-stu-id="00bb9-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="00bb9-184">**Сведения о вызове службы группы ответа**</span><span class="sxs-lookup"><span data-stu-id="00bb9-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00bb9-185"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="00bb9-186"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-187">Активных звонков</span><span class="sxs-lookup"><span data-stu-id="00bb9-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="00bb9-188">Общее количество активных звонков в приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="00bb9-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-189">Попытки звонков</span><span class="sxs-lookup"><span data-stu-id="00bb9-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="00bb9-190">Общее количество попыток звонков.</span><span class="sxs-lookup"><span data-stu-id="00bb9-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="00bb9-191">**Информация о звонках в мгновенных сообщениях**</span><span class="sxs-lookup"><span data-stu-id="00bb9-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00bb9-192"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="00bb9-193"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-194">Активных звонков</span><span class="sxs-lookup"><span data-stu-id="00bb9-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="00bb9-195">Общее количество текущих входящих и исходящих звонков с мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="00bb9-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-196">Прерванные звонки</span><span class="sxs-lookup"><span data-stu-id="00bb9-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="00bb9-197">Общее количество уже прерванных входящих и исходящих вызовов мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="00bb9-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-198">Получено звонков NNN</span><span class="sxs-lookup"><span data-stu-id="00bb9-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="00bb9-199">Общее количество кодов ответов NNN, полученных с сервера.</span><span class="sxs-lookup"><span data-stu-id="00bb9-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-200">Полученные и отправленные МГНОВЕНные сообщения</span><span class="sxs-lookup"><span data-stu-id="00bb9-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="00bb9-201">Общее количество сообщений, полученных или отправленных для всех сеансов.</span><span class="sxs-lookup"><span data-stu-id="00bb9-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-202">Попыток входящих и исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="00bb9-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="00bb9-203">Общее количество попыток входящих и исходящих вызовов мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="00bb9-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-204">Входящие и исходящие вызовы установлены</span><span class="sxs-lookup"><span data-stu-id="00bb9-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="00bb9-205">Общее количество установленных звонков для входящих и исходящих мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="00bb9-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="00bb9-206">**Сведения о вызовах для общего использования приложений**</span><span class="sxs-lookup"><span data-stu-id="00bb9-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00bb9-207"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="00bb9-208"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-209">Активных звонков</span><span class="sxs-lookup"><span data-stu-id="00bb9-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="00bb9-210">Общее количество текущих входящих и исходящих вызовов для общего использования приложений.</span><span class="sxs-lookup"><span data-stu-id="00bb9-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-211">Прерванные звонки</span><span class="sxs-lookup"><span data-stu-id="00bb9-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="00bb9-212">Общее количество входящих и исходящих вызовов для общего использования приложений, которые уже завершены.</span><span class="sxs-lookup"><span data-stu-id="00bb9-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-213">Получено звонков NNN</span><span class="sxs-lookup"><span data-stu-id="00bb9-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="00bb9-214">Общее количество кодов ответов NNN, полученных с сервера.</span><span class="sxs-lookup"><span data-stu-id="00bb9-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-215">Попыток входящих и исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="00bb9-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="00bb9-216">Общее количество попыток входящих и исходящих вызовов для общего использования приложений.</span><span class="sxs-lookup"><span data-stu-id="00bb9-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-217">Входящие и исходящие вызовы установлены</span><span class="sxs-lookup"><span data-stu-id="00bb9-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="00bb9-218">Общее количество установленных звонков входящих и исходящих приложений.</span><span class="sxs-lookup"><span data-stu-id="00bb9-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="00bb9-219">**Информация о звонке Каа**</span><span class="sxs-lookup"><span data-stu-id="00bb9-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00bb9-220"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="00bb9-221"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-222">Активных звонков</span><span class="sxs-lookup"><span data-stu-id="00bb9-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="00bb9-223">Общее количество входящих и исходящих телефонных сетей с открытым коммутируемым подключением (PSTN), в настоящее время используемых вами звонков.</span><span class="sxs-lookup"><span data-stu-id="00bb9-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-224">Прерванные звонки</span><span class="sxs-lookup"><span data-stu-id="00bb9-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="00bb9-225">Общее количество входящих и исходящих вызовов КТСОП, которые уже были прерваны.</span><span class="sxs-lookup"><span data-stu-id="00bb9-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-226">Попыток входящих и исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="00bb9-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="00bb9-227">Общее количество попыток входящих и исходящих звонков по КТСОП.</span><span class="sxs-lookup"><span data-stu-id="00bb9-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-228">Входящие и исходящие вызовы установлены</span><span class="sxs-lookup"><span data-stu-id="00bb9-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="00bb9-229">Общее количество установленных входящих и исходящих звонков по КТСОП.</span><span class="sxs-lookup"><span data-stu-id="00bb9-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="00bb9-230">**Сведения о Конференции**</span><span class="sxs-lookup"><span data-stu-id="00bb9-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00bb9-231"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="00bb9-232"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-233">Активные конференции для обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="00bb9-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="00bb9-234">Общее количество текущих конференций с обменом мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="00bb9-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-235">Активные аудио-и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="00bb9-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="00bb9-236">Общее количество текущих голосовых и видеоконференций (A/V).</span><span class="sxs-lookup"><span data-stu-id="00bb9-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-237">Активные конференции для совместного использования приложений</span><span class="sxs-lookup"><span data-stu-id="00bb9-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="00bb9-238">Общее количество текущих конференций общего обмена приложениями.</span><span class="sxs-lookup"><span data-stu-id="00bb9-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-239">Количество участников</span><span class="sxs-lookup"><span data-stu-id="00bb9-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="00bb9-240">Общее количество участников, которые в настоящее время подключены к конференциям.</span><span class="sxs-lookup"><span data-stu-id="00bb9-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-241">Сбой расписания Конференции</span><span class="sxs-lookup"><span data-stu-id="00bb9-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="00bb9-242">Общее количество сбоев при попытке запланировать конференцию.</span><span class="sxs-lookup"><span data-stu-id="00bb9-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-243">Присоединиться к Конференции с ошибкой</span><span class="sxs-lookup"><span data-stu-id="00bb9-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="00bb9-244">Общее количество сбоев при попытке подключиться к Конференции.</span><span class="sxs-lookup"><span data-stu-id="00bb9-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="00bb9-245">**Счетчики клиента УКВА**</span><span class="sxs-lookup"><span data-stu-id="00bb9-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00bb9-246"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="00bb9-247"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="00bb9-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00bb9-248">Общее количество успешных объединений ИММКУ</span><span class="sxs-lookup"><span data-stu-id="00bb9-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="00bb9-249">Общее количество Объединенных конференций с мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="00bb9-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00bb9-250">Общее количество успешных объединений ДМКУ</span><span class="sxs-lookup"><span data-stu-id="00bb9-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="00bb9-251">Общее количество Объединенных конференций/V.</span><span class="sxs-lookup"><span data-stu-id="00bb9-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

