---
title: 'Lync Server 2013: требования к резервному копированию и восстановлению: данные'
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
ms.openlocfilehash: a9b9f077e0f9d7c4137844b2cba352b096fdb564
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="ce86e-102">Требования к резервному копированию и восстановлению в Lync Server 2013: данные</span><span class="sxs-lookup"><span data-stu-id="ce86e-102">Backup and restoration requirements in Lync Server 2013: data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce86e-103">_**Тема последнего изменения:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="ce86e-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="ce86e-104">Lync Server использует параметры и сведения о конфигурации, хранящиеся в базе данных, и данные, хранящиеся в базах данных и хранилищах файлов.</span><span class="sxs-lookup"><span data-stu-id="ce86e-104">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="ce86e-105">В этой статье описаны данные, которые необходимо зарезервировать для восстановления служб, если в вашей организации возникла ошибка или сбой, а также указаны данные и компоненты, используемые Lync Server, для которого необходимо создать резервную копию отдельно.</span><span class="sxs-lookup"><span data-stu-id="ce86e-105">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="ce86e-106">Параметры и требования к конфигурации</span><span class="sxs-lookup"><span data-stu-id="ce86e-106">Settings and Configuration Requirements</span></span>

<span data-ttu-id="ce86e-107">Этот раздел содержит процедуры для резервного копирования и восстановления параметров и данных конфигурации, необходимых для восстановления службы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce86e-107">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="ce86e-108">Сведения о конфигурации находятся в хранилище Центрального управления или в другой серверной базе данных или на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ce86e-108">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="ce86e-109">В приведенной ниже таблице указаны параметры и сведения о конфигурации, необходимые для резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="ce86e-109">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="ce86e-110">Параметры и данные конфигурации</span><span class="sxs-lookup"><span data-stu-id="ce86e-110">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce86e-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ce86e-111">Type of data</span></span></th>
<th><span data-ttu-id="ce86e-112">Где хранится</span><span class="sxs-lookup"><span data-stu-id="ce86e-112">Where stored</span></span></th>
<th><span data-ttu-id="ce86e-113">Описание и время резервного копирования</span><span class="sxs-lookup"><span data-stu-id="ce86e-113">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce86e-114">Сведения о конфигурации топологии</span><span class="sxs-lookup"><span data-stu-id="ce86e-114">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="ce86e-115">Хранилище Центрального управления (база данных: XDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="ce86e-115">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="ce86e-116">Параметры топологии, политики и конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ce86e-116">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="ce86e-117">Создавайте резервные копии с помощью обычных резервных копий и создавайте настройки и политики, используя панель управления или командлеты Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce86e-117">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce86e-118">Сведения о расположении</span><span class="sxs-lookup"><span data-stu-id="ce86e-118">Location information</span></span></p></td>
<td><p><span data-ttu-id="ce86e-119">Хранилище Central Management (база данных: LIS. mdf)</span><span class="sxs-lookup"><span data-stu-id="ce86e-119">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="ce86e-120">Информация о конфигурации 9-1-1 (E9-1-1) Enterprise Voice Enhanced.</span><span class="sxs-lookup"><span data-stu-id="ce86e-120">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information.</span></span> <span data-ttu-id="ce86e-121">Эта информация обычно является статичной.</span><span class="sxs-lookup"><span data-stu-id="ce86e-121">This information is generally static.</span></span></p>
<p><span data-ttu-id="ce86e-122">Создавайте резервные копии с помощью регулярного резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="ce86e-122">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce86e-123">Сведения о конфигурации группы ответа</span><span class="sxs-lookup"><span data-stu-id="ce86e-123">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="ce86e-124">Сервер-сервер или стандартный выпуск Standard (база данных: Ргсконфиг. mdf)</span><span class="sxs-lookup"><span data-stu-id="ce86e-124">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="ce86e-125">Группы агента группы ответа, очереди и рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="ce86e-125">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="ce86e-126">Создавайте резервные копии с помощью регулярного резервного копирования, а затем добавляйте или изменяйте группы агентов, очереди или рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="ce86e-126">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="ce86e-127">Требования к данным</span><span class="sxs-lookup"><span data-stu-id="ce86e-127">Data Requirements</span></span>

