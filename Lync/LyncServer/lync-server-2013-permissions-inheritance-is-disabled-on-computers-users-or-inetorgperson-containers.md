---
title: 'Lync Server 2013: заблокировано наследование разрешений для компьютеров, пользователей и контейнеров inetOrgPerson'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da84454a6e02e02520206b5eb667edfcf4fce849
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="02f81-102">Заблокировано наследование разрешений для компьютеров, пользователей и контейнеров inetOrgPerson в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02f81-102">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02f81-103">_**Тема последнего изменения:** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="02f81-103">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="02f81-104">В заблокированных доменных службах Active Directory пользователи и объекты компьютеров часто размещаются в определенных организационных подразделениях (OU) с отключенным наследованием разрешений для обеспечения безопасности административного делегирования и включения использования объектов групповой политики (GPO). для применения политик безопасности.</span><span class="sxs-lookup"><span data-stu-id="02f81-104">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="02f81-105">Подготовка домена и активация сервера настройте элементы управления доступом (ACE), необходимые для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="02f81-105">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="02f81-106">Если отключено наследование разрешений, группы безопасности Lync Server не смогут наследовать эти ACE.</span><span class="sxs-lookup"><span data-stu-id="02f81-106">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="02f81-107">Если эти разрешения не наследуются, группам безопасности Lync Server не удается получить доступ к параметрам, и возникают указанные ниже проблемы.</span><span class="sxs-lookup"><span data-stu-id="02f81-107">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="02f81-108">Для администрирования пользователей, Инеторгперсонс и контактов, а также для работы серверов в группах безопасности Lync Server требуются ACE, заданные в процессе подготовки домена к наборам свойств каждого пользователя, взаимодействие в реальном времени (RTC), Поиск пользователей RTC и общедоступные сведения. .</span><span class="sxs-lookup"><span data-stu-id="02f81-108">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="02f81-109">Если отключено наследование разрешений, группы безопасности не наследуют эти ACE и не могут управлять серверами и пользователями.</span><span class="sxs-lookup"><span data-stu-id="02f81-109">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="02f81-110">Чтобы найти серверы и пулы, серверы с Lync Server используют записи ACE, заданные с помощью активации для объектов, связанных с компьютером, включая контейнер Microsoft и объект сервера.</span><span class="sxs-lookup"><span data-stu-id="02f81-110">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="02f81-111">Если отключено наследование разрешений, группы безопасности, серверы и пулы не наследуют эти ACE и не могут использовать эти ACE.</span><span class="sxs-lookup"><span data-stu-id="02f81-111">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="02f81-112">Чтобы устранить эти проблемы, Lync Server предоставляет командлет **Grant-ксаупермиссион** .</span><span class="sxs-lookup"><span data-stu-id="02f81-112">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="02f81-113">Этот командлет задает необходимые серверные ACE Lync Server непосредственно в указанном контейнере и организационных подразделениях и объектах в контейнере или подразделении.</span><span class="sxs-lookup"><span data-stu-id="02f81-113">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="02f81-114">Настройка разрешений для пользователей, InetOrgPerson и объектов контакта после подготовки домена</span><span class="sxs-lookup"><span data-stu-id="02f81-114">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="02f81-115">В заблокированной среде Active Directory, в которой отключено наследование разрешений, при подготовке домена не устанавливаются необходимые ACE для контейнеров и организационных подразделений, в которых хранятся пользователи или объекты InetOrgPerson в пределах домена.</span><span class="sxs-lookup"><span data-stu-id="02f81-115">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="02f81-116">В этом случае необходимо запустить командлет **Grant-ксаупермиссион** в каждом контейнере или подразделении, у которого есть объекты пользователя или inetOrgPerson, для которых отключено наследование разрешений.</span><span class="sxs-lookup"><span data-stu-id="02f81-116">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="02f81-117">Если у вас топология центрального леса, необходимо также выполнить эту процедуру в контейнерах или подразделениях, содержащих объекты контактов.</span><span class="sxs-lookup"><span data-stu-id="02f81-117">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="02f81-118">Подробные сведения о топологиях центрального леса содержатся [в разделе Поддерживаемые топологии службы каталогов Active Directory в Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="02f81-118">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="02f81-119">Параметр ObjectType указывает тип объекта.</span><span class="sxs-lookup"><span data-stu-id="02f81-119">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="02f81-120">Параметр OU задает подразделение.</span><span class="sxs-lookup"><span data-stu-id="02f81-120">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="02f81-121">Этот командлет добавляет необходимые ACE непосредственно в указанные контейнеры или подразделения, а также объекты пользователя или InetOrgPerson в контейнере.</span><span class="sxs-lookup"><span data-stu-id="02f81-121">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="02f81-122">Если подразделение, для которого выполняется эта команда, имеет дочерние подразделения с объектами User или InetOrgPerson, эти разрешения не будут применены.</span><span class="sxs-lookup"><span data-stu-id="02f81-122">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="02f81-123">Вам потребуется выполнить команду для каждого дочернего подразделения отдельно.</span><span class="sxs-lookup"><span data-stu-id="02f81-123">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="02f81-124">Это распространенный сценарий, в котором используются развертывания на хостинге Lync, например родительский OU = Клиенты OCS, DC = CONTOSO, DC = LOCAL и Child OU = первом клиенте, OU = Клиенты OCS, DC = CONTOSO, DC = LOCAL.</span><span class="sxs-lookup"><span data-stu-id="02f81-124">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="02f81-125">Для выполнения этого командлета необходимы права пользователя, эквивалентные членству в группе администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="02f81-125">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="02f81-126">Если ACE, прошедшие проверку подлинности, также были удалены в заблокированной среде, необходимо предоставить этой учетной записи ACE для доступа на чтение в соответствующих контейнерах или подразделениях в корневом домене леса, как описано в разделе [разрешения пользователей, прошедших проверку подлинности, которые удаляются в Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) или используют учетную запись, которая входит в группу администраторов предприятия.</span><span class="sxs-lookup"><span data-stu-id="02f81-126">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="02f81-127">**Настройка обязательных ACE для объектов User, InetOrgPerson и Contact**</span><span class="sxs-lookup"><span data-stu-id="02f81-127">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="02f81-128">Войдите в систему на компьютере, подключенном к домену, с учетной записью, которая является членом группы "Администраторы домена" или имеет эквивалентные права пользователя.</span><span class="sxs-lookup"><span data-stu-id="02f81-128">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="02f81-129">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="02f81-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="02f81-130">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="02f81-130">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="02f81-131">Если параметр Domain не указан, значение по умолчанию — локальный домен.</span><span class="sxs-lookup"><span data-stu-id="02f81-131">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="02f81-132">Например:</span><span class="sxs-lookup"><span data-stu-id="02f81-132">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="02f81-133">В файле журнала найдите \*\* \<\> результаты выполнения по завершении\*\* каждой задачи, чтобы убедиться в том, что разрешения заданы, а затем закройте окно журнала.</span><span class="sxs-lookup"><span data-stu-id="02f81-133">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="02f81-134">Кроме того, вы можете выполнить следующую команду, чтобы определить, установлены ли разрешения.</span><span class="sxs-lookup"><span data-stu-id="02f81-134">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="02f81-135">Например:</span><span class="sxs-lookup"><span data-stu-id="02f81-135">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="02f81-136">Настройка разрешений для объектов компьютера после выполнения подготовки домена</span><span class="sxs-lookup"><span data-stu-id="02f81-136">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="02f81-137">В заблокированной среде Active Directory, в которой отключено наследование разрешений, при подготовке домена не устанавливаются необходимые ACE для контейнеров и подразделений, которые содержат объекты компьютера внутри домена.</span><span class="sxs-lookup"><span data-stu-id="02f81-137">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="02f81-138">В этой ситуации вы должны запустить командлет **Grant-ксаупермиссион** в каждом контейнере или подразделении, где есть компьютеры, на которых работает Lync Server, в котором отключено наследование разрешений.</span><span class="sxs-lookup"><span data-stu-id="02f81-138">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="02f81-139">Параметр ObjectType указывает тип объекта.</span><span class="sxs-lookup"><span data-stu-id="02f81-139">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="02f81-140">Эта процедура добавляет необходимые ACE непосредственно в указанные контейнеры.</span><span class="sxs-lookup"><span data-stu-id="02f81-140">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="02f81-141">Для выполнения этого командлета необходимы права пользователя, эквивалентные членству в группе администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="02f81-141">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="02f81-142">Если ACE для пользователей, прошедших проверку подлинности, также были удалены, необходимо предоставить этому учетной записи ACE для доступа на чтение в соответствующих контейнерах в корневом домене леса, как описано в разделе [разрешения пользователей, прошедших проверку подлинности, которые удаляются в Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) или используют учетную запись, которая входит в группу администраторов предприятия.</span><span class="sxs-lookup"><span data-stu-id="02f81-142">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="02f81-143">**Настройка обязательных ACE для объектов компьютера**</span><span class="sxs-lookup"><span data-stu-id="02f81-143">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="02f81-144">Войдите на компьютер домена с помощью учетной записи, которая входит в группу "Администраторы домена" или имеет эквивалентные права пользователя.</span><span class="sxs-lookup"><span data-stu-id="02f81-144">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="02f81-145">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="02f81-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="02f81-146">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="02f81-146">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="02f81-147">Если параметр Domain не указан, значение по умолчанию — локальный домен.</span><span class="sxs-lookup"><span data-stu-id="02f81-147">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="02f81-148">Например:</span><span class="sxs-lookup"><span data-stu-id="02f81-148">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="02f81-149">В примере журнала C:\\заносит\\в журнал аупермиссионс. XML, и вы можете найти \*\* \<\> результаты выполнения в\*\* конце каждой задачи и убедиться в отсутствии ошибок и закрыть журнал.</span><span class="sxs-lookup"><span data-stu-id="02f81-149">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="02f81-150">Для проверки разрешений можно выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="02f81-150">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="02f81-151">Например:</span><span class="sxs-lookup"><span data-stu-id="02f81-151">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="02f81-152">Если вы выполняете подготовку домена в корневом домене леса в заблокированной среде Active Directory, имейте в виду, что для Lync Server требуется доступ к схеме Active Directory и контейнерам конфигурации.</span><span class="sxs-lookup"><span data-stu-id="02f81-152">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="02f81-153">Если разрешение пользователя, прошедшего проверку подлинности по умолчанию, удалено из схемы&nbsp;или контейнеров конфигурации в доменных службах Active Directory, для доступа к данному контейнеру могут использоваться только участники группы "Администраторы схемы" (для контейнера схемы) или "Администраторы предприятия" (для контейнера конфигурации).</span><span class="sxs-lookup"><span data-stu-id="02f81-153">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="02f81-154">Так как программа Setup. exe, Lync Server Management Shell и панель управления Lync Server требуют доступа к этим контейнерам, Настройка и установка средств администрирования будут завершаться сбоем, если пользователь, выполняющий установку, не имеет прав пользователя, эквивалентной схеме Участие в группах администраторов и администраторов предприятий.</span><span class="sxs-lookup"><span data-stu-id="02f81-154">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="02f81-155">Для устранения этой ситуации необходимо предоставить Рткуниверсалглобалвритеграуп группе чтение, доступ на запись к схеме и контейнерам конфигурации.</span><span class="sxs-lookup"><span data-stu-id="02f81-155">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

