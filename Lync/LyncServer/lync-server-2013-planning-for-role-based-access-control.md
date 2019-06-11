---
title: 'Lync Server 2013: планирование контроля доступа на основе ролей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1771eb906685294e588e0c67b1fa8fb1f67a8b6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="10cb1-102">Планирование контроля доступа на основе ролей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10cb1-102">Planning for role-based access control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10cb1-103">_**Тема последнего изменения:** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="10cb1-103">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="10cb1-104">Для делегирования административных задач при высоком стандарте обеспечения безопасности в Lync Server 2013 предлагается управление доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="10cb1-104">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="10cb1-105">С RBAC разрешения администратора предоставлены путем назначения пользователям административных ролей.</span><span class="sxs-lookup"><span data-stu-id="10cb1-105">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="10cb1-106">Lync Server 2013 включает обширный набор встроенных административных ролей, а также позволяет создавать новые роли и определять настраиваемый список командлетов для каждой новой роли.</span><span class="sxs-lookup"><span data-stu-id="10cb1-106">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="10cb1-107">Также можно добавлять скрипты командлетов в разрешенные задачи как предварительно заданных, так и настраиваемых ролей RBAC.</span><span class="sxs-lookup"><span data-stu-id="10cb1-107">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="10cb1-108">Улучшенная безопасность и централизованная защита сервера</span><span class="sxs-lookup"><span data-stu-id="10cb1-108">Better Server Security and Centralization</span></span>

<span data-ttu-id="10cb1-109">В случае с RBAC доступ и авторизация основываются на роли сервера Lync пользователя.</span><span class="sxs-lookup"><span data-stu-id="10cb1-109">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="10cb1-110">Это позволяет использовать правила безопасности "минимальные полномочия", предоставляя администраторам и пользователям права, необходимые для их работы.</span><span class="sxs-lookup"><span data-stu-id="10cb1-110">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="10cb1-111">Ограничения RBAC действуют только для администраторов, работающих в удаленном режиме, с помощью панели управления Lync Server или командной консоли Lync Server Management.</span><span class="sxs-lookup"><span data-stu-id="10cb1-111">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="10cb1-112">Пользователь, работающий на сервере Lync Server, не ограничивается с помощью RBAC.</span><span class="sxs-lookup"><span data-stu-id="10cb1-112">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="10cb1-113">Следовательно, физическая безопасность вашего сервера Lync важна для сохранения ограничений RBAC.</span><span class="sxs-lookup"><span data-stu-id="10cb1-113">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="10cb1-114">Роли и область охвата</span><span class="sxs-lookup"><span data-stu-id="10cb1-114">Roles and Scope</span></span>

