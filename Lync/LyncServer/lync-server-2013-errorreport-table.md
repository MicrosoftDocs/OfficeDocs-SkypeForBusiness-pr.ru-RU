---
title: 'Lync Server 2013: таблица ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f9377b70923c1dc2c7213e9ac72486daffcda99
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="d8a6f-102">Таблица ErrorReport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8a6f-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8a6f-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d8a6f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d8a6f-104">В таблице ErrorReport хранятся сведения о возникших ошибках.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="d8a6f-105">Каждая запись соответствует одному случаю возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-105">Each record is one error occurrence.</span></span> <span data-ttu-id="d8a6f-106">Ошибки фиксируются агентом CDR, работающим на сервере переднего плана, или передаются клиентом.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8a6f-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="d8a6f-107">Column</span></span></th>
<th><span data-ttu-id="d8a6f-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="d8a6f-108">Data Type</span></span></th>
<th><span data-ttu-id="d8a6f-109">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="d8a6f-109">Key/Index</span></span></th>
<th><span data-ttu-id="d8a6f-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="d8a6f-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8a6f-111"><strong>Поля errortime</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d8a6f-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d8a6f-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-114">Дата и время возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8a6f-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-116">int</span><span class="sxs-lookup"><span data-stu-id="d8a6f-116">int</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-117">Primary</span><span class="sxs-lookup"><span data-stu-id="d8a6f-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-118">ИДЕНТИФИКАЦИОНный номер, идентифицирующий отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-118">ID number to identify the error report.</span></span> <span data-ttu-id="d8a6f-119">Используется совместно с <strong>поля errortime</strong> для уникальной идентификации отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8a6f-120"><strong>еррорид</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-121">int</span><span class="sxs-lookup"><span data-stu-id="d8a6f-121">int</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-122">Правительства</span><span class="sxs-lookup"><span data-stu-id="d8a6f-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-123">Уникальный идентификатор типа ошибки.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-123">Unique ID of the error type.</span></span> <span data-ttu-id="d8a6f-124">Дополнительные сведения см. <a href="lync-server-2013-errordef-table.md">в таблице таблица errordef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d8a6f-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8a6f-125"><strong>фромусерид</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-126">int</span><span class="sxs-lookup"><span data-stu-id="d8a6f-126">int</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-127">Правительства</span><span class="sxs-lookup"><span data-stu-id="d8a6f-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-128">Пользователь, создавший запрос, вызвавший ошибку.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="d8a6f-129">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d8a6f-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8a6f-130"><strong>таусерид</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-131">int</span><span class="sxs-lookup"><span data-stu-id="d8a6f-131">int</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-132">Правительства</span><span class="sxs-lookup"><span data-stu-id="d8a6f-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-133">Конечный пользователь для запроса, вызвавшего ошибку.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="d8a6f-134">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d8a6f-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8a6f-135"><strong>конференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-136">int</span><span class="sxs-lookup"><span data-stu-id="d8a6f-136">int</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-137">Правительства</span><span class="sxs-lookup"><span data-stu-id="d8a6f-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-138">Универсальный код ресурса (URI) Конференции, связанный с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-138">Conference URI related to the error.</span></span> <span data-ttu-id="d8a6f-139">Дополнительные сведения см. <a href="lync-server-2013-conferenceuris-table.md">в таблице таблица conferenceuris в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d8a6f-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="d8a6f-140">Как правило, если Конференцеуриид не имеет значение null, то либо Фромусерид, либо Таусерид будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8a6f-141"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-142">datetime</span><span class="sxs-lookup"><span data-stu-id="d8a6f-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-143">Правительства</span><span class="sxs-lookup"><span data-stu-id="d8a6f-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-144">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d8a6f-145">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d8a6f-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8a6f-146"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-147">int</span><span class="sxs-lookup"><span data-stu-id="d8a6f-147">int</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-148">Правительства</span><span class="sxs-lookup"><span data-stu-id="d8a6f-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-149">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-149">ID number to identify the session.</span></span> <span data-ttu-id="d8a6f-150">В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d8a6f-151">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d8a6f-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8a6f-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-153">int</span><span class="sxs-lookup"><span data-stu-id="d8a6f-153">int</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-154">Правительства</span><span class="sxs-lookup"><span data-stu-id="d8a6f-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-155">Сервер, который отправил отчет об ошибках (при отправке отчета с серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="d8a6f-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="d8a6f-156">Дополнительные сведения см. <a href="lync-server-2013-servers-table.md">в таблице Servers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d8a6f-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="d8a6f-157">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8a6f-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-159">int</span><span class="sxs-lookup"><span data-stu-id="d8a6f-159">int</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-160">Правительства</span><span class="sxs-lookup"><span data-stu-id="d8a6f-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-161">Сервер, который отправил отчет об ошибках (при отправке отчета с серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="d8a6f-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="d8a6f-162">Дополнительные сведения приведены <a href="lync-server-2013-application-table.md">в таблице Application (приложение) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d8a6f-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="d8a6f-163">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8a6f-164"><strong>мсдиагхеадер</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-165">изображение</span><span class="sxs-lookup"><span data-stu-id="d8a6f-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d8a6f-166">Дополнительные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-166">More information about the error.</span></span></p>
<p><span data-ttu-id="d8a6f-167">Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d8a6f-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8a6f-168"><strong>клиентверсионид</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-169">int</span><span class="sxs-lookup"><span data-stu-id="d8a6f-169">int</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-170">Правительства</span><span class="sxs-lookup"><span data-stu-id="d8a6f-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-171">Клиентская версия конечной точки, которая отправляет отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="d8a6f-172">Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d8a6f-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8a6f-173"><strong>искаптуредбисервер</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-174">Битовая</span><span class="sxs-lookup"><span data-stu-id="d8a6f-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d8a6f-175">— Это отчет об ошибках, записанный агентом CDR, запущенным на сервере переднего плана или отправленным клиентом.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8a6f-176"><strong>Флаг</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-177">smallint</span><span class="sxs-lookup"><span data-stu-id="d8a6f-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d8a6f-178">Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8a6f-179"><strong>телеметрид</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-180">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="d8a6f-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d8a6f-181">Уникальный идентификатор времени присоединения для различных компонентов, участвующих в конференции.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="d8a6f-182">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8a6f-183"><strong>сессионсетуптиме</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-184">int</span><span class="sxs-lookup"><span data-stu-id="d8a6f-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d8a6f-185">Время (в миллисекундах), необходимое для присоединения к конференции определенного компонента.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="d8a6f-186">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8a6f-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-188">int</span><span class="sxs-lookup"><span data-stu-id="d8a6f-188">int</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-189">Правительства</span><span class="sxs-lookup"><span data-stu-id="d8a6f-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-190">Представляет полное доменное имя сервера, который создал отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8a6f-191"><strong>пулид</strong></span><span class="sxs-lookup"><span data-stu-id="d8a6f-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="d8a6f-192">int</span><span class="sxs-lookup"><span data-stu-id="d8a6f-192">int</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-193">Правительства</span><span class="sxs-lookup"><span data-stu-id="d8a6f-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8a6f-194">Представляет полное доменное имя пула, в котором был создан отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="d8a6f-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

