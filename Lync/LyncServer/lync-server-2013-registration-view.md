---
title: 'Lync Server 2013: представление регистрации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe1b01b748204d3d4365b6f28ae4480d3632b35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="fad42-102">Представление регистрации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fad42-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fad42-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="fad42-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="fad42-104">В представлении регистрация хранятся сведения о регистрации пользователей.</span><span class="sxs-lookup"><span data-stu-id="fad42-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="fad42-105">Это представление было представлено в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fad42-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fad42-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="fad42-106">Column</span></span></th>
<th><span data-ttu-id="fad42-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="fad42-107">Data Type</span></span></th>
<th><span data-ttu-id="fad42-108">Подробности</span><span class="sxs-lookup"><span data-stu-id="fad42-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fad42-109"><strong>Сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-110">datetime</span><span class="sxs-lookup"><span data-stu-id="fad42-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="fad42-111">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="fad42-111">Time of session request.</span></span> <span data-ttu-id="fad42-112">Используется в сочетании с Сессионидсек для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="fad42-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="fad42-113">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fad42-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad42-114"><strong>Сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-115">целое</span><span class="sxs-lookup"><span data-stu-id="fad42-115">int</span></span></p></td>
<td><p><span data-ttu-id="fad42-116">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="fad42-116">ID number to identify the session.</span></span> <span data-ttu-id="fad42-117">Используется в сочетании с Сессионидтиме для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="fad42-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="fad42-118">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fad42-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad42-119"><strong>Регистертиме</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-120">datetime</span><span class="sxs-lookup"><span data-stu-id="fad42-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="fad42-121">Время, когда была выполнена регистрация.</span><span class="sxs-lookup"><span data-stu-id="fad42-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad42-122"><strong>Усерури</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fad42-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fad42-124">URI пользователя, который зарегистрировался.</span><span class="sxs-lookup"><span data-stu-id="fad42-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad42-125"><strong>Усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fad42-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fad42-127">Тип URI пользователя, который зарегистрировался.</span><span class="sxs-lookup"><span data-stu-id="fad42-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="fad42-128">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fad42-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad42-129"><strong>Усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fad42-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fad42-131">Клиент пользователя, который зарегистрировался.</span><span class="sxs-lookup"><span data-stu-id="fad42-131">Tenant of the user who registered.</span></span> <span data-ttu-id="fad42-132">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fad42-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad42-133"><strong>Ендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-134">идентификатора</span><span class="sxs-lookup"><span data-stu-id="fad42-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="fad42-135">Уникальный идентификатор конечной точки пользователя, зарегистрированного в.</span><span class="sxs-lookup"><span data-stu-id="fad42-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad42-136"><strong>Ендпоинтера</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-137">идентификатора</span><span class="sxs-lookup"><span data-stu-id="fad42-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="fad42-138">Уникальный идентификатор, который используется для различения регистраций, включающих одного и того же пользователя и ту же конечную точку.</span><span class="sxs-lookup"><span data-stu-id="fad42-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad42-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-140">datetime</span><span class="sxs-lookup"><span data-stu-id="fad42-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="fad42-141">Время, когда была произведена отмена регистрации.</span><span class="sxs-lookup"><span data-stu-id="fad42-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad42-142"><strong>Дерегистерреасон</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fad42-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fad42-144">Причина отмены регистрации.</span><span class="sxs-lookup"><span data-stu-id="fad42-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad42-145"><strong>Клиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-146">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fad42-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fad42-147">Версия клиента, используемая пользователем, который зарегистрировался.</span><span class="sxs-lookup"><span data-stu-id="fad42-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad42-148"><strong>Клиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-149">целое</span><span class="sxs-lookup"><span data-stu-id="fad42-149">int</span></span></p></td>
<td><p><span data-ttu-id="fad42-150">Клиент, используемый зарегистрированным пользователем.</span><span class="sxs-lookup"><span data-stu-id="fad42-150">Client used by the user who registered.</span></span> <span data-ttu-id="fad42-151">Дополнительные сведения вы увидите <a href="lync-server-2013-useragentdef-table.md">в таблице усеражентдеф в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fad42-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad42-152"><strong>Клиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="fad42-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="fad42-154">Категория клиента, используемая пользователем, который зарегистрировался.</span><span class="sxs-lookup"><span data-stu-id="fad42-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad42-155"><strong>Следующий</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-156">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fad42-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fad42-157">IP-адрес, с которым пользователь зарегистрировался.</span><span class="sxs-lookup"><span data-stu-id="fad42-157">IP Address the user registered with.</span></span> <span data-ttu-id="fad42-158">Это может быть адрес IPv4 или IPv6.</span><span class="sxs-lookup"><span data-stu-id="fad42-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad42-159"><strong>Диалогид</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-160">варстринг (775)</span><span class="sxs-lookup"><span data-stu-id="fad42-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="fad42-161">ИДЕНТИФИКАТОР диалогового окна SIP.</span><span class="sxs-lookup"><span data-stu-id="fad42-161">SIP dialog ID.</span></span> <span data-ttu-id="fad42-162">Формат:</span><span class="sxs-lookup"><span data-stu-id="fad42-162">The format of the is:</span></span></p>
<p><span data-ttu-id="fad42-163">диалоговое окно; тег "from-Tag"</span><span class="sxs-lookup"><span data-stu-id="fad42-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad42-164"><strong>Респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-165">целое</span><span class="sxs-lookup"><span data-stu-id="fad42-165">int</span></span></p></td>
<td><p><span data-ttu-id="fad42-166">Код ответа SIP на приглашение на сеанс.</span><span class="sxs-lookup"><span data-stu-id="fad42-166">SIP response code to the session invitation.</span></span> <span data-ttu-id="fad42-167">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="fad42-167">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="fad42-168">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="fad42-168">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad42-169"><strong>ДиагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-170">целое</span><span class="sxs-lookup"><span data-stu-id="fad42-170">int</span></span></p></td>
<td><p><span data-ttu-id="fad42-171">Идентификатор диагностики, полученный в заголовке SIP.</span><span class="sxs-lookup"><span data-stu-id="fad42-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad42-172"><strong>регистратор</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fad42-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fad42-174">Полное доменное имя регистратора.</span><span class="sxs-lookup"><span data-stu-id="fad42-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad42-175"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fad42-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fad42-177">Полное доменное имя пула, который захватывает данные для сеанса.</span><span class="sxs-lookup"><span data-stu-id="fad42-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad42-178"><strong>Пограничный сервер</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fad42-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fad42-180">Полное доменное имя пограничного сервера, используемое пользователем, который зарегистрировался.</span><span class="sxs-lookup"><span data-stu-id="fad42-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad42-181"><strong>Internal (внутренний)</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-182">бит</span><span class="sxs-lookup"><span data-stu-id="fad42-182">bit</span></span></p></td>
<td><p><span data-ttu-id="fad42-183">Указывает, вошел ли пользователь из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="fad42-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad42-184"><strong>Исусерсервицеаваилабле</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-185">бит</span><span class="sxs-lookup"><span data-stu-id="fad42-185">bit</span></span></p></td>
<td><p><span data-ttu-id="fad42-186">Указывает, был ли Усерсервице доступен на момент регистрации.</span><span class="sxs-lookup"><span data-stu-id="fad42-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad42-187"><strong>Испримарирегистрар</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-188">бит</span><span class="sxs-lookup"><span data-stu-id="fad42-188">bit</span></span></p></td>
<td><p><span data-ttu-id="fad42-189">Указывает, была ли регистрация основным регистратором.</span><span class="sxs-lookup"><span data-stu-id="fad42-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad42-190"><strong>Девицемакаддресс</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-191">bigint</span><span class="sxs-lookup"><span data-stu-id="fad42-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="fad42-192">MAC-адрес устройства зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="fad42-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad42-193"><strong>Девицемануфактурер</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fad42-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fad42-195">Производитель зарегистрированного устройства.</span><span class="sxs-lookup"><span data-stu-id="fad42-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="fad42-196">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-manufacturers-table.md">таблицей изготовителей в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fad42-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad42-197"><strong>Девицехардвареверсион</strong></span><span class="sxs-lookup"><span data-stu-id="fad42-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="fad42-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fad42-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fad42-199">Аппаратная версия зарегистрированного устройства.</span><span class="sxs-lookup"><span data-stu-id="fad42-199">Hardware version of the device registered.</span></span> <span data-ttu-id="fad42-200">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-hardwareversions-table.md">таблицей хардвареверсионс в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fad42-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

