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
ms.openlocfilehash: c226e3b677965db03ba4d5fcc3c3dadb37192548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="5244b-102">Интерпретация результатов</span><span class="sxs-lookup"><span data-stu-id="5244b-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5244b-103">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="5244b-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="5244b-104">В средстве нагрузки и производительности Lync Server 2013 (Линкперфтул. exe) имеется множество счетчиков, которые можно использовать, чтобы узнать, что делает клиент, а также от того, возникают ли проблемы.</span><span class="sxs-lookup"><span data-stu-id="5244b-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="5244b-105">Счетчики клиентов</span><span class="sxs-lookup"><span data-stu-id="5244b-105">Client Counters</span></span>

<span data-ttu-id="5244b-106">Каждый выполняемый экземпляр Линкперфтул. exe имеет отдельный экземпляр счетчиков.</span><span class="sxs-lookup"><span data-stu-id="5244b-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="5244b-107">Каждый экземпляр именуется ИДЕНТИФИКАТОРом процесса.</span><span class="sxs-lookup"><span data-stu-id="5244b-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="5244b-108">Если клиенты перезагружены, могут возникнуть проблемы.</span><span class="sxs-lookup"><span data-stu-id="5244b-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="5244b-109">Чтобы избежать этих проблем, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5244b-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="5244b-110">Мониторинг ЦП и использования памяти на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="5244b-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="5244b-111">Если ЦП согласованно превышает 90 процентов, уменьшите количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="5244b-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="5244b-112">Если объем памяти велик, можно выполнить проблемы, если файл подкачки недостаточно велик.</span><span class="sxs-lookup"><span data-stu-id="5244b-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="5244b-113">Убедитесь, что зарядка фиксации не достигнута на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5244b-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="5244b-114">Если вы используете пределы памяти, рекомендуем увеличить размер файла подкачки или уменьшить количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="5244b-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="5244b-115">В приведенных ниже таблицах перечислены ключевые счетчики производительности Линкперфтул.</span><span class="sxs-lookup"><span data-stu-id="5244b-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="5244b-116">**Общие сведения**</span><span class="sxs-lookup"><span data-stu-id="5244b-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5244b-117"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5244b-118"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5244b-119">Время, затраченное в минутах</span><span class="sxs-lookup"><span data-stu-id="5244b-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="5244b-120">Время, затраченное с момента запуска процесса.</span><span class="sxs-lookup"><span data-stu-id="5244b-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-121">Активные конечные точки</span><span class="sxs-lookup"><span data-stu-id="5244b-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="5244b-122">Количество конечных точек, подключенных к серверу в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="5244b-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5244b-123">Неудачные входы</span><span class="sxs-lookup"><span data-stu-id="5244b-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="5244b-124">Общее количество неудачных попыток входа в конечную точку.</span><span class="sxs-lookup"><span data-stu-id="5244b-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-125">Попытки входа</span><span class="sxs-lookup"><span data-stu-id="5244b-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="5244b-126">Общее число попыток входа в конечную точку.</span><span class="sxs-lookup"><span data-stu-id="5244b-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5244b-127">Конечные точки отключены</span><span class="sxs-lookup"><span data-stu-id="5244b-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="5244b-128">Общее число отключенных конечных точек.</span><span class="sxs-lookup"><span data-stu-id="5244b-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5244b-129">**Сведения о присутствии**</span><span class="sxs-lookup"><span data-stu-id="5244b-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5244b-130"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5244b-131"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5244b-132">Вызовы Сетпресенце</span><span class="sxs-lookup"><span data-stu-id="5244b-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="5244b-133">Общее число попыток изменения сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="5244b-133">Total number of presence change attempts.</span></span> <span data-ttu-id="5244b-134">В разделе Сетпресенце (тип присутствия) вызываются счетчики производительности для различных типов изменений присутствия.</span><span class="sxs-lookup"><span data-stu-id="5244b-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-135">NNN ответов для Сетпресенце</span><span class="sxs-lookup"><span data-stu-id="5244b-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="5244b-136">Общее количество кодов ответов NNN, полученных с сервера.</span><span class="sxs-lookup"><span data-stu-id="5244b-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5244b-137">Звонки на присутствие</span><span class="sxs-lookup"><span data-stu-id="5244b-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="5244b-138">Общее число попыток получения запроса на присутствие.</span><span class="sxs-lookup"><span data-stu-id="5244b-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-139">NNN ответов для функции Presence</span><span class="sxs-lookup"><span data-stu-id="5244b-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="5244b-140">Общее количество кодов ответов NNN, полученных с сервера.</span><span class="sxs-lookup"><span data-stu-id="5244b-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5244b-141">**Сведения о службе адресной книги**</span><span class="sxs-lookup"><span data-stu-id="5244b-141">**Address Book service Information**</span></span>

