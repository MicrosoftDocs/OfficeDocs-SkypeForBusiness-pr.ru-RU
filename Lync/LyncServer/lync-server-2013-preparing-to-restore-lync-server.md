---
title: 'Lync Server 2013: подготовка к восстановлению Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a470a338d05436be942201e6df6a864f955ac87c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a><span data-ttu-id="68bf6-102">Подготовка к восстановлению Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68bf6-102">Preparing to restore Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68bf6-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="68bf6-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="68bf6-104">Прежде чем приступить к восстановлению серверов и баз данных после сбоя, необходимо определить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="68bf6-104">Before you begin restoring servers and databases after a failure, you need to determine the following:</span></span>

  - <span data-ttu-id="68bf6-105">Что необходимо восстановить.</span><span class="sxs-lookup"><span data-stu-id="68bf6-105">What needs to be restored.</span></span>

  - <span data-ttu-id="68bf6-106">Оборудование, программное обеспечение, данные и инструменты, необходимые для восстановления.</span><span class="sxs-lookup"><span data-stu-id="68bf6-106">The hardware, software, data, and tools you need for restoration.</span></span>

<div>

## <a name="determining-what-to-restore"></a><span data-ttu-id="68bf6-107">Определение содержимого для восстановления</span><span class="sxs-lookup"><span data-stu-id="68bf6-107">Determining What to Restore</span></span>

<span data-ttu-id="68bf6-108">В этой статье описано, как восстановить сбои сервера Lync Server, происходящие на уровне сервера, пула или центра управления.</span><span class="sxs-lookup"><span data-stu-id="68bf6-108">This topic describes how to restore Lync Server outages that occur at the server, pool, or Central Management store level.</span></span> <span data-ttu-id="68bf6-109">Если центральное хранилище Management завершается сбоем, развертывание Lync Server продолжает работать, но вы не можете вносить какие – либо изменения в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="68bf6-109">If the Central Management store fails, your Lync Server deployment continues to function, but you cannot make any configuration changes.</span></span> <span data-ttu-id="68bf6-110">В случае сбоя сервера или сервера Standard Edition пул пользователей перестает работать.</span><span class="sxs-lookup"><span data-stu-id="68bf6-110">If a Back End Server or Standard Edition server fails, the user pool stops functioning.</span></span> <span data-ttu-id="68bf6-111">Если какой – либо другой сервер завершается сбоем, значение этого параметра зависит от роли сервера, на котором запущен сервер, и от того, содержит ли сервер одну или несколько баз данных.</span><span class="sxs-lookup"><span data-stu-id="68bf6-111">If any other server fails, the magnitude of the failure depends on the server role the server is running and whether the server hosts one or more databases.</span></span>

