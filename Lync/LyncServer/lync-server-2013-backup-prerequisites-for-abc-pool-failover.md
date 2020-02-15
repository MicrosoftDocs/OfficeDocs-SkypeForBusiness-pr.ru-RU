---
title: 'Lync Server 2013: необходимые условия резервного копирования для отработки отказа для пула ABC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9b609a9867b9ca0e6a01f0ced38445ae55c7367
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a><span data-ttu-id="1d711-102">Необходимые условия резервного копирования для отработки отказа для пула ABC в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d711-102">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d711-103">_**Последнее изменение темы:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="1d711-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="1d711-104">Для получения максимальной выгоды от использования процедуры отработки отказа для пула ABC необходимо выполнить определенные резервные копии до аварии и отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="1d711-104">To get the maximum benefit from using the ABC pool failover procedure, you must perform certain backups before the disaster and failover happen:</span></span>

  - <span data-ttu-id="1d711-105">Необходимо регулярно выполнять резервное копирование данных конфигурации службы сведений о местоположении (LIS) из пула A с помощью командлета **Export-CsLISConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1d711-105">You must regularly back up the Location Information Service (LIS) configuration data from pool A by using the **Export-CsLISConfiguration** cmdlet.</span></span>
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - <span data-ttu-id="1d711-106">Необходимо регулярно выполнять резервное копирование данных конфигурации группы ответа в пуле A с помощью командлета **Export – CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1d711-106">You must regularly back up the Response Group configuration data in pool A by using the **Export-CsRgsConfiguration** cmdlet.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <span data-ttu-id="1d711-107">Как правило, рекомендуется выполнять ежедневное резервное копирование, но если у вас большой объем изменений, можно запланировать более частые резервные копии.</span><span class="sxs-lookup"><span data-stu-id="1d711-107">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="1d711-108">Объем данных, которые можно потерять в случае аварии, зависит от частоты резервного копирования, а также от частоты и объема изменений.</span><span class="sxs-lookup"><span data-stu-id="1d711-108">The amount of information that you can lose in the event of a disaster depends on the frequency of your backups, as well as on the frequency and volume of changes.</span></span>
    
    <span data-ttu-id="1d711-109">Приложение группы ответа может хранить только один набор параметров уровня приложения для каждого пула.</span><span class="sxs-lookup"><span data-stu-id="1d711-109">The Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="1d711-110">Доступ к этим параметрам можно получить с помощью командлетов **Get – CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1d711-110">These settings can be accessed through the **Get-CsRgsConfiguration** cmdlets.</span></span> <span data-ttu-id="1d711-111">Эти параметры включают стандартную конфигурацию хранения музыки, используемую по умолчанию для музыкальных файлов по умолчанию, льготный период для агента при обратной связи и настройки контекста вызовов.</span><span class="sxs-lookup"><span data-stu-id="1d711-111">The settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ring-back grace period, and the call context configuration.</span></span> <span data-ttu-id="1d711-112">Эти параметры можно перенести из одного пула в другой с помощью командлета **Import – CsRgsConfiguration** с помощью параметра **реплацеексистингсеттингс** , но эта операция переопределит все параметры уровня приложения в целевом пуле.</span><span class="sxs-lookup"><span data-stu-id="1d711-112">These settings can be transferred from one pool to another through the **Import-CsRgsConfiguration** cmdlet by using the **ReplaceExistingSettings** parameter, but this operation will override any application-level settings in the destination pool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="1d711-113">В отдельном расположении храните резервную копию всех исходных аудиофайлов, которые использовались для настройки приложения группы ответа (то есть, любых записей или файлов музыки для хранения на удержании).</span><span class="sxs-lookup"><span data-stu-id="1d711-113">In a separate location, keep a backup copy of all the original audio files that have been used to configure the Response Group application (that is, any recordings or music-on-hold files).</span></span>

    
    </div>
    
    <span data-ttu-id="1d711-114">Если вы настроили файлы музыки для сохранения, которые были отправлены для парковки вызовов в пуле, сохраните их копию в другом расположении.</span><span class="sxs-lookup"><span data-stu-id="1d711-114">If you have any customized music-on-hold files that have been uploaded for Call Park in a pool, you should keep a copy of these in another location.</span></span> <span data-ttu-id="1d711-115">Резервные копии этих файлов не входят в состав процесса аварийного восстановления Lync Server 2013, и они будут потеряны, если загруженные в пул файлы повреждены, повреждены или удалены.</span><span class="sxs-lookup"><span data-stu-id="1d711-115">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d711-116">Приложение парковки вызовов может хранить только один набор параметров и один настроенный звуковой файл музыки для хранения на каждом пуле.</span><span class="sxs-lookup"><span data-stu-id="1d711-116">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="1d711-117">Доступ к этим параметрам можно получить с помощью командлета <STRONG>Get – CsCpsConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1d711-117">These settings can be accessed through the <STRONG>Get-CsCpsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="1d711-118">Так как механизм аварийного восстановления для парковки вызовов полагается на приложение парковки резервного пула, параметры основного пула не архивируются и не сохраняются в случае аварии.</span><span class="sxs-lookup"><span data-stu-id="1d711-118">Because the disaster recovery mechanism for Call Park relies on the Call Park application of the backup pool, the settings of the primary pool are not backed up or preserved if a disaster occurs.</span></span> <span data-ttu-id="1d711-119">При потере основного пула эти параметры не могут быть восстановлены, а при развертывании нового пула для замены основного пула параметры парковки вызовов и любой настроенный звуковой файл музыки необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="1d711-119">If the primary pool is lost, these settings cannot be recovered, and when a new pool is deployed to replace the primary pool, the Call Park settings and any customized music-on-hold audio file would need to be reconfigured.</span></span>

    
    </div>

  - <span data-ttu-id="1d711-120">Если вы настроили объявления в рамках функции голосовой связи неназначенных номеров, мы рекомендуем оставить в другом месте копию любого оригинального звукового файла, используемого при начальной настройке.</span><span class="sxs-lookup"><span data-stu-id="1d711-120">If you configure any announcements as part of the Unassigned Number Voice Feature, we recommend that you keep in another location a copy of any original audio file used during the initial configuration.</span></span> <span data-ttu-id="1d711-121">Если вы этого не сделаете, вы можете получить копию настроенных звуковых файлов в хранилище файлов сервера или пула, в который были импортированы звуковые файлы.</span><span class="sxs-lookup"><span data-stu-id="1d711-121">If you did not do that, you can get a copy of the configured audio files in the file store of the server or pool to which the audio files were imported.</span></span> <span data-ttu-id="1d711-122">Резервные копии этих файлов не входят в состав процесса аварийного восстановления Lync Server 2013, и они будут потеряны, если загруженные в пул файлы повреждены, повреждены или удалены.</span><span class="sxs-lookup"><span data-stu-id="1d711-122">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="1d711-123">Чтобы скопировать все звуковые файлы, используемые для настройки функции голосовой связи неназначенных номеров, из хранилища файлов сервера или пула, используйте:</span><span class="sxs-lookup"><span data-stu-id="1d711-123">To copy all the audio files used to configure the Unassigned Number Voice Feature from the file store of a server or a pool, use:</span></span>
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - <span data-ttu-id="1d711-124">Если у вас есть мониторинг и Архивация баз данных в пуле, для их резервного копирования следует использовать средства управления SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1d711-124">If you have Monitoring and Archiving databases in a pool, you should use SQL Server management tools to back them up.</span></span> <span data-ttu-id="1d711-125">В процедуре отработки отказа ABC базы данных мониторинга и архивации не сохраняются, если они размещены в пуле A, так как эти базы данных не архивируются в службе резервного копирования Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d711-125">In the ABC failover procedure, Monitoring and Archiving databases are not preserved if they are collocated in pool A, because these databases are not backed up through Lync Server Backup Service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

