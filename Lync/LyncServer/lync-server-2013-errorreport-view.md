---
title: 'Lync Server 2013: представление ErrorReport'
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
ms.openlocfilehash: e635cd289f0224a7f8d4106cecc3d8b047e9bb92
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="5534b-102">Представление ErrorReport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5534b-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5534b-103">_**Последнее изменение темы:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="5534b-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="5534b-104">В представлении ErrorReport сохраняется информация о возникших ошибках.</span><span class="sxs-lookup"><span data-stu-id="5534b-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="5534b-105">Каждая запись соответствует одному случаю возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="5534b-105">Each record is one error occurrence.</span></span> <span data-ttu-id="5534b-106">Ошибки фиксируются агентом CDR, работающим на сервере переднего плана, или передаются клиентом.</span><span class="sxs-lookup"><span data-stu-id="5534b-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="5534b-107">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5534b-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5534b-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="5534b-108">Column</span></span></th>
<th><span data-ttu-id="5534b-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="5534b-109">Data Type</span></span></th>
<th><span data-ttu-id="5534b-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="5534b-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5534b-111"><strong>Поля errortime</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-112">datetime</span><span class="sxs-lookup"><span data-stu-id="5534b-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="5534b-p102">Время возникновения ошибки. Используется в сочетании с параметром ErrorReportSeq для уникальной идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="5534b-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5534b-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-116">int</span><span class="sxs-lookup"><span data-stu-id="5534b-116">int</span></span></p></td>
<td><p><span data-ttu-id="5534b-p103">Идентификатор ошибки. Используется в сочетании с параметром ErrorTime для уникальной идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="5534b-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5534b-119"><strong>мсдиагид</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-120">int</span><span class="sxs-lookup"><span data-stu-id="5534b-120">int</span></span></p></td>
<td><p><span data-ttu-id="5534b-121">Диагностический идентификатор для сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5534b-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5534b-122"><strong>фромури</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5534b-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5534b-124">URI пользователя, инициировавшего ошибку.</span><span class="sxs-lookup"><span data-stu-id="5534b-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5534b-125"><strong>фромуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5534b-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5534b-127">Тип URI пользователя, отправившего ошибку.</span><span class="sxs-lookup"><span data-stu-id="5534b-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="5534b-128">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5534b-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5534b-129"><strong>фромтенант</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5534b-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5534b-131">Клиент пользователя, который поступил с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="5534b-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="5534b-132">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5534b-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5534b-133"><strong>таури</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-134">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5534b-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5534b-135">URI пользователя, который был целью сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5534b-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5534b-136"><strong>тауритипе</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5534b-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5534b-p106">Тип URI пользователя, который был целью сообщения об ошибке. См. таблицу UriTypes для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="5534b-p106">Type of URI of the user who target of the error report. See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5534b-140"><strong>тотенант</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5534b-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5534b-142">Клиент пользователя, который нацелен на отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="5534b-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="5534b-143">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5534b-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5534b-144"><strong>конференцеури</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5534b-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5534b-146">URI конференции, которая была целью сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5534b-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5534b-147"><strong>конференцеуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5534b-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5534b-149">Тип URI конференции, которая была целью отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="5534b-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="5534b-150">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5534b-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5534b-151"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-152">datetime</span><span class="sxs-lookup"><span data-stu-id="5534b-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="5534b-153">Время запроса сеанса, созданного отчетом об ошибках.</span><span class="sxs-lookup"><span data-stu-id="5534b-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="5534b-154">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="5534b-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="5534b-155">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5534b-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5534b-156"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-157">int</span><span class="sxs-lookup"><span data-stu-id="5534b-157">int</span></span></p></td>
<td><p><span data-ttu-id="5534b-158">ИДЕНТИФИКАЦИОНный номер для идентификации запроса сеанса, созданного отчетом об ошибках.</span><span class="sxs-lookup"><span data-stu-id="5534b-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="5534b-159">Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="5534b-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="5534b-160">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5534b-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5534b-161"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-162">варстринг (775)</span><span class="sxs-lookup"><span data-stu-id="5534b-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="5534b-p111">Диалоговый идентификатор SIP сеанса, инициировавшего ошибку. Используется следующий формат:</span><span class="sxs-lookup"><span data-stu-id="5534b-p111">SIP dialog ID of session that originated the error. The format is:</span></span></p>
<p><span data-ttu-id="5534b-165">диалоговое окно; from — Tag; to – Tag</span><span class="sxs-lookup"><span data-stu-id="5534b-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="5534b-166">Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5534b-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="5534b-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="5534b-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5534b-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5534b-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5534b-170">Версии клиента, используемого пользователем, инициировавшим ошибку.</span><span class="sxs-lookup"><span data-stu-id="5534b-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5534b-171"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-172">int</span><span class="sxs-lookup"><span data-stu-id="5534b-172">int</span></span></p></td>
<td><p><span data-ttu-id="5534b-173">Клиент, используемый пользователем, который поступил с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="5534b-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="5534b-174">Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5534b-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5534b-175"><strong>клиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-176">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5534b-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5534b-177">Имя категории клиента, используемого пользователем, инициировавшим ошибку.</span><span class="sxs-lookup"><span data-stu-id="5534b-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5534b-178"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5534b-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5534b-180">Имя сервера, с которого поступило сообщение об ошибке (если отчет был отправлен серверным компонентом).</span><span class="sxs-lookup"><span data-stu-id="5534b-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5534b-181"><strong>Приложение</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-182">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5534b-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5534b-183">Имя приложения, инициировавшего ошибку (если отчет был отправлен серверным компонентом).</span><span class="sxs-lookup"><span data-stu-id="5534b-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5534b-184"><strong>респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-185">int</span><span class="sxs-lookup"><span data-stu-id="5534b-185">int</span></span></p></td>
<td><p><span data-ttu-id="5534b-186">Код ответа SIP на сеанс SIP-сообщения, содержащего отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="5534b-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5534b-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-188">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="5534b-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="5534b-189">Тип запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="5534b-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5534b-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-191">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="5534b-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="5534b-192">Тип содержимого запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="5534b-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5534b-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5534b-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5534b-195">Тип сеанса.</span><span class="sxs-lookup"><span data-stu-id="5534b-195">Type of session.</span></span> <span data-ttu-id="5534b-196">Дополнительные сведения см. <a href="lync-server-2013-calltype-table.md">в таблице CallType в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5534b-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5534b-197"><strong>телеметрид</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-198">идентификатора</span><span class="sxs-lookup"><span data-stu-id="5534b-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5534b-199">Уникальный идентификатор времени присоединения для различных компонентов, участвующих в конференции.</span><span class="sxs-lookup"><span data-stu-id="5534b-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5534b-200"><strong>сетуптиме</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-201">int</span><span class="sxs-lookup"><span data-stu-id="5534b-201">int</span></span></p></td>
<td><p><span data-ttu-id="5534b-202">Время (в миллисекундах), необходимое для присоединения к конференции определенного компонента.</span><span class="sxs-lookup"><span data-stu-id="5534b-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5534b-203"><strong>искаптуредбисервер</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-204">Битовая</span><span class="sxs-lookup"><span data-stu-id="5534b-204">bit</span></span></p></td>
<td><p><span data-ttu-id="5534b-205">Указывает, был ли данный отчет об ошибках получен агентом CDR, работающим на сервере переднего плана, или отправлен клиентом.</span><span class="sxs-lookup"><span data-stu-id="5534b-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5534b-206"><strong>Флаг</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-207">smallint</span><span class="sxs-lookup"><span data-stu-id="5534b-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="5534b-208">Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="5534b-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5534b-209"><strong>мсдиагхеадер</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-210">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="5534b-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="5534b-211">Дополнительные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5534b-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5534b-212"><strong>Интерфейса</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="5534b-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="5534b-214">Полное доменное имя сервера переднего плана, который отправил отчет.</span><span class="sxs-lookup"><span data-stu-id="5534b-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5534b-215"><strong>Ресурсов</strong></span><span class="sxs-lookup"><span data-stu-id="5534b-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="5534b-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="5534b-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="5534b-217">Полное доменное имя пула, содержащего сервер переднего плана, который отправил отчет.</span><span class="sxs-lookup"><span data-stu-id="5534b-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

