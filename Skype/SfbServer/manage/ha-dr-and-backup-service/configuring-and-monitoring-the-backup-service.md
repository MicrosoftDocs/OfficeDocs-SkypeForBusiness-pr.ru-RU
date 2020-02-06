---
title: Настройка и мониторинг службы резервного копирования
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Вы можете использовать команды командной консоли Skype для бизнеса Server для настройки и мониторинга службы резервного копирования.
ms.openlocfilehash: 80b15b2306807fe5bfc36449e16953466e3af75c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818220"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="0b6a0-103">Настройка и наблюдение за службой архивации в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="0b6a0-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="0b6a0-104">Для настройки и наблюдения за службой архивации можно использовать следующие команды командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="0b6a0-105">Чтобы восстановить сведения о конференции, хранящиеся в хранилище файлов в пуле переднего плана, в разделе [Восстановление содержимого конференции с помощью службы архивации](#restore-conference-contents-using-the-backup-service)ниже.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="0b6a0-106">Группа Рткуниверсалсерверадминс — единственная группа, у которой есть разрешения на запуск **Get-ксбаккупсервицестатус** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="0b6a0-107">Чтобы использовать этот командлет, войдите в систему как участник этой группы.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="0b6a0-108">Вы также можете предоставить доступ к этой команде другим группам (например, Ксадминистратор) с помощью командлета **Set-ксбаккупсервицеконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="0b6a0-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="0b6a0-109">Просмотр конфигурации службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="0b6a0-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="0b6a0-110">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="0b6a0-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="0b6a0-111">По умолчанию для СинЦинтервал используется два минуты.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="0b6a0-112">Настройка интервала синхронизации службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="0b6a0-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="0b6a0-113">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="0b6a0-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="0b6a0-114">Например, в приведенном ниже списке для интервала задается значение, равное трем минутам.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="0b6a0-115">Несмотря на то, что вы можете использовать этот командлет для изменения интервала синхронизации по умолчанию для службы резервного копирования, это не следует делать, если только это не является обязательным, так как интервал синхронизации сильно влияет на производительность службы резервного копирования и цель точки восстановления (RPO).</span><span class="sxs-lookup"><span data-stu-id="0b6a0-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="0b6a0-116">Получение состояния службы резервного копирования для определенного пула</span><span class="sxs-lookup"><span data-stu-id="0b6a0-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="0b6a0-117">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="0b6a0-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="0b6a0-118">Состояние синхронизации службы резервного копирования определяется односторонним из пула (P1) в резервный пул (P2).</span><span class="sxs-lookup"><span data-stu-id="0b6a0-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="0b6a0-119">Состояние синхронизации от P1 до P2 может отличаться от P2 до P1.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="0b6a0-120">В случае P1 — P2 служба резервного копирования находится в состоянии «стабильно», если все изменения, внесенные в P1, полностью реплицируются на P2 в течение интервала синхронизации.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="0b6a0-121">Она находится в состоянии "завершено", если больше нет изменений для синхронизации из P1 в P2.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="0b6a0-122">Оба состояния указывают на то, что служба резервного копирования на момент выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="0b6a0-123">Это не означает, что возвращенное состояние останется таким же, как и впоследствии.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="0b6a0-124">В частности, состояние "Final" продолжает храниться только в том случае, если P1 не создает никаких изменений после выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="0b6a0-125">Это справедливо в случае сбоя P1 в P2 после того, как он будет помещен в режим "только для чтения" в рамках логики выполнения **Invoke-кспулфаиловер** .</span><span class="sxs-lookup"><span data-stu-id="0b6a0-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="0b6a0-126">Получение сведений об отношении резервного копирования для определенного пула</span><span class="sxs-lookup"><span data-stu-id="0b6a0-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="0b6a0-127">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="0b6a0-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="0b6a0-128">Чтобы принудительно выполнить синхронизацию службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="0b6a0-128">To force a Backup Service sync</span></span>

<span data-ttu-id="0b6a0-129">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="0b6a0-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="0b6a0-130">Восстановление содержимого конференции с помощью службы архивации</span><span class="sxs-lookup"><span data-stu-id="0b6a0-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="0b6a0-131">Если сведения о конференции, хранящиеся в хранилище файлов в пуле переднего плана, становятся недоступными, необходимо восстановить эти данные, чтобы пользователи, расположенные в пуле, сохраняли данные Конференции.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="0b6a0-132">Если пул переднего плана, который потерял данные конференции, связан с другим пулом переднего плана, вы можете восстановить данные с помощью службы резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="0b6a0-133">Кроме того, вы должны выполнить эту задачу в случае сбоя всего пула, после чего вы должны переключиться между пользователями в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-133">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="0b6a0-134">Если эти пользователи не переносятся в исходный пул, необходимо выполнить описанные ниже действия, чтобы снова скопировать содержимое конференции в первоначальный пул.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-134">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="0b6a0-135">Предположим, что Pool1 связан с Pool2, а данные конференции в Pool1 теряются.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="0b6a0-136">Вы можете использовать следующий командлет для вызова службы резервного копирования для восстановления содержимого:</span><span class="sxs-lookup"><span data-stu-id="0b6a0-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="0b6a0-137">Восстановление содержимого конференции может занять некоторое время в зависимости от его размера.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-137">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="0b6a0-138">Вы можете проверить состояние процесса с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="0b6a0-138">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="0b6a0-139">Процесс выполняется, если этот командлет возвращает значение стабильного состояния для модуля конференции с данными.</span><span class="sxs-lookup"><span data-stu-id="0b6a0-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
