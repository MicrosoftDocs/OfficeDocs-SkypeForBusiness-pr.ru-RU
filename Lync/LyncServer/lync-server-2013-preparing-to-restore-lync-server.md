---
title: 'Lync Server 2013: подготовка к восстановлению Lync Server'
description: 'Lync Server 2013: подготовка к восстановлению Lync Server.'
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
ms.openlocfilehash: 1875a691cfb70a6a824ab19bfde3dee4d699e48a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579955"
---
# <a name="preparing-to-restore-lync-server-2013"></a><span data-ttu-id="7aa15-103">Подготовка к восстановлению Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aa15-103">Preparing to restore Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aa15-104">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="7aa15-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="7aa15-105">Прежде чем приступать к восстановлению серверов и баз данных после сбоя, необходимо определить следующее:</span><span class="sxs-lookup"><span data-stu-id="7aa15-105">Before you begin restoring servers and databases after a failure, you need to determine the following:</span></span>

  - <span data-ttu-id="7aa15-106">Что необходимо восстановить.</span><span class="sxs-lookup"><span data-stu-id="7aa15-106">What needs to be restored.</span></span>

  - <span data-ttu-id="7aa15-107">Оборудование, программное обеспечение, данные и инструменты, необходимые для восстановления.</span><span class="sxs-lookup"><span data-stu-id="7aa15-107">The hardware, software, data, and tools you need for restoration.</span></span>

<div>

## <a name="determining-what-to-restore"></a><span data-ttu-id="7aa15-108">Определение объектов для восстановления</span><span class="sxs-lookup"><span data-stu-id="7aa15-108">Determining What to Restore</span></span>

<span data-ttu-id="7aa15-109">В этом разделе описывается, как восстановить простои Lync Server, происходящие на уровне сервера, пула или центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="7aa15-109">This topic describes how to restore Lync Server outages that occur at the server, pool, or Central Management store level.</span></span> <span data-ttu-id="7aa15-110">Если центральное хранилище управления завершается с ошибкой, развертывание Lync Server продолжает работать, но вы не можете вносить какие – либо изменения в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="7aa15-110">If the Central Management store fails, your Lync Server deployment continues to function, but you cannot make any configuration changes.</span></span> <span data-ttu-id="7aa15-111">В случае сбоя фонового сервера или сервера Standard Edition пул пользователей перестает работать.</span><span class="sxs-lookup"><span data-stu-id="7aa15-111">If a Back End Server or Standard Edition server fails, the user pool stops functioning.</span></span> <span data-ttu-id="7aa15-112">Если какой-либо другой сервер завершается с ошибкой, то величина сбоя зависит от роли сервера, на котором работает сервер, и от того, содержит ли сервер одну или несколько баз данных.</span><span class="sxs-lookup"><span data-stu-id="7aa15-112">If any other server fails, the magnitude of the failure depends on the server role the server is running and whether the server hosts one or more databases.</span></span>

