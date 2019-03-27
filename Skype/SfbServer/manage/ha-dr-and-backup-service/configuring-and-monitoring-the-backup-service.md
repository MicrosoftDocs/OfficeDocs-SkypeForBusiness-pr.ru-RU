---
title: Настройка и мониторинг службы резервного копирования
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Скайп для команды консоли Business Server можно использовать для настройки и мониторинга службы резервного копирования.
ms.openlocfilehash: 3a41caecb4e123505da2d529ea74c22a5d0e28e7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896835"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="2afcd-103">Настройка и мониторинг службы резервного копирования в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="2afcd-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="2afcd-104">Следующие Скайп для команды консоли Business Server можно использовать для настройки и мониторинга службы резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="2afcd-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="2afcd-105">Чтобы восстановить данные конференции, хранящиеся в хранилище файлов пула переднего плана, ниже приведены [Восстановление содержимого конференций с помощью службы резервного копирования](#restore-conference-contents-using-the-backup-service).</span><span class="sxs-lookup"><span data-stu-id="2afcd-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="2afcd-106">Группа RTCUniversalServerAdmins — только группы, которая имеет разрешения на выполнение **Get-CsBackupServiceStatus** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2afcd-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="2afcd-107">Чтобы использовать этот командлет, войти в систему как член этой группы.</span><span class="sxs-lookup"><span data-stu-id="2afcd-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="2afcd-108">Или можно предоставить доступ к этой команды в другие группы (например, CSAdministrator) с помощью командлета **Set-CsBackupServiceConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="2afcd-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="2afcd-109">Для просмотра конфигурации службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="2afcd-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="2afcd-110">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2afcd-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="2afcd-111">Значение syncinterval по умолчанию равно двум минутам.</span><span class="sxs-lookup"><span data-stu-id="2afcd-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="2afcd-112">Чтобы задать интервал синхронизации службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="2afcd-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="2afcd-113">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2afcd-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="2afcd-114">Например следующая команда задает интервал в три минуты.</span><span class="sxs-lookup"><span data-stu-id="2afcd-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="2afcd-115">Несмотря на то, что этот командлет можно использовать для изменения интервала синхронизации, установленного по умолчанию для службы резервного копирования, которые не следует делать, если это действительно необходимо, как синхронизация интервал имеет значительное влияние на производительность службы резервного копирования и точка восстановления (RPO).</span><span class="sxs-lookup"><span data-stu-id="2afcd-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="2afcd-116">Чтобы получить сведения о состоянии службы резервного копирования для конкретного пула</span><span class="sxs-lookup"><span data-stu-id="2afcd-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="2afcd-117">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2afcd-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="2afcd-118">Состояние синхронизации службы резервного копирования определяется unidirectionally из пула (P1) его резервном пуле (P2).</span><span class="sxs-lookup"><span data-stu-id="2afcd-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="2afcd-119">Состояние синхронизации из P1 в P2 может отличаться от одного из P2 для P1.</span><span class="sxs-lookup"><span data-stu-id="2afcd-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="2afcd-120">Для P1 P2 службы резервного копирования находится в состоянии «постоянной», если все изменения, внесенные в P1 полностью реплицируются через P2 в течение интервала синхронизации.</span><span class="sxs-lookup"><span data-stu-id="2afcd-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="2afcd-121">Это в состояние «окончательный» при наличии больше нет изменений для синхронизации с P1 в P2.</span><span class="sxs-lookup"><span data-stu-id="2afcd-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="2afcd-122">Оба состояния указывают моментальный снимок службы резервного копирования во время выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="2afcd-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="2afcd-123">Это не означает хранятся состояние, возвращаемое как и впоследствии.</span><span class="sxs-lookup"><span data-stu-id="2afcd-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="2afcd-124">В частности «окончательный» состояние будет содержать только если P1 не вызывает изменений после выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="2afcd-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="2afcd-125">Это значение true в случае переключиться P1 P2 после P1 как часть логики выполнения **Invoke-CsPoolfailover** переводится в режим только для чтения.</span><span class="sxs-lookup"><span data-stu-id="2afcd-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="2afcd-126">Для получения сведений о резерве для конкретного пула</span><span class="sxs-lookup"><span data-stu-id="2afcd-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="2afcd-127">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2afcd-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="2afcd-128">Принудительная синхронизация службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="2afcd-128">To force a Backup Service sync</span></span>

<span data-ttu-id="2afcd-129">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2afcd-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="2afcd-130">Восстановление содержимого конференций с помощью службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="2afcd-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="2afcd-131">Недоступность конференции информацию, содержащуюся в хранилище файлов пула переднего плана, чтобы пользователей, размещенных в пуле необходимо восстановить эти сведения сохранять данные конференции.</span><span class="sxs-lookup"><span data-stu-id="2afcd-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="2afcd-132">Если пул переднего плана, в котором осуществлялась данных конференции сопоставляется с другой пул переднего плана, службы резервного копирования можно использовать для восстановления данных.</span><span class="sxs-lookup"><span data-stu-id="2afcd-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="2afcd-133">Необходимо также выполнить эту задачу, если не удалось выполнить весь пул и отработки отказа пользователей в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="2afcd-133">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="2afcd-134">При этих пользователей при сбое обратно в их исходный пул, необходимо использовать эту процедуру, чтобы скопировать содержимое конференций их исходный пул.</span><span class="sxs-lookup"><span data-stu-id="2afcd-134">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="2afcd-135">Предположим, что пула Pool1 сопряжено с Pool2 и данные конференции в пуле Pool1 будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="2afcd-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="2afcd-136">Для вызова службы резервного копирования для восстановления содержимого, можно использовать следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2afcd-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="2afcd-137">Восстановление содержимого конференций может занять некоторое время, в зависимости от их размера.</span><span class="sxs-lookup"><span data-stu-id="2afcd-137">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="2afcd-138">Чтобы проверить состояние процесса можно использовать следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2afcd-138">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="2afcd-139">Процесс завершается, когда этот командлет возвращает значение Steady State для данных в модуле конференций.</span><span class="sxs-lookup"><span data-stu-id="2afcd-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
