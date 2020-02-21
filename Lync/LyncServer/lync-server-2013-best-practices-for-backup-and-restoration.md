---
title: 'Lync Server 2013: рекомендации по резервному копированию и восстановлению'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30dd3345545ae8c77c4ebfcece7154e91059f9aa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a><span data-ttu-id="7b619-102">Рекомендации по резервному копированию и восстановлению для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b619-102">Best practices for backup and restoration for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b619-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="7b619-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="7b619-104">В этом разделе представлены два типа рекомендаций:</span><span class="sxs-lookup"><span data-stu-id="7b619-104">This section includes two types of best practices:</span></span>

  - <span data-ttu-id="7b619-105">Рекомендации по резервному копированию и восстановлению.</span><span class="sxs-lookup"><span data-stu-id="7b619-105">Best practices for backup and restoration.</span></span>

  - <span data-ttu-id="7b619-106">Рекомендации по минимизации последствий аварии.</span><span class="sxs-lookup"><span data-stu-id="7b619-106">Best practices for minimizing the impact of a disaster.</span></span>

<div>

## <a name="best-practices-for-backup-and-restoration"></a><span data-ttu-id="7b619-107">Рекомендации по резервному копированию и восстановлению</span><span class="sxs-lookup"><span data-stu-id="7b619-107">Best Practices for Backup and Restoration</span></span>

<span data-ttu-id="7b619-108">Для упрощения процесса резервного копирования и восстановления придерживайтесь следующих рекомендаций при резервном копировании или восстановлении данных:</span><span class="sxs-lookup"><span data-stu-id="7b619-108">To facilitate your backup and restoration process, apply the following best practices when you back up or restore your data:</span></span>

  - <span data-ttu-id="7b619-109">Регулярно выполняйте регулярное резервное копирование с нужными интервалами.</span><span class="sxs-lookup"><span data-stu-id="7b619-109">Perform regular backups at appropriate intervals.</span></span> <span data-ttu-id="7b619-110">Самый простой и наиболее часто используемый тип резервного копирования и расписание ротации — это полная резервная копия всей базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7b619-110">The simplest and most commonly used backup type and rotation schedule is a full, nightly backup of the entire SQL Server database.</span></span> <span data-ttu-id="7b619-111">В этом случае, если требуется восстановление, процесс восстановления требует только одной резервной копии, и данные не должны быть потеряны.</span><span class="sxs-lookup"><span data-stu-id="7b619-111">Then, if restoration is necessary, the restoration process requires only one backup, and no more than a day’s data should be lost.</span></span>

  - <span data-ttu-id="7b619-112">Если вы используете командлеты или панель управления Lync Server для внесения изменений в конфигурацию, используйте командлет **Export-CsConfiguration** , чтобы создать резервную копию файла конфигурации топологии (XDS. mdf) после внесения изменений, чтобы не потерять изменения, если необходимо восстановить базы данных.</span><span class="sxs-lookup"><span data-stu-id="7b619-112">If you use cmdlets or the Lync Server Control Panel to make configuration changes, use the **Export-CsConfiguration** cmdlet to take a snapshot backup of the topology configuration file (Xds.mdf) after you make the changes, so that you won't lose the changes if you need to restore your databases.</span></span> <span data-ttu-id="7b619-113">Обратите внимание, что резервная копия этой конфигурации создается в формате XML и сжимается как ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="7b619-113">Note that this configuration is backed up in XML format and compressed as a ZIP file.</span></span>

  - <span data-ttu-id="7b619-114">Убедитесь, что в общей папке, которую планируется использовать для резервного копирования Lync Server, достаточно дискового пространства для хранения всех архивных данных.</span><span class="sxs-lookup"><span data-stu-id="7b619-114">Make sure that the shared folder you plan to use for backing up Lync Server has sufficient disk space to hold all the backed up data.</span></span>

  - <span data-ttu-id="7b619-115">Планирование резервного копирования при использовании Lync Server обычно является нехваткой для улучшения производительности сервера и взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="7b619-115">Schedule backups when Lync Server usage is typically low, to improve server performance and user experience.</span></span>

  - <span data-ttu-id="7b619-116">Убедитесь, что выбрано место хранения резервных копий данных (рекомендуется удаленное расположение).</span><span class="sxs-lookup"><span data-stu-id="7b619-116">Make sure that the location where you back up data is secure (we recommend a remote location).</span></span>

  - <span data-ttu-id="7b619-117">Храните файлы резервных копий там, где они будут доступны, на тот случай, если потребуется восстановить данные.</span><span class="sxs-lookup"><span data-stu-id="7b619-117">Keep the backup files where they will be available, in case you need to restore the data.</span></span>

  - <span data-ttu-id="7b619-118">Планирование и планирование периодического тестирования процессов восстановления, поддерживаемых Организацией.</span><span class="sxs-lookup"><span data-stu-id="7b619-118">Plan for and schedule periodic testing of the restoration processes that are supported by your organization.</span></span>

  - <span data-ttu-id="7b619-119">Проверяйте процессы резервного копирования и восстановления заранее, чтобы убедиться, что они работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="7b619-119">Validate your backup and restoration processes in advance to make sure that they work as expected.</span></span>

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a><span data-ttu-id="7b619-120">Рекомендации по минимизации последствий аварии</span><span class="sxs-lookup"><span data-stu-id="7b619-120">Best Practices for Minimizing the Impact of a Disaster</span></span>