<span data-ttu-id="10cb1-115">В RBAC *роль* включает использование списка командлетов, разработанных для определенного типа администратора или специалиста.</span><span class="sxs-lookup"><span data-stu-id="10cb1-115">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician.</span></span> <span data-ttu-id="10cb1-116">*Область* — это набор объектов, на которые могут работать командлеты, определенные в роли.</span><span class="sxs-lookup"><span data-stu-id="10cb1-116">A *scope* is the set of objects which the cmdlets defined in a role can operate on.</span></span> <span data-ttu-id="10cb1-117">Объекты, к которым относится область действия, могут быть либо учетными записями пользователей (сгруппированными по подразделениям), либо серверами (сгруппированными по сайту).</span><span class="sxs-lookup"><span data-stu-id="10cb1-117">The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="10cb1-118">В приведенной ниже таблице перечислены предопределенные роли в Lync Server, а также общие сведения о типах задач.</span><span class="sxs-lookup"><span data-stu-id="10cb1-118">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="10cb1-119">В четвертом столбце показана аналогичная роль сервера Microsoft Exchange для каждой роли сервера Lync, если таковая имеется.</span><span class="sxs-lookup"><span data-stu-id="10cb1-119">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="10cb1-120">Предопределенные административные роли</span><span class="sxs-lookup"><span data-stu-id="10cb1-120">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10cb1-121">Должность</span><span class="sxs-lookup"><span data-stu-id="10cb1-121">Role</span></span></th>
<th><span data-ttu-id="10cb1-122">Разрешенные задачи</span><span class="sxs-lookup"><span data-stu-id="10cb1-122">Tasks allowed</span></span></th>
<th><span data-ttu-id="10cb1-123">Базовая группа Active Directory</span><span class="sxs-lookup"><span data-stu-id="10cb1-123">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="10cb1-124">Эквивалент Exchange</span><span class="sxs-lookup"><span data-stu-id="10cb1-124">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10cb1-125">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="10cb1-125">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-126">Можно выполнять все административные задачи и изменять все параметры, в том числе создавать роли и назначать пользователей ролям.</span><span class="sxs-lookup"><span data-stu-id="10cb1-126">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles.</span></span> <span data-ttu-id="10cb1-127">Развернуть развертывание можно с помощью добавления новых сайтов, пулов и служб.</span><span class="sxs-lookup"><span data-stu-id="10cb1-127">Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="10cb1-128">Ксадминистратор</span><span class="sxs-lookup"><span data-stu-id="10cb1-128">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-129">Управление организациями</span><span class="sxs-lookup"><span data-stu-id="10cb1-129">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10cb1-130">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="10cb1-130">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-131">Может включать и отключать пользователей для Lync Server, перемещать пользователей и назначать существующие политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="10cb1-131">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="10cb1-132">Изменить политики нельзя.</span><span class="sxs-lookup"><span data-stu-id="10cb1-132">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="10cb1-133">Ксусерадминистратор</span><span class="sxs-lookup"><span data-stu-id="10cb1-133">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-134">Получатели почты</span><span class="sxs-lookup"><span data-stu-id="10cb1-134">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10cb1-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="10cb1-135">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-136">Можно создавать, настраивать параметры и политики для голосовой связи, а также управлять ими.</span><span class="sxs-lookup"><span data-stu-id="10cb1-136">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="10cb1-137">Ксвоицеадминистратор</span><span class="sxs-lookup"><span data-stu-id="10cb1-137">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-138">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="10cb1-138">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10cb1-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="10cb1-139">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-140">Позволяет управлять серверами и службами и устранять неполадки с ними.</span><span class="sxs-lookup"><span data-stu-id="10cb1-140">Can manage, monitor, and troubleshoot servers and services.</span></span> <span data-ttu-id="10cb1-141">Может препятствовать новым подключениям к серверам, остановке и запуску служб, а также к применению обновлений программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="10cb1-141">Can prevent new connections to servers, stop and start services, and apply software updates.</span></span> <span data-ttu-id="10cb1-142">Нельзя вносить изменения, если это не повлияет на глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="10cb1-142">Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="10cb1-143">Кссерверадминистратор</span><span class="sxs-lookup"><span data-stu-id="10cb1-143">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-144">Управление сервером</span><span class="sxs-lookup"><span data-stu-id="10cb1-144">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10cb1-145">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="10cb1-145">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-146">Можно просматривать развертывание, включая сведения о пользователе и сервере, чтобы отслеживать состояние развертывания.</span><span class="sxs-lookup"><span data-stu-id="10cb1-146">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="10cb1-147">Ксвиевонлядминистратор</span><span class="sxs-lookup"><span data-stu-id="10cb1-147">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-148">Управление организациями только для просмотра</span><span class="sxs-lookup"><span data-stu-id="10cb1-148">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10cb1-149">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="10cb1-149">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="10cb1-150">Можно просматривать развертывание, включая свойства пользователя и политики.</span><span class="sxs-lookup"><span data-stu-id="10cb1-150">Can view the deployment, including user's properties and policies.</span></span> <span data-ttu-id="10cb1-151">Может выполнять определенные задачи по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="10cb1-151">Can run specific troubleshooting tasks.</span></span> <span data-ttu-id="10cb1-152">Не удается изменить свойства или политики пользователя, а также конфигурацию сервера или службы.</span><span class="sxs-lookup"><span data-stu-id="10cb1-152">Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="10cb1-153">Кшелпдеск</span><span class="sxs-lookup"><span data-stu-id="10cb1-153">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="10cb1-154">Службы поддержки</span><span class="sxs-lookup"><span data-stu-id="10cb1-154">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10cb1-155">Ксарчивингадминистратор</span><span class="sxs-lookup"><span data-stu-id="10cb1-155">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-156">Можно изменять конфигурацию архивации и политики.</span><span class="sxs-lookup"><span data-stu-id="10cb1-156">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="10cb1-157">Ксарчивингадминистратор</span><span class="sxs-lookup"><span data-stu-id="10cb1-157">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-158">Управление хранением, юридическое удержание</span><span class="sxs-lookup"><span data-stu-id="10cb1-158">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10cb1-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="10cb1-159">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-160">Можно управлять конфигурацией приложения группы ответа на сайте.</span><span class="sxs-lookup"><span data-stu-id="10cb1-160">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="10cb1-161">Ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="10cb1-161">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-162">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="10cb1-162">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10cb1-163">Кслокатионадминистратор</span><span class="sxs-lookup"><span data-stu-id="10cb1-163">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-164">Самый низкий уровень прав для расширенного управления 9-1-1 (E9-1-1), включая создание местоположений E9-1-1 и сетевых идентификаторов и их связь друг с другом.</span><span class="sxs-lookup"><span data-stu-id="10cb1-164">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other.</span></span> <span data-ttu-id="10cb1-165">Эта роль всегда назначается глобальной области действия.</span><span class="sxs-lookup"><span data-stu-id="10cb1-165">This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="10cb1-166">Кслокатионадминистратор</span><span class="sxs-lookup"><span data-stu-id="10cb1-166">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-167">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="10cb1-167">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10cb1-168">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="10cb1-168">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="10cb1-169">Можно управлять конкретными группами ответа.</span><span class="sxs-lookup"><span data-stu-id="10cb1-169">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="10cb1-170">Ксреспонсеграупманажер</span><span class="sxs-lookup"><span data-stu-id="10cb1-170">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="10cb1-171">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="10cb1-171">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10cb1-172">Ксперсистентчатадминистратор</span><span class="sxs-lookup"><span data-stu-id="10cb1-172">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-173">Можно управлять функцией сохраняемого чата и определенными сохраняемыми комнатами чата.</span><span class="sxs-lookup"><span data-stu-id="10cb1-173">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="10cb1-174">Ксперсистентчатадминистратор</span><span class="sxs-lookup"><span data-stu-id="10cb1-174">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="10cb1-175">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="10cb1-175">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="10cb1-176">Все предопределенные роли, отправленные в Lync Server, имеют глобальную область.</span><span class="sxs-lookup"><span data-stu-id="10cb1-176">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="10cb1-177">Чтобы следовать рекомендациям по крайней мере, вы не должны назначать пользователей ролям с глобальной областью действия, если они будут администрировать только ограниченный набор серверов или пользователей.</span><span class="sxs-lookup"><span data-stu-id="10cb1-177">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="10cb1-178">Для этого вы можете создавать роли, основанные на существующей роли, но с более ограниченной областью действия.</span><span class="sxs-lookup"><span data-stu-id="10cb1-178">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="10cb1-179">Создание роли с областью действия</span><span class="sxs-lookup"><span data-stu-id="10cb1-179">Creating a Scoped Role</span></span>