<span data-ttu-id="ce86e-128">Ниже приведен список данных сервера Lync, которые необходимо создать для резервного копирования, чтобы можно было восстановить службу Lync Server в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="ce86e-128">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="ce86e-129">Обратите внимание, что некоторые типы данных не требуются для восстановления.</span><span class="sxs-lookup"><span data-stu-id="ce86e-129">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="ce86e-130">В этой статье не содержатся процедуры для резервного копирования данных этих типов, в том числе следующие:</span><span class="sxs-lookup"><span data-stu-id="ce86e-130">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="ce86e-131">Временные данные пользователя, такие как конечные точки и подписки, серверы активных конференций и промежуточные состояния конференц-связи (база данных: Рткдин. mdf)</span><span class="sxs-lookup"><span data-stu-id="ce86e-131">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="ce86e-132">Данные адресной книги (базы данных: Рткаб. mdf и Rtcab1. mdf).</span><span class="sxs-lookup"><span data-stu-id="ce86e-132">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="ce86e-133">База данных адресной книги автоматически генерируется из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ce86e-133">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="ce86e-134">Динамическая информация для приложения для парковки звонков (база данных: Кпсдин. mdf)</span><span class="sxs-lookup"><span data-stu-id="ce86e-134">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="ce86e-135">Временные данные группы ответа, например состояние входа агента и сведения о ожидании звонка (база данных: Ргсдин. mdf)</span><span class="sxs-lookup"><span data-stu-id="ce86e-135">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="ce86e-136">База данных соответствия для сохраняемого чата (база данных: Мгккомп. mdf).</span><span class="sxs-lookup"><span data-stu-id="ce86e-136">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="ce86e-137">Если на вашем компьютере включена постоянная совместимость с друзьями, данные в постоянной базе данных соответствия требованиям к Skype будут переходить на временный период до тех пор, пока адаптер настроен для чтения данных из нее и преобразования их в альтернативный формат.</span><span class="sxs-lookup"><span data-stu-id="ce86e-137">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="ce86e-138">Таким образом, база данных соответствия для сохраняемого чата считается временной.</span><span class="sxs-lookup"><span data-stu-id="ce86e-138">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="ce86e-139">Сервер Lync Server 2013 с сохраненным чат-адаптером входит в комплект поставки адаптера XML.</span><span class="sxs-lookup"><span data-stu-id="ce86e-139">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="ce86e-140">Вы также можете установить пользовательские адаптеры, принимающие эти данные, и переместить их в другие источники, например на размещенные в Exchange архивы.</span><span class="sxs-lookup"><span data-stu-id="ce86e-140">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="ce86e-141">В приведенной ниже таблице указаны данные, для которых требуется выполнить резервное копирование и восстановление.</span><span class="sxs-lookup"><span data-stu-id="ce86e-141">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="ce86e-142">Данные, хранящиеся в базе данных</span><span class="sxs-lookup"><span data-stu-id="ce86e-142">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce86e-143">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ce86e-143">Type of data</span></span></th>
<th><span data-ttu-id="ce86e-144">Где хранится</span><span class="sxs-lookup"><span data-stu-id="ce86e-144">Where stored</span></span></th>
<th><span data-ttu-id="ce86e-145">Описание и время резервного копирования</span><span class="sxs-lookup"><span data-stu-id="ce86e-145">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce86e-146">Постоянные данные пользователя</span><span class="sxs-lookup"><span data-stu-id="ce86e-146">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="ce86e-147">Сервер-сервер или стандартный выпуск Standard (база данных: РТККСДС. mdf)</span><span class="sxs-lookup"><span data-stu-id="ce86e-147">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="ce86e-148">Пользовательские права, списки контактов пользователей, данные сервера или пула, запланированные конференции и т. д.</span><span class="sxs-lookup"><span data-stu-id="ce86e-148">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="ce86e-149">Эти данные пользователя не включают содержимое, отправленное на конференцию.</span><span class="sxs-lookup"><span data-stu-id="ce86e-149">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="ce86e-150">Создавайте резервные копии с помощью регулярного резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="ce86e-150">Back up with your regular backups.</span></span> <span data-ttu-id="ce86e-151">Эта информация является динамической, но потеря обновлений не является критическим для Lync Server, если вам необходимо восстановить последнюю обычную резервную копию.</span><span class="sxs-lookup"><span data-stu-id="ce86e-151">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="ce86e-152">Если список контактов важен для вашей организации, вы можете создавать резервные копии этих данных чаще.</span><span class="sxs-lookup"><span data-stu-id="ce86e-152">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce86e-153">Архивирование данных</span><span class="sxs-lookup"><span data-stu-id="ce86e-153">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="ce86e-154">Архивация базы данных (база данных: Лкслог. mdf)</span><span class="sxs-lookup"><span data-stu-id="ce86e-154">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="ce86e-155">Эти данные могут храниться в Exchange 2013, если вы включили параметр интеграции Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="ce86e-155">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="ce86e-156">В противном случае эти данные хранятся в базе данных архивации Lync Server, которая может быть размещена вместе с другой базой данных сервера Lync или отдельно на другом сервере базы данных.</span><span class="sxs-lookup"><span data-stu-id="ce86e-156">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="ce86e-157">Обмен мгновенными сообщениями и содержимое собрания;</span><span class="sxs-lookup"><span data-stu-id="ce86e-157">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="ce86e-158">Эти данные не очень важны для Lync Server, но это может быть важно для Организации в соответствии с нормативными потребностями.</span><span class="sxs-lookup"><span data-stu-id="ce86e-158">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="ce86e-159">Определите расписание резервного копирования соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="ce86e-159">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce86e-160">Наблюдение за данными</span><span class="sxs-lookup"><span data-stu-id="ce86e-160">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="ce86e-161">Мониторинг баз данных (Лкскдр. mdf и Коеметрикс. mdf)</span><span class="sxs-lookup"><span data-stu-id="ce86e-161">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="ce86e-162">Эти базы данных могут быть выровнены вместе с другой базой данных сервера Lync или изолированными на отдельном сервере базы данных.</span><span class="sxs-lookup"><span data-stu-id="ce86e-162">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="ce86e-163">Записи с подробными сведениями о звонке (Лкскдр. mdf) и качество качества (QoE) (Коеметрикс. mdf).</span><span class="sxs-lookup"><span data-stu-id="ce86e-163">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="ce86e-164">Записи с подробными сведениями о звонке являются динамическими и могут быть важными для вашего бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ce86e-164">Call detail records are dynamic and may be critical to your business.</span></span> <span data-ttu-id="ce86e-165">Определите, нужно ли учитывать эти записи в соответствии с нормативными соображениями, в зависимости от требований к резервному плану.</span><span class="sxs-lookup"><span data-stu-id="ce86e-165">Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="ce86e-166">Сведения о том, как это можно улучшить, — динамические.</span><span class="sxs-lookup"><span data-stu-id="ce86e-166">Quality of experience information is dynamic.</span></span> <span data-ttu-id="ce86e-167">Потеря данных QoE не является критической для работы Lync Server, но может быть очень важна для вашего бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ce86e-167">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="ce86e-168">Определение расписания архивации в зависимости от того, насколько важной является эта информация для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ce86e-168">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce86e-169">Сохраняемые данные чата</span><span class="sxs-lookup"><span data-stu-id="ce86e-169">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="ce86e-170">База данных сохраняемого чата (МГД. mdf).</span><span class="sxs-lookup"><span data-stu-id="ce86e-170">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="ce86e-171">Эта база данных может быть размещена вместе с другой базой данных сервера Lync или изолированной на отдельном сервере базы данных.</span><span class="sxs-lookup"><span data-stu-id="ce86e-171">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="ce86e-172">Сохраняемые данные чата — это реальное содержимое чата, которое публикуется в комнатах чата.</span><span class="sxs-lookup"><span data-stu-id="ce86e-172">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="ce86e-173">Эти данные чаще всего важны для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ce86e-173">This data is often business critical.</span></span></p>
<p><span data-ttu-id="ce86e-174">Вы можете выбрать использование резервной копии SQL Server или экспортировать базу данных с помощью командлета <strong>Export-ксперсистентчатдата</strong> , предоставленного в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce86e-174">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="ce86e-175">Для восстановления данных вы можете импортировать и восстановить базу данных в точке последнего полного резервного копирования, что означает, что вы не сможете восстановить базу данных до точки сбоя.</span><span class="sxs-lookup"><span data-stu-id="ce86e-175">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="ce86e-176">Требования к данным в хранилище файлов</span><span class="sxs-lookup"><span data-stu-id="ce86e-176">File Store Data Requirements</span></span>

