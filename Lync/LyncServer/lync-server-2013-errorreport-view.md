---
title: 'Lync Server 2013: представление ErrorReport'
description: 'Lync Server 2013: представление ErrorReport.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50fb0a362c71d8dfb5873157e7b1ed3d3eb680ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572045"
---
# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="66550-103">Представление ErrorReport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66550-103">ErrorReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66550-104">_**Последнее изменение темы:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="66550-104">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="66550-105">В представлении ErrorReport сохраняется информация о возникших ошибках.</span><span class="sxs-lookup"><span data-stu-id="66550-105">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="66550-106">Каждая запись соответствует одному случаю возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="66550-106">Each record is one error occurrence.</span></span> <span data-ttu-id="66550-107">Ошибки фиксируются агентом CDR, работающим на сервере переднего плана, или передаются клиентом.</span><span class="sxs-lookup"><span data-stu-id="66550-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="66550-108">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66550-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66550-109">Столбец</span><span class="sxs-lookup"><span data-stu-id="66550-109">Column</span></span></th>
<th><span data-ttu-id="66550-110">Тип данных</span><span class="sxs-lookup"><span data-stu-id="66550-110">Data Type</span></span></th>
<th><span data-ttu-id="66550-111">Сведения</span><span class="sxs-lookup"><span data-stu-id="66550-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66550-112"><strong>Поля errortime</strong></span><span class="sxs-lookup"><span data-stu-id="66550-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-113">datetime</span><span class="sxs-lookup"><span data-stu-id="66550-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="66550-p102">Время возникновения ошибки. Используется в сочетании с параметром ErrorReportSeq для уникальной идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="66550-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66550-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="66550-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-117">int</span><span class="sxs-lookup"><span data-stu-id="66550-117">int</span></span></p></td>
<td><p><span data-ttu-id="66550-p103">Идентификатор ошибки. Используется в сочетании с параметром ErrorTime для уникальной идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="66550-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66550-120"><strong>мсдиагид</strong></span><span class="sxs-lookup"><span data-stu-id="66550-120"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-121">int</span><span class="sxs-lookup"><span data-stu-id="66550-121">int</span></span></p></td>
<td><p><span data-ttu-id="66550-122">Диагностический идентификатор для сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="66550-122">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66550-123"><strong>фромури</strong></span><span class="sxs-lookup"><span data-stu-id="66550-123"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-124">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="66550-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="66550-125">URI пользователя, инициировавшего ошибку.</span><span class="sxs-lookup"><span data-stu-id="66550-125">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66550-126"><strong>фромуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="66550-126"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="66550-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="66550-128">Тип URI пользователя, отправившего ошибку.</span><span class="sxs-lookup"><span data-stu-id="66550-128">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="66550-129">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66550-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66550-130"><strong>фромтенант</strong></span><span class="sxs-lookup"><span data-stu-id="66550-130"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="66550-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="66550-132">Клиент пользователя, который поступил с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="66550-132">Tenant of the user who originated the error.</span></span> <span data-ttu-id="66550-133">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66550-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66550-134"><strong>таури</strong></span><span class="sxs-lookup"><span data-stu-id="66550-134"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-135">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="66550-135">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="66550-136">URI пользователя, который был целью сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="66550-136">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66550-137"><strong>тауритипе</strong></span><span class="sxs-lookup"><span data-stu-id="66550-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-138">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="66550-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="66550-p106">Тип URI пользователя, который был целью сообщения об ошибке. См. таблицу UriTypes для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="66550-p106">Type of URI of the user who target of the error report. See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66550-141"><strong>тотенант</strong></span><span class="sxs-lookup"><span data-stu-id="66550-141"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="66550-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="66550-143">Клиент пользователя, который нацелен на отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="66550-143">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="66550-144">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66550-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66550-145"><strong>конференцеури</strong></span><span class="sxs-lookup"><span data-stu-id="66550-145"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="66550-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="66550-147">URI конференции, которая была целью сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="66550-147">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66550-148"><strong>конференцеуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="66550-148"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="66550-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="66550-150">Тип URI конференции, которая была целью отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="66550-150">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="66550-151">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66550-151">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66550-152"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="66550-152"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-153">datetime</span><span class="sxs-lookup"><span data-stu-id="66550-153">datetime</span></span></p></td>
<td><p><span data-ttu-id="66550-154">Время запроса сеанса, созданного отчетом об ошибках.</span><span class="sxs-lookup"><span data-stu-id="66550-154">Time of session request that originated the error report.</span></span> <span data-ttu-id="66550-155">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="66550-155">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="66550-156">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66550-156">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66550-157"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="66550-157"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-158">int</span><span class="sxs-lookup"><span data-stu-id="66550-158">int</span></span></p></td>
<td><p><span data-ttu-id="66550-159">ИДЕНТИФИКАЦИОНный номер для идентификации запроса сеанса, созданного отчетом об ошибках.</span><span class="sxs-lookup"><span data-stu-id="66550-159">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="66550-160">Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="66550-160">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="66550-161">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66550-161">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66550-162"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="66550-162"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-163">варстринг (775)</span><span class="sxs-lookup"><span data-stu-id="66550-163">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="66550-p111">Диалоговый идентификатор SIP сеанса, инициировавшего ошибку. Используется следующий формат:</span><span class="sxs-lookup"><span data-stu-id="66550-p111">SIP dialog ID of session that originated the error. The format is:</span></span></p>
<p><span data-ttu-id="66550-166">диалоговое окно; from — Tag; to – Tag</span><span class="sxs-lookup"><span data-stu-id="66550-166">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="66550-167">Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="66550-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="66550-168">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="66550-168">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66550-169"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="66550-169"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-170">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="66550-170">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="66550-171">Версии клиента, используемого пользователем, инициировавшим ошибку.</span><span class="sxs-lookup"><span data-stu-id="66550-171">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66550-172"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="66550-172"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-173">int</span><span class="sxs-lookup"><span data-stu-id="66550-173">int</span></span></p></td>
<td><p><span data-ttu-id="66550-174">Клиент, используемый пользователем, который поступил с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="66550-174">Client used by the user who originated the error.</span></span> <span data-ttu-id="66550-175">Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66550-175">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66550-176"><strong>клиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="66550-176"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-177">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="66550-177">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="66550-178">Имя категории клиента, используемого пользователем, инициировавшим ошибку.</span><span class="sxs-lookup"><span data-stu-id="66550-178">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66550-179"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="66550-179"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-180">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="66550-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="66550-181">Имя сервера, с которого поступило сообщение об ошибке (если отчет был отправлен серверным компонентом).</span><span class="sxs-lookup"><span data-stu-id="66550-181">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66550-182"><strong>Приложение</strong></span><span class="sxs-lookup"><span data-stu-id="66550-182"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-183">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="66550-183">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="66550-184">Имя приложения, инициировавшего ошибку (если отчет был отправлен серверным компонентом).</span><span class="sxs-lookup"><span data-stu-id="66550-184">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66550-185"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="66550-185"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-186">int</span><span class="sxs-lookup"><span data-stu-id="66550-186">int</span></span></p></td>
<td><p><span data-ttu-id="66550-187">Код ответа SIP на сеанс SIP-сообщения, содержащего отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="66550-187">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66550-188"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="66550-188"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-189">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="66550-189">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="66550-190">Тип запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="66550-190">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66550-191"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="66550-191"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-192">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="66550-192">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="66550-193">Тип содержимого запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="66550-193">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66550-194"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="66550-194"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="66550-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="66550-196">Тип сеанса.</span><span class="sxs-lookup"><span data-stu-id="66550-196">Type of session.</span></span> <span data-ttu-id="66550-197">Дополнительные сведения см. <a href="lync-server-2013-calltype-table.md">в таблице CallType в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66550-197">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66550-198"><strong>телеметрид</strong></span><span class="sxs-lookup"><span data-stu-id="66550-198"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-199">идентификатора</span><span class="sxs-lookup"><span data-stu-id="66550-199">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="66550-200">Уникальный идентификатор времени присоединения для различных компонентов, участвующих в конференции.</span><span class="sxs-lookup"><span data-stu-id="66550-200">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66550-201"><strong>сетуптиме</strong></span><span class="sxs-lookup"><span data-stu-id="66550-201"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-202">int</span><span class="sxs-lookup"><span data-stu-id="66550-202">int</span></span></p></td>
<td><p><span data-ttu-id="66550-203">Время (в миллисекундах), необходимое для присоединения к конференции определенного компонента.</span><span class="sxs-lookup"><span data-stu-id="66550-203">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66550-204"><strong>искаптуредбисервер</strong></span><span class="sxs-lookup"><span data-stu-id="66550-204"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-205">Битовая</span><span class="sxs-lookup"><span data-stu-id="66550-205">bit</span></span></p></td>
<td><p><span data-ttu-id="66550-206">Указывает, был ли данный отчет об ошибках получен агентом CDR, работающим на сервере переднего плана, или отправлен клиентом.</span><span class="sxs-lookup"><span data-stu-id="66550-206">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66550-207"><strong>Флаг</strong></span><span class="sxs-lookup"><span data-stu-id="66550-207"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-208">smallint</span><span class="sxs-lookup"><span data-stu-id="66550-208">smallint</span></span></p></td>
<td><p><span data-ttu-id="66550-209">Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="66550-209">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66550-210"><strong>мсдиагхеадер</strong></span><span class="sxs-lookup"><span data-stu-id="66550-210"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-211">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="66550-211">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="66550-212">Дополнительные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="66550-212">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66550-213"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="66550-213"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-214">nvarchar</span><span class="sxs-lookup"><span data-stu-id="66550-214">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="66550-215">Полное доменное имя сервера переднего плана, который отправил отчет.</span><span class="sxs-lookup"><span data-stu-id="66550-215">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66550-216"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="66550-216"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="66550-217">nvarchar</span><span class="sxs-lookup"><span data-stu-id="66550-217">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="66550-218">Полное доменное имя пула, содержащего сервер переднего плана, который отправил отчет.</span><span class="sxs-lookup"><span data-stu-id="66550-218">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

