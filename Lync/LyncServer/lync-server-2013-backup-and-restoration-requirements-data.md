---
title: 'Lync Server 2013: требования к резервному копированию и восстановлению: Data'
description: 'Lync Server 2013: требования к резервному копированию и восстановлению: Data.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e135f09706d31ff3f0efa54c8687546de9fab78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563185"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="2cff8-103">Требования к резервному копированию и восстановлению в Lync Server 2013: Data</span><span class="sxs-lookup"><span data-stu-id="2cff8-103">Backup and restoration requirements in Lync Server 2013: data</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cff8-104">_**Последнее изменение темы:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="2cff8-104">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="2cff8-105">Lync Server использует параметры и сведения о конфигурации, хранящиеся в базах данных, и данные, хранящиеся в базах данных и хранилищах файлов.</span><span class="sxs-lookup"><span data-stu-id="2cff8-105">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="2cff8-106">В этом разделе описываются данные, которые необходимо создать для резервного копирования, чтобы иметь возможность восстановления службы, если ваша организация испытывает сбой или неисправность, а также определяет данные и компоненты, используемые Lync Server, для которого необходимо выполнить резервное копирование по отдельности.</span><span class="sxs-lookup"><span data-stu-id="2cff8-106">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="2cff8-107">Требования к параметрам и конфигурации</span><span class="sxs-lookup"><span data-stu-id="2cff8-107">Settings and Configuration Requirements</span></span>

<span data-ttu-id="2cff8-108">В этом разделе описываются процедуры резервного копирования и восстановления параметров и сведений о конфигурации, которые необходимы для восстановления службы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cff8-108">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="2cff8-109">Сведения о конфигурации находятся в центральном хранилище управления или в другой серверной базе данных или на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2cff8-109">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="2cff8-110">В приведенной ниже таблице указаны параметры и сведения о конфигурации, необходимые для резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="2cff8-110">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="2cff8-111">Параметры и данные конфигурации</span><span class="sxs-lookup"><span data-stu-id="2cff8-111">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cff8-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2cff8-112">Type of data</span></span></th>
<th><span data-ttu-id="2cff8-113">Где хранится</span><span class="sxs-lookup"><span data-stu-id="2cff8-113">Where stored</span></span></th>
<th><span data-ttu-id="2cff8-114">Описание/время резервного копирования</span><span class="sxs-lookup"><span data-stu-id="2cff8-114">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cff8-115">Сведения о конфигурации топологии</span><span class="sxs-lookup"><span data-stu-id="2cff8-115">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="2cff8-116">Центральное хранилище управления (база данных: XDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="2cff8-116">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="2cff8-117">Параметры топологии, политики и конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2cff8-117">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="2cff8-118">Выполните резервное копирование с регулярными резервными копиями и после использования панели управления Lync Server или командлетов для изменения конфигурации или политик.</span><span class="sxs-lookup"><span data-stu-id="2cff8-118">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cff8-119">Сведения о расположении</span><span class="sxs-lookup"><span data-stu-id="2cff8-119">Location information</span></span></p></td>
<td><p><span data-ttu-id="2cff8-120">Центральное хранилище управления (база данных: LIS. mdf)</span><span class="sxs-lookup"><span data-stu-id="2cff8-120">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="2cff8-121">Сведения о конфигурации расширенной корпоративной голосовой связи 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="2cff8-121">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information.</span></span> <span data-ttu-id="2cff8-122">Эти сведения как правило, являются статическими.</span><span class="sxs-lookup"><span data-stu-id="2cff8-122">This information is generally static.</span></span></p>
<p><span data-ttu-id="2cff8-123">Выполните резервное копирование с помощью регулярного резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="2cff8-123">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cff8-124">Сведения о конфигурации группы ответа</span><span class="sxs-lookup"><span data-stu-id="2cff8-124">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="2cff8-125">Сервер переднего внутреннего или стандартного выпуска (база данных: RgsConfig. mdf)</span><span class="sxs-lookup"><span data-stu-id="2cff8-125">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="2cff8-126">Группы агентов группы ответа, очереди и рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="2cff8-126">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="2cff8-127">Выполните резервное копирование с регулярными резервными копиями и после добавления или изменения групп агентов, очередей или рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="2cff8-127">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="2cff8-128">Требования к данным</span><span class="sxs-lookup"><span data-stu-id="2cff8-128">Data Requirements</span></span>

