---
title: 'Lync Server 2013: представление Ерроррепорт'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b50a2615fe83ed481d9642ac6895120f20b9fd0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="5f762-102">Ерроррепорт представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f762-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f762-103">_**Тема последнего изменения:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="5f762-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="5f762-104">В представлении Ерроррепорт хранятся сведения об ошибках, о которых сообщается.</span><span class="sxs-lookup"><span data-stu-id="5f762-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="5f762-105">Каждая запись содержит один экземпляр ошибки.</span><span class="sxs-lookup"><span data-stu-id="5f762-105">Each record is one error occurrence.</span></span> <span data-ttu-id="5f762-106">Эти ошибки регистрируются агентом CDR, который запущен на сервере переднего плана или отправлен клиентом.</span><span class="sxs-lookup"><span data-stu-id="5f762-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="5f762-107">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f762-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f762-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="5f762-108">Column</span></span></th>
<th><span data-ttu-id="5f762-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="5f762-109">Data Type</span></span></th>
<th><span data-ttu-id="5f762-110">Подробности</span><span class="sxs-lookup"><span data-stu-id="5f762-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f762-111"><strong>Еррортиме</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-112">datetime</span><span class="sxs-lookup"><span data-stu-id="5f762-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="5f762-113">Время возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="5f762-113">Time of error occurred.</span></span> <span data-ttu-id="5f762-114">Используется в сочетании с Ерроррепортсек для уникальной идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="5f762-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f762-115"><strong>Ерроррепортсек</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-116">целое</span><span class="sxs-lookup"><span data-stu-id="5f762-116">int</span></span></p></td>
<td><p><span data-ttu-id="5f762-117">ИДЕНТИФИКАЦИОНный номер для идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="5f762-117">ID number to identify the error.</span></span> <span data-ttu-id="5f762-118">Используется в сочетании с Еррортиме для уникальной идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="5f762-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f762-119"><strong>Мсдиагид</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-120">целое</span><span class="sxs-lookup"><span data-stu-id="5f762-120">int</span></span></p></td>
<td><p><span data-ttu-id="5f762-121">Идентификатор диагностики для отчета об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5f762-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f762-122"><strong>Фромури</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5f762-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5f762-124">URI пользователя, который поступил с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="5f762-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f762-125"><strong>Фромуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5f762-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f762-127">Тип URI пользователя, который поступил на ошибку.</span><span class="sxs-lookup"><span data-stu-id="5f762-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="5f762-128">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5f762-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f762-129"><strong>Фромтенант</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5f762-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f762-131">Клиент пользователя, который поступил с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="5f762-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="5f762-132">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5f762-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f762-133"><strong>Таури</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-134">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5f762-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5f762-135">Универсальный код ресурса (URI) пользователя, который является целью отчета об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5f762-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f762-136"><strong>Тауритипе</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5f762-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f762-138">Тип URI пользователя, который является конечным лицом отчета об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5f762-138">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="5f762-139">Для получения дополнительных сведений ознакомьтесь с таблицей Уритипес.</span><span class="sxs-lookup"><span data-stu-id="5f762-139">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f762-140"><strong>Тотенант</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-141">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5f762-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f762-142">Клиент пользователя, который является конечным лицом отчета об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5f762-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="5f762-143">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5f762-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f762-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5f762-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5f762-146">Универсальный код ресурса (URI) Конференции, которая была целью отчета об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5f762-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f762-147"><strong>Конференцеуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5f762-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f762-149">Тип URI конференции, которая была целью отчета об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5f762-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="5f762-150">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5f762-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f762-151"><strong>Сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-152">datetime</span><span class="sxs-lookup"><span data-stu-id="5f762-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="5f762-153">Время запроса сеанса, в котором был создан отчет об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5f762-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="5f762-154">Используется в сочетании с Сессионидсек для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="5f762-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="5f762-155">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5f762-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f762-156"><strong>Сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-157">целое</span><span class="sxs-lookup"><span data-stu-id="5f762-157">int</span></span></p></td>
<td><p><span data-ttu-id="5f762-158">ИДЕНТИФИКАЦИОНный номер для идентификации запроса на сеанс, который является источником отчета об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5f762-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="5f762-159">Используется в сочетании с Сессионидтиме для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="5f762-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="5f762-160">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5f762-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f762-161"><strong>Диалогид</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-162">варстринг (775)</span><span class="sxs-lookup"><span data-stu-id="5f762-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="5f762-163">ИДЕНТИФИКАТОР диалогового окна SIP сеанса, на который поступила ошибка.</span><span class="sxs-lookup"><span data-stu-id="5f762-163">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="5f762-164">Формат:</span><span class="sxs-lookup"><span data-stu-id="5f762-164">The format is:</span></span></p>
<p><span data-ttu-id="5f762-165">диалоговое окно; тег "from-Tag"</span><span class="sxs-lookup"><span data-stu-id="5f762-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="5f762-166">Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5f762-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="5f762-167">Cast (CAST (Екстерналид AS varbinary (max)) AS varchar (max))</span><span class="sxs-lookup"><span data-stu-id="5f762-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f762-168"><strong>Клиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-169">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5f762-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f762-170">Версия клиента, используемая пользователем, который поступил с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="5f762-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f762-171"><strong>Клиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-172">целое</span><span class="sxs-lookup"><span data-stu-id="5f762-172">int</span></span></p></td>
<td><p><span data-ttu-id="5f762-173">Клиент, использованный пользователем, который поступил с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="5f762-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="5f762-174">Дополнительные сведения вы увидите <a href="lync-server-2013-useragentdef-table.md">в таблице усеражентдеф в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5f762-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f762-175"><strong>Клиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-176">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5f762-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5f762-177">Имя категории клиента, используемой пользователем, который поступил с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="5f762-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f762-178"><strong>Источник</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5f762-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f762-180">Имя сервера, отправившего ошибку (при отправке отчета из серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="5f762-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f762-181"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-182">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5f762-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f762-183">Имя приложения, которое поступило об ошибке (при отправке отчета из серверного компонента).</span><span class="sxs-lookup"><span data-stu-id="5f762-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f762-184"><strong>Респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-185">целое</span><span class="sxs-lookup"><span data-stu-id="5f762-185">int</span></span></p></td>
<td><p><span data-ttu-id="5f762-186">Код ответа SIP в сеанс сообщения SIP с отчетом об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5f762-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f762-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-188">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="5f762-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="5f762-189">Тип запроса, который завершился сбоем.</span><span class="sxs-lookup"><span data-stu-id="5f762-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f762-190"><strong>Контента</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-191">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="5f762-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="5f762-192">Тип контента запроса, который завершился сбоем.</span><span class="sxs-lookup"><span data-stu-id="5f762-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f762-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5f762-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f762-195">Тип сеанса.</span><span class="sxs-lookup"><span data-stu-id="5f762-195">Type of session.</span></span> <span data-ttu-id="5f762-196">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-calltype-table.md">таблицей каллтипе в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5f762-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f762-197"><strong>Телеметрид</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-198">идентификатора</span><span class="sxs-lookup"><span data-stu-id="5f762-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5f762-199">Уникальный идентификатор, соответствующий сведениям о времени соединения для различных компонентов, участвующих в Конференции.</span><span class="sxs-lookup"><span data-stu-id="5f762-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f762-200"><strong>Сетуптиме</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-201">целое</span><span class="sxs-lookup"><span data-stu-id="5f762-201">int</span></span></p></td>
<td><p><span data-ttu-id="5f762-202">Время (в миллисекундах), требуемое конкретным компонентом для присоединения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="5f762-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f762-203"><strong>Искаптуредбисервер</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-204">бит</span><span class="sxs-lookup"><span data-stu-id="5f762-204">bit</span></span></p></td>
<td><p><span data-ttu-id="5f762-205">Указывает, был ли отчет об ошибке записан агентом CDR, запущенным на сервере переднего плана или отправлен клиентом.</span><span class="sxs-lookup"><span data-stu-id="5f762-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f762-206"><strong>Пометка</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-207">smallint</span><span class="sxs-lookup"><span data-stu-id="5f762-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="5f762-208">Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="5f762-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f762-209"><strong>Мсдиагхеадер</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-210">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="5f762-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="5f762-211">Дополнительные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5f762-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f762-212"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="5f762-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="5f762-214">Полное доменное имя сервера переднего плана, отправившего отчет.</span><span class="sxs-lookup"><span data-stu-id="5f762-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f762-215"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="5f762-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="5f762-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="5f762-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="5f762-217">Полное доменное имя пула, содержащего сервер переднего плана, отправивший отчет.</span><span class="sxs-lookup"><span data-stu-id="5f762-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

