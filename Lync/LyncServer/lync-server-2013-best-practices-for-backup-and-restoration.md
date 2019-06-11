---
title: 'Lync Server 2013: советы и рекомендации по резервному копированию и восстановлению'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc7a926bd8fd5c61f87d5e8252c30f40e5a6a69
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a><span data-ttu-id="88933-102">Рекомендации по резервному копированию и восстановлению для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88933-102">Best practices for backup and restoration for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88933-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="88933-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="88933-104">В этом разделе приводятся рекомендации двух типов:</span><span class="sxs-lookup"><span data-stu-id="88933-104">This section includes two types of best practices:</span></span>

  - <span data-ttu-id="88933-105">Рекомендации по резервному копированию и восстановлению.</span><span class="sxs-lookup"><span data-stu-id="88933-105">Best practices for backup and restoration.</span></span>

  - <span data-ttu-id="88933-106">Рекомендации по минимизации воздействия на аварии.</span><span class="sxs-lookup"><span data-stu-id="88933-106">Best practices for minimizing the impact of a disaster.</span></span>

<div>

## <a name="best-practices-for-backup-and-restoration"></a><span data-ttu-id="88933-107">Рекомендации по резервному копированию и восстановлению</span><span class="sxs-lookup"><span data-stu-id="88933-107">Best Practices for Backup and Restoration</span></span>

<span data-ttu-id="88933-108">Чтобы упростить процесс резервного копирования и восстановления, применяйте следующие рекомендации при резервном копировании или восстановлении данных.</span><span class="sxs-lookup"><span data-stu-id="88933-108">To facilitate your backup and restoration process, apply the following best practices when you back up or restore your data:</span></span>

  - <span data-ttu-id="88933-109">Регулярно выполняйте регулярные архивации с необходимыми интервалами.</span><span class="sxs-lookup"><span data-stu-id="88933-109">Perform regular backups at appropriate intervals.</span></span> <span data-ttu-id="88933-110">Самым простым и наиболее часто используемым типом резервного копирования и расписанием вращения является заполненная Ночная резервная копия всей базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="88933-110">The simplest and most commonly used backup type and rotation schedule is a full, nightly backup of the entire SQL Server database.</span></span> <span data-ttu-id="88933-111">Затем, если требуется восстановление, для процесса восстановления требуется только одна резервная копия, и данные за день не должны быть потеряны.</span><span class="sxs-lookup"><span data-stu-id="88933-111">Then, if restoration is necessary, the restoration process requires only one backup, and no more than a day’s data should be lost.</span></span>

  - <span data-ttu-id="88933-112">Если вы используете командлеты и панель управления Lync Server для изменения конфигурации, используйте командлет **Export-ксконфигуратион** , чтобы сделать резервную копию файла конфигурации топологии (XDS. mdf) после внесения изменений, чтобы не потерять изменения, если Вам необходимо восстановить базы данных.</span><span class="sxs-lookup"><span data-stu-id="88933-112">If you use cmdlets or the Lync Server Control Panel to make configuration changes, use the **Export-CsConfiguration** cmdlet to take a snapshot backup of the topology configuration file (Xds.mdf) after you make the changes, so that you won't lose the changes if you need to restore your databases.</span></span> <span data-ttu-id="88933-113">Обратите внимание, что эта конфигурация заархивирована в формате XML и сжата как ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="88933-113">Note that this configuration is backed up in XML format and compressed as a ZIP file.</span></span>

  - <span data-ttu-id="88933-114">Убедитесь в том, что общая папка, которую вы планируете использовать для резервного копирования сервера Lync Server, достаточно места на диске для размещения всех архивированных данных.</span><span class="sxs-lookup"><span data-stu-id="88933-114">Make sure that the shared folder you plan to use for backing up Lync Server has sufficient disk space to hold all the backed up data.</span></span>

  - <span data-ttu-id="88933-115">Планирование резервного копирования при использовании Lync Server обычно является низким, чтобы повысить производительность сервера и взаимодействие с пользователем.</span><span class="sxs-lookup"><span data-stu-id="88933-115">Schedule backups when Lync Server usage is typically low, to improve server performance and user experience.</span></span>

  - <span data-ttu-id="88933-116">Убедитесь в том, что место, в которое вы хотите создать резервную копию данных, защищено (мы рекомендуем использовать удаленное расположение).</span><span class="sxs-lookup"><span data-stu-id="88933-116">Make sure that the location where you back up data is secure (we recommend a remote location).</span></span>

  - <span data-ttu-id="88933-117">Храните файлы резервных копий, где они будут доступны, на случай необходимости восстановления данных.</span><span class="sxs-lookup"><span data-stu-id="88933-117">Keep the backup files where they will be available, in case you need to restore the data.</span></span>

  - <span data-ttu-id="88933-118">Планирование и планирование периодического тестирования процессов восстановления, которые поддерживаются вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="88933-118">Plan for and schedule periodic testing of the restoration processes that are supported by your organization.</span></span>

  - <span data-ttu-id="88933-119">Проверяйте процесс резервного копирования и восстановления заранее и убедитесь, что они работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="88933-119">Validate your backup and restoration processes in advance to make sure that they work as expected.</span></span>

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a><span data-ttu-id="88933-120">Рекомендации по минимизации воздействия аварии</span><span class="sxs-lookup"><span data-stu-id="88933-120">Best Practices for Minimizing the Impact of a Disaster</span></span>

