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
ms.openlocfilehash: 3f7a143a0812b19a840c7eb339e80611720a08b3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="34955-102">Представление SessionDetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34955-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34955-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="34955-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="34955-104">В представлении SessionDetails хранятся сведения об одноранговых сеансах, которые могут быть телефонным звонком VoIP, двусторонним сеансом обмена мгновенными сообщениями или другим типом сеансов.</span><span class="sxs-lookup"><span data-stu-id="34955-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="34955-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="34955-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34955-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="34955-106">Column</span></span></th>
<th><span data-ttu-id="34955-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="34955-107">Data Type</span></span></th>
<th><span data-ttu-id="34955-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="34955-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34955-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="34955-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-110">datetime</span><span class="sxs-lookup"><span data-stu-id="34955-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="34955-111">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="34955-111">Time of session request.</span></span> <span data-ttu-id="34955-112">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="34955-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="34955-113">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в таблице Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34955-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-114"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="34955-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-115">int</span><span class="sxs-lookup"><span data-stu-id="34955-115">int</span></span></p></td>
<td><p><span data-ttu-id="34955-116">Идентификационный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="34955-116">ID number to identify the session.</span></span> <span data-ttu-id="34955-117">Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="34955-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="34955-118">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34955-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-119"><strong>инвитетиме</strong></span><span class="sxs-lookup"><span data-stu-id="34955-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-120">datetime</span><span class="sxs-lookup"><span data-stu-id="34955-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="34955-p104">Время первого запроса INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO). Время первого запроса INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="34955-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-126"><strong>фромури</strong></span><span class="sxs-lookup"><span data-stu-id="34955-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="34955-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34955-128">URI пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="34955-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-129"><strong>таури</strong></span><span class="sxs-lookup"><span data-stu-id="34955-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="34955-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34955-131">URI пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="34955-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-132"><strong>фромуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="34955-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34955-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34955-134">Тип URI пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="34955-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="34955-135">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34955-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-136"><strong>тауритипе</strong></span><span class="sxs-lookup"><span data-stu-id="34955-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34955-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34955-138">Тип URI пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="34955-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="34955-139">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34955-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-140"><strong>фромтенант</strong></span><span class="sxs-lookup"><span data-stu-id="34955-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="34955-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34955-142">Клиент пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="34955-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="34955-143">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34955-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-144"><strong>тотенант</strong></span><span class="sxs-lookup"><span data-stu-id="34955-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34955-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34955-146">Клиент пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="34955-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="34955-147">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34955-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-148"><strong>фромендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="34955-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-149">идентификатора</span><span class="sxs-lookup"><span data-stu-id="34955-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="34955-150">Уникальный идентификатор конечной точки пользователя, запустившего сеанса.</span><span class="sxs-lookup"><span data-stu-id="34955-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-151"><strong>тоендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="34955-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-152">идентификатора</span><span class="sxs-lookup"><span data-stu-id="34955-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="34955-153">Уникальный идентификатор конечной точки пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="34955-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="34955-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-155">datetime</span><span class="sxs-lookup"><span data-stu-id="34955-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="34955-156">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="34955-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-157"><strong>фроммессажекаунт</strong></span><span class="sxs-lookup"><span data-stu-id="34955-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-158">int</span><span class="sxs-lookup"><span data-stu-id="34955-158">int</span></span></p></td>
<td><p><span data-ttu-id="34955-159">Число сообщений, отправленных пользователем, запустившим сеанс.</span><span class="sxs-lookup"><span data-stu-id="34955-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-160"><strong>томессажекаунт</strong></span><span class="sxs-lookup"><span data-stu-id="34955-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-161">int</span><span class="sxs-lookup"><span data-stu-id="34955-161">int</span></span></p></td>
<td><p><span data-ttu-id="34955-162">Число сообщений, отправленных пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="34955-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-163"><strong>фромклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="34955-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-164">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34955-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34955-165">Версия клиента пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="34955-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-166"><strong>фромклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="34955-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-167">int</span><span class="sxs-lookup"><span data-stu-id="34955-167">int</span></span></p></td>
<td><p><span data-ttu-id="34955-168">Версия клиента пользователя, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="34955-168">Client used by the user who started the session.</span></span> <span data-ttu-id="34955-169">Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34955-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-170"><strong>фромклиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="34955-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="34955-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="34955-172">Имя категории клиента пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="34955-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-173"><strong>токлиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="34955-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34955-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34955-175">Версия клиента пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="34955-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-176"><strong>токлиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="34955-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-177">int</span><span class="sxs-lookup"><span data-stu-id="34955-177">int</span></span></p></td>
<td><p><span data-ttu-id="34955-178">Версия клиента пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="34955-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="34955-179">Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34955-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-180"><strong>токлиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="34955-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="34955-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="34955-182">Имя категории клиента пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="34955-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="34955-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="34955-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34955-185">URI целевого пользователя сеанса.</span><span class="sxs-lookup"><span data-stu-id="34955-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-186"><strong>таржетуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="34955-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="34955-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34955-188">Тип URI целевого пользователя сеанса.</span><span class="sxs-lookup"><span data-stu-id="34955-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="34955-189">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34955-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-190"><strong>онбехалфофури</strong></span><span class="sxs-lookup"><span data-stu-id="34955-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="34955-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34955-192">URI пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="34955-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-193"><strong>онннбехалфофуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="34955-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34955-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34955-195">Тип URI пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="34955-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="34955-196">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34955-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-197"><strong>онбехалфофтенант</strong></span><span class="sxs-lookup"><span data-stu-id="34955-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34955-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34955-199">Клиент пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="34955-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="34955-200">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34955-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-201"><strong>реферредбюри</strong></span><span class="sxs-lookup"><span data-stu-id="34955-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="34955-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34955-203">URI пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="34955-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-204"><strong>реферредбюритипе</strong></span><span class="sxs-lookup"><span data-stu-id="34955-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-205">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34955-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34955-206">Тип URI пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="34955-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="34955-207">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34955-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-208"><strong>реферредбитенант</strong></span><span class="sxs-lookup"><span data-stu-id="34955-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-209">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34955-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34955-210">Клиент пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="34955-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="34955-211">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34955-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="34955-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="34955-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="34955-p116">Код диалога SIP. Формат:</span><span class="sxs-lookup"><span data-stu-id="34955-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="34955-216">диалоговое окно; from — Tag; to – Tag</span><span class="sxs-lookup"><span data-stu-id="34955-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-217"><strong>ИД</strong></span><span class="sxs-lookup"><span data-stu-id="34955-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-218">идентификатора</span><span class="sxs-lookup"><span data-stu-id="34955-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="34955-219">GUID, используемый для сопоставления нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="34955-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-220"><strong>реплацедиалогидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="34955-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-221">datetime</span><span class="sxs-lookup"><span data-stu-id="34955-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="34955-222">Время диалога, который был заменен сеансом.</span><span class="sxs-lookup"><span data-stu-id="34955-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="34955-223">Используется совместно с ReplaceDialogIdSeq для уникальной идентификации диалога, который был заменен сеансом.</span><span class="sxs-lookup"><span data-stu-id="34955-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="34955-224">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34955-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-225"><strong>реплацедиалогидсек</strong></span><span class="sxs-lookup"><span data-stu-id="34955-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-226">int</span><span class="sxs-lookup"><span data-stu-id="34955-226">int</span></span></p></td>
<td><p><span data-ttu-id="34955-227">Идентификатор сеанса.</span><span class="sxs-lookup"><span data-stu-id="34955-227">ID number to identify the session.</span></span> <span data-ttu-id="34955-228">Используется совместно с параметром ReplaceDialogIdTime для уникальной идентификации диалога, который был заменен сеансом.</span><span class="sxs-lookup"><span data-stu-id="34955-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="34955-229">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34955-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-230"><strong>реплацесдиалогид</strong></span><span class="sxs-lookup"><span data-stu-id="34955-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="34955-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="34955-p119">Код диалога SIP, который заменяется сеансом. Формат:</span><span class="sxs-lookup"><span data-stu-id="34955-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="34955-234">диалоговое окно; from — Tag; to – Tag</span><span class="sxs-lookup"><span data-stu-id="34955-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-235"><strong>респонсетиме</strong></span><span class="sxs-lookup"><span data-stu-id="34955-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-236">datetime</span><span class="sxs-lookup"><span data-stu-id="34955-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="34955-p120">Время ответа на первое сообщение INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="34955-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-240"><strong>респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="34955-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-241">int</span><span class="sxs-lookup"><span data-stu-id="34955-241">int</span></span></p></td>
<td><p><span data-ttu-id="34955-p121">Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="34955-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-245"><strong>диагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="34955-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-246">int</span><span class="sxs-lookup"><span data-stu-id="34955-246">int</span></span></p></td>
<td><p><span data-ttu-id="34955-247">Код диагностики из заголовков SIP.</span><span class="sxs-lookup"><span data-stu-id="34955-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="34955-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-249">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34955-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34955-250">Тип контента для этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="34955-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-251"><strong>Интерфейса</strong></span><span class="sxs-lookup"><span data-stu-id="34955-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-252">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34955-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34955-253">Полное доменное имя интерфейсного сервера, который получил данные этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="34955-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-254"><strong>Ресурсов</strong></span><span class="sxs-lookup"><span data-stu-id="34955-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-255">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34955-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34955-256">Полное доменное имя пула, который получил данные этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="34955-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-257"><strong>фромеджесервер</strong></span><span class="sxs-lookup"><span data-stu-id="34955-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-258">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34955-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34955-259">Полное доменное имя пограничного сервера, применяемого пользователем, запустившим сеанс.</span><span class="sxs-lookup"><span data-stu-id="34955-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-260"><strong>тоеджесервер</strong></span><span class="sxs-lookup"><span data-stu-id="34955-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-261">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34955-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34955-262">Полное доменное имя пограничного сервера, применяемого пользователем, запустившим сеанс</span><span class="sxs-lookup"><span data-stu-id="34955-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-263"><strong>исфроминтернал</strong></span><span class="sxs-lookup"><span data-stu-id="34955-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-264">Битовая</span><span class="sxs-lookup"><span data-stu-id="34955-264">bit</span></span></p></td>
<td><p><span data-ttu-id="34955-265">Указывает, вошел ли пользователь, запустивший сеанс, в систему из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="34955-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-266"><strong>истоинтернал</strong></span><span class="sxs-lookup"><span data-stu-id="34955-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-267">Битовая</span><span class="sxs-lookup"><span data-stu-id="34955-267">bit</span></span></p></td>
<td><p><span data-ttu-id="34955-268">Указывает, вошел ли пользователь, который присоединился к сеансу, в систему из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="34955-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-269"><strong>каллприорити</strong></span><span class="sxs-lookup"><span data-stu-id="34955-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-270">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34955-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34955-271">Приоритет вызова сеанса.</span><span class="sxs-lookup"><span data-stu-id="34955-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-272"><strong>фромусерфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="34955-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-273">smallint</span><span class="sxs-lookup"><span data-stu-id="34955-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="34955-p122">Указывает атрибуты пользователя, начавшего сеанс. Допустимы следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="34955-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="34955-276">0x01 — интегрировано со стационарным телефоном</span><span class="sxs-lookup"><span data-stu-id="34955-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-277"><strong>таусерфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="34955-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-278">smallint</span><span class="sxs-lookup"><span data-stu-id="34955-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="34955-p123">Указывает атрибуты пользователя, начавшего сеанс. Допустимы следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="34955-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="34955-281">0x01 — интегрировано со стационарным телефоном</span><span class="sxs-lookup"><span data-stu-id="34955-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34955-282"><strong>каллфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="34955-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-283">smallint</span><span class="sxs-lookup"><span data-stu-id="34955-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="34955-p124">Указывает атрибуты вызова. Допустимы следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="34955-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="34955-286">0x01 — повторенный сеанс</span><span class="sxs-lookup"><span data-stu-id="34955-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="34955-287">0x02 — вызов, выполненный агентом от имени группы ответа</span><span class="sxs-lookup"><span data-stu-id="34955-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34955-288"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="34955-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="34955-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="34955-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="34955-290">Расположение экстренного звонка.</span><span class="sxs-lookup"><span data-stu-id="34955-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

