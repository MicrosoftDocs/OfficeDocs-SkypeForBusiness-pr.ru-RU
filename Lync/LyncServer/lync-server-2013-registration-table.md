---
title: 'Lync Server 2013: таблица регистрации'
description: 'Lync Server 2013: таблица регистрации.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 806e1a4e944c9bc04ebdd167c41c80a57fde3f29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578534"
---
# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="7cacb-103">Таблица регистрации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cacb-103">Registration table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cacb-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7cacb-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7cacb-105">Каждая запись представляет одно событие регистрации пользователя.</span><span class="sxs-lookup"><span data-stu-id="7cacb-105">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cacb-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="7cacb-106">Column</span></span></th>
<th><span data-ttu-id="7cacb-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7cacb-107">Data Type</span></span></th>
<th><span data-ttu-id="7cacb-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="7cacb-108">Key/Index</span></span></th>
<th><span data-ttu-id="7cacb-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="7cacb-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cacb-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-111">datetime</span><span class="sxs-lookup"><span data-stu-id="7cacb-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="7cacb-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="7cacb-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cacb-113">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="7cacb-113">Time of session request.</span></span> <span data-ttu-id="7cacb-114">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="7cacb-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="7cacb-115">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cacb-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cacb-116"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-117">int</span><span class="sxs-lookup"><span data-stu-id="7cacb-117">int</span></span></p></td>
<td><p><span data-ttu-id="7cacb-118">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="7cacb-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cacb-119">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="7cacb-119">ID number to identify the session.</span></span> <span data-ttu-id="7cacb-120">В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="7cacb-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="7cacb-121">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cacb-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cacb-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-123">int</span><span class="sxs-lookup"><span data-stu-id="7cacb-123">int</span></span></p></td>
<td><p><span data-ttu-id="7cacb-124">Правительства</span><span class="sxs-lookup"><span data-stu-id="7cacb-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cacb-125">Идентификатор пользователя.</span><span class="sxs-lookup"><span data-stu-id="7cacb-125">The user ID.</span></span> <span data-ttu-id="7cacb-126">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cacb-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cacb-127"><strong>ендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-127"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-128">идентификатора</span><span class="sxs-lookup"><span data-stu-id="7cacb-128">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cacb-p104">GUID для идентификации конечной точки регистрации. Обычно события регистрации с одного и того же компьютера и одного и того же пользователя будут иметь одинаковый идентификатор конечной точки. Разные компьютеры имеют разные идентификаторы конечной точки.</span><span class="sxs-lookup"><span data-stu-id="7cacb-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cacb-132"><strong>ендпоинтера</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-132"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-133">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="7cacb-133">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cacb-134">Идентификатор, используемый, чтобы отличать друг от друга регистрации, в которых участвует один и тот же пользователь и одна и та же конечная точка.</span><span class="sxs-lookup"><span data-stu-id="7cacb-134">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="7cacb-135">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7cacb-135">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cacb-136"><strong>клиентверсионид</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-136"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-137">int</span><span class="sxs-lookup"><span data-stu-id="7cacb-137">int</span></span></p></td>
<td><p><span data-ttu-id="7cacb-138">Правительства</span><span class="sxs-lookup"><span data-stu-id="7cacb-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cacb-139">Версия клиента текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="7cacb-139">Client version of current user.</span></span> <span data-ttu-id="7cacb-140">Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cacb-140">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cacb-141"><strong>регистрарид</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-141"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-142">int</span><span class="sxs-lookup"><span data-stu-id="7cacb-142">int</span></span></p></td>
<td><p><span data-ttu-id="7cacb-143">Правительства</span><span class="sxs-lookup"><span data-stu-id="7cacb-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cacb-144">Идентификатор сервера регистратора, использовавшегося для регистрации.</span><span class="sxs-lookup"><span data-stu-id="7cacb-144">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="7cacb-145">Дополнительные сведения см. <a href="lync-server-2013-servers-table.md">в таблице Servers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cacb-145">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cacb-146"><strong>пулид</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-146"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-147">int</span><span class="sxs-lookup"><span data-stu-id="7cacb-147">int</span></span></p></td>
<td><p><span data-ttu-id="7cacb-148">Правительства</span><span class="sxs-lookup"><span data-stu-id="7cacb-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cacb-149">Идентификатор пула, в котором был записан сеанс.</span><span class="sxs-lookup"><span data-stu-id="7cacb-149">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="7cacb-150">Дополнительные сведения см. <a href="lync-server-2013-pools-table.md">в таблице Pools в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cacb-150">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cacb-151"><strong>еджесерверид</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-151"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-152">int</span><span class="sxs-lookup"><span data-stu-id="7cacb-152">int</span></span></p></td>
<td><p><span data-ttu-id="7cacb-153">Правительства</span><span class="sxs-lookup"><span data-stu-id="7cacb-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cacb-154">Пограничный сервер, через который проходила регистрация.</span><span class="sxs-lookup"><span data-stu-id="7cacb-154">Edge Server the registration is going through.</span></span> <span data-ttu-id="7cacb-155">Дополнительные сведения см. <a href="lync-server-2013-edgeservers-table.md">в таблице таблица edgeservers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cacb-155">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cacb-156"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-156"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-157">Битовая</span><span class="sxs-lookup"><span data-stu-id="7cacb-157">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cacb-158">Вошел ли пользователь из внутренней сети или нет.</span><span class="sxs-lookup"><span data-stu-id="7cacb-158">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cacb-159"><strong>исусерсервицеаваилабле</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-159"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-160">Битовая</span><span class="sxs-lookup"><span data-stu-id="7cacb-160">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cacb-161">Доступна ли служба UserService.</span><span class="sxs-lookup"><span data-stu-id="7cacb-161">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cacb-162"><strong>испримарирегистрар</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-162"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-163">Битовая</span><span class="sxs-lookup"><span data-stu-id="7cacb-163">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cacb-164">Является ли регистратор основным.</span><span class="sxs-lookup"><span data-stu-id="7cacb-164">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cacb-165"><strong>испримарирегистрарцентрал</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-165"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-166">Битовая</span><span class="sxs-lookup"><span data-stu-id="7cacb-166">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cacb-167">Указывает, регистрировался ли пользователь с помощью устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="7cacb-167">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="7cacb-168">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7cacb-168">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cacb-169"><strong>регистертиме</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-169"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-170">datetime</span><span class="sxs-lookup"><span data-stu-id="7cacb-170">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cacb-171">Время регистрации.</span><span class="sxs-lookup"><span data-stu-id="7cacb-171">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cacb-172"><strong>дерегистертиме</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-172"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-173">datetime</span><span class="sxs-lookup"><span data-stu-id="7cacb-173">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cacb-174">Время отмены регистрации.</span><span class="sxs-lookup"><span data-stu-id="7cacb-174">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cacb-175"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-175"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-176">int</span><span class="sxs-lookup"><span data-stu-id="7cacb-176">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cacb-177">Код ответа запроса регистрации.</span><span class="sxs-lookup"><span data-stu-id="7cacb-177">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cacb-178"><strong>диагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-178"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-179">int</span><span class="sxs-lookup"><span data-stu-id="7cacb-179">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cacb-p109">Диагностический идентификатор запроса регистрации. Указывает тип диагностической информации.</span><span class="sxs-lookup"><span data-stu-id="7cacb-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cacb-182"><strong>Устройства</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-182"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-183">int</span><span class="sxs-lookup"><span data-stu-id="7cacb-183">int</span></span></p></td>
<td><p><span data-ttu-id="7cacb-184">Правительства</span><span class="sxs-lookup"><span data-stu-id="7cacb-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cacb-185">Устройство, с которого поступил запрос регистрации.</span><span class="sxs-lookup"><span data-stu-id="7cacb-185">The device that the register request is coming from.</span></span> <span data-ttu-id="7cacb-186">Дополнительные сведения см. <a href="lync-server-2013-devices-table.md">в таблице Devices (устройства) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cacb-186">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cacb-187"><strong>дерегистертипеид</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-187"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-188">tinyint</span><span class="sxs-lookup"><span data-stu-id="7cacb-188">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7cacb-189">Правительства</span><span class="sxs-lookup"><span data-stu-id="7cacb-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cacb-190">Причина отмены регистрации, такая как "user initiated" ("инициатива пользователя"), "registration expired" ("истек срок действия регистрации"), "client fail" ("сбой клиента") и др.</span><span class="sxs-lookup"><span data-stu-id="7cacb-190">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="7cacb-191">Дополнительные сведения см. <a href="lync-server-2013-deregistertype-table.md">в таблице таблица deregistertype в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cacb-191">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cacb-192"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="7cacb-192"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="7cacb-193">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7cacb-193">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cacb-194">IP-адрес конечной точки зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="7cacb-194">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="7cacb-195">Это может быть IPv4-адрес или IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="7cacb-195">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="7cacb-196">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7cacb-196">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

