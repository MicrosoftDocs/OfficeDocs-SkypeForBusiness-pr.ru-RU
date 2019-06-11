---
title: 'Lync Server 2013: требования резервного копирования для отработки отказа в пуле ABC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7cdb228b0a748c830aa488e7b058bf8664360d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a><span data-ttu-id="e8e76-102">Требования для резервного копирования для отработки отказа в пуле ABC в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8e76-102">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8e76-103">_**Тема последнего изменения:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="e8e76-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="e8e76-104">Чтобы получить максимальную пользу от использования процедуры отработки отказа для ABC, необходимо выполнить определенные резервные копии до аварии и отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="e8e76-104">To get the maximum benefit from using the ABC pool failover procedure, you must perform certain backups before the disaster and failover happen:</span></span>

  - <span data-ttu-id="e8e76-105">Необходимо регулярно создавать резервные копии данных конфигурации службы сведений о расположениях (LIS) из пула A с помощью командлета **Export-кслисконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="e8e76-105">You must regularly back up the Location Information Service (LIS) configuration data from pool A by using the **Export-CsLISConfiguration** cmdlet.</span></span>
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - <span data-ttu-id="e8e76-106">Вы должны регулярно создавать резервные копии данных конфигурации группы ответа в пуле A с помощью командлета **Export-ксргсконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="e8e76-106">You must regularly back up the Response Group configuration data in pool A by using the **Export-CsRgsConfiguration** cmdlet.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <span data-ttu-id="e8e76-107">Как правило, мы рекомендуем выполнять ежедневные архивации, но если у вас много изменений, вам может понадобиться запланировать более частые резервные копии.</span><span class="sxs-lookup"><span data-stu-id="e8e76-107">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="e8e76-108">Объем данных, которые можно потерять в случае аварии, зависит от частоты резервных копий, а также от частоты и объема изменений.</span><span class="sxs-lookup"><span data-stu-id="e8e76-108">The amount of information that you can lose in the event of a disaster depends on the frequency of your backups, as well as on the frequency and volume of changes.</span></span>
    
    <span data-ttu-id="e8e76-109">Приложение группы ответа может хранить только один набор параметров уровня приложения для каждого пула.</span><span class="sxs-lookup"><span data-stu-id="e8e76-109">The Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="e8e76-110">Доступ к этим параметрам можно получить с помощью командлетов **Get-ксргсконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="e8e76-110">These settings can be accessed through the **Get-CsRgsConfiguration** cmdlets.</span></span> <span data-ttu-id="e8e76-111">Эти параметры включают в себя стандартную конфигурацию музыки с удержанием по умолчанию, звуковой файл по умолчанию для сохранения музыки, льготный период для агента по каналу звонков и конфигурацию контекста вызова.</span><span class="sxs-lookup"><span data-stu-id="e8e76-111">The settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ring-back grace period, and the call context configuration.</span></span> <span data-ttu-id="e8e76-112">Эти параметры можно передать из одного пула в другой через командлет **Import-ксргсконфигуратион** с помощью параметра **реплацеексистингсеттингс** , но эта операция переопределит все параметры уровня приложения в месте назначения. группу.</span><span class="sxs-lookup"><span data-stu-id="e8e76-112">These settings can be transferred from one pool to another through the **Import-CsRgsConfiguration** cmdlet by using the **ReplaceExistingSettings** parameter, but this operation will override any application-level settings in the destination pool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e8e76-113">В отдельном расположении Храните резервные копии всех исходных аудиофайлов, которые использовались для настройки приложения группы ответа (то есть каких-либо записей или файлов хранения музыки).</span><span class="sxs-lookup"><span data-stu-id="e8e76-113">In a separate location, keep a backup copy of all the original audio files that have been used to configure the Response Group application (that is, any recordings or music-on-hold files).</span></span>

    
    </div>
    
    <span data-ttu-id="e8e76-114">Если у вас есть настроенные на хранение музыкальные файлы, отправленные для приостановки звонков в пуле, вы должны сохранить их копию в другом расположении.</span><span class="sxs-lookup"><span data-stu-id="e8e76-114">If you have any customized music-on-hold files that have been uploaded for Call Park in a pool, you should keep a copy of these in another location.</span></span> <span data-ttu-id="e8e76-115">Эти файлы не заархивированы в рамках процесса аварийного восстановления Lync Server 2013, и они будут потеряны, если файлы, отправленные в пул, повреждены, повреждены или удалены.</span><span class="sxs-lookup"><span data-stu-id="e8e76-115">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e8e76-116">Приложение для парковки звонков может хранить только один набор параметров и один настроенный звуковой файл на хранение музыки на каждом пуле.</span><span class="sxs-lookup"><span data-stu-id="e8e76-116">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="e8e76-117">Доступ к этим параметрам можно получить с помощью командлета <STRONG>Get-кскпсконфигуратион</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="e8e76-117">These settings can be accessed through the <STRONG>Get-CsCpsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="e8e76-118">Так как механизм аварийного восстановления для приостановки вызова полагается на приложение парковки из пула резервных копий, параметры основного пула не записываются и не сохраняются при возникновении аварии.</span><span class="sxs-lookup"><span data-stu-id="e8e76-118">Because the disaster recovery mechanism for Call Park relies on the Call Park application of the backup pool, the settings of the primary pool are not backed up or preserved if a disaster occurs.</span></span> <span data-ttu-id="e8e76-119">Если в основном пуле теряется, эти параметры невозможно восстановить, а при развертывании нового пула для замены основного пула необходимо настроить параметры парковки звонков и любой настроенный звуковой файл на хранение музыки.</span><span class="sxs-lookup"><span data-stu-id="e8e76-119">If the primary pool is lost, these settings cannot be recovered, and when a new pool is deployed to replace the primary pool, the Call Park settings and any customized music-on-hold audio file would need to be reconfigured.</span></span>

    
    </div>

  - <span data-ttu-id="e8e76-120">Если вы настроили объявления в рамках функции "неназначенные звонки", мы рекомендуем вам сохранить копию исходного звукового файла, используемого при первоначальной настройке, в другом месте.</span><span class="sxs-lookup"><span data-stu-id="e8e76-120">If you configure any announcements as part of the Unassigned Number Voice Feature, we recommend that you keep in another location a copy of any original audio file used during the initial configuration.</span></span> <span data-ttu-id="e8e76-121">Если это не было сделано, вы можете получить копии настроенных аудиофайлов в хранилище файлов на сервере или в пуле, куда были импортированы звуковые файлы.</span><span class="sxs-lookup"><span data-stu-id="e8e76-121">If you did not do that, you can get a copy of the configured audio files in the file store of the server or pool to which the audio files were imported.</span></span> <span data-ttu-id="e8e76-122">Эти файлы не заархивированы в рамках процесса аварийного восстановления Lync Server 2013, и они будут потеряны, если файлы, отправленные в пул, повреждены, повреждены или удалены.</span><span class="sxs-lookup"><span data-stu-id="e8e76-122">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="e8e76-123">Чтобы скопировать все аудиофайлы, которые использовались для настройки функции голосовой связи "неназначенный номер" из хранилища файлов сервера или пула, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e8e76-123">To copy all the audio files used to configure the Unassigned Number Voice Feature from the file store of a server or a pool, use:</span></span>
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - <span data-ttu-id="e8e76-124">Если у вас есть мониторинг и Архивация баз данных в пуле, вы должны использовать средства управления SQL Server для их резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="e8e76-124">If you have Monitoring and Archiving databases in a pool, you should use SQL Server management tools to back them up.</span></span> <span data-ttu-id="e8e76-125">В процедуре ABC для отработки отказа базы данных мониторинга и архивация не сохраняются, если они выровнены в пуле A, так как они не заархивированы в службе архивации данных Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8e76-125">In the ABC failover procedure, Monitoring and Archiving databases are not preserved if they are collocated in pool A, because these databases are not backed up through Lync Server Backup Service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

