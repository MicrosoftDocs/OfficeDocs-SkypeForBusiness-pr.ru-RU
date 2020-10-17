---
title: 'Lync Server 2013: планирование управления доступом на основе ролей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65f6411023c80a527cff31c389a8283d090dfc0d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528036"
---
# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="b58bb-102">Планирование управления доступом на основе ролей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b58bb-102">Planning for role-based access control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b58bb-103">_**Последнее изменение темы:** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="b58bb-103">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="b58bb-104">Чтобы можно было делегировать административные задачи при поддержке высокого стандарта безопасности, Lync Server 2013 предлагает управление доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="b58bb-104">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="b58bb-105">При использовании функции RBAC привилегии администратора предоставляются путем назначения пользователям ролей администрирования.</span><span class="sxs-lookup"><span data-stu-id="b58bb-105">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="b58bb-106">Lync Server 2013 включает обширный набор встроенных административных ролей, а также позволяет создавать новые роли и указывать настраиваемый список командлетов для каждой новой роли.</span><span class="sxs-lookup"><span data-stu-id="b58bb-106">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="b58bb-107">Вы можете также добавлять сценарии командлетов в разрешенные задачи как предопределенных, так и пользовательских ролей RBAC.</span><span class="sxs-lookup"><span data-stu-id="b58bb-107">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="b58bb-108">Более эффективная централизация и обеспечение безопасности сервера</span><span class="sxs-lookup"><span data-stu-id="b58bb-108">Better Server Security and Centralization</span></span>

<span data-ttu-id="b58bb-109">При использовании RBAC доступ и авторизация основываются на роли сервера Lync пользователя.</span><span class="sxs-lookup"><span data-stu-id="b58bb-109">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="b58bb-110">Это позволяет использовать практику «минимальных привилегий», то есть предоставлять администраторам и пользователям только те права, которые необходимы для исполнения их рабочих обязанностей.</span><span class="sxs-lookup"><span data-stu-id="b58bb-110">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b58bb-111">Ограничения RBAC действуют только для администраторов, работающих удаленно, с помощью панели управления Lync Server или консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b58bb-111">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="b58bb-112">Пользователь, работающий на сервере Lync Server, не ограничивается RBAC.</span><span class="sxs-lookup"><span data-stu-id="b58bb-112">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="b58bb-113">Таким образом, физическая безопасность Lync Server важна для сохранения ограничений RBAC.</span><span class="sxs-lookup"><span data-stu-id="b58bb-113">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="b58bb-114">Роли и области действия</span><span class="sxs-lookup"><span data-stu-id="b58bb-114">Roles and Scope</span></span>

