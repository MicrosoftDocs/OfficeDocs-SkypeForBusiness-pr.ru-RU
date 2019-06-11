---
title: 'Lync Server 2013: представление Сессиондетаилс'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd3902fd35679366e905c04e99ff1e72b2ece86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="1dd89-102">Сессиондетаилс представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1dd89-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dd89-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="1dd89-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="1dd89-104">В представлении Сессиондетаилс хранятся сведения о одноранговых сеансах, которые могут быть телефонным звонком VoIP-VoIP, сеансом обмена мгновенными сообщениями с двумя субъектами или сеансом другого типа.</span><span class="sxs-lookup"><span data-stu-id="1dd89-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="1dd89-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1dd89-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dd89-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="1dd89-106">Column</span></span></th>
<th><span data-ttu-id="1dd89-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="1dd89-107">Data Type</span></span></th>
<th><span data-ttu-id="1dd89-108">Подробности</span><span class="sxs-lookup"><span data-stu-id="1dd89-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-109"><strong>Сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-110">datetime</span><span class="sxs-lookup"><span data-stu-id="1dd89-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="1dd89-111">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="1dd89-111">Time of session request.</span></span> <span data-ttu-id="1dd89-112">Используется в сочетании с Сессионидсек для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="1dd89-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="1dd89-113">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна в таблице Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1dd89-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-114"><strong>Сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-115">целое</span><span class="sxs-lookup"><span data-stu-id="1dd89-115">int</span></span></p></td>
<td><p><span data-ttu-id="1dd89-116">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="1dd89-116">ID number to identify the session.</span></span> <span data-ttu-id="1dd89-117">Используется в сочетании с Сессионидтиме для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="1dd89-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="1dd89-118">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1dd89-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-119"><strong>Инвитетиме</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-120">datetime</span><span class="sxs-lookup"><span data-stu-id="1dd89-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="1dd89-121">Время первого запроса приглашения.</span><span class="sxs-lookup"><span data-stu-id="1dd89-121">Time of the first INVITE request.</span></span> <span data-ttu-id="1dd89-122">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="1dd89-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="1dd89-123">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="1dd89-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="1dd89-124">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="1dd89-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="1dd89-125">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="1dd89-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-126"><strong>Фромури</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1dd89-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-128">URI пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-129"><strong>Таури</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1dd89-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-131">Универсальный код ресурса (URI) пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="1dd89-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-132"><strong>Фромуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1dd89-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-134">Тип URI пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="1dd89-135">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1dd89-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-136"><strong>Тауритипе</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1dd89-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-138">Тип URI пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="1dd89-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="1dd89-139">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1dd89-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-140"><strong>Фромтенант</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1dd89-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-142">Клиент пользователя, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="1dd89-143">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1dd89-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-144"><strong>Тотенант</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-145">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1dd89-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-146">Клиент пользователя, который присоединил сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="1dd89-147">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1dd89-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-148"><strong>Фромендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-149">идентификатора</span><span class="sxs-lookup"><span data-stu-id="1dd89-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="1dd89-150">Уникальный идентификатор конечной точки пользователя, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-151"><strong>Тоендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-152">идентификатора</span><span class="sxs-lookup"><span data-stu-id="1dd89-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="1dd89-153">Уникальный идентификатор конечной точки пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="1dd89-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-155">datetime</span><span class="sxs-lookup"><span data-stu-id="1dd89-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="1dd89-156">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="1dd89-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-157"><strong>Фроммессажекаунт</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-158">целое</span><span class="sxs-lookup"><span data-stu-id="1dd89-158">int</span></span></p></td>
<td><p><span data-ttu-id="1dd89-159">Количество сообщений, отправленных пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-160"><strong>Томессажекаунт</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-161">целое</span><span class="sxs-lookup"><span data-stu-id="1dd89-161">int</span></span></p></td>
<td><p><span data-ttu-id="1dd89-162">Количество сообщений, отправленных пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="1dd89-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-163"><strong>Фромклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-164">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1dd89-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-165">Версия клиента, используемая пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-166"><strong>Фромклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-167">целое</span><span class="sxs-lookup"><span data-stu-id="1dd89-167">int</span></span></p></td>
<td><p><span data-ttu-id="1dd89-168">Клиент, используемый пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-168">Client used by the user who started the session.</span></span> <span data-ttu-id="1dd89-169">Дополнительные сведения вы увидите <a href="lync-server-2013-useragentdef-table.md">в таблице усеражентдеф в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1dd89-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-170"><strong>Фромклиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="1dd89-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-172">Имя категории клиента, используемой пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-173"><strong>Токлиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-174">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1dd89-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-175">Версия клиента, используемая пользователем, который присоединился к сеансу</span><span class="sxs-lookup"><span data-stu-id="1dd89-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-176"><strong>Токлиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-177">целое</span><span class="sxs-lookup"><span data-stu-id="1dd89-177">int</span></span></p></td>
<td><p><span data-ttu-id="1dd89-178">Клиент, используемый пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="1dd89-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="1dd89-179">Дополнительные сведения вы увидите <a href="lync-server-2013-useragentdef-table.md">в таблице усеражентдеф в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1dd89-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-180"><strong>Токлиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="1dd89-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-182">Имя категории клиента, используемой пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="1dd89-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-183"><strong>Таржетури</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1dd89-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-185">Универсальный код ресурса (URI) целевого пользователя сеанса.</span><span class="sxs-lookup"><span data-stu-id="1dd89-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-186"><strong>Таржетуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1dd89-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-188">Тип универсального кода ресурса (URI) целевого пользователя для сеанса.</span><span class="sxs-lookup"><span data-stu-id="1dd89-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="1dd89-189">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1dd89-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-190"><strong>Онбехалфофури</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1dd89-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-192">Универсальный код ресурса (URI) пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-193"><strong>Онннбехалфофуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1dd89-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-195">Тип универсального кода ресурса (URI) пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="1dd89-196">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1dd89-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-197"><strong>Онбехалфофтенант</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1dd89-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-199">Клиент пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="1dd89-200">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1dd89-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-201"><strong>Реферредбюри</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1dd89-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-203">URI пользователя, который ссылался на сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-204"><strong>Реферредбюритипе</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-205">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1dd89-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-206">Тип URI пользователя, который ссылался на сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="1dd89-207">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1dd89-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-208"><strong>Реферредбитенант</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-209">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1dd89-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-210">Клиент пользователя, который ссылался на сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="1dd89-211">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1dd89-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-212"><strong>Диалогид</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="1dd89-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-214">ИДЕНТИФИКАТОР диалогового окна SIP.</span><span class="sxs-lookup"><span data-stu-id="1dd89-214">SIP dialog ID.</span></span> <span data-ttu-id="1dd89-215">Формат:</span><span class="sxs-lookup"><span data-stu-id="1dd89-215">The format is:</span></span></p>
<p><span data-ttu-id="1dd89-216">диалоговое окно; тег "from-Tag"</span><span class="sxs-lookup"><span data-stu-id="1dd89-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-217"><strong>Корреляци</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-218">идентификатора</span><span class="sxs-lookup"><span data-stu-id="1dd89-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="1dd89-219">GUID, используемый для корреляции нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="1dd89-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-220"><strong>Реплацедиалогидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-221">datetime</span><span class="sxs-lookup"><span data-stu-id="1dd89-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="1dd89-222">Время, когда диалоговое окно было заменено сеансом.</span><span class="sxs-lookup"><span data-stu-id="1dd89-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="1dd89-223">Используется в сочетании с Реплацедиалогидсек для уникальной идентификации диалогового окна, которое заменяется сеансом.</span><span class="sxs-lookup"><span data-stu-id="1dd89-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="1dd89-224">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1dd89-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-225"><strong>Реплацедиалогидсек</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-226">целое</span><span class="sxs-lookup"><span data-stu-id="1dd89-226">int</span></span></p></td>
<td><p><span data-ttu-id="1dd89-227">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="1dd89-227">ID number to identify the session.</span></span> <span data-ttu-id="1dd89-228">Используется в сочетании с Реплацедиалогидтиме для уникальной идентификации диалогового окна, которое заменяется сеансом.</span><span class="sxs-lookup"><span data-stu-id="1dd89-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="1dd89-229">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1dd89-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-230"><strong>Реплацесдиалогид</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="1dd89-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-232">ИДЕНТИФИКАТОР диалогового окна SIP, в котором будет заменяться сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="1dd89-233">Формат:</span><span class="sxs-lookup"><span data-stu-id="1dd89-233">The format is:</span></span></p>
<p><span data-ttu-id="1dd89-234">диалоговое окно; тег "from-Tag"</span><span class="sxs-lookup"><span data-stu-id="1dd89-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-235"><strong>Респонсетиме</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-236">datetime</span><span class="sxs-lookup"><span data-stu-id="1dd89-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="1dd89-237">Время ответа на первое сообщение приглашения.</span><span class="sxs-lookup"><span data-stu-id="1dd89-237">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="1dd89-238">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="1dd89-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="1dd89-239">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="1dd89-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-240"><strong>Респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-241">целое</span><span class="sxs-lookup"><span data-stu-id="1dd89-241">int</span></span></p></td>
<td><p><span data-ttu-id="1dd89-242">Код ответа SIP на приглашение на сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-242">SIP response code to the session invitation.</span></span> <span data-ttu-id="1dd89-243">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="1dd89-243">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="1dd89-244">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="1dd89-244">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-245"><strong>ДиагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-246">целое</span><span class="sxs-lookup"><span data-stu-id="1dd89-246">int</span></span></p></td>
<td><p><span data-ttu-id="1dd89-247">Идентификатор диагностики, полученный из заголовков SIP.</span><span class="sxs-lookup"><span data-stu-id="1dd89-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-248"><strong>Контента</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-249">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1dd89-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-250">Тип контента для сеанса.</span><span class="sxs-lookup"><span data-stu-id="1dd89-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-252">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1dd89-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-253">Полное доменное имя сервера переднего плана, который захватил данные для сеанса.</span><span class="sxs-lookup"><span data-stu-id="1dd89-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-255">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1dd89-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-256">Полное доменное имя пула, который захватывает данные для сеанса.</span><span class="sxs-lookup"><span data-stu-id="1dd89-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-257"><strong>Фромеджесервер</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-258">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1dd89-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-259">Полное доменное имя пограничного сервера, используемое пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-260"><strong>Тоеджесервер</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-261">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1dd89-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-262">Полное доменное имя пограничного сервера, используемое пользователем, который запустил сеанс</span><span class="sxs-lookup"><span data-stu-id="1dd89-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-263"><strong>Исфроминтернал</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-264">бит</span><span class="sxs-lookup"><span data-stu-id="1dd89-264">bit</span></span></p></td>
<td><p><span data-ttu-id="1dd89-265">Указывает, вошел ли пользователь, запустивший сеанс, с помощью внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="1dd89-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-266"><strong>Истоинтернал</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-267">бит</span><span class="sxs-lookup"><span data-stu-id="1dd89-267">bit</span></span></p></td>
<td><p><span data-ttu-id="1dd89-268">Указывает, вошел ли пользователь, который присоединился к сеансу, из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="1dd89-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-269"><strong>Каллприорити</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-270">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1dd89-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-271">Приоритет звонка для сеанса.</span><span class="sxs-lookup"><span data-stu-id="1dd89-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-272"><strong>Фромусерфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-273">smallint</span><span class="sxs-lookup"><span data-stu-id="1dd89-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="1dd89-274">Указывает атрибуты пользователя, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="1dd89-275">Допустимы следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="1dd89-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="1dd89-276">0x01 — интеграция с настольным телефоном</span><span class="sxs-lookup"><span data-stu-id="1dd89-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-277"><strong>Таусерфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-278">smallint</span><span class="sxs-lookup"><span data-stu-id="1dd89-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="1dd89-279">Указывает атрибуты пользователя, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="1dd89-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="1dd89-280">Допустимы следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="1dd89-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="1dd89-281">0x01 — интеграция с настольным телефоном</span><span class="sxs-lookup"><span data-stu-id="1dd89-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dd89-282"><strong>Каллфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-283">smallint</span><span class="sxs-lookup"><span data-stu-id="1dd89-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="1dd89-284">Указывает атрибуты вызова.</span><span class="sxs-lookup"><span data-stu-id="1dd89-284">Indicates the call attributes.</span></span> <span data-ttu-id="1dd89-285">Допустимы следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="1dd89-285">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="1dd89-286">0x01 — сеанс повторной попытки</span><span class="sxs-lookup"><span data-stu-id="1dd89-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="1dd89-287">0x02 — вызов, сделанный агентом от имени группы ответа</span><span class="sxs-lookup"><span data-stu-id="1dd89-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dd89-288"><strong>Расположение</strong></span><span class="sxs-lookup"><span data-stu-id="1dd89-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="1dd89-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="1dd89-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="1dd89-290">Место вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="1dd89-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

