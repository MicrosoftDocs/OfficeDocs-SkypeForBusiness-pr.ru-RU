---
title: 'Lync Server 2013: примечания к выпуску'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf5eadb591b7e198ee75ff197b3836673ae0ecc3
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="2634d-102">Примечания к выпуску для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2634d-102">Release notes for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2634d-103">_**Тема последнего изменения:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="2634d-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="2634d-104">Добро пожаловать в заметки о выпуске Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2634d-104">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="2634d-105">Сведения об известных проблемах, связанных с Lync Server 2013, содержатся в этом файле.</span><span class="sxs-lookup"><span data-stu-id="2634d-105">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="2634d-106">Об этом документе</span><span class="sxs-lookup"><span data-stu-id="2634d-106">About this document</span></span>

<span data-ttu-id="2634d-107">В этом документе содержатся важные сведения, которые необходимо знать перед развертыванием и использованием Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2634d-107">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="2634d-108">Подробные сведения о Lync Server 2013 можно найти в документации [Microsoft Lync server 2013](microsoft-lync-server-2013.md) .</span><span class="sxs-lookup"><span data-stu-id="2634d-108">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="2634d-109">Этот документ включает следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="2634d-109">This document contains the following sections:</span></span>

  - <span data-ttu-id="2634d-110">Клиент Lync 2013</span><span class="sxs-lookup"><span data-stu-id="2634d-110">Lync 2013 client</span></span>

  - <span data-ttu-id="2634d-111">Lync Server</span><span class="sxs-lookup"><span data-stu-id="2634d-111">Lync Server</span></span>

  - <span data-ttu-id="2634d-112">Установка</span><span class="sxs-lookup"><span data-stu-id="2634d-112">Installation</span></span>

  - <span data-ttu-id="2634d-113">Мобильность</span><span class="sxs-lookup"><span data-stu-id="2634d-113">Mobility</span></span>

  - <span data-ttu-id="2634d-114">Конференц-связь</span><span class="sxs-lookup"><span data-stu-id="2634d-114">Conferencing</span></span>

  - <span data-ttu-id="2634d-115">Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="2634d-115">Enterprise Voice</span></span>

  - <span data-ttu-id="2634d-116">Присутствие</span><span class="sxs-lookup"><span data-stu-id="2634d-116">Presence</span></span>

  - <span data-ttu-id="2634d-117">Приложение группы ответа и приложение парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="2634d-117">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="2634d-118">Панель управления Lync Server, построитель топологий и средство планирования</span><span class="sxs-lookup"><span data-stu-id="2634d-118">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="2634d-119">Локализации</span><span class="sxs-lookup"><span data-stu-id="2634d-119">Localization</span></span>

  - <span data-ttu-id="2634d-120">1996</span><span class="sxs-lookup"><span data-stu-id="2634d-120">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="2634d-121">Клиент Lync 2013</span><span class="sxs-lookup"><span data-stu-id="2634d-121">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="2634d-122">Передача файла в мгновенном сообщении завершается сбоем, если файл открыт в другом приложении</span><span class="sxs-lookup"><span data-stu-id="2634d-122">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="2634d-123">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-123">**Issue:**</span></span>

<span data-ttu-id="2634d-124">Если вы пытаетесь передать файл, например документ Word, включив его в мгновенное сообщение другому пользователю Lync, передача будет выполнена успешно, но в действительности может возникнуть сбой при передаче файла.</span><span class="sxs-lookup"><span data-stu-id="2634d-124">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="2634d-125">В клиенте Lync отображается значок для типа файлов, но этот файл нельзя открыть с помощью предполагаемого получателя.</span><span class="sxs-lookup"><span data-stu-id="2634d-125">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="2634d-126">Выводится сообщение об ошибке, в котором сообщается о том, что передача данных завершилась неудачно.</span><span class="sxs-lookup"><span data-stu-id="2634d-126">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="2634d-127">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-127">**Workaround:**</span></span>

<span data-ttu-id="2634d-128">Чтобы устранить эту ошибку, закройте открытый файл или приложение, которое оно открыто, прежде чем пытаться передать его в мгновенное сообщение.</span><span class="sxs-lookup"><span data-stu-id="2634d-128">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="2634d-129">Lync Server</span><span class="sxs-lookup"><span data-stu-id="2634d-129">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="2634d-130">Если служба хранилища данных Lync Server не может выполнить репликацию, администраторы должны будут проверять счетчики производительности для устаревших элементов очереди службы хранилища.</span><span class="sxs-lookup"><span data-stu-id="2634d-130">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="2634d-131">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-131">**Issue:**</span></span>

<span data-ttu-id="2634d-132">Служба хранилища Lync Server использует Windows Fabric для репликации.</span><span class="sxs-lookup"><span data-stu-id="2634d-132">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="2634d-133">Если данные удаляются на основном сервере переднего плана, но удаление на дополнительном сервере переднего плана завершается сбоем (например, при неожиданном завершении работы или ошибках на сервере переднего плана), данные могут быть оставлены и "потерянные".</span><span class="sxs-lookup"><span data-stu-id="2634d-133">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="2634d-134">Потерянные данные могут привести к снижению производительности и потреблению свободного места на диске.</span><span class="sxs-lookup"><span data-stu-id="2634d-134">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="2634d-135">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-135">**Workaround:**</span></span>

<span data-ttu-id="2634d-136">\_Чтобы обойти эту ошибку, если события Лисс DB\_\_, в которых\_используется база данных с ошибкой (ID =\_32058\_)\_и\_Лисс пространство, используемое в журнале событий, АДМИНИСТРАТОРЫ должны проверить счетчик производительности на сервере переднего плана в разделе **Ls: Лисс-API службы хранилища** с именем **Лисс — текущее количество устаревших элементов очереди для службы хранилища**.</span><span class="sxs-lookup"><span data-stu-id="2634d-136">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="2634d-137">Если этот счетчик производительности имеет большое значение (например, более 50000), администратор должен запустить средство Клеануупсторажесервицедата. exe в наборе ресурсов Lync Server 2013, в котором будут удалены все потерянные данные из пула.</span><span class="sxs-lookup"><span data-stu-id="2634d-137">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="2634d-138">Подробнее об этом средстве можно найти в документации по набору ресурсов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2634d-138">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="2634d-139">При изменении конфигурации IP-адреса для сервера или пула необходимо перезапустить службы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2634d-139">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="2634d-140">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-140">**Issue:**</span></span>

<span data-ttu-id="2634d-141">При изменении конфигурации IP-адреса для развертывания Lync Server 2013, например перехода с IPv4 на сдвоенный или из двух стеков в IPv6, не все серверные компоненты изменяют конфигурацию до тех пор, пока не будут перезапускаются эти службы.</span><span class="sxs-lookup"><span data-stu-id="2634d-141">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="2634d-142">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-142">**Workaround:**</span></span>

<span data-ttu-id="2634d-143">Чтобы обойти эту ошибку, перезапустите службы Lync Server после изменения конфигурации IP-адреса для развертывания.</span><span class="sxs-lookup"><span data-stu-id="2634d-143">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="2634d-144">Для этого выполните в командной консоли Lync Server следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="2634d-144">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="2634d-145">Командлет искусственной транзакции конференц-связи с телефонным подключением больше не доступен в пакете управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2634d-145">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="2634d-146">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-146">**Issue:**</span></span>

<span data-ttu-id="2634d-147">Командлет "синтетическая транзакция конференц-связи с телефонным подключением" **— ксдиалинконференЦинг** больше не доступен в пакете управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2634d-147">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="2634d-148">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-148">**Workaround:**</span></span>

<span data-ttu-id="2634d-149">Использование командлета "Виртуальная транзакция конференц-связи с телефонным подключением" **— ксдиалинконференЦинг** поддерживается только внутри предприятия.</span><span class="sxs-lookup"><span data-stu-id="2634d-149">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="2634d-150">Администраторы могут продолжать использовать командлет в командной консоли Lync Server для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="2634d-150">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="2634d-151">В случае необходимости предприятие также может разработать частный пакет управления, чтобы выполнить командлет внутренне.</span><span class="sxs-lookup"><span data-stu-id="2634d-151">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="2634d-152">Служба централизованного ведения журналов останавливается, если сетевой трафик недоступен при копировании файлов журнала в сетевой ресурс</span><span class="sxs-lookup"><span data-stu-id="2634d-152">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="2634d-153">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-153">**Issue:**</span></span>

<span data-ttu-id="2634d-154">Если Служба централизованного ведения журналов настроена на использование сетевого пути (значение параметра Качефиленетворкфолдер командлета **Get-ксклсконфигуратион** — допустимый путь в формате UNC), кэшированные файлы журнала копируются в сетевую папку.</span><span class="sxs-lookup"><span data-stu-id="2634d-154">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="2634d-155">Если при копировании файлов происходит перерыв в сетевом трафике, произойдет исключение, которое вызовет остановку службы централизованного протоколирования.</span><span class="sxs-lookup"><span data-stu-id="2634d-155">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="2634d-156">Служба настроена на автоматическую перезагрузку в три значения, поэтому служба будет восстанавливаться из первых трех исключений.</span><span class="sxs-lookup"><span data-stu-id="2634d-156">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="2634d-157">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-157">**Workaround:**</span></span>

<span data-ttu-id="2634d-158">Для этой проблемы не существует обходного пути.</span><span class="sxs-lookup"><span data-stu-id="2634d-158">There is no workaround for this issue.</span></span> <span data-ttu-id="2634d-159">Чтобы определить причину ошибки, проследите за журналом событий для события с кодом 7031 от диспетчера управления службами, которые регистрируются в журнале при внезапном завершении работы службы «Служба централизованного ведения журнала» Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2634d-159">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="2634d-160">Если это происходит более трех вхождений, перезапустите службу вручную с помощью командлета **Start-ксвиндовсервице** .</span><span class="sxs-lookup"><span data-stu-id="2634d-160">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="2634d-161">Элементы очереди обслуживания хранилища нужно импортировать вручную</span><span class="sxs-lookup"><span data-stu-id="2634d-161">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="2634d-162">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-162">**Issue:**</span></span>

<span data-ttu-id="2634d-163">В Lync Server 2013 хранятся данные о конференциях и обмен мгновенными сообщениями, в том числе архивированные сообщения и запись сведений о вызове (CDR) для базы данных на каждом сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="2634d-163">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="2634d-164">Данные хранятся в базе данных во время ее обработки до того момента, когда они будут переданы в целевое место назначения.</span><span class="sxs-lookup"><span data-stu-id="2634d-164">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="2634d-165">Для повышения производительности Lync Server 2013 периодически экспортирует элементы очереди из локальной базы данных, которые не обрабатываются в течение длительного периода времени, и сохраняет их в хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="2634d-165">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="2634d-166">Если хранилище файлов недоступно, элементы хранятся на каждом сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="2634d-166">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="2634d-167">Эта же операция возникает для предотвращения потери данных во время перемещения пула.</span><span class="sxs-lookup"><span data-stu-id="2634d-167">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="2634d-168">В ходе операции экспорта служба хранилища Lync Server регистрирует все этапы в журнале событий с кодами событий 32075 (полная очистка), 32076 (полная очистка завершена), 32082 (полное удаление), 32083 (запись на уровне обслуживания завершено) завершено), 32089 (произошел сброс из-за заполнения базы данных).</span><span class="sxs-lookup"><span data-stu-id="2634d-168">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="2634d-169">Эти данные не будут автоматически импортированы в систему и будут обрабатываться и доставляться в конечное расположение (SQL Server или Exchange Server).</span><span class="sxs-lookup"><span data-stu-id="2634d-169">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="2634d-170">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-170">**Workaround:**</span></span>

