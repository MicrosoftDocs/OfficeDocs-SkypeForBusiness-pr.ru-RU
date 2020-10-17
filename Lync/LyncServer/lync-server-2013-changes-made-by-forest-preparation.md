---
title: 'Lync Server 2013: изменения, внесенные при подготовке леса'
description: 'Lync Server 2013: изменения, внесенные при подготовке леса.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c9bc40539c285e03610b2fc97166842473997fb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543655"
---
# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a><span data-ttu-id="c4729-103">Изменения, внесенные при подготовке леса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4729-103">Changes made by forest preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4729-104">_**Последнее изменение темы:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="c4729-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="c4729-105">В данном разделе описываются глобальные параметры и объекты, а также универсальные группы служб и административные группы, создаваемые на этапе подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="c4729-105">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

<div>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="c4729-106">Глобальные параметры и объекты Active Directory</span><span class="sxs-lookup"><span data-stu-id="c4729-106">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="c4729-107">Если глобальные параметры хранятся в контейнере конфигурации (как в случае со всеми новыми развертываниями Lync Server 2013), подготовка леса использует существующий контейнер служб и добавляет объект **службы RTC** в \\ объект Configuration Services.</span><span class="sxs-lookup"><span data-stu-id="c4729-107">If you store global settings in the Configuration container (as is the case for all new Lync Server 2013 deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\\Services object.</span></span> <span data-ttu-id="c4729-108">В объект RTC Service процедура подготовки лета добавляет объект **Global Settings** типа msRTCSIP-GlobalContainer.</span><span class="sxs-lookup"><span data-stu-id="c4729-108">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="c4729-109">В глобальном объекте Settings хранятся все параметры, применимые к развертыванию Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4729-109">The global settings object holds all the settings that apply to the Lync Server deployment.</span></span> <span data-ttu-id="c4729-110">Если глобальные параметры хранятся в контейнере System, то при подготовке леса используется контейнер Microsoft Container в контейнере System корневого домена и объект службы RTC в системном \\ объекте Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c4729-110">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\\Microsoft object.</span></span>

<span data-ttu-id="c4729-111">Процедура подготовки леса также добавляет новый объект **msRTCSIP-Domain** для корневого домена, в котором выполняется процедура.</span><span class="sxs-lookup"><span data-stu-id="c4729-111">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="c4729-112">Универсальные группы служб и административные группы Active Directory</span><span class="sxs-lookup"><span data-stu-id="c4729-112">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="c4729-p102">Процедура подготовки леса создает универсальные группы на основании указанного вами домена и добавляет для этих групп элементы управления доступом (ACE). На данном этапе универсальные группы создаются в контейнерах User указанного вами домена.</span><span class="sxs-lookup"><span data-stu-id="c4729-p102">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups. This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="c4729-p103">Универсальные группы позволяют администраторам осуществлять доступ к глобальным параметрам и службам и управлять ими. Процедура подготовки леса добавляет следующие типы универсальных групп:</span><span class="sxs-lookup"><span data-stu-id="c4729-p103">Universal groups allow administrators to access and manage global settings and services. Forest preparation adds the following types of universal groups:</span></span>

  - <span data-ttu-id="c4729-117">**Административные группы**     Эти группы определяют роли администратора для сети Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4729-117">**Administrative groups**   These groups define administrator roles for a Lync Server network.</span></span>

  - <span data-ttu-id="c4729-118">**Группы инфраструктуры**     Эти группы предоставляют разрешение на доступ к определенным областям инфраструктуры Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4729-118">**Infrastructure groups**   These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="c4729-119">Они выступают в качестве компонентов административных групп.</span><span class="sxs-lookup"><span data-stu-id="c4729-119">They function as components of administrative groups.</span></span> <span data-ttu-id="c4729-120">Вам не следует изменять эти группы или добавлять пользователей непосредственно в них.</span><span class="sxs-lookup"><span data-stu-id="c4729-120">You should not modify these groups or add users directly to them.</span></span>

  - <span data-ttu-id="c4729-121">**Группы служб**     Эти группы являются учетными записями служб, необходимыми для доступа к различным службам Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4729-121">**Service groups**   These groups are service accounts that are required to access various Lync Server services.</span></span>

<span data-ttu-id="c4729-122">В следующей таблице описываются административные группы.</span><span class="sxs-lookup"><span data-stu-id="c4729-122">The following table describes the administrative groups.</span></span>

### <a name="administrative-groups-created-during-forest-preparation"></a><span data-ttu-id="c4729-123">Административные группы, созданные во время подготовки леса</span><span class="sxs-lookup"><span data-stu-id="c4729-123">Administrative Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4729-124">Административная группа</span><span class="sxs-lookup"><span data-stu-id="c4729-124">Administrative group</span></span></th>
<th><span data-ttu-id="c4729-125">Описание</span><span class="sxs-lookup"><span data-stu-id="c4729-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4729-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c4729-126">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="c4729-127">Позволяет членам управлять параметрами серверов и пулов, включая все роли сервера, глобальные параметры и пользователей.</span><span class="sxs-lookup"><span data-stu-id="c4729-127">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4729-128">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="c4729-128">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="c4729-129">Позволяет членам управлять параметрами пользователей и перемещать пользователей из одного сервера или пула в другой.</span><span class="sxs-lookup"><span data-stu-id="c4729-129">Allows members to manage user settings and move users from one server or pool to another.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4729-130">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="c4729-130">RTCUniversalReadOnlyAdmins</span></span></p></td>
<td><p><span data-ttu-id="c4729-131">Позволяет членам считывать параметры серверов, пулов и пользователей.</span><span class="sxs-lookup"><span data-stu-id="c4729-131">Allows members to read server, pool, and user settings.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c4729-132">В следующей таблице описываются группы инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="c4729-132">The following table describes the infrastructure groups.</span></span>

### <a name="infrastructure-groups-created-during-forest-preparation"></a><span data-ttu-id="c4729-133">Группы инфраструктуры, созданные во время подготовки леса</span><span class="sxs-lookup"><span data-stu-id="c4729-133">Infrastructure Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4729-134">Группа инфраструктуры</span><span class="sxs-lookup"><span data-stu-id="c4729-134">Infrastructure group</span></span></th>
<th><span data-ttu-id="c4729-135">Описание</span><span class="sxs-lookup"><span data-stu-id="c4729-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4729-136">рткуниверсалглобалвритеграуп</span><span class="sxs-lookup"><span data-stu-id="c4729-136">RTCUniversalGlobalWriteGroup</span></span></p></td>
<td><p><span data-ttu-id="c4729-137">Предоставляет доступ на запись к глобальным объектам параметров для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4729-137">Grants write access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4729-138">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c4729-138">RTCUniversalGlobalReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c4729-139">Предоставляет доступ только для чтения к глобальным объектам Setting для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4729-139">Grants read-only access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4729-140">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c4729-140">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c4729-141">Предоставляет доступ только для чтения к параметрам пользователя Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4729-141">Grants read-only access to Lync Server user settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4729-142">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c4729-142">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c4729-143">Предоставляет доступ только для чтения к параметрам Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4729-143">Grants read-only access to Lync Server settings.</span></span> <span data-ttu-id="c4729-144">Данная группа не имеет доступа к параметрам уровня пулов, ей доступны только параметры для отдельного сервера.</span><span class="sxs-lookup"><span data-stu-id="c4729-144">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4729-145">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="c4729-145">RTCUniversalSBATechnicians</span></span></p></td>
<td><p><span data-ttu-id="c4729-146">Предоставляет доступ только для чтения к конфигурации Lync Server и помещаются в группу локальных администраторов устройств для обеспечения связи в филиалах во время установки.</span><span class="sxs-lookup"><span data-stu-id="c4729-146">Grants read-only access to Lync Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c4729-147">В следующей таблице описываются группы служб.</span><span class="sxs-lookup"><span data-stu-id="c4729-147">The following table describes the service groups.</span></span>

### <a name="service-groups-created-during-forest-preparation"></a><span data-ttu-id="c4729-148">Группы служб, созданные во время подготовки леса</span><span class="sxs-lookup"><span data-stu-id="c4729-148">Service Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4729-149">Группа служб</span><span class="sxs-lookup"><span data-stu-id="c4729-149">Service group</span></span></th>
<th><span data-ttu-id="c4729-150">Описание</span><span class="sxs-lookup"><span data-stu-id="c4729-150">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4729-151">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="c4729-151">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="c4729-152">Включает учетные записи служб, используемые для запуска серверов переднего плана и серверов Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c4729-152">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="c4729-153">Эта группа разрешает серверам доступ для чтения и записи к глобальным параметрам Lync Server и объектам пользователя Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c4729-153">This group allows servers read/write access to Lync Server global settings and Active Directory user objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4729-154">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="c4729-154">RTCComponentUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="c4729-155">Включает служебные учетные записи, используемые для выполнения серверов аудио-и видеоконференций, веб-служб, сервера-посредника, сервера архивации и сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="c4729-155">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4729-156">рткпроксюниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="c4729-156">RTCProxyUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="c4729-157">Включает учетные записи служб, используемые для запуска пограничных серверов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4729-157">Includes service accounts used to run Lync Server Edge Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4729-158">рткуниверсалконфигрепликатор</span><span class="sxs-lookup"><span data-stu-id="c4729-158">RTCUniversalConfigReplicator</span></span></p></td>
<td><p><span data-ttu-id="c4729-159">Включает серверы, которые могут участвовать в репликации центрального хранилища управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4729-159">Includes servers that can participate in Lync Server Central Management store replication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4729-160">ртксбауниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="c4729-160">RTCSBAUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="c4729-161">Предоставляет доступ только для чтения к параметрам Lync Server, но позволяет настраивать установку сервера для обеспечения связи в филиалах и развертывания устройства в филиалах.</span><span class="sxs-lookup"><span data-stu-id="c4729-161">Grants read-only access to Lync Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c4729-162">После этого процедура подготовки леса добавляет группы служб и административные группы в соответствующие группы инфраструктуры следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c4729-162">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

  - <span data-ttu-id="c4729-163">RTCUniversalServerAdmins добавляется в RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="c4729-163">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="c4729-164">RTCUniversalUserAdmins добавляется в качестве члена групп RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="c4729-164">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="c4729-165">RTCHSUniversalServices, RTCComponentUniversalServices и RTCUniversalReadOnlyAdmins добавляются в качестве членов групп RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="c4729-165">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="c4729-166">Процедура подготовки леса также создает следующие группы управления доступом на основе ролей:</span><span class="sxs-lookup"><span data-stu-id="c4729-166">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

  - <span data-ttu-id="c4729-167">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="c4729-167">CSAdministrator</span></span>

  - <span data-ttu-id="c4729-168">Роли csarchivingadministrator</span><span class="sxs-lookup"><span data-stu-id="c4729-168">CSArchivingAdministrator</span></span>

  - <span data-ttu-id="c4729-169">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="c4729-169">CSHelpDesk</span></span>

  - <span data-ttu-id="c4729-170">кслокатионадминистратор</span><span class="sxs-lookup"><span data-stu-id="c4729-170">CSLocationAdministrator</span></span>

  - <span data-ttu-id="c4729-171">ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="c4729-171">CSResponseGroupAdministrator</span></span>

  - <span data-ttu-id="c4729-172">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c4729-172">CSServerAdministrator</span></span>

  - <span data-ttu-id="c4729-173">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="c4729-173">CSUserAdministrator</span></span>

  - <span data-ttu-id="c4729-174">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="c4729-174">CSViewOnlyAdministrator</span></span>

  - <span data-ttu-id="c4729-175">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="c4729-175">CSVoiceAdministrator</span></span>

  - <span data-ttu-id="c4729-176">ксперсистентчатадминистатор</span><span class="sxs-lookup"><span data-stu-id="c4729-176">CsPersistentChatAdministator</span></span>

  - <span data-ttu-id="c4729-177">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="c4729-177">CsResponseGroupManager</span></span>

<span data-ttu-id="c4729-178">Подробные сведения о ролях RBAC и задачах, разрешенных для каждого из них, приведены в статье [Планирование управления доступом на основе ролей в Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="c4729-178">For details about RBAC roles and the tasks allowed for each, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="c4729-179">Процедура подготовки леса создает как частные, так и общие элементы управления доступом.</span><span class="sxs-lookup"><span data-stu-id="c4729-179">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="c4729-180">Он создает частные записи управления доступом в контейнере глобальных параметров, используемом Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4729-180">It creates private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="c4729-181">Этот контейнер используется только Lync Server и находится в контейнере конфигурации или в контейнере System в корневом домене в зависимости от того, где хранятся глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="c4729-181">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="c4729-182">В следующей таблице приведены общие элементы управления доступом, создаваемые процедурой подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="c4729-182">The public ACEs created by forest preparation are listed in the following table.</span></span>

### <a name="public-aces-created-by-forest-preparation"></a><span data-ttu-id="c4729-183">Общие элементы управления доступом, создаваемые процедурой подготовки леса</span><span class="sxs-lookup"><span data-stu-id="c4729-183">Public ACEs created by Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4729-184">ACE</span><span class="sxs-lookup"><span data-stu-id="c4729-184">ACE</span></span></th>
<th><span data-ttu-id="c4729-185">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c4729-185">RTCUniversalGlobalReadOnlyGroup</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4729-186">Чтение контейнера System корневого домена (не наследуется)<strong>\*</strong></span><span class="sxs-lookup"><span data-stu-id="c4729-186">Read root domain System Container (not inherited)<strong>\*</strong></span></span></p></td>
<td><p><span data-ttu-id="c4729-187">X</span><span class="sxs-lookup"><span data-stu-id="c4729-187">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4729-188">Чтение контейнера DisplaySpecifiers конфигурации (не наследуется)</span><span class="sxs-lookup"><span data-stu-id="c4729-188">Read Configuration’s DisplaySpecifiers container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="c4729-189">X</span><span class="sxs-lookup"><span data-stu-id="c4729-189">X</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c4729-190"><STRONG>\*</STRONG>Элементы управления доступом, которые не являются унаследованными, не предоставляют доступ к дочерним объектам в этих контейнерах.</span><span class="sxs-lookup"><span data-stu-id="c4729-190"><STRONG>\*</STRONG>ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="c4729-191">Наследуемые элементы управления доступом предоставляют доступ к дочерним объектам в таких контейнерах.</span><span class="sxs-lookup"><span data-stu-id="c4729-191">ACEs that are inherited grant access to child objects under these containers.</span></span>



</div>

<span data-ttu-id="c4729-192">В контейнере Configuration в контексте именования Configuration процедура подготовки леса выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="c4729-192">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

  - <span data-ttu-id="c4729-193">Добавляет запись **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** для страницы **RTC property** в атрибутах adminContextMenu и adminPropertyPages описателя отображения языка для пользователей, контактов и InetOrgPersons (например, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="c4729-193">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="c4729-194">Добавляет объект **RTCPropertySet** типа **controlAccessRight** в **Extended-Rights**, применяемый к классам User и Contact.</span><span class="sxs-lookup"><span data-stu-id="c4729-194">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

  - <span data-ttu-id="c4729-195">Добавляет объект **RTCUserSearchPropertySet** типа **controlAccessRight** в **Extended-Rights**, применяемый к классам User, Contact, OU и DomainDNS.</span><span class="sxs-lookup"><span data-stu-id="c4729-195">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

  - <span data-ttu-id="c4729-196">Добавляет **msRTCSIP-PrimaryUserAddress** в атрибут **extraColumns** каждого описателя отображения языкового подразделения (например, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) и копирует значения атрибута **extraColumns** отображения по умолчанию (например, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="c4729-196">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="c4729-197">Добавляет атрибуты фильтрации **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** и **msRTCSIP-UserEnabled** в атрибут **attributeDisplayNames** каждого описателя отображения языка для объектов Users, Contacts и InetOrgPerson (например, для английского: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="c4729-197">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

