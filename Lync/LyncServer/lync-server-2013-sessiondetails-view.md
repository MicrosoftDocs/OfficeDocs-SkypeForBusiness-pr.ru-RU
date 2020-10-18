---
title: 'Lync Server 2013: представление SessionDetails'
description: 'Lync Server 2013: представление SessionDetails.'
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
ms.openlocfilehash: 4c9f657257e54389defb805919be61adbdecad74
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573245"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="051ec-103">Представление SessionDetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="051ec-103">SessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="051ec-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="051ec-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="051ec-105">В представлении SessionDetails хранятся сведения об одноранговых сеансах, которые могут быть VoIP-VoIP телефонным звонком, двусторонним сеансом обмена мгновенными сообщениями или другими типами сеансов.</span><span class="sxs-lookup"><span data-stu-id="051ec-105">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="051ec-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="051ec-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="051ec-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="051ec-107">Column</span></span></th>
<th><span data-ttu-id="051ec-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="051ec-108">Data Type</span></span></th>
<th><span data-ttu-id="051ec-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="051ec-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="051ec-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-111">datetime</span><span class="sxs-lookup"><span data-stu-id="051ec-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="051ec-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="051ec-112">Time of session request.</span></span> <span data-ttu-id="051ec-113">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="051ec-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="051ec-114">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в таблице Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="051ec-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-115"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-116">int</span><span class="sxs-lookup"><span data-stu-id="051ec-116">int</span></span></p></td>
<td><p><span data-ttu-id="051ec-117">Идентификационный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="051ec-117">ID number to identify the session.</span></span> <span data-ttu-id="051ec-118">Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="051ec-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="051ec-119">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="051ec-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-120"><strong>инвитетиме</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-121">datetime</span><span class="sxs-lookup"><span data-stu-id="051ec-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="051ec-p104">Время первого запроса INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO). Время первого запроса INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="051ec-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-127"><strong>фромури</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-127"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="051ec-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="051ec-129">URI пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="051ec-129">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-130"><strong>таури</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-130"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-131">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="051ec-131">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="051ec-132">URI пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="051ec-132">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-133"><strong>фромуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-133"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="051ec-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="051ec-135">Тип URI пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="051ec-135">Type of URI of the user who started the session.</span></span> <span data-ttu-id="051ec-136">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="051ec-136">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-137"><strong>тауритипе</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-138">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="051ec-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="051ec-139">Тип URI пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="051ec-139">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="051ec-140">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="051ec-140">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-141"><strong>фромтенант</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-141"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="051ec-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="051ec-143">Клиент пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="051ec-143">Tenant of the user who started the session.</span></span> <span data-ttu-id="051ec-144">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="051ec-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-145"><strong>тотенант</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-145"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="051ec-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="051ec-147">Клиент пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="051ec-147">The tenant of the user who joined the session.</span></span> <span data-ttu-id="051ec-148">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="051ec-148">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-149"><strong>фромендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-149"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-150">идентификатора</span><span class="sxs-lookup"><span data-stu-id="051ec-150">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="051ec-151">Уникальный идентификатор конечной точки пользователя, запустившего сеанса.</span><span class="sxs-lookup"><span data-stu-id="051ec-151">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-152"><strong>тоендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-152"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-153">идентификатора</span><span class="sxs-lookup"><span data-stu-id="051ec-153">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="051ec-154">Уникальный идентификатор конечной точки пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="051ec-154">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-155"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-155"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-156">datetime</span><span class="sxs-lookup"><span data-stu-id="051ec-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="051ec-157">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="051ec-157">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-158"><strong>фроммессажекаунт</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-158"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-159">int</span><span class="sxs-lookup"><span data-stu-id="051ec-159">int</span></span></p></td>
<td><p><span data-ttu-id="051ec-160">Число сообщений, отправленных пользователем, запустившим сеанс.</span><span class="sxs-lookup"><span data-stu-id="051ec-160">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-161"><strong>томессажекаунт</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-161"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-162">int</span><span class="sxs-lookup"><span data-stu-id="051ec-162">int</span></span></p></td>
<td><p><span data-ttu-id="051ec-163">Число сообщений, отправленных пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="051ec-163">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-164"><strong>фромклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-164"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="051ec-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="051ec-166">Версия клиента пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="051ec-166">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-167"><strong>фромклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-167"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-168">int</span><span class="sxs-lookup"><span data-stu-id="051ec-168">int</span></span></p></td>
<td><p><span data-ttu-id="051ec-169">Версия клиента пользователя, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="051ec-169">Client used by the user who started the session.</span></span> <span data-ttu-id="051ec-170">Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="051ec-170">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-171"><strong>фромклиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-171"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="051ec-172">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="051ec-173">Имя категории клиента пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="051ec-173">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-174"><strong>токлиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-174"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-175">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="051ec-175">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="051ec-176">Версия клиента пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="051ec-176">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-177"><strong>токлиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-177"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-178">int</span><span class="sxs-lookup"><span data-stu-id="051ec-178">int</span></span></p></td>
<td><p><span data-ttu-id="051ec-179">Версия клиента пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="051ec-179">Client used by the user who joined the session.</span></span> <span data-ttu-id="051ec-180">Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="051ec-180">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-181"><strong>токлиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-181"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-182">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="051ec-182">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="051ec-183">Имя категории клиента пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="051ec-183">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-184"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-184"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-185">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="051ec-185">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="051ec-186">URI целевого пользователя сеанса.</span><span class="sxs-lookup"><span data-stu-id="051ec-186">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-187"><strong>таржетуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-187"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-188">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="051ec-188">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="051ec-189">Тип URI целевого пользователя сеанса.</span><span class="sxs-lookup"><span data-stu-id="051ec-189">Type of URI of the target user for the session.</span></span> <span data-ttu-id="051ec-190">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="051ec-190">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-191"><strong>онбехалфофури</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-191"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="051ec-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="051ec-193">URI пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="051ec-193">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-194"><strong>онннбехалфофуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-194"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="051ec-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="051ec-196">Тип URI пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="051ec-196">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="051ec-197">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="051ec-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-198"><strong>онбехалфофтенант</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-198"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="051ec-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="051ec-200">Клиент пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="051ec-200">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="051ec-201">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="051ec-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-202"><strong>реферредбюри</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-202"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-203">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="051ec-203">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="051ec-204">URI пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="051ec-204">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-205"><strong>реферредбюритипе</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-205"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-206">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="051ec-206">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="051ec-207">Тип URI пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="051ec-207">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="051ec-208">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="051ec-208">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-209"><strong>реферредбитенант</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-209"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-210">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="051ec-210">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="051ec-211">Клиент пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="051ec-211">Tenant of the user who referred the session.</span></span> <span data-ttu-id="051ec-212">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="051ec-212">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-213"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-213"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-214">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="051ec-214">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="051ec-p116">Код диалога SIP. Формат:</span><span class="sxs-lookup"><span data-stu-id="051ec-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="051ec-217">диалоговое окно; from — Tag; to – Tag</span><span class="sxs-lookup"><span data-stu-id="051ec-217">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-218"><strong>ИД</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-218"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-219">идентификатора</span><span class="sxs-lookup"><span data-stu-id="051ec-219">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="051ec-220">GUID, используемый для сопоставления нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="051ec-220">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-221"><strong>реплацедиалогидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-221"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-222">datetime</span><span class="sxs-lookup"><span data-stu-id="051ec-222">datetime</span></span></p></td>
<td><p><span data-ttu-id="051ec-223">Время диалога, который был заменен сеансом.</span><span class="sxs-lookup"><span data-stu-id="051ec-223">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="051ec-224">Используется совместно с ReplaceDialogIdSeq для уникальной идентификации диалога, который был заменен сеансом.</span><span class="sxs-lookup"><span data-stu-id="051ec-224">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="051ec-225">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="051ec-225">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-226"><strong>реплацедиалогидсек</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-226"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-227">int</span><span class="sxs-lookup"><span data-stu-id="051ec-227">int</span></span></p></td>
<td><p><span data-ttu-id="051ec-228">Идентификатор сеанса.</span><span class="sxs-lookup"><span data-stu-id="051ec-228">ID number to identify the session.</span></span> <span data-ttu-id="051ec-229">Используется совместно с параметром ReplaceDialogIdTime для уникальной идентификации диалога, который был заменен сеансом.</span><span class="sxs-lookup"><span data-stu-id="051ec-229">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="051ec-230">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="051ec-230">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-231"><strong>реплацесдиалогид</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-231"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-232">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="051ec-232">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="051ec-p119">Код диалога SIP, который заменяется сеансом. Формат:</span><span class="sxs-lookup"><span data-stu-id="051ec-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="051ec-235">диалоговое окно; from — Tag; to – Tag</span><span class="sxs-lookup"><span data-stu-id="051ec-235">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-236"><strong>респонсетиме</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-236"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-237">datetime</span><span class="sxs-lookup"><span data-stu-id="051ec-237">datetime</span></span></p></td>
<td><p><span data-ttu-id="051ec-p120">Время ответа на первое сообщение INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="051ec-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-241"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-241"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-242">int</span><span class="sxs-lookup"><span data-stu-id="051ec-242">int</span></span></p></td>
<td><p><span data-ttu-id="051ec-p121">Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="051ec-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-246"><strong>диагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-246"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-247">int</span><span class="sxs-lookup"><span data-stu-id="051ec-247">int</span></span></p></td>
<td><p><span data-ttu-id="051ec-248">Код диагностики из заголовков SIP.</span><span class="sxs-lookup"><span data-stu-id="051ec-248">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-249"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-249"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="051ec-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="051ec-251">Тип контента для этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="051ec-251">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-252"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-252"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="051ec-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="051ec-254">Полное доменное имя интерфейсного сервера, который получил данные этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="051ec-254">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-255"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-255"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="051ec-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="051ec-257">Полное доменное имя пула, который получил данные этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="051ec-257">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-258"><strong>фромеджесервер</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-258"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="051ec-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="051ec-260">Полное доменное имя пограничного сервера, применяемого пользователем, запустившим сеанс.</span><span class="sxs-lookup"><span data-stu-id="051ec-260">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-261"><strong>тоеджесервер</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-261"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-262">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="051ec-262">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="051ec-263">Полное доменное имя пограничного сервера, применяемого пользователем, запустившим сеанс</span><span class="sxs-lookup"><span data-stu-id="051ec-263">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-264"><strong>исфроминтернал</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-264"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-265">Битовая</span><span class="sxs-lookup"><span data-stu-id="051ec-265">bit</span></span></p></td>
<td><p><span data-ttu-id="051ec-266">Указывает, вошел ли пользователь, запустивший сеанс, в систему из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="051ec-266">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-267"><strong>истоинтернал</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-267"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-268">Битовая</span><span class="sxs-lookup"><span data-stu-id="051ec-268">bit</span></span></p></td>
<td><p><span data-ttu-id="051ec-269">Указывает, вошел ли пользователь, который присоединился к сеансу, в систему из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="051ec-269">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-270"><strong>каллприорити</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-270"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-271">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="051ec-271">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="051ec-272">Приоритет вызова сеанса.</span><span class="sxs-lookup"><span data-stu-id="051ec-272">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-273"><strong>фромусерфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-273"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-274">smallint</span><span class="sxs-lookup"><span data-stu-id="051ec-274">smallint</span></span></p></td>
<td><p><span data-ttu-id="051ec-p122">Указывает атрибуты пользователя, начавшего сеанс. Допустимы следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="051ec-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="051ec-277">0x01 — интегрировано со стационарным телефоном</span><span class="sxs-lookup"><span data-stu-id="051ec-277">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-278"><strong>таусерфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-278"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-279">smallint</span><span class="sxs-lookup"><span data-stu-id="051ec-279">smallint</span></span></p></td>
<td><p><span data-ttu-id="051ec-p123">Указывает атрибуты пользователя, начавшего сеанс. Допустимы следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="051ec-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="051ec-282">0x01 — интегрировано со стационарным телефоном</span><span class="sxs-lookup"><span data-stu-id="051ec-282">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="051ec-283"><strong>каллфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-283"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-284">smallint</span><span class="sxs-lookup"><span data-stu-id="051ec-284">smallint</span></span></p></td>
<td><p><span data-ttu-id="051ec-p124">Указывает атрибуты вызова. Допустимы следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="051ec-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="051ec-287">0x01 — повторенный сеанс</span><span class="sxs-lookup"><span data-stu-id="051ec-287">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="051ec-288">0x02 — вызов, выполненный агентом от имени группы ответа</span><span class="sxs-lookup"><span data-stu-id="051ec-288">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="051ec-289"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="051ec-289"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="051ec-290">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="051ec-290">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="051ec-291">Расположение экстренного звонка.</span><span class="sxs-lookup"><span data-stu-id="051ec-291">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