<span data-ttu-id="10cb1-180">Когда вы создаете роль с ограниченной областью действия (роль с областью действия), вы указываете область, а также текущую роль, на которой она основана, и ей назначена роль.</span><span class="sxs-lookup"><span data-stu-id="10cb1-180">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="10cb1-181">Указанная группа Active Directory должна быть уже создана.</span><span class="sxs-lookup"><span data-stu-id="10cb1-181">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="10cb1-182">Следующий командлет является примером создания роли, обладающей привилегиями одной из предварительно определенных административных ролей, но с ограниченной областью действия.</span><span class="sxs-lookup"><span data-stu-id="10cb1-182">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="10cb1-183">Она создает новую роль с именем `Site01 Server Administrators`.</span><span class="sxs-lookup"><span data-stu-id="10cb1-183">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="10cb1-184">Роль обладает возможностями предопределенной роли Кссерверадминистратор, но только для серверов, расположенных на сайте Site01.</span><span class="sxs-lookup"><span data-stu-id="10cb1-184">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="10cb1-185">Для работы этого командлета необходимо, чтобы сайт Site01 был определен, а универсальная группа безопасности с именем `Site01 Server Administrators` уже существовала.</span><span class="sxs-lookup"><span data-stu-id="10cb1-185">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="10cb1-186">После запуска этого командлета все пользователи, входящие в эту `Site01 Server Administrators` группу, получат права администратора сервера для серверов в Site01.</span><span class="sxs-lookup"><span data-stu-id="10cb1-186">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="10cb1-187">Кроме того, пользователи, которые позже добавляются в эту универсальную группу безопасности, также получают полномочия для этой роли.</span><span class="sxs-lookup"><span data-stu-id="10cb1-187">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="10cb1-188">Обратите внимание, что и сама роль, и универсальная группа безопасности, которой она назначена, называется `Site01 Server Administrators`.</span><span class="sxs-lookup"><span data-stu-id="10cb1-188">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="10cb1-189">В следующем примере ограничивается область пользователя, а не область сервера.</span><span class="sxs-lookup"><span data-stu-id="10cb1-189">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="10cb1-190">Она создает `Sales Users Administrator` роль для управления учетными записями пользователей в подразделении Sales.</span><span class="sxs-lookup"><span data-stu-id="10cb1-190">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="10cb1-191">Для работы этого командлета необходимо, чтобы на нем была создана универсальная группа безопасности Салесусерсадминистратор.</span><span class="sxs-lookup"><span data-stu-id="10cb1-191">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="10cb1-192">Создание новой роли</span><span class="sxs-lookup"><span data-stu-id="10cb1-192">Creating a New Role</span></span>