### <a name="what-to-restore"></a><span data-ttu-id="68bf6-112">Что нужно восстановить</span><span class="sxs-lookup"><span data-stu-id="68bf6-112">What to Restore</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68bf6-113">Если это не удалось</span><span class="sxs-lookup"><span data-stu-id="68bf6-113">If this failed</span></span></th>
<th><span data-ttu-id="68bf6-114">Ознакомьтесь с разделом:</span><span class="sxs-lookup"><span data-stu-id="68bf6-114">See this section:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68bf6-115">Standard Edition</span><span class="sxs-lookup"><span data-stu-id="68bf6-115">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="68bf6-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Восстановление сервера Standard Edition в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="68bf6-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68bf6-117">управления</span><span class="sxs-lookup"><span data-stu-id="68bf6-117">Central Management store</span></span></p></td>
<td><p><span data-ttu-id="68bf6-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Восстановление сервера, на котором размещается центральное хранилище для управления в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="68bf6-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restoring the server hosting the Central Management store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68bf6-119">Серверная версия Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="68bf6-119">Enterprise Edition Back End</span></span></p></td>
<td><p><span data-ttu-id="68bf6-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Восстановление сервера выпуска Enterprise Edition в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="68bf6-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68bf6-121">Зеркальный сервер основного выпуска Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="68bf6-121">Enterprise Edition Mirrored Back End Primary Server</span></span></p></td>
<td><p><span data-ttu-id="68bf6-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Восстановление зеркального сервера выпуска Enterprise Edition на сервере Lync Server 2013-PRIMARY</a></span><span class="sxs-lookup"><span data-stu-id="68bf6-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68bf6-123">Дополнительный сервер зеркального отображения для выпуска Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="68bf6-123">Enterprise Edition Mirrored Back End Secondary Server</span></span></p></td>
<td><p><span data-ttu-id="68bf6-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Восстановление зеркального сервера выпуска Enterprise Edition на сервере Lync Server 2013 — зеркало</a></span><span class="sxs-lookup"><span data-stu-id="68bf6-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68bf6-125">Любой сервер Enterprise Edition, на котором работает серверная роль, например сервер переднего плана, пограничный сервер, режиссер, сервер-посредник или сохраняемый сервер чата.</span><span class="sxs-lookup"><span data-stu-id="68bf6-125">Any Enterprise Edition server running a server role, such as a Front End Server, Edge Server, Director, Mediation Server,.or Persistent Chat Server.</span></span></p></td>
<td><p><span data-ttu-id="68bf6-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Восстановление сервера участника Enterprise Edition в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="68bf6-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68bf6-127">Пул всего сервера Lync Server</span><span class="sxs-lookup"><span data-stu-id="68bf6-127">An entire Lync Server pool</span></span></p></td>
<td><p><span data-ttu-id="68bf6-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Восстановление пула сервера Lync Server в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="68bf6-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restoring a Lync Server pool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68bf6-129">Корпоративное хранилище файлов в выпуске</span><span class="sxs-lookup"><span data-stu-id="68bf6-129">Enterprise Edition File Store</span></span></p></td>
<td><p><span data-ttu-id="68bf6-130"><a href="lync-server-2013-restoring-a-file-store.md">Восстановление хранилища файлов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="68bf6-130"><a href="lync-server-2013-restoring-a-file-store.md">Restoring a file store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68bf6-131">Автономная база данных мониторинга или архивная база данных</span><span class="sxs-lookup"><span data-stu-id="68bf6-131">A standalone Monitoring database or Archiving database</span></span></p></td>
<td><p><span data-ttu-id="68bf6-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Восстановление данных мониторинга или архивации в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="68bf6-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restoring monitoring or archiving data in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68bf6-133">Отдельная база данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="68bf6-133">A stand-alone Persistent Chat database</span></span></p></td>
<td><p><span data-ttu-id="68bf6-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Восстановление данных из сохраняемого чата в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="68bf6-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restoring Persistent Chat data in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a><span data-ttu-id="68bf6-135">Сбор сведений о оборудовании, программном обеспечении и инструментах</span><span class="sxs-lookup"><span data-stu-id="68bf6-135">Gathering Hardware, Software, and Tools</span></span>

