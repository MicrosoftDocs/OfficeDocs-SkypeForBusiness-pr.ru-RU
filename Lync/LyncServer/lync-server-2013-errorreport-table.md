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
ms.openlocfilehash: 8de4163f94d5848808c5b01c34b1676d3a0bbcff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="7d498-102">Таблица ErrorReport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d498-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d498-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7d498-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7d498-104">В таблице Ерроррепорт хранятся сведения о возникших ошибках.</span><span class="sxs-lookup"><span data-stu-id="7d498-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="7d498-105">Каждая запись содержит один экземпляр ошибки.</span><span class="sxs-lookup"><span data-stu-id="7d498-105">Each record is one error occurrence.</span></span> <span data-ttu-id="7d498-106">Эти ошибки регистрируются агентом CDR, который запущен на сервере переднего плана или отправлен клиентом.</span><span class="sxs-lookup"><span data-stu-id="7d498-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d498-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="7d498-107">Column</span></span></th>
<th><span data-ttu-id="7d498-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7d498-108">Data Type</span></span></th>
<th><span data-ttu-id="7d498-109">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="7d498-109">Key/Index</span></span></th>
<th><span data-ttu-id="7d498-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="7d498-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d498-111"><strong>еррортиме</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-112">datetime</span><span class="sxs-lookup"><span data-stu-id="7d498-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="7d498-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7d498-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="7d498-114">Дата и время, когда возникла ошибка.</span><span class="sxs-lookup"><span data-stu-id="7d498-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d498-115"><strong>ерроррепортсек</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-116">целое</span><span class="sxs-lookup"><span data-stu-id="7d498-116">int</span></span></p></td>
<td><p><span data-ttu-id="7d498-117">Primary</span><span class="sxs-lookup"><span data-stu-id="7d498-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="7d498-118">ИДЕНТИФИКАЦИОНный номер для идентификации отчета об ошибке.</span><span class="sxs-lookup"><span data-stu-id="7d498-118">ID number to identify the error report.</span></span> <span data-ttu-id="7d498-119">Используется в сочетании с <strong>еррортиме</strong> для уникальной идентификации отчета об ошибке.</span><span class="sxs-lookup"><span data-stu-id="7d498-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d498-120"><strong>еррорид</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-121">целое</span><span class="sxs-lookup"><span data-stu-id="7d498-121">int</span></span></p></td>
<td><p><span data-ttu-id="7d498-122">Другом</span><span class="sxs-lookup"><span data-stu-id="7d498-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7d498-123">Уникальный идентификатор типа ошибки.</span><span class="sxs-lookup"><span data-stu-id="7d498-123">Unique ID of the error type.</span></span> <span data-ttu-id="7d498-124">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-errordef-table.md">таблицей еррордеф в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7d498-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d498-125"><strong>фромусерид</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-126">целое</span><span class="sxs-lookup"><span data-stu-id="7d498-126">int</span></span></p></td>
<td><p><span data-ttu-id="7d498-127">Другом</span><span class="sxs-lookup"><span data-stu-id="7d498-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7d498-128">Пользователь, который поступил на этот запрос, вызвавший ошибку.</span><span class="sxs-lookup"><span data-stu-id="7d498-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="7d498-129">Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7d498-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d498-130"><strong>таусерид</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-131">целое</span><span class="sxs-lookup"><span data-stu-id="7d498-131">int</span></span></p></td>
<td><p><span data-ttu-id="7d498-132">Другом</span><span class="sxs-lookup"><span data-stu-id="7d498-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7d498-133">Конечный пользователь для запроса, вызвавшего ошибку.</span><span class="sxs-lookup"><span data-stu-id="7d498-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="7d498-134">Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7d498-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d498-135"><strong>конференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-136">целое</span><span class="sxs-lookup"><span data-stu-id="7d498-136">int</span></span></p></td>
<td><p><span data-ttu-id="7d498-137">Другом</span><span class="sxs-lookup"><span data-stu-id="7d498-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7d498-138">Универсальный код ресурса (URI) для Конференции, связанный с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="7d498-138">Conference URI related to the error.</span></span> <span data-ttu-id="7d498-139">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-conferenceuris-table.md">таблицей конференцеурис в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7d498-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="7d498-140">Как правило, если Конференцеуриид не имеет значение null, то либо Фромусерид, либо Таусерид будет NULL.</span><span class="sxs-lookup"><span data-stu-id="7d498-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d498-141"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-142">datetime</span><span class="sxs-lookup"><span data-stu-id="7d498-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="7d498-143">Другом</span><span class="sxs-lookup"><span data-stu-id="7d498-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7d498-144">Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="7d498-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="7d498-145">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7d498-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d498-146"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-147">целое</span><span class="sxs-lookup"><span data-stu-id="7d498-147">int</span></span></p></td>
<td><p><span data-ttu-id="7d498-148">Другом</span><span class="sxs-lookup"><span data-stu-id="7d498-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7d498-149">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="7d498-149">ID number to identify the session.</span></span> <span data-ttu-id="7d498-150">Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="7d498-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="7d498-151">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7d498-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d498-152"><strong>Источника</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-153">целое</span><span class="sxs-lookup"><span data-stu-id="7d498-153">int</span></span></p></td>
<td><p><span data-ttu-id="7d498-154">Другом</span><span class="sxs-lookup"><span data-stu-id="7d498-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7d498-155">Сервер, отправивший отчет об ошибке (при отправке отчета из серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="7d498-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="7d498-156">Более подробную информацию вы видите <a href="lync-server-2013-servers-table.md">в таблице Servers (серверы) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7d498-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="7d498-157">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7d498-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d498-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-159">целое</span><span class="sxs-lookup"><span data-stu-id="7d498-159">int</span></span></p></td>
<td><p><span data-ttu-id="7d498-160">Другом</span><span class="sxs-lookup"><span data-stu-id="7d498-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7d498-161">Сервер, отправивший отчет об ошибке (при отправке отчета из серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="7d498-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="7d498-162">Дополнительные сведения приведены <a href="lync-server-2013-application-table.md">в таблице приложение Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7d498-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="7d498-163">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7d498-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d498-164"><strong>мсдиагхеадер</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-165">изображение</span><span class="sxs-lookup"><span data-stu-id="7d498-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7d498-166">Дополнительные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="7d498-166">More information about the error.</span></span></p>
<p><span data-ttu-id="7d498-167">Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="7d498-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d498-168"><strong>клиентверсионид</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-169">целое</span><span class="sxs-lookup"><span data-stu-id="7d498-169">int</span></span></p></td>
<td><p><span data-ttu-id="7d498-170">Другом</span><span class="sxs-lookup"><span data-stu-id="7d498-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7d498-171">Клиентская версия конечной точки, отправляющей отчет об ошибке.</span><span class="sxs-lookup"><span data-stu-id="7d498-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="7d498-172">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-clientversions-table.md">таблицей клиентверсионс в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7d498-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d498-173"><strong>искаптуредбисервер</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-174">бит</span><span class="sxs-lookup"><span data-stu-id="7d498-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d498-175">Отчет об ошибке, записанный агентом CDR, который запущен на сервере переднего плана или отправляется клиентом.</span><span class="sxs-lookup"><span data-stu-id="7d498-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d498-176"><strong>Пометка</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-177">smallint</span><span class="sxs-lookup"><span data-stu-id="7d498-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d498-178">Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="7d498-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d498-179"><strong>телеметрид</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-180">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="7d498-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d498-181">Уникальный идентификатор, соответствующий сведениям о времени соединения для различных компонентов, участвующих в Конференции.</span><span class="sxs-lookup"><span data-stu-id="7d498-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="7d498-182">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7d498-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d498-183"><strong>сессионсетуптиме</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-184">целое</span><span class="sxs-lookup"><span data-stu-id="7d498-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d498-185">Время (в миллисекундах), требуемое конкретным компонентом для присоединения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="7d498-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="7d498-186">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7d498-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d498-187"><strong>серверид</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-188">целое</span><span class="sxs-lookup"><span data-stu-id="7d498-188">int</span></span></p></td>
<td><p><span data-ttu-id="7d498-189">Другом</span><span class="sxs-lookup"><span data-stu-id="7d498-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7d498-190">Представляет полное доменное имя сервера, который сгенерировал отчет об ошибке.</span><span class="sxs-lookup"><span data-stu-id="7d498-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d498-191"><strong>пулид</strong></span><span class="sxs-lookup"><span data-stu-id="7d498-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="7d498-192">целое</span><span class="sxs-lookup"><span data-stu-id="7d498-192">int</span></span></p></td>
<td><p><span data-ttu-id="7d498-193">Другом</span><span class="sxs-lookup"><span data-stu-id="7d498-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7d498-194">Представляет полное доменное имя пула, в котором был создан отчет об ошибке.</span><span class="sxs-lookup"><span data-stu-id="7d498-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

