---
title: 'Lync Server 2013: подготовка к восстановлению Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70a011109c985f126c591698f3ea572242498771
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a><span data-ttu-id="730a9-102">Подготовка к восстановлению Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="730a9-102">Preparing to restore Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="730a9-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="730a9-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="730a9-104">Прежде чем приступать к восстановлению серверов и баз данных после сбоя, необходимо определить следующее:</span><span class="sxs-lookup"><span data-stu-id="730a9-104">Before you begin restoring servers and databases after a failure, you need to determine the following:</span></span>

  - <span data-ttu-id="730a9-105">Что необходимо восстановить.</span><span class="sxs-lookup"><span data-stu-id="730a9-105">What needs to be restored.</span></span>

  - <span data-ttu-id="730a9-106">Оборудование, программное обеспечение, данные и инструменты, необходимые для восстановления.</span><span class="sxs-lookup"><span data-stu-id="730a9-106">The hardware, software, data, and tools you need for restoration.</span></span>

<div>

## <a name="determining-what-to-restore"></a><span data-ttu-id="730a9-107">Определение объектов для восстановления</span><span class="sxs-lookup"><span data-stu-id="730a9-107">Determining What to Restore</span></span>

<span data-ttu-id="730a9-108">В этом разделе описывается, как восстановить простои Lync Server, происходящие на уровне сервера, пула или центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="730a9-108">This topic describes how to restore Lync Server outages that occur at the server, pool, or Central Management store level.</span></span> <span data-ttu-id="730a9-109">Если центральное хранилище управления завершается с ошибкой, развертывание Lync Server продолжает работать, но вы не можете вносить какие – либо изменения в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="730a9-109">If the Central Management store fails, your Lync Server deployment continues to function, but you cannot make any configuration changes.</span></span> <span data-ttu-id="730a9-110">В случае сбоя фонового сервера или сервера Standard Edition пул пользователей перестает работать.</span><span class="sxs-lookup"><span data-stu-id="730a9-110">If a Back End Server or Standard Edition server fails, the user pool stops functioning.</span></span> <span data-ttu-id="730a9-111">Если какой-либо другой сервер завершается с ошибкой, то величина сбоя зависит от роли сервера, на котором работает сервер, и от того, содержит ли сервер одну или несколько баз данных.</span><span class="sxs-lookup"><span data-stu-id="730a9-111">If any other server fails, the magnitude of the failure depends on the server role the server is running and whether the server hosts one or more databases.</span></span>

### <a name="what-to-restore"></a><span data-ttu-id="730a9-112">Восстановление</span><span class="sxs-lookup"><span data-stu-id="730a9-112">What to Restore</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="730a9-113">Если это не удалось</span><span class="sxs-lookup"><span data-stu-id="730a9-113">If this failed</span></span></th>
<th><span data-ttu-id="730a9-114">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="730a9-114">See this section:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="730a9-115">Сервер Standard Edition</span><span class="sxs-lookup"><span data-stu-id="730a9-115">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="730a9-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Восстановление сервера Standard Edition в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="730a9-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="730a9-117">Центральное хранилище управления</span><span class="sxs-lookup"><span data-stu-id="730a9-117">Central Management store</span></span></p></td>
<td><p><span data-ttu-id="730a9-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Восстановление сервера, на котором размещается центральное хранилище управления, в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="730a9-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restoring the server hosting the Central Management store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="730a9-119">Серверная часть Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="730a9-119">Enterprise Edition Back End</span></span></p></td>
<td><p><span data-ttu-id="730a9-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Восстановление внутреннего сервера Enterprise Edition в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="730a9-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="730a9-121">Зеркальный сервер основного сервера Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="730a9-121">Enterprise Edition Mirrored Back End Primary Server</span></span></p></td>
<td><p><span data-ttu-id="730a9-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Восстановление зеркального сервера переднего план выпуска Enterprise Edition в Lync Server 2013 — основной</a></span><span class="sxs-lookup"><span data-stu-id="730a9-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="730a9-123">Дополнительный зеркальный сервер сервера Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="730a9-123">Enterprise Edition Mirrored Back End Secondary Server</span></span></p></td>
<td><p><span data-ttu-id="730a9-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Восстановление зеркального сервера переднего план выпуска Enterprise Edition в Lync Server 2013 — зеркало</a></span><span class="sxs-lookup"><span data-stu-id="730a9-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="730a9-125">Любой сервер Enterprise Edition, на котором работает роль сервера, например, сервер переднего плана, пограничный сервер, директор, сервер-посредник или сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="730a9-125">Any Enterprise Edition server running a server role, such as a Front End Server, Edge Server, Director, Mediation Server,.or Persistent Chat Server.</span></span></p></td>
<td><p><span data-ttu-id="730a9-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Восстановление рядового сервера Enterprise Edition в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="730a9-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="730a9-127">Весь пул Lync Server</span><span class="sxs-lookup"><span data-stu-id="730a9-127">An entire Lync Server pool</span></span></p></td>
<td><p><span data-ttu-id="730a9-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Восстановление пула Lync Server в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="730a9-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restoring a Lync Server pool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="730a9-129">Хранилище файлов Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="730a9-129">Enterprise Edition File Store</span></span></p></td>
<td><p><span data-ttu-id="730a9-130"><a href="lync-server-2013-restoring-a-file-store.md">Восстановление хранилища файлов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="730a9-130"><a href="lync-server-2013-restoring-a-file-store.md">Restoring a file store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="730a9-131">Автономная база данных мониторинга или база данных архивации</span><span class="sxs-lookup"><span data-stu-id="730a9-131">A standalone Monitoring database or Archiving database</span></span></p></td>
<td><p><span data-ttu-id="730a9-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Восстановление данных мониторинга или архивации в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="730a9-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restoring monitoring or archiving data in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="730a9-133">Автономная база данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="730a9-133">A stand-alone Persistent Chat database</span></span></p></td>
<td><p><span data-ttu-id="730a9-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Восстановление данных сохраняемого чата в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="730a9-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restoring Persistent Chat data in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a><span data-ttu-id="730a9-135">Сбор данных о оборудовании, программном обеспечении и средствах</span><span class="sxs-lookup"><span data-stu-id="730a9-135">Gathering Hardware, Software, and Tools</span></span>