<span data-ttu-id="88933-121">Наилучшая стратегия использования аварийных прерываний (например, неуправляемых событий, таких как перебои питания или внезапные аппаратные сбои) — считать, что они будут выполнены, и соответствующим образом спланировать.</span><span class="sxs-lookup"><span data-stu-id="88933-121">The best strategy for dealing with disastrous service interruptions (caused by unmanageable events such as power outages or sudden hardware failures) is to assume they will happen, and to plan accordingly.</span></span>

<span data-ttu-id="88933-122">Если в вашей организации используются службы Lync, в которых не должно быть перерывов и отказов, следует предусмотреть использование парных пулов серверов переднего плана, как описано в разделе [Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="88933-122">If Lync services, with a minimum of disruption and outage, are business-critical for your organization, you should consider implementing paired pools of Front End Servers, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="88933-123">Затем, если один из этих пулов имеет аварии, администратор может переключить пользователей этого пула на то, что он будет обслуживаться другим пулом, с минимальным временем простоя.</span><span class="sxs-lookup"><span data-stu-id="88933-123">Then, if one of these pools has a disaster, an administrator can switch the users of that pool to be served by the other pool, with a minimum of downtime.</span></span>

<span data-ttu-id="88933-124">Планы управления аварийным управлением, которые вы разрабатываете как часть стратегии резервного копирования и восстановления, должны включать в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="88933-124">The disaster management plans that you develop as part of your backup and restoration strategy should include the following:</span></span>

  - <span data-ttu-id="88933-125">Хранение программного обеспечения и обновление программного обеспечения и микропрограмм.</span><span class="sxs-lookup"><span data-stu-id="88933-125">Keeping your software media, and your software and firmware updates, readily available.</span></span>

  - <span data-ttu-id="88933-126">Обслуживание аппаратных и программных записей.</span><span class="sxs-lookup"><span data-stu-id="88933-126">Maintaining hardware and software records.</span></span>

  - <span data-ttu-id="88933-127">Регулярно создавайте резервные копии данных и отслеживайте целостность резервных копий.</span><span class="sxs-lookup"><span data-stu-id="88933-127">Backing up your data regularly and monitoring the integrity of your backups.</span></span>

  - <span data-ttu-id="88933-128">Обучение сотрудников в аварийном восстановлении, документирование процедур и внедрение моделей аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="88933-128">Training your staff in disaster recovery, documenting procedures, and implementing disaster recovery simulation drills.</span></span>

  - <span data-ttu-id="88933-129">Поддержка запасного оборудования или, если у вас есть соглашение об уровне обслуживания (SLA), вы можете отдать запрос на обслуживание поставщикам оборудования и поставщикам для замены запросов.</span><span class="sxs-lookup"><span data-stu-id="88933-129">Keeping spare hardware available, or, if you have a service level agreement (SLA), contracting with hardware vendors and suppliers for prompt replacements.</span></span>

  - <span data-ttu-id="88933-130">Разделение местоположения файлов журнала транзакций (LDF-файлов) и файлов баз данных (MDF-файлов).</span><span class="sxs-lookup"><span data-stu-id="88933-130">Separating the location of your transaction log files (.ldf files) and database files (.mdf files).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

