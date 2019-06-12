---
title: 'Lync Server 2013: размещение данных и файла журнала SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a528ba7a348ebb5c8f865a795f8b1f1c1bc30cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="64f88-102">Размещение данных и файла журнала SQL Server для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64f88-102">SQL Server data and log file placement for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64f88-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="64f88-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="64f88-104">При планировании и развертывании Microsoft SQL Server 2012 или Microsoft SQL Server 2008 R2 SP1 для пула Lync Server 2013, важно помнить, что при работе с данными и файлами журнала на физических жестких дисках будет размещаться файл данных и журнал.</span><span class="sxs-lookup"><span data-stu-id="64f88-104">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="64f88-105">Рекомендуемая конфигурация диска — это реализация 1 + 0 RAID-массива с использованием шести дисков.</span><span class="sxs-lookup"><span data-stu-id="64f88-105">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="64f88-106">Размещение всех файлов базы данных и журналов, которые используются интерфейсным пулом и связанными ролями и службами сервера (то есть сервера архивирования и мониторинга, службы группы ответов Lync Server, службы «Служба поддержки пользователей» Lync Server) на диск RAID, установленный с помощью Lync Server Мастер развертывания приведет к тому, что конфигурация была протестирована на предмет оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="64f88-106">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="64f88-107">Файлы базы данных и их ответственные описаны в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="64f88-107">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="64f88-108">Если ваши политики и конфигурации SQL Server требуют более специализированной установки, файлы базы данных и журнала можно установить в любое предопределенное расположение с помощью командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="64f88-108">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="64f88-109">Дополнительные сведения о том, как <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">установить базу данных с помощью командной консоли Lync Server Management Shell, вы увидите в Lync server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="64f88-109">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="64f88-110">Файлы данных и журналов для централизованного управления хранилищем</span><span class="sxs-lookup"><span data-stu-id="64f88-110">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64f88-111">Файлы баз данных централизованного управления хранилищем</span><span class="sxs-lookup"><span data-stu-id="64f88-111">Central Management store database files</span></span></th>
<th><span data-ttu-id="64f88-112">Файл данных или назначение журнала</span><span class="sxs-lookup"><span data-stu-id="64f88-112">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64f88-113">XDS. ldf</span><span class="sxs-lookup"><span data-stu-id="64f88-113">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="64f88-114">Файл журнала транзакций для хранилища центрального управления</span><span class="sxs-lookup"><span data-stu-id="64f88-114">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f88-115">XDS. mdf</span><span class="sxs-lookup"><span data-stu-id="64f88-115">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="64f88-116">Сохраняет конфигурацию текущей топологии Lync Server 2013, определенную и опубликованную с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="64f88-116">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f88-117">LIS. mdf</span><span class="sxs-lookup"><span data-stu-id="64f88-117">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="64f88-118">Файл данных службы сведений о расположении</span><span class="sxs-lookup"><span data-stu-id="64f88-118">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f88-119">LIS. ldf</span><span class="sxs-lookup"><span data-stu-id="64f88-119">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="64f88-120">Журнал транзакций для файла данных службы сведений о расположении</span><span class="sxs-lookup"><span data-stu-id="64f88-120">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="64f88-121">Файлы данных и журналов для пользователей, конференций и адресной книги</span><span class="sxs-lookup"><span data-stu-id="64f88-121">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64f88-122">Файлы базы данных основного Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64f88-122">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="64f88-123">Файл данных или назначение журнала</span><span class="sxs-lookup"><span data-stu-id="64f88-123">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64f88-124">RTC. mdf</span><span class="sxs-lookup"><span data-stu-id="64f88-124">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="64f88-125">Постоянные данные пользователя (например, списки управления доступом (ACL), контакты, запланированные конференции)</span><span class="sxs-lookup"><span data-stu-id="64f88-125">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f88-126">RTC. ldf</span><span class="sxs-lookup"><span data-stu-id="64f88-126">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="64f88-127">Журнал транзакций для данных RTC</span><span class="sxs-lookup"><span data-stu-id="64f88-127">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f88-128">Рткдин. mdf</span><span class="sxs-lookup"><span data-stu-id="64f88-128">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="64f88-129">Поддерживает временные пользовательские данные (данные среды выполнения присутствия)</span><span class="sxs-lookup"><span data-stu-id="64f88-129">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f88-130">Рткдин. ldf</span><span class="sxs-lookup"><span data-stu-id="64f88-130">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="64f88-131">Журнал транзакций для данных Рткдин</span><span class="sxs-lookup"><span data-stu-id="64f88-131">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f88-132">Рткаб. mdf</span><span class="sxs-lookup"><span data-stu-id="64f88-132">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="64f88-133">База данных адресной книги в реальном времени (RTC) — это репозиторий SQL Server, в котором хранятся сведения о службе адресной книги</span><span class="sxs-lookup"><span data-stu-id="64f88-133">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f88-134">Рткаб. ldf</span><span class="sxs-lookup"><span data-stu-id="64f88-134">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="64f88-135">Журнал транзакций для службы «адресная книга»</span><span class="sxs-lookup"><span data-stu-id="64f88-135">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f88-136">Ртклокал. mdb</span><span class="sxs-lookup"><span data-stu-id="64f88-136">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="64f88-137">Размещение каталога конференций</span><span class="sxs-lookup"><span data-stu-id="64f88-137">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f88-138">Рткксдс. mdf</span><span class="sxs-lookup"><span data-stu-id="64f88-138">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="64f88-139">Сохранение резервной копии данных пользователя</span><span class="sxs-lookup"><span data-stu-id="64f88-139">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f88-140">Рткксдс. ldf</span><span class="sxs-lookup"><span data-stu-id="64f88-140">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="64f88-141">Журнал транзакций для данных Рткксдс</span><span class="sxs-lookup"><span data-stu-id="64f88-141">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="64f88-142">Файлы данных и журналов для парковки звонков и группы ответа</span><span class="sxs-lookup"><span data-stu-id="64f88-142">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64f88-143">данных приложения</span><span class="sxs-lookup"><span data-stu-id="64f88-143">Application database</span></span></th>
<th><span data-ttu-id="64f88-144">Файл данных или назначение журнала</span><span class="sxs-lookup"><span data-stu-id="64f88-144">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64f88-145">Кпсдин. mdf</span><span class="sxs-lookup"><span data-stu-id="64f88-145">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="64f88-146">Динамическая информационная база данных для приложения парковки звонков</span><span class="sxs-lookup"><span data-stu-id="64f88-146">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f88-147">Кпсдин. ldf</span><span class="sxs-lookup"><span data-stu-id="64f88-147">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="64f88-148">Журнал транзакций для файла данных приложения с приостановкой звонков</span><span class="sxs-lookup"><span data-stu-id="64f88-148">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f88-149">Ргсконфиг. mdf</span><span class="sxs-lookup"><span data-stu-id="64f88-149">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="64f88-150">Файл данных службы группы ответа Lync Server для настройки служб</span><span class="sxs-lookup"><span data-stu-id="64f88-150">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f88-151">Ргсконфиг. ldf</span><span class="sxs-lookup"><span data-stu-id="64f88-151">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="64f88-152">Файл журнала транзакций для конфигурации приложения группы ответа</span><span class="sxs-lookup"><span data-stu-id="64f88-152">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f88-153">Ргсдин. mdf</span><span class="sxs-lookup"><span data-stu-id="64f88-153">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="64f88-154">Файл данных службы группы ответа для операций среды выполнения</span><span class="sxs-lookup"><span data-stu-id="64f88-154">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f88-155">Ргсдин. ldf</span><span class="sxs-lookup"><span data-stu-id="64f88-155">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="64f88-156">Журнал транзакций для файла данных среды выполнения службы группы ответа</span><span class="sxs-lookup"><span data-stu-id="64f88-156">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="64f88-157">Файлы данных и журналов для архивации и мониторинга сервера</span><span class="sxs-lookup"><span data-stu-id="64f88-157">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64f88-158">Архивирование и мониторинг файлов базы данных</span><span class="sxs-lookup"><span data-stu-id="64f88-158">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="64f88-159">Файл данных или назначение журнала</span><span class="sxs-lookup"><span data-stu-id="64f88-159">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64f88-160">Лкскдр. mdf</span><span class="sxs-lookup"><span data-stu-id="64f88-160">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="64f88-161">Хранилище данных для процесса записи сведений о звонке (CDR) на сервере мониторинга</span><span class="sxs-lookup"><span data-stu-id="64f88-161">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f88-162">Лкскдр. ldf</span><span class="sxs-lookup"><span data-stu-id="64f88-162">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="64f88-163">Журнал транзакций для данных записи сведений о звонке (CDR)</span><span class="sxs-lookup"><span data-stu-id="64f88-163">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f88-164">Коеметрикс. mdf</span><span class="sxs-lookup"><span data-stu-id="64f88-164">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="64f88-165">Файл данных качества взаимодействия, хранящийся на сервере мониторинга</span><span class="sxs-lookup"><span data-stu-id="64f88-165">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f88-166">Коеметрикс. ldf</span><span class="sxs-lookup"><span data-stu-id="64f88-166">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="64f88-167">Журнал транзакций для наблюдения за данными</span><span class="sxs-lookup"><span data-stu-id="64f88-167">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64f88-168">Лкслог. mdf</span><span class="sxs-lookup"><span data-stu-id="64f88-168">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="64f88-169">Файл данных для хранения данных о мгновенных сообщениях и конференц-связи на сервере архивации</span><span class="sxs-lookup"><span data-stu-id="64f88-169">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64f88-170">Лкслог. ldf</span><span class="sxs-lookup"><span data-stu-id="64f88-170">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="64f88-171">Журнал транзакций для архивации данных</span><span class="sxs-lookup"><span data-stu-id="64f88-171">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="64f88-172">В этом разделе приведены ссылки на диск и на наборы RAID.</span><span class="sxs-lookup"><span data-stu-id="64f88-172">In this topic, references are made to disk and to RAID set.</span></span> <span data-ttu-id="64f88-173">Обратите внимание, что в конфигурации ресурсов SQL Server обращение к диску означает, что это одно аппаратное устройство.</span><span class="sxs-lookup"><span data-stu-id="64f88-173">Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device.</span></span> <span data-ttu-id="64f88-174">Жесткий диск с двумя разделами, один из которых хранит файлы журнала и другой раздел, содержащий файлы данных, отличается от двух дисков, каждый из которых предназначен для файлов журнала или данных.</span><span class="sxs-lookup"><span data-stu-id="64f88-174">A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="64f88-175">В ссылках на массивы RAID существуют различные технологии RAID различных производителей.</span><span class="sxs-lookup"><span data-stu-id="64f88-175">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="64f88-176">И с ростом числа сетей хранения данных (SAN) наборы RAID, выделенные для одной системы, рарер.</span><span class="sxs-lookup"><span data-stu-id="64f88-176">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="64f88-177">Вы должны обратиться к поставщику RAID или сети хранения данных, чтобы определить оптимальную конфигурацию для вашего макета диска при настройке производительности SQL Server с помощью Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64f88-177">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="64f88-178">Кроме того, обратите внимание на то, что не все диски создаются одинаково. Некоторые действия выполняются лучше, чем другие.</span><span class="sxs-lookup"><span data-stu-id="64f88-178">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="64f88-179">Даже диски одного и того же производителя могут варьироваться в зависимости от скорости вращения, размера кэша оборудования и других факторов.</span><span class="sxs-lookup"><span data-stu-id="64f88-179">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