<span data-ttu-id="68bf6-136">При восстановлении сервера необходимо начать с нового или чистого компьютера.</span><span class="sxs-lookup"><span data-stu-id="68bf6-136">When you restore a server, you need to start with a new or clean computer.</span></span> <span data-ttu-id="68bf6-137">Кроме того, на компьютере должно быть доступно следующее оборудование и программное обеспечение:</span><span class="sxs-lookup"><span data-stu-id="68bf6-137">Additionally, you must have the following hardware and software available:</span></span>

  - <span data-ttu-id="68bf6-138">Пустой или новый сервер с таким же полным доменным именем (FQDN), как и у сервера, на котором произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="68bf6-138">A clean or new server with the same fully qualified domain name (FQDN) as the server that failed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="68bf6-139">При установке операционной системы убедитесь в том, что вы не удаляете учетную запись компьютера в доменных службах Active Directory и убедитесь в том, что разрешения группы для учетной записи сохранены.</span><span class="sxs-lookup"><span data-stu-id="68bf6-139">When you install the operating system, make sure that you do not delete the computer account in Active Directory Domain Services, and verify that the group permissions for the account are retained.</span></span>

    
    </div>

  - <span data-ttu-id="68bf6-140">Установка программного обеспечения для операционной системы.</span><span class="sxs-lookup"><span data-stu-id="68bf6-140">Installation software for the operating system.</span></span> <span data-ttu-id="68bf6-141">Для установки операционной системы используйте процедуры развертывания сервера и конфигурации, установленные вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="68bf6-141">To install the operating system, use the server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="68bf6-142">При восстановлении службы вам должны быть доступны указанные ниже процедуры и требования к конфигурации.</span><span class="sxs-lookup"><span data-stu-id="68bf6-142">You should have these procedures and configuration requirements available when you restore service.</span></span>

  - <span data-ttu-id="68bf6-143">Установка программного обеспечения SQL Server 2012 или SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="68bf6-143">Installation software for SQL Server 2012 or SQL Server 2008 R2.</span></span> <span data-ttu-id="68bf6-144">Чтобы установить сервер базы данных, используйте соответствующую версию SQL Server, а также процедуры и конфигурации сервера базы данных, установленные вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="68bf6-144">To install a database server, use the appropriate version of SQL Server and the database server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="68bf6-145">При восстановлении службы вам должны быть доступны указанные ниже процедуры и требования к конфигурации.</span><span class="sxs-lookup"><span data-stu-id="68bf6-145">You should have these procedures and configuration requirements available when you restore service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68bf6-146">Мастер развертывания Lync Server автоматически устанавливает SQL Server 2012 Express на сервер Standard Edition и на любой другой сервер Lync Server при установке локального хранилища конфигураций, если только вы не предустановили SQL Server 2012 или SQL Server 2008 R2 для сервер.</span><span class="sxs-lookup"><span data-stu-id="68bf6-146">The Lync Server Deployment Wizard automatically installs SQL Server 2012 Express on each Standard Edition server and on any other Lync Server server when a local configuration store is installed, unless you have preinstalled SQL Server 2012 or SQL Server 2008 R2 on the server.</span></span>

    
    </div>

  - <span data-ttu-id="68bf6-147">Программное обеспечение для принятия изображений системы.</span><span class="sxs-lookup"><span data-stu-id="68bf6-147">Software for taking system images.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="68bf6-148">Мы рекомендуем использовать копию системы после установки операционной системы и сервера SQL Server, а также перед началом восстановления для использования этого образа в качестве точки отката в случае, если что-то пошло не так во время восстановления.</span><span class="sxs-lookup"><span data-stu-id="68bf6-148">We recommend that you take an image copy of the system after you install the operating system and SQL Server, and before you start restoration, so that you can use this image as a rollback point in case something goes wrong during restoration.</span></span>

    
    </div>

  - <span data-ttu-id="68bf6-149">Установка программного обеспечения Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68bf6-149">Lync Server 2013 installation software.</span></span> <span data-ttu-id="68bf6-150">Мастер развертывания Lync Server находится в папке установки Lync Server или мультимедиа в \\файле Setup. exe\\программы\\установки amd64.</span><span class="sxs-lookup"><span data-stu-id="68bf6-150">The Lync Server Deployment Wizard is located in the Lync Server installation folder or media at \\setup\\amd64\\Setup.exe.</span></span>

<span data-ttu-id="68bf6-151">Во время восстановления вы используете следующие инструменты:</span><span class="sxs-lookup"><span data-stu-id="68bf6-151">During restoration, you use the following tools:</span></span>

  - <span data-ttu-id="68bf6-152">Командлеты оболочки Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="68bf6-152">Lync Server Management Shell cmdlets</span></span>

  - <span data-ttu-id="68bf6-153">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="68bf6-153">Import-CsUserData</span></span>

  - <span data-ttu-id="68bf6-154">Средства для восстановления папок Windows</span><span class="sxs-lookup"><span data-stu-id="68bf6-154">Tools for restoring Windows folders</span></span>

  - <span data-ttu-id="68bf6-155">топологий</span><span class="sxs-lookup"><span data-stu-id="68bf6-155">Topology Builder</span></span>

  - <span data-ttu-id="68bf6-156">Служебные программы для работы с базами данных SQL Server, например SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="68bf6-156">SQL Server database utilities, such as SQL Server Management Studio</span></span>