<span data-ttu-id="2634d-171">Для импорта данных в систему администраторам потребуется средство Импортсторажесервицедата в наборе ресурсов Lync Server Resource Kit, который добавляет данные обратно в систему для обработки и доставляется в конечную точку.</span><span class="sxs-lookup"><span data-stu-id="2634d-171">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="2634d-172">Поиск в веб-книге не выполняется, если значение по умолчанию для Усенормализатионрулес изменено на "ложь"</span><span class="sxs-lookup"><span data-stu-id="2634d-172">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="2634d-173">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-173">**Issue:**</span></span>

<span data-ttu-id="2634d-174">Если значение по умолчанию для Усенормализатионрулес изменено на "false", поиск в адресной книге веб-запроса завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="2634d-174">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail.</span></span> <span data-ttu-id="2634d-175">После того как значение по умолчанию будет изменено, пользователи клиента Lync не смогут использовать веб-запрос адресной книги Lync для поиска пользователей.</span><span class="sxs-lookup"><span data-stu-id="2634d-175">After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="2634d-176">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-176">**Workaround:**</span></span>

<span data-ttu-id="2634d-177">Если в качестве значения по умолчанию для Усенормализатионрулес задано значение false, чтобы пользователи могли использовать номера телефонов, определенные в доменных службах Active Directory 2013 без применения правил нормализации, обойти эту ошибку, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="2634d-177">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="2634d-178">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2634d-178">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2634d-179">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="2634d-179">Do one of the following:</span></span>
    
      - <span data-ttu-id="2634d-180">Если в развертывании есть только серверы Lync Server 2013, выполните следующий командлет на глобальном уровне, чтобы изменить значения Усенормализатионрулес и Игнореженерикрулес на true:</span><span class="sxs-lookup"><span data-stu-id="2634d-180">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="2634d-181">Если в развертывании есть сочетание Lync Server 2013 и Lync Server 2010 или Office Communications Server 2007 R2, запустите следующий командлет и назначьте его каждому пулу Lync Server 2013 в топологии.</span><span class="sxs-lookup"><span data-stu-id="2634d-181">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="2634d-182">Дождитесь появления репликации CMS на всех пулах.</span><span class="sxs-lookup"><span data-stu-id="2634d-182">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="2634d-183">Измените файл правил нормализации телефона для развертывания, чтобы очистить содержимое.</span><span class="sxs-lookup"><span data-stu-id="2634d-183">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="2634d-184">Файл находится в общей папке каждого пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2634d-184">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="2634d-185">Если файл отсутствует, создайте пустой файл\_под названием "\_\_\_правила нормализации" номера компании ". txt".</span><span class="sxs-lookup"><span data-stu-id="2634d-185">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="2634d-186">Подождите несколько минут, пока все клиентские пулы смогут прочитать новые файлы.</span><span class="sxs-lookup"><span data-stu-id="2634d-186">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="2634d-187">Выполните следующий командлет на каждом пуле Lync Server 2013 в развертывании.</span><span class="sxs-lookup"><span data-stu-id="2634d-187">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="2634d-188">Сообщение об ошибке сервера адресной книги 21054 формируется один раз для каждого пула Lync 2013</span><span class="sxs-lookup"><span data-stu-id="2634d-188">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="2634d-189">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-189">**Issue:**</span></span>

<span data-ttu-id="2634d-190">Lync Server 2013 Server Book создает событие ошибки 21054 один раз в день, когда выполняется ежедневное обслуживание.</span><span class="sxs-lookup"><span data-stu-id="2634d-190">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="2634d-191">Это сообщение об ошибке также генерируется каждый раз, когда администратор выполняет командлет **Update-ксаддрессбук** , даже если обновление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="2634d-191">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="2634d-192">Однако это событие ошибки можно спокойно проигнорировать после успешного обновления.</span><span class="sxs-lookup"><span data-stu-id="2634d-192">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="2634d-193">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-193">**Workaround:**</span></span>

<span data-ttu-id="2634d-194">При возникновении этого события с ошибкой запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2634d-194">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="2634d-195">Если в командлете сообщается, что нет неиндексированных или отброшенных объектов, событие Error 21054 может быть проигнорировано.</span><span class="sxs-lookup"><span data-stu-id="2634d-195">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="2634d-196">Кроме того, индикатор работоспособности ключа (КХИ) "правильно индексированные пользователи в адресной книге" должен быть отключен в System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="2634d-196">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="2634d-197">Возможен сбой запросов при настройке IPv6 на пограничном пуле</span><span class="sxs-lookup"><span data-stu-id="2634d-197">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="2634d-198">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-198">**Issue:**</span></span>

<span data-ttu-id="2634d-199">Если в пуле Edge настроен протокол IPv6, некоторые запросы к пулу Edge могут завершиться сбоем.</span><span class="sxs-lookup"><span data-stu-id="2634d-199">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="2634d-200">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-200">**Workaround:**</span></span>

<span data-ttu-id="2634d-201">Для решения этой проблемы не настраивайте для пула пограничного сервера IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="2634d-201">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="2634d-202">Во время восстановления пула может произойти сбой командлет Invoke-Кспулфаилбакк</span><span class="sxs-lookup"><span data-stu-id="2634d-202">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="2634d-203">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-203">**Issue:**</span></span>

<span data-ttu-id="2634d-204">При попытке восстановления пула может произойти сбой командлет **Invoke-кспулфаилбакк** , но после повторяющихся попыток сообщение "не удалось завершить процесс хидратион".</span><span class="sxs-lookup"><span data-stu-id="2634d-204">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="2634d-205">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-205">**Workaround:**</span></span>

<span data-ttu-id="2634d-206">Чтобы устранить эту ошибку, запустите командлет повторно и дождитесь, пока командлет не завершится успешно.</span><span class="sxs-lookup"><span data-stu-id="2634d-206">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds.</span></span> <span data-ttu-id="2634d-207">Обратите внимание, что процесс восстановления после сбоя может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="2634d-207">Note that the failback process can take several minutes to complete.</span></span> <span data-ttu-id="2634d-208">Для пула с 20 000 пользователей может потребоваться до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="2634d-208">It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="2634d-209">При добавлении сервера переднего плана в уже установленный пул (гибридная среда, Skype для бизнеса Online) может произойти потеря данных</span><span class="sxs-lookup"><span data-stu-id="2634d-209">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="2634d-210">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-210">**Issue:**</span></span>

<span data-ttu-id="2634d-211">Эта проблема может возникать в среде, в которой в пуле есть более одного сервера переднего плана, и вы либо перезагрузите один из серверов переднего плана, либо добавьте новый сервер переднего плана, который ранее не был частью пула.</span><span class="sxs-lookup"><span data-stu-id="2634d-211">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="2634d-212">Пользователи, чьи данные архивируются, могут столкнуться с потерей данных до тех пор, пока не будет установлено стабильное распределение архивации данных для пула.</span><span class="sxs-lookup"><span data-stu-id="2634d-212">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool.</span></span> <span data-ttu-id="2634d-213">Этот период возможной потери данных ограничен 15 минутами общения между абонентами и 30 минут для конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="2634d-213">This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="2634d-214">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-214">**Workaround:**</span></span>

<span data-ttu-id="2634d-215">Если вы выполняете обслуживание, вместо того, чтобы запускать серверы переднего плана в пуле по одному, вы должны выполнить переключение из пула в другой пул, а затем выполнить на серверах задачи обслуживания.</span><span class="sxs-lookup"><span data-stu-id="2634d-215">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="2634d-216">Вы также можете сделать службу недоступной, прежде чем выполнять задачи обслуживания, а затем восстановить доступность по завершении обслуживания.</span><span class="sxs-lookup"><span data-stu-id="2634d-216">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="2634d-217">Администраторам не удается получить подсчеты лицензий с помощью командлета Get-Ксклиентакцесслиценсе</span><span class="sxs-lookup"><span data-stu-id="2634d-217">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="2634d-218">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-218">**Issue:**</span></span>

<span data-ttu-id="2634d-219">Администраторам не удается получить точную информацию об использовании клиентских лицензий с помощью командлета **Get-ксклиентакцесслиценсе** .</span><span class="sxs-lookup"><span data-stu-id="2634d-219">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="2634d-220">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-220">**Workaround:**</span></span>

<span data-ttu-id="2634d-221">Для проверки типа лицензий сервера можно выполнить командлет **Get-кссервице** , чтобы получить полные доменные имена (фдкнс) всех баз данных.</span><span class="sxs-lookup"><span data-stu-id="2634d-221">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="2634d-222">Если полное доменное имя сервера переднего плана совпадает с полным доменным именем серверной базы данных, лицензия является лицензией Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2634d-222">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="2634d-223">В противном случае лицензия является лицензией Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="2634d-223">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="2634d-224">Счетчик клиентских лицензий не сообщается точно</span><span class="sxs-lookup"><span data-stu-id="2634d-224">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="2634d-225">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-225">**Issue:**</span></span>