<span data-ttu-id="2cff8-129">Ниже приведен список данных Lync Server, которые необходимо создать для резервного копирования, чтобы можно было восстановить службу Lync Server в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="2cff8-129">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="2cff8-130">Обратите внимание, что некоторые типы данных не требуются для восстановления.</span><span class="sxs-lookup"><span data-stu-id="2cff8-130">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="2cff8-131">В этом разделе не содержатся процедуры для резервного копирования этих типов данных, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="2cff8-131">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="2cff8-132">Временные данные пользователя, такие как конечные точки и подписки, активные серверы конференций и временные состояния конференц-связи (база данных: журнал RTCDyn. mdf)</span><span class="sxs-lookup"><span data-stu-id="2cff8-132">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="2cff8-133">Данные адресной книги (базы данных: Rtcab. mdf и Rtcab1. mdf).</span><span class="sxs-lookup"><span data-stu-id="2cff8-133">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="2cff8-134">База данных адресных книг автоматически создается автоматически из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2cff8-134">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="2cff8-135">Динамическая информация для приложения парковки вызовов (база данных: Кпсдин. mdf)</span><span class="sxs-lookup"><span data-stu-id="2cff8-135">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="2cff8-136">Временные данные группы ответа, такие как состояние входа в систему агента и сведения о ожидании вызовов (база данных: Ргсдин. mdf)</span><span class="sxs-lookup"><span data-stu-id="2cff8-136">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="2cff8-137">База данных соответствия для сохраняемого чата (база данных: MgcComp. mdf).</span><span class="sxs-lookup"><span data-stu-id="2cff8-137">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="2cff8-138">Если включено соответствие сохраняемого чата, информация в базе данных соответствия сохраняемого чата временная, так как у вас есть адаптер, настроенный для считывания сведений из базы данных и преобразования их в альтернативный формат.</span><span class="sxs-lookup"><span data-stu-id="2cff8-138">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="2cff8-139">Поэтому база данных соответствия для сохраняемого чата считается временной.</span><span class="sxs-lookup"><span data-stu-id="2cff8-139">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="2cff8-140">Сервер для сервера сохраняемого чата Lync Server 2013 поставляется с адаптером XML.</span><span class="sxs-lookup"><span data-stu-id="2cff8-140">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="2cff8-141">Вы также можете установить настраиваемые адаптеры, которые принимают эти данные и перемещают их в другие источники, например в архивы Exchange Hosted.</span><span class="sxs-lookup"><span data-stu-id="2cff8-141">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="2cff8-142">В следующей таблице указаны данные, которые необходимо создать для резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="2cff8-142">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="2cff8-143">Данные, хранящиеся в базах данных</span><span class="sxs-lookup"><span data-stu-id="2cff8-143">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cff8-144">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2cff8-144">Type of data</span></span></th>
<th><span data-ttu-id="2cff8-145">Где хранится</span><span class="sxs-lookup"><span data-stu-id="2cff8-145">Where stored</span></span></th>
<th><span data-ttu-id="2cff8-146">Описание/время резервного копирования</span><span class="sxs-lookup"><span data-stu-id="2cff8-146">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cff8-147">Постоянные данные пользователя</span><span class="sxs-lookup"><span data-stu-id="2cff8-147">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="2cff8-148">Сервер переднего внутреннего или стандартного выпуска (база данных: RTCXDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="2cff8-148">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="2cff8-149">Пользовательские права, списки контактов пользователя, данные сервера или пула, запланированные конференции и т. д.</span><span class="sxs-lookup"><span data-stu-id="2cff8-149">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="2cff8-150">Эти данные пользователя не включают контент, переданный в конференцию.</span><span class="sxs-lookup"><span data-stu-id="2cff8-150">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="2cff8-151">Выполните резервное копирование с помощью регулярного резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="2cff8-151">Back up with your regular backups.</span></span> <span data-ttu-id="2cff8-152">Эта информация является динамической, но потеря обновлений не является фатальной для Lync Server, если вам нужно восстановить последнюю обычную резервную копию.</span><span class="sxs-lookup"><span data-stu-id="2cff8-152">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="2cff8-153">Если списки контактов важны для вашей организации, вы можете создавать резервные копии этих данных чаще.</span><span class="sxs-lookup"><span data-stu-id="2cff8-153">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cff8-154">Архивирование данных</span><span class="sxs-lookup"><span data-stu-id="2cff8-154">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="2cff8-155">База данных архивации (база данных: LcsLog. mdf)</span><span class="sxs-lookup"><span data-stu-id="2cff8-155">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="2cff8-156">Эти данные могут храниться в Exchange 2013, если вы включили параметр интеграции с Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="2cff8-156">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="2cff8-157">В противном случае эти данные хранятся в базе данных архивации Lync Server, которая может быть размещена совместно с другой базой данных Lync Server или изолирован на отдельном сервере базы данных.</span><span class="sxs-lookup"><span data-stu-id="2cff8-157">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="2cff8-158">Обмен мгновенными сообщениями и контент собрания.</span><span class="sxs-lookup"><span data-stu-id="2cff8-158">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="2cff8-159">Эти данные не являются критически важными для Lync Server, но они могут быть критически важными для вашей организации в целях соблюдения нормативных требований.</span><span class="sxs-lookup"><span data-stu-id="2cff8-159">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="2cff8-160">Соответствующим образом определите расписание резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="2cff8-160">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cff8-161">Данные мониторинга</span><span class="sxs-lookup"><span data-stu-id="2cff8-161">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="2cff8-162">Мониторинг баз данных (LcsCDR. mdf и QoeMetrics. mdf)</span><span class="sxs-lookup"><span data-stu-id="2cff8-162">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="2cff8-163">Эти базы данных можно разместить совместно с другой базой данных Lync Server или отдельно на отдельном сервере баз данных.</span><span class="sxs-lookup"><span data-stu-id="2cff8-163">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="2cff8-164">Записи сведений о вызовах (LcsCDR. mdf) и показатели качества взаимодействия (QoE) (QoeMetrics. mdf).</span><span class="sxs-lookup"><span data-stu-id="2cff8-164">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="2cff8-165">Записи сведений о вызовах являются динамическими и могут быть критически важными для вашего бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2cff8-165">Call detail records are dynamic and may be critical to your business.</span></span> <span data-ttu-id="2cff8-166">Определите расписание резервного копирования, учитывая, требуются ли эти записи по нормативным причинам.</span><span class="sxs-lookup"><span data-stu-id="2cff8-166">Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="2cff8-167">Сведения о качестве качества взаимодействия: Dynamic.</span><span class="sxs-lookup"><span data-stu-id="2cff8-167">Quality of experience information is dynamic.</span></span> <span data-ttu-id="2cff8-168">Потеря данных QoE не является критической для работы Lync Server, но может быть очень важна для вашего бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2cff8-168">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="2cff8-169">Определите расписание резервного копирования, исходя из того, как критическая информация относится к вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2cff8-169">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cff8-170">Данные сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="2cff8-170">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="2cff8-171">База данных сохраняемого чата (МГД. mdf).</span><span class="sxs-lookup"><span data-stu-id="2cff8-171">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="2cff8-172">Эта база данных может быть размещена совместно с другой базой данных Lync Server или изолированной на отдельном сервере баз данных.</span><span class="sxs-lookup"><span data-stu-id="2cff8-172">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="2cff8-173">Данные сохраняемого чата фактически публикуются в комнатах чата.</span><span class="sxs-lookup"><span data-stu-id="2cff8-173">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="2cff8-174">Эти данные часто являются критически важными для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2cff8-174">This data is often business critical.</span></span></p>
<p><span data-ttu-id="2cff8-175">Можно выбрать использование резервного копирования SQL Server или экспортировать базу данных с помощью командлета <strong>Export-CsPersistentChatData</strong> , который предоставляется в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cff8-175">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="2cff8-176">Для восстановления данных можно импортировать и восстановить базу данных на момент последнего полного резервного копирования, что означает, что базу данных невозможно восстановить до точки сбоя.</span><span class="sxs-lookup"><span data-stu-id="2cff8-176">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="2cff8-177">Требования к данным в хранилище файлов</span><span class="sxs-lookup"><span data-stu-id="2cff8-177">File Store Data Requirements</span></span>