<span data-ttu-id="730a9-136">При восстановлении сервера необходимо начать с нового или чистого компьютера.</span><span class="sxs-lookup"><span data-stu-id="730a9-136">When you restore a server, you need to start with a new or clean computer.</span></span> <span data-ttu-id="730a9-137">Кроме того, необходимо наличие следующего аппаратного и программного обеспечения:</span><span class="sxs-lookup"><span data-stu-id="730a9-137">Additionally, you must have the following hardware and software available:</span></span>

  - <span data-ttu-id="730a9-138">Чистый или новый сервер с таким же полным доменным именем (FQDN), что и сервер, на котором произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="730a9-138">A clean or new server with the same fully qualified domain name (FQDN) as the server that failed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="730a9-139">При установке операционной системы убедитесь, что учетная запись компьютера не удалена в доменных службах Active Directory, и убедитесь, что разрешения группы для учетной записи сохранены.</span><span class="sxs-lookup"><span data-stu-id="730a9-139">When you install the operating system, make sure that you do not delete the computer account in Active Directory Domain Services, and verify that the group permissions for the account are retained.</span></span>

    
    </div>

  - <span data-ttu-id="730a9-140">Установка программного обеспечения для операционной системы.</span><span class="sxs-lookup"><span data-stu-id="730a9-140">Installation software for the operating system.</span></span> <span data-ttu-id="730a9-141">Чтобы установить операционную систему, воспользуйтесь процедурами и конфигурациями развертывания сервера, установленными в Организации.</span><span class="sxs-lookup"><span data-stu-id="730a9-141">To install the operating system, use the server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="730a9-142">При восстановлении службы должны быть доступны указанные ниже процедуры и требования к конфигурации.</span><span class="sxs-lookup"><span data-stu-id="730a9-142">You should have these procedures and configuration requirements available when you restore service.</span></span>

  - <span data-ttu-id="730a9-143">Установка программного обеспечения для SQL Server 2012 или SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="730a9-143">Installation software for SQL Server 2012 or SQL Server 2008 R2.</span></span> <span data-ttu-id="730a9-144">Чтобы установить сервер баз данных, используйте соответствующую версию SQL Server, а также процедуры и конфигурации развертывания сервера базы данных, установленные вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="730a9-144">To install a database server, use the appropriate version of SQL Server and the database server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="730a9-145">При восстановлении службы должны быть доступны указанные ниже процедуры и требования к конфигурации.</span><span class="sxs-lookup"><span data-stu-id="730a9-145">You should have these procedures and configuration requirements available when you restore service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="730a9-146">Мастер развертывания Lync Server автоматически устанавливает SQL Server 2012 Express на каждом сервере Standard Edition и на любом другом сервере Lync Server при установке локального хранилища конфигурации, если вы не предустановили SQL Server 2012 или SQL Server 2008 R2 на сервер.</span><span class="sxs-lookup"><span data-stu-id="730a9-146">The Lync Server Deployment Wizard automatically installs SQL Server 2012 Express on each Standard Edition server and on any other Lync Server server when a local configuration store is installed, unless you have preinstalled SQL Server 2012 or SQL Server 2008 R2 on the server.</span></span>

    
    </div>

  - <span data-ttu-id="730a9-147">Программное обеспечение для принятия образов системы.</span><span class="sxs-lookup"><span data-stu-id="730a9-147">Software for taking system images.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="730a9-148">Мы рекомендуем использовать копию системы после установки операционной системы и SQL Server, а также до начала восстановления, чтобы использовать это изображение в качестве точки отката в случае, если что-то пойдет не так во время восстановления.</span><span class="sxs-lookup"><span data-stu-id="730a9-148">We recommend that you take an image copy of the system after you install the operating system and SQL Server, and before you start restoration, so that you can use this image as a rollback point in case something goes wrong during restoration.</span></span>

    
    </div>

  - <span data-ttu-id="730a9-149">Установка программного обеспечения Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="730a9-149">Lync Server 2013 installation software.</span></span> <span data-ttu-id="730a9-150">Мастер развертывания Lync Server находится в папке установки Lync Server или на носителе во время \\установки\\amd64\\. exe.</span><span class="sxs-lookup"><span data-stu-id="730a9-150">The Lync Server Deployment Wizard is located in the Lync Server installation folder or media at \\setup\\amd64\\Setup.exe.</span></span>

