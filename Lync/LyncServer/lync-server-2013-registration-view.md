---
title: 'Lync Server 2013: представление регистрации'
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
ms.openlocfilehash: a7418c5aa80e35d783517a86626dd2b77a393e1d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="2b690-102">Представление регистрации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b690-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b690-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2b690-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2b690-104">В представлении Registration хранится информация о регистрации пользователей.</span><span class="sxs-lookup"><span data-stu-id="2b690-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="2b690-105">Это представление было представлено в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b690-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b690-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="2b690-106">Column</span></span></th>
<th><span data-ttu-id="2b690-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2b690-107">Data Type</span></span></th>
<th><span data-ttu-id="2b690-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="2b690-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b690-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-110">datetime</span><span class="sxs-lookup"><span data-stu-id="2b690-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b690-111">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="2b690-111">Time of session request.</span></span> <span data-ttu-id="2b690-112">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="2b690-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="2b690-113">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2b690-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b690-114"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-115">int</span><span class="sxs-lookup"><span data-stu-id="2b690-115">int</span></span></p></td>
<td><p><span data-ttu-id="2b690-116">Идентификационный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="2b690-116">ID number to identify the session.</span></span> <span data-ttu-id="2b690-117">Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="2b690-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="2b690-118">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2b690-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b690-119"><strong>регистертиме</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-120">datetime</span><span class="sxs-lookup"><span data-stu-id="2b690-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b690-121">Время регистрации.</span><span class="sxs-lookup"><span data-stu-id="2b690-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b690-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b690-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b690-124">URI зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="2b690-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b690-125"><strong>усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b690-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b690-127">Тип URI зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="2b690-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="2b690-128">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2b690-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b690-129"><strong>усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b690-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b690-131">Клиент зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="2b690-131">Tenant of the user who registered.</span></span> <span data-ttu-id="2b690-132">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2b690-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b690-133"><strong>ендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-134">идентификатора</span><span class="sxs-lookup"><span data-stu-id="2b690-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="2b690-135">Уникальный идентификатор конечной точки зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="2b690-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b690-136"><strong>ендпоинтера</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-137">идентификатора</span><span class="sxs-lookup"><span data-stu-id="2b690-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="2b690-138">Уникальный идентификатор для различия регистраций с одним пользователем и одной конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="2b690-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b690-139"><strong>Таблица deregistertype</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-140">datetime</span><span class="sxs-lookup"><span data-stu-id="2b690-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b690-141">Время отмены регистрации.</span><span class="sxs-lookup"><span data-stu-id="2b690-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b690-142"><strong>дерегистерреасон</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b690-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b690-144">Причина отмены регистрации.</span><span class="sxs-lookup"><span data-stu-id="2b690-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b690-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b690-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b690-147">Версия клиента зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="2b690-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b690-148"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-149">int</span><span class="sxs-lookup"><span data-stu-id="2b690-149">int</span></span></p></td>
<td><p><span data-ttu-id="2b690-150">Версия клиента зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="2b690-150">Client used by the user who registered.</span></span> <span data-ttu-id="2b690-151">Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2b690-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b690-152"><strong>клиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="2b690-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="2b690-154">Категория клиента зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="2b690-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b690-155"><strong>Адреса</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-156">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b690-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b690-157">IP-адрес зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="2b690-157">IP Address the user registered with.</span></span> <span data-ttu-id="2b690-158">Это может быть IPv4- или IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="2b690-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b690-159"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-160">варстринг (775)</span><span class="sxs-lookup"><span data-stu-id="2b690-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="2b690-p108">Код диалога SIP. Формат:</span><span class="sxs-lookup"><span data-stu-id="2b690-p108">SIP dialog ID. The format of the is:</span></span></p>
<p><span data-ttu-id="2b690-163">диалоговое окно; from — Tag; to – Tag</span><span class="sxs-lookup"><span data-stu-id="2b690-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b690-164"><strong>респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-165">int</span><span class="sxs-lookup"><span data-stu-id="2b690-165">int</span></span></p></td>
<td><p><span data-ttu-id="2b690-p109">Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="2b690-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b690-169"><strong>диагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-170">int</span><span class="sxs-lookup"><span data-stu-id="2b690-170">int</span></span></p></td>
<td><p><span data-ttu-id="2b690-171">Код диагностики из заголовков SIP.</span><span class="sxs-lookup"><span data-stu-id="2b690-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b690-172"><strong>Регистратор</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b690-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b690-174">Полное доменное имя регистратора.</span><span class="sxs-lookup"><span data-stu-id="2b690-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b690-175"><strong>Ресурсов</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b690-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b690-177">Полное доменное имя пула, который получил данные этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="2b690-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b690-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b690-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b690-180">Полное доменное имя пограничного сервера зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="2b690-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b690-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-182">Битовая</span><span class="sxs-lookup"><span data-stu-id="2b690-182">bit</span></span></p></td>
<td><p><span data-ttu-id="2b690-183">Показывает, зашел ли пользователь в систему из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="2b690-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b690-184"><strong>исусерсервицеаваилабле</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-185">Битовая</span><span class="sxs-lookup"><span data-stu-id="2b690-185">bit</span></span></p></td>
<td><p><span data-ttu-id="2b690-186">Указывает, была ли служба UserService доступна во время регистрации.</span><span class="sxs-lookup"><span data-stu-id="2b690-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b690-187"><strong>испримарирегистрар</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-188">Битовая</span><span class="sxs-lookup"><span data-stu-id="2b690-188">bit</span></span></p></td>
<td><p><span data-ttu-id="2b690-189">Указывает, осуществлялась регистрация в основном регистраторе.</span><span class="sxs-lookup"><span data-stu-id="2b690-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b690-190"><strong>девицемакаддресс</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-191">типу</span><span class="sxs-lookup"><span data-stu-id="2b690-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="2b690-192">MAC-адрес зарегистрировавшегося устройства.</span><span class="sxs-lookup"><span data-stu-id="2b690-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b690-193"><strong>девицемануфактурер</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b690-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b690-195">Производитель зарегистрировавшегося устройства.</span><span class="sxs-lookup"><span data-stu-id="2b690-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="2b690-196">Для получения дополнительных сведений ознакомьтесь со статьей <a href="lync-server-2013-manufacturers-table.md">Таблица производители в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2b690-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b690-197"><strong>девицехардвареверсион</strong></span><span class="sxs-lookup"><span data-stu-id="2b690-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="2b690-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b690-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b690-199">Версия оборудования зарегистрировавшегося устройства.</span><span class="sxs-lookup"><span data-stu-id="2b690-199">Hardware version of the device registered.</span></span> <span data-ttu-id="2b690-200">Дополнительные сведения см. <a href="lync-server-2013-hardwareversions-table.md">в таблице таблица hardwareversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2b690-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

