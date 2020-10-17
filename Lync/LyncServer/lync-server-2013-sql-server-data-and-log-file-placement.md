---
title: 'Lync Server 2013: размещение данных и файлов журналов SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f536f2d67010856259abf6b98936cd9e096fc93
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509626"
---
# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="3885f-102">Размещение данных и файлов журналов SQL Server для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3885f-102">SQL Server data and log file placement for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3885f-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="3885f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="3885f-104">При планировании и развертывании Microsoft SQL Server 2012 или Microsoft SQL Server 2008 R2 с пакетом обновления 1 (SP1) для пула переднего плана Lync Server 2013, важно учесть, что размещение файлов данных и журналов на физических жестких дисках для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="3885f-104">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="3885f-105">Рекомендуемая конфигурация диска — реализация набора RAID 1 + 0 с использованием 6 шпинделей.</span><span class="sxs-lookup"><span data-stu-id="3885f-105">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="3885f-106">Помещение всех файлов базы данных и журналов, используемых интерфейсным пулом и связанными ролями и службами серверов (то есть, сервера архивации и мониторинга, службы группы ответа Lync Server, службы парковки вызовов Lync Server) на набор дисков RAID с помощью мастера развертывания Lync Server, приведет к конфигурации, которая была протестирована на хорошую производительность.</span><span class="sxs-lookup"><span data-stu-id="3885f-106">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="3885f-107">В следующей таблице подробно описываются файлы базы данных и их назначение.</span><span class="sxs-lookup"><span data-stu-id="3885f-107">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3885f-108">Если для политик и конфигураций SQL Server требуется более специализированная установка, файлы базы данных и журналов можно установить в любое заданное расположение с помощью командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3885f-108">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="3885f-109">Более подробную информацию можно узнать <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">в статье Установка базы данных с помощью командной консоли Lync Server в Lync server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="3885f-109">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="3885f-110">Файлы данных и журналов для центрального хранилища управления</span><span class="sxs-lookup"><span data-stu-id="3885f-110">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3885f-111">Файлы баз данных центрального хранилища управления</span><span class="sxs-lookup"><span data-stu-id="3885f-111">Central Management store database files</span></span></th>
<th><span data-ttu-id="3885f-112">Назначение файла данных или журнала</span><span class="sxs-lookup"><span data-stu-id="3885f-112">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3885f-113">XDS. ldf</span><span class="sxs-lookup"><span data-stu-id="3885f-113">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="3885f-114">Файл журнала транзакций для центрального хранилища управления</span><span class="sxs-lookup"><span data-stu-id="3885f-114">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3885f-115">XDS. mdf</span><span class="sxs-lookup"><span data-stu-id="3885f-115">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="3885f-116">Поддерживает конфигурацию текущей топологии Lync Server 2013, определенную и опубликованную построителем топологий</span><span class="sxs-lookup"><span data-stu-id="3885f-116">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3885f-117">LIS. mdf</span><span class="sxs-lookup"><span data-stu-id="3885f-117">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="3885f-118">Файл данных службы сведений о расположении</span><span class="sxs-lookup"><span data-stu-id="3885f-118">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3885f-119">LIS. ldf</span><span class="sxs-lookup"><span data-stu-id="3885f-119">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="3885f-120">Журнал транзакций для файла данных службы сведений о расположении</span><span class="sxs-lookup"><span data-stu-id="3885f-120">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="3885f-121">Файлы данных и журналов для пользователей, конференц-связи и адресной книги</span><span class="sxs-lookup"><span data-stu-id="3885f-121">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3885f-122">Основные файлы базы данных Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3885f-122">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="3885f-123">Назначение файла данных или журнала</span><span class="sxs-lookup"><span data-stu-id="3885f-123">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3885f-124">RTC. mdf</span><span class="sxs-lookup"><span data-stu-id="3885f-124">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="3885f-125">Постоянные данные пользователя (например, списки управления доступом (ACL), контакты, запланированные конференции)</span><span class="sxs-lookup"><span data-stu-id="3885f-125">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3885f-126">RTC. ldf</span><span class="sxs-lookup"><span data-stu-id="3885f-126">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="3885f-127">Журнал транзакций для данных RTC</span><span class="sxs-lookup"><span data-stu-id="3885f-127">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3885f-128">Журнал RTCDyn. mdf</span><span class="sxs-lookup"><span data-stu-id="3885f-128">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="3885f-129">Поддерживает временные данные пользователя (данные среды выполнения присутствия)</span><span class="sxs-lookup"><span data-stu-id="3885f-129">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3885f-130">Журнал RTCDyn. ldf</span><span class="sxs-lookup"><span data-stu-id="3885f-130">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="3885f-131">Журнал транзакций для данных журнал RTCDyn</span><span class="sxs-lookup"><span data-stu-id="3885f-131">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3885f-132">Rtcab. mdf</span><span class="sxs-lookup"><span data-stu-id="3885f-132">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="3885f-133">База данных адресной книги для связи в режиме реального времени (RTC) — это репозиторий SQL Server, в котором хранятся данные службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="3885f-133">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3885f-134">Rtcab. ldf</span><span class="sxs-lookup"><span data-stu-id="3885f-134">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="3885f-135">Журнал транзакций для службы адресной книги</span><span class="sxs-lookup"><span data-stu-id="3885f-135">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3885f-136">Rtclocal. mdb</span><span class="sxs-lookup"><span data-stu-id="3885f-136">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="3885f-137">Размещение каталога конференций</span><span class="sxs-lookup"><span data-stu-id="3885f-137">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3885f-138">Rtcxds. mdf</span><span class="sxs-lookup"><span data-stu-id="3885f-138">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="3885f-139">Поддерживает резервное копирование данных пользователя</span><span class="sxs-lookup"><span data-stu-id="3885f-139">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3885f-140">Rtcxds. ldf</span><span class="sxs-lookup"><span data-stu-id="3885f-140">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="3885f-141">Журнал транзакций для данных Rtcxds</span><span class="sxs-lookup"><span data-stu-id="3885f-141">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="3885f-142">Файлы данных и журналов для Парковки вызовов и группы ответа</span><span class="sxs-lookup"><span data-stu-id="3885f-142">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3885f-143">База данных приложения</span><span class="sxs-lookup"><span data-stu-id="3885f-143">Application database</span></span></th>
<th><span data-ttu-id="3885f-144">Назначение файла данных или журнала</span><span class="sxs-lookup"><span data-stu-id="3885f-144">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3885f-145">Кпсдин. mdf</span><span class="sxs-lookup"><span data-stu-id="3885f-145">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="3885f-146">Динамическая информационная база данных для приложения парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="3885f-146">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3885f-147">Кпсдин. ldf</span><span class="sxs-lookup"><span data-stu-id="3885f-147">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="3885f-148">Журнал транзакций для файла данных приложения парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="3885f-148">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3885f-149">Rgsconfig. mdf</span><span class="sxs-lookup"><span data-stu-id="3885f-149">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="3885f-150">Файл данных службы группы ответа Lync Server для настройки служб</span><span class="sxs-lookup"><span data-stu-id="3885f-150">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3885f-151">Rgsconfig. ldf</span><span class="sxs-lookup"><span data-stu-id="3885f-151">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="3885f-152">Файл журнала транзакций для конфигурации приложения группы ответа</span><span class="sxs-lookup"><span data-stu-id="3885f-152">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3885f-153">Ргсдин. mdf</span><span class="sxs-lookup"><span data-stu-id="3885f-153">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="3885f-154">Файл данных службы группы ответа для выполняемых операций</span><span class="sxs-lookup"><span data-stu-id="3885f-154">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3885f-155">Ргсдин. ldf</span><span class="sxs-lookup"><span data-stu-id="3885f-155">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="3885f-156">Журнал транзакций для файла данных времени выполнения, связанных со службой группы ответа</span><span class="sxs-lookup"><span data-stu-id="3885f-156">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="3885f-157">Файлы данных и журналов для сервера архивации и мониторинга</span><span class="sxs-lookup"><span data-stu-id="3885f-157">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3885f-158">Файлы базы данных архивации и мониторинга</span><span class="sxs-lookup"><span data-stu-id="3885f-158">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="3885f-159">Назначение файла данных или журнала</span><span class="sxs-lookup"><span data-stu-id="3885f-159">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3885f-160">LcsCdr. mdf</span><span class="sxs-lookup"><span data-stu-id="3885f-160">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="3885f-161">Хранилище данных для процесса записи сведений о вызовах (CDR) сервера мониторинга</span><span class="sxs-lookup"><span data-stu-id="3885f-161">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3885f-162">LcsCdr. ldf</span><span class="sxs-lookup"><span data-stu-id="3885f-162">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="3885f-163">Журнал транзакций для данных регистрации вызовов (CDR)</span><span class="sxs-lookup"><span data-stu-id="3885f-163">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3885f-164">QoEMetrics. mdf</span><span class="sxs-lookup"><span data-stu-id="3885f-164">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="3885f-165">Файл данных качества взаимодействия, хранящийся на сервере мониторинга</span><span class="sxs-lookup"><span data-stu-id="3885f-165">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3885f-166">QoEMetrics. ldf</span><span class="sxs-lookup"><span data-stu-id="3885f-166">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="3885f-167">Журнал транзакций для данных мониторинга</span><span class="sxs-lookup"><span data-stu-id="3885f-167">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3885f-168">Lcslog. mdf</span><span class="sxs-lookup"><span data-stu-id="3885f-168">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="3885f-169">Файл данных для хранения данных о мгновенных сообщениях и конференц-связи на сервере архивации</span><span class="sxs-lookup"><span data-stu-id="3885f-169">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3885f-170">Lcslog. ldf</span><span class="sxs-lookup"><span data-stu-id="3885f-170">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="3885f-171">Журнал транзакций для данных архивации</span><span class="sxs-lookup"><span data-stu-id="3885f-171">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3885f-p103">В этом разделе упоминаются диски и массивы RAID. Обратите внимание на то, что при настройке ресурсов SQL Server под диском понимается отдельное устройство. Жесткий диск с двумя разделами, одним для файлов журналов, а другим для файлов данных, не равноценен двум дискам, выделенным для тех же целей.</span><span class="sxs-lookup"><span data-stu-id="3885f-p103">In this topic, references are made to disk and to RAID set. Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device. A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="3885f-175">Когда речь идет о массивах RAID, следует иметь в виду, что существует ряд различных технологий RAID от разных поставщиков.</span><span class="sxs-lookup"><span data-stu-id="3885f-175">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="3885f-176">А с распространением сетей хранения данных (SAN) выделенные массивы RAID используются все реже.</span><span class="sxs-lookup"><span data-stu-id="3885f-176">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="3885f-177">Вы должны обратиться к поставщику RAID или SAN, чтобы определить оптимальную конфигурацию для вашей структуры диска при настройке производительности SQL Server с помощью Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3885f-177">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="3885f-178">Также обратите внимание на то, что не все диски одинаковы по своим показателям — некоторые работают быстрее, чем другие.</span><span class="sxs-lookup"><span data-stu-id="3885f-178">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="3885f-179">Даже диски от одного производителя могут различаться по производительности из-за скорости вращения, размера аппаратного кэша и других факторов.</span><span class="sxs-lookup"><span data-stu-id="3885f-179">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