<span data-ttu-id="2cff8-178">В развертывании Enterprise Edition хранилище файлов Lync Server обычно размещается на файловом сервере.</span><span class="sxs-lookup"><span data-stu-id="2cff8-178">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="2cff8-179">В развертывании Standard Edition хранилище файлов Lync Server по умолчанию расположено на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2cff8-179">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="2cff8-180">Как правило, существует одно хранилище файлов Lync Server, доступное для сайта.</span><span class="sxs-lookup"><span data-stu-id="2cff8-180">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="2cff8-181">Хранилище файлов сохраняемого чата использует тот же общий файловый ресурс, что и хранилище файлов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cff8-181">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="2cff8-182">Расположения хранилища файлов определяются как \\ \\ \\ имя общего ресурса сервера.</span><span class="sxs-lookup"><span data-stu-id="2cff8-182">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="2cff8-183">Чтобы найти конкретные места хранения файлов, откройте построитель топологий и просмотрите узел **хранилища файлов** .</span><span class="sxs-lookup"><span data-stu-id="2cff8-183">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="2cff8-184">В следующей таблице указаны хранилища файлов, для которых необходимо выполнить резервное копирование и восстановление.</span><span class="sxs-lookup"><span data-stu-id="2cff8-184">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="2cff8-185">Хранилища файлов</span><span class="sxs-lookup"><span data-stu-id="2cff8-185">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cff8-186">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2cff8-186">Type of data</span></span></th>
<th><span data-ttu-id="2cff8-187">Где хранится</span><span class="sxs-lookup"><span data-stu-id="2cff8-187">Where stored</span></span></th>
<th><span data-ttu-id="2cff8-188">Описание/время резервного копирования</span><span class="sxs-lookup"><span data-stu-id="2cff8-188">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cff8-189">Хранилище файлов Lync Server</span><span class="sxs-lookup"><span data-stu-id="2cff8-189">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="2cff8-190">Как правило, на файловом сервере, кластере файлов или сервере Standard Edition</span><span class="sxs-lookup"><span data-stu-id="2cff8-190">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="2cff8-191">Содержимое собраний, метаданные контента собраний, журналы соответствия требованиям для собраний, файлы данных приложений, файлы обновлений для обновления устройств, звуковые файлы для группы ответа, приостановки вызовов и пообъявлений, а так же файлы, помещенные в комнаты сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="2cff8-191">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="2cff8-192">Выполните резервное копирование с помощью регулярного резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="2cff8-192">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="2cff8-193">Дополнительные требования к резервному копированию</span><span class="sxs-lookup"><span data-stu-id="2cff8-193">Additional Backup Requirements</span></span>

