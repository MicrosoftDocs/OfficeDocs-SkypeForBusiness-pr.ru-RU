---
title: 'Lync Server 2013: таблица ErrorReport'
description: 'Lync Server 2013: таблица ErrorReport.'
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
ms.openlocfilehash: 9c1cc65c396c16dc137255438f7ef7c32b2d0b78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572015"
---
# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="1e12c-103">Таблица ErrorReport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e12c-103">ErrorReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e12c-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1e12c-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1e12c-105">В таблице ErrorReport хранятся сведения о возникших ошибках.</span><span class="sxs-lookup"><span data-stu-id="1e12c-105">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="1e12c-106">Каждая запись соответствует одному случаю возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="1e12c-106">Each record is one error occurrence.</span></span> <span data-ttu-id="1e12c-107">Ошибки фиксируются агентом CDR, работающим на сервере переднего плана, или передаются клиентом.</span><span class="sxs-lookup"><span data-stu-id="1e12c-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e12c-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="1e12c-108">Column</span></span></th>
<th><span data-ttu-id="1e12c-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="1e12c-109">Data Type</span></span></th>
<th><span data-ttu-id="1e12c-110">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="1e12c-110">Key/Index</span></span></th>
<th><span data-ttu-id="1e12c-111">Сведения</span><span class="sxs-lookup"><span data-stu-id="1e12c-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e12c-112"><strong>Поля errortime</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-113">datetime</span><span class="sxs-lookup"><span data-stu-id="1e12c-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="1e12c-114">Primary</span><span class="sxs-lookup"><span data-stu-id="1e12c-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="1e12c-115">Дата и время возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="1e12c-115">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e12c-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-117">int</span><span class="sxs-lookup"><span data-stu-id="1e12c-117">int</span></span></p></td>
<td><p><span data-ttu-id="1e12c-118">Primary</span><span class="sxs-lookup"><span data-stu-id="1e12c-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="1e12c-119">ИДЕНТИФИКАЦИОНный номер, идентифицирующий отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="1e12c-119">ID number to identify the error report.</span></span> <span data-ttu-id="1e12c-120">Используется совместно с <strong>поля errortime</strong> для уникальной идентификации отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="1e12c-120">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e12c-121"><strong>еррорид</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-121"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-122">int</span><span class="sxs-lookup"><span data-stu-id="1e12c-122">int</span></span></p></td>
<td><p><span data-ttu-id="1e12c-123">Правительства</span><span class="sxs-lookup"><span data-stu-id="1e12c-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1e12c-124">Уникальный идентификатор типа ошибки.</span><span class="sxs-lookup"><span data-stu-id="1e12c-124">Unique ID of the error type.</span></span> <span data-ttu-id="1e12c-125">Дополнительные сведения см. <a href="lync-server-2013-errordef-table.md">в таблице таблица errordef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1e12c-125">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e12c-126"><strong>фромусерид</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-126"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-127">int</span><span class="sxs-lookup"><span data-stu-id="1e12c-127">int</span></span></p></td>
<td><p><span data-ttu-id="1e12c-128">Правительства</span><span class="sxs-lookup"><span data-stu-id="1e12c-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1e12c-129">Пользователь, создавший запрос, вызвавший ошибку.</span><span class="sxs-lookup"><span data-stu-id="1e12c-129">User who originated the request that caused the error.</span></span> <span data-ttu-id="1e12c-130">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1e12c-130">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e12c-131"><strong>таусерид</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-131"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-132">int</span><span class="sxs-lookup"><span data-stu-id="1e12c-132">int</span></span></p></td>
<td><p><span data-ttu-id="1e12c-133">Правительства</span><span class="sxs-lookup"><span data-stu-id="1e12c-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1e12c-134">Конечный пользователь для запроса, вызвавшего ошибку.</span><span class="sxs-lookup"><span data-stu-id="1e12c-134">Destination user for the request that caused the error.</span></span> <span data-ttu-id="1e12c-135">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1e12c-135">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e12c-136"><strong>конференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-136"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-137">int</span><span class="sxs-lookup"><span data-stu-id="1e12c-137">int</span></span></p></td>
<td><p><span data-ttu-id="1e12c-138">Правительства</span><span class="sxs-lookup"><span data-stu-id="1e12c-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1e12c-139">Универсальный код ресурса (URI) Конференции, связанный с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="1e12c-139">Conference URI related to the error.</span></span> <span data-ttu-id="1e12c-140">Дополнительные сведения см. <a href="lync-server-2013-conferenceuris-table.md">в таблице таблица conferenceuris в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1e12c-140">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="1e12c-141">Как правило, если Конференцеуриид не имеет значение null, то либо Фромусерид, либо Таусерид будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="1e12c-141">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e12c-142"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-142"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-143">datetime</span><span class="sxs-lookup"><span data-stu-id="1e12c-143">datetime</span></span></p></td>
<td><p><span data-ttu-id="1e12c-144">Правительства</span><span class="sxs-lookup"><span data-stu-id="1e12c-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1e12c-145">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="1e12c-145">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1e12c-146">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1e12c-146">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e12c-147"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-147"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-148">int</span><span class="sxs-lookup"><span data-stu-id="1e12c-148">int</span></span></p></td>
<td><p><span data-ttu-id="1e12c-149">Правительства</span><span class="sxs-lookup"><span data-stu-id="1e12c-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1e12c-150">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="1e12c-150">ID number to identify the session.</span></span> <span data-ttu-id="1e12c-151">В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="1e12c-151">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1e12c-152">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1e12c-152">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e12c-153"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-153"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-154">int</span><span class="sxs-lookup"><span data-stu-id="1e12c-154">int</span></span></p></td>
<td><p><span data-ttu-id="1e12c-155">Правительства</span><span class="sxs-lookup"><span data-stu-id="1e12c-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1e12c-156">Сервер, который отправил отчет об ошибках (при отправке отчета с серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="1e12c-156">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="1e12c-157">Дополнительные сведения см. <a href="lync-server-2013-servers-table.md">в таблице Servers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1e12c-157">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="1e12c-158">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e12c-158">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e12c-159"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-159"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-160">int</span><span class="sxs-lookup"><span data-stu-id="1e12c-160">int</span></span></p></td>
<td><p><span data-ttu-id="1e12c-161">Правительства</span><span class="sxs-lookup"><span data-stu-id="1e12c-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1e12c-162">Сервер, который отправил отчет об ошибках (при отправке отчета с серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="1e12c-162">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="1e12c-163">Дополнительные сведения приведены <a href="lync-server-2013-application-table.md">в таблице Application (приложение) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1e12c-163">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="1e12c-164">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e12c-164">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e12c-165"><strong>мсдиагхеадер</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-165"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-166">изображение</span><span class="sxs-lookup"><span data-stu-id="1e12c-166">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1e12c-167">Дополнительные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="1e12c-167">More information about the error.</span></span></p>
<p><span data-ttu-id="1e12c-168">Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="1e12c-168">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e12c-169"><strong>клиентверсионид</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-169"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-170">int</span><span class="sxs-lookup"><span data-stu-id="1e12c-170">int</span></span></p></td>
<td><p><span data-ttu-id="1e12c-171">Правительства</span><span class="sxs-lookup"><span data-stu-id="1e12c-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1e12c-172">Клиентская версия конечной точки, которая отправляет отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="1e12c-172">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="1e12c-173">Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1e12c-173">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e12c-174"><strong>искаптуредбисервер</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-174"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-175">Битовая</span><span class="sxs-lookup"><span data-stu-id="1e12c-175">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1e12c-176">— Это отчет об ошибках, записанный агентом CDR, запущенным на сервере переднего плана или отправленным клиентом.</span><span class="sxs-lookup"><span data-stu-id="1e12c-176">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e12c-177"><strong>Флаг</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-177"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-178">smallint</span><span class="sxs-lookup"><span data-stu-id="1e12c-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1e12c-179">Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="1e12c-179">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e12c-180"><strong>телеметрид</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-180"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-181">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="1e12c-181">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1e12c-182">Уникальный идентификатор времени присоединения для различных компонентов, участвующих в конференции.</span><span class="sxs-lookup"><span data-stu-id="1e12c-182">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="1e12c-183">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e12c-183">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e12c-184"><strong>сессионсетуптиме</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-184"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-185">int</span><span class="sxs-lookup"><span data-stu-id="1e12c-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1e12c-186">Время (в миллисекундах), необходимое для присоединения к конференции определенного компонента.</span><span class="sxs-lookup"><span data-stu-id="1e12c-186">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="1e12c-187">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e12c-187">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e12c-188"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-188"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-189">int</span><span class="sxs-lookup"><span data-stu-id="1e12c-189">int</span></span></p></td>
<td><p><span data-ttu-id="1e12c-190">Правительства</span><span class="sxs-lookup"><span data-stu-id="1e12c-190">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1e12c-191">Представляет полное доменное имя сервера, который создал отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="1e12c-191">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e12c-192"><strong>пулид</strong></span><span class="sxs-lookup"><span data-stu-id="1e12c-192"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="1e12c-193">int</span><span class="sxs-lookup"><span data-stu-id="1e12c-193">int</span></span></p></td>
<td><p><span data-ttu-id="1e12c-194">Правительства</span><span class="sxs-lookup"><span data-stu-id="1e12c-194">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1e12c-195">Представляет полное доменное имя пула, в котором был создан отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="1e12c-195">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

