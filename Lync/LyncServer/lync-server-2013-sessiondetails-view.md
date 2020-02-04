---
title: 'Lync Server 2013: представление Сессиондетаилс'
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
ms.openlocfilehash: fabf7ae963240f6a2b14ac8c3db272e0cb06091c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="74ba5-102">Сессиондетаилс представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74ba5-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74ba5-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="74ba5-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="74ba5-104">В представлении Сессиондетаилс хранятся сведения о одноранговых сеансах, которые могут быть телефонным звонком VoIP-VoIP, сеансом обмена мгновенными сообщениями с двумя субъектами или сеансом другого типа.</span><span class="sxs-lookup"><span data-stu-id="74ba5-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="74ba5-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74ba5-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74ba5-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="74ba5-106">Column</span></span></th>
<th><span data-ttu-id="74ba5-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="74ba5-107">Data Type</span></span></th>
<th><span data-ttu-id="74ba5-108">Подробности</span><span class="sxs-lookup"><span data-stu-id="74ba5-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-110">datetime</span><span class="sxs-lookup"><span data-stu-id="74ba5-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="74ba5-111">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="74ba5-111">Time of session request.</span></span> <span data-ttu-id="74ba5-112">Используется в сочетании с Сессионидсек для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="74ba5-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="74ba5-113">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна в таблице Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="74ba5-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-114"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-115">целое</span><span class="sxs-lookup"><span data-stu-id="74ba5-115">int</span></span></p></td>
<td><p><span data-ttu-id="74ba5-116">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="74ba5-116">ID number to identify the session.</span></span> <span data-ttu-id="74ba5-117">Используется в сочетании с Сессионидтиме для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="74ba5-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="74ba5-118">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="74ba5-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-119"><strong>инвитетиме</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-120">datetime</span><span class="sxs-lookup"><span data-stu-id="74ba5-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="74ba5-121">Время первого запроса приглашения.</span><span class="sxs-lookup"><span data-stu-id="74ba5-121">Time of the first INVITE request.</span></span> <span data-ttu-id="74ba5-122">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="74ba5-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="74ba5-123">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="74ba5-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="74ba5-124">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="74ba5-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="74ba5-125">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="74ba5-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-126"><strong>фромури</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="74ba5-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-128">URI пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-129"><strong>таури</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="74ba5-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-131">Универсальный код ресурса (URI) пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="74ba5-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-132"><strong>фромуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="74ba5-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-134">Тип URI пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="74ba5-135">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="74ba5-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-136"><strong>тауритипе</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="74ba5-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-138">Тип URI пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="74ba5-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="74ba5-139">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="74ba5-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-140"><strong>фромтенант</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="74ba5-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-142">Клиент пользователя, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="74ba5-143">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="74ba5-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-144"><strong>тотенант</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-145">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="74ba5-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-146">Клиент пользователя, который присоединил сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="74ba5-147">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="74ba5-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-148"><strong>фромендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-149">идентификатора</span><span class="sxs-lookup"><span data-stu-id="74ba5-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="74ba5-150">Уникальный идентификатор конечной точки пользователя, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-151"><strong>тоендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-152">идентификатора</span><span class="sxs-lookup"><span data-stu-id="74ba5-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="74ba5-153">Уникальный идентификатор конечной точки пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="74ba5-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-155">datetime</span><span class="sxs-lookup"><span data-stu-id="74ba5-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="74ba5-156">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="74ba5-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-157"><strong>фроммессажекаунт</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-158">целое</span><span class="sxs-lookup"><span data-stu-id="74ba5-158">int</span></span></p></td>
<td><p><span data-ttu-id="74ba5-159">Количество сообщений, отправленных пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-160"><strong>томессажекаунт</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-161">целое</span><span class="sxs-lookup"><span data-stu-id="74ba5-161">int</span></span></p></td>
<td><p><span data-ttu-id="74ba5-162">Количество сообщений, отправленных пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="74ba5-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-163"><strong>фромклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-164">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="74ba5-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-165">Версия клиента, используемая пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-166"><strong>фромклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-167">целое</span><span class="sxs-lookup"><span data-stu-id="74ba5-167">int</span></span></p></td>
<td><p><span data-ttu-id="74ba5-168">Клиент, используемый пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-168">Client used by the user who started the session.</span></span> <span data-ttu-id="74ba5-169">Дополнительные сведения вы увидите <a href="lync-server-2013-useragentdef-table.md">в таблице усеражентдеф в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="74ba5-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-170"><strong>фромклиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="74ba5-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-172">Имя категории клиента, используемой пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-173"><strong>токлиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-174">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="74ba5-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-175">Версия клиента, используемая пользователем, который присоединился к сеансу</span><span class="sxs-lookup"><span data-stu-id="74ba5-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-176"><strong>токлиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-177">целое</span><span class="sxs-lookup"><span data-stu-id="74ba5-177">int</span></span></p></td>
<td><p><span data-ttu-id="74ba5-178">Клиент, используемый пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="74ba5-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="74ba5-179">Дополнительные сведения вы увидите <a href="lync-server-2013-useragentdef-table.md">в таблице усеражентдеф в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="74ba5-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-180"><strong>токлиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="74ba5-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-182">Имя категории клиента, используемой пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="74ba5-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-183"><strong>таржетури</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="74ba5-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-185">Универсальный код ресурса (URI) целевого пользователя сеанса.</span><span class="sxs-lookup"><span data-stu-id="74ba5-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-186"><strong>таржетуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="74ba5-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-188">Тип универсального кода ресурса (URI) целевого пользователя для сеанса.</span><span class="sxs-lookup"><span data-stu-id="74ba5-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="74ba5-189">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="74ba5-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-190"><strong>онбехалфофури</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="74ba5-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-192">Универсальный код ресурса (URI) пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-193"><strong>онннбехалфофуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="74ba5-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-195">Тип универсального кода ресурса (URI) пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="74ba5-196">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="74ba5-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-197"><strong>онбехалфофтенант</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="74ba5-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-199">Клиент пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="74ba5-200">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="74ba5-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-201"><strong>реферредбюри</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="74ba5-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-203">URI пользователя, который ссылался на сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-204"><strong>реферредбюритипе</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-205">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="74ba5-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-206">Тип URI пользователя, который ссылался на сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="74ba5-207">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="74ba5-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-208"><strong>реферредбитенант</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-209">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="74ba5-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-210">Клиент пользователя, который ссылался на сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="74ba5-211">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="74ba5-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-212"><strong>диалогид</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="74ba5-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-214">ИДЕНТИФИКАТОР диалогового окна SIP.</span><span class="sxs-lookup"><span data-stu-id="74ba5-214">SIP dialog ID.</span></span> <span data-ttu-id="74ba5-215">Формат:</span><span class="sxs-lookup"><span data-stu-id="74ba5-215">The format is:</span></span></p>
<p><span data-ttu-id="74ba5-216">диалоговое окно; тег "from-Tag"</span><span class="sxs-lookup"><span data-stu-id="74ba5-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-217"><strong>Корреляци</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-218">идентификатора</span><span class="sxs-lookup"><span data-stu-id="74ba5-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="74ba5-219">GUID, используемый для корреляции нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="74ba5-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-220"><strong>реплацедиалогидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-221">datetime</span><span class="sxs-lookup"><span data-stu-id="74ba5-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="74ba5-222">Время, когда диалоговое окно было заменено сеансом.</span><span class="sxs-lookup"><span data-stu-id="74ba5-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="74ba5-223">Используется в сочетании с Реплацедиалогидсек для уникальной идентификации диалогового окна, которое заменяется сеансом.</span><span class="sxs-lookup"><span data-stu-id="74ba5-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="74ba5-224">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="74ba5-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-225"><strong>реплацедиалогидсек</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-226">целое</span><span class="sxs-lookup"><span data-stu-id="74ba5-226">int</span></span></p></td>
<td><p><span data-ttu-id="74ba5-227">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="74ba5-227">ID number to identify the session.</span></span> <span data-ttu-id="74ba5-228">Используется в сочетании с Реплацедиалогидтиме для уникальной идентификации диалогового окна, которое заменяется сеансом.</span><span class="sxs-lookup"><span data-stu-id="74ba5-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="74ba5-229">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="74ba5-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-230"><strong>реплацесдиалогид</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="74ba5-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-232">ИДЕНТИФИКАТОР диалогового окна SIP, в котором будет заменяться сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="74ba5-233">Формат:</span><span class="sxs-lookup"><span data-stu-id="74ba5-233">The format is:</span></span></p>
<p><span data-ttu-id="74ba5-234">диалоговое окно; тег "from-Tag"</span><span class="sxs-lookup"><span data-stu-id="74ba5-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-235"><strong>респонсетиме</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-236">datetime</span><span class="sxs-lookup"><span data-stu-id="74ba5-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="74ba5-237">Время ответа на первое сообщение приглашения.</span><span class="sxs-lookup"><span data-stu-id="74ba5-237">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="74ba5-238">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="74ba5-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="74ba5-239">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="74ba5-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-240"><strong>респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-241">целое</span><span class="sxs-lookup"><span data-stu-id="74ba5-241">int</span></span></p></td>
<td><p><span data-ttu-id="74ba5-242">Код ответа SIP на приглашение на сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-242">SIP response code to the session invitation.</span></span> <span data-ttu-id="74ba5-243">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="74ba5-243">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="74ba5-244">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="74ba5-244">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-245"><strong>диагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-246">целое</span><span class="sxs-lookup"><span data-stu-id="74ba5-246">int</span></span></p></td>
<td><p><span data-ttu-id="74ba5-247">Идентификатор диагностики, полученный из заголовков SIP.</span><span class="sxs-lookup"><span data-stu-id="74ba5-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-248"><strong>Контента</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-249">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="74ba5-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-250">Тип контента для сеанса.</span><span class="sxs-lookup"><span data-stu-id="74ba5-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-252">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="74ba5-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-253">Полное доменное имя сервера переднего плана, который захватил данные для сеанса.</span><span class="sxs-lookup"><span data-stu-id="74ba5-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-255">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="74ba5-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-256">Полное доменное имя пула, который захватывает данные для сеанса.</span><span class="sxs-lookup"><span data-stu-id="74ba5-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-257"><strong>фромеджесервер</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-258">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="74ba5-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-259">Полное доменное имя пограничного сервера, используемое пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-260"><strong>тоеджесервер</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-261">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="74ba5-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-262">Полное доменное имя пограничного сервера, используемое пользователем, который запустил сеанс</span><span class="sxs-lookup"><span data-stu-id="74ba5-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-263"><strong>исфроминтернал</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-264">бит</span><span class="sxs-lookup"><span data-stu-id="74ba5-264">bit</span></span></p></td>
<td><p><span data-ttu-id="74ba5-265">Указывает, вошел ли пользователь, запустивший сеанс, с помощью внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="74ba5-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-266"><strong>истоинтернал</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-267">бит</span><span class="sxs-lookup"><span data-stu-id="74ba5-267">bit</span></span></p></td>
<td><p><span data-ttu-id="74ba5-268">Указывает, вошел ли пользователь, который присоединился к сеансу, из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="74ba5-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-269"><strong>каллприорити</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-270">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="74ba5-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-271">Приоритет звонка для сеанса.</span><span class="sxs-lookup"><span data-stu-id="74ba5-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-272"><strong>фромусерфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-273">smallint</span><span class="sxs-lookup"><span data-stu-id="74ba5-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="74ba5-274">Указывает атрибуты пользователя, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="74ba5-275">Допустимы следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="74ba5-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="74ba5-276">0x01 — интеграция с настольным телефоном</span><span class="sxs-lookup"><span data-stu-id="74ba5-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-277"><strong>таусерфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-278">smallint</span><span class="sxs-lookup"><span data-stu-id="74ba5-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="74ba5-279">Указывает атрибуты пользователя, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="74ba5-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="74ba5-280">Допустимы следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="74ba5-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="74ba5-281">0x01 — интеграция с настольным телефоном</span><span class="sxs-lookup"><span data-stu-id="74ba5-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba5-282"><strong>каллфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-283">smallint</span><span class="sxs-lookup"><span data-stu-id="74ba5-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="74ba5-284">Указывает атрибуты вызова.</span><span class="sxs-lookup"><span data-stu-id="74ba5-284">Indicates the call attributes.</span></span> <span data-ttu-id="74ba5-285">Допустимы следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="74ba5-285">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="74ba5-286">0x01 — сеанс повторной попытки</span><span class="sxs-lookup"><span data-stu-id="74ba5-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="74ba5-287">0x02 — вызов, сделанный агентом от имени группы ответа</span><span class="sxs-lookup"><span data-stu-id="74ba5-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba5-288"><strong>Расположение</strong></span><span class="sxs-lookup"><span data-stu-id="74ba5-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="74ba5-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="74ba5-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="74ba5-290">Место вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="74ba5-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

