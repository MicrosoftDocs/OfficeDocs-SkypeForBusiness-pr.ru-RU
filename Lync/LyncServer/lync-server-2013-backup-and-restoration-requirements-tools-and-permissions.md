---
title: 'Lync Server 2013: требования к резервному копированию и восстановлению: средства и разрешения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 900421ed081d5fb8e37fb6b23ddbb80dc85963eb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="f4e60-102">Требования к резервному копированию и восстановлению в Lync Server 2013: инструменты и разрешения</span><span class="sxs-lookup"><span data-stu-id="f4e60-102">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4e60-103">_**Последнее изменение темы:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="f4e60-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="f4e60-104">В этом разделе описываются средства, которые можно использовать для резервного копирования и восстановления Lync Server 2013, необходимые разрешения, а также возможность удаленного или локального запуска команд.</span><span class="sxs-lookup"><span data-stu-id="f4e60-104">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="f4e60-105">В частности, этот раздел посвящен средствам, предоставляемым Lync Server для резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="f4e60-105">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="f4e60-106">Резервные копии</span><span class="sxs-lookup"><span data-stu-id="f4e60-106">Backups</span></span>

<span data-ttu-id="f4e60-107">Для резервного копирования Lync Server используйте средства, указанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="f4e60-107">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="f4e60-108">Все команды, необходимые для резервного копирования Lync Server, можно создавать с помощью скриптов и могут быть запущены удаленно.</span><span class="sxs-lookup"><span data-stu-id="f4e60-108">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="f4e60-109">Средства резервного копирования Lync Server</span><span class="sxs-lookup"><span data-stu-id="f4e60-109">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4e60-110">Чтобы выполнить резервное копирование, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f4e60-110">To back up this:</span></span></th>
<th><span data-ttu-id="f4e60-111">Используйте это средство или командлет:</span><span class="sxs-lookup"><span data-stu-id="f4e60-111">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4e60-112">Данные конфигурации топологии (XDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="f4e60-112">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="f4e60-113">Export — CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="f4e60-113">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e60-114">Data Information Service (E9-1-1) Data (LIS. mdf)</span><span class="sxs-lookup"><span data-stu-id="f4e60-114">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="f4e60-115">Export — CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="f4e60-115">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e60-116">Данные конфигурации группы ответа (RgsConfig. mdf)</span><span class="sxs-lookup"><span data-stu-id="f4e60-116">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="f4e60-117">Export — CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="f4e60-117">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e60-118">Постоянные данные пользователя (база данных Rtcxds. mdf)</span><span class="sxs-lookup"><span data-stu-id="f4e60-118">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="f4e60-119">Идентификаторы конференций</span><span class="sxs-lookup"><span data-stu-id="f4e60-119">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="f4e60-120">Export — CsUserData</span><span class="sxs-lookup"><span data-stu-id="f4e60-120">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="f4e60-121">Архивная база данных (LcsLog. mdf)</span><span class="sxs-lookup"><span data-stu-id="f4e60-121">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="f4e60-122">Отслеживание базы данных записи сведений о вызовах (LcsCDR. mdf)</span><span class="sxs-lookup"><span data-stu-id="f4e60-122">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="f4e60-123">Мониторинг базы данных QoE (QoEMetrics. mdf)</span><span class="sxs-lookup"><span data-stu-id="f4e60-123">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f4e60-124">Средство для баз данных SQL Server, например SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f4e60-124">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e60-125">База данных сохраняемого чата (MGC. mdf)</span><span class="sxs-lookup"><span data-stu-id="f4e60-125">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="f4e60-126">Процедуры резервного копирования SQL Server или Export — CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="f4e60-126">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="f4e60-127">Export — CsPersistentChatData экспортирует данные сохраняемого чата в виде файла.</span><span class="sxs-lookup"><span data-stu-id="f4e60-127">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e60-128">Все хранилища файлов: хранилище файлов Lync Server, архивирование хранилища файлов</span><span class="sxs-lookup"><span data-stu-id="f4e60-128">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f4e60-129">Невозможно создать резервную копию файлов с именем <STRONG>Meeting. Active</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="f4e60-129">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="f4e60-130">Эти файлы используются и заблокированы во время собрания.</span><span class="sxs-lookup"><span data-stu-id="f4e60-130">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="f4e60-131">Стандартное средство управления файловой системой, например Robocopy.</span><span class="sxs-lookup"><span data-stu-id="f4e60-131">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="f4e60-132">Оно</span><span class="sxs-lookup"><span data-stu-id="f4e60-132">Restoration</span></span>