</div>

<div>

## <a name="preparing-to-restore-a-server"></a><span data-ttu-id="68bf6-157">Подготовка к восстановлению сервера</span><span class="sxs-lookup"><span data-stu-id="68bf6-157">Preparing to Restore a Server</span></span>

<span data-ttu-id="68bf6-158">Прежде чем восстанавливать сервер, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="68bf6-158">Before you restore the server, you must perform the following steps:</span></span>

1.  <span data-ttu-id="68bf6-159">Установите операционную систему.</span><span class="sxs-lookup"><span data-stu-id="68bf6-159">Install the operating system.</span></span>

2.  <span data-ttu-id="68bf6-160">Если сервер является конечным сервером, установите SQL Server 2012 или SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="68bf6-160">If the server is a Back End Server, install SQL Server 2012 or SQL Server 2008 R2.</span></span>

3.  <span data-ttu-id="68bf6-161">Восстановите и порегистрируйте сертификаты.</span><span class="sxs-lookup"><span data-stu-id="68bf6-161">Restore or reenroll your certificates.</span></span> <span data-ttu-id="68bf6-162">Подробнее о сертификатах можно узнать в статье "дополнительные требования к резервному копированию" в статье [требования к резервному копированию и восстановлению в Lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="68bf6-162">For details about certificates, see "Additional Backup Requirements" in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

4.  <span data-ttu-id="68bf6-163">Сделайте снимок системы перед началом восстановления, чтобы использовать его в качестве точки отката, если что-то пойдет не так во время восстановления.</span><span class="sxs-lookup"><span data-stu-id="68bf6-163">Take an image of the system before starting restoration to use as a rollback point, in case something goes wrong during restoration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="68bf6-164">Мастер развертывания Lync Server и командлеты, описанные в описанных в этой статье процедурах, и связанные разделы, задают все необходимые списки управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="68bf6-164">The Lync Server Deployment Wizard and cmdlets described in the procedures in this topic, and related topics, set all required access control lists (ACLs).</span></span>



</div>

<span data-ttu-id="68bf6-165">Перед началом восстановления убедитесь в том, что оборудование и программное обеспечение, необходимое для восстановления необходимых компонентов, доступны.</span><span class="sxs-lookup"><span data-stu-id="68bf6-165">Verify that the hardware and the software that you need for the components that you plan to restore are available before you start restoration.</span></span> <span data-ttu-id="68bf6-166">После установки операционной системы и сервера SQL Server можно выполнить удаленное выполнение практических действий, описанных в описанных ниже процедурах восстановления.</span><span class="sxs-lookup"><span data-stu-id="68bf6-166">After you install the operating system and SQL Server, most of the steps in the following restoration procedures can be run remotely.</span></span> <span data-ttu-id="68bf6-167">Исключения указаны в процедурах.</span><span class="sxs-lookup"><span data-stu-id="68bf6-167">The exceptions are noted in the procedures.</span></span>

<span data-ttu-id="68bf6-168">Кроме того, вы должны иметь план резервного копирования и восстановления своей организации, а также данные из последней резервной копии, например сведения о листах, указанных в этом документе (Дополнительные сведения можно найти в разделе [листы резервного копирования и восстановления для Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)). доступно, прежде чем приступить к восстановлению.</span><span class="sxs-lookup"><span data-stu-id="68bf6-168">You should also have your organization's backup and restoration plan and the information from your last backup, such as the information in the worksheets in this document (for details, see [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), available before you begin restoration.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

