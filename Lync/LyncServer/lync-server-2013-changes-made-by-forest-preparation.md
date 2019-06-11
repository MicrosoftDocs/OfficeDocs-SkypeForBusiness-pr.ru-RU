---
title: 'Lync Server 2013: изменения, внесенные с помощью подготовки леса'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef94ea82f31871cf90939aa25a130903f15ef756
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a><span data-ttu-id="a5280-102">Изменения, внесенные в процессе подготовки леса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5280-102">Changes made by forest preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5280-103">_**Тема последнего изменения:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="a5280-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="a5280-104">В этом разделе описаны глобальные параметры и объекты, а также универсальные службы и группы администрирования, созданные на этапе подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="a5280-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

<div>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="a5280-105">Глобальные параметры и объекты в службе каталогов Active Directory</span><span class="sxs-lookup"><span data-stu-id="a5280-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="a5280-106">Если вы сохраняете глобальные параметры в контейнере конфигурации (как в случае со всеми новыми развертываниями для Lync Server 2013), подготовка леса использует существующий контейнер служб и добавляет объект **службы RTC** в службах\\конфигурации. DataObject.</span><span class="sxs-lookup"><span data-stu-id="a5280-106">If you store global settings in the Configuration container (as is the case for all new Lync Server 2013 deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\\Services object.</span></span> <span data-ttu-id="a5280-107">В разделе объект службы RTC для подготовки леса добавляется **глобальный объект параметров** типа MsRTCSIP-глобалконтаинер.</span><span class="sxs-lookup"><span data-stu-id="a5280-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="a5280-108">Объект глобальных параметров содержит все параметры, которые применяются к развертыванию Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a5280-108">The global settings object holds all the settings that apply to the Lync Server deployment.</span></span> <span data-ttu-id="a5280-109">При хранении глобальных параметров в контейнере System для подготовки леса используется контейнер Microsoft из контейнера System корневого домена и объект службы RTC из системного\\объекта Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a5280-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\\Microsoft object.</span></span>

<span data-ttu-id="a5280-110">Подготовка леса также добавляет новый объект **msRTCSIP-Domain** для корневого домена, в котором выполняется процедура.</span><span class="sxs-lookup"><span data-stu-id="a5280-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="a5280-111">Универсальные службы и группы администрирования Active Directory</span><span class="sxs-lookup"><span data-stu-id="a5280-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="a5280-112">Подготовка леса создает универсальные группы на основе указанного домена и добавляет элементы управления доступом (ACE) для этих групп.</span><span class="sxs-lookup"><span data-stu-id="a5280-112">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups.</span></span> <span data-ttu-id="a5280-113">На этом этапе создаются универсальные группы в контейнерах пользователей указанного домена.</span><span class="sxs-lookup"><span data-stu-id="a5280-113">This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="a5280-114">Универсальные группы позволяют администраторам получать доступ к глобальным параметрам и службам и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="a5280-114">Universal groups allow administrators to access and manage global settings and services.</span></span> <span data-ttu-id="a5280-115">Подготовка леса добавляет следующие типы универсальных групп:</span><span class="sxs-lookup"><span data-stu-id="a5280-115">Forest preparation adds the following types of universal groups:</span></span>

  - <span data-ttu-id="a5280-116">**Административные группы**   . в этих группах определяются роли администратора для сети Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a5280-116">**Administrative groups**   These groups define administrator roles for a Lync Server network.</span></span>

  - <span data-ttu-id="a5280-117">**Группы инфраструктуры эти**   группы предоставляют разрешения на доступ к определенным областям инфраструктуры Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a5280-117">**Infrastructure groups**   These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="a5280-118">Они будут работать как компоненты административных групп.</span><span class="sxs-lookup"><span data-stu-id="a5280-118">They function as components of administrative groups.</span></span> <span data-ttu-id="a5280-119">Не следует изменять эти группы и добавлять пользователей прямо в них.</span><span class="sxs-lookup"><span data-stu-id="a5280-119">You should not modify these groups or add users directly to them.</span></span>

  - <span data-ttu-id="a5280-120">**Группы служб эти**   группы являются учетными записями служб, необходимыми для доступа к различным службам Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a5280-120">**Service groups**   These groups are service accounts that are required to access various Lync Server services.</span></span>

<span data-ttu-id="a5280-121">В приведенной ниже таблице описаны группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="a5280-121">The following table describes the administrative groups.</span></span>