### <a name="what-to-restore"></a><span data-ttu-id="7aa15-113">Восстановление</span><span class="sxs-lookup"><span data-stu-id="7aa15-113">What to Restore</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7aa15-114">Если это не удалось</span><span class="sxs-lookup"><span data-stu-id="7aa15-114">If this failed</span></span></th>
<th><span data-ttu-id="7aa15-115">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="7aa15-115">See this section:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aa15-116">Сервер Standard Edition</span><span class="sxs-lookup"><span data-stu-id="7aa15-116">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="7aa15-117"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Восстановление сервера Standard Edition в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aa15-117"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aa15-118">Центральное хранилище управления</span><span class="sxs-lookup"><span data-stu-id="7aa15-118">Central Management store</span></span></p></td>
<td><p><span data-ttu-id="7aa15-119"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Восстановление сервера, на котором размещается центральное хранилище управления, в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aa15-119"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restoring the server hosting the Central Management store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aa15-120">Серверная часть Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="7aa15-120">Enterprise Edition Back End</span></span></p></td>
<td><p><span data-ttu-id="7aa15-121"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Восстановление внутреннего сервера Enterprise Edition в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aa15-121"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aa15-122">Зеркальный сервер основного сервера Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="7aa15-122">Enterprise Edition Mirrored Back End Primary Server</span></span></p></td>
<td><p><span data-ttu-id="7aa15-123"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Восстановление зеркального сервера переднего план выпуска Enterprise Edition в Lync Server 2013 — основной</a></span><span class="sxs-lookup"><span data-stu-id="7aa15-123"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aa15-124">Дополнительный зеркальный сервер сервера Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="7aa15-124">Enterprise Edition Mirrored Back End Secondary Server</span></span></p></td>
<td><p><span data-ttu-id="7aa15-125"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Восстановление зеркального сервера переднего план выпуска Enterprise Edition в Lync Server 2013 — зеркало</a></span><span class="sxs-lookup"><span data-stu-id="7aa15-125"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aa15-126">Любой сервер Enterprise Edition, на котором работает роль сервера, например, сервер переднего плана, пограничный сервер, директор, сервер-посредник или сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="7aa15-126">Any Enterprise Edition server running a server role, such as a Front End Server, Edge Server, Director, Mediation Server,.or Persistent Chat Server.</span></span></p></td>
<td><p><span data-ttu-id="7aa15-127"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Восстановление рядового сервера Enterprise Edition в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aa15-127"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aa15-128">Весь пул Lync Server</span><span class="sxs-lookup"><span data-stu-id="7aa15-128">An entire Lync Server pool</span></span></p></td>
<td><p><span data-ttu-id="7aa15-129"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Восстановление пула Lync Server в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aa15-129"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restoring a Lync Server pool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aa15-130">Хранилище файлов Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="7aa15-130">Enterprise Edition File Store</span></span></p></td>
<td><p><span data-ttu-id="7aa15-131"><a href="lync-server-2013-restoring-a-file-store.md">Восстановление хранилища файлов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aa15-131"><a href="lync-server-2013-restoring-a-file-store.md">Restoring a file store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aa15-132">Автономная база данных мониторинга или база данных архивации</span><span class="sxs-lookup"><span data-stu-id="7aa15-132">A standalone Monitoring database or Archiving database</span></span></p></td>
<td><p><span data-ttu-id="7aa15-133"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Восстановление данных мониторинга или архивации в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aa15-133"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restoring monitoring or archiving data in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aa15-134">Автономная база данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="7aa15-134">A stand-alone Persistent Chat database</span></span></p></td>
<td><p><span data-ttu-id="7aa15-135"><a href="lync-server-2013-restoring-persistent-chat-data.md">Восстановление данных сохраняемого чата в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aa15-135"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restoring Persistent Chat data in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a><span data-ttu-id="7aa15-136">Сбор данных о оборудовании, программном обеспечении и средствах</span><span class="sxs-lookup"><span data-stu-id="7aa15-136">Gathering Hardware, Software, and Tools</span></span>

