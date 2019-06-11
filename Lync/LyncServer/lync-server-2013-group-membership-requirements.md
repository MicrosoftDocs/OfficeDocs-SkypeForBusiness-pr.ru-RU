---
title: 'Lync Server 2013: требования членства в группах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6aed308674cc334cfb8f3d4f214ce7388ae89fea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a><span data-ttu-id="03f91-102">Требования членства в группах для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03f91-102">Group membership requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03f91-103">_**Тема последнего изменения:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="03f91-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="03f91-104">В приведенной ниже таблице перечислены группы или группы, которым должен принадлежать человек, чтобы успешно установить, управлять и устранять неполадки в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03f91-104">The following table summarizes the group or groups that a person should belong to in order to successfully install, manage, and troubleshoot Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03f91-105">Исполняемый файл Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03f91-105">Lync Server 2013 Executable</span></span></th>
<th><span data-ttu-id="03f91-106">Требуется членство в группах</span><span class="sxs-lookup"><span data-stu-id="03f91-106">Group Membership Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03f91-107"><strong>Setup. exe</strong> — исполняемый файл, в котором начинается установка средств администрирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03f91-107"><strong>Setup.exe</strong> – Executable that starts the installation of the Lync Server 2013 administrative tools.</span></span></p></td>
<td><p><span data-ttu-id="03f91-108">Входить в локальную группу администраторов на компьютере, с которого запускается исполняемый объект.</span><span class="sxs-lookup"><span data-stu-id="03f91-108">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="03f91-109">Член группы "Пользователи домена" для чтения данных в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="03f91-109">Member of Domain Users group to read information in Active Directory Domain Services.</span></span> <span data-ttu-id="03f91-110">Этот уровень разрешений необходим, поскольку автоматическая установка необходимых пакетов MSI на локальном компьютере требует наличия привилегий, позволяющих считывать и записывать данные на защищенные локальные ресурсы компьютера, такие как каталоги программных файлов и защищенные. реестр, например куст локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="03f91-110">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="03f91-111">Вы также можете делегировать разрешения на настройку для пользователей или групп, которым вы не хотите предоставлять членство в группе Администраторы домена.</span><span class="sxs-lookup"><span data-stu-id="03f91-111">You can also delegate setup permissions to users or groups to whom you do not want to grant membership in the Domain Admins group.</span></span> <span data-ttu-id="03f91-112">Подробности можно найти <A href="lync-server-2013-granting-setup-permissions.md">в разделе Предоставление разрешений на установку в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="03f91-112">For details, see <A href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</A> in the Deployment documentation.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f91-113">Программа Deploy. <strong>exe</strong> , вызываемая Setup. exe, отвечает за развертывание компонентов программного обеспечения для ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="03f91-113"><strong>Deploy.exe</strong> – Called by setup.exe, deploy.exe is responsible for the deployment of the software components for the server roles.</span></span></p></td>
<td><p><span data-ttu-id="03f91-114">Входить в локальную группу администраторов на компьютере, с которого запускается исполняемый объект.</span><span class="sxs-lookup"><span data-stu-id="03f91-114">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="03f91-115">Член группы "Пользователи домена" для чтения данных в доменных СЛУЖБах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="03f91-115">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="03f91-116">Этот уровень разрешений необходим, поскольку автоматическая установка необходимых пакетов MSI на локальном компьютере требует наличия привилегий, позволяющих считывать и записывать данные на защищенные локальные ресурсы компьютера, такие как каталоги программных файлов и защищенные. реестр, например куст локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="03f91-116">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span> <span data-ttu-id="03f91-117">Членство в группе Рткуниверсалреадонлядминс необходимо для чтения хранилища центрального управления.</span><span class="sxs-lookup"><span data-stu-id="03f91-117">Membership in RtcUniversalReadOnlyAdmins group is necessary to read the Central Management store.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="03f91-118">Если вы используете операционную систему Windows Vista или операционную систему Windows 7, вам будет предложено управлять учетными записями пользователей (UAC) для продолжения установки.</span><span class="sxs-lookup"><span data-stu-id="03f91-118">If you are running the Windows Vista operating system or Windows 7 operating system, you will be prompted by User Account Control (UAC) to proceed with installation.</span></span> <span data-ttu-id="03f91-119">Если вы вошли в систему с помощью стандартной учетной записи пользователя, вам понадобится кто-то, кто входит в локальную группу администраторов для предоставления учетных данных, если вам будет предложено ввести учетную запись с разрешениями на установку программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="03f91-119">If you are logged on with a standard user account, you will need someone who is a member of the Local Administrators group to provide credentials when prompted for an account with permissions to install the software.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f91-120"><strong>Загрузчик.</strong> exe — вызывается Setup. exe, загрузчик. exe отвечает за развертывание и настройку ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="03f91-120"><strong>Bootstrapper.exe</strong> – Called by setup.exe, bootstrapper.exe is responsible for deployment and configuration of server roles.</span></span></p></td>
<td><p><span data-ttu-id="03f91-121">Входить в локальную группу администраторов на компьютере, с которого запускается исполняемый объект.</span><span class="sxs-lookup"><span data-stu-id="03f91-121">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="03f91-122">Член группы Рткуниверсалсерверадминс для запуска загрузчика. exe.</span><span class="sxs-lookup"><span data-stu-id="03f91-122">Member of the RTCUniversalServerAdmins group to run Bootstrapper.exe.</span></span> <span data-ttu-id="03f91-123">Член группы "Пользователи домена" для чтения данных в доменных СЛУЖБах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="03f91-123">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="03f91-124">Этот уровень разрешений необходим, поскольку автоматическая установка необходимых пакетов MSI на локальном компьютере требует наличия привилегий, позволяющих считывать и записывать данные на защищенные локальные ресурсы компьютера, такие как каталоги программных файлов и защищенные. реестр, например куст локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="03f91-124">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f91-125"><strong>Топологибуилдер</strong> — пользовательский интерфейс, управляемый мастером, для создания, просмотра, настройки и проверки топологий Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03f91-125"><strong>TopologyBuilder</strong> – Wizard-driven user interface to create, view, adjust, and validate Lync Server 2013 topologies.</span></span></p></td>
<td><p><span data-ttu-id="03f91-126">Член локальной группы администраторов на компьютере, с которого запускается исполняемый объект для просмотра топологии.</span><span class="sxs-lookup"><span data-stu-id="03f91-126">Member of the Local Administrators group on the computer from which the executable is run to view the topology.</span></span> <span data-ttu-id="03f91-127">Чтобы изменить параметры конфигурации, пользователь должен быть членом группы Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="03f91-127">Member of the RTCUniversalServerAdmins group to change configuration settings.</span></span> <span data-ttu-id="03f91-128">Чтобы опубликовать топологию, участник группы Рткуниверсалсерверадминс и группа администраторов домена или член группы Рткуниверсалсерверадминс (только если группе предоставлены разрешения на настройку делегирования).</span><span class="sxs-lookup"><span data-stu-id="03f91-128">Member of the RTCUniversalServerAdmins group and Domain Admins group, or member of the RTCUniversalServerAdmins group (only if the group has been granted delegate setup permissions), to publish the topology.</span></span> <span data-ttu-id="03f91-129">Сведения о делегировании разрешений на настройку для разрешения пользователям, которым разрешено публиковать топологию, без участия в группе "Администраторы домена", приведены в разделе <a href="lync-server-2013-granting-setup-permissions.md">предоставление разрешений на установку в Lync Server 2013</a> в развертывании содержатся.</span><span class="sxs-lookup"><span data-stu-id="03f91-129">For details about delegating setup permissions to allow members of the RTCUniversalServerAdmins group to publish the topology without being members of the Domain Admins group, see <a href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f91-130"><strong>Админуихост</strong> — графический пользовательский интерфейс на основе веб-сайта для управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03f91-130"><strong>AdminUIHost</strong> – Web-based graphical user interface for managing Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="03f91-131">Участник группы Ксадминистратор или участник другой роли управления доступом на основе ролей (RBAC), которым назначена определенная административная задача.</span><span class="sxs-lookup"><span data-stu-id="03f91-131">Member of CsAdministrator group or member of another role-based access control (RBAC) role to which the specific administrative task is assigned.</span></span> <span data-ttu-id="03f91-132">Панель управления Lync Server 2013 реализует изменения конфигурации с помощью командлетов командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03f91-132">Lync Server 2013 Control Panel implements configuration changes by running Lync Server 2013 Management Shell cmdlets.</span></span> <span data-ttu-id="03f91-133">Список стандартных ролей и членов командлетов, которые разрешено запускать, можно найти <a href="lync-server-2013-planning-for-role-based-access-control.md">в разделе Планирование управления доступом на основе ролей в Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="03f91-133">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f91-134"><strong>PowerShell. exe с загруженным модулем Lync server 2013</strong> — административным средством командной строки с командлетами, предназначенными для управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03f91-134"><strong>PowerShell.exe with the Lync Server 2013 module loaded</strong> – Command-line administrative tool with cmdlets specific to management of Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="03f91-135">Участник группы Ксадминистратор или член другой роли RBAC, которому назначен определенный командлет.</span><span class="sxs-lookup"><span data-stu-id="03f91-135">Member of CsAdministrator group or member of another RBAC role to which the specific cmdlet has been assigned.</span></span> <span data-ttu-id="03f91-136">Список стандартных ролей и членов командлетов, которые разрешено запускать, можно найти <a href="lync-server-2013-planning-for-role-based-access-control.md">в разделе Планирование управления доступом на основе ролей в Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="03f91-136">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="03f91-137">Или, если вы входите в одну или несколько из следующих групп, в зависимости от командлета:</span><span class="sxs-lookup"><span data-stu-id="03f91-137">Or, member of one or more of the following groups, depending on the cmdlet:</span></span></p>
<ul>
<li><p><span data-ttu-id="03f91-138">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="03f91-138">RTCUniversalServerAdmins</span></span></p></li>
<li><p><span data-ttu-id="03f91-139">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="03f91-139">RTCUniversalUserAdmins</span></span></p></li>
<li><p><span data-ttu-id="03f91-140">Рткуниверсалреадонлядминс</span><span class="sxs-lookup"><span data-stu-id="03f91-140">RTCUniversalReadOnlyAdmins</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

