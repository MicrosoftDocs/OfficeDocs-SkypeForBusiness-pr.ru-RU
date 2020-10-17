---
title: 'Lync Server 2013: листы резервного копирования и восстановления'
description: 'Lync Server 2013: таблицы резервного копирования и восстановления.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1713e291ae7132cc96309fa499bd97bf7f4f5016
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552325"
---
# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="4516d-103">Таблицы резервного копирования и восстановления для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4516d-103">Backup and restoration worksheets for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4516d-104">_**Последнее изменение темы:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="4516d-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="4516d-105">План резервного копирования и восстановления в Организации должен содержать сведения о том, как и когда выполняется резервное копирование данных и параметров.</span><span class="sxs-lookup"><span data-stu-id="4516d-105">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="4516d-106">Вы можете использовать приведенные здесь листы, чтобы задокументировать эти сведения для конкретных развертываний, а также требования к резервному копированию и восстановлению в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4516d-106">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="4516d-107">Используйте следующие листы для записи сведений, необходимых для резервного копирования и восстановления базы данных, хранилища файлов и сведений о параметрах для пула Lync Server или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4516d-107">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="4516d-108">Сохраните одну или несколько копий этих листов в безопасном расположении, чтобы они были доступны для восстановления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4516d-108">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4516d-109">На листах в этом разделе рассматриваются только те сведения, которые необходимы для восстановления данных и параметров баз данных и серверов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4516d-109">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="4516d-110">Если вам необходимо задокументировать другие сведения о восстановлении, например сведения для переустановки операционных систем и другого программного обеспечения, воспользуйтесь планами развертывания и резервным копированием Организации, чтобы устранить эти требования.</span><span class="sxs-lookup"><span data-stu-id="4516d-110">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="4516d-111">Таблица резервного копирования и восстановления базы данных</span><span class="sxs-lookup"><span data-stu-id="4516d-111">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="4516d-112">Используйте приведенную ниже таблицу для записи сведений, необходимых для резервного копирования и восстановления баз данных Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4516d-112">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="4516d-113">Сведения о базе данных для резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="4516d-113">Database Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4516d-114">Database</span><span class="sxs-lookup"><span data-stu-id="4516d-114">Database</span></span></th>
<th><span data-ttu-id="4516d-115">Имя сервера (полное доменное имя)</span><span class="sxs-lookup"><span data-stu-id="4516d-115">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="4516d-116">Расписание резервного копирования</span><span class="sxs-lookup"><span data-stu-id="4516d-116">Backup schedule</span></span></th>
<th><span data-ttu-id="4516d-117">Средство резервного копирования баз данных</span><span class="sxs-lookup"><span data-stu-id="4516d-117">Database backup tool</span></span></th>
<th><span data-ttu-id="4516d-118">Резервный набор данных</span><span class="sxs-lookup"><span data-stu-id="4516d-118">Backup set</span></span></th>
<th><span data-ttu-id="4516d-119">Назначение резервного копирования</span><span class="sxs-lookup"><span data-stu-id="4516d-119">Backup destination</span></span></th>
<th><span data-ttu-id="4516d-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="4516d-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4516d-121">База данных RTC на внутреннем сервере для данных пользователя</span><span class="sxs-lookup"><span data-stu-id="4516d-121">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="4516d-122">Командлет <strong>Export — CsUserData</strong></span><span class="sxs-lookup"><span data-stu-id="4516d-122"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="4516d-123">Расширением</span><span class="sxs-lookup"><span data-stu-id="4516d-123">Name:</span></span></p>
<p><span data-ttu-id="4516d-124">Срока действия</span><span class="sxs-lookup"><span data-stu-id="4516d-124">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4516d-125">База данных LcsLog (имя по умолчанию) на архивном сервере баз данных</span><span class="sxs-lookup"><span data-stu-id="4516d-125">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4516d-126">Средство управления SQL Server</span><span class="sxs-lookup"><span data-stu-id="4516d-126">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="4516d-127">Расширением</span><span class="sxs-lookup"><span data-stu-id="4516d-127">Name:</span></span></p>
<p><span data-ttu-id="4516d-128">Срока действия</span><span class="sxs-lookup"><span data-stu-id="4516d-128">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4516d-129">База данных LcsCdr на сервере мониторинга базы данных для записей сведений о вызовах (CDRs)</span><span class="sxs-lookup"><span data-stu-id="4516d-129">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4516d-130">Средство управления SQL Server</span><span class="sxs-lookup"><span data-stu-id="4516d-130">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="4516d-131">Расширением</span><span class="sxs-lookup"><span data-stu-id="4516d-131">Name:</span></span></p>
<p><span data-ttu-id="4516d-132">Срока действия</span><span class="sxs-lookup"><span data-stu-id="4516d-132">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4516d-133">База данных QoEMetrics на сервере мониторинга для данных качества взаимодействия (QoE)</span><span class="sxs-lookup"><span data-stu-id="4516d-133">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4516d-134">Средство управления SQL Server</span><span class="sxs-lookup"><span data-stu-id="4516d-134">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="4516d-135">Расширением</span><span class="sxs-lookup"><span data-stu-id="4516d-135">Name:</span></span></p>
<p><span data-ttu-id="4516d-136">Срока действия</span><span class="sxs-lookup"><span data-stu-id="4516d-136">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4516d-137">База данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="4516d-137">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="4516d-138">Средство управления SQL Server или командлет <strong>Export — CsPersistentChatData</strong></span><span class="sxs-lookup"><span data-stu-id="4516d-138">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="4516d-139">Расширением</span><span class="sxs-lookup"><span data-stu-id="4516d-139">Name:</span></span></p>
<p><span data-ttu-id="4516d-140">Срока действия</span><span class="sxs-lookup"><span data-stu-id="4516d-140">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4516d-141">Резервное копирование и восстановление для следующих баз данных не требуются:</span><span class="sxs-lookup"><span data-stu-id="4516d-141">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="4516d-142">Журнал RTCDyn.</span><span class="sxs-lookup"><span data-stu-id="4516d-142">Rtcdyn.</span></span> <span data-ttu-id="4516d-143">Временные данные пользователя в этой базе данных не являются обязательными для восстановления службы.</span><span class="sxs-lookup"><span data-stu-id="4516d-143">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="4516d-144">Rtcab.</span><span class="sxs-lookup"><span data-stu-id="4516d-144">Rtcab.</span></span> <span data-ttu-id="4516d-145">База данных адресной книги автоматически воссоздается в глобальном списке адресов (GAL) в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4516d-145">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="4516d-146">Ргсдин.</span><span class="sxs-lookup"><span data-stu-id="4516d-146">Rgsdyn.</span></span> <span data-ttu-id="4516d-147">Временные данные службы группы ответа в этой базе данных не являются обязательными для восстановления службы.</span><span class="sxs-lookup"><span data-stu-id="4516d-147">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="4516d-148">Кпсдин.</span><span class="sxs-lookup"><span data-stu-id="4516d-148">Cpsdyn.</span></span> <span data-ttu-id="4516d-149">Динамическая информация для приложения парковки вызовов не требуется для восстановления службы.</span><span class="sxs-lookup"><span data-stu-id="4516d-149">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="4516d-150">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="4516d-150">MgcComp.</span></span> <span data-ttu-id="4516d-151">База данных соответствия для сохраняемого чата не требуется для восстановления службы.</span><span class="sxs-lookup"><span data-stu-id="4516d-151">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="4516d-152">Таблица резервного копирования и восстановления хранилища файлов</span><span class="sxs-lookup"><span data-stu-id="4516d-152">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="4516d-153">Используйте приведенную ниже таблицу для записи сведений, необходимых для резервного копирования и восстановления хранилищ файлов.</span><span class="sxs-lookup"><span data-stu-id="4516d-153">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="4516d-154">Хранилища файлов содержат данные, такие как метаданные контента собраний, журналы соответствия требованиям к собранию, журналы обновлений для обновлений устройств и звуковые файлы для группы ответа, приостановки вызовов и приложений оповещений.</span><span class="sxs-lookup"><span data-stu-id="4516d-154">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="4516d-155">Сведения о хранении файлов для резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="4516d-155">File Store Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4516d-156">Контент</span><span class="sxs-lookup"><span data-stu-id="4516d-156">Content</span></span></th>
<th><span data-ttu-id="4516d-157">Имя сервера (полное доменное имя)</span><span class="sxs-lookup"><span data-stu-id="4516d-157">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="4516d-158">Расписание резервного копирования</span><span class="sxs-lookup"><span data-stu-id="4516d-158">Backup schedule</span></span></th>
<th><span data-ttu-id="4516d-159">Средство резервного копирования файловой системы</span><span class="sxs-lookup"><span data-stu-id="4516d-159">File system backup tool</span></span></th>
<th><span data-ttu-id="4516d-160">Резервное копирование общего файлового ресурса \*</span><span class="sxs-lookup"><span data-stu-id="4516d-160">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="4516d-161">Назначение резервного копирования</span><span class="sxs-lookup"><span data-stu-id="4516d-161">Backup destination</span></span></th>
<th><span data-ttu-id="4516d-162">Примечания</span><span class="sxs-lookup"><span data-stu-id="4516d-162">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4516d-163">Хранилище файлов Lync Server</span><span class="sxs-lookup"><span data-stu-id="4516d-163">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="4516d-164">Стандартный инструмент резервного копирования, например, Robocopy</span><span class="sxs-lookup"><span data-stu-id="4516d-164">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="4516d-165">На файловом сервере для Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="4516d-165">On file server for Enterprise Edition.</span></span> <span data-ttu-id="4516d-166">В стандартном выпуске по умолчанию для развертывания Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4516d-166">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="4516d-167">Как правило, по одному на сайт.</span><span class="sxs-lookup"><span data-stu-id="4516d-167">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4516d-168">Невозможно создать резервную копию файлов с именем <strong>Meeting. Active</strong> .</span><span class="sxs-lookup"><span data-stu-id="4516d-168">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="4516d-169">Эти файлы используются и заблокированы, пока выполняется собрание.</span><span class="sxs-lookup"><span data-stu-id="4516d-169">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="4516d-170">Таблица резервного копирования и восстановления параметров</span><span class="sxs-lookup"><span data-stu-id="4516d-170">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="4516d-171">Используйте приведенную ниже таблицу для записи сведений, необходимых для резервного копирования и восстановления параметров.</span><span class="sxs-lookup"><span data-stu-id="4516d-171">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="4516d-172">Сведения о параметрах для резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="4516d-172">Settings Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4516d-173">Database</span><span class="sxs-lookup"><span data-stu-id="4516d-173">Database</span></span></th>
<th><span data-ttu-id="4516d-174">Имя сервера (полное доменное имя)</span><span class="sxs-lookup"><span data-stu-id="4516d-174">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="4516d-175">Расписание резервного копирования</span><span class="sxs-lookup"><span data-stu-id="4516d-175">Backup schedule</span></span></th>
<th><span data-ttu-id="4516d-176">Средство резервного копирования</span><span class="sxs-lookup"><span data-stu-id="4516d-176">Backup tool</span></span></th>
<th><span data-ttu-id="4516d-177">Имя файла конфигурации (XML)</span><span class="sxs-lookup"><span data-stu-id="4516d-177">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="4516d-178">Расположение резервной копии</span><span class="sxs-lookup"><span data-stu-id="4516d-178">Backup location</span></span></th>
<th><span data-ttu-id="4516d-179">Примечания</span><span class="sxs-lookup"><span data-stu-id="4516d-179">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4516d-180">База данных XDS в центральном хранилище управления для конфигурации топологии (Глобальная)</span><span class="sxs-lookup"><span data-stu-id="4516d-180">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="4516d-181">Командлет <strong>Export — CsConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="4516d-181"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4516d-182">База данных LIS в центральном хранилище управления для сведений о расположении E9-1-1 (Глобальная)</span><span class="sxs-lookup"><span data-stu-id="4516d-182">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4516d-183">Командлет <strong>Export — CsLisConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="4516d-183"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4516d-184">База данных RgsConfig на внутреннем сервере для настройки группы ответа (пул)</span><span class="sxs-lookup"><span data-stu-id="4516d-184">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4516d-185">Командлет <strong>Export — CsRgsConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="4516d-185"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