<span data-ttu-id="7aa15-137">При восстановлении сервера необходимо начать с нового или чистого компьютера.</span><span class="sxs-lookup"><span data-stu-id="7aa15-137">When you restore a server, you need to start with a new or clean computer.</span></span> <span data-ttu-id="7aa15-138">Кроме того, необходимо наличие следующего аппаратного и программного обеспечения:</span><span class="sxs-lookup"><span data-stu-id="7aa15-138">Additionally, you must have the following hardware and software available:</span></span>

  - <span data-ttu-id="7aa15-139">Чистый или новый сервер с таким же полным доменным именем (FQDN), что и сервер, на котором произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="7aa15-139">A clean or new server with the same fully qualified domain name (FQDN) as the server that failed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7aa15-140">При установке операционной системы убедитесь, что учетная запись компьютера не удалена в доменных службах Active Directory, и убедитесь, что разрешения группы для учетной записи сохранены.</span><span class="sxs-lookup"><span data-stu-id="7aa15-140">When you install the operating system, make sure that you do not delete the computer account in Active Directory Domain Services, and verify that the group permissions for the account are retained.</span></span>

    
    </div>

  - <span data-ttu-id="7aa15-141">Установка программного обеспечения для операционной системы.</span><span class="sxs-lookup"><span data-stu-id="7aa15-141">Installation software for the operating system.</span></span> <span data-ttu-id="7aa15-142">Чтобы установить операционную систему, воспользуйтесь процедурами и конфигурациями развертывания сервера, установленными в Организации.</span><span class="sxs-lookup"><span data-stu-id="7aa15-142">To install the operating system, use the server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="7aa15-143">При восстановлении службы должны быть доступны указанные ниже процедуры и требования к конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7aa15-143">You should have these procedures and configuration requirements available when you restore service.</span></span>

  - <span data-ttu-id="7aa15-144">Установка программного обеспечения для SQL Server 2012 или SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="7aa15-144">Installation software for SQL Server 2012 or SQL Server 2008 R2.</span></span> <span data-ttu-id="7aa15-145">Чтобы установить сервер баз данных, используйте соответствующую версию SQL Server, а также процедуры и конфигурации развертывания сервера базы данных, установленные вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="7aa15-145">To install a database server, use the appropriate version of SQL Server and the database server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="7aa15-146">При восстановлении службы должны быть доступны указанные ниже процедуры и требования к конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7aa15-146">You should have these procedures and configuration requirements available when you restore service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7aa15-147">Мастер развертывания Lync Server автоматически устанавливает SQL Server 2012 Express на каждом сервере Standard Edition и на любом другом сервере Lync Server при установке локального хранилища конфигурации, если вы не предустановили SQL Server 2012 или SQL Server 2008 R2 на сервере.</span><span class="sxs-lookup"><span data-stu-id="7aa15-147">The Lync Server Deployment Wizard automatically installs SQL Server 2012 Express on each Standard Edition server and on any other Lync Server server when a local configuration store is installed, unless you have preinstalled SQL Server 2012 or SQL Server 2008 R2 on the server.</span></span>

    
    </div>

  - <span data-ttu-id="7aa15-148">Программное обеспечение для принятия образов системы.</span><span class="sxs-lookup"><span data-stu-id="7aa15-148">Software for taking system images.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="7aa15-149">Мы рекомендуем использовать копию системы после установки операционной системы и SQL Server, а также до начала восстановления, чтобы использовать это изображение в качестве точки отката в случае, если что-то пойдет не так во время восстановления.</span><span class="sxs-lookup"><span data-stu-id="7aa15-149">We recommend that you take an image copy of the system after you install the operating system and SQL Server, and before you start restoration, so that you can use this image as a rollback point in case something goes wrong during restoration.</span></span>

    
    </div>

  - <span data-ttu-id="7aa15-150">Установка программного обеспечения Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7aa15-150">Lync Server 2013 installation software.</span></span> <span data-ttu-id="7aa15-151">Мастер развертывания Lync Server находится в папке установки Lync Server или на носителе во время \\ установки \\ amd64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="7aa15-151">The Lync Server Deployment Wizard is located in the Lync Server installation folder or media at \\setup\\amd64\\Setup.exe.</span></span>

<span data-ttu-id="7aa15-152">Во время восстановления используются следующие инструменты:</span><span class="sxs-lookup"><span data-stu-id="7aa15-152">During restoration, you use the following tools:</span></span>

  - <span data-ttu-id="7aa15-153">Командлеты командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="7aa15-153">Lync Server Management Shell cmdlets</span></span>

  - <span data-ttu-id="7aa15-154">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="7aa15-154">Import-CsUserData</span></span>

  - <span data-ttu-id="7aa15-155">Средства для восстановления папок Windows</span><span class="sxs-lookup"><span data-stu-id="7aa15-155">Tools for restoring Windows folders</span></span>

  - <span data-ttu-id="7aa15-156">Построитель топологий</span><span class="sxs-lookup"><span data-stu-id="7aa15-156">Topology Builder</span></span>

  - <span data-ttu-id="7aa15-157">Служебные программы для баз данных SQL Server, например SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7aa15-157">SQL Server database utilities, such as SQL Server Management Studio</span></span>

