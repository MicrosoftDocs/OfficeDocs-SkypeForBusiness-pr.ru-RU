---
title: Изменения, внесенные в ходе подготовки леса в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: В данном разделе описываются глобальные параметры и объекты, а также универсальные группы служб и административные группы, создаваемые на этапе подготовки леса.
ms.openlocfilehash: 4e8032cb91b012c710dc509708a813d55825f7a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831919"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a><span data-ttu-id="72450-103">Изменения, внесенные в ходе подготовки леса в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="72450-103">Changes made by forest preparation in Skype for Business Server</span></span>

<span data-ttu-id="72450-104">В данном разделе описываются глобальные параметры и объекты, а также универсальные группы служб и административные группы, создаваемые на этапе подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="72450-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="72450-105">Глобальные параметры и объекты Active Directory</span><span class="sxs-lookup"><span data-stu-id="72450-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="72450-106">Если глобальные параметры хранятся в контейнере Configuration (как и для всех новых развертывании Skype для бизнеса Server), при подготовке леса используется существующий контейнер служб и добавляется объект **службы RTC** в объект Configuration\Services.</span><span class="sxs-lookup"><span data-stu-id="72450-106">If you store global settings in the Configuration container (as is the case for all new Skype for Business Server deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\Services object.</span></span> <span data-ttu-id="72450-107">В объект RTC Service процедура подготовки лета добавляет объект **Global Settings** типа msRTCSIP-GlobalContainer.</span><span class="sxs-lookup"><span data-stu-id="72450-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="72450-108">Объект глобальных параметров содержит все параметры, которые применяются к развертыванию Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="72450-108">The global settings object holds all the settings that apply to the Skype for Business Server deployment.</span></span> <span data-ttu-id="72450-109">Если вы храните глобальные параметры в контейнере System, процедура подготовки леса использует контейнер Microsoft в контейнере System корневого домена и объект RTC Service в объекте System\Microsoft.</span><span class="sxs-lookup"><span data-stu-id="72450-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\Microsoft object.</span></span>

<span data-ttu-id="72450-110">Процедура подготовки леса также добавляет новый объект **msRTCSIP-Domain** для корневого домена, в котором выполняется процедура.</span><span class="sxs-lookup"><span data-stu-id="72450-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="72450-111">Универсальные группы служб и административные группы Active Directory</span><span class="sxs-lookup"><span data-stu-id="72450-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="72450-p102">Процедура подготовки леса создает универсальные группы на основании указанного вами домена и добавляет для этих групп элементы управления доступом (ACE). На данном этапе универсальные группы создаются в контейнерах User указанного вами домена.</span><span class="sxs-lookup"><span data-stu-id="72450-p102">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups. This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="72450-p103">Универсальные группы позволяют администраторам осуществлять доступ к глобальным параметрам и службам и управлять ими. Процедура подготовки леса добавляет следующие типы универсальных групп:</span><span class="sxs-lookup"><span data-stu-id="72450-p103">Universal groups allow administrators to access and manage global settings and services. Forest preparation adds the following types of universal groups:</span></span>

- <span data-ttu-id="72450-116">**Административные группы** Эти группы определяют роли администратора для сети Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="72450-116">**Administrative groups** These groups define administrator roles for a Skype for Business Server network.</span></span>

- <span data-ttu-id="72450-117">**Группы инфраструктуры** Эти группы предоставляют разрешения на доступ к определенным областям инфраструктуры Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="72450-117">**Infrastructure groups** These groups provide permission to access specific areas of the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="72450-118">Они выступают в качестве компонентов административных групп.</span><span class="sxs-lookup"><span data-stu-id="72450-118">They function as components of administrative groups.</span></span> <span data-ttu-id="72450-119">Вам не следует изменять эти группы или добавлять пользователей непосредственно в них.</span><span class="sxs-lookup"><span data-stu-id="72450-119">You should not modify these groups or add users directly to them.</span></span>

- <span data-ttu-id="72450-120">**Группы служб** Эти группы — это учетные записи служб, необходимые для доступа к различным службам Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="72450-120">**Service groups** These groups are service accounts that are required to access various Skype for Business Server services.</span></span>

<span data-ttu-id="72450-121">В следующей таблице описываются административные группы.</span><span class="sxs-lookup"><span data-stu-id="72450-121">The following table describes the administrative groups.</span></span>

<span data-ttu-id="72450-122">**Административные группы, созданные во время подготовки леса**</span><span class="sxs-lookup"><span data-stu-id="72450-122">**Administrative Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="72450-123">**Административная группа**</span><span class="sxs-lookup"><span data-stu-id="72450-123">**Administrative group**</span></span>|<span data-ttu-id="72450-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="72450-124">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="72450-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="72450-125">RTCUniversalServerAdmins</span></span>  <br/> |<span data-ttu-id="72450-126">Позволяет членам управлять параметрами серверов и пулов, включая все роли сервера, глобальные параметры и пользователей.</span><span class="sxs-lookup"><span data-stu-id="72450-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span>  <br/> |
|<span data-ttu-id="72450-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="72450-127">RTCUniversalUserAdmins</span></span>  <br/> |<span data-ttu-id="72450-128">Позволяет членам управлять параметрами пользователей и перемещать пользователей из одного сервера или пула в другой.</span><span class="sxs-lookup"><span data-stu-id="72450-128">Allows members to manage user settings and move users from one server or pool to another.</span></span>  <br/> |
|<span data-ttu-id="72450-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="72450-129">RTCUniversalReadOnlyAdmins</span></span>  <br/> |<span data-ttu-id="72450-130">Позволяет членам считывать параметры серверов, пулов и пользователей.</span><span class="sxs-lookup"><span data-stu-id="72450-130">Allows members to read server, pool, and user settings.</span></span>  <br/> |

<span data-ttu-id="72450-131">В следующей таблице описываются группы инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="72450-131">The following table describes the infrastructure groups.</span></span>

<span data-ttu-id="72450-132">**Группы инфраструктуры, созданные во время подготовки леса**</span><span class="sxs-lookup"><span data-stu-id="72450-132">**Infrastructure Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="72450-133">**Группа инфраструктуры**</span><span class="sxs-lookup"><span data-stu-id="72450-133">**Infrastructure group**</span></span>|<span data-ttu-id="72450-134">**Описание**</span><span class="sxs-lookup"><span data-stu-id="72450-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="72450-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="72450-135">RTCUniversalGlobalWriteGroup</span></span>  <br/> |<span data-ttu-id="72450-136">Предоставляет доступ на запись к объектам глобальных параметров для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="72450-136">Grants write access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="72450-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="72450-137">RTCUniversalGlobalReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="72450-138">Предоставляет доступ только для чтения к объектам глобальных параметров для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="72450-138">Grants read-only access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="72450-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="72450-139">RTCUniversalUserReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="72450-140">Предоставляет доступ только для чтения к пользовательским настройкам Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="72450-140">Grants read-only access to Skype for Business Server user settings.</span></span>  <br/> |
|<span data-ttu-id="72450-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="72450-141">RTCUniversalServerReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="72450-142">Предоставляет доступ только для чтения к настройкам Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="72450-142">Grants read-only access to Skype for Business Server settings.</span></span> <span data-ttu-id="72450-143">Данная группа не имеет доступа к параметрам уровня пулов, ей доступны только параметры для отдельного сервера.</span><span class="sxs-lookup"><span data-stu-id="72450-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span>  <br/> |
|<span data-ttu-id="72450-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="72450-144">RTCUniversalSBATechnicians</span></span>  <br/> |<span data-ttu-id="72450-145">Предоставляет доступ только для чтения к конфигурации Skype для бизнеса Server и помещается в группу локальных администраторов устройств для survivable branch во время установки.</span><span class="sxs-lookup"><span data-stu-id="72450-145">Grants read-only access to Skype for Business Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span>  <br/> |

<span data-ttu-id="72450-146">В следующей таблице описываются группы служб.</span><span class="sxs-lookup"><span data-stu-id="72450-146">The following table describes the service groups.</span></span>

<span data-ttu-id="72450-147">**Группы служб, созданные во время подготовки леса**</span><span class="sxs-lookup"><span data-stu-id="72450-147">**Service Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="72450-148">**Группа служб**</span><span class="sxs-lookup"><span data-stu-id="72450-148">**Service group**</span></span>|<span data-ttu-id="72450-149">**Описание**</span><span class="sxs-lookup"><span data-stu-id="72450-149">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="72450-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="72450-150">RTCHSUniversalServices</span></span>  <br/> |<span data-ttu-id="72450-151">Включает учетные записи служб, используемые для запуска серверов переднего сервера и сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="72450-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="72450-152">Эта группа позволяет серверам считывать и записывать доступ к глобальным настройкам Skype для бизнеса Server и объектам пользователей Active Directory.</span><span class="sxs-lookup"><span data-stu-id="72450-152">This group allows servers read/write access to Skype for Business Server global settings and Active Directory user objects.</span></span>  <br/> |
|<span data-ttu-id="72450-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="72450-153">RTCComponentUniversalServices</span></span>  <br/> |<span data-ttu-id="72450-154">Включает учетные записи служб, используемые для запуска серверов A/V Conferencing Server, веб-служб, сервера-посредника, сервера архивации и сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="72450-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span>  <br/> |
|<span data-ttu-id="72450-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="72450-155">RTCProxyUniversalServices</span></span>  <br/> |<span data-ttu-id="72450-156">Включает учетные записи служб, используемые для запуска серверов Skype для бизнеса Server Edge Server.</span><span class="sxs-lookup"><span data-stu-id="72450-156">Includes service accounts used to run Skype for Business Server Edge Servers.</span></span>  <br/> |
|<span data-ttu-id="72450-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="72450-157">RTCUniversalConfigReplicator</span></span>  <br/> |<span data-ttu-id="72450-158">Включает серверы, которые могут участвовать в репликации центрального банка управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="72450-158">Includes servers that can participate in Skype for Business Server Central Management store replication.</span></span>  <br/> |
|<span data-ttu-id="72450-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="72450-159">RTCSBAUniversalServices</span></span>  <br/> |<span data-ttu-id="72450-160">Предоставляет доступ только для чтения к настройкам Skype для бизнеса Server, но позволяет настраивать конфигурацию для установки сервера для survivable branch server и развертывания устройства для устройств для survivable branch appliance.</span><span class="sxs-lookup"><span data-stu-id="72450-160">Grants read-only access to Skype for Business Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span>  <br/> |

<span data-ttu-id="72450-161">После этого процедура подготовки леса добавляет группы служб и административные группы в соответствующие группы инфраструктуры следующим образом:</span><span class="sxs-lookup"><span data-stu-id="72450-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

- <span data-ttu-id="72450-162">RTCUniversalServerAdmins добавляется в RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="72450-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="72450-163">RTCUniversalUserAdmins добавляется в качестве члена групп RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="72450-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="72450-164">RTCHSUniversalServices, RTCComponentUniversalServices и RTCUniversalReadOnlyAdmins добавляются в качестве членов групп RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="72450-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="72450-165">Процедура подготовки леса также создает следующие группы управления доступом на основе ролей:</span><span class="sxs-lookup"><span data-stu-id="72450-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

- <span data-ttu-id="72450-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="72450-166">CSAdministrator</span></span>

- <span data-ttu-id="72450-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="72450-167">CSArchivingAdministrator</span></span>

- <span data-ttu-id="72450-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="72450-168">CSHelpDesk</span></span>

- <span data-ttu-id="72450-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="72450-169">CSLocationAdministrator</span></span>

- <span data-ttu-id="72450-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="72450-170">CSResponseGroupAdministrator</span></span>

- <span data-ttu-id="72450-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="72450-171">CSServerAdministrator</span></span>

- <span data-ttu-id="72450-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="72450-172">CSUserAdministrator</span></span>

- <span data-ttu-id="72450-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="72450-173">CSViewOnlyAdministrator</span></span>

- <span data-ttu-id="72450-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="72450-174">CSVoiceAdministrator</span></span>

- <span data-ttu-id="72450-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="72450-175">CsPersistentChatAdministator</span></span>

- <span data-ttu-id="72450-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="72450-176">CsResponseGroupManager</span></span>

<span data-ttu-id="72450-177">Дополнительные сведения о ролях управления доступом на основе ролей и задачах, разрешенных для каждой из них, см. в разделе [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="72450-177">For details about RBAC roles and the tasks allowed for each, see [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="72450-178">Процедура подготовки леса создает как частные, так и общие элементы управления доступом.</span><span class="sxs-lookup"><span data-stu-id="72450-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="72450-179">Он создает частные AES в контейнере глобальных параметров, используемом Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="72450-179">It creates private ACEs on the global settings container used by Skype for Business Server.</span></span> <span data-ttu-id="72450-180">Этот контейнер используется только Skype для бизнеса Server и расположен в контейнере Configuration или в контейнере System в корневом домене в зависимости от того, где хранятся глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="72450-180">This container is used only by Skype for Business Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="72450-181">В следующей таблице приведены общие элементы управления доступом, создаваемые процедурой подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="72450-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

<span data-ttu-id="72450-182">**Общие элементы управления доступом, создаваемые процедурой подготовки леса**</span><span class="sxs-lookup"><span data-stu-id="72450-182">**Public ACEs created by Forest Preparation**</span></span>


| <span data-ttu-id="72450-183">**ACE**</span><span class="sxs-lookup"><span data-stu-id="72450-183">**ACE**</span></span>                                                                 | <span data-ttu-id="72450-184">**RTCUniversalGlobalReadOnlyGroup**</span><span class="sxs-lookup"><span data-stu-id="72450-184">**RTCUniversalGlobalReadOnlyGroup**</span></span> |
|:------------------------------------------------------------------------|:------------------------------------|
| <span data-ttu-id="72450-185">Чтение системного контейнера корневого домена (не унаследовано) **\\**\*</span><span class="sxs-lookup"><span data-stu-id="72450-185">Read root domain System Container (not inherited) **\\**\*</span></span> <br/>        | <span data-ttu-id="72450-186">X</span><span class="sxs-lookup"><span data-stu-id="72450-186">X</span></span>  <br/>                            |
| <span data-ttu-id="72450-187">Чтение контейнера DisplaySpecifiers конфигурации (не наследуется)</span><span class="sxs-lookup"><span data-stu-id="72450-187">Read Configuration's DisplaySpecifiers container (not inherited)</span></span>  <br/> | <span data-ttu-id="72450-188">X</span><span class="sxs-lookup"><span data-stu-id="72450-188">X</span></span>  <br/>                            |

> [!NOTE]
> <span data-ttu-id="72450-189"><strong>\\</strong>\*AES, которые не наследуются, не предоставляет доступ к объектам-child в этих контейнерах.</span><span class="sxs-lookup"><span data-stu-id="72450-189"><strong>\\</strong>\*ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="72450-190">Наследуемые элементы управления доступом предоставляют доступ к дочерним объектам в таких контейнерах.</span><span class="sxs-lookup"><span data-stu-id="72450-190">ACEs that are inherited grant access to child objects under these containers.</span></span>

<span data-ttu-id="72450-191">В контейнере Configuration в контексте именования Configuration процедура подготовки леса выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="72450-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

- <span data-ttu-id="72450-192">Добавляет запись **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** для страницы **RTC property** в атрибутах adminContextMenu и adminPropertyPages описателя отображения языка для пользователей, контактов и InetOrgPersons (например, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="72450-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="72450-193">Добавляет объект **RTCPropertySet** типа **controlAccessRight** в **Extended-Rights**, применяемый к классам User и Contact.</span><span class="sxs-lookup"><span data-stu-id="72450-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

- <span data-ttu-id="72450-194">Добавляет объект **RTCUserSearchPropertySet** типа **controlAccessRight** в **Extended-Rights**, применяемый к классам User, Contact, OU и DomainDNS.</span><span class="sxs-lookup"><span data-stu-id="72450-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

- <span data-ttu-id="72450-195">Добавляет **msRTCSIP-PrimaryUserAddress** в атрибут **extraColumns** каждого описателя отображения языкового подразделения (например, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) и копирует значения атрибута **extraColumns** отображения по умолчанию (например, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="72450-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="72450-196">Добавляет атрибуты фильтрации **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** и **msRTCSIP-UserEnabled** в атрибут **attributeDisplayNames** каждого описателя отображения языка для объектов Users, Contacts и InetOrgPerson (например, для английского: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="72450-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>


