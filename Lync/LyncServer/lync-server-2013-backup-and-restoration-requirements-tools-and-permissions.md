---
title: 'Lync Server 2013: требования к резервному копированию и восстановлению: инструменты и разрешения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53128d99abfd438c174b98544889781b5f29b57b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="943b4-102">Требования к резервному копированию и восстановлению в Lync Server 2013: инструменты и разрешения</span><span class="sxs-lookup"><span data-stu-id="943b4-102">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="943b4-103">_**Тема последнего изменения:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="943b4-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="943b4-104">В этой статье описаны средства, с помощью которых можно создавать резервные копии и восстанавливать Lync Server 2013, нужные разрешения, а также можно ли выполнять команды удаленно или локально.</span><span class="sxs-lookup"><span data-stu-id="943b4-104">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="943b4-105">В частности, этот раздел посвящен средствам, которые предоставляются в Lync Server для резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="943b4-105">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="943b4-106">Архиваци</span><span class="sxs-lookup"><span data-stu-id="943b4-106">Backups</span></span>

<span data-ttu-id="943b4-107">Для резервного копирования сервера Lync Server используйте инструменты, описанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="943b4-107">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="943b4-108">Все команды, необходимые для создания резервной копии сервера Lync Server, могут быть внесены в сценарий и могут быть запущены удаленно.</span><span class="sxs-lookup"><span data-stu-id="943b4-108">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="943b4-109">Инструменты для резервного копирования сервера Lync Server</span><span class="sxs-lookup"><span data-stu-id="943b4-109">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="943b4-110">Чтобы создать резервную копию, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="943b4-110">To back up this:</span></span></th>
<th><span data-ttu-id="943b4-111">Используйте это средство или командлет:</span><span class="sxs-lookup"><span data-stu-id="943b4-111">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="943b4-112">Данные конфигурации топологии (XDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="943b4-112">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="943b4-113">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="943b4-113">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="943b4-114">Служба сведений о расположении (E9-1-1) Data (LIS. mdf)</span><span class="sxs-lookup"><span data-stu-id="943b4-114">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="943b4-115">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="943b4-115">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="943b4-116">Данные конфигурации группы ответа (Ргсконфиг. mdf)</span><span class="sxs-lookup"><span data-stu-id="943b4-116">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="943b4-117">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="943b4-117">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="943b4-118">Постоянные данные пользователя (Рткксдс. mdf)</span><span class="sxs-lookup"><span data-stu-id="943b4-118">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="943b4-119">Идентификаторы конференций</span><span class="sxs-lookup"><span data-stu-id="943b4-119">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="943b4-120">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="943b4-120">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="943b4-121">Архивирование базы данных (Лкслог. mdf)</span><span class="sxs-lookup"><span data-stu-id="943b4-121">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="943b4-122">Наблюдение за базой данных записи сведений о вызовах (Лкскдр. mdf)</span><span class="sxs-lookup"><span data-stu-id="943b4-122">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="943b4-123">Мониторинг QoE базы данных (Коеметрикс. mdf)</span><span class="sxs-lookup"><span data-stu-id="943b4-123">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="943b4-124">Средство для создания баз данных SQL Server, например SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="943b4-124">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="943b4-125">База данных сохраняемого чата (MGC. mdf)</span><span class="sxs-lookup"><span data-stu-id="943b4-125">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="943b4-126">Процедуры резервного копирования SQL Server или Export-Ксперсистентчатдата.</span><span class="sxs-lookup"><span data-stu-id="943b4-126">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="943b4-127">Export-Ксперсистентчатдата экспортирует сохраняемые данные чата в виде файла.</span><span class="sxs-lookup"><span data-stu-id="943b4-127">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="943b4-128">Все хранилища файлов: хранилище файлов Lync Server, архивное хранилище файлов</span><span class="sxs-lookup"><span data-stu-id="943b4-128">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="943b4-129">Файлы с именем <STRONG>Meeting. Active</STRONG> не следует архивировать.</span><span class="sxs-lookup"><span data-stu-id="943b4-129">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="943b4-130">Эти файлы используются и заблокированы во время собрания.</span><span class="sxs-lookup"><span data-stu-id="943b4-130">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="943b4-131">Стандартная программа управления файловой системой, например Robocopy.</span><span class="sxs-lookup"><span data-stu-id="943b4-131">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="943b4-132">Восстановление</span><span class="sxs-lookup"><span data-stu-id="943b4-132">Restoration</span></span>

<span data-ttu-id="943b4-133">Чтобы восстановить Lync Server, воспользуйтесь инструментами, приведенными в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="943b4-133">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="943b4-134">Все команды, необходимые для восстановления сервера Lync Server, могут быть внесены в сценарий.</span><span class="sxs-lookup"><span data-stu-id="943b4-134">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="943b4-135">Некоторые из них можно запускать удаленно, но другие должны выполняться локально, как указано в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="943b4-135">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="943b4-136">Инструменты для восстановления сервера Lync Server</span><span class="sxs-lookup"><span data-stu-id="943b4-136">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="943b4-137">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="943b4-137">To do this:</span></span></th>
<th><span data-ttu-id="943b4-138">Используйте это средство или командлет:</span><span class="sxs-lookup"><span data-stu-id="943b4-138">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="943b4-139">Создание нового или очистка компьютера</span><span class="sxs-lookup"><span data-stu-id="943b4-139">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="943b4-140">Программное обеспечение для установки операционной системы Windows</span><span class="sxs-lookup"><span data-stu-id="943b4-140">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="943b4-141">Программное обеспечение SQL Server для установки</span><span class="sxs-lookup"><span data-stu-id="943b4-141">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="943b4-142">Оснастка консоли управления Microsoft Management Console (MMC), если вы восстанавливаете сертификаты с помощью экспортируемого закрытого ключа</span><span class="sxs-lookup"><span data-stu-id="943b4-142">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="943b4-143">Восстановление данных из хранилища файлов</span><span class="sxs-lookup"><span data-stu-id="943b4-143">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="943b4-144">Стандартная программа управления файловой системой, например Robocopy</span><span class="sxs-lookup"><span data-stu-id="943b4-144">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="943b4-145">Повторно создайте пустые базы данных и настройте разрешения для указанных ниже параметров.</span><span class="sxs-lookup"><span data-stu-id="943b4-145">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="943b4-146">управления</span><span class="sxs-lookup"><span data-stu-id="943b4-146">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="943b4-147">внутренний сервер</span><span class="sxs-lookup"><span data-stu-id="943b4-147">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="943b4-148">данных мониторинга</span><span class="sxs-lookup"><span data-stu-id="943b4-148">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="943b4-149">данных архивации</span><span class="sxs-lookup"><span data-stu-id="943b4-149">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="943b4-150">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="943b4-150">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="943b4-151">Восстановление указателя доменных служб Active Directory в хранилище Центрального управления</span><span class="sxs-lookup"><span data-stu-id="943b4-151">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="943b4-152">Если вы в любой момент потеряли точку соединения службы, вы можете повторно запустить этот командлет.</span><span class="sxs-lookup"><span data-stu-id="943b4-152">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="943b4-153">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="943b4-153">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="943b4-154">Импорт топологии, политик и параметров конфигурации в хранилище Центрального управления (XDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="943b4-154">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="943b4-155">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="943b4-155">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="943b4-156">Публикация и включение топологии</span><span class="sxs-lookup"><span data-stu-id="943b4-156">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="943b4-157">топологий</span><span class="sxs-lookup"><span data-stu-id="943b4-157">Topology Builder</span></span></p>
<p><span data-ttu-id="943b4-158">/</span><span class="sxs-lookup"><span data-stu-id="943b4-158">-or-</span></span></p>
<p><span data-ttu-id="943b4-159">Publishing-Кстопологи и Enable-Кстопологи</span><span class="sxs-lookup"><span data-stu-id="943b4-159">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="943b4-160">Включение последней опубликованной топологии</span><span class="sxs-lookup"><span data-stu-id="943b4-160">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="943b4-161">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="943b4-161">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="943b4-162">Переустановка серверных компонентов Lync</span><span class="sxs-lookup"><span data-stu-id="943b4-162">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="943b4-163">Настройка сервера Lync Server</span><span class="sxs-lookup"><span data-stu-id="943b4-163">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="943b4-164">Находится в папке установки Lync Server или мультимедиа на \setup\amd64\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="943b4-164">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="943b4-165">Восстановление сведений о расположении (E9-1-1) Data (LIS. mdf)</span><span class="sxs-lookup"><span data-stu-id="943b4-165">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="943b4-166">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="943b4-166">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="943b4-167">Восстановление постоянных данных пользователя (Рткксдс. mdf)</span><span class="sxs-lookup"><span data-stu-id="943b4-167">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="943b4-168">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="943b4-168">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="943b4-169">Восстановление данных конфигурации группы ответа (Ргсконфиг. mdf)</span><span class="sxs-lookup"><span data-stu-id="943b4-169">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="943b4-170">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="943b4-170">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="943b4-171">Если конфигурация восстанавливается в только что развернутом пуле, в базе данных которого нет данных о группе ответа, следует использовать параметр – Овервритеовнер.</span><span class="sxs-lookup"><span data-stu-id="943b4-171">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="943b4-172">Используйте этот параметр, даже если восстанавливаемые данные находятся в пуле с таким же полным доменным именем (FQDN).</span><span class="sxs-lookup"><span data-stu-id="943b4-172">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="943b4-173">В противном случае импорт завершится сбоем из-за объектов контакта с группами ответа, уже существующими в службе каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="943b4-173">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="943b4-174">Восстановите следующие базы данных:</span><span class="sxs-lookup"><span data-stu-id="943b4-174">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="943b4-175">Архивирование базы данных (Лкслог. mdf)</span><span class="sxs-lookup"><span data-stu-id="943b4-175">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="943b4-176">Наблюдение за базами данных: база данных записей с данными о вызовах (Лкскдр. mdf) и QoE Database (Коеметрикс. mdf)</span><span class="sxs-lookup"><span data-stu-id="943b4-176">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="943b4-177">Средства управления базами данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="943b4-177">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="943b4-178">База данных сохраняемого чата (МГС. mdf)</span><span class="sxs-lookup"><span data-stu-id="943b4-178">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="943b4-179">Процедуры восстановления SQL Server или импорт-Ксперсистентчатдата.</span><span class="sxs-lookup"><span data-stu-id="943b4-179">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="943b4-180">Вы можете использовать import-Ксперсистентчатдата с файлом, созданным функцией экспорт-Ксперсистентчатдата, и данные будут импортированы в сохраненную базу данных чата.</span><span class="sxs-lookup"><span data-stu-id="943b4-180">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="943b4-181">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="943b4-181">Required Permissions</span></span>

<span data-ttu-id="943b4-182">Для выполнения всех команд, описанных в этом разделе, пользователи должны быть членами группы **рткуниверсалсерверадминс** .</span><span class="sxs-lookup"><span data-stu-id="943b4-182">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="943b4-183">Большинство команд резервного копирования и восстановления не поддерживают управление доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="943b4-183">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="943b4-184">Два исключения — это хранимые командлеты Export-Ксперсистентчатдата и Import-Ксперсистентчатдата, которые должны выполняться пользователем, который является членом группы "Ксперсистентчатадминистратор".</span><span class="sxs-lookup"><span data-stu-id="943b4-184">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="943b4-185">Чтобы запустить мастер развертывания Lync Server, пользователь также должен быть членом локальной группы Админстраторс.</span><span class="sxs-lookup"><span data-stu-id="943b4-185">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