<span data-ttu-id="ce86e-177">В развертывании Enterprise Edition хранилище файлов Lync Server обычно находится на файловом сервере.</span><span class="sxs-lookup"><span data-stu-id="ce86e-177">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="ce86e-178">В стандартном развертывании выпуска хранилище файлов Lync Server по умолчанию расположено на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ce86e-178">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="ce86e-179">Обычно существует одно хранилище файлов Lync Server, которое является общим для сайта.</span><span class="sxs-lookup"><span data-stu-id="ce86e-179">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="ce86e-180">В хранилище файлов сохраняемого чата используется тот же общий доступ к файлам, что и в хранилище файлов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce86e-180">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="ce86e-181">Расположение хранилища файлов идентифицировано как \\ \\имя\\общего сервера.</span><span class="sxs-lookup"><span data-stu-id="ce86e-181">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="ce86e-182">Чтобы найти определенные места хранения файлов, откройте "Построитель топологии" и просмотрите раздел " **хранилища файлов** ".</span><span class="sxs-lookup"><span data-stu-id="ce86e-182">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="ce86e-183">В следующей таблице указаны хранилища файлов, для которых необходимо создать резервную копию и восстановить.</span><span class="sxs-lookup"><span data-stu-id="ce86e-183">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="ce86e-184">Хранилища файлов</span><span class="sxs-lookup"><span data-stu-id="ce86e-184">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce86e-185">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ce86e-185">Type of data</span></span></th>
<th><span data-ttu-id="ce86e-186">Где хранится</span><span class="sxs-lookup"><span data-stu-id="ce86e-186">Where stored</span></span></th>
<th><span data-ttu-id="ce86e-187">Описание и время резервного копирования</span><span class="sxs-lookup"><span data-stu-id="ce86e-187">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce86e-188">Хранилище файлов Lync Server</span><span class="sxs-lookup"><span data-stu-id="ce86e-188">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="ce86e-189">Обычно на файловом сервере, кластере файлов или стандартном сервере выпуска</span><span class="sxs-lookup"><span data-stu-id="ce86e-189">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="ce86e-190">Содержимое собрания, метаданные содержимого собраний, журналы соответствия требованиям к собранию, файлы данных приложения, файлы обновлений для обновления устройства, звуковые файлы для группы ответа, регистрация звонков и файлы, отправленные в сохраняемые комнаты чатов.</span><span class="sxs-lookup"><span data-stu-id="ce86e-190">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="ce86e-191">Создавайте резервные копии с помощью регулярного резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="ce86e-191">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="ce86e-192">Дополнительные требования к резервной копии</span><span class="sxs-lookup"><span data-stu-id="ce86e-192">Additional Backup Requirements</span></span>

