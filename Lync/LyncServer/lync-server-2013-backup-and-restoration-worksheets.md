---
title: 'Lync Server 2013: журналы резервного копирования и восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ca10b848dfa1f6cf53724b364cf53b1fc0fad90
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="4800a-102">Журналы резервного копирования и восстановления для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4800a-102">Backup and restoration worksheets for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4800a-103">_**Тема последнего изменения:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="4800a-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="4800a-104">План резервного копирования и восстановления для Организации должен содержать сведения о том, как и когда вы захотите создать резервную копию данных и параметров.</span><span class="sxs-lookup"><span data-stu-id="4800a-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="4800a-105">Вы можете использовать представленные здесь листы, которые помогут вам документировать эти сведения о конкретном развертывании, а также о требованиях к резервному копированию и восстановлению в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4800a-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="4800a-106">С помощью следующих листов вы можете записать сведения, необходимые для резервного копирования и восстановления базы данных, хранилища файлов и параметров для пула Lync Server или стандартного сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4800a-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="4800a-107">Храните одну или несколько копий этих листов в безопасном месте, чтобы они были доступны, если вам нужно восстановить Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4800a-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4800a-108">На листах в этом разделе рассматриваются только те данные, которые необходимы для восстановления данных и параметров баз данных и серверов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4800a-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="4800a-109">Если вам нужно документировать другие данные для восстановления, например сведения для переустановки операционной системы и другого программного обеспечения, используйте планы развертывания и резервные копии и планы восстановления Организации, чтобы устранить эти требования.</span><span class="sxs-lookup"><span data-stu-id="4800a-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="4800a-110">Журнал резервного копирования и восстановления базы данных</span><span class="sxs-lookup"><span data-stu-id="4800a-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="4800a-111">Ниже приведена таблица, в которой записываются сведения, необходимые для резервного копирования и восстановления баз данных Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4800a-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="4800a-112">Сведения о базе данных для резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="4800a-112">Database Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="4800a-113">База</span><span class="sxs-lookup"><span data-stu-id="4800a-113">Database</span></span></th>
<th><span data-ttu-id="4800a-114">Имя сервера (FQDN)</span><span class="sxs-lookup"><span data-stu-id="4800a-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="4800a-115">Расписание резервного копирования</span><span class="sxs-lookup"><span data-stu-id="4800a-115">Backup schedule</span></span></th>
<th><span data-ttu-id="4800a-116">Средство резервного копирования базы данных</span><span class="sxs-lookup"><span data-stu-id="4800a-116">Database backup tool</span></span></th>
<th><span data-ttu-id="4800a-117">Резервный наборы данных</span><span class="sxs-lookup"><span data-stu-id="4800a-117">Backup set</span></span></th>
<th><span data-ttu-id="4800a-118">Место назначения резервной копии</span><span class="sxs-lookup"><span data-stu-id="4800a-118">Backup destination</span></span></th>
<th><span data-ttu-id="4800a-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="4800a-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4800a-120">База данных RTC на обратном стороне сервера для данных пользователя</span><span class="sxs-lookup"><span data-stu-id="4800a-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="4800a-121">Командлет <strong>Export-ксусердата</strong></span><span class="sxs-lookup"><span data-stu-id="4800a-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="4800a-122">Псевдоним</span><span class="sxs-lookup"><span data-stu-id="4800a-122">Name:</span></span></p>
<p><span data-ttu-id="4800a-123">Окончания срока действия</span><span class="sxs-lookup"><span data-stu-id="4800a-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4800a-124">База данных Лкслог (имя по умолчанию) на сервере архивации базы данных</span><span class="sxs-lookup"><span data-stu-id="4800a-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4800a-125">Средство управления SQL Server</span><span class="sxs-lookup"><span data-stu-id="4800a-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="4800a-126">Псевдоним</span><span class="sxs-lookup"><span data-stu-id="4800a-126">Name:</span></span></p>
<p><span data-ttu-id="4800a-127">Окончания срока действия</span><span class="sxs-lookup"><span data-stu-id="4800a-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4800a-128">База данных Лкскдр на сервере мониторинга для записей сведений о вызовах (Кдрс)</span><span class="sxs-lookup"><span data-stu-id="4800a-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4800a-129">Средство управления SQL Server</span><span class="sxs-lookup"><span data-stu-id="4800a-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="4800a-130">Псевдоним</span><span class="sxs-lookup"><span data-stu-id="4800a-130">Name:</span></span></p>
<p><span data-ttu-id="4800a-131">Окончания срока действия</span><span class="sxs-lookup"><span data-stu-id="4800a-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4800a-132">Коеметрикс Database на сервере базы данных для отслеживания качества взаимодействия (QoE)</span><span class="sxs-lookup"><span data-stu-id="4800a-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4800a-133">Средство управления SQL Server</span><span class="sxs-lookup"><span data-stu-id="4800a-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="4800a-134">Псевдоним</span><span class="sxs-lookup"><span data-stu-id="4800a-134">Name:</span></span></p>
<p><span data-ttu-id="4800a-135">Окончания срока действия</span><span class="sxs-lookup"><span data-stu-id="4800a-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4800a-136">База данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="4800a-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="4800a-137">Средство управления SQL Server или командлет <strong>Export-ксперсистентчатдата</strong></span><span class="sxs-lookup"><span data-stu-id="4800a-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="4800a-138">Псевдоним</span><span class="sxs-lookup"><span data-stu-id="4800a-138">Name:</span></span></p>
<p><span data-ttu-id="4800a-139">Окончания срока действия</span><span class="sxs-lookup"><span data-stu-id="4800a-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4800a-140">Для следующих баз данных резервное копирование и восстановление не требуется:</span><span class="sxs-lookup"><span data-stu-id="4800a-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="4800a-141">Рткдин.</span><span class="sxs-lookup"><span data-stu-id="4800a-141">Rtcdyn.</span></span> <span data-ttu-id="4800a-142">Временные данные пользователя в этой базе данных не требуются для восстановления служб.</span><span class="sxs-lookup"><span data-stu-id="4800a-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="4800a-143">Рткаб.</span><span class="sxs-lookup"><span data-stu-id="4800a-143">Rtcab.</span></span> <span data-ttu-id="4800a-144">База данных адресной книги автоматически воссоздается в глобальном списке адресов (GAL) доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4800a-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="4800a-145">Ргсдин.</span><span class="sxs-lookup"><span data-stu-id="4800a-145">Rgsdyn.</span></span> <span data-ttu-id="4800a-146">Промежуточные данные службы группы ответа в этой базе данных не требуются для восстановления служб.</span><span class="sxs-lookup"><span data-stu-id="4800a-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="4800a-147">Кпсдин.</span><span class="sxs-lookup"><span data-stu-id="4800a-147">Cpsdyn.</span></span> <span data-ttu-id="4800a-148">Динамическая информация для приложения парковки на приостановке не требуется для восстановления служб.</span><span class="sxs-lookup"><span data-stu-id="4800a-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="4800a-149">Мгккомп.</span><span class="sxs-lookup"><span data-stu-id="4800a-149">MgcComp.</span></span> <span data-ttu-id="4800a-150">База данных соответствия требованиям для сохраняемого чата не требуется для восстановления служб.</span><span class="sxs-lookup"><span data-stu-id="4800a-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="4800a-151">Журнал резервного копирования и восстановления хранилища файлов</span><span class="sxs-lookup"><span data-stu-id="4800a-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="4800a-152">Ниже приведена таблица, в которой записываются сведения, необходимые для резервного копирования и восстановления хранилища файлов.</span><span class="sxs-lookup"><span data-stu-id="4800a-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="4800a-153">В хранилищах файлов содержатся данные, такие как метаданные контента собраний, журналы соответствия собраний, журналы обновлений для устройств и звуковые файлы для групп ответа, приостановки звонков и объявлений.</span><span class="sxs-lookup"><span data-stu-id="4800a-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="4800a-154">Сведения о хранилище файлов для резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="4800a-154">File Store Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="4800a-155">Содержимое</span><span class="sxs-lookup"><span data-stu-id="4800a-155">Content</span></span></th>
<th><span data-ttu-id="4800a-156">Имя сервера (FQDN)</span><span class="sxs-lookup"><span data-stu-id="4800a-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="4800a-157">Расписание резервного копирования</span><span class="sxs-lookup"><span data-stu-id="4800a-157">Backup schedule</span></span></th>
<th><span data-ttu-id="4800a-158">Средство архивации файловой системы</span><span class="sxs-lookup"><span data-stu-id="4800a-158">File system backup tool</span></span></th>
<th><span data-ttu-id="4800a-159">Вы хотите создать резервную копию файла \*?</span><span class="sxs-lookup"><span data-stu-id="4800a-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="4800a-160">Место назначения резервной копии</span><span class="sxs-lookup"><span data-stu-id="4800a-160">Backup destination</span></span></th>
<th><span data-ttu-id="4800a-161">Примечания</span><span class="sxs-lookup"><span data-stu-id="4800a-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4800a-162">Хранилище файлов Lync Server</span><span class="sxs-lookup"><span data-stu-id="4800a-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="4800a-163">Стандартный инструмент резервного копирования, например Robocopy</span><span class="sxs-lookup"><span data-stu-id="4800a-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="4800a-164">На файловом сервере для Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="4800a-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="4800a-165">В стандартном выпуске по умолчанию для развертывания в стандартном выпуске.</span><span class="sxs-lookup"><span data-stu-id="4800a-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="4800a-166">Как правило, по одному на сайт.</span><span class="sxs-lookup"><span data-stu-id="4800a-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4800a-167">Файлы с именем <strong>Meeting. Active</strong> не следует архивировать.</span><span class="sxs-lookup"><span data-stu-id="4800a-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="4800a-168">Эти файлы используются и заблокированы во время собрания.</span><span class="sxs-lookup"><span data-stu-id="4800a-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="4800a-169">Журнал резервного копирования и восстановления параметров</span><span class="sxs-lookup"><span data-stu-id="4800a-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="4800a-170">Ниже приведена таблица, в которой записываются сведения, необходимые для резервного копирования и восстановления параметров.</span><span class="sxs-lookup"><span data-stu-id="4800a-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="4800a-171">Сведения о параметрах для резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="4800a-171">Settings Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="4800a-172">База</span><span class="sxs-lookup"><span data-stu-id="4800a-172">Database</span></span></th>
<th><span data-ttu-id="4800a-173">Имя сервера (FQDN)</span><span class="sxs-lookup"><span data-stu-id="4800a-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="4800a-174">Расписание резервного копирования</span><span class="sxs-lookup"><span data-stu-id="4800a-174">Backup schedule</span></span></th>
<th><span data-ttu-id="4800a-175">Средство резервного копирования</span><span class="sxs-lookup"><span data-stu-id="4800a-175">Backup tool</span></span></th>
<th><span data-ttu-id="4800a-176">Имя файла конфигурации (XML)</span><span class="sxs-lookup"><span data-stu-id="4800a-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="4800a-177">Расположение резервной копии</span><span class="sxs-lookup"><span data-stu-id="4800a-177">Backup location</span></span></th>
<th><span data-ttu-id="4800a-178">Примечания</span><span class="sxs-lookup"><span data-stu-id="4800a-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4800a-179">База данных XDS в хранилище для централизованного управления конфигурацией топологии (Global)</span><span class="sxs-lookup"><span data-stu-id="4800a-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="4800a-180">Командлет <strong>Export-ксконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="4800a-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4800a-181">База данных LIS в хранилище для централизованного управления E9 — 1 – 1 — сведения о расположении (Global)</span><span class="sxs-lookup"><span data-stu-id="4800a-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4800a-182">Командлет <strong>Export-кслисконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="4800a-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4800a-183">Конфигурация группы ответа Ргсконфиг базы данных сервера на обратном сервере.</span><span class="sxs-lookup"><span data-stu-id="4800a-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4800a-184">Командлет <strong>Export-ксргсконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="4800a-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
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