<span data-ttu-id="f4e60-133">Для восстановления Lync Server воспользуйтесь средствами, приведенными в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f4e60-133">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="f4e60-134">Все команды, необходимые для восстановления Lync Server, могут быть внесены в скрипт.</span><span class="sxs-lookup"><span data-stu-id="f4e60-134">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="f4e60-135">Некоторые из них можно запускать удаленно, но другие необходимо запускать локально, как указано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f4e60-135">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="f4e60-136">Средства для восстановления Lync Server</span><span class="sxs-lookup"><span data-stu-id="f4e60-136">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4e60-137">Для этого сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="f4e60-137">To do this:</span></span></th>
<th><span data-ttu-id="f4e60-138">Используйте это средство или командлет:</span><span class="sxs-lookup"><span data-stu-id="f4e60-138">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4e60-139">Создание нового или чистого компьютера</span><span class="sxs-lookup"><span data-stu-id="f4e60-139">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f4e60-140">Программное обеспечение для установки операционной системы Windows</span><span class="sxs-lookup"><span data-stu-id="f4e60-140">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="f4e60-141">Программное обеспечение для установки SQL Server</span><span class="sxs-lookup"><span data-stu-id="f4e60-141">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="f4e60-142">Оснастка "сертификаты" консоли управления (MMC), если вы восстанавливаете сертификаты с закрытым ключом</span><span class="sxs-lookup"><span data-stu-id="f4e60-142">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e60-143">Восстановление данных из хранилища файлов</span><span class="sxs-lookup"><span data-stu-id="f4e60-143">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="f4e60-144">Стандартное средство управления файловой системой, например Robocopy</span><span class="sxs-lookup"><span data-stu-id="f4e60-144">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e60-145">Повторно создайте пустые базы данных и установите разрешения для следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="f4e60-145">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f4e60-146">Центральное хранилище управления</span><span class="sxs-lookup"><span data-stu-id="f4e60-146">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="f4e60-147">Сервер переднего план</span><span class="sxs-lookup"><span data-stu-id="f4e60-147">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="f4e60-148">база данных мониторинга;</span><span class="sxs-lookup"><span data-stu-id="f4e60-148">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="f4e60-149">база данных архивации;</span><span class="sxs-lookup"><span data-stu-id="f4e60-149">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f4e60-150">Install — CsDatabase</span><span class="sxs-lookup"><span data-stu-id="f4e60-150">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e60-151">Восстановление указателя доменных служб Active Directory в центральном хранилище управления</span><span class="sxs-lookup"><span data-stu-id="f4e60-151">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f4e60-152">Если вы потеряете точку подключения службы в любое время, вы можете повторно запустить этот командлет.</span><span class="sxs-lookup"><span data-stu-id="f4e60-152">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="f4e60-153">Set — CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="f4e60-153">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e60-154">Импорт топологии, политик и параметров конфигурации в центральное хранилище управления (XDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="f4e60-154">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="f4e60-155">Import — CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="f4e60-155">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e60-156">Публикация и включение топологии</span><span class="sxs-lookup"><span data-stu-id="f4e60-156">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="f4e60-157">Построитель топологий</span><span class="sxs-lookup"><span data-stu-id="f4e60-157">Topology Builder</span></span></p>
<p><span data-ttu-id="f4e60-158">-или-</span><span class="sxs-lookup"><span data-stu-id="f4e60-158">-or-</span></span></p>
<p><span data-ttu-id="f4e60-159">Publish — CsTopology и Enable — CsTopology</span><span class="sxs-lookup"><span data-stu-id="f4e60-159">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e60-160">Включение последней опубликованной топологии</span><span class="sxs-lookup"><span data-stu-id="f4e60-160">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="f4e60-161">Enable — CsTopology</span><span class="sxs-lookup"><span data-stu-id="f4e60-161">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e60-162">Переустановка компонентов Lync Server</span><span class="sxs-lookup"><span data-stu-id="f4e60-162">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="f4e60-163">Установка Lync Server</span><span class="sxs-lookup"><span data-stu-id="f4e60-163">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f4e60-164">Размещается в папке установки Lync Server или на носителе по адресу \setup\amd64\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="f4e60-164">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e60-165">Восстановление сведений о расположении (E9-1-1) Data (LIS. mdf)</span><span class="sxs-lookup"><span data-stu-id="f4e60-165">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="f4e60-166">Import — CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="f4e60-166">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e60-167">Восстановление постоянных пользовательских данных (Rtcxds. mdf)</span><span class="sxs-lookup"><span data-stu-id="f4e60-167">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="f4e60-168">Import — CsUserData</span><span class="sxs-lookup"><span data-stu-id="f4e60-168">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e60-169">Восстановление данных конфигурации группы ответа (RgsConfig. mdf)</span><span class="sxs-lookup"><span data-stu-id="f4e60-169">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="f4e60-170">Import — CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="f4e60-170">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f4e60-171">Если конфигурация восстанавливается в новом развернутом пуле, в базе данных которого нет данных группы ответа, следует использовать параметр – Овервритеовнер.</span><span class="sxs-lookup"><span data-stu-id="f4e60-171">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="f4e60-172">Используйте этот параметр, даже если восстанавливаемые данные находятся в пуле с таким же полным доменным именем (FQDN).</span><span class="sxs-lookup"><span data-stu-id="f4e60-172">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="f4e60-173">В противном случае импорт завершится неудачно из-за объектов Contact в группы ответа, уже существующие в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f4e60-173">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e60-174">Восстановите следующие базы данных:</span><span class="sxs-lookup"><span data-stu-id="f4e60-174">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="f4e60-175">Архивная база данных (LcsLog. mdf)</span><span class="sxs-lookup"><span data-stu-id="f4e60-175">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="f4e60-176">Мониторинг баз данных: база данных записей сведений о вызовах (LcsCDR. mdf) и база данных QoE (QoEMetrics. mdf)</span><span class="sxs-lookup"><span data-stu-id="f4e60-176">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f4e60-177">Средства управления базами данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="f4e60-177">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e60-178">База данных сохраняемого чата (МГС. mdf)</span><span class="sxs-lookup"><span data-stu-id="f4e60-178">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="f4e60-179">Процедуры восстановления SQL Server или импорт — CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="f4e60-179">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="f4e60-180">Вы можете использовать import – CsPersistentChatData с файлом, созданным с помощью Export – CsPersistentChatData, и данные будут импортированы в базу данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="f4e60-180">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="f4e60-181">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="f4e60-181">Required Permissions</span></span>

<span data-ttu-id="f4e60-182">Для выполнения всех команд, описанных в этом разделе, пользователи должны быть членами группы **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="f4e60-182">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="f4e60-183">Большинство команд резервного копирования и восстановления не поддерживают управление доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="f4e60-183">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="f4e60-184">Два исключения — командлеты сохраняемого чата Export-CsPersistentChatData и Import-CsPersistentChatData, которые должны выполняться пользователем, который является членом группы CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f4e60-184">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="f4e60-185">Для запуска мастера развертывания Lync Server пользователь также должен быть членом локальной группы Администраторы.</span><span class="sxs-lookup"><span data-stu-id="f4e60-185">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