### <a name="administrative-groups-created-during-forest-preparation"></a><span data-ttu-id="a5280-122">Административные группы, созданные во время подготовки леса</span><span class="sxs-lookup"><span data-stu-id="a5280-122">Administrative Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5280-123">Группа администраторов</span><span class="sxs-lookup"><span data-stu-id="a5280-123">Administrative group</span></span></th>
<th><span data-ttu-id="a5280-124">Описание</span><span class="sxs-lookup"><span data-stu-id="a5280-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5280-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a5280-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="a5280-126">Позволяет пользователям управлять параметрами сервера и пула, включая все роли сервера, глобальные параметры и пользователей.</span><span class="sxs-lookup"><span data-stu-id="a5280-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5280-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a5280-127">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a5280-128">Позволяет пользователям управлять параметрами пользователей и перемещать пользователей из одного сервера или пула в другой.</span><span class="sxs-lookup"><span data-stu-id="a5280-128">Allows members to manage user settings and move users from one server or pool to another.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5280-129">Рткуниверсалреадонлядминс</span><span class="sxs-lookup"><span data-stu-id="a5280-129">RTCUniversalReadOnlyAdmins</span></span></p></td>
<td><p><span data-ttu-id="a5280-130">Позволяет участникам читать параметры сервера, пула и пользователей.</span><span class="sxs-lookup"><span data-stu-id="a5280-130">Allows members to read server, pool, and user settings.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a5280-131">В приведенной ниже таблице описаны группы инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="a5280-131">The following table describes the infrastructure groups.</span></span>

### <a name="infrastructure-groups-created-during-forest-preparation"></a><span data-ttu-id="a5280-132">Группы инфраструктуры, созданные во время подготовки леса</span><span class="sxs-lookup"><span data-stu-id="a5280-132">Infrastructure Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5280-133">Группа инфраструктуры</span><span class="sxs-lookup"><span data-stu-id="a5280-133">Infrastructure group</span></span></th>
<th><span data-ttu-id="a5280-134">Описание</span><span class="sxs-lookup"><span data-stu-id="a5280-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5280-135">Рткуниверсалглобалвритеграуп</span><span class="sxs-lookup"><span data-stu-id="a5280-135">RTCUniversalGlobalWriteGroup</span></span></p></td>
<td><p><span data-ttu-id="a5280-136">Предоставление доступа на запись к глобальным объектам параметров для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a5280-136">Grants write access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5280-137">Рткуниверсалглобалреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="a5280-137">RTCUniversalGlobalReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a5280-138">Предоставляет доступ только для чтения к глобальным объектам параметров для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a5280-138">Grants read-only access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5280-139">Рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="a5280-139">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a5280-140">Предоставляет доступ только для чтения к параметрам пользователя Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a5280-140">Grants read-only access to Lync Server user settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5280-141">Рткуниверсалсерверреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="a5280-141">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a5280-142">Предоставляет доступ только для чтения к параметрам Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a5280-142">Grants read-only access to Lync Server settings.</span></span> <span data-ttu-id="a5280-143">У этой группы нет доступа к параметрам уровня группы, только к параметрам, относящимся к отдельному серверу.</span><span class="sxs-lookup"><span data-stu-id="a5280-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5280-144">РткуниверсалсбатечниЦианс</span><span class="sxs-lookup"><span data-stu-id="a5280-144">RTCUniversalSBATechnicians</span></span></p></td>
<td><p><span data-ttu-id="a5280-145">Предоставляет доступ только для чтения к конфигурации Lync Server и помещается в локальную группу администраторов для бесперебойных устройств филиала во время установки.</span><span class="sxs-lookup"><span data-stu-id="a5280-145">Grants read-only access to Lync Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a5280-146">В приведенной ниже таблице описаны группы служб.</span><span class="sxs-lookup"><span data-stu-id="a5280-146">The following table describes the service groups.</span></span>

