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
ms.openlocfilehash: 321a975e9461e39de882d9620cdded9d2554e8ed
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533146"
---
# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="a2b2b-102">Таблица ErrorReport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2b2b-102">ErrorReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2b2b-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a2b2b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a2b2b-104">В таблице ErrorReport хранятся сведения о возникших ошибках.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="a2b2b-105">Каждая запись соответствует одному случаю возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-105">Each record is one error occurrence.</span></span> <span data-ttu-id="a2b2b-106">Ошибки фиксируются агентом CDR, работающим на сервере переднего плана, или передаются клиентом.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2b2b-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="a2b2b-107">Column</span></span></th>
<th><span data-ttu-id="a2b2b-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="a2b2b-108">Data Type</span></span></th>
<th><span data-ttu-id="a2b2b-109">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="a2b2b-109">Key/Index</span></span></th>
<th><span data-ttu-id="a2b2b-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="a2b2b-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2b2b-111"><strong>Поля errortime</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-112">datetime</span><span class="sxs-lookup"><span data-stu-id="a2b2b-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a2b2b-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-114">Дата и время возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b2b-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-116">int</span><span class="sxs-lookup"><span data-stu-id="a2b2b-116">int</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-117">Primary</span><span class="sxs-lookup"><span data-stu-id="a2b2b-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-118">ИДЕНТИФИКАЦИОНный номер, идентифицирующий отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-118">ID number to identify the error report.</span></span> <span data-ttu-id="a2b2b-119">Используется совместно с <strong>поля errortime</strong> для уникальной идентификации отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b2b-120"><strong>еррорид</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-121">int</span><span class="sxs-lookup"><span data-stu-id="a2b2b-121">int</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-122">Правительства</span><span class="sxs-lookup"><span data-stu-id="a2b2b-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-123">Уникальный идентификатор типа ошибки.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-123">Unique ID of the error type.</span></span> <span data-ttu-id="a2b2b-124">Дополнительные сведения см. <a href="lync-server-2013-errordef-table.md">в таблице таблица errordef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2b2b-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b2b-125"><strong>фромусерид</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-126">int</span><span class="sxs-lookup"><span data-stu-id="a2b2b-126">int</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-127">Правительства</span><span class="sxs-lookup"><span data-stu-id="a2b2b-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-128">Пользователь, создавший запрос, вызвавший ошибку.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="a2b2b-129">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2b2b-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b2b-130"><strong>таусерид</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-131">int</span><span class="sxs-lookup"><span data-stu-id="a2b2b-131">int</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-132">Правительства</span><span class="sxs-lookup"><span data-stu-id="a2b2b-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-133">Конечный пользователь для запроса, вызвавшего ошибку.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="a2b2b-134">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2b2b-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b2b-135"><strong>конференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-136">int</span><span class="sxs-lookup"><span data-stu-id="a2b2b-136">int</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-137">Правительства</span><span class="sxs-lookup"><span data-stu-id="a2b2b-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-138">Универсальный код ресурса (URI) Конференции, связанный с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-138">Conference URI related to the error.</span></span> <span data-ttu-id="a2b2b-139">Дополнительные сведения см. <a href="lync-server-2013-conferenceuris-table.md">в таблице таблица conferenceuris в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2b2b-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="a2b2b-140">Как правило, если Конференцеуриид не имеет значение null, то либо Фромусерид, либо Таусерид будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b2b-141"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-142">datetime</span><span class="sxs-lookup"><span data-stu-id="a2b2b-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-143">Правительства</span><span class="sxs-lookup"><span data-stu-id="a2b2b-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-144">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a2b2b-145">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2b2b-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b2b-146"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-147">int</span><span class="sxs-lookup"><span data-stu-id="a2b2b-147">int</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-148">Правительства</span><span class="sxs-lookup"><span data-stu-id="a2b2b-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-149">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-149">ID number to identify the session.</span></span> <span data-ttu-id="a2b2b-150">В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a2b2b-151">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2b2b-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b2b-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-153">int</span><span class="sxs-lookup"><span data-stu-id="a2b2b-153">int</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-154">Правительства</span><span class="sxs-lookup"><span data-stu-id="a2b2b-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-155">Сервер, который отправил отчет об ошибках (при отправке отчета с серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="a2b2b-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="a2b2b-156">Дополнительные сведения см. <a href="lync-server-2013-servers-table.md">в таблице Servers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2b2b-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="a2b2b-157">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b2b-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-159">int</span><span class="sxs-lookup"><span data-stu-id="a2b2b-159">int</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-160">Правительства</span><span class="sxs-lookup"><span data-stu-id="a2b2b-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-161">Сервер, который отправил отчет об ошибках (при отправке отчета с серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="a2b2b-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="a2b2b-162">Дополнительные сведения приведены <a href="lync-server-2013-application-table.md">в таблице Application (приложение) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2b2b-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="a2b2b-163">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b2b-164"><strong>мсдиагхеадер</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-165">изображение</span><span class="sxs-lookup"><span data-stu-id="a2b2b-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a2b2b-166">Дополнительные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-166">More information about the error.</span></span></p>
<p><span data-ttu-id="a2b2b-167">Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="a2b2b-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b2b-168"><strong>клиентверсионид</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-169">int</span><span class="sxs-lookup"><span data-stu-id="a2b2b-169">int</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-170">Правительства</span><span class="sxs-lookup"><span data-stu-id="a2b2b-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-171">Клиентская версия конечной точки, которая отправляет отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="a2b2b-172">Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a2b2b-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b2b-173"><strong>искаптуредбисервер</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-174">Битовая</span><span class="sxs-lookup"><span data-stu-id="a2b2b-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a2b2b-175">— Это отчет об ошибках, записанный агентом CDR, запущенным на сервере переднего плана или отправленным клиентом.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b2b-176"><strong>Флаг</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-177">smallint</span><span class="sxs-lookup"><span data-stu-id="a2b2b-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a2b2b-178">Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b2b-179"><strong>телеметрид</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-180">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="a2b2b-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a2b2b-181">Уникальный идентификатор времени присоединения для различных компонентов, участвующих в конференции.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="a2b2b-182">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b2b-183"><strong>сессионсетуптиме</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-184">int</span><span class="sxs-lookup"><span data-stu-id="a2b2b-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a2b2b-185">Время (в миллисекундах), необходимое для присоединения к конференции определенного компонента.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="a2b2b-186">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b2b-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-188">int</span><span class="sxs-lookup"><span data-stu-id="a2b2b-188">int</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-189">Правительства</span><span class="sxs-lookup"><span data-stu-id="a2b2b-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-190">Представляет полное доменное имя сервера, который создал отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b2b-191"><strong>пулид</strong></span><span class="sxs-lookup"><span data-stu-id="a2b2b-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="a2b2b-192">int</span><span class="sxs-lookup"><span data-stu-id="a2b2b-192">int</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-193">Правительства</span><span class="sxs-lookup"><span data-stu-id="a2b2b-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a2b2b-194">Представляет полное доменное имя пула, в котором был создан отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

