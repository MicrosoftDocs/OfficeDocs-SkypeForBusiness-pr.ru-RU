---
title: Заметки о выпуске Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc7339b4861fe6e7e93e08d4928f6128916aeea0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="feee7-102">Заметки о выпуске для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="feee7-102">Release notes for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="feee7-103">_**Последнее изменение темы:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="feee7-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="feee7-104">Добро пожаловать в заметки о выпуске Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feee7-104">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="feee7-105">Обратитесь к этому файлу для получения сведений об известных проблемах, связанных с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feee7-105">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="feee7-106">Описание документа</span><span class="sxs-lookup"><span data-stu-id="feee7-106">About this document</span></span>

<span data-ttu-id="feee7-107">В этом документе содержатся важные сведения, которые необходимо знать перед развертыванием и использованием Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feee7-107">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="feee7-108">Дополнительные сведения о Lync Server 2013 можно найти в документации по [Microsoft Lync server 2013](microsoft-lync-server-2013.md) .</span><span class="sxs-lookup"><span data-stu-id="feee7-108">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="feee7-109">В этом документе имеются следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="feee7-109">This document contains the following sections:</span></span>

  - <span data-ttu-id="feee7-110">Клиент Lync 2013</span><span class="sxs-lookup"><span data-stu-id="feee7-110">Lync 2013 client</span></span>

  - <span data-ttu-id="feee7-111">Lync Server</span><span class="sxs-lookup"><span data-stu-id="feee7-111">Lync Server</span></span>

  - <span data-ttu-id="feee7-112">Установка</span><span class="sxs-lookup"><span data-stu-id="feee7-112">Installation</span></span>

  - <span data-ttu-id="feee7-113">Мобильность</span><span class="sxs-lookup"><span data-stu-id="feee7-113">Mobility</span></span>

  - <span data-ttu-id="feee7-114">Конференции</span><span class="sxs-lookup"><span data-stu-id="feee7-114">Conferencing</span></span>

  - <span data-ttu-id="feee7-115">Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="feee7-115">Enterprise Voice</span></span>

  - <span data-ttu-id="feee7-116">Присутствие</span><span class="sxs-lookup"><span data-stu-id="feee7-116">Presence</span></span>

  - <span data-ttu-id="feee7-117">Приложение группы ответа и приложение парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="feee7-117">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="feee7-118">Панель управления Lync Server, построитель топологий и средство планирования</span><span class="sxs-lookup"><span data-stu-id="feee7-118">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="feee7-119">Локализация</span><span class="sxs-lookup"><span data-stu-id="feee7-119">Localization</span></span>

  - <span data-ttu-id="feee7-120">Авторское право</span><span class="sxs-lookup"><span data-stu-id="feee7-120">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="feee7-121">Клиент Lync 2013</span><span class="sxs-lookup"><span data-stu-id="feee7-121">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="feee7-122">Передача файла в мгновенном сообщении завершается неудачей, если файл открыт в другом приложении</span><span class="sxs-lookup"><span data-stu-id="feee7-122">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="feee7-123">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-123">**Issue:**</span></span>

<span data-ttu-id="feee7-124">Если вы попытаетесь перенести файл (например, документ Word), включив его в мгновенное сообщение другому пользователю Lync, передача будет выполнена успешно, но на самом деле может не удаться передать файл.</span><span class="sxs-lookup"><span data-stu-id="feee7-124">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="feee7-125">В клиенте Lync будет отображаться значок для типа файлов, но он не может быть открыт предполагаемым получателем.</span><span class="sxs-lookup"><span data-stu-id="feee7-125">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="feee7-126">Сообщение об ошибке не отображается, чтобы сообщить о том, что передача не была выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="feee7-126">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="feee7-127">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-127">**Workaround:**</span></span>

<span data-ttu-id="feee7-128">Чтобы обойти эту проблему, закройте открытый файл или приложение, которые он открыл, прежде чем пытаться перенести файл в мгновенном сообщении.</span><span class="sxs-lookup"><span data-stu-id="feee7-128">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="feee7-129">Lync Server</span><span class="sxs-lookup"><span data-stu-id="feee7-129">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="feee7-130">Если не удается выполнить репликацию данных службы хранилища Lync Server, администраторам необходимо проверить счетчики производительности для устаревших элементов очереди службы хранения</span><span class="sxs-lookup"><span data-stu-id="feee7-130">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="feee7-131">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-131">**Issue:**</span></span>

<span data-ttu-id="feee7-132">Служба хранилища Lync Server использует Windows Fabric для репликации.</span><span class="sxs-lookup"><span data-stu-id="feee7-132">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="feee7-133">Если данные удаляются на основном сервере переднего плана, но удаление на дополнительном сервере переднего плана завершается с ошибкой (например, при неожиданном завершении работы или ошибке на сервере переднего плана), данные могут остаться и "потерянными".</span><span class="sxs-lookup"><span data-stu-id="feee7-133">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="feee7-134">Наличие потерянных данных может привести к резкому снижению производительности и неэффективному использованию дискового пространства.</span><span class="sxs-lookup"><span data-stu-id="feee7-134">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="feee7-135">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-135">**Workaround:**</span></span>

<span data-ttu-id="feee7-136">\_Чтобы обойти эту проблему, если события LYSS DB\_\_used\_Error (ID = 32058) и LYSS\_DB\_\_used used\_(ID = 32059) были созданы в журнале событий, администраторы должны проверить счетчик производительности на сервере переднего плана в разделе **Ls: LYSS-Storage Service API** , указав имя **LYSS-Current Number of устаревшие элементы очереди хранения**.</span><span class="sxs-lookup"><span data-stu-id="feee7-136">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="feee7-137">Если этот счетчик производительности имеет высокое значение (например, больше 50000), администратор должен запустить средство Клеануупсторажесервицедата. exe в наборе ресурсов Lync Server 2013, что приведет к удалению всех потерянных данных из пула.</span><span class="sxs-lookup"><span data-stu-id="feee7-137">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="feee7-138">Сведения о средстве можно найти в документации по набору ресурсов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feee7-138">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="feee7-139">При изменении конфигурации IP-адреса для сервера или пула необходимо перезапустить службы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="feee7-139">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="feee7-140">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-140">**Issue:**</span></span>

<span data-ttu-id="feee7-141">При изменении конфигурации IP-адреса для развертывания Lync Server 2013, например при переходе с IPv4 на сдвоенный стек или из двойного стека на IPv6, не все серверные компоненты выбирают изменение конфигурации до перезапуска служб.</span><span class="sxs-lookup"><span data-stu-id="feee7-141">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="feee7-142">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-142">**Workaround:**</span></span>

<span data-ttu-id="feee7-143">Чтобы обойти эту проблему, перезапустите службы Lync Server после изменения конфигурации IP-адреса для развертывания.</span><span class="sxs-lookup"><span data-stu-id="feee7-143">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="feee7-144">Для этого выполните в командной консоли Lync Server следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="feee7-144">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="feee7-145">Командлет искусственной транзакции конференц-связи с телефонным подключением больше недоступен в пакете управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="feee7-145">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="feee7-146">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-146">**Issue:**</span></span>

<span data-ttu-id="feee7-147">Командлет искусственной транзакции конференц-связи с телефонным подключением **Test-CsDialInConferencing** больше недоступен в пакете управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feee7-147">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="feee7-148">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-148">**Workaround:**</span></span>

<span data-ttu-id="feee7-149">Использование командлета искусственной транзакции конференц-связи с телефонным подключением **Test-CsDialInConferencing** поддерживается на предприятии только внутренним образом.</span><span class="sxs-lookup"><span data-stu-id="feee7-149">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="feee7-150">Администраторы могут продолжать использовать командлет в командной консоли Lync Server для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="feee7-150">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="feee7-151">Если требуется, предприятие может разработать частный пакет управления для внутреннего запуска командлета.</span><span class="sxs-lookup"><span data-stu-id="feee7-151">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="feee7-152">Служба централизованного ведения журналов остановлена, если сетевой трафик нарушается при копировании файлов журнала в сетевую папку</span><span class="sxs-lookup"><span data-stu-id="feee7-152">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="feee7-153">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-153">**Issue:**</span></span>

<span data-ttu-id="feee7-154">Когда служба централизованного ведения журналов настраивается для использования сетевого пути (значение параметра CacheFileNetworkFolder командлета **Get-CsClsConfiguration** представляет собой допустимый UNC-путь), кэшированные файлы журналов копируются в сетевую папку.</span><span class="sxs-lookup"><span data-stu-id="feee7-154">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="feee7-155">Если сетевой трафик прерывается, когда файлы журналов копируются в сетевую папку, возникает исключение, вызывающее остановку службы централизованного ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="feee7-155">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="feee7-156">Эта служба настроена таким образом, что ее автоматический перезапуск может выполняться до трех раз. Благодаря этому данная служба будет восстанавливаться после возникновения первых трех исключений.</span><span class="sxs-lookup"><span data-stu-id="feee7-156">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="feee7-157">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-157">**Workaround:**</span></span>

<span data-ttu-id="feee7-158">Способа решения этой проблемы не существует.</span><span class="sxs-lookup"><span data-stu-id="feee7-158">There is no workaround for this issue.</span></span> <span data-ttu-id="feee7-159">Чтобы определить эту ошибку, отслеживайте журнал событий для события с ИДЕНТИФИКАТОРом 7031 из "диспетчера управления службами", которые записываются в журнал при неожиданном завершении работы службы "централизованное ведение журнала" Lync Server.</span><span class="sxs-lookup"><span data-stu-id="feee7-159">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="feee7-160">Если это произойдет более трех раз, вручную перезапустите данную службу с помощью командлета **Start-CsWindowService**.</span><span class="sxs-lookup"><span data-stu-id="feee7-160">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="feee7-161">Необходимо импортировать элементы очереди службы хранилища вручную</span><span class="sxs-lookup"><span data-stu-id="feee7-161">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="feee7-162">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-162">**Issue:**</span></span>