### <a name="service-groups-created-during-forest-preparation"></a><span data-ttu-id="a5280-147">Группы служб, созданные во время подготовки леса</span><span class="sxs-lookup"><span data-stu-id="a5280-147">Service Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5280-148">Группа "Сервис"</span><span class="sxs-lookup"><span data-stu-id="a5280-148">Service group</span></span></th>
<th><span data-ttu-id="a5280-149">Описание</span><span class="sxs-lookup"><span data-stu-id="a5280-149">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5280-150">Ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="a5280-150">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="a5280-151">Включает служебные учетные записи, используемые для запуска серверного сервера и сервера стандартных выпусков.</span><span class="sxs-lookup"><span data-stu-id="a5280-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="a5280-152">Эта группа позволяет серверам просматривать и записывать доступ к глобальным параметрам Lync Server и объектам пользователей Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a5280-152">This group allows servers read/write access to Lync Server global settings and Active Directory user objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5280-153">Ртккомпонентуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="a5280-153">RTCComponentUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="a5280-154">Включает служебные учетные записи, которые используются для работы серверов конференц-связи, веб-служб, сервера исправлений, сервера архивирования и сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="a5280-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5280-155">Рткпроксюниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="a5280-155">RTCProxyUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="a5280-156">Включает учетные записи служб, используемые для выполнения пограничных серверов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a5280-156">Includes service accounts used to run Lync Server Edge Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5280-157">Рткуниверсалконфигрепликатор</span><span class="sxs-lookup"><span data-stu-id="a5280-157">RTCUniversalConfigReplicator</span></span></p></td>
<td><p><span data-ttu-id="a5280-158">Включает серверы, которые могут принимать участие в репликации в магазине Lync Server Central Management.</span><span class="sxs-lookup"><span data-stu-id="a5280-158">Includes servers that can participate in Lync Server Central Management store replication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5280-159">Ртксбауниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="a5280-159">RTCSBAUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="a5280-160">Предоставляет доступ только для чтения к параметрам Lync Server, но позволяет настроить конфигурацию для установления работающего сервера филиала и для бесперебойной конфигурации устройства филиала.</span><span class="sxs-lookup"><span data-stu-id="a5280-160">Grants read-only access to Lync Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a5280-161">После подготовки леса в соответствующие группы инфраструктуры добавляются группы служб и администрирования, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="a5280-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

  - <span data-ttu-id="a5280-162">Рткуниверсалсерверадминс добавляется в Рткуниверсалглобалреадонлиграуп, Рткуниверсалглобалвритеграуп, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="a5280-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="a5280-163">Рткуниверсалусерадминс добавляется как член из Рткуниверсалглобалреадонлиграуп, Рткуниверсалсерверреадонлиграуп и RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="a5280-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="a5280-164">Ртчсуниверсалсервицес, Ртккомпонентуниверсалсервицес и Рткуниверсалреадонлядминс добавляются как члены RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="a5280-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="a5280-165">При подготовке леса также создаются следующие группы управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="a5280-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

  - <span data-ttu-id="a5280-166">Ксадминистратор</span><span class="sxs-lookup"><span data-stu-id="a5280-166">CSAdministrator</span></span>

  - <span data-ttu-id="a5280-167">Ксарчивингадминистратор</span><span class="sxs-lookup"><span data-stu-id="a5280-167">CSArchivingAdministrator</span></span>

  - <span data-ttu-id="a5280-168">Кшелпдеск</span><span class="sxs-lookup"><span data-stu-id="a5280-168">CSHelpDesk</span></span>

  - <span data-ttu-id="a5280-169">Кслокатионадминистратор</span><span class="sxs-lookup"><span data-stu-id="a5280-169">CSLocationAdministrator</span></span>

  - <span data-ttu-id="a5280-170">Ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="a5280-170">CSResponseGroupAdministrator</span></span>

  - <span data-ttu-id="a5280-171">Кссерверадминистратор</span><span class="sxs-lookup"><span data-stu-id="a5280-171">CSServerAdministrator</span></span>

  - <span data-ttu-id="a5280-172">Ксусерадминистратор</span><span class="sxs-lookup"><span data-stu-id="a5280-172">CSUserAdministrator</span></span>

  - <span data-ttu-id="a5280-173">Ксвиевонлядминистратор</span><span class="sxs-lookup"><span data-stu-id="a5280-173">CSViewOnlyAdministrator</span></span>

  - <span data-ttu-id="a5280-174">Ксвоицеадминистратор</span><span class="sxs-lookup"><span data-stu-id="a5280-174">CSVoiceAdministrator</span></span>

  - <span data-ttu-id="a5280-175">Ксперсистентчатадминистатор</span><span class="sxs-lookup"><span data-stu-id="a5280-175">CsPersistentChatAdministator</span></span>

  - <span data-ttu-id="a5280-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="a5280-176">CsResponseGroupManager</span></span>