<span data-ttu-id="2634d-226">При определении счетчиков клиентских лицензий могут возникать указанные ниже условия.</span><span class="sxs-lookup"><span data-stu-id="2634d-226">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="2634d-227">**Неверное число лицензий для мобильных пользователей**</span><span class="sxs-lookup"><span data-stu-id="2634d-227">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="2634d-228">Количество лицензий зависит от количества уникальных IP-адресов для пользователей, работающих с устройством.</span><span class="sxs-lookup"><span data-stu-id="2634d-228">The license count is based on the number of unique IP addresses for device-based users.</span></span> <span data-ttu-id="2634d-229">Число лицензий будет ограничено указанными ниже способами.</span><span class="sxs-lookup"><span data-stu-id="2634d-229">The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="2634d-230">Если IP-адрес пользователя изменяется во время сеансов Lync, лицензии будут перечислены.</span><span class="sxs-lookup"><span data-stu-id="2634d-230">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="2634d-231">Это может произойти, если пользователь подключается к серверу Lync Server из нескольких местоположений с помощью настольного клиента.</span><span class="sxs-lookup"><span data-stu-id="2634d-231">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="2634d-232">Лицензии будут подсчитываться, если пользователь подключается к мобильному клиенту, так как не удается определить IP-адрес устройства.</span><span class="sxs-lookup"><span data-stu-id="2634d-232">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="2634d-233">**Лицензии используются дважды для звонков по коммутируемой телефонной сети, а клиент Lync — на линии PSTN и звонки из Lync, переадресованные в PSTN-линии**</span><span class="sxs-lookup"><span data-stu-id="2634d-233">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="2634d-234">В следующих сценариях вместо одной будет учитываться две дополнительные лицензии, так как номер телефона и пользователь Lync будут учитываться для определения количества используемых лицензий.</span><span class="sxs-lookup"><span data-stu-id="2634d-234">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used.</span></span> <span data-ttu-id="2634d-235">Чтобы получить точные данные о лицензировании, вручную удалите лицензии, созданные с помощью номера телефона.</span><span class="sxs-lookup"><span data-stu-id="2634d-235">To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="2634d-236">Телефонный звонок в Lync по телефонной линии</span><span class="sxs-lookup"><span data-stu-id="2634d-236">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="2634d-237">Вызов Lync на линии PSTN</span><span class="sxs-lookup"><span data-stu-id="2634d-237">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="2634d-238">КОММУТИРУЕМый Звонок в Lync, а затем Lync пересылает Звонок на телефон PSTN.</span><span class="sxs-lookup"><span data-stu-id="2634d-238">A PSTN call to Lync, and then Lync forwards the call to a PSTN line.</span></span> <span data-ttu-id="2634d-239">Будет учитываться одна из линий PSTN.</span><span class="sxs-lookup"><span data-stu-id="2634d-239">One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="2634d-240">**Лицензия не будет учитываться при входе в систему Lync на телефоне**</span><span class="sxs-lookup"><span data-stu-id="2634d-240">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="2634d-241">Если пользователь использует телефон, сертифицированный Lync, если телефон входит в систему и остается подключенным, то есть состояние входа в систему, но при этом номер телефона не будет считаться на использование лицензии, если запрос на лицензии произошел после входа в систему.</span><span class="sxs-lookup"><span data-stu-id="2634d-241">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="2634d-242">**Лицензии, подсчитанные для КОММУТИРУЕМых телефонов, соединяющих конференции**</span><span class="sxs-lookup"><span data-stu-id="2634d-242">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="2634d-243">Когда пользователь присоединяется к Конференции с помощью телефонной сети PSTN, лицензия будет считаться неточной для присоединения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="2634d-243">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference.</span></span> <span data-ttu-id="2634d-244">Тем не менее, для присоединения к Конференции с помощью телефонной сети PSTN лицензия не требуется.</span><span class="sxs-lookup"><span data-stu-id="2634d-244">However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="2634d-245">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-245">**Workaround:**</span></span>

1.  <span data-ttu-id="2634d-246">**Неверное число лицензий для мобильных пользователей**</span><span class="sxs-lookup"><span data-stu-id="2634d-246">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="2634d-247">Вы можете вручную идентифицировать IP-адреса, которые принадлежат тому же устройству, а затем удалить один из них в подсчете лицензий.</span><span class="sxs-lookup"><span data-stu-id="2634d-247">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="2634d-248">Для этой проблемы не существует обходного пути для мобильных устройств, которые подключаются с помощью клиента Lync.</span><span class="sxs-lookup"><span data-stu-id="2634d-248">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="2634d-249">**Лицензии используются дважды для звонков по коммутируемой телефонной линии в клиенте Lync, клиентам Lync для звонков по сети PSTN и звонков в Lync, пересылаемых на линии PSTN**</span><span class="sxs-lookup"><span data-stu-id="2634d-249">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="2634d-250">Вам потребуется вручную указать номер телефона КТСОП и удалить число лицензий, созданное для него.</span><span class="sxs-lookup"><span data-stu-id="2634d-250">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="2634d-251">**Лицензия не будет учитываться для входного телефона Lync**</span><span class="sxs-lookup"><span data-stu-id="2634d-251">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="2634d-252">Вы можете настроить телефон Lync для выхода из системы, а затем снова войти в систему через определенный интервал, например каждые 3 месяца.</span><span class="sxs-lookup"><span data-stu-id="2634d-252">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="2634d-253">**Лицензии, подсчитанные для КОММУТИРУЕМых телефонов, соединяющих конференции**</span><span class="sxs-lookup"><span data-stu-id="2634d-253">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="2634d-254">Вы можете вручную идентифицировать телефонный номер PSTN, который используется для присоединения к Конференции, и удалить лицензию, созданную номером телефона.</span><span class="sxs-lookup"><span data-stu-id="2634d-254">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="2634d-255">После обновления до Silverlight 5 панель управления Lync Server перестает работать в среде VMware</span><span class="sxs-lookup"><span data-stu-id="2634d-255">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="2634d-256">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-256">**Issue:**</span></span>

<span data-ttu-id="2634d-257">Если вы используете панель управления Lync Server в среде VMware, то после обновления Microsoft Silverlight до версии 5 панель управления Lync Server может перестать работать.</span><span class="sxs-lookup"><span data-stu-id="2634d-257">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="2634d-258">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-258">**Workaround:**</span></span>

