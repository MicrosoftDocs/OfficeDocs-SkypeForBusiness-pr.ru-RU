---
title: 'Lync Server 2013: таблица Registration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfee81d83fb58b2fbeccff68a672da47e6770bd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="e3722-102">Таблица Registration в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3722-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3722-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e3722-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e3722-104">Каждая запись представляет одно событие регистрации пользователя.</span><span class="sxs-lookup"><span data-stu-id="e3722-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3722-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="e3722-105">Column</span></span></th>
<th><span data-ttu-id="e3722-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e3722-106">Data Type</span></span></th>
<th><span data-ttu-id="e3722-107">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="e3722-107">Key/Index</span></span></th>
<th><span data-ttu-id="e3722-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="e3722-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3722-109"><strong>Сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-110">datetime</span><span class="sxs-lookup"><span data-stu-id="e3722-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e3722-111">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="e3722-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3722-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="e3722-112">Time of session request.</span></span> <span data-ttu-id="e3722-113">Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="e3722-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e3722-114">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3722-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3722-115"><strong>Сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-116">целое</span><span class="sxs-lookup"><span data-stu-id="e3722-116">int</span></span></p></td>
<td><p><span data-ttu-id="e3722-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="e3722-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3722-118">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="e3722-118">ID number to identify the session.</span></span> <span data-ttu-id="e3722-119">Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="e3722-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e3722-120">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3722-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3722-121"><strong>Идентификатора пользователя</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-122">целое</span><span class="sxs-lookup"><span data-stu-id="e3722-122">int</span></span></p></td>
<td><p><span data-ttu-id="e3722-123">Другом</span><span class="sxs-lookup"><span data-stu-id="e3722-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3722-124">Идентификатор пользователя.</span><span class="sxs-lookup"><span data-stu-id="e3722-124">The user ID.</span></span> <span data-ttu-id="e3722-125">Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3722-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3722-126"><strong>Ендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-127">идентификатора</span><span class="sxs-lookup"><span data-stu-id="e3722-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3722-128">GUID для идентификации конечной точки регистрации.</span><span class="sxs-lookup"><span data-stu-id="e3722-128">A GUID to identify a registration endpoint.</span></span> <span data-ttu-id="e3722-129">Обычно событие Register на том же компьютере того же пользователя будет иметь тот же идентификатор конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e3722-129">Usually the register event from the same computer of the same user will have the same endpoint ID.</span></span> <span data-ttu-id="e3722-130">У разных компьютеров другой идентификатор конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e3722-130">Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3722-131"><strong>Ендпоинтера</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-132">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="e3722-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3722-133">Идентификатор, который используется для различения регистраций, включающих одного и того же пользователя и ту же конечную точку.</span><span class="sxs-lookup"><span data-stu-id="e3722-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="e3722-134">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3722-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3722-135"><strong>Клиентверсионид</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-136">целое</span><span class="sxs-lookup"><span data-stu-id="e3722-136">int</span></span></p></td>
<td><p><span data-ttu-id="e3722-137">Другом</span><span class="sxs-lookup"><span data-stu-id="e3722-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3722-138">Клиентская версия текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="e3722-138">Client version of current user.</span></span> <span data-ttu-id="e3722-139">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-clientversions-table.md">таблицей клиентверсионс в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3722-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3722-140"><strong>Регистрарид</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-141">целое</span><span class="sxs-lookup"><span data-stu-id="e3722-141">int</span></span></p></td>
<td><p><span data-ttu-id="e3722-142">Другом</span><span class="sxs-lookup"><span data-stu-id="e3722-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3722-143">Идентификатор сервера регистратора, используемого для регистрации.</span><span class="sxs-lookup"><span data-stu-id="e3722-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="e3722-144">Более подробную информацию вы видите <a href="lync-server-2013-servers-table.md">в таблице Servers (серверы) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3722-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3722-145"><strong>Пулид</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-146">целое</span><span class="sxs-lookup"><span data-stu-id="e3722-146">int</span></span></p></td>
<td><p><span data-ttu-id="e3722-147">Другом</span><span class="sxs-lookup"><span data-stu-id="e3722-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3722-148">Идентификатор пула, в котором был собран сеанс.</span><span class="sxs-lookup"><span data-stu-id="e3722-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="e3722-149">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-pools-table.md">таблицей пулы в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3722-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3722-150"><strong>Еджесерверид</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-151">целое</span><span class="sxs-lookup"><span data-stu-id="e3722-151">int</span></span></p></td>
<td><p><span data-ttu-id="e3722-152">Другом</span><span class="sxs-lookup"><span data-stu-id="e3722-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3722-153">Пограничный сервер, на котором проходит регистрация.</span><span class="sxs-lookup"><span data-stu-id="e3722-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="e3722-154">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-edgeservers-table.md">таблицей еджесерверс в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3722-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3722-155"><strong>Internal (внутренний)</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-156">Разрядная версия</span><span class="sxs-lookup"><span data-stu-id="e3722-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3722-157">Вход пользователя из внутреннего режима или нет.</span><span class="sxs-lookup"><span data-stu-id="e3722-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3722-158"><strong>Исусерсервицеаваилабле</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-159">бит</span><span class="sxs-lookup"><span data-stu-id="e3722-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3722-160">Доступен ли Усерсервице или нет.</span><span class="sxs-lookup"><span data-stu-id="e3722-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3722-161"><strong>Испримарирегистрар</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-162">бит</span><span class="sxs-lookup"><span data-stu-id="e3722-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3722-163">Регистрация для основного регистратора или нет.</span><span class="sxs-lookup"><span data-stu-id="e3722-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3722-164"><strong>Испримарирегистрарцентрал</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-165">бит</span><span class="sxs-lookup"><span data-stu-id="e3722-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3722-166">Указывает, зарегистрирован ли пользователь в работающем устройстве филиала.</span><span class="sxs-lookup"><span data-stu-id="e3722-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="e3722-167">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3722-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3722-168"><strong>Регистертиме</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-169">datetime</span><span class="sxs-lookup"><span data-stu-id="e3722-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3722-170">Время регистрации.</span><span class="sxs-lookup"><span data-stu-id="e3722-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3722-171"><strong>Дерегистертиме</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-172">datetime</span><span class="sxs-lookup"><span data-stu-id="e3722-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3722-173">Время отмены регистрации.</span><span class="sxs-lookup"><span data-stu-id="e3722-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3722-174"><strong>Респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-175">целое</span><span class="sxs-lookup"><span data-stu-id="e3722-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3722-176">Код ответа на запрос на регистрацию.</span><span class="sxs-lookup"><span data-stu-id="e3722-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3722-177"><strong>ДиагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-178">целое</span><span class="sxs-lookup"><span data-stu-id="e3722-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3722-179">Идентификатор диагностики запроса на регистрацию.</span><span class="sxs-lookup"><span data-stu-id="e3722-179">Diagnostic ID of the register request.</span></span> <span data-ttu-id="e3722-180">Это означает, что тип данных диагностики.</span><span class="sxs-lookup"><span data-stu-id="e3722-180">This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3722-181"><strong>Устройства</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-182">целое</span><span class="sxs-lookup"><span data-stu-id="e3722-182">int</span></span></p></td>
<td><p><span data-ttu-id="e3722-183">Другом</span><span class="sxs-lookup"><span data-stu-id="e3722-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3722-184">Устройство, от которого поступил запрос на регистрацию.</span><span class="sxs-lookup"><span data-stu-id="e3722-184">The device that the register request is coming from.</span></span> <span data-ttu-id="e3722-185">Более подробную информацию вы видите в <a href="lync-server-2013-devices-table.md">таблице "устройства" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3722-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3722-186"><strong>Дерегистертипеид</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="e3722-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e3722-188">Другом</span><span class="sxs-lookup"><span data-stu-id="e3722-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3722-189">Причина отмены регистрации, например "пользователь инициировал", "регистрация просрочена", "клиент не проходит" и многое другое.</span><span class="sxs-lookup"><span data-stu-id="e3722-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="e3722-190">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-deregistertype-table.md">таблицей дерегистертипе в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3722-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3722-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="e3722-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="e3722-192">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e3722-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3722-193">IP-адрес конечной точки, зарегистрированной пользователем.</span><span class="sxs-lookup"><span data-stu-id="e3722-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="e3722-194">Это может быть адрес IPv4 или IPv6.</span><span class="sxs-lookup"><span data-stu-id="e3722-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="e3722-195">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3722-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