<span data-ttu-id="10cb1-193">Чтобы создать роль, которая имеет доступ к набору командлетов, не либо в одной из предопределенных ролей, либо в наборе сценариев или модулей, вы снова начнете использовать одну из предопределенных ролей в качестве шаблона.</span><span class="sxs-lookup"><span data-stu-id="10cb1-193">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template.</span></span> <span data-ttu-id="10cb1-194">Обратите внимание на то, что сценарии и модули, которые могут быть доступны для выполнения, должны храниться в следующих папках:</span><span class="sxs-lookup"><span data-stu-id="10cb1-194">Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="10cb1-195">Путь к\\модулю Lync по умолчанию C: Program Files\\— общие\\файлы Microsoft Lync Server\\2013\\modules Lync</span><span class="sxs-lookup"><span data-stu-id="10cb1-195">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="10cb1-196">Путь к пользовательскому сценарию по умолчанию C:\\Program Files\\,\\файлы в стандарте\\Microsoft Lync Server 2013 админскриптс</span><span class="sxs-lookup"><span data-stu-id="10cb1-196">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="10cb1-197">Чтобы создать новую роль, вы можете использовать командлет **New-ксадминроле** .</span><span class="sxs-lookup"><span data-stu-id="10cb1-197">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="10cb1-198">Перед запуском **New-ксадминроле**необходимо сначала создать основную универсальную группу безопасности, которая будет связана с этой ролью.</span><span class="sxs-lookup"><span data-stu-id="10cb1-198">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="10cb1-199">Следующие командлеты служат примером создания новой роли.</span><span class="sxs-lookup"><span data-stu-id="10cb1-199">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="10cb1-200">Они создают новый тип роли `MyHelpDeskScriptRole`.</span><span class="sxs-lookup"><span data-stu-id="10cb1-200">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="10cb1-201">Новая роль обладает возможностями предопределенной роли Кшелпдеск и может дополнительно выполнять функции в сценарии с именем "тестскрипт".</span><span class="sxs-lookup"><span data-stu-id="10cb1-201">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="10cb1-202">Чтобы этот командлет работал, сначала необходимо создать универсальную группу безопасности Михелпдескскриптроле.</span><span class="sxs-lookup"><span data-stu-id="10cb1-202">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="10cb1-203">После запуска этого командлета вы можете назначить пользователей непосредственно этой роли (в этом случае она имеет глобальную область) или создать роль с областью на основе этой роли, как объясняется, как создать роль с областью, ранее в этом документе.</span><span class="sxs-lookup"><span data-stu-id="10cb1-203">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="10cb1-204">Назначение ролей пользователям</span><span class="sxs-lookup"><span data-stu-id="10cb1-204">Assigning Roles to Users</span></span>

