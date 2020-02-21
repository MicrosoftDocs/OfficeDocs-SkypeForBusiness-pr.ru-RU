---
title: 'Lync Server 2013: наследование разрешений отключено для компьютеров, пользователей и контейнеров InetOrgPerson'
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
ms.openlocfilehash: b6f0ac6b7614da844a35f97070b61f1b074a4367
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="23938-102">Наследование разрешений отключено на компьютерах, пользователях и контейнерах InetOrgPerson в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23938-102">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23938-103">_**Последнее изменение темы:** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="23938-103">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="23938-104">В заблокированных доменных службах Active Directory пользователи и объекты компьютеров часто размещаются в определенных подразделениях (OU) с отключенными наследованием разрешений для обеспечения безопасности административного делегирования и включения использования объектов групповой политики (GPO). для применения политик безопасности.</span><span class="sxs-lookup"><span data-stu-id="23938-104">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="23938-105">Подготовка домена и активация сервера задавайте записи управления доступом (ACE), необходимые для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23938-105">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="23938-106">Если наследование разрешений отключено, группы безопасности Lync Server не могут наследовать эти элементы управления доступом.</span><span class="sxs-lookup"><span data-stu-id="23938-106">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="23938-107">Если эти разрешения не наследуются, группам безопасности Lync Server не удается получить доступ к параметрам, и возникают следующие две проблемы:</span><span class="sxs-lookup"><span data-stu-id="23938-107">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="23938-108">Для администрирования пользователей, Инеторгперсонс и контактов, а также для работы с серверами в группах безопасности Lync Server требуются записи ACE, заданные в процедуре подготовки домена для наборов свойств каждого пользователя, взаимодействия в реальном времени (RTC), поиска пользователей RTC и общедоступной информации. .</span><span class="sxs-lookup"><span data-stu-id="23938-108">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="23938-109">Когда наследование разрешений отключено, группы безопасности не наследуют эти элементы ACE и не могут управлять серверами и пользователями.</span><span class="sxs-lookup"><span data-stu-id="23938-109">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="23938-110">Для обнаружения серверов и пулов серверы, на которых работает Lync Server, используют записи управления доступом (ACE), установленные при активации объектов, связанных с компьютером, в том числе Microsoft Container и объект сервера.</span><span class="sxs-lookup"><span data-stu-id="23938-110">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="23938-111">Когда наследование разрешений отключено, группы безопасности, серверы и пулы не наследуют эти элементы ACE и не могут их использовать.</span><span class="sxs-lookup"><span data-stu-id="23938-111">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="23938-112">Чтобы устранить эти проблемы, Lync Server предоставляет командлет **Grant – CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="23938-112">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="23938-113">Этот командлет задает необходимые элементы управления Lync Server непосредственно для указанного контейнера и подразделений и объектов в контейнере или подразделении.</span><span class="sxs-lookup"><span data-stu-id="23938-113">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="23938-114">Установка разрешений для объектов User, InetOrgPerson и Contact после проведения подготовки домена</span><span class="sxs-lookup"><span data-stu-id="23938-114">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="23938-115">В заблокированной среде Active Directory, в которой отключено наследование разрешений, при подготовке домена не устанавливаются необходимые элементы ACE для контейнеров или подразделений, в которых хранятся объекты пользователей или InetOrgPerson в домене.</span><span class="sxs-lookup"><span data-stu-id="23938-115">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="23938-116">В этом случае необходимо выполнить командлет **Grant-CsOuPermission** для каждого контейнера или подразделения, у которого есть объекты user или inetOrgPerson, для которых отключено наследование разрешений.</span><span class="sxs-lookup"><span data-stu-id="23938-116">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="23938-117">Если у вас есть топология центрального леса, необходимо также выполнить эту процедуру в контейнерах или подразделениях, содержащих объекты Contact.</span><span class="sxs-lookup"><span data-stu-id="23938-117">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="23938-118">Подробные сведения о топологиях с центральным лесом приведены [в статье поддерживаемые топологии Active Directory в Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="23938-118">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="23938-119">Параметр ObjectType задает тип объекта.</span><span class="sxs-lookup"><span data-stu-id="23938-119">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="23938-120">Параметр OU указывает подразделение.</span><span class="sxs-lookup"><span data-stu-id="23938-120">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="23938-121">Этот командлет добавляет необходимые элементы ACE непосредственно для заданных контейнеров или организационных подразделений и объектов User или InetOrgPerson внутри контейнера.</span><span class="sxs-lookup"><span data-stu-id="23938-121">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="23938-122">Если подразделение, в котором выполняется эта команда, имеет дочерние подразделения с объектами User или InetOrgPerson, эти разрешения не будут применяться к ним.</span><span class="sxs-lookup"><span data-stu-id="23938-122">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="23938-123">Вам потребуется выполнить команду для каждого дочернего подразделения по отдельности.</span><span class="sxs-lookup"><span data-stu-id="23938-123">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="23938-124">Это распространенный сценарий, в котором используются развертывания Lync Hosting, например Parent OU = Клиенты OCS, DC = CONTOSO, DC = LOCAL и Child OU = Tenant1, OU = клиентские Клиенты OCS, DC = CONTOSO, DC = LOCAL.</span><span class="sxs-lookup"><span data-stu-id="23938-124">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="23938-125">Для запуска этого командлета необходимы права пользователя, эквивалентные членству в группе администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="23938-125">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="23938-126">Если ACE, прошедшие проверку подлинности, также были удалены в заблокированной среде, необходимо предоставить этой учетной записи ACE для доступа на чтение в соответствующих контейнерах или подразделениях в корневом домене леса, как описано в разделе [разрешения пользователей с проверкой подлинности удалено в Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) или использовать учетную запись, входящую в группу администраторов предприятия.</span><span class="sxs-lookup"><span data-stu-id="23938-126">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="23938-127">**Установка необходимых элементов ACE для объектов User, InetOrgPerson и Contact**</span><span class="sxs-lookup"><span data-stu-id="23938-127">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="23938-128">Выполните вход на компьютер, присоединенный к домену, с использованием учетной записи, которая является членом группы администраторов домена или имеет эквивалентные права пользователя.</span><span class="sxs-lookup"><span data-stu-id="23938-128">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="23938-129">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="23938-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="23938-130">Выполняем</span><span class="sxs-lookup"><span data-stu-id="23938-130">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="23938-131">Если параметр Domain не указан, значением по умолчанию является локальный домен.</span><span class="sxs-lookup"><span data-stu-id="23938-131">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="23938-132">Например:</span><span class="sxs-lookup"><span data-stu-id="23938-132">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="23938-133">В файле журнала найдите \*\* \<\> результаты выполнения в\*\* конце каждой задачи, чтобы убедиться, что были заданы разрешения, а затем закройте окно Журнал.</span><span class="sxs-lookup"><span data-stu-id="23938-133">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="23938-134">Либо выполните следующую команду, чтобы убедиться, что разрешения были установлены:</span><span class="sxs-lookup"><span data-stu-id="23938-134">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="23938-135">Пример:</span><span class="sxs-lookup"><span data-stu-id="23938-135">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="23938-136">Установка разрешения для объектов Computer после проведения подготовки домена</span><span class="sxs-lookup"><span data-stu-id="23938-136">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="23938-137">В заблокированной среде Active Directory с отключенным наследованием разрешений подготовка домена не ведет к установке необходимых элементов ACE для контейнеров или организационных подразделений внутри домена, содержащих объекты Computer.</span><span class="sxs-lookup"><span data-stu-id="23938-137">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="23938-138">В этом случае необходимо выполнить командлет **Grant-CsOuPermission** на каждом контейнере или подразделении с компьютерами, на которых работает Lync Server, где отключено наследование разрешений.</span><span class="sxs-lookup"><span data-stu-id="23938-138">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="23938-139">Параметр ObjectType задает тип объекта.</span><span class="sxs-lookup"><span data-stu-id="23938-139">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="23938-140">Эта процедура добавляет необходимые элементы ACE непосредственно для указанных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="23938-140">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="23938-141">Для запуска этого командлета необходимы права пользователя, эквивалентные членству в группе администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="23938-141">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="23938-142">Если ACE, прошедшие проверку подлинности, также были удалены, необходимо предоставить этой учетной записи ACE для доступа на чтение в соответствующих контейнерах в корневом домене леса, как описано в разделе [разрешения пользователей с проверкой подлинности удалено в Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) или использовать учетную запись, входящую в группу администраторов предприятия.</span><span class="sxs-lookup"><span data-stu-id="23938-142">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="23938-143">**Установка необходимых элементов ACE для объектов Computer**</span><span class="sxs-lookup"><span data-stu-id="23938-143">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="23938-144">Выполните вход на компьютер, присоединенный к домену, с использованием учетной записи, которая является членом группы администраторов домена или имеет эквивалентные права пользователя.</span><span class="sxs-lookup"><span data-stu-id="23938-144">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="23938-145">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="23938-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="23938-146">Выполняем</span><span class="sxs-lookup"><span data-stu-id="23938-146">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="23938-147">Если параметр Domain не указан, значением по умолчанию является локальный домен.</span><span class="sxs-lookup"><span data-stu-id="23938-147">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="23938-148">Например:</span><span class="sxs-lookup"><span data-stu-id="23938-148">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="23938-149">В примере журнала C:\\заносится\\в журнал файл аупермиссионс. XML, вы должны найти \*\* \<\> результаты выполнения в\*\* конце каждой задачи и убедиться в отсутствии ошибок, а затем закрыть журнал.</span><span class="sxs-lookup"><span data-stu-id="23938-149">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="23938-150">Для проверки разрешений можно воспользоваться следующим командлетом:</span><span class="sxs-lookup"><span data-stu-id="23938-150">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="23938-151">Пример:</span><span class="sxs-lookup"><span data-stu-id="23938-151">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23938-152">При выполнении подготовки домена в корневом домене леса в заблокированной среде Active Directory следует учитывать, что Lync Server должен иметь доступ к схеме Active Directory и контейнерам конфигурации.</span><span class="sxs-lookup"><span data-stu-id="23938-152">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="23938-153">Если разрешение пользователя, прошедшего проверку подлинности по умолчанию, удалено из схемы&nbsp;или из контейнеров конфигурации в доменных СЛУЖБАХ Active Directory, доступ к заданному контейнеру разрешен только членам группы "Администраторы схемы" (для контейнера схемы) или "Администраторы предприятия" (для контейнера конфигурации).</span><span class="sxs-lookup"><span data-stu-id="23938-153">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="23938-154">Так как программе Setup. exe, командлетам командной консоли Lync Server и панели управления Lync Server требуется доступ к этим контейнерам, установка и установка средств администрирования не будут выполняться, если пользователь, выполняющий установку, не имеет прав, эквивалентных схеме Членство в группах "Администраторы" и "Администраторы предприятия".</span><span class="sxs-lookup"><span data-stu-id="23938-154">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="23938-155">Чтобы решить эту проблему, необходимо предоставить группе RTCUniversalGlobalWriteGroup доступ на чтение и запись к контейнерам Schema и Configuration.</span><span class="sxs-lookup"><span data-stu-id="23938-155">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