<span data-ttu-id="7b619-121">Оптимальная стратегия, связанная с аварийными перерывами в обслуживании (например, неконтролируемые события, такие как перебои в питании или неожиданные сбои оборудования), предполагает, что они будут выполняться и планируется соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="7b619-121">The best strategy for dealing with disastrous service interruptions (caused by unmanageable events such as power outages or sudden hardware failures) is to assume they will happen, and to plan accordingly.</span></span>

<span data-ttu-id="7b619-122">Если службы Lync, с минимальными нарушениями и сбоями, являются критически важными для Организации, следует рассмотреть возможность реализации посторонних пулов серверов переднего плана, как описано в статье [Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="7b619-122">If Lync services, with a minimum of disruption and outage, are business-critical for your organization, you should consider implementing paired pools of Front End Servers, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="7b619-123">Затем, если один из этих пулов имеет аварии, администратор может переключить пользователей этого пула в другой пул с минимальным временем простоя.</span><span class="sxs-lookup"><span data-stu-id="7b619-123">Then, if one of these pools has a disaster, an administrator can switch the users of that pool to be served by the other pool, with a minimum of downtime.</span></span>

<span data-ttu-id="7b619-124">Планы аварийного управления, которые вы разрабатываете в рамках стратегии резервного копирования и восстановления, должны включать в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="7b619-124">The disaster management plans that you develop as part of your backup and restoration strategy should include the following:</span></span>

  - <span data-ttu-id="7b619-125">Хранение программного обеспечения и обновление программного обеспечения и микропрограммного обеспечения, легко доступные.</span><span class="sxs-lookup"><span data-stu-id="7b619-125">Keeping your software media, and your software and firmware updates, readily available.</span></span>

  - <span data-ttu-id="7b619-126">Обслуживание аппаратных и программных записей.</span><span class="sxs-lookup"><span data-stu-id="7b619-126">Maintaining hardware and software records.</span></span>

  - <span data-ttu-id="7b619-127">Регулярное резервное копирование данных и отслеживание целостности резервных копий.</span><span class="sxs-lookup"><span data-stu-id="7b619-127">Backing up your data regularly and monitoring the integrity of your backups.</span></span>

  - <span data-ttu-id="7b619-128">Обучение сотрудников при аварийном восстановлении, документирование процедур и внедрение детализации для моделирования аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="7b619-128">Training your staff in disaster recovery, documenting procedures, and implementing disaster recovery simulation drills.</span></span>

  - <span data-ttu-id="7b619-129">Обеспечение доступности запасного оборудования или, если у вас есть соглашение об уровне обслуживания (SLA), следует отключить поставщиков аппаратного обеспечения и поставщиков для замены приглашения.</span><span class="sxs-lookup"><span data-stu-id="7b619-129">Keeping spare hardware available, or, if you have a service level agreement (SLA), contracting with hardware vendors and suppliers for prompt replacements.</span></span>

  - <span data-ttu-id="7b619-130">Отделение расположения файлов журнала транзакций (LDF-файлов) и файлов базы данных (MDF-файлы).</span><span class="sxs-lookup"><span data-stu-id="7b619-130">Separating the location of your transaction log files (.ldf files) and database files (.mdf files).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

