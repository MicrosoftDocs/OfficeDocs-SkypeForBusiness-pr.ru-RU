---
title: 'Lync Server 2013: таблица ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0fc30d4686ffcc1d1cda0474b3b01a645c94be5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="c2d05-102">Таблица ErrorReport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2d05-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2d05-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c2d05-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c2d05-104">В таблице Ерроррепорт хранятся сведения о возникших ошибках.</span><span class="sxs-lookup"><span data-stu-id="c2d05-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="c2d05-105">Каждая запись содержит один экземпляр ошибки.</span><span class="sxs-lookup"><span data-stu-id="c2d05-105">Each record is one error occurrence.</span></span> <span data-ttu-id="c2d05-106">Эти ошибки регистрируются агентом CDR, который запущен на сервере переднего плана или отправлен клиентом.</span><span class="sxs-lookup"><span data-stu-id="c2d05-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2d05-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="c2d05-107">Column</span></span></th>
<th><span data-ttu-id="c2d05-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c2d05-108">Data Type</span></span></th>
<th><span data-ttu-id="c2d05-109">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="c2d05-109">Key/Index</span></span></th>
<th><span data-ttu-id="c2d05-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="c2d05-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2d05-111"><strong>Еррортиме</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-112">datetime</span><span class="sxs-lookup"><span data-stu-id="c2d05-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="c2d05-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c2d05-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c2d05-114">Дата и время, когда возникла ошибка.</span><span class="sxs-lookup"><span data-stu-id="c2d05-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2d05-115"><strong>Ерроррепортсек</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-116">целое</span><span class="sxs-lookup"><span data-stu-id="c2d05-116">int</span></span></p></td>
<td><p><span data-ttu-id="c2d05-117">Primary</span><span class="sxs-lookup"><span data-stu-id="c2d05-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="c2d05-118">ИДЕНТИФИКАЦИОНный номер для идентификации отчета об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c2d05-118">ID number to identify the error report.</span></span> <span data-ttu-id="c2d05-119">Используется в сочетании с <strong>еррортиме</strong> для уникальной идентификации отчета об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c2d05-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2d05-120"><strong>Еррорид</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-121">целое</span><span class="sxs-lookup"><span data-stu-id="c2d05-121">int</span></span></p></td>
<td><p><span data-ttu-id="c2d05-122">Другом</span><span class="sxs-lookup"><span data-stu-id="c2d05-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c2d05-123">Уникальный идентификатор типа ошибки.</span><span class="sxs-lookup"><span data-stu-id="c2d05-123">Unique ID of the error type.</span></span> <span data-ttu-id="c2d05-124">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-errordef-table.md">таблицей еррордеф в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c2d05-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2d05-125"><strong>Фромусерид</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-126">целое</span><span class="sxs-lookup"><span data-stu-id="c2d05-126">int</span></span></p></td>
<td><p><span data-ttu-id="c2d05-127">Другом</span><span class="sxs-lookup"><span data-stu-id="c2d05-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c2d05-128">Пользователь, который поступил на этот запрос, вызвавший ошибку.</span><span class="sxs-lookup"><span data-stu-id="c2d05-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="c2d05-129">Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c2d05-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2d05-130"><strong>Таусерид</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-131">целое</span><span class="sxs-lookup"><span data-stu-id="c2d05-131">int</span></span></p></td>
<td><p><span data-ttu-id="c2d05-132">Другом</span><span class="sxs-lookup"><span data-stu-id="c2d05-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c2d05-133">Конечный пользователь для запроса, вызвавшего ошибку.</span><span class="sxs-lookup"><span data-stu-id="c2d05-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="c2d05-134">Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c2d05-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2d05-135"><strong>Конференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-136">целое</span><span class="sxs-lookup"><span data-stu-id="c2d05-136">int</span></span></p></td>
<td><p><span data-ttu-id="c2d05-137">Другом</span><span class="sxs-lookup"><span data-stu-id="c2d05-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c2d05-138">Универсальный код ресурса (URI) для Конференции, связанный с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c2d05-138">Conference URI related to the error.</span></span> <span data-ttu-id="c2d05-139">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-conferenceuris-table.md">таблицей конференцеурис в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c2d05-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="c2d05-140">Как правило, если Конференцеуриид не имеет значение null, то либо Фромусерид, либо Таусерид будет NULL.</span><span class="sxs-lookup"><span data-stu-id="c2d05-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2d05-141"><strong>Сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-142">datetime</span><span class="sxs-lookup"><span data-stu-id="c2d05-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="c2d05-143">Другом</span><span class="sxs-lookup"><span data-stu-id="c2d05-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c2d05-144">Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c2d05-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c2d05-145">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c2d05-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2d05-146"><strong>Сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-147">целое</span><span class="sxs-lookup"><span data-stu-id="c2d05-147">int</span></span></p></td>
<td><p><span data-ttu-id="c2d05-148">Другом</span><span class="sxs-lookup"><span data-stu-id="c2d05-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c2d05-149">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c2d05-149">ID number to identify the session.</span></span> <span data-ttu-id="c2d05-150">Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c2d05-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c2d05-151">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c2d05-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2d05-152"><strong>Источника</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-153">целое</span><span class="sxs-lookup"><span data-stu-id="c2d05-153">int</span></span></p></td>
<td><p><span data-ttu-id="c2d05-154">Другом</span><span class="sxs-lookup"><span data-stu-id="c2d05-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c2d05-155">Сервер, отправивший отчет об ошибке (при отправке отчета из серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="c2d05-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="c2d05-156">Более подробную информацию вы видите <a href="lync-server-2013-servers-table.md">в таблице Servers (серверы) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c2d05-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="c2d05-157">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2d05-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2d05-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-159">целое</span><span class="sxs-lookup"><span data-stu-id="c2d05-159">int</span></span></p></td>
<td><p><span data-ttu-id="c2d05-160">Другом</span><span class="sxs-lookup"><span data-stu-id="c2d05-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c2d05-161">Сервер, отправивший отчет об ошибке (при отправке отчета из серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="c2d05-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="c2d05-162">Дополнительные сведения приведены <a href="lync-server-2013-application-table.md">в таблице приложение Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c2d05-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="c2d05-163">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2d05-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2d05-164"><strong>Мсдиагхеадер</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-165">изображение</span><span class="sxs-lookup"><span data-stu-id="c2d05-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c2d05-166">Дополнительные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c2d05-166">More information about the error.</span></span></p>
<p><span data-ttu-id="c2d05-167">Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c2d05-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2d05-168"><strong>Клиентверсионид</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-169">целое</span><span class="sxs-lookup"><span data-stu-id="c2d05-169">int</span></span></p></td>
<td><p><span data-ttu-id="c2d05-170">Другом</span><span class="sxs-lookup"><span data-stu-id="c2d05-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c2d05-171">Клиентская версия конечной точки, отправляющей отчет об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c2d05-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="c2d05-172">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-clientversions-table.md">таблицей клиентверсионс в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c2d05-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2d05-173"><strong>Искаптуредбисервер</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-174">бит</span><span class="sxs-lookup"><span data-stu-id="c2d05-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c2d05-175">Отчет об ошибке, записанный агентом CDR, который запущен на сервере переднего плана или отправляется клиентом.</span><span class="sxs-lookup"><span data-stu-id="c2d05-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2d05-176"><strong>Пометка</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-177">smallint</span><span class="sxs-lookup"><span data-stu-id="c2d05-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c2d05-178">Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="c2d05-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2d05-179"><strong>Телеметрид</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-180">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="c2d05-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c2d05-181">Уникальный идентификатор, соответствующий сведениям о времени соединения для различных компонентов, участвующих в Конференции.</span><span class="sxs-lookup"><span data-stu-id="c2d05-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="c2d05-182">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2d05-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2d05-183"><strong>Сессионсетуптиме</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-184">целое</span><span class="sxs-lookup"><span data-stu-id="c2d05-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c2d05-185">Время (в миллисекундах), требуемое конкретным компонентом для присоединения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="c2d05-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="c2d05-186">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2d05-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2d05-187"><strong>Серверид</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-188">целое</span><span class="sxs-lookup"><span data-stu-id="c2d05-188">int</span></span></p></td>
<td><p><span data-ttu-id="c2d05-189">Другом</span><span class="sxs-lookup"><span data-stu-id="c2d05-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c2d05-190">Представляет полное доменное имя сервера, который сгенерировал отчет об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c2d05-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2d05-191"><strong>Пулид</strong></span><span class="sxs-lookup"><span data-stu-id="c2d05-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="c2d05-192">целое</span><span class="sxs-lookup"><span data-stu-id="c2d05-192">int</span></span></p></td>
<td><p><span data-ttu-id="c2d05-193">Другом</span><span class="sxs-lookup"><span data-stu-id="c2d05-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c2d05-194">Представляет полное доменное имя пула, в котором был создан отчет об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c2d05-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

