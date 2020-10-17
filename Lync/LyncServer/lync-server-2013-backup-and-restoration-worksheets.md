---
title: 'Lync Server 2013: листы резервного копирования и восстановления'
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
ms.openlocfilehash: 161a8577558705c773974b1cc733337b29b6dbd5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532626"
---
# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="8c933-102">Таблицы резервного копирования и восстановления для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c933-102">Backup and restoration worksheets for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c933-103">_**Последнее изменение темы:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="8c933-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="8c933-104">План резервного копирования и восстановления в Организации должен содержать сведения о том, как и когда выполняется резервное копирование данных и параметров.</span><span class="sxs-lookup"><span data-stu-id="8c933-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="8c933-105">Вы можете использовать приведенные здесь листы, чтобы задокументировать эти сведения для конкретных развертываний, а также требования к резервному копированию и восстановлению в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8c933-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="8c933-106">Используйте следующие листы для записи сведений, необходимых для резервного копирования и восстановления базы данных, хранилища файлов и сведений о параметрах для пула Lync Server или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8c933-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="8c933-107">Сохраните одну или несколько копий этих листов в безопасном расположении, чтобы они были доступны для восстановления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c933-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8c933-108">На листах в этом разделе рассматриваются только те сведения, которые необходимы для восстановления данных и параметров баз данных и серверов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c933-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="8c933-109">Если вам необходимо задокументировать другие сведения о восстановлении, например сведения для переустановки операционных систем и другого программного обеспечения, воспользуйтесь планами развертывания и резервным копированием Организации, чтобы устранить эти требования.</span><span class="sxs-lookup"><span data-stu-id="8c933-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="8c933-110">Таблица резервного копирования и восстановления базы данных</span><span class="sxs-lookup"><span data-stu-id="8c933-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="8c933-111">Используйте приведенную ниже таблицу для записи сведений, необходимых для резервного копирования и восстановления баз данных Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c933-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="8c933-112">Сведения о базе данных для резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="8c933-112">Database Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="8c933-113">Database</span><span class="sxs-lookup"><span data-stu-id="8c933-113">Database</span></span></th>
<th><span data-ttu-id="8c933-114">Имя сервера (полное доменное имя)</span><span class="sxs-lookup"><span data-stu-id="8c933-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="8c933-115">Расписание резервного копирования</span><span class="sxs-lookup"><span data-stu-id="8c933-115">Backup schedule</span></span></th>
<th><span data-ttu-id="8c933-116">Средство резервного копирования баз данных</span><span class="sxs-lookup"><span data-stu-id="8c933-116">Database backup tool</span></span></th>
<th><span data-ttu-id="8c933-117">Резервный набор данных</span><span class="sxs-lookup"><span data-stu-id="8c933-117">Backup set</span></span></th>
<th><span data-ttu-id="8c933-118">Назначение резервного копирования</span><span class="sxs-lookup"><span data-stu-id="8c933-118">Backup destination</span></span></th>
<th><span data-ttu-id="8c933-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c933-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c933-120">База данных RTC на внутреннем сервере для данных пользователя</span><span class="sxs-lookup"><span data-stu-id="8c933-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="8c933-121">Командлет <strong>Export — CsUserData</strong></span><span class="sxs-lookup"><span data-stu-id="8c933-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="8c933-122">Расширением</span><span class="sxs-lookup"><span data-stu-id="8c933-122">Name:</span></span></p>
<p><span data-ttu-id="8c933-123">Срока действия</span><span class="sxs-lookup"><span data-stu-id="8c933-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c933-124">База данных LcsLog (имя по умолчанию) на архивном сервере баз данных</span><span class="sxs-lookup"><span data-stu-id="8c933-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8c933-125">Средство управления SQL Server</span><span class="sxs-lookup"><span data-stu-id="8c933-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="8c933-126">Расширением</span><span class="sxs-lookup"><span data-stu-id="8c933-126">Name:</span></span></p>
<p><span data-ttu-id="8c933-127">Срока действия</span><span class="sxs-lookup"><span data-stu-id="8c933-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c933-128">База данных LcsCdr на сервере мониторинга базы данных для записей сведений о вызовах (CDRs)</span><span class="sxs-lookup"><span data-stu-id="8c933-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8c933-129">Средство управления SQL Server</span><span class="sxs-lookup"><span data-stu-id="8c933-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="8c933-130">Расширением</span><span class="sxs-lookup"><span data-stu-id="8c933-130">Name:</span></span></p>
<p><span data-ttu-id="8c933-131">Срока действия</span><span class="sxs-lookup"><span data-stu-id="8c933-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c933-132">База данных QoEMetrics на сервере мониторинга для данных качества взаимодействия (QoE)</span><span class="sxs-lookup"><span data-stu-id="8c933-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8c933-133">Средство управления SQL Server</span><span class="sxs-lookup"><span data-stu-id="8c933-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="8c933-134">Расширением</span><span class="sxs-lookup"><span data-stu-id="8c933-134">Name:</span></span></p>
<p><span data-ttu-id="8c933-135">Срока действия</span><span class="sxs-lookup"><span data-stu-id="8c933-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c933-136">База данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="8c933-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="8c933-137">Средство управления SQL Server или командлет <strong>Export — CsPersistentChatData</strong></span><span class="sxs-lookup"><span data-stu-id="8c933-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="8c933-138">Расширением</span><span class="sxs-lookup"><span data-stu-id="8c933-138">Name:</span></span></p>
<p><span data-ttu-id="8c933-139">Срока действия</span><span class="sxs-lookup"><span data-stu-id="8c933-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8c933-140">Резервное копирование и восстановление для следующих баз данных не требуются:</span><span class="sxs-lookup"><span data-stu-id="8c933-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="8c933-141">Журнал RTCDyn.</span><span class="sxs-lookup"><span data-stu-id="8c933-141">Rtcdyn.</span></span> <span data-ttu-id="8c933-142">Временные данные пользователя в этой базе данных не являются обязательными для восстановления службы.</span><span class="sxs-lookup"><span data-stu-id="8c933-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="8c933-143">Rtcab.</span><span class="sxs-lookup"><span data-stu-id="8c933-143">Rtcab.</span></span> <span data-ttu-id="8c933-144">База данных адресной книги автоматически воссоздается в глобальном списке адресов (GAL) в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8c933-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="8c933-145">Ргсдин.</span><span class="sxs-lookup"><span data-stu-id="8c933-145">Rgsdyn.</span></span> <span data-ttu-id="8c933-146">Временные данные службы группы ответа в этой базе данных не являются обязательными для восстановления службы.</span><span class="sxs-lookup"><span data-stu-id="8c933-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="8c933-147">Кпсдин.</span><span class="sxs-lookup"><span data-stu-id="8c933-147">Cpsdyn.</span></span> <span data-ttu-id="8c933-148">Динамическая информация для приложения парковки вызовов не требуется для восстановления службы.</span><span class="sxs-lookup"><span data-stu-id="8c933-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="8c933-149">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="8c933-149">MgcComp.</span></span> <span data-ttu-id="8c933-150">База данных соответствия для сохраняемого чата не требуется для восстановления службы.</span><span class="sxs-lookup"><span data-stu-id="8c933-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="8c933-151">Таблица резервного копирования и восстановления хранилища файлов</span><span class="sxs-lookup"><span data-stu-id="8c933-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="8c933-152">Используйте приведенную ниже таблицу для записи сведений, необходимых для резервного копирования и восстановления хранилищ файлов.</span><span class="sxs-lookup"><span data-stu-id="8c933-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="8c933-153">Хранилища файлов содержат данные, такие как метаданные контента собраний, журналы соответствия требованиям к собранию, журналы обновлений для обновлений устройств и звуковые файлы для группы ответа, приостановки вызовов и приложений оповещений.</span><span class="sxs-lookup"><span data-stu-id="8c933-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="8c933-154">Сведения о хранении файлов для резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="8c933-154">File Store Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="8c933-155">Контент</span><span class="sxs-lookup"><span data-stu-id="8c933-155">Content</span></span></th>
<th><span data-ttu-id="8c933-156">Имя сервера (полное доменное имя)</span><span class="sxs-lookup"><span data-stu-id="8c933-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="8c933-157">Расписание резервного копирования</span><span class="sxs-lookup"><span data-stu-id="8c933-157">Backup schedule</span></span></th>
<th><span data-ttu-id="8c933-158">Средство резервного копирования файловой системы</span><span class="sxs-lookup"><span data-stu-id="8c933-158">File system backup tool</span></span></th>
<th><span data-ttu-id="8c933-159">Резервное копирование общего файлового ресурса \*</span><span class="sxs-lookup"><span data-stu-id="8c933-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="8c933-160">Назначение резервного копирования</span><span class="sxs-lookup"><span data-stu-id="8c933-160">Backup destination</span></span></th>
<th><span data-ttu-id="8c933-161">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c933-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c933-162">Хранилище файлов Lync Server</span><span class="sxs-lookup"><span data-stu-id="8c933-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="8c933-163">Стандартный инструмент резервного копирования, например, Robocopy</span><span class="sxs-lookup"><span data-stu-id="8c933-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="8c933-164">На файловом сервере для Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="8c933-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="8c933-165">В стандартном выпуске по умолчанию для развертывания Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8c933-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="8c933-166">Как правило, по одному на сайт.</span><span class="sxs-lookup"><span data-stu-id="8c933-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8c933-167">Невозможно создать резервную копию файлов с именем <strong>Meeting. Active</strong> .</span><span class="sxs-lookup"><span data-stu-id="8c933-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="8c933-168">Эти файлы используются и заблокированы, пока выполняется собрание.</span><span class="sxs-lookup"><span data-stu-id="8c933-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="8c933-169">Таблица резервного копирования и восстановления параметров</span><span class="sxs-lookup"><span data-stu-id="8c933-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="8c933-170">Используйте приведенную ниже таблицу для записи сведений, необходимых для резервного копирования и восстановления параметров.</span><span class="sxs-lookup"><span data-stu-id="8c933-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="8c933-171">Сведения о параметрах для резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="8c933-171">Settings Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="8c933-172">Database</span><span class="sxs-lookup"><span data-stu-id="8c933-172">Database</span></span></th>
<th><span data-ttu-id="8c933-173">Имя сервера (полное доменное имя)</span><span class="sxs-lookup"><span data-stu-id="8c933-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="8c933-174">Расписание резервного копирования</span><span class="sxs-lookup"><span data-stu-id="8c933-174">Backup schedule</span></span></th>
<th><span data-ttu-id="8c933-175">Средство резервного копирования</span><span class="sxs-lookup"><span data-stu-id="8c933-175">Backup tool</span></span></th>
<th><span data-ttu-id="8c933-176">Имя файла конфигурации (XML)</span><span class="sxs-lookup"><span data-stu-id="8c933-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="8c933-177">Расположение резервной копии</span><span class="sxs-lookup"><span data-stu-id="8c933-177">Backup location</span></span></th>
<th><span data-ttu-id="8c933-178">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c933-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c933-179">База данных XDS в центральном хранилище управления для конфигурации топологии (Глобальная)</span><span class="sxs-lookup"><span data-stu-id="8c933-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="8c933-180">Командлет <strong>Export — CsConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="8c933-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c933-181">База данных LIS в центральном хранилище управления для сведений о расположении E9-1-1 (Глобальная)</span><span class="sxs-lookup"><span data-stu-id="8c933-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8c933-182">Командлет <strong>Export — CsLisConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="8c933-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c933-183">База данных RgsConfig на внутреннем сервере для настройки группы ответа (пул)</span><span class="sxs-lookup"><span data-stu-id="8c933-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8c933-184">Командлет <strong>Export — CsRgsConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="8c933-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
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