<span data-ttu-id="b58bb-p104">При использовании RBAC назначается *роль* на использование списка командлетов, которая подходит для определенного типа администраторов или технических специалистов. *Область действия* — это набор объектов, на которых могут работать командлеты, заданные для роли. Объектами, которые затрагивает область действия, могут быть либо учетные записи пользователей (с группировкой по рабочему подразделению), либо серверы (с группировкой по сайту).</span><span class="sxs-lookup"><span data-stu-id="b58bb-p104">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician. A *scope* is the set of objects which the cmdlets defined in a role can operate on. The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="b58bb-118">В следующей таблице перечислены предопределенные роли в Lync Server и приводятся общие сведения о типах задач, которые могут выполняться.</span><span class="sxs-lookup"><span data-stu-id="b58bb-118">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="b58bb-119">В четвертом столбце показана подобная роль Microsoft Exchange Server для каждой роли Lync Server, если таковая имеется.</span><span class="sxs-lookup"><span data-stu-id="b58bb-119">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="b58bb-120">Предопределенные административные роли</span><span class="sxs-lookup"><span data-stu-id="b58bb-120">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b58bb-121">Role</span><span class="sxs-lookup"><span data-stu-id="b58bb-121">Role</span></span></th>
<th><span data-ttu-id="b58bb-122">Разрешенные задачи</span><span class="sxs-lookup"><span data-stu-id="b58bb-122">Tasks allowed</span></span></th>
<th><span data-ttu-id="b58bb-123">Базовая группа Active Directory</span><span class="sxs-lookup"><span data-stu-id="b58bb-123">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="b58bb-124">Аналог в Exchange</span><span class="sxs-lookup"><span data-stu-id="b58bb-124">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b58bb-125">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="b58bb-125">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-p106">Может выполнять все административные задачи и изменять все параметры, включая создание ролей и назначение их пользователям. Может расширять развертывание, добавляя новые сайты, пулы и службы.</span><span class="sxs-lookup"><span data-stu-id="b58bb-p106">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles. Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="b58bb-128">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="b58bb-128">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-129">Управление организацией</span><span class="sxs-lookup"><span data-stu-id="b58bb-129">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58bb-130">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="b58bb-130">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-131">Позволяет включать и отключать пользователей для Lync Server, перемещать пользователей и назначать существующие политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="b58bb-131">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="b58bb-132">Не может изменять политики.</span><span class="sxs-lookup"><span data-stu-id="b58bb-132">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="b58bb-133">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="b58bb-133">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-134">Получатели почты</span><span class="sxs-lookup"><span data-stu-id="b58bb-134">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b58bb-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b58bb-135">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-136">Может создавать, настраивать параметры и политики голосовых служб и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="b58bb-136">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="b58bb-137">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b58bb-137">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-138">Не применимо</span><span class="sxs-lookup"><span data-stu-id="b58bb-138">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58bb-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="b58bb-139">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-p108">Может управлять, контролировать и осуществлять диагностику и устранение неполадок серверов и служб. Может запрещать новые подключения к серверам, запускать и останавливать службы и применять обновления программного обеспечения. Не может вносить изменения, которые оказывают влияние на глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="b58bb-p108">Can manage, monitor, and troubleshoot servers and services. Can prevent new connections to servers, stop and start services, and apply software updates. Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="b58bb-143">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="b58bb-143">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-144">Управление сервером</span><span class="sxs-lookup"><span data-stu-id="b58bb-144">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b58bb-145">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="b58bb-145">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-146">Может просматривать развертывание, включая сведения о пользователях и серверах, в целях отслеживания работоспособности.</span><span class="sxs-lookup"><span data-stu-id="b58bb-146">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="b58bb-147">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="b58bb-147">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-148">Управление организацией с правами только на просмотр</span><span class="sxs-lookup"><span data-stu-id="b58bb-148">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58bb-149">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="b58bb-149">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="b58bb-p109">Может просматривать развертывание, включая свойства и политики пользователей. Может запускать определенные задачи по устранению неполадок. Не может изменять свойства или политики пользователей, конфигурацию сервера или службы.</span><span class="sxs-lookup"><span data-stu-id="b58bb-p109">Can view the deployment, including user's properties and policies. Can run specific troubleshooting tasks. Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="b58bb-153">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="b58bb-153">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="b58bb-154">HelpDesk</span><span class="sxs-lookup"><span data-stu-id="b58bb-154">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b58bb-155">Роли csarchivingadministrator</span><span class="sxs-lookup"><span data-stu-id="b58bb-155">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-156">Может изменять конфигурацию и политики архивирования.</span><span class="sxs-lookup"><span data-stu-id="b58bb-156">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="b58bb-157">Роли csarchivingadministrator</span><span class="sxs-lookup"><span data-stu-id="b58bb-157">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-158">Управление хранением и удержанием по юридическим причинам</span><span class="sxs-lookup"><span data-stu-id="b58bb-158">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58bb-159">ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="b58bb-159">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-160">Может управлять конфигурацией приложения группы ответа на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="b58bb-160">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="b58bb-161">ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="b58bb-161">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-162">Не применимо</span><span class="sxs-lookup"><span data-stu-id="b58bb-162">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b58bb-163">кслокатионадминистратор</span><span class="sxs-lookup"><span data-stu-id="b58bb-163">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-p110">Самый низкий уровень прав на управление Enhanced 9-1-1 (E9-1-1), который включает создание местоположений E9-1-1 и сетевых идентификаторов и сопоставление их друг с другом. Эта роль всегда назначается с глобальной областью действия.</span><span class="sxs-lookup"><span data-stu-id="b58bb-p110">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other. This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="b58bb-166">кслокатионадминистратор</span><span class="sxs-lookup"><span data-stu-id="b58bb-166">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-167">Не применимо</span><span class="sxs-lookup"><span data-stu-id="b58bb-167">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58bb-168">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="b58bb-168">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="b58bb-169">Может управлять определенными группами ответа.</span><span class="sxs-lookup"><span data-stu-id="b58bb-169">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="b58bb-170">CSResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="b58bb-170">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="b58bb-171">Не применимо</span><span class="sxs-lookup"><span data-stu-id="b58bb-171">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b58bb-172">CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="b58bb-172">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-173">Может управлять функцией сохраняемых сеансов беседы и определенными разговорными каналами сохраняемых сеансов бесед.</span><span class="sxs-lookup"><span data-stu-id="b58bb-173">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="b58bb-174">CSPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="b58bb-174">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b58bb-175">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="b58bb-175">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b58bb-176">Все предопределенные роли, поставленные в Lync Server, имеют глобальную область.</span><span class="sxs-lookup"><span data-stu-id="b58bb-176">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="b58bb-177">Для применения практик назначения минимальных привилегий не следует назначать пользователям роли с глобальной областью действия, если предполагается, что они будут осуществлять администрирование только ограниченного набора серверов или пользователей.</span><span class="sxs-lookup"><span data-stu-id="b58bb-177">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="b58bb-178">Для этого можно создать роли на основе существующих ролей, которые будут обладать более ограниченной областью действия.</span><span class="sxs-lookup"><span data-stu-id="b58bb-178">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="b58bb-179">Создание роли с заданным уровнем</span><span class="sxs-lookup"><span data-stu-id="b58bb-179">Creating a Scoped Role</span></span>