<span data-ttu-id="2cff8-194">Чтобы обеспечить возможность восстановления служб Lync Server в случае сбоя, необходимо выполнить резервное копирование некоторых необходимых компонентов, которые не входят в состав Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cff8-194">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="2cff8-195">В процессе резервного копирования и восстановления Lync Server, описанных в этом документе, не выполняется резервное копирование и восстановление следующих компонентов.</span><span class="sxs-lookup"><span data-stu-id="2cff8-195">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="2cff8-196">**Доменные службы**     Active Directory Необходимо выполнить резервное копирование AD DS, используя средства Active Directory, в то же время, когда вы выполняете резервное копирование сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cff8-196">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="2cff8-197">Важно обеспечить синхронизацию AD DS с Lync Server, чтобы избежать проблем, которые могут возникать, если Lync Server ожидает обращения к контактным объектам, не соответствующим этим в доменных СЛУЖБах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2cff8-197">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="2cff8-198">AD DS хранит следующие параметры, используемые в Lync Server:</span><span class="sxs-lookup"><span data-stu-id="2cff8-198">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="2cff8-199">URI SIP пользователя и другие параметры пользователя.</span><span class="sxs-lookup"><span data-stu-id="2cff8-199">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="2cff8-200">Объекты Contact для таких приложений, как группа ответа и помощник по конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="2cff8-200">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="2cff8-201">Указатель на центральное хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="2cff8-201">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="2cff8-202">Учетная запись проверки подлинности Kerberos (необязательный объект компьютера) и группы безопасности Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cff8-202">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="2cff8-203">Сведения о резервном копировании и восстановлении доменных служб Active Directory в Windows Server 2008 можно найти в разделе "резервное копирование и восстановление AD DS" (пошаговое руководство) по адресу [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105) .</span><span class="sxs-lookup"><span data-stu-id="2cff8-203">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="2cff8-204">**Центр сертификации и сертификаты**     Используйте политику Организации для резервного копирования центра сертификации (ЦС) и сертификатов.</span><span class="sxs-lookup"><span data-stu-id="2cff8-204">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="2cff8-205">Если вы используете экспортируемые закрытые ключи, вы можете создать резервную копию сертификата и закрытого ключа, а затем экспортировать их, если вы используете процедуры, приведенные в этом документе, для восстановления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cff8-205">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="2cff8-206">Если вы используете внутренний ЦС, вы можете повторно зарегистрировать его, если вам потребуется восстановить Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cff8-206">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="2cff8-207">Важно сохранить закрытый ключ в надежном месте, где оно будет доступно в случае сбоя компьютера.</span><span class="sxs-lookup"><span data-stu-id="2cff8-207">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="2cff8-208">**System Center Operations Manager**     Если вы используете Microsoft System Center Operations Manager (ранее Microsoft Operations Manager) для отслеживания развертывания Lync Server, при необходимости можно выполнить резервное копирование данных, создаваемых при мониторинге Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cff8-208">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="2cff8-209">Используйте стандартный процесс резервного копирования SQL Server для резервного копирования файлов System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="2cff8-209">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="2cff8-210">Эти файлы не восстанавливаются во время восстановления.</span><span class="sxs-lookup"><span data-stu-id="2cff8-210">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="2cff8-211">**Конфигурация шлюза телефонной сети общего пользования (PSTN)**     Если вы используете корпоративную голосовую связь или устройства для обеспечения связи в филиалах, необходимо выполнить резервное копирование конфигурации шлюза PSTN.</span><span class="sxs-lookup"><span data-stu-id="2cff8-211">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="2cff8-212">Узнайте у поставщика о резервном копировании и восстановлении конфигураций шлюза PSTN.</span><span class="sxs-lookup"><span data-stu-id="2cff8-212">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="2cff8-213">**Сосуществующие версии Lync Server или Office Communications Server**     Если развертывание Lync Server 2013 входит в состав Lync Server 2010 или более ранней версии Office Communications Server, вы не можете использовать процедуры, описанные в этом документе, для резервного копирования или восстановления более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="2cff8-213">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="2cff8-214">Вместо этого необходимо использовать процедуры резервного копирования и восстановления, описанные специально для более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="2cff8-214">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="2cff8-215">Сведения о резервном копировании и восстановлении Lync Server 2010 приведены в разделе [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) .</span><span class="sxs-lookup"><span data-stu-id="2cff8-215">For details about backing up and restoring Lync Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="2cff8-216">Сведения о резервном копировании и восстановлении Microsoft Office Communications Server 2007 R2 приведены в разделе [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162) .</span><span class="sxs-lookup"><span data-stu-id="2cff8-216">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="2cff8-217">**Сведения о**     инфраструктуре Необходимо выполнить резервное копирование сведений о вашей инфраструктуре, таких как конфигурация брандмауэра, конфигурация балансировки нагрузки, Конфигурация IIS, записи доменных имен (DNS) и IP-адреса, а также конфигурация протокола динамической конфигурации узла (DHCP).</span><span class="sxs-lookup"><span data-stu-id="2cff8-217">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="2cff8-218">Для получения сведений о резервном копировании этих компонентов обратитесь к соответствующим поставщикам.</span><span class="sxs-lookup"><span data-stu-id="2cff8-218">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="2cff8-219">**Microsoft Exchange и единая система обмена сообщениями Exchange (UM)**     Резервное копирование и восстановление единой системы обмена сообщениями Microsoft Exchange и Exchange, как описано в документации по Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="2cff8-219">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="2cff8-220">Подробные сведения о резервном копировании и восстановлении сервера Exchange Server 2013 приведены в разделе [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384) .</span><span class="sxs-lookup"><span data-stu-id="2cff8-220">For details about backing up and restoring Exchange Server 2013, see [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="2cff8-221">Подробные сведения о резервном копировании и восстановлении сервера Exchange Server 2010 приведены в разделе [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179) .</span><span class="sxs-lookup"><span data-stu-id="2cff8-221">For details about backing up and restoring Exchange Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="2cff8-222">Обратите внимание на то, что Lync Server 2013 предоставляет возможность иметь списки контактов пользователей, фотографии пользователей высокой четкости и архивные данные, хранящиеся в Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2cff8-222">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="2cff8-223">Чтобы узнать, как создать резервную копию этих типов данных, просмотрите приведенный ниже список.</span><span class="sxs-lookup"><span data-stu-id="2cff8-223">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="2cff8-224">**Снимки High Definition** архивируются в составе резервной копии Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="2cff8-224">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="2cff8-225">**Единое хранилище контактов** вводится в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2cff8-225">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="2cff8-226">Единое хранилище контактов позволяет пользователям хранить все контактные данные в Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2cff8-226">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="2cff8-227">Необходимо убедиться, что резервные копии актуальны для пользователей с точки зрения того, хранятся ли их контакты в едином хранилище контактов или на внутреннем сервере Lync.</span><span class="sxs-lookup"><span data-stu-id="2cff8-227">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="2cff8-228">В следующих сценариях показано, как миграция контактов пользователей в единое хранилище контактов может вызвать проблемы с процессом резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="2cff8-228">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="2cff8-229">**Сценарий 1:** Контакты пользователей переносятся в единое хранилище контактов, и выполняется восстановление из резервной копии Lync Server, созданной перед переносом контактов пользователей.</span><span class="sxs-lookup"><span data-stu-id="2cff8-229">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="2cff8-230">В этом сценарии пользователь будет иметь состояние устаревших контактов в течение одного дня до тех пор, пока задача миграции Lync Server не начнет перенос контактов пользователя в Exchange.</span><span class="sxs-lookup"><span data-stu-id="2cff8-230">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="2cff8-231">(Обратите внимание, что из-за того, что контакты пользователя были ранее перенесены в единое хранилище контактов, будет использоваться Контактная информация Exchange).</span><span class="sxs-lookup"><span data-stu-id="2cff8-231">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="2cff8-232">В этом сценарии вмешательство администратора не требуется.</span><span class="sxs-lookup"><span data-stu-id="2cff8-232">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="2cff8-233">**Сценарий 2:** Контакты пользователей ранее хранились в едином хранилище контактов, а затем откатываются.</span><span class="sxs-lookup"><span data-stu-id="2cff8-233">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="2cff8-234">Восстановление выполняется из резервной копии Lync Server, созданной при хранении контактов пользователя в едином хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="2cff8-234">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="2cff8-235">В этом сценарии сообщение об ошибке `Error: Incorrect Exchange Version` в журналах клиента или сервера Lyss может указывать на ошибку.</span><span class="sxs-lookup"><span data-stu-id="2cff8-235">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="2cff8-236">Пользователь сможет получить доступ к своему списку контактов в Lync 2013 напрямую из Exchange, но состояние клиента не будет совпадать с состоянием Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cff8-236">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="2cff8-237">Чтобы устранить эту проблему, администратору потребуется выполнить командлеты **Invoke – CsUCSRollback** для затронутых пользователей.</span><span class="sxs-lookup"><span data-stu-id="2cff8-237">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="2cff8-238">**Данные архивации** могут храниться в Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2cff8-238">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="2cff8-239">Эти данные не являются критически важными для Lync Server, но они могут быть критически важными для вашей организации в целях соблюдения нормативных требований.</span><span class="sxs-lookup"><span data-stu-id="2cff8-239">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="2cff8-240">Если данные архивации хранятся в Exchange и важны для Организации, следуйте процедурам резервного копирования и восстановления Exchange.</span><span class="sxs-lookup"><span data-stu-id="2cff8-240">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="2cff8-241">Обратите внимание, что архивные данные, хранящиеся в Exchange, невозможно переместить обратно на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cff8-241">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="2cff8-242">Кроме того, невозможно переместить данные, которые уже хранятся в базе данных архивации Lync, в Exchange.</span><span class="sxs-lookup"><span data-stu-id="2cff8-242">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