<span data-ttu-id="2634d-259">Чтобы устранить эту ошибку, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="2634d-259">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="2634d-260">Удалите Silverlight 5 и установите Silverlight 4 [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span><span class="sxs-lookup"><span data-stu-id="2634d-260">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="2634d-261">Получить доступ к панели управления Lync Server с компьютера, который не является виртуальным компьютером VMware.</span><span class="sxs-lookup"><span data-stu-id="2634d-261">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="2634d-262">Для этого вы можете открыть панель управления Lync Server в меню " **Пуск** " на сервере, если на компьютере установлены средства администрирования Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2634d-262">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="2634d-263">Вы также можете получить доступ к панели управления Lync Server с помощью веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="2634d-263">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="2634d-264">\<URL-адрес будет подобен\_\_домену FQDN\>HTTPS://переднего плана/КСКП.</span><span class="sxs-lookup"><span data-stu-id="2634d-264">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="2634d-265">Сведения о пользователе в службе адресной книги не обновляются после изменения различающегося имени пользователя в Active Directory</span><span class="sxs-lookup"><span data-stu-id="2634d-265">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="2634d-266">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-266">**Issue:**</span></span>

<span data-ttu-id="2634d-267">Если в доменных службах Active Directory изменилось различающееся имя пользователя (DN), все дополнительные изменения не будут обновлены в службе «адресная книга» (ABS).</span><span class="sxs-lookup"><span data-stu-id="2634d-267">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="2634d-268">Это не повлияет на вход или присутствие для пользователя, но предотвращает обмен данными для пользователя, если адрес SIP также изменился, так как при поиске будет возвращен устаревший адрес SIP.</span><span class="sxs-lookup"><span data-stu-id="2634d-268">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="2634d-269">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-269">**Workaround:**</span></span>

<span data-ttu-id="2634d-270">Для решения этой проблемы не изменяйте DN пользователя.</span><span class="sxs-lookup"><span data-stu-id="2634d-270">To work around this issue, do not change a user’s DN.</span></span> <span data-ttu-id="2634d-271">Если вы меняете DN для пользователя на предыдущее, обновления будут отражаться в службе адресной книги.</span><span class="sxs-lookup"><span data-stu-id="2634d-271">If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="2634d-272">Установка</span><span class="sxs-lookup"><span data-stu-id="2634d-272">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="2634d-273">Использование знаков, отличных от ASCII, может привести к сбою при запуске Lync Server</span><span class="sxs-lookup"><span data-stu-id="2634d-273">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="2634d-274">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-274">**Issue:**</span></span>

<span data-ttu-id="2634d-275">Программа установки завершится сбоем, если имя конечной папки содержит знаки, не входящие в набор ASCII (в том числе Юникод, набор двухбайтовых знаков (DBCS), UTF-8 и UTF-16).</span><span class="sxs-lookup"><span data-stu-id="2634d-275">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="2634d-276">Кроме того, программа установки может быть успешно выполнена, но сервер не будет запускаться, если символы, не входящие в набор ASCII, находятся в одном из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="2634d-276">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="2634d-277">Имя компьютера</span><span class="sxs-lookup"><span data-stu-id="2634d-277">Computer name</span></span>

  - <span data-ttu-id="2634d-278">Имя домена</span><span class="sxs-lookup"><span data-stu-id="2634d-278">Domain name</span></span>

  - <span data-ttu-id="2634d-279">Имя пользователя</span><span class="sxs-lookup"><span data-stu-id="2634d-279">User name</span></span>

  - <span data-ttu-id="2634d-280">URI пользователя SIP</span><span class="sxs-lookup"><span data-stu-id="2634d-280">User SIP URI</span></span>

  - <span data-ttu-id="2634d-281">Имя учетной записи службы</span><span class="sxs-lookup"><span data-stu-id="2634d-281">Service account name</span></span>

<span data-ttu-id="2634d-282">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-282">**Workaround:**</span></span>

<span data-ttu-id="2634d-283">Используйте только знаки ASCII в имени конечной папки, имени компьютера, имени домена, имени пользователя, URI пользователя SIP и именах учетных записей служб.</span><span class="sxs-lookup"><span data-stu-id="2634d-283">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="2634d-284">Исправление "повреждение кучи возникает, когда модуль вызывает метод Инсертентитибоди в IIS 7,5", прежде чем устанавливать Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2634d-284">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="2634d-285">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-285">**Issue:**</span></span>

<span data-ttu-id="2634d-286">Исправление "повреждение кучи" возникает, когда модуль вызывает метод Инсертентитибоди в IIS 7,5 "([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), описанный в статье базы знаний Майкрософт 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), перед установкой Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2634d-286">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="2634d-287">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-287">**Workaround:**</span></span>

<span data-ttu-id="2634d-288">Скачайте и установите исправление в центре загрузки Майкрософт по адресу [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span><span class="sxs-lookup"><span data-stu-id="2634d-288">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="2634d-289">Не удается установить Lync Server 2013 в операционной системе Windows Server 2012 версии RTM</span><span class="sxs-lookup"><span data-stu-id="2634d-289">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="2634d-290">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-290">**Issue:**</span></span>

<span data-ttu-id="2634d-291">Не удается установить Lync Server 2013 на сервер ITA Windows Server 2012 из-за сбоя установки Windows Fabric.</span><span class="sxs-lookup"><span data-stu-id="2634d-291">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="2634d-292">Установка Windows Fabric завершается сбоем, так как при этом трассировка структуры создается с использованием формата времени ЧЧ: мм: СС.</span><span class="sxs-lookup"><span data-stu-id="2634d-292">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS.</span></span> <span data-ttu-id="2634d-293">Однако в операционной системе Windows Server ITA формат времени — чч. MM.SS.</span><span class="sxs-lookup"><span data-stu-id="2634d-293">However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="2634d-294">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-294">**Workaround:**</span></span>

<span data-ttu-id="2634d-295">Чтобы устранить эту ошибку, обновите системный реестр перед установкой Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2634d-295">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="2634d-296">Раздел реестра, который необходимо обновить: HKEY\_пользователи.\\ Международная\\\\стимеформат по\\умолчанию для панели управления.</span><span class="sxs-lookup"><span data-stu-id="2634d-296">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="2634d-297">Измените значение Стимеформат на чч: мм: СС с помощью интерфейса командной строки Windows PowerShell следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2634d-297">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="2634d-298">Запустите Windows PowerShell и выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="2634d-298">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="2634d-299">Чтобы просмотреть текущее значение, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2634d-299">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="2634d-300">Запишите текущее значение для Стимеформат, чтобы его можно было восстановить после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="2634d-300">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="2634d-301">Чтобы установить новое значение, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2634d-301">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="2634d-302">После успешной установки Lync Server 2013 восстановите исходное значение для Стимеформат, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2634d-302">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="2634d-303">Set-Итемпроперти $a-Name Стимеформат-value "<значение, указанное в действии 3.</span><span class="sxs-lookup"><span data-stu-id="2634d-303">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="2634d-304">выше> "</span><span class="sxs-lookup"><span data-stu-id="2634d-304">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="2634d-305">Мобильность</span><span class="sxs-lookup"><span data-stu-id="2634d-305">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="2634d-306">Проблемы, связанные с мобильными клиентами в процессе отработки отказа сервера</span><span class="sxs-lookup"><span data-stu-id="2634d-306">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="2634d-307">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-307">**Issue:**</span></span>

<span data-ttu-id="2634d-308">Если происходит сбой сервера Lync и начинается процесс отработки отказа, пользователи мобильных клиентов могут столкнуться со следующими проблемами:</span><span class="sxs-lookup"><span data-stu-id="2634d-308">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="2634d-309">Не удается выполнить входящий звонок или сигнал Lync в течение 10 минут после перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="2634d-309">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="2634d-310">Не удается приема входящих запросов чата</span><span class="sxs-lookup"><span data-stu-id="2634d-310">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="2634d-311">Не удается присоединиться к собранию, если сервер с ошибкой является домашним сервером для пользователя</span><span class="sxs-lookup"><span data-stu-id="2634d-311">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="2634d-312">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-312">**Workaround:**</span></span>

<span data-ttu-id="2634d-313">Для этой проблемы не существует обходного пути.</span><span class="sxs-lookup"><span data-stu-id="2634d-313">There is no workaround for this issue.</span></span> <span data-ttu-id="2634d-314">После завершения процесса отработки отказа обычно будут восстановлены обычные функции.</span><span class="sxs-lookup"><span data-stu-id="2634d-314">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="2634d-315">Если пользователь мобильного устройства отклоняет входящий звонок из другой конечной точки Lync, этот звонок отображается как пропущенное преобразование на мобильных клиентах Lync.</span><span class="sxs-lookup"><span data-stu-id="2634d-315">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="2634d-316">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-316">**Issue:**</span></span>

<span data-ttu-id="2634d-317">Если пользователь мобильного устройства отклоняет входящий звонок, а вызов происходит из другой конечной точки Lync, этот звонок отображается как пропущенный разговор в мобильном клиенте Lync, а не на вызов в списке звонков.</span><span class="sxs-lookup"><span data-stu-id="2634d-317">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="2634d-318">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-318">**Workaround:**</span></span>

<span data-ttu-id="2634d-319">Для этой проблемы не существует обходного пути.</span><span class="sxs-lookup"><span data-stu-id="2634d-319">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="2634d-320">Мобильный клиент может не отображать отображаемое имя федеративного контакта при поиске контактов.</span><span class="sxs-lookup"><span data-stu-id="2634d-320">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="2634d-321">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-321">**Issue:**</span></span>

<span data-ttu-id="2634d-322">Отображаемое имя для федеративных контактов может не отображаться в некоторых сценариях, например при поиске федеративного контакта в списке контактов.</span><span class="sxs-lookup"><span data-stu-id="2634d-322">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="2634d-323">Это может произойти, если в клиенте Lync Mobile отсутствует активная подписка на присутствие для контакта.</span><span class="sxs-lookup"><span data-stu-id="2634d-323">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="2634d-324">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-324">**Workaround:**</span></span>

<span data-ttu-id="2634d-325">Для этой проблемы не существует обходного пути.</span><span class="sxs-lookup"><span data-stu-id="2634d-325">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="2634d-326">В мобильном клиенте отсутствуют сведения о приглашенных и временных метках для пропущенной беседы, которая является приглашением на конференцию</span><span class="sxs-lookup"><span data-stu-id="2634d-326">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="2634d-327">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-327">**Issue:**</span></span>

<span data-ttu-id="2634d-328">В мобильном клиенте, когда пропущенный разговор является приглашением на Конференц-связь, в сообщении о приглашении и отметке экрана отсутствует информация.</span><span class="sxs-lookup"><span data-stu-id="2634d-328">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="2634d-329">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-329">**Workaround:**</span></span>

<span data-ttu-id="2634d-330">Для этой проблемы не существует обходного пути.</span><span class="sxs-lookup"><span data-stu-id="2634d-330">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="2634d-331">Пользователи мобильных клиентов, совершающие звонки по протоколу VoIP, не смогут покинуть голосовую почту для пользователей, для которых настроена Голосовая почта в Exchange 2010 или более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="2634d-331">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="2634d-332">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-332">**Issue:**</span></span>

<span data-ttu-id="2634d-333">Если пользователь мобильного клиента использует VoIP для звонков, пользователь не сможет оставлять сообщения голосовой почты для пользователей, настроенных на использование голосовой почты в Microsoft Exchange Server 2007 или Microsoft Exchange Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2634d-333">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="2634d-334">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-334">**Workaround:**</span></span>

<span data-ttu-id="2634d-335">Для решения этой проблемы используйте Exchange 2010 с пакетом обновления 1 (SP1) или более поздней версии Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="2634d-335">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="2634d-336">При использовании блока с URL-адресом для конфигурации версии клиента на мобильных клиентах может отображаться неправильное сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="2634d-336">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="2634d-337">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-337">**Issue:**</span></span>

<span data-ttu-id="2634d-338">При использовании **блока с URL-адресом** конфигурации клиентской версии на мобильных клиентах, если клиентская версия не поддерживается, может отображаться неправильное сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="2634d-338">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="2634d-339">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-339">**Workaround:**</span></span>

<span data-ttu-id="2634d-340">Чтобы обойти эту ошибку, настройте конфигурацию клиентской версии так, чтобы она использовала **блок** , а не **блок с URL-адресом**.</span><span class="sxs-lookup"><span data-stu-id="2634d-340">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="2634d-341">Конференц-связь</span><span class="sxs-lookup"><span data-stu-id="2634d-341">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="2634d-342">Антивирусное программное обеспечение, работающее на серверах переднего плана Lync Server 2013, может вызвать повторное использование домена приложения, что временно прерывает работу служб для Lync Web App 2013, Lync Mobile 2010 и Lync Mobile 2013 клиенты</span><span class="sxs-lookup"><span data-stu-id="2634d-342">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="2634d-343">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-343">**Issue:**</span></span>

<span data-ttu-id="2634d-344">Антивирусное программное обеспечение может инициировать перезапуск домена приложения, что может привести к тому, что клиентские приложения служб Windows Mobility Service 2013 и единой системы обмена сообщениями (UC) веб-API (Lync Web App 2013, Lync Mobile 2010 и Lync Mobile 2013) теряют свое состояние.</span><span class="sxs-lookup"><span data-stu-id="2634d-344">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="2634d-345">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-345">**Workaround:**</span></span>

<span data-ttu-id="2634d-346">Для решения этой проблемы исключите из антивирусной программы папки, содержащие веб-компоненты и платформу .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2634d-346">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="2634d-347">Дополнительные сведения можно найти в статье 312592 базы знаний Майкрософт "ПРБ: restarts (приложение перезапустится вместе с приложением") в ASP.NET, "at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span><span class="sxs-lookup"><span data-stu-id="2634d-347">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="2634d-348">Следует исключить следующие папки:</span><span class="sxs-lookup"><span data-stu-id="2634d-348">The following folders should be excluded:</span></span>

  - <span data-ttu-id="2634d-349">% ProgramFiles%\\Microsoft Lync Server 2013\\веб-\\компоненты\\МККС рсш</span><span class="sxs-lookup"><span data-stu-id="2634d-349">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="2634d-350">% ProgramFiles%\\Microsoft Lync Server 2013\\веб-\\компоненты\\МККС int</span><span class="sxs-lookup"><span data-stu-id="2634d-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="2634d-351">% ProgramFiles%\\Microsoft Lync Server 2013\\веб-\\компоненты\\Уква int</span><span class="sxs-lookup"><span data-stu-id="2634d-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="2634d-352">% ProgramFiles%\\Microsoft Lync Server 2013\\веб-\\компоненты\\Уква рсш</span><span class="sxs-lookup"><span data-stu-id="2634d-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="2634d-353">% WINDIR%\\Microsoft.NET\\Framework64\\v 4.0.30319\\config</span><span class="sxs-lookup"><span data-stu-id="2634d-353">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="2634d-354">Для успешного присоединения к конференциям в Windows Internet Explorer необходимо включить элементы ActiveX или собственную поддержку XMLHTTP</span><span class="sxs-lookup"><span data-stu-id="2634d-354">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="2634d-355">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-355">**Issue:**</span></span>

<span data-ttu-id="2634d-356">Если пользователь отключил оба элемента ActiveX и поддержку собственного XMLHTTP в Windows Internet Explorer, пользователь не сможет присоединиться к собранию, если Internet Explorer выбран в качестве браузера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2634d-356">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="2634d-357">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-357">**Workaround:**</span></span>

<span data-ttu-id="2634d-358">Включите в Internet Explorer либо элементы ActiveX, либо встроенную поддержку XMLHTTP.</span><span class="sxs-lookup"><span data-stu-id="2634d-358">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="2634d-359">Служба веб-конференций Lync Server не может восстановить базу в критическом режиме</span><span class="sxs-lookup"><span data-stu-id="2634d-359">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="2634d-360">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-360">**Issue:**</span></span>

<span data-ttu-id="2634d-361">Если для архивации включен критический режим, в случае сбоев системы будет запущен критический режим, и Конференции больше не будут работать для участников.</span><span class="sxs-lookup"><span data-stu-id="2634d-361">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants.</span></span> <span data-ttu-id="2634d-362">После того как администратор исправит системные ошибки (например, исправить проблему с базой данных), служба конференц-связи с данными не будет восстановлена автоматически, а администратор должен вручную перезапустить службу конференц-связи для последующего возобновления Конференции.</span><span class="sxs-lookup"><span data-stu-id="2634d-362">After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="2634d-363">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-363">**Workaround:**</span></span>

<span data-ttu-id="2634d-364">Администратору потребуется вручную перезапустить службу конференц-связи после устранения сбоя системы.</span><span class="sxs-lookup"><span data-stu-id="2634d-364">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="2634d-365">Служба веб-конференций пропускает HTTP-прокси для внешних серверов Office Web App</span><span class="sxs-lookup"><span data-stu-id="2634d-365">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="2634d-366">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-366">**Issue:**</span></span>

<span data-ttu-id="2634d-367">Если вы развернули сервер Office Web Apps, внешний по отношению к службе веб-конференций (то есть серверу, не подключенному к внутренней корпоративной сети) в Интернете, сети периметра, и службе веб-конференций требуется HTTP-прокси для подключения к нему, то Сервер Office Web Apps может завершиться сбоем.</span><span class="sxs-lookup"><span data-stu-id="2634d-367">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="2634d-368">Служба веб-конференций пропускает параметр HTTP-прокси, как определено в построителе топологии для настройки сервера Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="2634d-368">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="2634d-369">В результате клиент Lync не сможет предоставить общий доступ к Microsoft PowerPoint 2010 другим участникам Конференции.</span><span class="sxs-lookup"><span data-stu-id="2634d-369">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="2634d-370">При установке локального сервера Lync Server и настройке локального сервера Office Web Apps во внутренней сети конфигурация прокси-сервера не требуется.</span><span class="sxs-lookup"><span data-stu-id="2634d-370">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="2634d-371">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-371">**Workaround:**</span></span>

<span data-ttu-id="2634d-372">Единственным обходным решением является отсутствие конфигурации развертывания, требующей использования прокси-сервера HTTP для связи с внешним сервером Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="2634d-372">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="2634d-373">Добавление видео к Конференции поставщика голосовой конференц-связи не поддерживается</span><span class="sxs-lookup"><span data-stu-id="2634d-373">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="2634d-374">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-374">**Issue:**</span></span>

<span data-ttu-id="2634d-375">Добавление видео не поддерживается, если пользователь присоединен к Конференции поставщика видеоконференций для звука.</span><span class="sxs-lookup"><span data-stu-id="2634d-375">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="2634d-376">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-376">**Workaround:**</span></span>

<span data-ttu-id="2634d-377">Для этой проблемы не существует обходного пути.</span><span class="sxs-lookup"><span data-stu-id="2634d-377">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="2634d-378">Топологии с включенным параметром IPv6. принудительное автоматическое обновление Lync Web App Silverlight для обеспечения возможности демонстрации экрана с помощью Lync Web App</span><span class="sxs-lookup"><span data-stu-id="2634d-378">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="2634d-379">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-379">**Issue:**</span></span>

<span data-ttu-id="2634d-380">Если топология настроена с поддержкой IPv6, пользователи не могут демонстрировать экран в клиенте Lync Web App, если уже установлена более ранняя версия плагина для совместного доступа к экрану.</span><span class="sxs-lookup"><span data-stu-id="2634d-380">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="2634d-381">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-381">**Workaround:**</span></span>

<span data-ttu-id="2634d-382">Чтобы принудительно присоединиться к последней версии плагина для совместного использования экрана при присоединении к собранию через Lync Web App, измените значение **минсуппортедбуилдверсион** с "4.0.7457.0" на "4.0.7577.380" в обоих следующих файлах:</span><span class="sxs-lookup"><span data-stu-id="2634d-382">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="2634d-383">% ProgramFiles%\\веб-компоненты\\\\Microsoft Lync Server 15\\достигают\\клиентские\\подключаемые модули\\реачаппшплугинпропертиес. XML</span><span class="sxs-lookup"><span data-stu-id="2634d-383">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="2634d-384">% ProgramFiles%\\веб\\-компоненты\\Microsoft Lync Server 15\\достигают\\расширения для подключаемых модулей\\клиента\\реачаппшплугинпропертиес. XML</span><span class="sxs-lookup"><span data-stu-id="2634d-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="2634d-385">Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="2634d-385">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="2634d-386">В некоторых случаях клиент Lync, работающий на компьютере, который настроен на использование IPv4 и IPv6, может не поддерживать возможности, которые используют подсеть IP компьютера, такую как E911, обход мультимедиа, управление допуском звонков и маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="2634d-386">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="2634d-387">Сведения, представленные в данном разделе, относятся к накопительным обновлениям для Lync Server 2013: февраль 2013 г.</span><span class="sxs-lookup"><span data-stu-id="2634d-387">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="2634d-388">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-388">**Issue:**</span></span>

<span data-ttu-id="2634d-389">Если клиент Lync запущен на компьютере, на котором включена поддержка двух стеков IPv4 и IPv6, и основан на разрешении DNS для прокси-сервера, клиент может использовать адрес IPv6 компьютера для входа.</span><span class="sxs-lookup"><span data-stu-id="2634d-389">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="2634d-390">После этого клиент Lync будет поддерживать только возможности, поддерживаемые протоколом IPv6, исключив E911, обход мультимедиа, управление допуском звонков и маршрутизацию на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="2634d-390">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="2634d-391">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-391">**Workaround:**</span></span>

<span data-ttu-id="2634d-392">Чтобы обойти эту ошибку, отключите поддержку IPv6 на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="2634d-392">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="2634d-393">Если для пользователя не настроена Корпоративная голосовая связь, пользователю потребуется использовать формат E164 для исходящих звонков с конференции</span><span class="sxs-lookup"><span data-stu-id="2634d-393">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="2634d-394">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-394">**Issue:**</span></span>

<span data-ttu-id="2634d-395">Если для пользователя не настроена Корпоративная голосовая связь, этот пользователь должен будет использовать формат E164 для успешного набора номера из конференции.</span><span class="sxs-lookup"><span data-stu-id="2634d-395">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="2634d-396">Если формат E164 не используется, пользователь не сможет звонить с конференции.</span><span class="sxs-lookup"><span data-stu-id="2634d-396">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="2634d-397">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-397">**Workaround:**</span></span>

<span data-ttu-id="2634d-398">Для решения этой проблемы пользователи, не поддерживающие корпоративную голосовую почту, должны звонить с конференции, используя номера в формате e164.</span><span class="sxs-lookup"><span data-stu-id="2634d-398">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="2634d-399">Присутствие</span><span class="sxs-lookup"><span data-stu-id="2634d-399">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="2634d-400">Если пользователь выбрал параметр "блокировать все приглашения и обмениваться сообщениями", а единое хранилище контактов включается для пользователя, состояние присутствия не будет отвергнуто, если оно должно быть</span><span class="sxs-lookup"><span data-stu-id="2634d-400">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="2634d-401">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-401">**Issue:**</span></span>

<span data-ttu-id="2634d-402">Если пользователь выбрал параметр "блокировать все приглашения и обмениваться сообщениями", а единое хранилище контактов включается для пользователя, состояние присутствия не будет отвергнуто, когда оно должно быть.</span><span class="sxs-lookup"><span data-stu-id="2634d-402">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="2634d-403">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-403">**Workaround:**</span></span>

<span data-ttu-id="2634d-404">Для решения этой проблемы можно отключить единое хранилище контактов для пользователя.</span><span class="sxs-lookup"><span data-stu-id="2634d-404">To work around this issue, you can turn off the unified contact store for the user.</span></span> <span data-ttu-id="2634d-405">Для этого выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="2634d-405">To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="2634d-406">Например:</span><span class="sxs-lookup"><span data-stu-id="2634d-406">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="2634d-407">Пользователи Office Communications Server 2007 R2, расположенные в локальной среде, не видят состояние присутствия пользователей Skype для бизнеса Online в гибридных развертываниях — Гибридная версия</span><span class="sxs-lookup"><span data-stu-id="2634d-407">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="2634d-408">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-408">**Issue:**</span></span>

<span data-ttu-id="2634d-409">Эта неполадка может возникнуть в гибридном развертывании при использовании Lync Server 2013 Director.</span><span class="sxs-lookup"><span data-stu-id="2634d-409">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="2634d-410">Состояние присутствия для пользователей, подключенных к Skype для бизнеса Online, отображается как неизвестное для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="2634d-410">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="2634d-411">Кроме того, пользователи, подключенные к Skype для бизнеса Online, не видят состояние присутствия для локальных пользователей Office Communications Server R2.</span><span class="sxs-lookup"><span data-stu-id="2634d-411">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="2634d-412">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-412">**Workaround:**</span></span>

<span data-ttu-id="2634d-413">Чтобы частично обойти эту ошибку, измените основной сервер (msRTCSIP-пресенцехомесервер) пользователей Skype для бизнеса Online, чтобы он указывал на локальный пул Lync Server 2013, а не в директории Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2634d-413">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="2634d-414">Этот параметр можно изменить на локальном сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="2634d-414">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="2634d-415">Это временное решение правильно показывает состояние присутствия пользователей, которые появятся в Office Communications Server 2007 R2 для пользователей Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="2634d-415">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="2634d-416">Приложение группы ответа, приложение для приостановки звонков и Отправка группового звонка</span><span class="sxs-lookup"><span data-stu-id="2634d-416">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="2634d-417">Вызывающий абонент может услышать одну секунду музыки на удержание во время установки звонка с помощью абонента.</span><span class="sxs-lookup"><span data-stu-id="2634d-417">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="2634d-418">Сведения, представленные в данном разделе, относятся к накопительным обновлениям для Lync Server 2013: февраль 2013 г.</span><span class="sxs-lookup"><span data-stu-id="2634d-418">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="2634d-419">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-419">**Issue:**</span></span>

<span data-ttu-id="2634d-420">Когда звонок извлекается с помощью отправки группового звонка, вызывающий абонент может услышать одну секунду музыки на удержание во время установки звонка с субъекта-получатель.</span><span class="sxs-lookup"><span data-stu-id="2634d-420">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="2634d-421">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-421">**Workaround:**</span></span>

<span data-ttu-id="2634d-422">Для этой проблемы не существует обходного пути.</span><span class="sxs-lookup"><span data-stu-id="2634d-422">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="2634d-423">Агент группы ответа может войти в службу, а затем выйти из нее с помощью консоли агента Lync Server 2010 на сайте Lync Server 2010 формальную группу агента</span><span class="sxs-lookup"><span data-stu-id="2634d-423">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="2634d-424">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-424">**Issue:**</span></span>

<span data-ttu-id="2634d-425">Агент группы ответа Lync Server 2013 может войти в службу и выйти из нее с помощью консоли агента Lync Server 2010 на Lync Server 2010 только для групп с формальными агентами.</span><span class="sxs-lookup"><span data-stu-id="2634d-425">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="2634d-426">В консоли агента Lync Server 2010 пользователи могут видеть только ту группу ответа Lync Server 2010, в которую она входит.</span><span class="sxs-lookup"><span data-stu-id="2634d-426">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="2634d-427">Пользователи не увидят ни одной из групп ответа Lync Server 2013, к которым они относятся.</span><span class="sxs-lookup"><span data-stu-id="2634d-427">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="2634d-428">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-428">**Workaround:**</span></span>

<span data-ttu-id="2634d-429">Если агент группы ответа — пользователь Lync Server 2013 и часть группы "формальный агент" Lync Server 2013, пользователь должен получить доступ к консоли Lync Server 2013 с помощью веб-ссылки в браузере, чтобы выполнить вход и выйти из групп Lync Server 2013 Agent.</span><span class="sxs-lookup"><span data-stu-id="2634d-429">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="2634d-430">Агент группы ответа Lync Server 2010 не может звонить по поручению Lync Server 2013 группы ответа.</span><span class="sxs-lookup"><span data-stu-id="2634d-430">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="2634d-431">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-431">**Issue:**</span></span>

<span data-ttu-id="2634d-432">Пользователь Lync Server 2010, который является агентом группы ответа Lync Server 2013, не может установить звонок от имени группы ответа.</span><span class="sxs-lookup"><span data-stu-id="2634d-432">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="2634d-433">Группа ответа Lync Server 2013 будет недоступна в клиенте Lync, чтобы позвонить.</span><span class="sxs-lookup"><span data-stu-id="2634d-433">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="2634d-434">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-434">**Workaround:**</span></span>

<span data-ttu-id="2634d-435">Для решения этой проблемы необходимо переместить пользователя Lync Server 2010 в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2634d-435">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="2634d-436">Удаление группы ответа из Lync Server 2010 после миграции на Lync Server 2013 запрещает группе ответа принимать входящие звонки</span><span class="sxs-lookup"><span data-stu-id="2634d-436">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="2634d-437">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-437">**Issue:**</span></span>

<span data-ttu-id="2634d-438">Если группа ответа, которая была перенесена из Lync Server 2010 в Lync Server 2013, будет удалена с Lync Server 2010 на панели управления Lync Server 2013 или в командной консоли Lync Server, группа ответа в Lync Server прекратит получать входящие звонки.</span><span class="sxs-lookup"><span data-stu-id="2634d-438">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="2634d-439">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-439">**Workaround:**</span></span>

<span data-ttu-id="2634d-440">Для решения этой проблемы не удаляйте группы ответа из Lync Server 2010, которые были перенесены с Lync Server 2010 на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2634d-440">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="2634d-441">Если группа ответа уже была удалена, вы должны повторно развернуть ее в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2634d-441">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="2634d-442">Если при создании нового управляемого рабочего процесса будет задано значение "неактивен", развертывание рабочего процесса завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="2634d-442">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="2634d-443">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-443">**Issue:**</span></span>

<span data-ttu-id="2634d-444">Если при создании нового управляемого рабочего процесса будет задано значение "неактивен", развертывание рабочего процесса завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="2634d-444">When a new managed workflow is set to inactive when created, deployment of the workflow will fail.</span></span> <span data-ttu-id="2634d-445">Эта проблема возникает, если во время создания рабочего процесса в рабочем процессе задано значение неактивен, но не влияет на рабочий процесс, который редактируется, чтобы сделать его неактивным после развертывания.</span><span class="sxs-lookup"><span data-stu-id="2634d-445">This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="2634d-446">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-446">**Workaround:**</span></span>

<span data-ttu-id="2634d-447">При создании и развертывании рабочего процесса настройте рабочий процесс как активный и затем разверните его.</span><span class="sxs-lookup"><span data-stu-id="2634d-447">When creating and deploying a workflow, set the workflow as active and then deploy it.</span></span> <span data-ttu-id="2634d-448">После успешного развертывания рабочего процесса его можно изменить и установить на неактивный.</span><span class="sxs-lookup"><span data-stu-id="2634d-448">After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="2634d-449">Удаление группы ответа из пула владельца не позволит группе ответа в пуле резервных копий принимать входящие звонки во время отработки отказа, если группа ответа была импортирована в пул резервных копий</span><span class="sxs-lookup"><span data-stu-id="2634d-449">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="2634d-450">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-450">**Issue:**</span></span>

<span data-ttu-id="2634d-451">Если группа ответа, принадлежащая основным пулам, импортирована в пул резервных копий без перезаписи владельца, а группа ответа удалена из пула владельцев, группа ответа в пуле резервных копий не будет отвечать на входящие звонки во время отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="2634d-451">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="2634d-452">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-452">**Workaround:**</span></span>

<span data-ttu-id="2634d-453">Вы должны повторно развернуть группу ответа в основном пуле.</span><span class="sxs-lookup"><span data-stu-id="2634d-453">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="2634d-454">Затем нужно будет экспортировать конфигурацию группы ответа из основного пула и снова импортировать ее в пул резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="2634d-454">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="2634d-455">Вы также можете повторно создать группу ответа в пуле резервных копий.</span><span class="sxs-lookup"><span data-stu-id="2634d-455">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="2634d-456">В этом случае пул резервных копий станет пулом владельцев группы ответа.</span><span class="sxs-lookup"><span data-stu-id="2634d-456">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="2634d-457">Припаркованный звонок не может быть получен из приложения для остановки звонка, если запрос на получение получения выполнен от имени группы ответа.</span><span class="sxs-lookup"><span data-stu-id="2634d-457">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="2634d-458">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-458">**Issue:**</span></span>

<span data-ttu-id="2634d-459">Если выполняются указанные ниже условия, запрос на извлечение для приостановленного звонка завершится сбоем:</span><span class="sxs-lookup"><span data-stu-id="2634d-459">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="2634d-460">Агент входит в группу анонимных ответов.</span><span class="sxs-lookup"><span data-stu-id="2634d-460">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="2634d-461">Агент пытается получить припаркованный вызов из приложения парковки на дозвонку через анонимную группу ответа.</span><span class="sxs-lookup"><span data-stu-id="2634d-461">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="2634d-462">Агент пытается получить звонок, набрав номер орбиты с помощью параметра "позвонить от имени" или с помощью того же параметра в клиенте Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="2634d-462">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="2634d-463">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-463">**Workaround:**</span></span>

<span data-ttu-id="2634d-464">Для этой проблемы не существует обходного пути.</span><span class="sxs-lookup"><span data-stu-id="2634d-464">There are no workarounds for this issue.</span></span> <span data-ttu-id="2634d-465">Припаркованный звонок следует извлечь, не выполняя ее от имени группы ответа.</span><span class="sxs-lookup"><span data-stu-id="2634d-465">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="2634d-466">Панель управления Lync Server, построитель топологий и средство планирования</span><span class="sxs-lookup"><span data-stu-id="2634d-466">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="2634d-467">Ограничения средств планирования</span><span class="sxs-lookup"><span data-stu-id="2634d-467">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="2634d-468">Сведения, представленные в данном разделе, относятся к накопительным обновлениям для Lync Server 2013: февраль 2013 г.</span><span class="sxs-lookup"><span data-stu-id="2634d-468">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="2634d-469">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-469">**Issue:**</span></span>

<span data-ttu-id="2634d-470">При планировании развертывания средство планирования имеет перечисленные ниже ограничения.</span><span class="sxs-lookup"><span data-stu-id="2634d-470">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="2634d-471">Поддерживается не более 10 центральных сайтов</span><span class="sxs-lookup"><span data-stu-id="2634d-471">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="2634d-472">Каждый центральный сайт может иметь не более 14 сайтов филиалов</span><span class="sxs-lookup"><span data-stu-id="2634d-472">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="2634d-473">Каждый центральный сайт может иметь не более 240 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="2634d-473">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="2634d-474">Кроме того, при вычислении рекомендуемой топологии в инструменте "планирование" не включаются значения, указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="2634d-474">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="2634d-475">Количество пользователей, которые были размещены в сети</span><span class="sxs-lookup"><span data-stu-id="2634d-475">The number of users that are homed online</span></span>

  - <span data-ttu-id="2634d-476">Процент пользователей, для которых включена Федерация КСМПП</span><span class="sxs-lookup"><span data-stu-id="2634d-476">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="2634d-477">Процент пользователей, использующих приложение Lync Web App</span><span class="sxs-lookup"><span data-stu-id="2634d-477">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="2634d-478">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-478">**Workaround:**</span></span>

<span data-ttu-id="2634d-479">Для этих проблем не существует обходного пути.</span><span class="sxs-lookup"><span data-stu-id="2634d-479">There is no workaround for these issues.</span></span> <span data-ttu-id="2634d-480">Дополнительные сведения о средстве планирования можно найти в разделе [проектирование топологии для Lync Server 2013 с помощью средства планирования](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span><span class="sxs-lookup"><span data-stu-id="2634d-480">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="2634d-481">Средство планирования может не использовать ранее определенные IP-адреса для пограничной сети при обновлении параметров</span><span class="sxs-lookup"><span data-stu-id="2634d-481">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="2634d-482">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-482">**Issue:**</span></span>

<span data-ttu-id="2634d-483">После того как вы закончите оформление с помощью средства планирования, после внесения изменений в параметры пограничной сети, вместо того, чтобы обновлять существующие IP-адреса, можно добавить в макет дополнительные IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="2634d-483">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="2634d-484">Это может произойти, если вы просматриваете сведения о схеме пограничного сетевого файла, выбираете **ссылку Щелкните здесь, чтобы обновить параметры**, а затем в диалоговом окне Параметры конфигурации Выбери подходящие **полные доменные имена и IP-адреса, но разные порты для служб EDGE на пограничном сервере**.</span><span class="sxs-lookup"><span data-stu-id="2634d-484">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="2634d-485">Применение изменений может привести к тому, что новые IP-адреса и пограничные серверы будут добавлены в проект.</span><span class="sxs-lookup"><span data-stu-id="2634d-485">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="2634d-486">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-486">**Workaround:**</span></span>

<span data-ttu-id="2634d-487">В настоящее время решения этой проблемы не существует.</span><span class="sxs-lookup"><span data-stu-id="2634d-487">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="2634d-488">На панели управления Lync Server "перемещение всех пользователей в пул" может не работать должным образом</span><span class="sxs-lookup"><span data-stu-id="2634d-488">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="2634d-489">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-489">**Issue:**</span></span>

<span data-ttu-id="2634d-490">При использовании панели управления Lync Server для перемещения всех пользователей из одной группы в другую в сложной среде Active Directory, например с несколькими контроллерами домена и родительскими и дочерними доменами, может быть возвращено сообщение об ошибке, в котором указано, что указанный пользователь не является устаревшим пользователем, вместо него используйте командлет Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="2634d-490">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="2634d-491">Это является результатом продолжительных операций репликации в сложных средах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2634d-491">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="2634d-492">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-492">**Workaround:**</span></span>

<span data-ttu-id="2634d-493">Чтобы устранить эту ошибку, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="2634d-493">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="2634d-494">Использование фильтров на панели управления Lync Server для поиска устаревших пользователей, выбор пользователей и использование **команды переместить выбранных пользователей в группу** вместо **перемещения всех пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="2634d-494">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="2634d-495">Используйте командную консоль Lync Server для перемещения пользователей из прежних версий в пакеты с помощью командлетов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2634d-495">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="2634d-496">После обновления подключаемого модуля Microsoft Silverlight для браузера до версии 5 панель управления Lync Server перестает работать в среде VMware.</span><span class="sxs-lookup"><span data-stu-id="2634d-496">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="2634d-497">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-497">**Issue:**</span></span>

<span data-ttu-id="2634d-498">Если вы используете панель управления Lync Server в среде VMware, то после обновления Silverlight до версии 5 панель управления Lync Server может перестать работать.</span><span class="sxs-lookup"><span data-stu-id="2634d-498">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="2634d-499">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-499">**Workaround:**</span></span>

<span data-ttu-id="2634d-500">Чтобы устранить эту ошибку, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="2634d-500">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="2634d-501">Удалите Silverlight 5, а затем установите Silverlight 4 [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span><span class="sxs-lookup"><span data-stu-id="2634d-501">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="2634d-502">Откройте панель управления Lync Server на компьютере, который не является виртуальным компьютером VMware.</span><span class="sxs-lookup"><span data-stu-id="2634d-502">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="2634d-503">Чтобы открыть панель управления Lync Server на удаленном компьютере, установите на нем средства администрирования Lync Server и откройте панель управления Lync Server в меню " **Пуск** " Windows.</span><span class="sxs-lookup"><span data-stu-id="2634d-503">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="2634d-504">Вы также можете открыть панель управления Lync Server, введя URL-адрес в браузере.</span><span class="sxs-lookup"><span data-stu-id="2634d-504">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="2634d-505">\<URL-адрес будет подобен\_\_домену FQDN\>HTTPS://переднего плана/КСКП.</span><span class="sxs-lookup"><span data-stu-id="2634d-505">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="2634d-506">Администратор не может запустить командлет Uninstall-Ксмиррордб после удаления зеркальной базы данных в построителе топологии</span><span class="sxs-lookup"><span data-stu-id="2634d-506">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="2634d-507">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-507">**Issue:**</span></span>

<span data-ttu-id="2634d-508">Если администратор отключает зеркальную базу данных в построителе топологии, а затем удаляет зеркальную базу данных в построителе топологии, в списке дел появляется сообщение о том, что для удаления зеркального отображения с сервера SQL Server необходимо, чтобы администратор выпустил командлет **uninstall-ксмиррордатабасе** .</span><span class="sxs-lookup"><span data-stu-id="2634d-508">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="2634d-509">При попытке администратора выполнить командлет происходит сбой.</span><span class="sxs-lookup"><span data-stu-id="2634d-509">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="2634d-510">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-510">**Workaround:**</span></span>

<span data-ttu-id="2634d-511">Для удаления зеркального отображения SQL пула в построителе топологии необходимо сначала использовать командлет для удаления зеркала в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2634d-511">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="2634d-512">Затем вы можете использовать построитель топологий, чтобы удалить зеркало из топологии.</span><span class="sxs-lookup"><span data-stu-id="2634d-512">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="2634d-513">Чтобы сделать это в SQL Server, запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2634d-513">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="2634d-514">Например, чтобы удалить зеркальное отображение и удалить базы данных пользователей, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2634d-514">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="2634d-515">Параметр *дропексистингдатабасесонмиррор* приводит к удалению затронутых баз данных из зеркала.</span><span class="sxs-lookup"><span data-stu-id="2634d-515">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="2634d-516">Чтобы затем удалить это зеркальное отображение из топологии, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="2634d-516">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="2634d-517">В построителе топологии щелкните пул правой кнопкой мыши и выберите пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="2634d-517">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="2634d-518">Снимите флажок **включить зеркальное отображение хранилища SQL** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2634d-518">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="2634d-519">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="2634d-519">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="2634d-520">Каждый раз, когда вы вносите изменения в отношение зеркального отображения базы данных, необходимо перезапустить все серверы переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="2634d-520">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="2634d-521">Ошибки проверки возвращены в построителе топологии при попытке администратора удалить развертывание с пулом переднего плана, на котором есть связанный с ним Банк-свидетель</span><span class="sxs-lookup"><span data-stu-id="2634d-521">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="2634d-522">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-522">**Issue:**</span></span>

<span data-ttu-id="2634d-523">Если администратор попытается использовать команду **удалить развертывание** в построителе топологии для удаления развертывания, включающего пул переднего плана с соответствующим хранилищем следящего сервера, в построителе топологии появится ошибка проверки подлинности, и действие не будет продолжено.</span><span class="sxs-lookup"><span data-stu-id="2634d-523">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="2634d-524">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-524">**Workaround:**</span></span>

<span data-ttu-id="2634d-525">Чтобы устранить эту ошибку, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="2634d-525">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="2634d-526">Удалите хранилище следящего сервера, прежде чем пытаться удалить развертывание.</span><span class="sxs-lookup"><span data-stu-id="2634d-526">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="2634d-527">Добавьте хранилище следящего сервера для пула переднего плана и удалите его.</span><span class="sxs-lookup"><span data-stu-id="2634d-527">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="2634d-528">Сведения о развертывании сервера сохраняемого чата в средстве планирования и Topology Builder не совпадают</span><span class="sxs-lookup"><span data-stu-id="2634d-528">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="2634d-529">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-529">**Issue:**</span></span>

<span data-ttu-id="2634d-530">Когда Lync Server 2013, средство планирования выводит схему топологии сайтов для развертывания на сервере сохраняемого чата с включенным аварийным восстановлением, схема топологии сайта включает несколько (физических) сайтов, в том числе с одинаковым назначенными на них сохраняемыми серверами чата. семейств.</span><span class="sxs-lookup"><span data-stu-id="2634d-530">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="2634d-531">В построителе топологии все сохраняемые серверы чата представлены как относящиеся к одному (логическому) сайту и указаны в том же узле пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="2634d-531">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="2634d-532">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-532">**Workaround:**</span></span>

<span data-ttu-id="2634d-533">В настоящее время для этой проблемы не существует обходного пути.</span><span class="sxs-lookup"><span data-stu-id="2634d-533">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="2634d-534">Пользователь должен проанализировать выходные данные средства планирования для развертывания сервера сохраняемого чата, а также изменить план в соответствии с конкретными потребностями.</span><span class="sxs-lookup"><span data-stu-id="2634d-534">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="2634d-535">Локализации</span><span class="sxs-lookup"><span data-stu-id="2634d-535">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="2634d-536">Мониторинг</span><span class="sxs-lookup"><span data-stu-id="2634d-536">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="2634d-537">При использовании восточно-азиатской версии Lync Server мастер развертывания отчетов мониторинга отображает неверные символы при определенных обстоятельствах</span><span class="sxs-lookup"><span data-stu-id="2634d-537">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="2634d-538">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-538">**Issue:**</span></span>

<span data-ttu-id="2634d-539">При использовании восточноазиатских версий Lync Server 2013 (например, китайский (упрощенное письмо), китайский (традиционное письмо), японский или корейский — в операционной системе, в которой язык системы не настроен на использование восточноазиатских языков, мастер развертывания отчетов мониторинга вместо локализованных сообщений отображаются вопросительные знаки и другие символы.</span><span class="sxs-lookup"><span data-stu-id="2634d-539">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="2634d-540">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-540">**Workaround:**</span></span>

<span data-ttu-id="2634d-541">Чтобы устранить эту ошибку, настройте языковой стандарт для операционной системы и Lync Server 2013 на тот же язык, после чего будут правильно отображены все сообщения.</span><span class="sxs-lookup"><span data-stu-id="2634d-541">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="2634d-542">Панель управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="2634d-542">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="2634d-543">В некоторых случаях первый элемент верхней панели навигации на странице панели управления Lync Server исчезает, когда вы щелкните последний элемент на верхней панели навигации.</span><span class="sxs-lookup"><span data-stu-id="2634d-543">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="2634d-544">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-544">**Issue:**</span></span>

<span data-ttu-id="2634d-545">В большинстве случаев, когда щелчок последнего элемента на верхней панели навигации на странице сервера Lync Server приводит к исчезновению первого элемента в верхней панели навигации:</span><span class="sxs-lookup"><span data-stu-id="2634d-545">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="2634d-546">На французском языке на странице "Фéдератион et аккèс extern" элемент "Стратéгие д'аккèс extern" исчезнет после нажатия кнопки "Партенаирес фéдéрéс КСМПП".</span><span class="sxs-lookup"><span data-stu-id="2634d-546">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="2634d-547">В немецкой версии на странице "клиенты" элемент "Клиентверсионсконфигуратион" исчезает при нажатии кнопки "Пушбеначричтигунгсконфигуратион".</span><span class="sxs-lookup"><span data-stu-id="2634d-547">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="2634d-548">В русской версии на странице "Конфигурация сети" элемент "глобально" исчезает при нажатии кнопки "маршрут региона".</span><span class="sxs-lookup"><span data-stu-id="2634d-548">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="2634d-549">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-549">**Workaround:**</span></span>

<span data-ttu-id="2634d-550">Чтобы устранить эту ошибку, обновите страницу панели управления Lync Server в браузере.</span><span class="sxs-lookup"><span data-stu-id="2634d-550">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="2634d-551">Страница будет загружена в браузере, где все элементы верхней панели навигации будут отображены.</span><span class="sxs-lookup"><span data-stu-id="2634d-551">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="2634d-552">Адресная книга</span><span class="sxs-lookup"><span data-stu-id="2634d-552">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="2634d-553">Индексирование в адресной книге не работает должным образом в некоторых языках</span><span class="sxs-lookup"><span data-stu-id="2634d-553">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="2634d-554">Сведения, представленные в данном разделе, относятся к накопительным обновлениям для Lync Server 2013: февраль 2013 г.</span><span class="sxs-lookup"><span data-stu-id="2634d-554">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="2634d-555">Если в свойствах пользователя содержится индексированное поле, а в поле содержатся только те символы, которые не могут быть проиндексированы, пользователь не будет отображаться в области поиска, выполненной в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="2634d-555">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="2634d-556">Следующие символы и языковые стандарты не подлежат индексированию:</span><span class="sxs-lookup"><span data-stu-id="2634d-556">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="2634d-557">Прописные, греческие и армянские символы в верхнем регистре</span><span class="sxs-lookup"><span data-stu-id="2634d-557">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="2634d-558">Прописные с надстрочными знаками</span><span class="sxs-lookup"><span data-stu-id="2634d-558">Upper-case accented characters</span></span>

  - <span data-ttu-id="2634d-559">тайский</span><span class="sxs-lookup"><span data-stu-id="2634d-559">Thai</span></span>

  - <span data-ttu-id="2634d-560">Лаос</span><span class="sxs-lookup"><span data-stu-id="2634d-560">Lao</span></span>

  - <span data-ttu-id="2634d-561">Мьянма</span><span class="sxs-lookup"><span data-stu-id="2634d-561">Myanmar</span></span>

  - <span data-ttu-id="2634d-562">Деванагари</span><span class="sxs-lookup"><span data-stu-id="2634d-562">Devanagari</span></span>

  - <span data-ttu-id="2634d-563">Эфиопский</span><span class="sxs-lookup"><span data-stu-id="2634d-563">Ethiopic</span></span>

  - <span data-ttu-id="2634d-564">Тибетский</span><span class="sxs-lookup"><span data-stu-id="2634d-564">Tibetan</span></span>

  - <span data-ttu-id="2634d-565">бенгальский</span><span class="sxs-lookup"><span data-stu-id="2634d-565">Bengali</span></span>

  - <span data-ttu-id="2634d-566">гуджарати</span><span class="sxs-lookup"><span data-stu-id="2634d-566">Gujarati</span></span>

  - <span data-ttu-id="2634d-567">телугу</span><span class="sxs-lookup"><span data-stu-id="2634d-567">Telugu</span></span>

  - <span data-ttu-id="2634d-568">Все другие индийские наборы знаков</span><span class="sxs-lookup"><span data-stu-id="2634d-568">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="2634d-569">Lync Web App, веб-планировщик и веб-компоненты</span><span class="sxs-lookup"><span data-stu-id="2634d-569">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="2634d-570">Резервные языковые параметры для некоторых языков в веб-планировщике Lync, подключение к Интернету, средство запуска присоединения к сети, управление комнатой чата и Октаб могут не работать должным образом</span><span class="sxs-lookup"><span data-stu-id="2634d-570">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="2634d-571">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-571">**Issue:**</span></span>

<span data-ttu-id="2634d-572">При выборе нейтрального языкового стандарта в веб-браузере (в Internet Explorer) например, имя языка без дополнительных спецификаций, например " \[Норвежский номер\]"), а не языковой стандарт, задающий язык, сценарий и языковой стандарт (например \[, "Норвежский, букмол (Норвегия)-нет\]") может привести к неожиданному поведению отображения для некоторых языков в веб</span><span class="sxs-lookup"><span data-stu-id="2634d-572">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="2634d-573">Например, пользователи могут видеть страницу на английском языке, если выбран один из указанных ниже языков.</span><span class="sxs-lookup"><span data-stu-id="2634d-573">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="2634d-574">норвежский</span><span class="sxs-lookup"><span data-stu-id="2634d-574">Norwegian</span></span>

  - <span data-ttu-id="2634d-575">Португальский</span><span class="sxs-lookup"><span data-stu-id="2634d-575">Portuguese</span></span>

  - <span data-ttu-id="2634d-576">сербский</span><span class="sxs-lookup"><span data-stu-id="2634d-576">Serbian</span></span>

<span data-ttu-id="2634d-577">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-577">**Workaround:**</span></span>

<span data-ttu-id="2634d-578">Если вы хотите выбрать язык со нейтральным региональным стандартом, всегда убедитесь, что вы также добавляете язык с определенным языковым стандартом (с использованием сценария и/или кода страны) в качестве дополнительного языка в списке языковых параметров вашего браузера.</span><span class="sxs-lookup"><span data-stu-id="2634d-578">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="2634d-579">Ограниченная поддержка национальных настроек азербайджанский и узбекский при использовании веб-планировщика Lync, подключение к сети, средство запуска присоединения к Интернету, управление комнатой чата и Октаб в некоторых веб-браузерах</span><span class="sxs-lookup"><span data-stu-id="2634d-579">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="2634d-580">Сведения, представленные в данном разделе, относятся к накопительным обновлениям для Lync Server 2013: февраль 2013 г.</span><span class="sxs-lookup"><span data-stu-id="2634d-580">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="2634d-581">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-581">**Issue:**</span></span>

<span data-ttu-id="2634d-582">Если вы используете Internet Explorer 8 или Internet Explorer 9 и устанавливаете для языка браузера значение Азербайджанский (латиница) или узбекский (латиница), страницы средства запуска для подключения к Интернету и присоединения будут отображаться на английском языке или на предпочтительном языке, выбранном в браузере.</span><span class="sxs-lookup"><span data-stu-id="2634d-582">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="2634d-583">При использовании браузеров Firefox или Chrome и настройке языка браузера на азербайджанский (латиница) или узбекский (латиница), веб-приложение Lync Web App, веб-планировщик Lync и RGS Октаб будут отображаться на английском языке или на предпочтительном языке, установленном для браузера.</span><span class="sxs-lookup"><span data-stu-id="2634d-583">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="2634d-584">Язык "узбекский (латиница)" не поддерживается в браузере Safari.</span><span class="sxs-lookup"><span data-stu-id="2634d-584">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="2634d-585">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-585">**Workaround:**</span></span>

<span data-ttu-id="2634d-586">Для этих проблем не существует обходного пути.</span><span class="sxs-lookup"><span data-stu-id="2634d-586">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="2634d-587">Отсутствует стрелка раскрывающегося списка "присоединиться к собранию из" в румынского версии Lync Web App</span><span class="sxs-lookup"><span data-stu-id="2634d-587">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="2634d-588">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-588">**Issue:**</span></span>

<span data-ttu-id="2634d-589">Если пользователь, использующий версию Lync Web App, выполняет описанные ниже действия, в раскрывающемся списке **присоединиться к собранию** не отображается стрелка раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="2634d-589">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="2634d-590">На вкладке **Общие** установите флажок **Запомнить меня на этом компьютере** .</span><span class="sxs-lookup"><span data-stu-id="2634d-590">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="2634d-591">Откройте вкладку **Телефон** .</span><span class="sxs-lookup"><span data-stu-id="2634d-591">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="2634d-592">Щелкните раскрывающийся список **присоединиться к собранию**.</span><span class="sxs-lookup"><span data-stu-id="2634d-592">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="2634d-593">Пользователи не увидят стрелки, указывающей на то, что в **Lync Web App**есть больше параметров, которые включают: **не присоединять звук** (в румынская, "ню SE асоЦиаžа La компонент) и **новый номер**" (на румынского, "нумăр НАУ").</span><span class="sxs-lookup"><span data-stu-id="2634d-593">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="2634d-594">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-594">**Workaround:**</span></span>

<span data-ttu-id="2634d-595">Несмотря на то, что стрелка для этого раскрывающегося списка не отображается, пользователи могут по-прежнему выбирать дополнительные параметры в списке, щелкая значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2634d-595">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="2634d-596">При использовании турецкой версии веб-планировщика Lync не удается сохранить собрание при использовании параметра "люди, выбранные" в разделе "кто является выступающим"</span><span class="sxs-lookup"><span data-stu-id="2634d-596">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="2634d-597">**Проблемах**</span><span class="sxs-lookup"><span data-stu-id="2634d-597">**Issue:**</span></span>

<span data-ttu-id="2634d-598">При создании и редактировании собрания в турецком варианте веб-планировщика Lync параметр "люди, выбранные пользователем" в разделе "кто является выступающим" не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="2634d-598">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported.</span></span> <span data-ttu-id="2634d-599">Если выбран этот параметр, собрание невозможно сохранить.</span><span class="sxs-lookup"><span data-stu-id="2634d-599">When this option is selected, the meeting can't be saved.</span></span> <span data-ttu-id="2634d-600">Вместо этого появляется сообщение об ошибке, указывающее на то, что один или несколько пользователей нельзя сделать выступающими.</span><span class="sxs-lookup"><span data-stu-id="2634d-600">Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="2634d-601">**Смысла**</span><span class="sxs-lookup"><span data-stu-id="2634d-601">**Workaround:**</span></span>

<span data-ttu-id="2634d-602">Для решения этой проблемы пользователи могут использовать параметр по умолчанию "люди из моей организации" или любой другой вариант, например "только организатор" или "все, включая пользователей за пределами моей компании".</span><span class="sxs-lookup"><span data-stu-id="2634d-602">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company."</span></span> <span data-ttu-id="2634d-603">После того как вы присоединяется к собранию, организатор может понизить или переместить людей на их правильную роль.</span><span class="sxs-lookup"><span data-stu-id="2634d-603">The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="2634d-604">Кроме того, пользователи, знакомые с другим языком, могут изменить язык, выбранный в браузере, на один из языков, поддерживаемых 43, и попытаться использовать параметр "люди, которые вы выбираете".</span><span class="sxs-lookup"><span data-stu-id="2634d-604">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="2634d-605">1996</span><span class="sxs-lookup"><span data-stu-id="2634d-605">Copyright</span></span>

<span data-ttu-id="2634d-606">Этот документ поддерживает предварительную версию программного продукта, который может быть изменен перед окончательным коммерческой выпуском, а также конфиденциальной информацией и сведениями о собственности Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="2634d-606">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation.</span></span> <span data-ttu-id="2634d-607">Оно раскрывается в соответствии с соглашением о неразглашении между получателем и корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2634d-607">It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft.</span></span> <span data-ttu-id="2634d-608">Этот документ предоставляется исключительно в информационных целях, и корпорация Майкрософт не дает никаких гарантий, явных и подразумеваемых, в этом документе.</span><span class="sxs-lookup"><span data-stu-id="2634d-608">This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document.</span></span> <span data-ttu-id="2634d-609">Информация в этом документе, включая URL-адреса и другие ссылки на веб-сайты, может быть изменена без предварительного уведомления.</span><span class="sxs-lookup"><span data-stu-id="2634d-609">Information in this document, including URL and other Internet website references, is subject to change without notice.</span></span> <span data-ttu-id="2634d-610">Весь риск за использование или результаты использования этого документа сохраняется вместе с пользователем.</span><span class="sxs-lookup"><span data-stu-id="2634d-610">The entire risk of the use or the results from the use of this document remains with the user.</span></span> <span data-ttu-id="2634d-611">Если не указано иное, компании, Организации, товары, доменные имена, адреса электронной почты, логотипы, люди, места и события, показанные в приведенных ниже примерах, являются вымышленными.</span><span class="sxs-lookup"><span data-stu-id="2634d-611">Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious.</span></span> <span data-ttu-id="2634d-612">Никаких связей с реальными компаниями, организациями, продуктами, доменными именами, адресами электронной почты, логотипами, лицами, местами и событиями является случайным образом.</span><span class="sxs-lookup"><span data-stu-id="2634d-612">No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred.</span></span> <span data-ttu-id="2634d-613">Ответственность за соблюдение всех применимых законов об авторском праве лежит на пользователе.</span><span class="sxs-lookup"><span data-stu-id="2634d-613">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="2634d-614">Без ограничения прав, описанных в разделе "авторские права", никакие части этого документа нельзя воспроизводить, хранить или вносить в систему поиска, а также передавать в любой форме или любым способом (электронным, механической, фотонабором, записью или иным способом) или в любых целях. без специального письменного разрешения корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2634d-614">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="2634d-615">Корпорация Майкрософт может иметь патенты, патентные приложения, торговые марки, авторские права и другие права на интеллектуальную собственность, касающиеся темы в этом документе.</span><span class="sxs-lookup"><span data-stu-id="2634d-615">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document.</span></span> <span data-ttu-id="2634d-616">За исключением случаев, явно оговоренных в письменных лицензионных соглашениях от корпорации Майкрософт, предоставление этого документа не дает вам лицензии на эти патенты, товарные знаки, авторские права и другую интеллектуальную собственность.</span><span class="sxs-lookup"><span data-stu-id="2634d-616">Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="2634d-617">© 2012 Корпорация Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2634d-617">© 2012 Microsoft Corporation.</span></span> <span data-ttu-id="2634d-618">Все права защищены.</span><span class="sxs-lookup"><span data-stu-id="2634d-618">All rights reserved.</span></span>

<span data-ttu-id="2634d-619">Microsoft, Windows, Windows Live, Internet Explorer, MSN, Outlook и SQL Server — охраняемые товарные знаки или охраняемые товарные знаки Microsoft Corporation в США и/или других странах или регионах.</span><span class="sxs-lookup"><span data-stu-id="2634d-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="2634d-620">Все прочие товарные знаки являются собственностью соответствующих владельцев.</span><span class="sxs-lookup"><span data-stu-id="2634d-620">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

