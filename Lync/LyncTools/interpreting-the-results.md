---
title: Интерпретация результатов
description: Интерпретация результатов.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8342a1ec1e15e42852fc5293f87342e98587a60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565345"
---
# <a name="interpreting-the-results"></a><span data-ttu-id="16d1d-103">Интерпретация результатов</span><span class="sxs-lookup"><span data-stu-id="16d1d-103">Interpreting the Results</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16d1d-104">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="16d1d-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="16d1d-105">Средство нагрузочного тестирования и производительности Lync Server 2013 (LyncPerfTool.exe) имеет множество счетчиков, которые можно использовать, чтобы узнать, что делает клиент, и возникают ли они.</span><span class="sxs-lookup"><span data-stu-id="16d1d-105">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="16d1d-106">Счетчики клиентов</span><span class="sxs-lookup"><span data-stu-id="16d1d-106">Client Counters</span></span>

<span data-ttu-id="16d1d-107">Каждый выполняемый экземпляр LyncPerfTool.exe имеет отдельный экземпляр счетчиков.</span><span class="sxs-lookup"><span data-stu-id="16d1d-107">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="16d1d-108">Каждый экземпляр именуется ИДЕНТИФИКАТОРом процесса.</span><span class="sxs-lookup"><span data-stu-id="16d1d-108">Each instance is named by its process ID.</span></span>

<span data-ttu-id="16d1d-109">Если клиенты перезагружены, могут возникнуть проблемы.</span><span class="sxs-lookup"><span data-stu-id="16d1d-109">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="16d1d-110">Чтобы избежать этих проблем, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="16d1d-110">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="16d1d-111">Мониторинг ЦП и использования памяти на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="16d1d-111">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="16d1d-112">Если ЦП согласованно превышает 90 процентов, уменьшите количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="16d1d-112">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="16d1d-113">Если объем памяти велик, можно выполнить проблемы, если файл подкачки недостаточно велик.</span><span class="sxs-lookup"><span data-stu-id="16d1d-113">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="16d1d-114">Убедитесь, что зарядка фиксации не достигнута на компьютере.</span><span class="sxs-lookup"><span data-stu-id="16d1d-114">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="16d1d-115">Если вы используете пределы памяти, рекомендуем увеличить размер файла подкачки или уменьшить количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="16d1d-115">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="16d1d-116">В приведенных ниже таблицах перечислены ключевые счетчики производительности Линкперфтул.</span><span class="sxs-lookup"><span data-stu-id="16d1d-116">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="16d1d-117">**Общие сведения**</span><span class="sxs-lookup"><span data-stu-id="16d1d-117">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16d1d-118"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-118"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="16d1d-119"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-119"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-120">Время, затраченное в минутах</span><span class="sxs-lookup"><span data-stu-id="16d1d-120">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="16d1d-121">Время, затраченное с момента запуска процесса.</span><span class="sxs-lookup"><span data-stu-id="16d1d-121">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-122">Активные конечные точки</span><span class="sxs-lookup"><span data-stu-id="16d1d-122">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="16d1d-123">Количество конечных точек, подключенных к серверу в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="16d1d-123">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-124">Неудачные входы</span><span class="sxs-lookup"><span data-stu-id="16d1d-124">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="16d1d-125">Общее количество неудачных попыток входа в конечную точку.</span><span class="sxs-lookup"><span data-stu-id="16d1d-125">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-126">Попытки входа</span><span class="sxs-lookup"><span data-stu-id="16d1d-126">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="16d1d-127">Общее число попыток входа в конечную точку.</span><span class="sxs-lookup"><span data-stu-id="16d1d-127">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-128">Конечные точки отключены</span><span class="sxs-lookup"><span data-stu-id="16d1d-128">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="16d1d-129">Общее число отключенных конечных точек.</span><span class="sxs-lookup"><span data-stu-id="16d1d-129">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="16d1d-130">**Сведения о присутствии**</span><span class="sxs-lookup"><span data-stu-id="16d1d-130">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16d1d-131"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-131"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="16d1d-132"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-132"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-133">Вызовы Сетпресенце</span><span class="sxs-lookup"><span data-stu-id="16d1d-133">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="16d1d-134">Общее число попыток изменения сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="16d1d-134">Total number of presence change attempts.</span></span> <span data-ttu-id="16d1d-135">В разделе Сетпресенце (тип присутствия) вызываются счетчики производительности для различных типов изменений присутствия.</span><span class="sxs-lookup"><span data-stu-id="16d1d-135">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-136">NNN ответов для Сетпресенце</span><span class="sxs-lookup"><span data-stu-id="16d1d-136">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="16d1d-137">Общее количество кодов ответов NNN, полученных с сервера.</span><span class="sxs-lookup"><span data-stu-id="16d1d-137">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-138">Звонки на присутствие</span><span class="sxs-lookup"><span data-stu-id="16d1d-138">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="16d1d-139">Общее число попыток получения запроса на присутствие.</span><span class="sxs-lookup"><span data-stu-id="16d1d-139">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-140">NNN ответов для функции Presence</span><span class="sxs-lookup"><span data-stu-id="16d1d-140">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="16d1d-141">Общее количество кодов ответов NNN, полученных с сервера.</span><span class="sxs-lookup"><span data-stu-id="16d1d-141">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="16d1d-142">**Сведения о службе адресной книги**</span><span class="sxs-lookup"><span data-stu-id="16d1d-142">**Address Book service Information**</span></span>