<span data-ttu-id="ce86e-193">Чтобы обеспечить возможность восстановления служб Lync Server в случае сбоя, необходимо выполнить резервное копирование некоторых необходимых компонентов, которые не входят в состав Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce86e-193">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="ce86e-194">Следующие компоненты не заархивированы или восстановлены в рамках процесса резервного копирования и восстановления на Lync Server, описанного в этом документе:</span><span class="sxs-lookup"><span data-stu-id="ce86e-194">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="ce86e-195">**Доменные службы**   Active Directory для резервного копирования AD DS следует использовать средства Active Directory одновременно с тем же моментом, что и Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce86e-195">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="ce86e-196">Чтобы избежать проблем, которые могут возникать в случае, когда приложение Lync Server считает объекты контакта, не соответствующие этим данным, в AD DS, необходимо поддерживать синхронизацию доменных служб Active Directory с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce86e-196">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="ce86e-197">Доменные службы Active Directory хранят следующие параметры, используемые приложением Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce86e-197">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="ce86e-198">Универсальный код ресурса (URI) пользователя SIP и другие параметры пользователя.</span><span class="sxs-lookup"><span data-stu-id="ce86e-198">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="ce86e-199">Объекты контактов для таких приложений, как группа ответа и конференция.</span><span class="sxs-lookup"><span data-stu-id="ce86e-199">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="ce86e-200">Указатель на хранилище Центрального управления.</span><span class="sxs-lookup"><span data-stu-id="ce86e-200">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="ce86e-201">Учетная запись проверки подлинности Kerberos (необязательный объект компьютера) и группы безопасности Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce86e-201">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="ce86e-202">Подробные сведения о резервном копировании и восстановлении доменных служб Active Directory в Windows Server 2008 можно найти в разделе "резервное копирование и восстановление доменных служб Active Directory" на [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105)этапе.</span><span class="sxs-lookup"><span data-stu-id="ce86e-202">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="ce86e-203">**Центр сертификации и сертификаты**   используют политику своей организации для резервного копирования центра сертификации (ЦС) и сертификатов.</span><span class="sxs-lookup"><span data-stu-id="ce86e-203">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="ce86e-204">Если вы используете экспортируемые закрытые ключи, вы можете создавать резервные копии сертификата и закрытого ключа, а затем экспортировать их, если вы используете процедуры, описанные в этом документе, для восстановления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce86e-204">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="ce86e-205">Если вы используете внутренний центр сертификации, вы можете повторно подать заявку, если вам нужно восстановить Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce86e-205">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="ce86e-206">Важно сохранить закрытый ключ в безопасном месте, где оно будет доступно в случае сбоя компьютера.</span><span class="sxs-lookup"><span data-stu-id="ce86e-206">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="ce86e-207">**System Center Operations Manager**   . Если вы используете Microsoft System Center Operations Manager (прежнее название — Microsoft Operations Manager) для наблюдения за развертыванием Lync Server, вы можете при необходимости создать резервные копии данных, создаваемых в ходе мониторинга сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce86e-207">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="ce86e-208">Используйте стандартный процесс архивации SQL Server для резервного копирования файлов System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="ce86e-208">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="ce86e-209">Эти файлы не восстанавливаются во время восстановления.</span><span class="sxs-lookup"><span data-stu-id="ce86e-209">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="ce86e-210">**Настройка шлюза коммутируемой телефонной сети (PSTN)**   если вы используете корпоративную голосовую или бесперебойную подразделение, вам необходимо создать резервную копию конфигурации шлюза PSTN.</span><span class="sxs-lookup"><span data-stu-id="ce86e-210">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="ce86e-211">Сведения о том, как создавать резервные копии и восстанавливать конфигурации шлюза PSTN, можно получить у своего поставщика.</span><span class="sxs-lookup"><span data-stu-id="ce86e-211">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="ce86e-212">**Сосуществование версий Lync Server и Office Communications Server**   если вы используете развертывание Lync Server 2013 с помощью Lync Server 2010 или более ранней версии Office Communications Server, вы не сможете использовать процедуры, описанные в этом документе, для резервного копирования или восстановления более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="ce86e-212">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="ce86e-213">Вместо этого необходимо использовать процедуры резервного копирования и восстановления, описанные специально для вашей более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="ce86e-213">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="ce86e-214">Подробные сведения об архивации и восстановлении сервера Lync Server 2010 можно [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) найти в разделе.</span><span class="sxs-lookup"><span data-stu-id="ce86e-214">For details about backing up and restoring Lync Server 2010, see [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="ce86e-215">Подробные сведения об архивации и восстановлении Microsoft Office Communications Server 2007 R2 можно найти [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162)в разделе.</span><span class="sxs-lookup"><span data-stu-id="ce86e-215">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="ce86e-216">**Сведения о инфраструктуре**   для архивации сведений о вашей инфраструктуре, например конфигурации брандмауэра, конфигурации балансировки нагрузки, конфигурации информационных служб Интернета (IIS), записей DNS и IP-адресов и динамической конфигурации протокола DHCP (Dynamic Host Configuration Protocol).</span><span class="sxs-lookup"><span data-stu-id="ce86e-216">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="ce86e-217">Подробнее об архивации этих компонентов можно узнать у соответствующих поставщиков.</span><span class="sxs-lookup"><span data-stu-id="ce86e-217">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="ce86e-218">\*\*\*\* Резервное копирование и восстановление единой системы обмена сообщениями Microsoft Exchange и Exchange и Exchange, как описано в документации Microsoft Exchange.   </span><span class="sxs-lookup"><span data-stu-id="ce86e-218">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="ce86e-219">Подробные сведения об архивации и восстановлении Exchange Server 2013 можно найти [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384)в статьях.</span><span class="sxs-lookup"><span data-stu-id="ce86e-219">For details about backing up and restoring Exchange Server 2013, see [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="ce86e-220">Подробные сведения об архивации и восстановлении Exchange Server 2010 можно найти [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179)в статьях.</span><span class="sxs-lookup"><span data-stu-id="ce86e-220">For details about backing up and restoring Exchange Server 2010, see [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="ce86e-221">Обратите внимание, что в Lync Server 2013 введена возможность иметь списки контактов пользователей, пользовательские фотографии High Definition и архивированные данные, хранящиеся в Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ce86e-221">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="ce86e-222">Чтобы узнать, как создавать резервные копии этих типов данных, ознакомьтесь со списком ниже.</span><span class="sxs-lookup"><span data-stu-id="ce86e-222">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="ce86e-223">**Фотографии с высоким разрешением** записываются в резервную копию Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="ce86e-223">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="ce86e-224">**Единое хранилище контактов** представлено в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce86e-224">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="ce86e-225">Единое хранилище контактов позволяет пользователям хранить все контактные данные в Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ce86e-225">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="ce86e-226">Необходимо убедиться в том, что резервные копии обновлены для пользователей в зависимости от того, хранятся ли контакты пользователей в едином банке контактов или на обратном сервере Lync.</span><span class="sxs-lookup"><span data-stu-id="ce86e-226">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="ce86e-227">В следующих сценариях показано, как переносить контакты пользователей в единое хранилище контактов может вызвать проблемы с процессом резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="ce86e-227">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="ce86e-228">**Сценарий 1:** Контакты пользователей переносятся в единое хранилище контактов, и восстановление выполняется из резервной копии сервера Lync, сделанного до миграции контактов пользователей.</span><span class="sxs-lookup"><span data-stu-id="ce86e-228">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="ce86e-229">В этом сценарии пользователь получит состояние устаревших контактов в течение одного дня, пока задача миграции сервера Lync не начнет перенос контактов пользователей в Exchange.</span><span class="sxs-lookup"><span data-stu-id="ce86e-229">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="ce86e-230">(Обратите внимание, что из-за того, что контакты пользователей были ранее перенесены в единое хранилище контактов, будет использоваться Контактная информация Exchange).</span><span class="sxs-lookup"><span data-stu-id="ce86e-230">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="ce86e-231">В этом сценарии вмешательство администратора не требуется.</span><span class="sxs-lookup"><span data-stu-id="ce86e-231">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="ce86e-232">**Сценарий 2.** Контакты пользователей ранее хранились в едином хранилище контактов, но затем откатываются.</span><span class="sxs-lookup"><span data-stu-id="ce86e-232">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="ce86e-233">Восстановление выполняется из резервной копии сервера Lync, которая создается, когда контакты пользователей хранились в едином банке контактов.</span><span class="sxs-lookup"><span data-stu-id="ce86e-233">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="ce86e-234">В этом сценарии сообщение об ошибке `Error: Incorrect Exchange Version` в журналах сервера клиента или Лисс может указывать на ошибку.</span><span class="sxs-lookup"><span data-stu-id="ce86e-234">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="ce86e-235">Пользователь сможет получить доступ к списку контактов в Lync 2013 прямо из Exchange, но состояние клиента не будет совпадать с состоянием сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce86e-235">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="ce86e-236">Чтобы устранить эту проблему, администратору потребуется выполнить командлеты **Invoke-ксуксроллбакк** для пользователей, которых вы затронули.</span><span class="sxs-lookup"><span data-stu-id="ce86e-236">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="ce86e-237">**Данные для архивации** могут храниться в Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ce86e-237">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="ce86e-238">Эти данные не очень важны для Lync Server, но это может быть важно для Организации в соответствии с нормативными потребностями.</span><span class="sxs-lookup"><span data-stu-id="ce86e-238">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="ce86e-239">Если данные архивации хранятся в Exchange и важны для вашей организации, следуйте процедурам резервного копирования и восстановления Exchange.</span><span class="sxs-lookup"><span data-stu-id="ce86e-239">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="ce86e-240">Обратите внимание, что архивированные данные, хранящиеся в Exchange, невозможно вернуть на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce86e-240">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="ce86e-241">Кроме того, невозможно переместить данные, которые уже хранятся в базе данных архивации Lync, в Exchange.</span><span class="sxs-lookup"><span data-stu-id="ce86e-241">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