<span data-ttu-id="730a9-151">Во время восстановления используются следующие инструменты:</span><span class="sxs-lookup"><span data-stu-id="730a9-151">During restoration, you use the following tools:</span></span>

  - <span data-ttu-id="730a9-152">Командлеты командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="730a9-152">Lync Server Management Shell cmdlets</span></span>

  - <span data-ttu-id="730a9-153">Import — CsUserData</span><span class="sxs-lookup"><span data-stu-id="730a9-153">Import-CsUserData</span></span>

  - <span data-ttu-id="730a9-154">Средства для восстановления папок Windows</span><span class="sxs-lookup"><span data-stu-id="730a9-154">Tools for restoring Windows folders</span></span>

  - <span data-ttu-id="730a9-155">Построитель топологий</span><span class="sxs-lookup"><span data-stu-id="730a9-155">Topology Builder</span></span>

  - <span data-ttu-id="730a9-156">Служебные программы для баз данных SQL Server, например SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="730a9-156">SQL Server database utilities, such as SQL Server Management Studio</span></span>

</div>

<div>

## <a name="preparing-to-restore-a-server"></a><span data-ttu-id="730a9-157">Подготовка к восстановлению сервера</span><span class="sxs-lookup"><span data-stu-id="730a9-157">Preparing to Restore a Server</span></span>

<span data-ttu-id="730a9-158">Перед восстановлением сервера необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="730a9-158">Before you restore the server, you must perform the following steps:</span></span>

1.  <span data-ttu-id="730a9-159">Установите операционную систему.</span><span class="sxs-lookup"><span data-stu-id="730a9-159">Install the operating system.</span></span>

2.  <span data-ttu-id="730a9-160">Если сервер является внутренним сервером, установите SQL Server 2012 или SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="730a9-160">If the server is a Back End Server, install SQL Server 2012 or SQL Server 2008 R2.</span></span>

3.  <span data-ttu-id="730a9-161">Восстановите или повторно зарегистрируйте сертификаты.</span><span class="sxs-lookup"><span data-stu-id="730a9-161">Restore or reenroll your certificates.</span></span> <span data-ttu-id="730a9-162">Сведения о сертификатах можно найти в статье "дополнительные требования к резервному копированию" в статье [требования к резервному копированию и восстановлению в Lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="730a9-162">For details about certificates, see "Additional Backup Requirements" in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

4.  <span data-ttu-id="730a9-163">Создайте образ системы перед началом восстановления, чтобы использовать его в качестве точки отката, если что-то пойдет не так во время восстановления.</span><span class="sxs-lookup"><span data-stu-id="730a9-163">Take an image of the system before starting restoration to use as a rollback point, in case something goes wrong during restoration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="730a9-164">Мастер развертывания Lync Server и командлеты, описанные в процедурах, описанных в этой статье, и связанные темы задают все необходимые списки управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="730a9-164">The Lync Server Deployment Wizard and cmdlets described in the procedures in this topic, and related topics, set all required access control lists (ACLs).</span></span>



</div>

<span data-ttu-id="730a9-165">Прежде чем начать восстановление, убедитесь, что оборудование и программное обеспечение, необходимое для восстанавливаемых компонентов, доступны.</span><span class="sxs-lookup"><span data-stu-id="730a9-165">Verify that the hardware and the software that you need for the components that you plan to restore are available before you start restoration.</span></span> <span data-ttu-id="730a9-166">После установки операционной системы и сервера SQL Server большинство действий, описанных в следующих процедурах восстановления, могут быть запущены удаленно.</span><span class="sxs-lookup"><span data-stu-id="730a9-166">After you install the operating system and SQL Server, most of the steps in the following restoration procedures can be run remotely.</span></span> <span data-ttu-id="730a9-167">Исключения указаны в процедурах.</span><span class="sxs-lookup"><span data-stu-id="730a9-167">The exceptions are noted in the procedures.</span></span>

<span data-ttu-id="730a9-168">Кроме того, вы должны иметь план резервного копирования и восстановления вашей организации, а также сведения из последней резервной копии, такие как сведения на листах в этом документе (Дополнительные сведения см. в статье [резервное копирование и восстановление для Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), которые доступны до начала восстановления.</span><span class="sxs-lookup"><span data-stu-id="730a9-168">You should also have your organization's backup and restoration plan and the information from your last backup, such as the information in the worksheets in this document (for details, see [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), available before you begin restoration.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