<span data-ttu-id="16d1d-143">Эта категория включает счетчики, используемые для мониторинга файлов и веб-запросов веб-запросов на файлы службы адресной книги (ABS).</span><span class="sxs-lookup"><span data-stu-id="16d1d-143">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16d1d-144"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-144"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="16d1d-145"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-145"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-146">Попытка скачивания файлов с полным и разностным индексом ABS</span><span class="sxs-lookup"><span data-stu-id="16d1d-146">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="16d1d-147">Общее число попыток полных или разностных запросов на скачивание файлов.</span><span class="sxs-lookup"><span data-stu-id="16d1d-147">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-148">Успешное скачивание полных/разностных файлов ABS</span><span class="sxs-lookup"><span data-stu-id="16d1d-148">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="16d1d-149">Общее число попыток полных или разностных запросов на скачивание файлов.</span><span class="sxs-lookup"><span data-stu-id="16d1d-149">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-150">Счетчики, связанные со службой веб-запросов адресной книги</span><span class="sxs-lookup"><span data-stu-id="16d1d-150">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="16d1d-151">Счетчики, связанные с скачиванием файла адресной книги.</span><span class="sxs-lookup"><span data-stu-id="16d1d-151">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-152">Попытки вызовов ABS WS</span><span class="sxs-lookup"><span data-stu-id="16d1d-152">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="16d1d-153">Общее число попыток запросов к службе веб-запросов в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="16d1d-153">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-154">Успешные вызовы ABS WS</span><span class="sxs-lookup"><span data-stu-id="16d1d-154">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="16d1d-155">Общее количество запросов службы веб-запросов к адресной книге, которые возвращали успешный код ответа.</span><span class="sxs-lookup"><span data-stu-id="16d1d-155">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-156">Неудачных вызовов ABS WS</span><span class="sxs-lookup"><span data-stu-id="16d1d-156">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="16d1d-157">Общее количество запросов службы веб-запросов к адресной книге, которые возвращали код ответа об ошибке.</span><span class="sxs-lookup"><span data-stu-id="16d1d-157">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="16d1d-158">**Сведения о списке рассылки (DL)**</span><span class="sxs-lookup"><span data-stu-id="16d1d-158">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16d1d-159"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-159"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="16d1d-160"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-160"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-161">Попытки вызовов</span><span class="sxs-lookup"><span data-stu-id="16d1d-161">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="16d1d-162">Общее число попыток запроса веб-службы расширения списка рассылки (ДЛКС).</span><span class="sxs-lookup"><span data-stu-id="16d1d-162">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-163">Успешные вызовы</span><span class="sxs-lookup"><span data-stu-id="16d1d-163">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="16d1d-164">Общее количество запросов веб-службы ДЛКС, которые возвращали успешный код ответа.</span><span class="sxs-lookup"><span data-stu-id="16d1d-164">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-165">Неудачных вызовов</span><span class="sxs-lookup"><span data-stu-id="16d1d-165">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="16d1d-166">Общее количество запросов веб-службы ДЛКС, которые возвращали код ответа на сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="16d1d-166">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="16d1d-167">**Основные сведения о VoIP**</span><span class="sxs-lookup"><span data-stu-id="16d1d-167">**VoIP Basic Information**</span></span>