<span data-ttu-id="b58bb-180">При создании роли с ограниченной областью действия (роль с областью действия) необходимо указать область, а также существующую роль, на которой она основана, и группу Active Directory, которой будет назначена роль.</span><span class="sxs-lookup"><span data-stu-id="b58bb-180">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="b58bb-181">Группа Active Directory, которую вы указали, должна быть уже создана.</span><span class="sxs-lookup"><span data-stu-id="b58bb-181">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="b58bb-182">Следующий командлет — это пример создания роли, имеющей привилегии одной из предварительно определенных административных ролей, но с ограниченной областью действия.</span><span class="sxs-lookup"><span data-stu-id="b58bb-182">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="b58bb-183">Он создает новую роль с именем `Site01 Server Administrators` .</span><span class="sxs-lookup"><span data-stu-id="b58bb-183">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="b58bb-184">Роль обладает возможностями предопределенной роли CsServerAdministrator, но только для серверов, расположенных на сайте Site01.</span><span class="sxs-lookup"><span data-stu-id="b58bb-184">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="b58bb-185">Чтобы этот командлет работал, сайт Site01 должен быть уже определен, а универсальная группа безопасности с именем `Site01 Server Administrators` должен уже существовать.</span><span class="sxs-lookup"><span data-stu-id="b58bb-185">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="b58bb-186">После запуска этого командлета все пользователи, являющиеся участниками группы, `Site01 Server Administrators` будут иметь права администратора сервера для серверов в Site01.</span><span class="sxs-lookup"><span data-stu-id="b58bb-186">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="b58bb-187">Кроме того, все пользователи, которые позже добавляются в эту универсальную группу безопасности, также получают права этой роли.</span><span class="sxs-lookup"><span data-stu-id="b58bb-187">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="b58bb-188">Обратите внимание на то, что и сама роль, и универсальная группа безопасности, которой она назначена, называются `Site01 Server Administrators` .</span><span class="sxs-lookup"><span data-stu-id="b58bb-188">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="b58bb-189">В следующем примере представлено ограничение области действия на уровне пользователей, а не на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="b58bb-189">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="b58bb-190">Он создает `Sales Users Administrator` роль для управления учетными записями пользователей в подразделении Sales.</span><span class="sxs-lookup"><span data-stu-id="b58bb-190">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="b58bb-191">Для работы этого командлета уже должна быть создана универсальная группа безопасности Салесусерсадминистратор.</span><span class="sxs-lookup"><span data-stu-id="b58bb-191">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="b58bb-192">Создание новой роли</span><span class="sxs-lookup"><span data-stu-id="b58bb-192">Creating a New Role</span></span>

<span data-ttu-id="b58bb-p115">Чтобы создать роль, предоставляющую доступ к набору командлетов, который не указан ни в одной из предопределенных ролей, или к набору сценариев или модулей, можно опять использовать одну из предопределенных ролей в качестве шаблона. Обратите внимание, что сценарии и модули, которые могут запускать роли, должны храниться в следующих каталогах:</span><span class="sxs-lookup"><span data-stu-id="b58bb-p115">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template. Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="b58bb-195">Путь к модулю Lync по умолчанию C: \\ Program Files \\ Common Files \\ Microsoft Lync Server 2013 \\ modules \\ Lync</span><span class="sxs-lookup"><span data-stu-id="b58bb-195">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="b58bb-196">Путь к сценарию пользователя по умолчанию C: \\ Program Files \\ Common Files \\ Microsoft Lync Server 2013 \\ админскриптс</span><span class="sxs-lookup"><span data-stu-id="b58bb-196">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="b58bb-197">Для создания новой роли следует использовать командлет **New-CsAdminRole**.</span><span class="sxs-lookup"><span data-stu-id="b58bb-197">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="b58bb-198">Перед запуском команды **New — CsAdminRole**необходимо создать базовую универсальную группу безопасности, которая будет связана с этой ролью.</span><span class="sxs-lookup"><span data-stu-id="b58bb-198">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="b58bb-199">Следующие командлеты выступают в качестве примера создания новой роли.</span><span class="sxs-lookup"><span data-stu-id="b58bb-199">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="b58bb-200">Они создают новый тип роли с именем `MyHelpDeskScriptRole` .</span><span class="sxs-lookup"><span data-stu-id="b58bb-200">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="b58bb-201">Новая роль обладает возможностями предопределенной роли CsHelpDesk и дополнительно предоставляет возможности выполнения функций в сценарии testscript.</span><span class="sxs-lookup"><span data-stu-id="b58bb-201">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="b58bb-202">Чтобы этот командлет работал, сначала необходимо создать универсальную группу безопасности Михелпдескскриптроле.</span><span class="sxs-lookup"><span data-stu-id="b58bb-202">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="b58bb-203">После запуска этого командлета можно назначить пользователей непосредственно этой роли (в этом случае они обладают глобальной областью действия) или создать роль с заданным уровнем на основе этой роли, как описано в разделе «Создание роли с заданным уровнем» ранее в этом документе.</span><span class="sxs-lookup"><span data-stu-id="b58bb-203">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="b58bb-204">Назначение ролей пользователям</span><span class="sxs-lookup"><span data-stu-id="b58bb-204">Assigning Roles to Users</span></span>