<span data-ttu-id="a5280-177">Подробные сведения о ролях RBAC и допустимых задачах можно найти [в разделе Планирование управления доступом на основе ролей в Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="a5280-177">For details about RBAC roles and the tasks allowed for each, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="a5280-178">Подготовка леса создает как закрытые, так и общедоступные элементы управления доступом.</span><span class="sxs-lookup"><span data-stu-id="a5280-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="a5280-179">Он создает закрытые записи ACE в контейнере глобальных параметров, используемом в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a5280-179">It creates private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="a5280-180">Этот контейнер используется только приложением Lync Server и находится в контейнере Configuration или контейнере System в корневом домене в зависимости от того, где хранятся глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="a5280-180">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="a5280-181">Общедоступные ACE, созданные с помощью подготовки леса, перечислены в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="a5280-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

### <a name="public-aces-created-by-forest-preparation"></a><span data-ttu-id="a5280-182">Общедоступные ACE, созданные с помощью подготовки леса</span><span class="sxs-lookup"><span data-stu-id="a5280-182">Public ACEs created by Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5280-183">РЕЗУЛЬТИРУЮЩ</span><span class="sxs-lookup"><span data-stu-id="a5280-183">ACE</span></span></th>
<th><span data-ttu-id="a5280-184">Рткуниверсалглобалреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="a5280-184">RTCUniversalGlobalReadOnlyGroup</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5280-185">Чтение контейнера корневого домена системы (не наследуется)<strong>\*</strong></span><span class="sxs-lookup"><span data-stu-id="a5280-185">Read root domain System Container (not inherited)<strong>\*</strong></span></span></p></td>
<td><p><span data-ttu-id="a5280-186">X</span><span class="sxs-lookup"><span data-stu-id="a5280-186">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5280-187">ДисплайспеЦифиерс контейнер конфигурации чтения (не унаследовано)</span><span class="sxs-lookup"><span data-stu-id="a5280-187">Read Configuration’s DisplaySpecifiers container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="a5280-188">X</span><span class="sxs-lookup"><span data-stu-id="a5280-188">X</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a5280-189"><STRONG>\*</STRONG>ACE, не унаследованные, не предоставляют доступ к дочерним объектам в этих контейнерах.</span><span class="sxs-lookup"><span data-stu-id="a5280-189"><STRONG>\*</STRONG>ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="a5280-190">ACE, наследуемые предоставлением разрешения на доступ к дочерним объектам в этих контейнерах.</span><span class="sxs-lookup"><span data-stu-id="a5280-190">ACEs that are inherited grant access to child objects under these containers.</span></span>



</div>

<span data-ttu-id="a5280-191">В контейнере конфигурации в разделе контекст именования конфигурации для подготовки леса выполняются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="a5280-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

  - <span data-ttu-id="a5280-192">Добавляет запись **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** на странице **свойств RTC** под атрибутами админконтекстмену и админпропертипажес в описателе языка для пользователей, контактов и ИНЕТОРГПЕРСОНС (например, CN = User-Display, CN = 409, CN = ДисплайспеЦифиерс).</span><span class="sxs-lookup"><span data-stu-id="a5280-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="a5280-193">Добавляет объект **рткпропертисет** типа **Контролакцессригхт** в разделе **Extended-Rights** , который относится к классу пользователя и контакту.</span><span class="sxs-lookup"><span data-stu-id="a5280-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

  - <span data-ttu-id="a5280-194">Добавляет объект **рткусерсеарчпропертисет** типа **Контролакцессригхт** в разделе **Расширенные права** , применимые к классам пользователь, контакт, OU и домаинднс.</span><span class="sxs-lookup"><span data-stu-id="a5280-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

  - <span data-ttu-id="a5280-195">Добавляет **msRTCSIP-примарюсераддресс** в атрибут **екстраколумнс** для спецификатора отображения (например, CN = ОРГАНИЗАТИОНАЛУНИТ-Display, CN = 409, CN = дисплайспеЦифиерс) и копирует значения атрибут **екстраколумнс** дисплея по умолчанию (например, CN = по умолчанию-Display, CN = 409, CN = дисплайспеЦифиерс).</span><span class="sxs-lookup"><span data-stu-id="a5280-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="a5280-196">Добавляются атрибуты фильтрации **msRTCSIP-примарюсераддресс**, **msRTCSIP-примарихомесервер**и **msRTCSIP-UserEnabled** в атрибуте **Аттрибутедисплайнамес** каждого спецификатора отображения языка для пользователей, контактов и объекты InetOrgPerson (например, на английском языке: CN = User-Display, CN = 409, CN = ДисплайспеЦифиерс).</span><span class="sxs-lookup"><span data-stu-id="a5280-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

