---
title: Изменения, внесенные в процессе подготовки леса в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: В этом разделе описаны глобальные параметры и объекты, а также универсальные службы и группы администрирования, созданные на этапе подготовки леса.
ms.openlocfilehash: 26917915d89aff721e74f094eb8ad5bb72db3cf6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815537"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a><span data-ttu-id="0b498-103">Изменения, внесенные в процессе подготовки леса в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="0b498-103">Changes made by forest preparation in Skype for Business Server</span></span>

<span data-ttu-id="0b498-104">В этом разделе описаны глобальные параметры и объекты, а также универсальные службы и группы администрирования, созданные на этапе подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="0b498-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="0b498-105">Глобальные параметры и объекты в службе каталогов Active Directory</span><span class="sxs-lookup"><span data-stu-id="0b498-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="0b498-106">Если вы сохраняете глобальные параметры в контейнере конфигурации (как это происходит для всех новых развертываний сервера Skype для бизнеса), подготовка леса использует существующий контейнер служб и добавляет объект **службы RTC** в объект конфигуратион\сервицес.</span><span class="sxs-lookup"><span data-stu-id="0b498-106">If you store global settings in the Configuration container (as is the case for all new Skype for Business Server deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\Services object.</span></span> <span data-ttu-id="0b498-107">В разделе объект службы RTC для подготовки леса добавляется **глобальный объект параметров** типа MsRTCSIP-глобалконтаинер.</span><span class="sxs-lookup"><span data-stu-id="0b498-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="0b498-108">Объект глобальных параметров содержит все параметры, которые применяются к развертыванию сервера Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b498-108">The global settings object holds all the settings that apply to the Skype for Business Server deployment.</span></span> <span data-ttu-id="0b498-109">При хранении глобальных параметров в контейнере System для подготовки леса используется контейнер Microsoft из контейнера System корневого домена и объект службы RTC в объекте Систем\микрософт.</span><span class="sxs-lookup"><span data-stu-id="0b498-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\Microsoft object.</span></span>

<span data-ttu-id="0b498-110">Подготовка леса также добавляет новый объект **msRTCSIP-Domain** для корневого домена, в котором выполняется процедура.</span><span class="sxs-lookup"><span data-stu-id="0b498-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="0b498-111">Универсальные службы и группы администрирования Active Directory</span><span class="sxs-lookup"><span data-stu-id="0b498-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="0b498-112">Подготовка леса создает универсальные группы на основе указанного домена и добавляет элементы управления доступом (ACE) для этих групп.</span><span class="sxs-lookup"><span data-stu-id="0b498-112">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups.</span></span> <span data-ttu-id="0b498-113">На этом этапе создаются универсальные группы в контейнерах пользователей указанного домена.</span><span class="sxs-lookup"><span data-stu-id="0b498-113">This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="0b498-114">Универсальные группы позволяют администраторам получать доступ к глобальным параметрам и службам и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="0b498-114">Universal groups allow administrators to access and manage global settings and services.</span></span> <span data-ttu-id="0b498-115">Подготовка леса добавляет следующие типы универсальных групп:</span><span class="sxs-lookup"><span data-stu-id="0b498-115">Forest preparation adds the following types of universal groups:</span></span>

- <span data-ttu-id="0b498-116">**Административные группы** Эти группы определяют роли администратора для сети Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b498-116">**Administrative groups** These groups define administrator roles for a Skype for Business Server network.</span></span>

- <span data-ttu-id="0b498-117">**Группы инфраструктуры** Эти группы предоставляют разрешения на доступ к определенным областям инфраструктуры Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b498-117">**Infrastructure groups** These groups provide permission to access specific areas of the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="0b498-118">Они будут работать как компоненты административных групп.</span><span class="sxs-lookup"><span data-stu-id="0b498-118">They function as components of administrative groups.</span></span> <span data-ttu-id="0b498-119">Не следует изменять эти группы и добавлять пользователей прямо в них.</span><span class="sxs-lookup"><span data-stu-id="0b498-119">You should not modify these groups or add users directly to them.</span></span>

- <span data-ttu-id="0b498-120">**Группы служб** Эти группы представляют собой учетные записи служб, необходимые для доступа к различным службам Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b498-120">**Service groups** These groups are service accounts that are required to access various Skype for Business Server services.</span></span>

<span data-ttu-id="0b498-121">В приведенной ниже таблице описаны группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="0b498-121">The following table describes the administrative groups.</span></span>

<span data-ttu-id="0b498-122">**Административные группы, созданные во время подготовки леса**</span><span class="sxs-lookup"><span data-stu-id="0b498-122">**Administrative Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="0b498-123">**Группа администраторов**</span><span class="sxs-lookup"><span data-stu-id="0b498-123">**Administrative group**</span></span>|<span data-ttu-id="0b498-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0b498-124">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0b498-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0b498-125">RTCUniversalServerAdmins</span></span>  <br/> |<span data-ttu-id="0b498-126">Позволяет пользователям управлять параметрами сервера и пула, включая все роли сервера, глобальные параметры и пользователей.</span><span class="sxs-lookup"><span data-stu-id="0b498-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span>  <br/> |
|<span data-ttu-id="0b498-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="0b498-127">RTCUniversalUserAdmins</span></span>  <br/> |<span data-ttu-id="0b498-128">Позволяет пользователям управлять параметрами пользователей и перемещать пользователей из одного сервера или пула в другой.</span><span class="sxs-lookup"><span data-stu-id="0b498-128">Allows members to manage user settings and move users from one server or pool to another.</span></span>  <br/> |
|<span data-ttu-id="0b498-129">рткуниверсалреадонлядминс</span><span class="sxs-lookup"><span data-stu-id="0b498-129">RTCUniversalReadOnlyAdmins</span></span>  <br/> |<span data-ttu-id="0b498-130">Позволяет участникам читать параметры сервера, пула и пользователей.</span><span class="sxs-lookup"><span data-stu-id="0b498-130">Allows members to read server, pool, and user settings.</span></span>  <br/> |

<span data-ttu-id="0b498-131">В приведенной ниже таблице описаны группы инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="0b498-131">The following table describes the infrastructure groups.</span></span>

<span data-ttu-id="0b498-132">**Группы инфраструктуры, созданные во время подготовки леса**</span><span class="sxs-lookup"><span data-stu-id="0b498-132">**Infrastructure Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="0b498-133">**Группа инфраструктуры**</span><span class="sxs-lookup"><span data-stu-id="0b498-133">**Infrastructure group**</span></span>|<span data-ttu-id="0b498-134">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0b498-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0b498-135">рткуниверсалглобалвритеграуп</span><span class="sxs-lookup"><span data-stu-id="0b498-135">RTCUniversalGlobalWriteGroup</span></span>  <br/> |<span data-ttu-id="0b498-136">Предоставление доступа на запись к глобальным объектам параметров для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b498-136">Grants write access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="0b498-137">рткуниверсалглобалреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="0b498-137">RTCUniversalGlobalReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="0b498-138">Предоставление доступа только для чтения к глобальным объектам параметров для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b498-138">Grants read-only access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="0b498-139">рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="0b498-139">RTCUniversalUserReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="0b498-140">Предоставление доступа только для чтения к параметрам пользователя в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b498-140">Grants read-only access to Skype for Business Server user settings.</span></span>  <br/> |
|<span data-ttu-id="0b498-141">рткуниверсалсерверреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="0b498-141">RTCUniversalServerReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="0b498-142">Предоставление доступа только для чтения к параметрам Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b498-142">Grants read-only access to Skype for Business Server settings.</span></span> <span data-ttu-id="0b498-143">У этой группы нет доступа к параметрам уровня группы, только к параметрам, относящимся к отдельному серверу.</span><span class="sxs-lookup"><span data-stu-id="0b498-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span>  <br/> |
|<span data-ttu-id="0b498-144">рткуниверсалсбатечниЦианс</span><span class="sxs-lookup"><span data-stu-id="0b498-144">RTCUniversalSBATechnicians</span></span>  <br/> |<span data-ttu-id="0b498-145">Предоставление доступа только для чтения к конфигурации Skype для бизнеса Server и помещается в локальную группу администраторов для бесперебойных устройств филиала во время установки.</span><span class="sxs-lookup"><span data-stu-id="0b498-145">Grants read-only access to Skype for Business Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span>  <br/> |

<span data-ttu-id="0b498-146">В приведенной ниже таблице описаны группы служб.</span><span class="sxs-lookup"><span data-stu-id="0b498-146">The following table describes the service groups.</span></span>

<span data-ttu-id="0b498-147">**Группы служб, созданные во время подготовки леса**</span><span class="sxs-lookup"><span data-stu-id="0b498-147">**Service Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="0b498-148">**Группа "Сервис"**</span><span class="sxs-lookup"><span data-stu-id="0b498-148">**Service group**</span></span>|<span data-ttu-id="0b498-149">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0b498-149">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0b498-150">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="0b498-150">RTCHSUniversalServices</span></span>  <br/> |<span data-ttu-id="0b498-151">Включает служебные учетные записи, используемые для запуска серверного сервера и сервера стандартных выпусков.</span><span class="sxs-lookup"><span data-stu-id="0b498-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="0b498-152">Эта группа позволяет серверам просматривать и записывать доступ к глобальным параметрам и объектам пользователей Active Directory в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b498-152">This group allows servers read/write access to Skype for Business Server global settings and Active Directory user objects.</span></span>  <br/> |
|<span data-ttu-id="0b498-153">ртккомпонентуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="0b498-153">RTCComponentUniversalServices</span></span>  <br/> |<span data-ttu-id="0b498-154">Включает служебные учетные записи, которые используются для работы серверов конференц-связи, веб-служб, сервера исправлений, сервера архивирования и сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="0b498-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span>  <br/> |
|<span data-ttu-id="0b498-155">рткпроксюниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="0b498-155">RTCProxyUniversalServices</span></span>  <br/> |<span data-ttu-id="0b498-156">Включает служебные учетные записи, которые используются для запуска пограничного сервера Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b498-156">Includes service accounts used to run Skype for Business Server Edge Servers.</span></span>  <br/> |
|<span data-ttu-id="0b498-157">рткуниверсалконфигрепликатор</span><span class="sxs-lookup"><span data-stu-id="0b498-157">RTCUniversalConfigReplicator</span></span>  <br/> |<span data-ttu-id="0b498-158">Включает серверы, которые могут принимать участие в репликации хранилища централизованного управления в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b498-158">Includes servers that can participate in Skype for Business Server Central Management store replication.</span></span>  <br/> |
|<span data-ttu-id="0b498-159">ртксбауниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="0b498-159">RTCSBAUniversalServices</span></span>  <br/> |<span data-ttu-id="0b498-160">Предоставление доступа только для чтения к параметрам Skype для бизнеса Server, но позволяет настроить конфигурацию для установки работающего сервера филиала и работающего развертывания устройства филиала.</span><span class="sxs-lookup"><span data-stu-id="0b498-160">Grants read-only access to Skype for Business Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span>  <br/> |

<span data-ttu-id="0b498-161">После подготовки леса в соответствующие группы инфраструктуры добавляются группы служб и администрирования, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="0b498-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

- <span data-ttu-id="0b498-162">Рткуниверсалсерверадминс добавляется в Рткуниверсалглобалреадонлиграуп, Рткуниверсалглобалвритеграуп, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="0b498-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="0b498-163">Рткуниверсалусерадминс добавляется как член из Рткуниверсалглобалреадонлиграуп, Рткуниверсалсерверреадонлиграуп и RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="0b498-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="0b498-164">Ртчсуниверсалсервицес, Ртккомпонентуниверсалсервицес и Рткуниверсалреадонлядминс добавляются как члены RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="0b498-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="0b498-165">При подготовке леса также создаются следующие группы управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="0b498-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

- <span data-ttu-id="0b498-166">ксадминистратор</span><span class="sxs-lookup"><span data-stu-id="0b498-166">CSAdministrator</span></span>

- <span data-ttu-id="0b498-167">ксарчивингадминистратор</span><span class="sxs-lookup"><span data-stu-id="0b498-167">CSArchivingAdministrator</span></span>

- <span data-ttu-id="0b498-168">кшелпдеск</span><span class="sxs-lookup"><span data-stu-id="0b498-168">CSHelpDesk</span></span>

- <span data-ttu-id="0b498-169">кслокатионадминистратор</span><span class="sxs-lookup"><span data-stu-id="0b498-169">CSLocationAdministrator</span></span>

- <span data-ttu-id="0b498-170">ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="0b498-170">CSResponseGroupAdministrator</span></span>

- <span data-ttu-id="0b498-171">кссерверадминистратор</span><span class="sxs-lookup"><span data-stu-id="0b498-171">CSServerAdministrator</span></span>

- <span data-ttu-id="0b498-172">ксусерадминистратор</span><span class="sxs-lookup"><span data-stu-id="0b498-172">CSUserAdministrator</span></span>

- <span data-ttu-id="0b498-173">ксвиевонлядминистратор</span><span class="sxs-lookup"><span data-stu-id="0b498-173">CSViewOnlyAdministrator</span></span>

- <span data-ttu-id="0b498-174">ксвоицеадминистратор</span><span class="sxs-lookup"><span data-stu-id="0b498-174">CSVoiceAdministrator</span></span>

- <span data-ttu-id="0b498-175">ксперсистентчатадминистатор</span><span class="sxs-lookup"><span data-stu-id="0b498-175">CsPersistentChatAdministator</span></span>

- <span data-ttu-id="0b498-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="0b498-176">CsResponseGroupManager</span></span>

<span data-ttu-id="0b498-177">Сведения о ролях RBAC и допустимых задачах можно найти в разделе [Управление доступом на основе ролей](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="0b498-177">For details about RBAC roles and the tasks allowed for each, see [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="0b498-178">Подготовка леса создает как закрытые, так и общедоступные элементы управления доступом.</span><span class="sxs-lookup"><span data-stu-id="0b498-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="0b498-179">Она создает закрытые записи ACE в контейнере глобальных параметров, используемом в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b498-179">It creates private ACEs on the global settings container used by Skype for Business Server.</span></span> <span data-ttu-id="0b498-180">Этот контейнер используется только в Skype для бизнеса Server и находится в контейнере конфигурации или контейнере System в корневом домене (в зависимости от того, где хранятся глобальные параметры).</span><span class="sxs-lookup"><span data-stu-id="0b498-180">This container is used only by Skype for Business Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="0b498-181">Общедоступные ACE, созданные с помощью подготовки леса, перечислены в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="0b498-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

<span data-ttu-id="0b498-182">**Общедоступные ACE, созданные с помощью подготовки леса**</span><span class="sxs-lookup"><span data-stu-id="0b498-182">**Public ACEs created by Forest Preparation**</span></span>


| <span data-ttu-id="0b498-183">**РЕЗУЛЬТИРУЮЩ**</span><span class="sxs-lookup"><span data-stu-id="0b498-183">**ACE**</span></span>                                                                 | <span data-ttu-id="0b498-184">**рткуниверсалглобалреадонлиграуп**</span><span class="sxs-lookup"><span data-stu-id="0b498-184">**RTCUniversalGlobalReadOnlyGroup**</span></span> |
|:------------------------------------------------------------------------|:------------------------------------|
| <span data-ttu-id="0b498-185">Чтение контейнера корневого домена системы (не наследуется)**\\**\*</span><span class="sxs-lookup"><span data-stu-id="0b498-185">Read root domain System Container (not inherited) **\\**\*</span></span> <br/>        | <span data-ttu-id="0b498-186">X</span><span class="sxs-lookup"><span data-stu-id="0b498-186">X</span></span>  <br/>                            |
| <span data-ttu-id="0b498-187">ДисплайспеЦифиерс контейнер конфигурации чтения (не унаследовано)</span><span class="sxs-lookup"><span data-stu-id="0b498-187">Read Configuration's DisplaySpecifiers container (not inherited)</span></span>  <br/> | <span data-ttu-id="0b498-188">X</span><span class="sxs-lookup"><span data-stu-id="0b498-188">X</span></span>  <br/>                            |

> [!NOTE]
> <span data-ttu-id="0b498-189"><strong>\\</strong>\* Неунаследованные ACE не предоставляют доступ к дочерним объектам в этих контейнерах.</span><span class="sxs-lookup"><span data-stu-id="0b498-189"><strong>\\</strong>\*ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="0b498-190">ACE, наследуемые предоставлением разрешения на доступ к дочерним объектам в этих контейнерах.</span><span class="sxs-lookup"><span data-stu-id="0b498-190">ACEs that are inherited grant access to child objects under these containers.</span></span>

<span data-ttu-id="0b498-191">В контейнере конфигурации в разделе контекст именования конфигурации для подготовки леса выполняются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="0b498-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

- <span data-ttu-id="0b498-192">Добавляет запись **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** для страницы **Свойства RTC** в соответствии с атрибутами админконтекстмену и админпропертипажес в описателе языка для пользователей, контактов и ИНЕТОРГПЕРСОНС (например, CN = User-Display, CN = 409, CN = дисплайспеЦифиерс).</span><span class="sxs-lookup"><span data-stu-id="0b498-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="0b498-193">Добавляет объект **рткпропертисет** типа **Контролакцессригхт** в разделе **Extended-Rights** , который относится к классу пользователя и контакту.</span><span class="sxs-lookup"><span data-stu-id="0b498-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

- <span data-ttu-id="0b498-194">Добавляет объект **рткусерсеарчпропертисет** типа **Контролакцессригхт** в разделе **Расширенные права** , применимые к классам пользователь, контакт, OU и домаинднс.</span><span class="sxs-lookup"><span data-stu-id="0b498-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

- <span data-ttu-id="0b498-195">Добавляет **msRTCSIP-примарюсераддресс** в атрибуте **екстраколумнс** для описателя отображения каждого из языков (например, CN = ОРГАНИЗАТИОНАЛУНИТ-Display, CN = 409, CN = дисплайспеЦифиерс) и копирует значения атрибута **екстраколумнс** дисплея по умолчанию (например, CN = Default-Display, CN = 409, CN = DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="0b498-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="0b498-196">Добавляются атрибуты фильтрации **msRTCSIP-примарюсераддресс**, **msRTCSIP-примарихомесервер**и **msRTCSIP-UserEnabled** в атрибуте **Аттрибутедисплайнамес** каждого спецификатора отображения языка для пользователей, контактов и объектов INETORGPERSON (например, на английском языке: CN = User-Display, CN = 409, CN = дисплайспеЦифиерс).</span><span class="sxs-lookup"><span data-stu-id="0b498-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>


