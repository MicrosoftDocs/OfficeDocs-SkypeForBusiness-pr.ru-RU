---
title: 'Lync Server 2013: представление SessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb7b664761aa8506b01e114366016b98637eb30e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="62e82-102">Представление SessionDetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62e82-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62e82-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="62e82-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="62e82-104">В представлении SessionDetails хранятся сведения об одноранговых сеансах, которые могут быть телефонным звонком VoIP, двусторонним сеансом обмена мгновенными сообщениями или другим типом сеансов.</span><span class="sxs-lookup"><span data-stu-id="62e82-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="62e82-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="62e82-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62e82-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="62e82-106">Column</span></span></th>
<th><span data-ttu-id="62e82-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="62e82-107">Data Type</span></span></th>
<th><span data-ttu-id="62e82-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="62e82-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62e82-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-110">datetime</span><span class="sxs-lookup"><span data-stu-id="62e82-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="62e82-111">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="62e82-111">Time of session request.</span></span> <span data-ttu-id="62e82-112">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="62e82-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="62e82-113">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в таблице Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="62e82-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-114"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-115">int</span><span class="sxs-lookup"><span data-stu-id="62e82-115">int</span></span></p></td>
<td><p><span data-ttu-id="62e82-116">Идентификационный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="62e82-116">ID number to identify the session.</span></span> <span data-ttu-id="62e82-117">Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="62e82-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="62e82-118">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="62e82-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-119"><strong>инвитетиме</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-120">datetime</span><span class="sxs-lookup"><span data-stu-id="62e82-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="62e82-p104">Время первого запроса INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO). Время первого запроса INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="62e82-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-126"><strong>фромури</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="62e82-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="62e82-128">URI пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="62e82-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-129"><strong>таури</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="62e82-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="62e82-131">URI пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="62e82-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-132"><strong>фромуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="62e82-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="62e82-134">Тип URI пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="62e82-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="62e82-135">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="62e82-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-136"><strong>тауритипе</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="62e82-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="62e82-138">Тип URI пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="62e82-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="62e82-139">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="62e82-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-140"><strong>фромтенант</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="62e82-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="62e82-142">Клиент пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="62e82-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="62e82-143">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="62e82-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-144"><strong>тотенант</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="62e82-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="62e82-146">Клиент пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="62e82-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="62e82-147">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="62e82-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-148"><strong>фромендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-149">идентификатора</span><span class="sxs-lookup"><span data-stu-id="62e82-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="62e82-150">Уникальный идентификатор конечной точки пользователя, запустившего сеанса.</span><span class="sxs-lookup"><span data-stu-id="62e82-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-151"><strong>тоендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-152">идентификатора</span><span class="sxs-lookup"><span data-stu-id="62e82-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="62e82-153">Уникальный идентификатор конечной точки пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="62e82-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-155">datetime</span><span class="sxs-lookup"><span data-stu-id="62e82-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="62e82-156">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="62e82-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-157"><strong>фроммессажекаунт</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-158">int</span><span class="sxs-lookup"><span data-stu-id="62e82-158">int</span></span></p></td>
<td><p><span data-ttu-id="62e82-159">Число сообщений, отправленных пользователем, запустившим сеанс.</span><span class="sxs-lookup"><span data-stu-id="62e82-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-160"><strong>томессажекаунт</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-161">int</span><span class="sxs-lookup"><span data-stu-id="62e82-161">int</span></span></p></td>
<td><p><span data-ttu-id="62e82-162">Число сообщений, отправленных пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="62e82-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-163"><strong>фромклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-164">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="62e82-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="62e82-165">Версия клиента пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="62e82-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-166"><strong>фромклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-167">int</span><span class="sxs-lookup"><span data-stu-id="62e82-167">int</span></span></p></td>
<td><p><span data-ttu-id="62e82-168">Версия клиента пользователя, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="62e82-168">Client used by the user who started the session.</span></span> <span data-ttu-id="62e82-169">Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="62e82-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-170"><strong>фромклиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="62e82-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="62e82-172">Имя категории клиента пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="62e82-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-173"><strong>токлиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="62e82-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="62e82-175">Версия клиента пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="62e82-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-176"><strong>токлиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-177">int</span><span class="sxs-lookup"><span data-stu-id="62e82-177">int</span></span></p></td>
<td><p><span data-ttu-id="62e82-178">Версия клиента пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="62e82-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="62e82-179">Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="62e82-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-180"><strong>токлиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="62e82-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="62e82-182">Имя категории клиента пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="62e82-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="62e82-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="62e82-185">URI целевого пользователя сеанса.</span><span class="sxs-lookup"><span data-stu-id="62e82-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-186"><strong>таржетуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="62e82-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="62e82-188">Тип URI целевого пользователя сеанса.</span><span class="sxs-lookup"><span data-stu-id="62e82-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="62e82-189">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="62e82-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-190"><strong>онбехалфофури</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="62e82-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="62e82-192">URI пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="62e82-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-193"><strong>онннбехалфофуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="62e82-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="62e82-195">Тип URI пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="62e82-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="62e82-196">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="62e82-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-197"><strong>онбехалфофтенант</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="62e82-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="62e82-199">Клиент пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="62e82-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="62e82-200">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="62e82-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-201"><strong>реферредбюри</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="62e82-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="62e82-203">URI пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="62e82-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-204"><strong>реферредбюритипе</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-205">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="62e82-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="62e82-206">Тип URI пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="62e82-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="62e82-207">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="62e82-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-208"><strong>реферредбитенант</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-209">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="62e82-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="62e82-210">Клиент пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="62e82-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="62e82-211">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="62e82-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="62e82-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="62e82-p116">Код диалога SIP. Формат:</span><span class="sxs-lookup"><span data-stu-id="62e82-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="62e82-216">диалоговое окно; from — Tag; to – Tag</span><span class="sxs-lookup"><span data-stu-id="62e82-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-217"><strong>ИД</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-218">идентификатора</span><span class="sxs-lookup"><span data-stu-id="62e82-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="62e82-219">GUID, используемый для сопоставления нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="62e82-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-220"><strong>реплацедиалогидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-221">datetime</span><span class="sxs-lookup"><span data-stu-id="62e82-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="62e82-222">Время диалога, который был заменен сеансом.</span><span class="sxs-lookup"><span data-stu-id="62e82-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="62e82-223">Используется совместно с ReplaceDialogIdSeq для уникальной идентификации диалога, который был заменен сеансом.</span><span class="sxs-lookup"><span data-stu-id="62e82-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="62e82-224">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="62e82-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-225"><strong>реплацедиалогидсек</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-226">int</span><span class="sxs-lookup"><span data-stu-id="62e82-226">int</span></span></p></td>
<td><p><span data-ttu-id="62e82-227">Идентификатор сеанса.</span><span class="sxs-lookup"><span data-stu-id="62e82-227">ID number to identify the session.</span></span> <span data-ttu-id="62e82-228">Используется совместно с параметром ReplaceDialogIdTime для уникальной идентификации диалога, который был заменен сеансом.</span><span class="sxs-lookup"><span data-stu-id="62e82-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="62e82-229">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="62e82-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-230"><strong>реплацесдиалогид</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="62e82-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="62e82-p119">Код диалога SIP, который заменяется сеансом. Формат:</span><span class="sxs-lookup"><span data-stu-id="62e82-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="62e82-234">диалоговое окно; from — Tag; to – Tag</span><span class="sxs-lookup"><span data-stu-id="62e82-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-235"><strong>респонсетиме</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-236">datetime</span><span class="sxs-lookup"><span data-stu-id="62e82-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="62e82-p120">Время ответа на первое сообщение INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="62e82-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-240"><strong>респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-241">int</span><span class="sxs-lookup"><span data-stu-id="62e82-241">int</span></span></p></td>
<td><p><span data-ttu-id="62e82-p121">Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="62e82-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-245"><strong>диагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-246">int</span><span class="sxs-lookup"><span data-stu-id="62e82-246">int</span></span></p></td>
<td><p><span data-ttu-id="62e82-247">Код диагностики из заголовков SIP.</span><span class="sxs-lookup"><span data-stu-id="62e82-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-249">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="62e82-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="62e82-250">Тип контента для этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="62e82-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-251"><strong>Интерфейса</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-252">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="62e82-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="62e82-253">Полное доменное имя интерфейсного сервера, который получил данные этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="62e82-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-254"><strong>Ресурсов</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-255">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="62e82-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="62e82-256">Полное доменное имя пула, который получил данные этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="62e82-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-257"><strong>фромеджесервер</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-258">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="62e82-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="62e82-259">Полное доменное имя пограничного сервера, применяемого пользователем, запустившим сеанс.</span><span class="sxs-lookup"><span data-stu-id="62e82-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-260"><strong>тоеджесервер</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-261">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="62e82-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="62e82-262">Полное доменное имя пограничного сервера, применяемого пользователем, запустившим сеанс</span><span class="sxs-lookup"><span data-stu-id="62e82-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-263"><strong>исфроминтернал</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-264">Битовая</span><span class="sxs-lookup"><span data-stu-id="62e82-264">bit</span></span></p></td>
<td><p><span data-ttu-id="62e82-265">Указывает, вошел ли пользователь, запустивший сеанс, в систему из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="62e82-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-266"><strong>истоинтернал</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-267">Битовая</span><span class="sxs-lookup"><span data-stu-id="62e82-267">bit</span></span></p></td>
<td><p><span data-ttu-id="62e82-268">Указывает, вошел ли пользователь, который присоединился к сеансу, в систему из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="62e82-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-269"><strong>каллприорити</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-270">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="62e82-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="62e82-271">Приоритет вызова сеанса.</span><span class="sxs-lookup"><span data-stu-id="62e82-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-272"><strong>фромусерфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-273">smallint</span><span class="sxs-lookup"><span data-stu-id="62e82-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="62e82-p122">Указывает атрибуты пользователя, начавшего сеанс. Допустимы следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="62e82-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="62e82-276">0x01 — интегрировано со стационарным телефоном</span><span class="sxs-lookup"><span data-stu-id="62e82-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-277"><strong>таусерфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-278">smallint</span><span class="sxs-lookup"><span data-stu-id="62e82-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="62e82-p123">Указывает атрибуты пользователя, начавшего сеанс. Допустимы следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="62e82-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="62e82-281">0x01 — интегрировано со стационарным телефоном</span><span class="sxs-lookup"><span data-stu-id="62e82-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e82-282"><strong>каллфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-283">smallint</span><span class="sxs-lookup"><span data-stu-id="62e82-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="62e82-p124">Указывает атрибуты вызова. Допустимы следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="62e82-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="62e82-286">0x01 — повторенный сеанс</span><span class="sxs-lookup"><span data-stu-id="62e82-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="62e82-287">0x02 — вызов, выполненный агентом от имени группы ответа</span><span class="sxs-lookup"><span data-stu-id="62e82-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e82-288"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="62e82-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="62e82-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="62e82-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="62e82-290">Расположение экстренного звонка.</span><span class="sxs-lookup"><span data-stu-id="62e82-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

