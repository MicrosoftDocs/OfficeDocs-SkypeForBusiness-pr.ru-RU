---
title: 'Lync Server 2013: требования к членству в группах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93c1a79d39a70c21e353799a43c76599cc7af2b5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a><span data-ttu-id="3bc3a-102">Требования к членству в группах для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bc3a-102">Group membership requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bc3a-103">_**Последнее изменение темы:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="3bc3a-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="3bc3a-104">В следующей таблице обобщены группы или группы, к которым должен принадлежать пользователь, чтобы успешно установить, управлять и устранять неполадки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-104">The following table summarizes the group or groups that a person should belong to in order to successfully install, manage, and troubleshoot Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3bc3a-105">Исполняемый файл Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bc3a-105">Lync Server 2013 Executable</span></span></th>
<th><span data-ttu-id="3bc3a-106">Обязательное членство в группах</span><span class="sxs-lookup"><span data-stu-id="3bc3a-106">Group Membership Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3bc3a-107"><strong>Setup. exe</strong> — исполняемый файл, который запускает установку средств администрирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-107"><strong>Setup.exe</strong> – Executable that starts the installation of the Lync Server 2013 administrative tools.</span></span></p></td>
<td><p><span data-ttu-id="3bc3a-108">Участник группы локальных администраторов на компьютере, с которого запускается исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-108">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="3bc3a-109">Член группы "Пользователи домена" для чтения информации в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-109">Member of Domain Users group to read information in Active Directory Domain Services.</span></span> <span data-ttu-id="3bc3a-110">Этот уровень разрешений обязателен, так как для автоматической установки требуемых пакетов MSI на локальном компьютере необходимы права чтения и записи относительно защищенных ресурсов локального компьютера, таких как каталоги "Program Files", и защищенного реестра, такого как раздел "Local Machine".</span><span class="sxs-lookup"><span data-stu-id="3bc3a-110">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="3bc3a-111">Можно также делегировать разрешения на установку пользователям или группам, которым нежелательно предоставлять членство в группе администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-111">You can also delegate setup permissions to users or groups to whom you do not want to grant membership in the Domain Admins group.</span></span> <span data-ttu-id="3bc3a-112">Дополнительные сведения приведены в разделе <A href="lync-server-2013-granting-setup-permissions.md">предоставление разрешений на установку в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-112">For details, see <A href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</A> in the Deployment documentation.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bc3a-113"><strong>Deploy.exe</strong> – вызывается из setup.exe и отвечает за развертывание программных компонентов для ролей серверов.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-113"><strong>Deploy.exe</strong> – Called by setup.exe, deploy.exe is responsible for the deployment of the software components for the server roles.</span></span></p></td>
<td><p><span data-ttu-id="3bc3a-114">Участник группы локальных администраторов на компьютере, с которого запускается исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-114">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="3bc3a-115">Участник группы пользователей домена для чтения информации в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-115">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="3bc3a-116">Этот уровень разрешений обязателен, так как для автоматической установки требуемых пакетов MSI на локальном компьютере необходимы права чтения и записи относительно защищенных ресурсов локального компьютера, таких как каталоги "Program Files", и защищенного реестра, такого как раздел "Local Machine".</span><span class="sxs-lookup"><span data-stu-id="3bc3a-116">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span> <span data-ttu-id="3bc3a-117">Членство в группе RtcUniversalReadOnlyAdmins необходимо для чтения центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-117">Membership in RtcUniversalReadOnlyAdmins group is necessary to read the Central Management store.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3bc3a-118">Если вы используете операционную систему Windows Vista или операционную систему Windows 7, вам будет предложено управление учетными записями пользователей (UAC) для продолжения установки.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-118">If you are running the Windows Vista operating system or Windows 7 operating system, you will be prompted by User Account Control (UAC) to proceed with installation.</span></span> <span data-ttu-id="3bc3a-119">Если вход в систему выполнен от имени обычного пользователя, понадобится помощь участника локальной группы администраторов для ввода учетных данных, когда будет предложено указать учетную запись с разрешениями на установку программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-119">If you are logged on with a standard user account, you will need someone who is a member of the Local Administrators group to provide credentials when prompted for an account with permissions to install the software.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bc3a-120"><strong>Bootstrapper.exe</strong> – вызывается из setup.exe и отвечает за развертывание и конфигурирование ролей серверов.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-120"><strong>Bootstrapper.exe</strong> – Called by setup.exe, bootstrapper.exe is responsible for deployment and configuration of server roles.</span></span></p></td>
<td><p><span data-ttu-id="3bc3a-p105">Участник группы локальных администраторов на компьютере, с которого запускается исполняемый файл. Участник группы RTCUniversalServerAdmins для выполнения Bootstrapper.exe. Участник группы пользователей домена для чтения информации в доменных службах Active Directory. Этот уровень разрешений обязателен, так как для автоматической установки требуемых пакетов MSI на локальном компьютере необходимы права чтения и записи относительно защищенных ресурсов локального компьютера, таких как каталоги "Program Files", и защищенного реестра, такого как раздел "Local Machine".</span><span class="sxs-lookup"><span data-stu-id="3bc3a-p105">Member of the Local Administrators group on the computer from which the executable is run. Member of the RTCUniversalServerAdmins group to run Bootstrapper.exe. Member of Domain Users group to read information in AD DS. This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bc3a-125"><strong>Топологибуилдер</strong> — пользовательский интерфейс, основанный на мастере, для создания, просмотра, корректировки и проверки топологий Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-125"><strong>TopologyBuilder</strong> – Wizard-driven user interface to create, view, adjust, and validate Lync Server 2013 topologies.</span></span></p></td>
<td><p><span data-ttu-id="3bc3a-126">Участник группы локальных администраторов на компьютере, с которого запускается исполняемый файл для просмотра топологии.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-126">Member of the Local Administrators group on the computer from which the executable is run to view the topology.</span></span> <span data-ttu-id="3bc3a-127">Участник группы RTCUniversalServerAdmins для изменения настроек конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-127">Member of the RTCUniversalServerAdmins group to change configuration settings.</span></span> <span data-ttu-id="3bc3a-128">Участник группы RTCUniversalServerAdmins и группы администраторов домена или участник группы RTCUniversalServerAdmins (только если группе были предоставлены разрешения делегировать установку) для публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-128">Member of the RTCUniversalServerAdmins group and Domain Admins group, or member of the RTCUniversalServerAdmins group (only if the group has been granted delegate setup permissions), to publish the topology.</span></span> <span data-ttu-id="3bc3a-129">Дополнительные сведения о делегировании разрешений на установку, позволяющих членам группы RTCUniversalServerAdmins для публикации топологии без участия в группе "Администраторы домена", приведены в статье <a href="lync-server-2013-granting-setup-permissions.md">предоставление разрешений на установку в Lync Server 2013</a> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-129">For details about delegating setup permissions to allow members of the RTCUniversalServerAdmins group to publish the topology without being members of the Domain Admins group, see <a href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bc3a-130"><strong>Админуихост</strong> — графический пользовательский интерфейс на основе веб-сайта для управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-130"><strong>AdminUIHost</strong> – Web-based graphical user interface for managing Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="3bc3a-131">Участник группы CsAdministrator или участник другой роли управления доступом на основе ролей (RBAC), которой назначена конкретная административная задача.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-131">Member of CsAdministrator group or member of another role-based access control (RBAC) role to which the specific administrative task is assigned.</span></span> <span data-ttu-id="3bc3a-132">Панель управления Lync Server 2013 реализует изменения конфигурации, запуская командлеты командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-132">Lync Server 2013 Control Panel implements configuration changes by running Lync Server 2013 Management Shell cmdlets.</span></span> <span data-ttu-id="3bc3a-133">Список предопределенных ролей и членов командлетов, разрешенных для запуска, приведен в статье <a href="lync-server-2013-planning-for-role-based-access-control.md">Планирование управления доступом на основе ролей в Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-133">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bc3a-134"><strong>PowerShell. exe с загруженным модулем Lync server 2013</strong> — административным средством командной строки с командлетами, предназначенными для управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-134"><strong>PowerShell.exe with the Lync Server 2013 module loaded</strong> – Command-line administrative tool with cmdlets specific to management of Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="3bc3a-135">Участник группы CsAdministrator или участник другой роли RBAC, которой был назначен конкретных командлет.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-135">Member of CsAdministrator group or member of another RBAC role to which the specific cmdlet has been assigned.</span></span> <span data-ttu-id="3bc3a-136">Список предопределенных ролей и членов командлетов, разрешенных для запуска, приведен в статье <a href="lync-server-2013-planning-for-role-based-access-control.md">Планирование управления доступом на основе ролей в Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="3bc3a-136">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="3bc3a-137">Либо участник одной или нескольких из следующих групп, в зависимости от командлета:</span><span class="sxs-lookup"><span data-stu-id="3bc3a-137">Or, member of one or more of the following groups, depending on the cmdlet:</span></span></p>
<ul>
<li><p><span data-ttu-id="3bc3a-138">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3bc3a-138">RTCUniversalServerAdmins</span></span></p></li>
<li><p><span data-ttu-id="3bc3a-139">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3bc3a-139">RTCUniversalUserAdmins</span></span></p></li>
<li><p><span data-ttu-id="3bc3a-140">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="3bc3a-140">RTCUniversalReadOnlyAdmins</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