</div>

<div>

## <a name="preparing-to-restore-a-server"></a><span data-ttu-id="7aa15-158">Подготовка к восстановлению сервера</span><span class="sxs-lookup"><span data-stu-id="7aa15-158">Preparing to Restore a Server</span></span>

<span data-ttu-id="7aa15-159">Перед восстановлением сервера необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7aa15-159">Before you restore the server, you must perform the following steps:</span></span>

1.  <span data-ttu-id="7aa15-160">Установите операционную систему.</span><span class="sxs-lookup"><span data-stu-id="7aa15-160">Install the operating system.</span></span>

2.  <span data-ttu-id="7aa15-161">Если сервер является внутренним сервером, установите SQL Server 2012 или SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="7aa15-161">If the server is a Back End Server, install SQL Server 2012 or SQL Server 2008 R2.</span></span>

3.  <span data-ttu-id="7aa15-162">Восстановите или повторно зарегистрируйте сертификаты.</span><span class="sxs-lookup"><span data-stu-id="7aa15-162">Restore or reenroll your certificates.</span></span> <span data-ttu-id="7aa15-163">Сведения о сертификатах можно найти в статье "дополнительные требования к резервному копированию" в статье [требования к резервному копированию и восстановлению в Lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="7aa15-163">For details about certificates, see "Additional Backup Requirements" in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

4.  <span data-ttu-id="7aa15-164">Создайте образ системы перед началом восстановления, чтобы использовать его в качестве точки отката, если что-то пойдет не так во время восстановления.</span><span class="sxs-lookup"><span data-stu-id="7aa15-164">Take an image of the system before starting restoration to use as a rollback point, in case something goes wrong during restoration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7aa15-165">Мастер развертывания Lync Server и командлеты, описанные в процедурах, описанных в этой статье, и связанные темы задают все необходимые списки управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="7aa15-165">The Lync Server Deployment Wizard and cmdlets described in the procedures in this topic, and related topics, set all required access control lists (ACLs).</span></span>



</div>

<span data-ttu-id="7aa15-166">Прежде чем начать восстановление, убедитесь, что оборудование и программное обеспечение, необходимое для восстанавливаемых компонентов, доступны.</span><span class="sxs-lookup"><span data-stu-id="7aa15-166">Verify that the hardware and the software that you need for the components that you plan to restore are available before you start restoration.</span></span> <span data-ttu-id="7aa15-167">После установки операционной системы и сервера SQL Server большинство действий, описанных в следующих процедурах восстановления, могут быть запущены удаленно.</span><span class="sxs-lookup"><span data-stu-id="7aa15-167">After you install the operating system and SQL Server, most of the steps in the following restoration procedures can be run remotely.</span></span> <span data-ttu-id="7aa15-168">Исключения указаны в процедурах.</span><span class="sxs-lookup"><span data-stu-id="7aa15-168">The exceptions are noted in the procedures.</span></span>

<span data-ttu-id="7aa15-169">Кроме того, вы должны иметь план резервного копирования и восстановления вашей организации, а также сведения из последней резервной копии, такие как сведения на листах в этом документе (Дополнительные сведения см. в статье [резервное копирование и восстановление для Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), которые доступны до начала восстановления.</span><span class="sxs-lookup"><span data-stu-id="7aa15-169">You should also have your organization's backup and restoration plan and the information from your last backup, such as the information in the worksheets in this document (for details, see [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), available before you begin restoration.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

