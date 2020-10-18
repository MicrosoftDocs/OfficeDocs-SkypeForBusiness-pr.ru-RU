---
title: 'Lync Server 2013: представление регистрации'
description: 'Lync Server 2013: представление регистрации.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be169cafc324f89cacedda154ca49a8ff1ff39aa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578533"
---
# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="0b6a0-103">Представление регистрации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b6a0-103">Registration view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b6a0-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0b6a0-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0b6a0-105">В представлении Registration хранится информация о регистрации пользователей.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-105">The Registration view stores information about user registration.</span></span> <span data-ttu-id="0b6a0-106">Это представление было представлено в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-106">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b6a0-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="0b6a0-107">Column</span></span></th>
<th><span data-ttu-id="0b6a0-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0b6a0-108">Data Type</span></span></th>
<th><span data-ttu-id="0b6a0-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="0b6a0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b6a0-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-111">datetime</span><span class="sxs-lookup"><span data-stu-id="0b6a0-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-112">Time of session request.</span></span> <span data-ttu-id="0b6a0-113">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="0b6a0-114">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b6a0-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6a0-115"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-116">int</span><span class="sxs-lookup"><span data-stu-id="0b6a0-116">int</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-117">Идентификационный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-117">ID number to identify the session.</span></span> <span data-ttu-id="0b6a0-118">Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="0b6a0-119">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b6a0-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6a0-120"><strong>регистертиме</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-120"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-121">datetime</span><span class="sxs-lookup"><span data-stu-id="0b6a0-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-122">Время регистрации.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-122">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6a0-123"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-123"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-124">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0b6a0-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-125">URI зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-125">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6a0-126"><strong>усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-126"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b6a0-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-128">Тип URI зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-128">Type of URI of the user who registered.</span></span> <span data-ttu-id="0b6a0-129">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b6a0-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6a0-130"><strong>усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-130"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b6a0-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-132">Клиент зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-132">Tenant of the user who registered.</span></span> <span data-ttu-id="0b6a0-133">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b6a0-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6a0-134"><strong>ендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-134"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-135">идентификатора</span><span class="sxs-lookup"><span data-stu-id="0b6a0-135">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-136">Уникальный идентификатор конечной точки зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-136">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6a0-137"><strong>ендпоинтера</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-137"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-138">идентификатора</span><span class="sxs-lookup"><span data-stu-id="0b6a0-138">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-139">Уникальный идентификатор для различия регистраций с одним пользователем и одной конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-139">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6a0-140"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-140"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-141">datetime</span><span class="sxs-lookup"><span data-stu-id="0b6a0-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-142">Время отмены регистрации.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-142">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6a0-143"><strong>дерегистерреасон</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-143"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b6a0-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-145">Причина отмены регистрации.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-145">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6a0-146"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-146"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b6a0-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-148">Версия клиента зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-148">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6a0-149"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-149"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-150">int</span><span class="sxs-lookup"><span data-stu-id="0b6a0-150">int</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-151">Версия клиента зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-151">Client used by the user who registered.</span></span> <span data-ttu-id="0b6a0-152">Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b6a0-152">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6a0-153"><strong>клиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-153"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-154">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="0b6a0-154">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-155">Категория клиента зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-155">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6a0-156"><strong>Адреса</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-156"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-157">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b6a0-157">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-158">IP-адрес зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-158">IP Address the user registered with.</span></span> <span data-ttu-id="0b6a0-159">Это может быть IPv4- или IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-159">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6a0-160"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-160"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-161">варстринг (775)</span><span class="sxs-lookup"><span data-stu-id="0b6a0-161">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-p108">Код диалога SIP. Формат:</span><span class="sxs-lookup"><span data-stu-id="0b6a0-p108">SIP dialog ID. The format of the is:</span></span></p>
<p><span data-ttu-id="0b6a0-164">диалоговое окно; from — Tag; to – Tag</span><span class="sxs-lookup"><span data-stu-id="0b6a0-164">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6a0-165"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-165"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-166">int</span><span class="sxs-lookup"><span data-stu-id="0b6a0-166">int</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-p109">Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="0b6a0-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6a0-170"><strong>диагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-170"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-171">int</span><span class="sxs-lookup"><span data-stu-id="0b6a0-171">int</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-172">Код диагностики из заголовков SIP.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-172">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6a0-173"><strong>Регистратор</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-173"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b6a0-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-175">Полное доменное имя регистратора.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-175">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6a0-176"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-177">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b6a0-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-178">Полное доменное имя пула, который получил данные этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-178">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6a0-179"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-179"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-180">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b6a0-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-181">Полное доменное имя пограничного сервера зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-181">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6a0-182"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-182"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-183">Битовая</span><span class="sxs-lookup"><span data-stu-id="0b6a0-183">bit</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-184">Показывает, зашел ли пользователь в систему из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-184">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6a0-185"><strong>исусерсервицеаваилабле</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-185"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-186">Битовая</span><span class="sxs-lookup"><span data-stu-id="0b6a0-186">bit</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-187">Указывает, была ли служба UserService доступна во время регистрации.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-187">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6a0-188"><strong>испримарирегистрар</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-188"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-189">Битовая</span><span class="sxs-lookup"><span data-stu-id="0b6a0-189">bit</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-190">Указывает, осуществлялась регистрация в основном регистраторе.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-190">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6a0-191"><strong>девицемакаддресс</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-191"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-192">типу</span><span class="sxs-lookup"><span data-stu-id="0b6a0-192">bigint</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-193">MAC-адрес зарегистрировавшегося устройства.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-193">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6a0-194"><strong>девицемануфактурер</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-194"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b6a0-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-196">Производитель зарегистрировавшегося устройства.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-196">Manufacturer of the device registered.</span></span> <span data-ttu-id="0b6a0-197">Для получения дополнительных сведений ознакомьтесь со статьей <a href="lync-server-2013-manufacturers-table.md">Таблица производители в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b6a0-197">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6a0-198"><strong>девицехардвареверсион</strong></span><span class="sxs-lookup"><span data-stu-id="0b6a0-198"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="0b6a0-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b6a0-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b6a0-200">Версия оборудования зарегистрировавшегося устройства.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-200">Hardware version of the device registered.</span></span> <span data-ttu-id="0b6a0-201">Дополнительные сведения см. <a href="lync-server-2013-hardwareversions-table.md">в таблице таблица hardwareversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b6a0-201">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