<span data-ttu-id="10cb1-205">Каждая роль сервера Lync связана с базовой группой безопасности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="10cb1-205">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="10cb1-206">Любые пользователи, добавленные в основную группу, получают возможности этой роли.</span><span class="sxs-lookup"><span data-stu-id="10cb1-206">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="10cb1-207">В примерах, приведенных в предыдущих разделах, создана новая роль, и ей назначается существующая универсальная группа безопасности для новой роли.</span><span class="sxs-lookup"><span data-stu-id="10cb1-207">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="10cb1-208">Чтобы назначить существующую роль для одного или нескольких пользователей, добавьте этих пользователей в группу, связанную с этой ролью.</span><span class="sxs-lookup"><span data-stu-id="10cb1-208">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="10cb1-209">Вы можете добавить в эти группы как отдельные пользователи, так и универсальные группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="10cb1-209">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="10cb1-210">Например, роль **ксадминистратор** автоматически предоставляется в универсальную группу безопасности " **Администраторы CS** " в службе каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="10cb1-210">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="10cb1-211">Эта универсальная группа безопасности создается в службе каталогов Active Directory при развертывании сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="10cb1-211">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="10cb1-212">Чтобы предоставить пользователю или группе эту привилегию, вы можете просто добавить их в группу " **Администраторы CS** ".</span><span class="sxs-lookup"><span data-stu-id="10cb1-212">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="10cb1-213">Пользователю может быть предоставлено несколько ролей RBAC путем добавления в базовые группы Active Directory, соответствующие каждой роли.</span><span class="sxs-lookup"><span data-stu-id="10cb1-213">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="10cb1-214">Обратите внимание, что при создании роли пользователи, которые позже добавляются в основную группу Active Directory, получают возможности этой роли.</span><span class="sxs-lookup"><span data-stu-id="10cb1-214">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="10cb1-215">Изменение возможностей роли</span><span class="sxs-lookup"><span data-stu-id="10cb1-215">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="10cb1-216">Вы можете изменить список командлетов и сценариев, которые может выполнять роль.</span><span class="sxs-lookup"><span data-stu-id="10cb1-216">You can modify the list of cmdlets and scripts that a role can run.</span></span> <span data-ttu-id="10cb1-217">Вы можете изменить как командлеты, так и сценарии, которые могут запускать пользовательские роли, но вы можете изменять только сценарии для предопределенных ролей.</span><span class="sxs-lookup"><span data-stu-id="10cb1-217">You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles.</span></span> <span data-ttu-id="10cb1-218">Каждый из введенных командлетов может добавлять, удалять или заменять командлеты или сценарии.</span><span class="sxs-lookup"><span data-stu-id="10cb1-218">Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="10cb1-219">Чтобы изменить роль, используйте командлет **Set-ксадминроле** .</span><span class="sxs-lookup"><span data-stu-id="10cb1-219">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="10cb1-220">Следующий командлет удаляет один сценарий из роли.</span><span class="sxs-lookup"><span data-stu-id="10cb1-220">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="10cb1-221">Планирование для RBAC</span><span class="sxs-lookup"><span data-stu-id="10cb1-221">Planning for RBAC</span></span>

<span data-ttu-id="10cb1-222">Для каждого пользователя, которому необходимо предоставить права администратора для развертывания Lync Server, необходимо точно определить, какие задачи они должны выполнить, а затем назначить им роли с минимальными полномочиями и областью, необходимыми для их работы.</span><span class="sxs-lookup"><span data-stu-id="10cb1-222">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="10cb1-223">При необходимости можно использовать командлет **Set-ксадминроле** , чтобы создать новую роль с командлетами, необходимыми для задач этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="10cb1-223">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="10cb1-224">Пользователи, имеющие роль Ксадминистратор, могут создавать все типы ролей, в том числе роли на основе Ксадминистратор и назначать им пользователей.</span><span class="sxs-lookup"><span data-stu-id="10cb1-224">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them.</span></span> <span data-ttu-id="10cb1-225">Рекомендуется назначать роль Ксадминистратор очень маленькому набору доверенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="10cb1-225">The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