<span data-ttu-id="16d1d-168">Счетчики производительности, перечисленные ниже, приведены в разделе номера отчетов для всех звонков по протоколу VoIP, в том числе звонки на сервер-посредник, сервер аудио-и видеоконференций, пограничный сервер, приложение группы ответа и автосекретарь конференций, если эти сценарии включены.</span><span class="sxs-lookup"><span data-stu-id="16d1d-168">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16d1d-169"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-169"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="16d1d-170"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-170"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-171">Активные вызовы</span><span class="sxs-lookup"><span data-stu-id="16d1d-171">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="16d1d-172">Общее количество текущих входящих и исходящих вызовов голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="16d1d-172">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-173">Завершенные вызовы</span><span class="sxs-lookup"><span data-stu-id="16d1d-173">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="16d1d-174">Общее количество входящих и исходящих вызовов голосовых вызовов, которые уже были завершены.</span><span class="sxs-lookup"><span data-stu-id="16d1d-174">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-175">Отклоненные вызовы</span><span class="sxs-lookup"><span data-stu-id="16d1d-175">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="16d1d-176">Общее количество отклоненных входящих голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="16d1d-176">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-177">Попыток входящих и исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="16d1d-177">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="16d1d-178">Общее число попыток входящих и исходящих голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="16d1d-178">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-179">Входящие/исходящие вызовы установлены</span><span class="sxs-lookup"><span data-stu-id="16d1d-179">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="16d1d-180">Общее количество установленных входящих и исходящих голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="16d1d-180">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-181">Получено звонков NNN</span><span class="sxs-lookup"><span data-stu-id="16d1d-181">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="16d1d-182">Общее количество кодов ответов NNN, полученных с сервера.</span><span class="sxs-lookup"><span data-stu-id="16d1d-182">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-183">Частота прохода VoIP (%)</span><span class="sxs-lookup"><span data-stu-id="16d1d-183">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="16d1d-184">Общее количество выполненных вызовов, которые попытались выполнить.</span><span class="sxs-lookup"><span data-stu-id="16d1d-184">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="16d1d-185">**Сведения о вызове службы группы ответа**</span><span class="sxs-lookup"><span data-stu-id="16d1d-185">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16d1d-186"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-186"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="16d1d-187"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-187"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-188">Активные вызовы</span><span class="sxs-lookup"><span data-stu-id="16d1d-188">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="16d1d-189">Общее количество активных вызовов приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="16d1d-189">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-190">Попытки вызовов</span><span class="sxs-lookup"><span data-stu-id="16d1d-190">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="16d1d-191">Общее число попыток вызовов.</span><span class="sxs-lookup"><span data-stu-id="16d1d-191">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="16d1d-192">**Сведения о вызовах для обмена мгновенными сообщениями**</span><span class="sxs-lookup"><span data-stu-id="16d1d-192">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16d1d-193"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-193"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="16d1d-194"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-194"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-195">Активные вызовы</span><span class="sxs-lookup"><span data-stu-id="16d1d-195">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="16d1d-196">Общее количество текущих входящих и исходящих вызовов обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="16d1d-196">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-197">Завершенные вызовы</span><span class="sxs-lookup"><span data-stu-id="16d1d-197">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="16d1d-198">Общее количество уже завершенных звонков для входящих и исходящих мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="16d1d-198">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-199">Получено звонков NNN</span><span class="sxs-lookup"><span data-stu-id="16d1d-199">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="16d1d-200">Общее количество кодов ответов NNN, полученных с сервера.</span><span class="sxs-lookup"><span data-stu-id="16d1d-200">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-201">Получено/Отправлено сообщений обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="16d1d-201">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="16d1d-202">Общее количество сообщений, полученных или отправленных для всех сеансов.</span><span class="sxs-lookup"><span data-stu-id="16d1d-202">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-203">Попыток входящих и исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="16d1d-203">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="16d1d-204">Общее число попыток входящих и исходящих вызовов обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="16d1d-204">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-205">Входящие/исходящие вызовы установлены</span><span class="sxs-lookup"><span data-stu-id="16d1d-205">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="16d1d-206">Общее количество установленных входящих и исходящих вызовов мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="16d1d-206">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="16d1d-207">**Сведения о вызовах общего доступа к приложениям**</span><span class="sxs-lookup"><span data-stu-id="16d1d-207">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16d1d-208"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-208"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="16d1d-209"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-209"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-210">Активные вызовы</span><span class="sxs-lookup"><span data-stu-id="16d1d-210">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="16d1d-211">Общее количество текущих входящих и исходящих вызовов общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="16d1d-211">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-212">Завершенные вызовы</span><span class="sxs-lookup"><span data-stu-id="16d1d-212">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="16d1d-213">Общее количество входящих и исходящих вызовов общего доступа к приложениям, которые уже завершены.</span><span class="sxs-lookup"><span data-stu-id="16d1d-213">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-214">Получено звонков NNN</span><span class="sxs-lookup"><span data-stu-id="16d1d-214">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="16d1d-215">Общее количество кодов ответов NNN, полученных с сервера.</span><span class="sxs-lookup"><span data-stu-id="16d1d-215">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-216">Попыток входящих и исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="16d1d-216">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="16d1d-217">Общее число попыток входящих и исходящих вызовов общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="16d1d-217">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-218">Входящие/исходящие вызовы установлены</span><span class="sxs-lookup"><span data-stu-id="16d1d-218">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="16d1d-219">Общее количество установленных вызовов общего доступа для входящих и исходящих приложений.</span><span class="sxs-lookup"><span data-stu-id="16d1d-219">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="16d1d-220">**Сведения о вызове CAA**</span><span class="sxs-lookup"><span data-stu-id="16d1d-220">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16d1d-221"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-221"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="16d1d-222"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-222"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-223">Активные вызовы</span><span class="sxs-lookup"><span data-stu-id="16d1d-223">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="16d1d-224">Общее количество текущих звонков входящих и исходящих звонков по телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="16d1d-224">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-225">Завершенные вызовы</span><span class="sxs-lookup"><span data-stu-id="16d1d-225">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="16d1d-226">Общее количество входящих и исходящих вызовов PSTN, которые уже были завершены.</span><span class="sxs-lookup"><span data-stu-id="16d1d-226">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-227">Попыток входящих и исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="16d1d-227">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="16d1d-228">Общее число попыток входящих и исходящих звонков PSTN.</span><span class="sxs-lookup"><span data-stu-id="16d1d-228">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-229">Входящие/исходящие вызовы установлены</span><span class="sxs-lookup"><span data-stu-id="16d1d-229">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="16d1d-230">Общее количество установленных входящих и исходящих звонков PSTN.</span><span class="sxs-lookup"><span data-stu-id="16d1d-230">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="16d1d-231">**Сведения о Конференции**</span><span class="sxs-lookup"><span data-stu-id="16d1d-231">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16d1d-232"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-232"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="16d1d-233"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-233"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-234">Активные конференции для обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="16d1d-234">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="16d1d-235">Общее количество текущих конференций обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="16d1d-235">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-236">Активные аудио-и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="16d1d-236">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="16d1d-237">Общее количество текущих конференций аудио-и видеосвязи (A/V).</span><span class="sxs-lookup"><span data-stu-id="16d1d-237">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-238">Активные конференции общего доступа к приложениям</span><span class="sxs-lookup"><span data-stu-id="16d1d-238">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="16d1d-239">Общее количество текущих конференций общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="16d1d-239">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-240">Количество участников</span><span class="sxs-lookup"><span data-stu-id="16d1d-240">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="16d1d-241">Общее количество участников, которые в настоящее время подключены к конференциям.</span><span class="sxs-lookup"><span data-stu-id="16d1d-241">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-242">Сбой расписания Конференции</span><span class="sxs-lookup"><span data-stu-id="16d1d-242">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="16d1d-243">Общее количество неудачных попыток планирования конференции.</span><span class="sxs-lookup"><span data-stu-id="16d1d-243">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-244">Сбой присоединения к Конференции</span><span class="sxs-lookup"><span data-stu-id="16d1d-244">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="16d1d-245">Общее количество сбоев при попытке подключения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="16d1d-245">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="16d1d-246">**Счетчики клиента UCWA**</span><span class="sxs-lookup"><span data-stu-id="16d1d-246">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16d1d-247"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-247"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="16d1d-248"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="16d1d-248"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16d1d-249">Общее число успешно выполненных объединений ИММКУ</span><span class="sxs-lookup"><span data-stu-id="16d1d-249">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="16d1d-250">Общее количество подключенных конференций с обменом мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="16d1d-250">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16d1d-251">Общее число успешно выполненных объединений ДМКУ</span><span class="sxs-lookup"><span data-stu-id="16d1d-251">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="16d1d-252">Общее число объединений аудио-и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="16d1d-252">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