<span data-ttu-id="feee7-163">В Lync Server 2013 хранятся данные о конференциях и обмене мгновенными сообщениями, такие как архивные сообщения и регистрация вызовов (CDR), в базе данных на каждом сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="feee7-163">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="feee7-164">Данные хранятся в базе данных, пока она обрабатывается до доставки в нужное место назначения.</span><span class="sxs-lookup"><span data-stu-id="feee7-164">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="feee7-165">Чтобы увеличить производительность, Lync Server 2013 периодически экспортирует элементы очереди из локальной базы данных, которые не обрабатываются в течение длительного периода времени, и сохраняет их в хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="feee7-165">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="feee7-166">Если хранилище файлов недоступно, элементы хранятся на каждом сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="feee7-166">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="feee7-167">Данная операция выполняется также, чтобы предотвратить потерю данных во время отработки отказа пула.</span><span class="sxs-lookup"><span data-stu-id="feee7-167">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="feee7-168">Во время операции экспорта служба хранилища Lync Server записывает все этапы в журнале событий с идентификаторами 32075 (выполняется полная очистка), 32076 (полная очистка завершается), 32082 (запускается сброс уровня обслуживания), 32083 (сброс уровня обслуживания завершено), 32089 (произошла очистка из-за заполнения базы данных).</span><span class="sxs-lookup"><span data-stu-id="feee7-168">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="feee7-169">Эти данные не будут автоматически импортированы в систему для обработки и доставки в конечный сервер (SQL Server или Exchange Server).</span><span class="sxs-lookup"><span data-stu-id="feee7-169">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="feee7-170">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-170">**Workaround:**</span></span>

<span data-ttu-id="feee7-171">Чтобы импортировать данные в систему, администраторам потребуется использовать средство Импортсторажесервицедата в наборе ресурсов Lync Server, который будет добавлять данные обратно в систему для обработки и доставки в конечный объект.</span><span class="sxs-lookup"><span data-stu-id="feee7-171">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="feee7-172">Поиск в веб-книге не выполняется, если значение по умолчанию для UseNormalizationRules изменяется на "false"</span><span class="sxs-lookup"><span data-stu-id="feee7-172">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="feee7-173">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-173">**Issue:**</span></span>

<span data-ttu-id="feee7-p112">Если значение по умолчанию для UseNormalizationRules изменяется на False, процедуры поиска, выполняемого с помощью веб-запроса к адресной книге, будут давать сбой. После изменения значения по умолчанию пользователи клиента Lync не смогут использовать веб-запрос к адресной книге Lync для поиска пользователей.</span><span class="sxs-lookup"><span data-stu-id="feee7-p112">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail. After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="feee7-176">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-176">**Workaround:**</span></span>

<span data-ttu-id="feee7-177">Если для UseNormalizationRules задано значение false, чтобы пользователи могли использовать номера телефонов в соответствии с определением в доменных службах Active Directory без Lync Server 2013 применение правил нормализации, обойти эту проблему, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="feee7-177">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="feee7-178">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="feee7-178">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="feee7-179">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="feee7-179">Do one of the following:</span></span>
    
      - <span data-ttu-id="feee7-180">Если в развертывании есть только серверы Lync Server 2013, выполните следующий командлет на глобальном уровне, чтобы изменить значения для UseNormalizationRules и IgnoreGenericRules на true:</span><span class="sxs-lookup"><span data-stu-id="feee7-180">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="feee7-181">Если в развертывании имеется сочетание Lync Server 2013 и Lync Server 2010 или Office Communications Server 2007 R2, выполните следующий командлет и назначьте его каждому пулу Lync Server 2013 в топологии:</span><span class="sxs-lookup"><span data-stu-id="feee7-181">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="feee7-182">Подождите, пока репликация CMS не будет выполнена для всех пулов.</span><span class="sxs-lookup"><span data-stu-id="feee7-182">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="feee7-183">Измените файл правил нормализации телефона для развертывания, чтобы очистить соответствующее содержимое.</span><span class="sxs-lookup"><span data-stu-id="feee7-183">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="feee7-184">Файл находится на общем файловом ресурсе каждого пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feee7-184">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="feee7-185">Если файл отсутствует, создайте пустой файл\_с именем "\_\_\_Rules нормализации телефонных номеров компаний. txt".</span><span class="sxs-lookup"><span data-stu-id="feee7-185">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="feee7-186">Подождите несколько минут, пока для всех интерфейсных пулов не будут прочитаны новые файлы.</span><span class="sxs-lookup"><span data-stu-id="feee7-186">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="feee7-187">Выполните следующий командлет на каждом пуле Lync Server 2013 в развертывании.</span><span class="sxs-lookup"><span data-stu-id="feee7-187">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="feee7-188">Событие ошибки сервера адресной книги 21054 формируется ежедневно для каждого пула Lync 2013</span><span class="sxs-lookup"><span data-stu-id="feee7-188">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="feee7-189">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-189">**Issue:**</span></span>

<span data-ttu-id="feee7-190">Lync Server 2013. сервер адресной книги будет создавать событие ошибки 21054 раз в день при ежедневном обслуживании.</span><span class="sxs-lookup"><span data-stu-id="feee7-190">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="feee7-191">Эта ошибка также создается каждый раз, когда администратор запускает командлет **Update-csAddressBook** , даже если обновление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="feee7-191">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="feee7-192">Тем не менее, это событие ошибки можно игнорировать при успешном завершении обновления.</span><span class="sxs-lookup"><span data-stu-id="feee7-192">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="feee7-193">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-193">**Workaround:**</span></span>

<span data-ttu-id="feee7-194">При возникновении этой ошибки запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="feee7-194">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="feee7-195">Если командлет сообщает о том, что нет неиндексированных или отброшенных объектов, событие ошибки 21054 можно спокойно игнорировать.</span><span class="sxs-lookup"><span data-stu-id="feee7-195">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="feee7-196">Кроме того, следует отключить ключевой индикатор работоспособности (KHI) "Address Book Users Correctly Indexed" (Пользователи адресной книги проиндексированы правильно) в System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="feee7-196">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="feee7-197">При настройке IPv6 в пограничном пуле могут возникать сбои запросов</span><span class="sxs-lookup"><span data-stu-id="feee7-197">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="feee7-198">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-198">**Issue:**</span></span>

<span data-ttu-id="feee7-199">Когда IPv6 настроен для пограничного пула, некоторые запросы к пограничному пулу могут завершиться с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="feee7-199">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="feee7-200">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-200">**Workaround:**</span></span>

<span data-ttu-id="feee7-201">Чтобы решить эту проблему, не следует настраивать пограничный пул с IPv6.</span><span class="sxs-lookup"><span data-stu-id="feee7-201">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="feee7-202">Во время восстановления размещения пула может произойти сбой командлета Invoke – csPoolFailback</span><span class="sxs-lookup"><span data-stu-id="feee7-202">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="feee7-203">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-203">**Issue:**</span></span>

<span data-ttu-id="feee7-204">Командлет **invoke-csPoolFailback** может при попытке восстановления размещения пула завершиться с ошибкой, "Несколько попыток выполнить расконсервацию завершились неудачно".</span><span class="sxs-lookup"><span data-stu-id="feee7-204">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="feee7-205">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-205">**Workaround:**</span></span>

<span data-ttu-id="feee7-p115">Чтобы решить эту проблему, запустите командлет еще раз и дождитесь успешного завершения его работы. Обратите внимание, что процесс восстановления размещения может занять несколько минут — до 60 минут для пула, включающего 20 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="feee7-p115">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds. Note that the failback process can take several minutes to complete. It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="feee7-209">При добавлении сервера переднего плана в уже установленный пул могут возникать потери данных: Гибридная среда Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="feee7-209">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="feee7-210">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-210">**Issue:**</span></span>

<span data-ttu-id="feee7-211">Эта проблема может возникнуть в среде с несколькими серверами переднего плана, а также при перезапуске одного из серверов переднего плана или при добавлении нового сервера переднего плана, который ранее не был частью пула.</span><span class="sxs-lookup"><span data-stu-id="feee7-211">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="feee7-p116">Пользователи, чьи данные архивируются, могут столкнуться с потерей данных, пока для пула не будет установлено стабильное распределение архивируемых данных. Такой период возможной потери данных ограничивается 15 минутами для бесед двух лиц и 30 минутами для конференций.</span><span class="sxs-lookup"><span data-stu-id="feee7-p116">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool. This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="feee7-214">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-214">**Workaround:**</span></span>

<span data-ttu-id="feee7-215">При выполнении обслуживания вместо первого запуска серверов переднего плана в пуле необходимо отработка отказа пула в другом пуле, а затем выполнять задачи обслуживания на серверах.</span><span class="sxs-lookup"><span data-stu-id="feee7-215">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="feee7-216">Можно также перед выполнением задач обслуживания сделать службу недоступной, а затем после завершения этих задач восстановить доступность.</span><span class="sxs-lookup"><span data-stu-id="feee7-216">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="feee7-217">Администраторы не могут получить количество лицензий с помощью командлета Get – CsClientAccessLicense.</span><span class="sxs-lookup"><span data-stu-id="feee7-217">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="feee7-218">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-218">**Issue:**</span></span>

<span data-ttu-id="feee7-219">Администраторы не могут получить точное количество используемых клиентских лицензий с помощью командлета **Get-CsClientAccessLicense**.</span><span class="sxs-lookup"><span data-stu-id="feee7-219">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="feee7-220">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-220">**Workaround:**</span></span>

<span data-ttu-id="feee7-221">Чтобы проверить тип серверной лицензии, можно выполнить командлет **Get-CsService** для получения полных доменных имен всех баз данных.</span><span class="sxs-lookup"><span data-stu-id="feee7-221">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="feee7-222">Если полное доменное имя сервера переднего плана совпадает с полным доменным именем внутренней базы данных, лицензия является лицензией Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="feee7-222">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="feee7-223">В противном случае это лицензия Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="feee7-223">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="feee7-224">Счетчик клиентских лицензий не сообщается точно</span><span class="sxs-lookup"><span data-stu-id="feee7-224">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="feee7-225">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-225">**Issue:**</span></span>

