---
title: 'Lync Server 2013: таблица регистрации'
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
ms.openlocfilehash: d56f08db69fab4dfbf8da0c09d5d693bccf76bf2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="463bb-102">Таблица регистрации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="463bb-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="463bb-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="463bb-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="463bb-104">Каждая запись представляет одно событие регистрации пользователя.</span><span class="sxs-lookup"><span data-stu-id="463bb-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="463bb-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="463bb-105">Column</span></span></th>
<th><span data-ttu-id="463bb-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="463bb-106">Data Type</span></span></th>
<th><span data-ttu-id="463bb-107">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="463bb-107">Key/Index</span></span></th>
<th><span data-ttu-id="463bb-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="463bb-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="463bb-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-110">datetime</span><span class="sxs-lookup"><span data-stu-id="463bb-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="463bb-111">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="463bb-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="463bb-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="463bb-112">Time of session request.</span></span> <span data-ttu-id="463bb-113">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="463bb-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="463bb-114">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="463bb-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463bb-115"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-116">int</span><span class="sxs-lookup"><span data-stu-id="463bb-116">int</span></span></p></td>
<td><p><span data-ttu-id="463bb-117">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="463bb-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="463bb-118">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="463bb-118">ID number to identify the session.</span></span> <span data-ttu-id="463bb-119">В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="463bb-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="463bb-120">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="463bb-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463bb-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-122">int</span><span class="sxs-lookup"><span data-stu-id="463bb-122">int</span></span></p></td>
<td><p><span data-ttu-id="463bb-123">Правительства</span><span class="sxs-lookup"><span data-stu-id="463bb-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="463bb-124">Идентификатор пользователя.</span><span class="sxs-lookup"><span data-stu-id="463bb-124">The user ID.</span></span> <span data-ttu-id="463bb-125">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="463bb-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463bb-126"><strong>ендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-127">идентификатора</span><span class="sxs-lookup"><span data-stu-id="463bb-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="463bb-p104">GUID для идентификации конечной точки регистрации. Обычно события регистрации с одного и того же компьютера и одного и того же пользователя будут иметь одинаковый идентификатор конечной точки. Разные компьютеры имеют разные идентификаторы конечной точки.</span><span class="sxs-lookup"><span data-stu-id="463bb-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463bb-131"><strong>ендпоинтера</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-132">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="463bb-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="463bb-133">Идентификатор, используемый, чтобы отличать друг от друга регистрации, в которых участвует один и тот же пользователь и одна и та же конечная точка.</span><span class="sxs-lookup"><span data-stu-id="463bb-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="463bb-134">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="463bb-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463bb-135"><strong>клиентверсионид</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-136">int</span><span class="sxs-lookup"><span data-stu-id="463bb-136">int</span></span></p></td>
<td><p><span data-ttu-id="463bb-137">Правительства</span><span class="sxs-lookup"><span data-stu-id="463bb-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="463bb-138">Версия клиента текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="463bb-138">Client version of current user.</span></span> <span data-ttu-id="463bb-139">Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="463bb-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463bb-140"><strong>регистрарид</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-141">int</span><span class="sxs-lookup"><span data-stu-id="463bb-141">int</span></span></p></td>
<td><p><span data-ttu-id="463bb-142">Правительства</span><span class="sxs-lookup"><span data-stu-id="463bb-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="463bb-143">Идентификатор сервера регистратора, использовавшегося для регистрации.</span><span class="sxs-lookup"><span data-stu-id="463bb-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="463bb-144">Дополнительные сведения см. <a href="lync-server-2013-servers-table.md">в таблице Servers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="463bb-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463bb-145"><strong>пулид</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-146">int</span><span class="sxs-lookup"><span data-stu-id="463bb-146">int</span></span></p></td>
<td><p><span data-ttu-id="463bb-147">Правительства</span><span class="sxs-lookup"><span data-stu-id="463bb-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="463bb-148">Идентификатор пула, в котором был записан сеанс.</span><span class="sxs-lookup"><span data-stu-id="463bb-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="463bb-149">Дополнительные сведения см. <a href="lync-server-2013-pools-table.md">в таблице Pools в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="463bb-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463bb-150"><strong>еджесерверид</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-151">int</span><span class="sxs-lookup"><span data-stu-id="463bb-151">int</span></span></p></td>
<td><p><span data-ttu-id="463bb-152">Правительства</span><span class="sxs-lookup"><span data-stu-id="463bb-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="463bb-153">Пограничный сервер, через который проходила регистрация.</span><span class="sxs-lookup"><span data-stu-id="463bb-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="463bb-154">Дополнительные сведения см. <a href="lync-server-2013-edgeservers-table.md">в таблице таблица edgeservers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="463bb-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463bb-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-156">Битовая</span><span class="sxs-lookup"><span data-stu-id="463bb-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="463bb-157">Вошел ли пользователь из внутренней сети или нет.</span><span class="sxs-lookup"><span data-stu-id="463bb-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463bb-158"><strong>исусерсервицеаваилабле</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-159">Битовая</span><span class="sxs-lookup"><span data-stu-id="463bb-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="463bb-160">Доступна ли служба UserService.</span><span class="sxs-lookup"><span data-stu-id="463bb-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463bb-161"><strong>испримарирегистрар</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-162">Битовая</span><span class="sxs-lookup"><span data-stu-id="463bb-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="463bb-163">Является ли регистратор основным.</span><span class="sxs-lookup"><span data-stu-id="463bb-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463bb-164"><strong>испримарирегистрарцентрал</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-165">Битовая</span><span class="sxs-lookup"><span data-stu-id="463bb-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="463bb-166">Указывает, регистрировался ли пользователь с помощью устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="463bb-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="463bb-167">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="463bb-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463bb-168"><strong>регистертиме</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-169">datetime</span><span class="sxs-lookup"><span data-stu-id="463bb-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="463bb-170">Время регистрации.</span><span class="sxs-lookup"><span data-stu-id="463bb-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463bb-171"><strong>дерегистертиме</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-172">datetime</span><span class="sxs-lookup"><span data-stu-id="463bb-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="463bb-173">Время отмены регистрации.</span><span class="sxs-lookup"><span data-stu-id="463bb-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463bb-174"><strong>респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-175">int</span><span class="sxs-lookup"><span data-stu-id="463bb-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="463bb-176">Код ответа запроса регистрации.</span><span class="sxs-lookup"><span data-stu-id="463bb-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463bb-177"><strong>диагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-178">int</span><span class="sxs-lookup"><span data-stu-id="463bb-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="463bb-p109">Диагностический идентификатор запроса регистрации. Указывает тип диагностической информации.</span><span class="sxs-lookup"><span data-stu-id="463bb-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463bb-181"><strong>Устройства</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-182">int</span><span class="sxs-lookup"><span data-stu-id="463bb-182">int</span></span></p></td>
<td><p><span data-ttu-id="463bb-183">Правительства</span><span class="sxs-lookup"><span data-stu-id="463bb-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="463bb-184">Устройство, с которого поступил запрос регистрации.</span><span class="sxs-lookup"><span data-stu-id="463bb-184">The device that the register request is coming from.</span></span> <span data-ttu-id="463bb-185">Дополнительные сведения см. <a href="lync-server-2013-devices-table.md">в таблице Devices (устройства) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="463bb-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463bb-186"><strong>дерегистертипеид</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="463bb-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="463bb-188">Правительства</span><span class="sxs-lookup"><span data-stu-id="463bb-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="463bb-189">Причина отмены регистрации, такая как "user initiated" ("инициатива пользователя"), "registration expired" ("истек срок действия регистрации"), "client fail" ("сбой клиента") и др.</span><span class="sxs-lookup"><span data-stu-id="463bb-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="463bb-190">Дополнительные сведения см. <a href="lync-server-2013-deregistertype-table.md">в таблице таблица deregistertype в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="463bb-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463bb-191"><strong>Адреса</strong></span><span class="sxs-lookup"><span data-stu-id="463bb-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="463bb-192">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="463bb-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="463bb-193">IP-адрес конечной точки зарегистрировавшегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="463bb-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="463bb-194">Это может быть IPv4-адрес или IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="463bb-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="463bb-195">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="463bb-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