<span data-ttu-id="5244b-142">Эта категория включает счетчики, используемые для мониторинга файлов и веб-запросов веб-запросов на файлы службы адресной книги (ABS).</span><span class="sxs-lookup"><span data-stu-id="5244b-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5244b-143"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5244b-144"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5244b-145">Попытка скачивания файлов с полным и разностным индексом ABS</span><span class="sxs-lookup"><span data-stu-id="5244b-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="5244b-146">Общее число попыток полных или разностных запросов на скачивание файлов.</span><span class="sxs-lookup"><span data-stu-id="5244b-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-147">Успешное скачивание полных/разностных файлов ABS</span><span class="sxs-lookup"><span data-stu-id="5244b-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="5244b-148">Общее число попыток полных или разностных запросов на скачивание файлов.</span><span class="sxs-lookup"><span data-stu-id="5244b-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5244b-149">Счетчики, связанные со службой веб-запросов адресной книги</span><span class="sxs-lookup"><span data-stu-id="5244b-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="5244b-150">Счетчики, связанные с скачиванием файла адресной книги.</span><span class="sxs-lookup"><span data-stu-id="5244b-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-151">Попытки вызовов ABS WS</span><span class="sxs-lookup"><span data-stu-id="5244b-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="5244b-152">Общее число попыток запросов к службе веб-запросов в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="5244b-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5244b-153">Успешные вызовы ABS WS</span><span class="sxs-lookup"><span data-stu-id="5244b-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="5244b-154">Общее количество запросов службы веб-запросов к адресной книге, которые возвращали успешный код ответа.</span><span class="sxs-lookup"><span data-stu-id="5244b-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-155">Неудачных вызовов ABS WS</span><span class="sxs-lookup"><span data-stu-id="5244b-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="5244b-156">Общее количество запросов службы веб-запросов к адресной книге, которые возвращали код ответа об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5244b-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5244b-157">**Сведения о списке рассылки (DL)**</span><span class="sxs-lookup"><span data-stu-id="5244b-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5244b-158"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5244b-159"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5244b-160">Попытки вызовов</span><span class="sxs-lookup"><span data-stu-id="5244b-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5244b-161">Общее число попыток запроса веб-службы расширения списка рассылки (ДЛКС).</span><span class="sxs-lookup"><span data-stu-id="5244b-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-162">Успешные вызовы</span><span class="sxs-lookup"><span data-stu-id="5244b-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="5244b-163">Общее количество запросов веб-службы ДЛКС, которые возвращали успешный код ответа.</span><span class="sxs-lookup"><span data-stu-id="5244b-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5244b-164">Неудачных вызовов</span><span class="sxs-lookup"><span data-stu-id="5244b-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="5244b-165">Общее количество запросов веб-службы ДЛКС, которые возвращали код ответа на сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5244b-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5244b-166">**Основные сведения о VoIP**</span><span class="sxs-lookup"><span data-stu-id="5244b-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="5244b-167">Счетчики производительности, перечисленные ниже, приведены в разделе номера отчетов для всех звонков по протоколу VoIP, в том числе звонки на сервер-посредник, сервер аудио-и видеоконференций, пограничный сервер, приложение группы ответа и автосекретарь конференций, если эти сценарии включены.</span><span class="sxs-lookup"><span data-stu-id="5244b-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5244b-168"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5244b-169"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5244b-170">Активные вызовы</span><span class="sxs-lookup"><span data-stu-id="5244b-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="5244b-171">Общее количество текущих входящих и исходящих вызовов голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="5244b-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-172">Завершенные вызовы</span><span class="sxs-lookup"><span data-stu-id="5244b-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="5244b-173">Общее количество входящих и исходящих вызовов голосовых вызовов, которые уже были завершены.</span><span class="sxs-lookup"><span data-stu-id="5244b-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5244b-174">Отклоненные вызовы</span><span class="sxs-lookup"><span data-stu-id="5244b-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="5244b-175">Общее количество отклоненных входящих голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="5244b-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-176">Попыток входящих и исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="5244b-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5244b-177">Общее число попыток входящих и исходящих голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="5244b-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5244b-178">Входящие/исходящие вызовы установлены</span><span class="sxs-lookup"><span data-stu-id="5244b-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="5244b-179">Общее количество установленных входящих и исходящих голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="5244b-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-180">Получено звонков NNN</span><span class="sxs-lookup"><span data-stu-id="5244b-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="5244b-181">Общее количество кодов ответов NNN, полученных с сервера.</span><span class="sxs-lookup"><span data-stu-id="5244b-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5244b-182">Частота прохода VoIP (%)</span><span class="sxs-lookup"><span data-stu-id="5244b-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="5244b-183">Общее количество выполненных вызовов, которые попытались выполнить.</span><span class="sxs-lookup"><span data-stu-id="5244b-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5244b-184">**Сведения о вызове службы группы ответа**</span><span class="sxs-lookup"><span data-stu-id="5244b-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5244b-185"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5244b-186"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5244b-187">Активные вызовы</span><span class="sxs-lookup"><span data-stu-id="5244b-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="5244b-188">Общее количество активных вызовов приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="5244b-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-189">Попытки вызовов</span><span class="sxs-lookup"><span data-stu-id="5244b-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5244b-190">Общее число попыток вызовов.</span><span class="sxs-lookup"><span data-stu-id="5244b-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5244b-191">**Сведения о вызовах для обмена мгновенными сообщениями**</span><span class="sxs-lookup"><span data-stu-id="5244b-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5244b-192"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5244b-193"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5244b-194">Активные вызовы</span><span class="sxs-lookup"><span data-stu-id="5244b-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="5244b-195">Общее количество текущих входящих и исходящих вызовов обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="5244b-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-196">Завершенные вызовы</span><span class="sxs-lookup"><span data-stu-id="5244b-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="5244b-197">Общее количество уже завершенных звонков для входящих и исходящих мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="5244b-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5244b-198">Получено звонков NNN</span><span class="sxs-lookup"><span data-stu-id="5244b-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="5244b-199">Общее количество кодов ответов NNN, полученных с сервера.</span><span class="sxs-lookup"><span data-stu-id="5244b-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-200">Получено/Отправлено сообщений обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="5244b-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="5244b-201">Общее количество сообщений, полученных или отправленных для всех сеансов.</span><span class="sxs-lookup"><span data-stu-id="5244b-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5244b-202">Попыток входящих и исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="5244b-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5244b-203">Общее число попыток входящих и исходящих вызовов обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="5244b-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-204">Входящие/исходящие вызовы установлены</span><span class="sxs-lookup"><span data-stu-id="5244b-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="5244b-205">Общее количество установленных входящих и исходящих вызовов мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="5244b-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5244b-206">**Сведения о вызовах общего доступа к приложениям**</span><span class="sxs-lookup"><span data-stu-id="5244b-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5244b-207"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5244b-208"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5244b-209">Активные вызовы</span><span class="sxs-lookup"><span data-stu-id="5244b-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="5244b-210">Общее количество текущих входящих и исходящих вызовов общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="5244b-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-211">Завершенные вызовы</span><span class="sxs-lookup"><span data-stu-id="5244b-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="5244b-212">Общее количество входящих и исходящих вызовов общего доступа к приложениям, которые уже завершены.</span><span class="sxs-lookup"><span data-stu-id="5244b-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5244b-213">Получено звонков NNN</span><span class="sxs-lookup"><span data-stu-id="5244b-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="5244b-214">Общее количество кодов ответов NNN, полученных с сервера.</span><span class="sxs-lookup"><span data-stu-id="5244b-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-215">Попыток входящих и исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="5244b-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5244b-216">Общее число попыток входящих и исходящих вызовов общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="5244b-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5244b-217">Входящие/исходящие вызовы установлены</span><span class="sxs-lookup"><span data-stu-id="5244b-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="5244b-218">Общее количество установленных вызовов общего доступа для входящих и исходящих приложений.</span><span class="sxs-lookup"><span data-stu-id="5244b-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5244b-219">**Сведения о вызове CAA**</span><span class="sxs-lookup"><span data-stu-id="5244b-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5244b-220"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5244b-221"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5244b-222">Активные вызовы</span><span class="sxs-lookup"><span data-stu-id="5244b-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="5244b-223">Общее количество текущих звонков входящих и исходящих звонков по телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="5244b-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-224">Завершенные вызовы</span><span class="sxs-lookup"><span data-stu-id="5244b-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="5244b-225">Общее количество входящих и исходящих вызовов PSTN, которые уже были завершены.</span><span class="sxs-lookup"><span data-stu-id="5244b-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5244b-226">Попыток входящих и исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="5244b-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5244b-227">Общее число попыток входящих и исходящих звонков PSTN.</span><span class="sxs-lookup"><span data-stu-id="5244b-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-228">Входящие/исходящие вызовы установлены</span><span class="sxs-lookup"><span data-stu-id="5244b-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="5244b-229">Общее количество установленных входящих и исходящих звонков PSTN.</span><span class="sxs-lookup"><span data-stu-id="5244b-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5244b-230">**Сведения о Конференции**</span><span class="sxs-lookup"><span data-stu-id="5244b-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5244b-231"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5244b-232"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5244b-233">Активные конференции для обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="5244b-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="5244b-234">Общее количество текущих конференций обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="5244b-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-235">Активные аудио-и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="5244b-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="5244b-236">Общее количество текущих конференций аудио-и видеосвязи (A/V).</span><span class="sxs-lookup"><span data-stu-id="5244b-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5244b-237">Активные конференции общего доступа к приложениям</span><span class="sxs-lookup"><span data-stu-id="5244b-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="5244b-238">Общее количество текущих конференций общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="5244b-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-239">Количество участников</span><span class="sxs-lookup"><span data-stu-id="5244b-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="5244b-240">Общее количество участников, которые в настоящее время подключены к конференциям.</span><span class="sxs-lookup"><span data-stu-id="5244b-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5244b-241">Сбой расписания Конференции</span><span class="sxs-lookup"><span data-stu-id="5244b-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="5244b-242">Общее количество неудачных попыток планирования конференции.</span><span class="sxs-lookup"><span data-stu-id="5244b-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-243">Сбой присоединения к Конференции</span><span class="sxs-lookup"><span data-stu-id="5244b-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="5244b-244">Общее количество сбоев при попытке подключения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="5244b-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5244b-245">**Счетчики клиента UCWA**</span><span class="sxs-lookup"><span data-stu-id="5244b-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5244b-246"><strong>Счетчик производительности</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5244b-247"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="5244b-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5244b-248">Общее число успешно выполненных объединений ИММКУ</span><span class="sxs-lookup"><span data-stu-id="5244b-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="5244b-249">Общее количество подключенных конференций с обменом мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="5244b-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5244b-250">Общее число успешно выполненных объединений ДМКУ</span><span class="sxs-lookup"><span data-stu-id="5244b-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="5244b-251">Общее число объединений аудио-и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="5244b-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