<span data-ttu-id="feee7-226">При определении количества клиентских лицензий могут возникнуть следующие обстоятельства.</span><span class="sxs-lookup"><span data-stu-id="feee7-226">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="feee7-227">**Неточное количество лицензий для пользователей мобильных устройств**</span><span class="sxs-lookup"><span data-stu-id="feee7-227">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="feee7-p119">Количество лицензий определяется количеством уникальных IP-адресов для пользователей устройств. Количество лицензий будет ограничиваться следующими способами.</span><span class="sxs-lookup"><span data-stu-id="feee7-p119">The license count is based on the number of unique IP addresses for device-based users. The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="feee7-230">Количество лицензий будет переоценено, если IP-адрес пользователя во время сеанса Lync изменяется.</span><span class="sxs-lookup"><span data-stu-id="feee7-230">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="feee7-231">Это может произойти, если пользователь подключается к Lync Server из нескольких расположений с настольным клиентом.</span><span class="sxs-lookup"><span data-stu-id="feee7-231">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="feee7-232">Количество лицензий будет недооценено, если пользователь подключается с помощью мобильного клиента, поскольку IP-адрес устройства определить невозможно.</span><span class="sxs-lookup"><span data-stu-id="feee7-232">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="feee7-233">**Количество лицензий удваивается при вызовах клиента Lync из телефонной сети общего пользования
(ТСОП), звонках клиента Lync на линии ТСОП и звонках Lync, переадресованных на линии ТСОП**</span><span class="sxs-lookup"><span data-stu-id="feee7-233">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="feee7-p121">В следующих сценариях будут учтены две дополнительные лицензии вместо одной, поскольку для определения количества используемых лицензий учитывается как номер телефона, так и пользователь Lync. Чтобы получить точные данные о лицензиях, вручную удалите лицензии, созданные номером телефона.</span><span class="sxs-lookup"><span data-stu-id="feee7-p121">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used. To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="feee7-236">Телефонный звонок в Lync из ТСОП.</span><span class="sxs-lookup"><span data-stu-id="feee7-236">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="feee7-237">Звонок Lync на линию ТСОП.</span><span class="sxs-lookup"><span data-stu-id="feee7-237">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="feee7-p122">Звонок из ТСОП в Lync с последующей переадресацией этого звонка на линию ТСОП. Одна из линий ТСОП будет учтена.</span><span class="sxs-lookup"><span data-stu-id="feee7-p122">A PSTN call to Lync, and then Lync forwards the call to a PSTN line. One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="feee7-240">**При входе с телефона Lync лицензия не будет учтена**</span><span class="sxs-lookup"><span data-stu-id="feee7-240">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="feee7-241">Если пользователь использует сертифицированный для Lync телефон, выполняет вход с этого телефона и телефон остается подключенным, что сохраняет состояние входа, то при запросе количества лицензий после входа с телефона он не будет учтен как использующий лицензию.</span><span class="sxs-lookup"><span data-stu-id="feee7-241">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="feee7-242">**Подсчет лицензий для телефонов ТСОП, присоединяющихся к конференциям**</span><span class="sxs-lookup"><span data-stu-id="feee7-242">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="feee7-p123">Если пользователи присоединяются к конференции с помощью телефона ТСОП, количество лицензий для присоединения к конференции будет подсчитано неточно. Однако для присоединения к конференции с использованием телефона ТСОП лицензия не требуется.</span><span class="sxs-lookup"><span data-stu-id="feee7-p123">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference. However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="feee7-245">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-245">**Workaround:**</span></span>

1.  <span data-ttu-id="feee7-246">**Неточное количество лицензий для пользователей мобильных устройств**</span><span class="sxs-lookup"><span data-stu-id="feee7-246">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="feee7-247">Можно вручную определить IP-адреса, которые относятся к одному и тому же устройству, а затем удалить лишние из числа лицензий.</span><span class="sxs-lookup"><span data-stu-id="feee7-247">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="feee7-248">Для мобильных устройств, подключающихся с помощью клиента Lync, способа решения этой проблемы не существует.</span><span class="sxs-lookup"><span data-stu-id="feee7-248">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="feee7-249">**Количество лицензий удваивается при вызовах клиента Lync из ТСОП, звонках клиента Lync на линии ТСОП и звонках Lync, переадресованных на линии ТСОП**</span><span class="sxs-lookup"><span data-stu-id="feee7-249">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="feee7-250">Потребуется вручную определить номера телефонов ТСОП и удалить количество лицензий, созданных этими номерами.</span><span class="sxs-lookup"><span data-stu-id="feee7-250">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="feee7-251">**При входе с телефона Lync лицензия не будет учтена**</span><span class="sxs-lookup"><span data-stu-id="feee7-251">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="feee7-252">Можно настроить телефон Lync таким образом, чтобы он с заданной периодичностью выходил из системы, а затем входил снова, например каждые 3 месяца.</span><span class="sxs-lookup"><span data-stu-id="feee7-252">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="feee7-253">**Подсчет лицензий для телефонов ТСОП, присоединяющихся к конференциям**</span><span class="sxs-lookup"><span data-stu-id="feee7-253">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="feee7-254">Можно вручную определить номер телефона ТСОП, который используется для присоединения к конференции, и удалить лицензию, созданную этим номером телефона.</span><span class="sxs-lookup"><span data-stu-id="feee7-254">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="feee7-255">После обновления до Silverlight 5 панель управления Lync Server перестает работать в среде VMware</span><span class="sxs-lookup"><span data-stu-id="feee7-255">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="feee7-256">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-256">**Issue:**</span></span>

<span data-ttu-id="feee7-257">Если вы используете панель управления Lync Server в среде VMware, панель управления Lync Server может перестать работать после обновления Microsoft Silverlight до версии 5.</span><span class="sxs-lookup"><span data-stu-id="feee7-257">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="feee7-258">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-258">**Workaround:**</span></span>