<span data-ttu-id="b58bb-205">Каждая роль сервера Lync связана с основной универсальной группой безопасности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b58bb-205">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="b58bb-206">Любые пользователи, добавленные в базовую группу, получают возможности, доступные для данной роли.</span><span class="sxs-lookup"><span data-stu-id="b58bb-206">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="b58bb-207">В примерах, приведенных в предыдущих разделах, была создана новая роль, а для новой роли назначена существующая универсальная группа безопасности.</span><span class="sxs-lookup"><span data-stu-id="b58bb-207">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="b58bb-208">Чтобы назначить существующую роль одному или нескольким пользователям, добавьте этих пользователей в группу, связанную с ролью.</span><span class="sxs-lookup"><span data-stu-id="b58bb-208">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="b58bb-209">В эти группы можно добавить как отдельных пользователей, так и универсальные группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="b58bb-209">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="b58bb-210">Например, роль **CsAdministrator** автоматически назначается универсальной группе безопасности " **Администраторы CS** " в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b58bb-210">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="b58bb-211">Эта универсальная группа безопасности создается в Active Directory при развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b58bb-211">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="b58bb-212">Чтобы предоставить эту привилегию пользователю или группе, можно просто добавить их в группу **CS Administrators**.</span><span class="sxs-lookup"><span data-stu-id="b58bb-212">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="b58bb-213">Пользователю можно назначать различные роли RBAC, добавляя его в базовые группы Active Directory, которые соответствуют каждой роли.</span><span class="sxs-lookup"><span data-stu-id="b58bb-213">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="b58bb-214">Обратите внимание, что при создании роли пользователи, которые позднее добавляются в базовую группу Active Directory, получают все возможности, предоставляемые данной ролью.</span><span class="sxs-lookup"><span data-stu-id="b58bb-214">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="b58bb-215">Изменение возможностей роли</span><span class="sxs-lookup"><span data-stu-id="b58bb-215">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="b58bb-p121">Вы можете изменять список командлетов и сценариев, которые может выполнять роль. Можно изменять и командлеты, и сценарии, которые могут выполнять пользовательские роли, но для предопределенных ролей возможно изменение только сценариев. Каждый указываемый командлет может добавлять, удалять или заменять командлеты или сценарии.</span><span class="sxs-lookup"><span data-stu-id="b58bb-p121">You can modify the list of cmdlets and scripts that a role can run. You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles. Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="b58bb-219">Чтобы изменить роль, используйте командлет **Set-CsAdminRole**.</span><span class="sxs-lookup"><span data-stu-id="b58bb-219">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="b58bb-220">Следующий командлет удаляет один скрипт из роли.</span><span class="sxs-lookup"><span data-stu-id="b58bb-220">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="b58bb-221">Планирование для RBAC</span><span class="sxs-lookup"><span data-stu-id="b58bb-221">Planning for RBAC</span></span>

<span data-ttu-id="b58bb-222">Для каждого лица, которому необходимо предоставить административные права для развертывания Lync Server, следует точно определить, какие задачи необходимо выполнить, а затем назначить их ролям с минимальными правами и областью, необходимыми для их работы.</span><span class="sxs-lookup"><span data-stu-id="b58bb-222">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="b58bb-223">При необходимости используйте командлет **Set-CsAdminRole** для создания новой роли с включением только тех командлетов, которые необходимы для выполнения задач данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="b58bb-223">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="b58bb-p124">Пользователи, обладающие ролью CsAdministrator, могут создавать все типы ролей, включая роли на основе CsAdministrator, и назначать их пользователям. Рекомендуется назначать роль CsAdministrator только крайне ограниченному кругу доверенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="b58bb-p124">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them. The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