<span data-ttu-id="feee7-259">Чтобы устранить эту проблему, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="feee7-259">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="feee7-260">Удалите Silverlight 5 и установите Silverlight 4 с [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span><span class="sxs-lookup"><span data-stu-id="feee7-260">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="feee7-261">Доступ к панели управления Lync Server с компьютера, который не является виртуальным компьютером VMware.</span><span class="sxs-lookup"><span data-stu-id="feee7-261">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="feee7-262">Для этого можно запустить панель управления Lync Server в меню **Пуск** Windows на сервере, если на компьютере установлены средства администрирования Lync Server.</span><span class="sxs-lookup"><span data-stu-id="feee7-262">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="feee7-263">Вы также можете получить доступ к панели управления Lync Server с помощью веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="feee7-263">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="feee7-264">URL-адрес будет похож на полное\<доменное\_имя\>HTTPS://интерфейсного\_пула/КСКП.</span><span class="sxs-lookup"><span data-stu-id="feee7-264">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="feee7-265">Сведения о пользователях в службе адресной книги не обновляются после изменения различающегося имени пользователя в Active Directory</span><span class="sxs-lookup"><span data-stu-id="feee7-265">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="feee7-266">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-266">**Issue:**</span></span>

<span data-ttu-id="feee7-267">Если различающееся имя пользователя (DN) изменяется в доменных службах Active Directory, любые дополнительные изменения не будут обновлены в службе адресной книги (ABS).</span><span class="sxs-lookup"><span data-stu-id="feee7-267">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="feee7-268">Это не влияет на возможность входа или присутствие пользователя, однако будет препятствовать возможностям соединения пользователя, если адрес SIP также изменяется, поскольку поиск будет возвращать устаревший адрес SIP.</span><span class="sxs-lookup"><span data-stu-id="feee7-268">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="feee7-269">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-269">**Workaround:**</span></span>

<span data-ttu-id="feee7-p126">Чтобы решить эту проблему, не изменяйте различающееся имя пользователя. Если вернуть прежнее значение имени DN для пользователя, обновления будут отображаться в службе адресной книги.</span><span class="sxs-lookup"><span data-stu-id="feee7-p126">To work around this issue, do not change a user’s DN. If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="feee7-272">Установка</span><span class="sxs-lookup"><span data-stu-id="feee7-272">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="feee7-273">Использование символов, отличных от ASCII, может привести к сбою при запуске Lync Server</span><span class="sxs-lookup"><span data-stu-id="feee7-273">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="feee7-274">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-274">**Issue:**</span></span>

<span data-ttu-id="feee7-275">Если имя конечной папки содержит символы, не входящие в набор ASCII (включая Юникод, двухбайтовый набор знаков, UTF-8 и UTF-16), программа установки завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="feee7-275">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="feee7-276">Кроме того, программа установки может завершиться с ошибкой, но сервер не будет запускаться, если символы, не входящие в набор ASCII, входят в один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="feee7-276">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="feee7-277">Имя компьютера</span><span class="sxs-lookup"><span data-stu-id="feee7-277">Computer name</span></span>

  - <span data-ttu-id="feee7-278">Доменное имя</span><span class="sxs-lookup"><span data-stu-id="feee7-278">Domain name</span></span>

  - <span data-ttu-id="feee7-279">Имя пользователя</span><span class="sxs-lookup"><span data-stu-id="feee7-279">User name</span></span>

  - <span data-ttu-id="feee7-280">URI SIP пользователя</span><span class="sxs-lookup"><span data-stu-id="feee7-280">User SIP URI</span></span>

  - <span data-ttu-id="feee7-281">Имя учетной записи службы</span><span class="sxs-lookup"><span data-stu-id="feee7-281">Service account name</span></span>

<span data-ttu-id="feee7-282">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-282">**Workaround:**</span></span>

<span data-ttu-id="feee7-283">Используйте только символы ASCII в имени конечной папки, имени компьютера, имени домена, имени пользователя, URI SIP и имени учетной записи службы.</span><span class="sxs-lookup"><span data-stu-id="feee7-283">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="feee7-284">Исправление "повреждение кучи возникает, когда модуль вызывает метод InsertEntityBody Method в IIS 7,5", прежде чем устанавливать Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="feee7-284">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="feee7-285">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-285">**Issue:**</span></span>

<span data-ttu-id="feee7-286">Исправление "повреждение кучи возникает, когда модуль вызывает метод InsertEntityBody Method в IIS 7,5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), описанный в статье базы знаний Майкрософт 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), должен быть установлен перед установкой Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feee7-286">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="feee7-287">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-287">**Workaround:**</span></span>

<span data-ttu-id="feee7-288">Скачайте и установите исправление из центра загрузки Майкрософт по адресу [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span><span class="sxs-lookup"><span data-stu-id="feee7-288">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="feee7-289">Не удается установить Lync Server 2013 на сервере ITA Windows Server 2012 для ОС версии RTM</span><span class="sxs-lookup"><span data-stu-id="feee7-289">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="feee7-290">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-290">**Issue:**</span></span>

<span data-ttu-id="feee7-291">Сбой установки Lync Server 2013 на сервере ITA Windows Server 2012 из-за сбоя установки Windows Fabric.</span><span class="sxs-lookup"><span data-stu-id="feee7-291">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="feee7-p128">Не удалось выполнить установку Windows Fabric, поскольку трассировки Fabric создавались в формате времени ЧЧ:ММ:СС. Однако в системе ITA Windows Server формат времени имеет вид ЧЧ.ММ.СС.</span><span class="sxs-lookup"><span data-stu-id="feee7-p128">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS. However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="feee7-294">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-294">**Workaround:**</span></span>

<span data-ttu-id="feee7-295">Чтобы обойти эту проблему, обновите системный реестр перед установкой Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feee7-295">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="feee7-296">Раздел реестра, который необходимо обновить: HKEY\_пользователи.\\ Международная\\\\стимеформат панели\\управления по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="feee7-296">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="feee7-297">Измените значение параметра Стимеформат на чч: мм: СС с помощью интерфейса командной строки Windows PowerShell следующим образом:</span><span class="sxs-lookup"><span data-stu-id="feee7-297">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="feee7-298">Запустите Windows PowerShell и выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="feee7-298">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="feee7-299">Чтобы просмотреть текущее значение, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="feee7-299">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="feee7-300">Запомните текущее значение для sTimeFormat, чтобы его можно было восстановить после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="feee7-300">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="feee7-301">Чтобы задать новое значение, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="feee7-301">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="feee7-302">После успешной установки Lync Server 2013 восстановите исходное значение для Стимеформат, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="feee7-302">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="feee7-303">Set – ItemProperty $a – Name Стимеформат — value "<значение, указанное на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="feee7-303">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="feee7-304">над> "</span><span class="sxs-lookup"><span data-stu-id="feee7-304">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="feee7-305">Мобильность</span><span class="sxs-lookup"><span data-stu-id="feee7-305">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="feee7-306">Проблемы для мобильных клиентов в процессе отработки отказа сервера</span><span class="sxs-lookup"><span data-stu-id="feee7-306">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="feee7-307">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-307">**Issue:**</span></span>

<span data-ttu-id="feee7-308">При сбое сервера Lync и запуске процесса отработки отказа могут возникать следующие проблемы, связанные с мобильными клиентами:</span><span class="sxs-lookup"><span data-stu-id="feee7-308">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="feee7-309">Нет входящего звонка Lync или сигнала Lync в течение 10 минут после отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="feee7-309">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="feee7-310">Не удается принимать входящие запросы чата</span><span class="sxs-lookup"><span data-stu-id="feee7-310">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="feee7-311">Не удается присоединиться к собранию, если неисправной сервер является домашним сервером для пользователя</span><span class="sxs-lookup"><span data-stu-id="feee7-311">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="feee7-312">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-312">**Workaround:**</span></span>

<span data-ttu-id="feee7-313">Способа решения этой проблемы не существует.</span><span class="sxs-lookup"><span data-stu-id="feee7-313">There is no workaround for this issue.</span></span> <span data-ttu-id="feee7-314">После завершения отработки отказа будут восстановлены нормальные функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="feee7-314">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="feee7-315">Если пользователь мобильного устройства отклоняет входящий звонок от другой конечной точки Lync, вызов отображается как пропущенное преобразование на мобильных клиентах Lync</span><span class="sxs-lookup"><span data-stu-id="feee7-315">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="feee7-316">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-316">**Issue:**</span></span>

<span data-ttu-id="feee7-317">Если пользователь мобильного устройства отклоняет входящий вызов, а вызов, поступающий из другой конечной точки Lync, вызов отображается как пропущенная беседа в клиенте Lync Mobile, а не на вызов в списке вызовов устройств.</span><span class="sxs-lookup"><span data-stu-id="feee7-317">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="feee7-318">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-318">**Workaround:**</span></span>

<span data-ttu-id="feee7-319">Способа решения этой проблемы не существует.</span><span class="sxs-lookup"><span data-stu-id="feee7-319">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="feee7-320">Мобильный клиент может не отображать отображаемое имя федеративного контакта при поиске контактов</span><span class="sxs-lookup"><span data-stu-id="feee7-320">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="feee7-321">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-321">**Issue:**</span></span>

<span data-ttu-id="feee7-322">Отображаемое имя для федеративных контактов может не отображаться в некоторых сценариях, например при поиске федеративного контакта в списке контактов.</span><span class="sxs-lookup"><span data-stu-id="feee7-322">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="feee7-323">Это может произойти, если для контакта отсутствует активная подписка на присутствие из клиента Lync Mobile.</span><span class="sxs-lookup"><span data-stu-id="feee7-323">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="feee7-324">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-324">**Workaround:**</span></span>

<span data-ttu-id="feee7-325">Способа решения этой проблемы не существует.</span><span class="sxs-lookup"><span data-stu-id="feee7-325">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="feee7-326">В мобильном клиенте сведения о приглашении и отметке времени отсутствуют во пропущенной беседе, которая является приглашением на конференцию</span><span class="sxs-lookup"><span data-stu-id="feee7-326">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="feee7-327">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-327">**Issue:**</span></span>

<span data-ttu-id="feee7-328">В мобильном клиенте, когда пропущенная беседа является приглашением на конференцию, сведения о приглашении и временной метке отсутствуют в сообщении о пропущенной беседе.</span><span class="sxs-lookup"><span data-stu-id="feee7-328">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="feee7-329">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-329">**Workaround:**</span></span>

<span data-ttu-id="feee7-330">Способа решения этой проблемы не существует.</span><span class="sxs-lookup"><span data-stu-id="feee7-330">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="feee7-331">Пользователи мобильных клиентов, совершающие вызовы с помощью VoIP, не могут оставлять голосовую почту для пользователей, чьи голосовые сообщения настроены в Exchange 2010 или более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="feee7-331">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="feee7-332">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-332">**Issue:**</span></span>

<span data-ttu-id="feee7-333">Если пользователь мобильного клиента использует VoIP для вызова звонков, пользователь не сможет оставлять сообщения голосовой почты для пользователей, настроенных на использование голосовой почты в Microsoft Exchange Server 2007 или Microsoft Exchange Server 2010.</span><span class="sxs-lookup"><span data-stu-id="feee7-333">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="feee7-334">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-334">**Workaround:**</span></span>

<span data-ttu-id="feee7-335">Чтобы обойти эту проблему, используйте Exchange 2010 с пакетом обновления 1 (SP1) или более поздней версии Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="feee7-335">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="feee7-336">При использовании блока с URL-адресом для конфигурации версий клиентов в мобильных клиентах может отображаться неправильное сообщение об ошибке</span><span class="sxs-lookup"><span data-stu-id="feee7-336">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="feee7-337">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-337">**Issue:**</span></span>

<span data-ttu-id="feee7-338">При использовании **блока с URL-адресом** для конфигурации версии клиента на мобильных клиентах может отображаться неправильное сообщение об ошибке, если версия клиента не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="feee7-338">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="feee7-339">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-339">**Workaround:**</span></span>

<span data-ttu-id="feee7-340">Чтобы обойти эту проблему, настройте конфигурацию версии клиента так, чтобы она использовала **Block** , а не **Block с URL-адресом**.</span><span class="sxs-lookup"><span data-stu-id="feee7-340">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="feee7-341">Конференции</span><span class="sxs-lookup"><span data-stu-id="feee7-341">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="feee7-342">Антивирусное программное обеспечение, работающее на серверах переднего плана Lync Server 2013, может привести к повторному запуску домена приложений, который временно прерывает обслуживание для Lync Web App 2013, Lync Mobile 2010 и клиентов Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="feee7-342">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="feee7-343">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-343">**Issue:**</span></span>

<span data-ttu-id="feee7-344">Антивирусное программное обеспечение может инициировать перезагрузку доменов приложений, что может привести к потере их состояния клиентскими приложениями Lync Mobility Service 2013 и единой системы обмена сообщениями (UC) веб-API (Lync Web App 2013, Lync Mobile 2010 и Lync Mobile 2013).</span><span class="sxs-lookup"><span data-stu-id="feee7-344">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="feee7-345">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-345">**Workaround:**</span></span>

<span data-ttu-id="feee7-346">Чтобы решить эту проблему, исключите папки, содержащие веб-компоненты и платформу .NET, из антивирусной проверки.</span><span class="sxs-lookup"><span data-stu-id="feee7-346">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="feee7-347">Дополнительные сведения см. в статье 312592 базы знаний Майкрософт "ПРБ: перезапускать случайное приложение с ошибкой" приложение перезапускается "в ASP.NET," at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span><span class="sxs-lookup"><span data-stu-id="feee7-347">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="feee7-348">Следует исключить следующие папки:</span><span class="sxs-lookup"><span data-stu-id="feee7-348">The following folders should be excluded:</span></span>

  - <span data-ttu-id="feee7-349">% ProgramFiles%\\компонентов Microsoft Lync Server\\2013 Web\\Components MCX\\ext</span><span class="sxs-lookup"><span data-stu-id="feee7-349">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="feee7-350">% ProgramFiles%\\веб-компоненты\\\\Microsoft Lync Server 2013\\MCX int</span><span class="sxs-lookup"><span data-stu-id="feee7-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="feee7-351">% ProgramFiles%\\веб-компоненты\\\\Microsoft Lync Server 2013\\Ucwa int</span><span class="sxs-lookup"><span data-stu-id="feee7-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="feee7-352">% ProgramFiles%\\компонентов Microsoft Lync Server\\2013 Web\\Components Ucwa\\ext</span><span class="sxs-lookup"><span data-stu-id="feee7-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="feee7-353">% WINDIR%\\Microsoft.NET\\Framework64\\v 4.0.30319\\config</span><span class="sxs-lookup"><span data-stu-id="feee7-353">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="feee7-354">Для успешного присоединения к конференциям в Windows Internet Explorer необходимо включить элементы управления ActiveX или собственную поддержку XMLHTTP</span><span class="sxs-lookup"><span data-stu-id="feee7-354">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="feee7-355">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-355">**Issue:**</span></span>

<span data-ttu-id="feee7-356">Если пользователь отключил и элементы управления ActiveX Controls, и внутреннюю поддержку XMLHTTP в параметрах интернет-браузера Windows Internet Explorer, этот пользователь не сможет присоединиться к собранию, если в качестве браузера по умолчанию выбран Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="feee7-356">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="feee7-357">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-357">**Workaround:**</span></span>

<span data-ttu-id="feee7-358">Включите либо элементы ActiveX Controls, либо "внутреннюю поддержку XMLHTTP" в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="feee7-358">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="feee7-359">Служба веб-конференций Lync Server не может быть восстановлена из критического режима</span><span class="sxs-lookup"><span data-stu-id="feee7-359">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="feee7-360">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-360">**Issue:**</span></span>

<span data-ttu-id="feee7-p134">Если для архивации включен критический режим, то в случае системных сбоев будет включаться критический режим, и конференции перестанут работать для своих участников. После того как администратор исправит системный сбой (например, исправит проблему в базе данных), служба конференций с передачей данных не будет восстановлена автоматически, и администратор должен вручную запустить эту службу, чтобы возобновить конференции.</span><span class="sxs-lookup"><span data-stu-id="feee7-p134">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants. After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="feee7-363">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-363">**Workaround:**</span></span>

<span data-ttu-id="feee7-364">Администратор должен вручную перезапускать службу конференций после исправления сбоя системы.</span><span class="sxs-lookup"><span data-stu-id="feee7-364">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="feee7-365">Служба веб-конференций игнорирует прокси-сервер HTTP для внешних серверов Office Web App</span><span class="sxs-lookup"><span data-stu-id="feee7-365">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="feee7-366">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-366">**Issue:**</span></span>

<span data-ttu-id="feee7-367">Если сервер Office Web Apps является внешним по отношению к службе веб-конференций (то есть серверу, не подключенному к внутренней корпоративной сети) в Интернете, сети периметра, а службе веб-конференций требуется HTTP-прокси для подключения к этому серверу, то Обнаружение серверов Office Web Apps завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="feee7-367">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="feee7-368">Служба веб-конференций игнорирует параметр HTTP-прокси, как определено в построителе топологий для установки сервера Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="feee7-368">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="feee7-369">В результате клиент Lync не сможет использовать Microsoft PowerPoint 2010 совместно с другими участниками Конференции.</span><span class="sxs-lookup"><span data-stu-id="feee7-369">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="feee7-370">Если вы устанавливаете локальную среду Lync Server, а также настроили локальный сервер Office Web Apps во внутренней сети, Настройка прокси-сервера не требуется.</span><span class="sxs-lookup"><span data-stu-id="feee7-370">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="feee7-371">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-371">**Workaround:**</span></span>

<span data-ttu-id="feee7-372">Единственным обходным решением является отсутствие конфигурации развертывания, которая требует использования прокси-сервера HTTP для подключения к внешнему серверу Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="feee7-372">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="feee7-373">Добавление видео к Конференции поставщика голосовой конференц-связи не поддерживается</span><span class="sxs-lookup"><span data-stu-id="feee7-373">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="feee7-374">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-374">**Issue:**</span></span>

<span data-ttu-id="feee7-375">Добавление видео не поддерживается, если пользователь присоединяется к конференции поставщика услуг аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="feee7-375">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="feee7-376">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-376">**Workaround:**</span></span>

<span data-ttu-id="feee7-377">Способа решения этой проблемы не существует.</span><span class="sxs-lookup"><span data-stu-id="feee7-377">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="feee7-378">Топологии с включенной поддержкой IPv6 принудительное автоматическое обновление подключаемого модуля Lync Web App Silverlight для обеспечения возможности общего доступа к экрану с помощью Lync Web App</span><span class="sxs-lookup"><span data-stu-id="feee7-378">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="feee7-379">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-379">**Issue:**</span></span>

<span data-ttu-id="feee7-380">При настройке топологии с включенной поддержкой IPv6 пользователи не могут делиться экранами из клиента Lync Web App, если уже установлена более ранняя версия подключаемого модуля совместного использования экрана.</span><span class="sxs-lookup"><span data-stu-id="feee7-380">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="feee7-381">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-381">**Workaround:**</span></span>

<span data-ttu-id="feee7-382">Чтобы принудительно выполнить обновление до последней версии подключаемого модуля совместного использования экрана при присоединении к собранию с помощью Lync Web App, измените значение параметра **минсуппортедбуилдверсион** с "4.0.7457.0" на "4.0.7577.380" в обоих следующих файлах:</span><span class="sxs-lookup"><span data-stu-id="feee7-382">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="feee7-383">% ProgramFiles%\\веб-компоненты\\\\Microsoft Lync Server 15\\достигают\\клиентского\\подключаемых модулей\\реачаппшплугинпропертиес. XML</span><span class="sxs-lookup"><span data-stu-id="feee7-383">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="feee7-384">% ProgramFiles%\\веб-компоненты\\\\Microsoft Lync Server 15\\достигают расширения\\клиентского\\подключаемого\\модуля реачаппшплугинпропертиес. XML</span><span class="sxs-lookup"><span data-stu-id="feee7-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="feee7-385">Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="feee7-385">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="feee7-386">В некоторых случаях клиент Lync, работающий на компьютере с двумя стеками IPv4 и IPv6, может не поддерживать возможности, зависящие от IP-подсети компьютера, например E911, обхода сервера-посредника, контроля допуска звонков и маршрутизации на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="feee7-386">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="feee7-387">Сведения, приведенные в этом разделе, относятся к накопительным обновлениям для Lync Server 2013:2013 февраля.</span><span class="sxs-lookup"><span data-stu-id="feee7-387">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="feee7-388">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-388">**Issue:**</span></span>

<span data-ttu-id="feee7-389">Когда клиент Lync выполняется на компьютере, на котором размещается двойной стек IPv4 и IPv6 и на основе разрешения DNS прокси-сервера, клиент может использовать IPv6-адрес компьютера для входа.</span><span class="sxs-lookup"><span data-stu-id="feee7-389">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="feee7-390">После этого клиент Lync будет поддерживать только возможности, поддерживаемые для IPv6, которые исключают E911, обход сервера-посредника, контроль допуска звонков и маршрутизацию на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="feee7-390">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="feee7-391">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-391">**Workaround:**</span></span>

<span data-ttu-id="feee7-392">Чтобы обойти эту проблему, отключите поддержку протокола IPv6 на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="feee7-392">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="feee7-393">Если для пользователя не настроена Корпоративная голосовая связь, пользователю потребуется использовать формат E164 для исходящих звонков из конференции.</span><span class="sxs-lookup"><span data-stu-id="feee7-393">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="feee7-394">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-394">**Issue:**</span></span>

<span data-ttu-id="feee7-395">Если для пользователя не настроена Корпоративная голосовая связь, этот пользователь должен будет использовать формат E164 для успешного исходящих звонков из конференции.</span><span class="sxs-lookup"><span data-stu-id="feee7-395">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="feee7-396">Если формат E164 не применяется, пользователь не сможет выполнять звонки из конференции.</span><span class="sxs-lookup"><span data-stu-id="feee7-396">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="feee7-397">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-397">**Workaround:**</span></span>

<span data-ttu-id="feee7-398">Чтобы обойти эту проблему, пользователи, не поддерживающие корпоративную голосовую связь, должны звонить из конференции с использованием номеров в формате e164.</span><span class="sxs-lookup"><span data-stu-id="feee7-398">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="feee7-399">Присутствие</span><span class="sxs-lookup"><span data-stu-id="feee7-399">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="feee7-400">Если пользователь выбрал параметр "блокировать все приглашения и коммуникации", когда для пользователя включено единое хранилище контактов, состояние присутствия не отклоняется, если оно должно быть</span><span class="sxs-lookup"><span data-stu-id="feee7-400">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="feee7-401">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-401">**Issue:**</span></span>

<span data-ttu-id="feee7-402">Если пользователь выбрал параметр "Блокировать все приглашения и коммуникации", когда для этого пользователя включено единое хранилище контактов, состояние присутствия не отклоняется, хотя это и должно было делаться.</span><span class="sxs-lookup"><span data-stu-id="feee7-402">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="feee7-403">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-403">**Workaround:**</span></span>

<span data-ttu-id="feee7-p138">Чтобы решить эту проблему, для этого пользователя можно отключить единое хранилище контактов. Чтобы сделать это, выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="feee7-p138">To work around this issue, you can turn off the unified contact store for the user. To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="feee7-406">Пример:</span><span class="sxs-lookup"><span data-stu-id="feee7-406">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="feee7-407">Пользователи Office Communications Server 2007 R2, размещенные локально, не могут видеть состояние присутствия пользователей Skype для бизнеса Online в гибридных развертываниях — гибридная среда</span><span class="sxs-lookup"><span data-stu-id="feee7-407">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="feee7-408">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-408">**Issue:**</span></span>

<span data-ttu-id="feee7-409">Эта ошибка может возникнуть в гибридном развертывании, когда вы используете Lync Server 2013 Director.</span><span class="sxs-lookup"><span data-stu-id="feee7-409">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="feee7-410">Состояние присутствия для пользователей, размещенных в Skype для бизнеса Online, отображается как присутствие неизвестно для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="feee7-410">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="feee7-411">Кроме того, пользователи, размещенные в Skype для бизнеса Online, не могут видеть состояние присутствия для локальных пользователей Office Communications Server R2.</span><span class="sxs-lookup"><span data-stu-id="feee7-411">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="feee7-412">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-412">**Workaround:**</span></span>

<span data-ttu-id="feee7-413">Чтобы частично обойти эту проблему, измените домашний сервер (msRTCSIP-пресенцехомесервер) пользователей Skype для бизнеса Online так, чтобы он ссылался на локальный пул Lync Server 2013, а не в директорию Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feee7-413">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="feee7-414">Этот параметр можно изменить на локальном сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="feee7-414">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="feee7-415">Этот обходной путь будет правильно отображать состояние присутствия пользователей, размещенных в Office Communications Server 2007 R2 пользователям Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="feee7-415">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="feee7-416">Приложение группы ответа, приложение парковки вызовов и групповое раскладки вызовов</span><span class="sxs-lookup"><span data-stu-id="feee7-416">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="feee7-417">Во время установки звонка абоненту со стороны приема может слышаться одна секунда на удержание абонента</span><span class="sxs-lookup"><span data-stu-id="feee7-417">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="feee7-418">Сведения, приведенные в этом разделе, относятся к накопительным обновлениям для Lync Server 2013:2013 февраля.</span><span class="sxs-lookup"><span data-stu-id="feee7-418">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="feee7-419">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-419">**Issue:**</span></span>

<span data-ttu-id="feee7-420">При получении вызова с помощью группового ответа на звонки абоненту может слышаться одна секунда на удержание музыки во время установки вызова с стороной получения.</span><span class="sxs-lookup"><span data-stu-id="feee7-420">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="feee7-421">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-421">**Workaround:**</span></span>

<span data-ttu-id="feee7-422">Способа решения этой проблемы не существует.</span><span class="sxs-lookup"><span data-stu-id="feee7-422">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="feee7-423">Агент группы ответа может выполнить вход и выход с консоли агента Lync Server 2010 на Lync Server 2010 формальные группы агентов</span><span class="sxs-lookup"><span data-stu-id="feee7-423">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="feee7-424">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-424">**Issue:**</span></span>

<span data-ttu-id="feee7-425">Агент группы ответа Lync Server 2013 может выполнить вход и выход с помощью консоли агента Lync Server 2010 на Lync Server 2010 только в формальные группы агентов.</span><span class="sxs-lookup"><span data-stu-id="feee7-425">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="feee7-426">В консоли агента Lync Server 2010 пользователи могут видеть только группу ответа Lync Server 2010, к которой он принадлежит.</span><span class="sxs-lookup"><span data-stu-id="feee7-426">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="feee7-427">В них не отображаются группы ответа Lync Server 2013, к которым они относятся.</span><span class="sxs-lookup"><span data-stu-id="feee7-427">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="feee7-428">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-428">**Workaround:**</span></span>

<span data-ttu-id="feee7-429">Если агент группы ответа является пользователем Lync Server 2013 и частью группы формальных агентов Lync Server 2013, пользователь должен получить доступ к консоли агента Lync Server 2013 напрямую через веб-ссылку в браузере, чтобы войти в систему и выйти из групп агентов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feee7-429">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="feee7-430">Агент группы ответа Lync Server 2010 не может помещать вызовы от имени группы ответа Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="feee7-430">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="feee7-431">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-431">**Issue:**</span></span>

<span data-ttu-id="feee7-432">Пользователь Lync Server 2010, который является агентом группы ответа Lync Server 2013, не может выполнить вызов от имени группы ответа.</span><span class="sxs-lookup"><span data-stu-id="feee7-432">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="feee7-433">Группа ответа Lync Server 2013 не будет доступна в клиенте Lync для вызова.</span><span class="sxs-lookup"><span data-stu-id="feee7-433">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="feee7-434">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-434">**Workaround:**</span></span>

<span data-ttu-id="feee7-435">Чтобы обойти эту проблему, необходимо переместить пользователя Lync Server 2010 в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feee7-435">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="feee7-436">Удаление группы ответа из Lync Server 2010 после переноса на Lync Server 2013 не позволит группе ответа принимать входящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="feee7-436">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="feee7-437">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-437">**Issue:**</span></span>

<span data-ttu-id="feee7-438">Если группа ответа, которая была перенесена из Lync Server 2010 в Lync Server 2013, удалена из Lync Server 2010 через панель управления Lync Server или Командная консоль Lync Server, группа ответа в Lync Server 2013 перестанет принимать какие-либо входящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="feee7-438">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="feee7-439">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-439">**Workaround:**</span></span>

<span data-ttu-id="feee7-440">Чтобы обойти эту проблему, не удаляйте группы ответа из Lync Server 2010, перенесенные с Lync Server 2010 на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feee7-440">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="feee7-441">Если группа ответа уже удалена, ее следует повторно развернуть в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feee7-441">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="feee7-442">Если для нового управляемого рабочего процесса при создании задано значение "Неактивный", развертывание рабочего процесса завершится с ошибками</span><span class="sxs-lookup"><span data-stu-id="feee7-442">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="feee7-443">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-443">**Issue:**</span></span>

<span data-ttu-id="feee7-p143">Когда новый управляемый рабочий процесс указывается при его создании как неактивный, развертывание этого рабочего процесса завершится с ошибкой. Эта проблема возникает, когда рабочий процесс указывается при его создании как неактивный, но не оказывает влияния на рабочий процесс, который указывается как неактивный при его изменении после того, как он был уже развернут.</span><span class="sxs-lookup"><span data-stu-id="feee7-p143">When a new managed workflow is set to inactive when created, deployment of the workflow will fail. This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="feee7-446">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-446">**Workaround:**</span></span>

<span data-ttu-id="feee7-p144">При создании и развертывании рабочего процесса определите его как активный перед развертыванием. После успешного развертывания рабочего процесса его можно изменять и задавать как неактивный.</span><span class="sxs-lookup"><span data-stu-id="feee7-p144">When creating and deploying a workflow, set the workflow as active and then deploy it. After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="feee7-449">Удаление группы ответа из пула владельца не позволит группе ответа в резервном пуле принимать входящие вызовы во время отработки отказа, если группа ответа была импортирована в резервный пул</span><span class="sxs-lookup"><span data-stu-id="feee7-449">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="feee7-450">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-450">**Issue:**</span></span>

<span data-ttu-id="feee7-451">Если группа ответа, принадлежащая основному пулу, была импортирована в резервный пул без перезаписи владельца, а группа ответа удалена из пула владельца, группа ответа в резервном пуле не будет принимать какие-либо входящие вызовы во время отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="feee7-451">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="feee7-452">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-452">**Workaround:**</span></span>

<span data-ttu-id="feee7-453">Необходимо повторно развернуть группу ответа в основном пуле.</span><span class="sxs-lookup"><span data-stu-id="feee7-453">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="feee7-454">Затем необходимо экспортировать конфигурацию группы ответа из основного пула и снова импортировать ее в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="feee7-454">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="feee7-455">Вы также можете повторно создать группу ответа в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="feee7-455">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="feee7-456">В этом случае резервный пул будет пулом владельца группы ответа.</span><span class="sxs-lookup"><span data-stu-id="feee7-456">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="feee7-457">Приостановленный вызов не может быть получен из приложения парковки вызовов, если запрос на получение выполняется от имени группы ответа</span><span class="sxs-lookup"><span data-stu-id="feee7-457">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="feee7-458">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-458">**Issue:**</span></span>

<span data-ttu-id="feee7-459">При выполнении следующих условий запрос на получение приостановленного вызова завершается с ошибкой:</span><span class="sxs-lookup"><span data-stu-id="feee7-459">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="feee7-460">Агент является частью анонимной группы ответа.</span><span class="sxs-lookup"><span data-stu-id="feee7-460">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="feee7-461">Агент пытается получить приостановленный вызов из приложения парковки вызовов через анонимную группу ответа.</span><span class="sxs-lookup"><span data-stu-id="feee7-461">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="feee7-462">Агент пытается получить вызов, набирая номер орбиты вызовов через параметр "Звонок от имени" или через тот же параметр в клиенте Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="feee7-462">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="feee7-463">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-463">**Workaround:**</span></span>

<span data-ttu-id="feee7-464">Обходные пути для решения этой проблемы отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="feee7-464">There are no workarounds for this issue.</span></span> <span data-ttu-id="feee7-465">Приостановленный звонок должен быть получен без этого от имени группы ответа.</span><span class="sxs-lookup"><span data-stu-id="feee7-465">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="feee7-466">Панель управления Lync Server, Topology Builder и Planning Tool</span><span class="sxs-lookup"><span data-stu-id="feee7-466">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="feee7-467">Ограничения средств планирования</span><span class="sxs-lookup"><span data-stu-id="feee7-467">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="feee7-468">Сведения, приведенные в этом разделе, относятся к накопительным обновлениям для Lync Server 2013:2013 февраля.</span><span class="sxs-lookup"><span data-stu-id="feee7-468">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="feee7-469">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-469">**Issue:**</span></span>

<span data-ttu-id="feee7-470">При планировании развертывания средство планирования имеет следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="feee7-470">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="feee7-471">Поддерживается не более 10 центральных сайтов.</span><span class="sxs-lookup"><span data-stu-id="feee7-471">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="feee7-472">Каждый центральный сайт может иметь до 14 сайтов филиалов</span><span class="sxs-lookup"><span data-stu-id="feee7-472">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="feee7-473">Каждый центральный сайт может иметь не более 240 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="feee7-473">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="feee7-474">Кроме того, средство планирования не включает следующие значения при расчете рекомендуемой топологии:</span><span class="sxs-lookup"><span data-stu-id="feee7-474">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="feee7-475">Количество пользователей, размещенных в сети</span><span class="sxs-lookup"><span data-stu-id="feee7-475">The number of users that are homed online</span></span>

  - <span data-ttu-id="feee7-476">Процент пользователей, для которых включена Федерация XMPP</span><span class="sxs-lookup"><span data-stu-id="feee7-476">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="feee7-477">Процент пользователей, использующих Lync Web App</span><span class="sxs-lookup"><span data-stu-id="feee7-477">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="feee7-478">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-478">**Workaround:**</span></span>

<span data-ttu-id="feee7-479">Решения этих проблем не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="feee7-479">There is no workaround for these issues.</span></span> <span data-ttu-id="feee7-480">Более подробную информацию о средстве планирования можно узнать в статье [Разработка топологии для Lync Server 2013 с помощью средства планирования](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span><span class="sxs-lookup"><span data-stu-id="feee7-480">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="feee7-481">Средство планирования может не использовать ранее определенные IP-адреса для пограничной сети при обновлении параметров</span><span class="sxs-lookup"><span data-stu-id="feee7-481">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="feee7-482">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-482">**Issue:**</span></span>

<span data-ttu-id="feee7-483">После завершения создания проекта с помощью средства планирования при внесении изменений в параметры пограничной сети можно добавить в макет дополнительные IP-адреса, а не обновлять существующие IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="feee7-483">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="feee7-484">Это может произойти, если вы просматриваете сведения о схеме пограничной сети, выберите **пункт Щелкните здесь, чтобы обновить параметры**, а затем в диалоговом окне Параметры конфигурации выберите пункт пограничная сеть. Выберите **требуется ли использовать одни и те же полные доменные имена и IP-адреса, но разные порты для пограничных служб на пограничном сервере**.</span><span class="sxs-lookup"><span data-stu-id="feee7-484">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="feee7-485">Применение любых изменений может привести к добавлению новых IP-адресов и пограничных серверов в проект.</span><span class="sxs-lookup"><span data-stu-id="feee7-485">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="feee7-486">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-486">**Workaround:**</span></span>

<span data-ttu-id="feee7-487">В настоящее время решения этой проблемы не существует.</span><span class="sxs-lookup"><span data-stu-id="feee7-487">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="feee7-488">В панели управления Lync Server "перемещение всех пользователей в пул" может работать не так, как ожидалось</span><span class="sxs-lookup"><span data-stu-id="feee7-488">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="feee7-489">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-489">**Issue:**</span></span>

<span data-ttu-id="feee7-490">При использовании панели управления Lync Server для перемещения всех пользователей из одного пула в другой пул в сложной среде Active Directory (например, с несколькими контроллерами домена и родительскими и дочерними доменами) может возвращаться сообщение об ошибке "указанный пользователь не является устаревшим, используйте командлет Move-CsUser."</span><span class="sxs-lookup"><span data-stu-id="feee7-490">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="feee7-491">Это является результатом длительных операций репликации в сложных средах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="feee7-491">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="feee7-492">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-492">**Workaround:**</span></span>

<span data-ttu-id="feee7-493">Чтобы устранить эту проблему, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="feee7-493">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="feee7-494">Используйте фильтры в панели управления Lync Server для поиска устаревших пользователей, выберите этих пользователей, а затем с помощью **команды переместить выбранных пользователей в пул** вместо **перемещения всех пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="feee7-494">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="feee7-495">Используйте командную консоль Lync Server для перемещения устаревших пользователей в пакетах с помощью командлетов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="feee7-495">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="feee7-496">Панель управления Lync Server перестает работать в среде VMware после обновления подключаемого модуля Microsoft Silverlight Browser до версии 5</span><span class="sxs-lookup"><span data-stu-id="feee7-496">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="feee7-497">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-497">**Issue:**</span></span>

<span data-ttu-id="feee7-498">Если вы используете панель управления Lync Server в среде VMware, панель управления Lync Server может перестать работать после обновления Silverlight до версии 5.</span><span class="sxs-lookup"><span data-stu-id="feee7-498">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="feee7-499">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-499">**Workaround:**</span></span>

<span data-ttu-id="feee7-500">Чтобы устранить эту проблему, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="feee7-500">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="feee7-501">Удалите Silverlight 5, а затем установите Silverlight 4 с [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span><span class="sxs-lookup"><span data-stu-id="feee7-501">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="feee7-502">Откройте панель управления Lync Server на компьютере, который не является виртуальным компьютером VMware.</span><span class="sxs-lookup"><span data-stu-id="feee7-502">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="feee7-503">Чтобы открыть панель управления Lync Server на удаленном компьютере, установите средства администрирования Lync Server на компьютер, а затем откройте панель управления Lync Server в меню **Пуск** Windows.</span><span class="sxs-lookup"><span data-stu-id="feee7-503">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="feee7-504">Вы также можете открыть панель управления Lync Server, введя URL-адрес в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="feee7-504">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="feee7-505">URL-адрес будет похож на полное\<доменное\_имя\>HTTPS://интерфейсного\_пула/КСКП.</span><span class="sxs-lookup"><span data-stu-id="feee7-505">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="feee7-506">Администратор не может запустить командлет Uninstall – Ксмиррордб после удаления зеркальной базы данных в построителе топологий</span><span class="sxs-lookup"><span data-stu-id="feee7-506">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="feee7-507">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-507">**Issue:**</span></span>

<span data-ttu-id="feee7-508">Когда администратор отключает зеркальную базу данных в построителе топологий, а затем удаляет зеркальную базу данных в построителе топологий, в списке дел администратор может выполнить командлет **uninstall-csMirrorDatabase** для удаления зеркального отображения из SQL Server.</span><span class="sxs-lookup"><span data-stu-id="feee7-508">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="feee7-509">Когда администратор попытается запустить этот командлет, произойдет его сбой.</span><span class="sxs-lookup"><span data-stu-id="feee7-509">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="feee7-510">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-510">**Workaround:**</span></span>

<span data-ttu-id="feee7-511">Чтобы удалить зеркальное отображение SQL пула в построителе топологий, сначала необходимо использовать командлет для удаления зеркала в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="feee7-511">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="feee7-512">Затем вы можете использовать построитель топологий, чтобы удалить зеркало из топологии.</span><span class="sxs-lookup"><span data-stu-id="feee7-512">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="feee7-513">Чтобы сделать это в SQL Server, запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="feee7-513">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="feee7-514">Например, чтобы удалить зеркальное отображение и сбросить базы данных для баз данных пользователей, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="feee7-514">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="feee7-515">Параметр *DropExistingDatabasesOnMirror* осуществляет удаление указанных баз данных из зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="feee7-515">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="feee7-516">Затем чтобы удалить зеркало из топологии, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="feee7-516">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="feee7-517">В построителе топологии щелкните пул правой кнопкой мыши и щелкните **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="feee7-517">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="feee7-518">Снимите флажок **Включить зеркальное отображение хранилища SQL** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="feee7-518">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="feee7-519">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="feee7-519">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="feee7-520">При внесении изменений в отношения зеркального отображения серверных баз данных необходимо перезагрузить все серверы переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="feee7-520">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="feee7-521">Ошибки проверки возвращаются в построителе топологий, когда администратор пытается удалить развертывание с пулом переднего плана с соответствующим хранилищем-свидетелем</span><span class="sxs-lookup"><span data-stu-id="feee7-521">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="feee7-522">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-522">**Issue:**</span></span>

<span data-ttu-id="feee7-523">Если администратор пытается использовать команду **Remove Deployment** в построителе топологий для удаления развертывания, включающего пул переднего плана со связанным хранилищем-свидетелем, в построителе топологий отображается ошибка проверки, и действие не будет продолжено.</span><span class="sxs-lookup"><span data-stu-id="feee7-523">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="feee7-524">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-524">**Workaround:**</span></span>

<span data-ttu-id="feee7-525">Чтобы устранить эту проблему, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="feee7-525">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="feee7-526">Удалите следящее хранилище перед выполнением попытки удаления развертывания.</span><span class="sxs-lookup"><span data-stu-id="feee7-526">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="feee7-527">Добавьте следящее хранилище для интерфейсного пула, а затем удалите его.</span><span class="sxs-lookup"><span data-stu-id="feee7-527">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="feee7-528">Сведения о развертывании сервера сохраняемого чата несогласованны между средством планирования и построителем топологий</span><span class="sxs-lookup"><span data-stu-id="feee7-528">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="feee7-529">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-529">**Issue:**</span></span>

<span data-ttu-id="feee7-530">Когда Lync Server 2013, средство планирования выводит схему топологии сайта для развертывания сервера сохраняемого чата с включенным аварийным восстановлением, схема топологии сайта включает несколько (физических) сайтов с одинаковым назначенными серверами сохраняемого чата на каждом страницу.</span><span class="sxs-lookup"><span data-stu-id="feee7-530">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="feee7-531">В построителе топологий все серверы сохраняемого чата представлены как принадлежащие одному (логическому) сайту и перечислены в том же узле пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="feee7-531">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="feee7-532">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-532">**Workaround:**</span></span>

<span data-ttu-id="feee7-533">В настоящее время отсутствуют способы решения этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="feee7-533">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="feee7-534">Пользователь должен проанализировать выходные данные средства планирования для развертывания сервера сохраняемого чата и изменить план в соответствии с конкретными потребностями.</span><span class="sxs-lookup"><span data-stu-id="feee7-534">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="feee7-535">Локализация</span><span class="sxs-lookup"><span data-stu-id="feee7-535">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="feee7-536">Мониторинг</span><span class="sxs-lookup"><span data-stu-id="feee7-536">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="feee7-537">Мастер развертывания отчетов мониторинга при определенных обстоятельствах отображает неправильные знаки при использовании восточно-азиатской версии Lync Server</span><span class="sxs-lookup"><span data-stu-id="feee7-537">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="feee7-538">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-538">**Issue:**</span></span>

<span data-ttu-id="feee7-539">При использовании восточно-азиатской версии Lync Server 2013, например, китайского (упрощенное письмо), китайского (традиционное письмо), японского или корейского языков, в операционной системе, в которой язык системы не установлен на восточно-азиатский язык, мастер развертывания отчетов мониторинга будет Отображение вопросительных знаков или других знаков вместо локализованных сообщений.</span><span class="sxs-lookup"><span data-stu-id="feee7-539">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="feee7-540">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-540">**Workaround:**</span></span>

<span data-ttu-id="feee7-541">Чтобы устранить эту ошибку, задайте для языкового стандарта операционной системы и Lync Server 2013 один и тот же язык, который будет правильно отображать все сообщения.</span><span class="sxs-lookup"><span data-stu-id="feee7-541">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="feee7-542">Панель управления сервера Lync</span><span class="sxs-lookup"><span data-stu-id="feee7-542">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="feee7-543">В некоторых случаях первый элемент в верхней панели навигации на странице панели управления Lync Server исчезает, когда щелкнуть последний элемент в верхней панели навигации.</span><span class="sxs-lookup"><span data-stu-id="feee7-543">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="feee7-544">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-544">**Issue:**</span></span>

<span data-ttu-id="feee7-545">Существует три известных случая, когда щелчок последнего элемента в верхней панели управления Lync Server приведет к исчезновению первого элемента в верхней панели навигации:</span><span class="sxs-lookup"><span data-stu-id="feee7-545">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="feee7-546">Во французской версии на странице "Féderation et accès externe" элемент "Stratégie d'accès externe" исчезает, когда выбирается элемент "Partenaires fédérés XMPP".</span><span class="sxs-lookup"><span data-stu-id="feee7-546">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="feee7-547">В немецкой версии на странице "Clients" элемент "Clientversionskonfiguration" исчезает, когда выбирается элемент "Pushbenachrichtigungskonfiguration".</span><span class="sxs-lookup"><span data-stu-id="feee7-547">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="feee7-548">В русской версии на странице "Конфигурация сети" элемент "Глобально" исчезает, когда выбирается элемент "Маршрут региона".</span><span class="sxs-lookup"><span data-stu-id="feee7-548">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="feee7-549">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-549">**Workaround:**</span></span>

<span data-ttu-id="feee7-550">Чтобы обойти эту проблему, обновите страницу в панели управления Lync Server в браузере.</span><span class="sxs-lookup"><span data-stu-id="feee7-550">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="feee7-551">Эта страница будет загружена в браузер с отображением всех элементов в верхней панели навигации.</span><span class="sxs-lookup"><span data-stu-id="feee7-551">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="feee7-552">Адресная книга</span><span class="sxs-lookup"><span data-stu-id="feee7-552">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="feee7-553">Индексирование в адресной книге работает не так, как ожидалось, на некоторых языках</span><span class="sxs-lookup"><span data-stu-id="feee7-553">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="feee7-554">Сведения, приведенные в этом разделе, относятся к накопительным обновлениям для Lync Server 2013:2013 февраля.</span><span class="sxs-lookup"><span data-stu-id="feee7-554">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="feee7-555">Если свойства пользователя содержат индексированное поле, и это поле содержит только те символы, которые не удается индексировать, то пользователь не будет отображаться в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="feee7-555">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="feee7-556">Следующие символы и языки не могут индексироваться:</span><span class="sxs-lookup"><span data-stu-id="feee7-556">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="feee7-557">Символы верхнего регистра, греческий и армянский</span><span class="sxs-lookup"><span data-stu-id="feee7-557">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="feee7-558">Символы с диакритическими знаками верхнего регистра</span><span class="sxs-lookup"><span data-stu-id="feee7-558">Upper-case accented characters</span></span>

  - <span data-ttu-id="feee7-559">тайский;</span><span class="sxs-lookup"><span data-stu-id="feee7-559">Thai</span></span>

  - <span data-ttu-id="feee7-560">Лаосский</span><span class="sxs-lookup"><span data-stu-id="feee7-560">Lao</span></span>

  - <span data-ttu-id="feee7-561">Мьянма</span><span class="sxs-lookup"><span data-stu-id="feee7-561">Myanmar</span></span>

  - <span data-ttu-id="feee7-562">Деванагари</span><span class="sxs-lookup"><span data-stu-id="feee7-562">Devanagari</span></span>

  - <span data-ttu-id="feee7-563">есиопик</span><span class="sxs-lookup"><span data-stu-id="feee7-563">Ethiopic</span></span>

  - <span data-ttu-id="feee7-564">Тибетский</span><span class="sxs-lookup"><span data-stu-id="feee7-564">Tibetan</span></span>

  - <span data-ttu-id="feee7-565">Бенгальский</span><span class="sxs-lookup"><span data-stu-id="feee7-565">Bengali</span></span>

  - <span data-ttu-id="feee7-566">Гуджарати</span><span class="sxs-lookup"><span data-stu-id="feee7-566">Gujarati</span></span>

  - <span data-ttu-id="feee7-567">Телугу</span><span class="sxs-lookup"><span data-stu-id="feee7-567">Telugu</span></span>

  - <span data-ttu-id="feee7-568">Все остальные индийские сценарии</span><span class="sxs-lookup"><span data-stu-id="feee7-568">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="feee7-569">Lync Web App, веб-планировщик и веб-компоненты</span><span class="sxs-lookup"><span data-stu-id="feee7-569">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="feee7-570">Откат языка для определенных языков в веб-планировщике Lync, подключения удаленного доступа, средства запуска присоединения, управления комнатой для сохраняемого чата и OCTab могут работать не так, как ожидалось</span><span class="sxs-lookup"><span data-stu-id="feee7-570">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="feee7-571">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-571">**Issue:**</span></span>

<span data-ttu-id="feee7-572">При выборе нейтрального языкового стандарта в веб-браузере (в Internet Explorer например, имя языка без дополнительной спецификации, например "Норвежский \[No\]"), вместо языкового стандарта, в котором задан язык, сценарий и языковой стандарт (например, " \[норвежский,\]букмол (Норвегия) без ключа") может привести к непредвиденному поведению отображения для определенных языков в веб-планировщике Lync, удаленном доступе, средстве запуска присоединения, управления комнатой чата и</span><span class="sxs-lookup"><span data-stu-id="feee7-572">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="feee7-573">Например, пользователи могут видеть страницу на английском языке при выборе одного из следующих языков:</span><span class="sxs-lookup"><span data-stu-id="feee7-573">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="feee7-574">Норвежский</span><span class="sxs-lookup"><span data-stu-id="feee7-574">Norwegian</span></span>

  - <span data-ttu-id="feee7-575">Португальский</span><span class="sxs-lookup"><span data-stu-id="feee7-575">Portuguese</span></span>

  - <span data-ttu-id="feee7-576">Сербский</span><span class="sxs-lookup"><span data-stu-id="feee7-576">Serbian</span></span>

<span data-ttu-id="feee7-577">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-577">**Workaround:**</span></span>

<span data-ttu-id="feee7-578">Если требуется выбрать язык с нейтральным языковым стандартом, всегда необходимо убедиться, что этот язык был добавлен с конкретным языковым стандартом (с кодом набора знаков и/или кодом страны) в качестве дополнительного языка в список предпочитаемых языков.</span><span class="sxs-lookup"><span data-stu-id="feee7-578">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="feee7-579">При использовании веб-планировщика Lync, подключения удаленного доступа, управления комнатой чата и OCTab в некоторых веб-браузерах предусмотрена ограниченная поддержка национальных настроек азербайджанский и узбекский.</span><span class="sxs-lookup"><span data-stu-id="feee7-579">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="feee7-580">Сведения, приведенные в этом разделе, относятся к накопительным обновлениям для Lync Server 2013:2013 февраля.</span><span class="sxs-lookup"><span data-stu-id="feee7-580">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="feee7-581">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-581">**Issue:**</span></span>

<span data-ttu-id="feee7-582">Если вы используете Internet Explorer 8 или Internet Explorer 9 и устанавливаете язык браузера в Азербайджанский (латиница) или узбекский (латиница), то страницы средства запуска и присоединения будут отображаться на английском языке или на предпочтительном языке в браузере.</span><span class="sxs-lookup"><span data-stu-id="feee7-582">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="feee7-583">При использовании браузеров Firefox или Chrome и настройке языка браузера на азербайджанский (латиница) или узбекский (латиница) веб-приложение Lync, веб-планировщик Lync и RGS OCTab будут отображаться на английском языке или на предпочтительном языке, установленном для браузера.</span><span class="sxs-lookup"><span data-stu-id="feee7-583">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="feee7-584">Язык узбекский (латиница) не поддерживается в браузере Safari.</span><span class="sxs-lookup"><span data-stu-id="feee7-584">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="feee7-585">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-585">**Workaround:**</span></span>

<span data-ttu-id="feee7-586">Решения этих проблем не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="feee7-586">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="feee7-587">Отсутствует стрелка раскрывающегося списка "присоединение к собранию" в румынский версия Lync Web App</span><span class="sxs-lookup"><span data-stu-id="feee7-587">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="feee7-588">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-588">**Issue:**</span></span>

<span data-ttu-id="feee7-589">Когда пользователь, использующий Румынский Web App, выполняет следующие действия, стрелка раскрывающегося списка не отображается в раскрывающемся списке **Присоединение к собранию** .</span><span class="sxs-lookup"><span data-stu-id="feee7-589">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="feee7-590">Выберите **Запомнить мои данные на этом компьютере** на вкладке **Общие**.</span><span class="sxs-lookup"><span data-stu-id="feee7-590">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="feee7-591">Выберите вкладку **Телефон**.</span><span class="sxs-lookup"><span data-stu-id="feee7-591">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="feee7-592">Щелкните раскрывающийся список **Присоединение к собранию**.</span><span class="sxs-lookup"><span data-stu-id="feee7-592">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="feee7-593">Пользователи не увидят стрелку, указывающую на то, что существует больше вариантов, чем **Lync Web App**по умолчанию, включая: **не присоединять звук** (в румынский, "ню SE асоЦиаžа La Component") и **новый номер**"(в румынский," нумăр НАУ ").</span><span class="sxs-lookup"><span data-stu-id="feee7-593">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="feee7-594">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-594">**Workaround:**</span></span>

<span data-ttu-id="feee7-595">Несмотря на то, что стрелка для этого раскрывающегося списка не отображается, пользователи все же могут выбирать дополнительные элементы в этом списке, щелкнув значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="feee7-595">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="feee7-596">При использовании турецкой версии веб-планировщика Lync невозможно сохранить собрание при использовании параметра "люди, которые я выберет" в разделе "кто является докладчиком"</span><span class="sxs-lookup"><span data-stu-id="feee7-596">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="feee7-597">**Позволя**</span><span class="sxs-lookup"><span data-stu-id="feee7-597">**Issue:**</span></span>

<span data-ttu-id="feee7-p159">При создании или изменении собрания в турецкой версии веб-планировщика Lync параметр "Выбранные пользователи " в разделе "Докладчик" не поддерживается. При выборе этого параметра собрание не удается сохранить. Вместо этого отображается ошибка, в которой указывается, что одного или нескольких человек нельзя сделать докладчиками.</span><span class="sxs-lookup"><span data-stu-id="feee7-p159">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported. When this option is selected, the meeting can't be saved. Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="feee7-601">**Временные**</span><span class="sxs-lookup"><span data-stu-id="feee7-601">**Workaround:**</span></span>

<span data-ttu-id="feee7-p160">Чтобы устранить эту проблему, можно воспользоваться параметром по умолчанию "Пользователи из организации" или любым другим вариантом выбора параметров, например "Только организатор" или "Все, включая сотрудников вне моей организации". Организатор может в дальнейшем, после присоединения людей к собранию, понижать или выдвигать их на соответствующие роли.</span><span class="sxs-lookup"><span data-stu-id="feee7-p160">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company." The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="feee7-604">Кроме того, пользователи, знающие другой язык, могут изменить язык в браузере, выбрав любой из 43 поддерживаемых языков, и попытаться воспользоваться параметром "Выбранные пользователи".</span><span class="sxs-lookup"><span data-stu-id="feee7-604">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="feee7-605">Авторское право</span><span class="sxs-lookup"><span data-stu-id="feee7-605">Copyright</span></span>

<span data-ttu-id="feee7-p161">Данный документ предназначен для предварительного выпуска программного продукта, который может значительно измениться до окончательного коммерческого выпуска, и представляет конфиденциальные и служебные сведения корпорации Майкрософт. Сведения, содержащиеся в этом документе, сообщаются на условиях соглашения о неразглашении, заключенного между получателем и корпорацией Майкрософт. Документ предоставляется исключительно в информационных целях, корпорация Майкрософт не дает в этом документе никаких гарантий, прямых или косвенных. Сведения этого документа, включая URL-адреса и другие ссылки на веб-сайты, могут изменяться без предварительного уведомления. Весь риск, связанный с использованием данного документа, несет пользователь. Если не указано иное, то все названия компаний, организаций, продуктов, доменные имена, адреса электронной почты, эмблемы, люди, места и события, описываемые в примерах, являются вымышленными. Все связи с реальными компаниями, организациями, продуктами, доменными именами, адресами электронной почты, эмблемами, людьми, местами или событиями являются случайными и непреднамеренными. Пользователь несет ответственность за соблюдение всех применимых законов об авторском праве. В соответствии с законом об авторских правах, никакая часть этого документа не может быть воспроизведена, сохранена или использована в системах поиска, или передана в любом виде, любыми средствами (электронными, механическими, с помощью фотокопирования, записи или другими способов) и в любых целях без письменного разрешения корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="feee7-p161">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation. It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft. This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document. Information in this document, including URL and other Internet website references, is subject to change without notice. The entire risk of the use or the results from the use of this document remains with the user. Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious. No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred. Complying with all applicable copyright laws is the responsibility of the user. Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="feee7-p162">Корпорации Майкрософт могут принадлежать патенты, патентные заявки, товарные знаки, авторские права или другие права интеллектуальной собственности, относящиеся к предмету данного документа. За исключением случаев, явно оговоренных в письменном лицензионном соглашении корпорации Майкрософт, предъявление этого документа не дает прав на эти патенты, товарные знаки, авторские права либо другие права на интеллектуальную собственность.</span><span class="sxs-lookup"><span data-stu-id="feee7-p162">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="feee7-p163">© Корпорация Майкрософт (Microsoft Corporation), 2012. Все права защищены.</span><span class="sxs-lookup"><span data-stu-id="feee7-p163">© 2012 Microsoft Corporation. All rights reserved.</span></span>

<span data-ttu-id="feee7-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook и SQL Server являются охраняемыми товарными знаками корпорации Майкрософт в США и в других странах и регионах.</span><span class="sxs-lookup"><span data-stu-id="feee7-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="feee7-620">Все прочие товарные знаки являются собственностью соответствующих владельцев.</span><span class="sxs-lookup"><span data-stu-id="feee7-620">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

