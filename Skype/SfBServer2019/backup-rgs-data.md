---
title: Backing up Response Group Service (RGS) data in Skype for Business Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Learn how to back up Response Group Service (RGS) data in Skype for Business Server 2019.
ms.openlocfilehash: f9c62953dcb859be2aa34bdee84ca76e3303d738
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824073"
---
# <a name="back-up-response-group-service-rgs-data"></a><span data-ttu-id="3ba84-103">Back up Response Group Service (RGS) data</span><span class="sxs-lookup"><span data-stu-id="3ba84-103">Back up Response Group Service (RGS) data</span></span>

<span data-ttu-id="3ba84-104">В накопительном обновлении Skype для бизнеса Server 2019 за июль мы включили возможность включать данные RGS в стандартное резервное копирование.</span><span class="sxs-lookup"><span data-stu-id="3ba84-104">With the Skype for Business Server 2019 July cumulative update, we’ve included the ability to include RGS data as part of the standard backup.</span></span>

## <a name="rgs-data-replication"></a><span data-ttu-id="3ba84-105">Репликация данных RGS</span><span class="sxs-lookup"><span data-stu-id="3ba84-105">RGS data replication</span></span>

<span data-ttu-id="3ba84-106">Чтобы попробовать функции репликации данных RGS, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3ba84-106">To try RGS data replication functionality, please follow the steps below:</span></span>

1. <span data-ttu-id="3ba84-107">Установите накопительное обновление за июль на всех переднем конце сопряженного пула.</span><span class="sxs-lookup"><span data-stu-id="3ba84-107">Install the July cumulative update on all front-ends (FEs) of your paired pool.</span></span>
1. <span data-ttu-id="3ba84-108">Установите базу данных RGS на обоих членах сопряженного пула:</span><span class="sxs-lookup"><span data-stu-id="3ba84-108">Install the RGS database on both members of the paired pool:</span></span>
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. <span data-ttu-id="3ba84-109">Чтобы реплицировать существующие данные RGS в резервные таблицы, чтобы их можно было получить с помощью RGSBackupService, запустите следующий в обоих пулах:</span><span class="sxs-lookup"><span data-stu-id="3ba84-109">Run the following cmdlet on both pools to replicate existing RGS Data to the backup tables so that the data can be picked up by RGSBackupService:</span></span>
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. <span data-ttu-id="3ba84-110">В включить RGSBackupService (это позволит включить RGSBackupService глобально.</span><span class="sxs-lookup"><span data-stu-id="3ba84-110">Enable RGSBackupService (This will enable RGSBackupService globally.</span></span> <span data-ttu-id="3ba84-111">Если для этого параметра установлено true, RGSBackupService начнет синхронизировать данные RGS в сопряженных пулах (оба пула должны быть cu1).</span><span class="sxs-lookup"><span data-stu-id="3ba84-111">If this parameter is set to true , RGSBackupService will start syncing RGS data on paired pools (both pools needs to be CU1).</span></span> <span data-ttu-id="3ba84-112">Подождите несколько минут, чтобы начать работу.</span><span class="sxs-lookup"><span data-stu-id="3ba84-112">Wait for a few minutes to get it started.</span></span> <span data-ttu-id="3ba84-113">Изначально состояние RGS BackupService будет notInitialized.):</span><span class="sxs-lookup"><span data-stu-id="3ba84-113">Initially, RGS BackupService status will be NotInitialized.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. <span data-ttu-id="3ba84-114">Чтобы проверить BackupServiceStatus:</span><span class="sxs-lookup"><span data-stu-id="3ba84-114">To check BackupServiceStatus:</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. <span data-ttu-id="3ba84-115">Чтобы проверить DataReplication в пулах, используйте эти cmdlets (эти данные показывают только данные пула владельца):</span><span class="sxs-lookup"><span data-stu-id="3ba84-115">To check DataReplication across pools, use these cmdlets (These cmdlets show only owner pool data):</span></span>
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. <span data-ttu-id="3ba84-116">Чтобы проверить данные RGS пула владельца и их резервные данные:</span><span class="sxs-lookup"><span data-stu-id="3ba84-116">To check Owner pool RGS data and its backup data:</span></span>
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. <span data-ttu-id="3ba84-117">Проверьте функциональность рабочего процесса, выполнив звуковой вызов рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3ba84-117">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="3ba84-118">Отладка пула владельцев RGS.</span><span class="sxs-lookup"><span data-stu-id="3ba84-118">Failover your RGS Owner pool.</span></span>
1. <span data-ttu-id="3ba84-119">Проверьте функциональность рабочего процесса, выполнив звуковой вызов рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3ba84-119">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="3ba84-120">Откат пула.</span><span class="sxs-lookup"><span data-stu-id="3ba84-120">Failback the pool.</span></span>
1. <span data-ttu-id="3ba84-121">Обновим данные RGS в пуле источника и выполните еще одну отбойную передачу, чтобы проверить, отражаются ли изменения в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="3ba84-121">Update RGS Data on source pool and perform another failover to check that changes are reflected on backup pool.</span></span> <span data-ttu-id="3ba84-122">RGS должна вести себя так же, как и до отката.</span><span class="sxs-lookup"><span data-stu-id="3ba84-122">RGS should behave in same way as it was behaving before failover.</span></span>

> [!TIP]
> <span data-ttu-id="3ba84-123">Рекомендуется выполнить эти действия для больших объемов данных и выполнять частые откаты и откаты.</span><span class="sxs-lookup"><span data-stu-id="3ba84-123">It is recommended you perform these steps on a bulk of data and do frequent failover and failbacks.</span></span> <span data-ttu-id="3ba84-124">Все новые RGS, созданные после этого обновления CU, также должны быть реплицированы.</span><span class="sxs-lookup"><span data-stu-id="3ba84-124">Any new RGS created after this CU update should also be replicated.</span></span>

## <a name="rgs-cmdlets"></a><span data-ttu-id="3ba84-125">RGS cmdlets</span><span class="sxs-lookup"><span data-stu-id="3ba84-125">RGS cmdlets</span></span>

- <span data-ttu-id="3ba84-126">Чтобы проверить BackupServiceStatus (состояние экспорта должно быть в окончательном или стабильном состоянии.</span><span class="sxs-lookup"><span data-stu-id="3ba84-126">To check BackupServiceStatus (The export status should be in the Final or Steady state.</span></span> <span data-ttu-id="3ba84-127">Состояние импорта должно быть в обычном состоянии.</span><span class="sxs-lookup"><span data-stu-id="3ba84-127">The import status should be in the Normal state.</span></span> <span data-ttu-id="3ba84-128">Должна быть включена RGSBackupservice.):</span><span class="sxs-lookup"><span data-stu-id="3ba84-128">RGSBackupservice should be enabled.):</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- <span data-ttu-id="3ba84-129">Чтобы полностью синхронизировать данные RGS в резервном пуле (синхронизируется полная синхронизация данных RGS в резервном пуле).):</span><span class="sxs-lookup"><span data-stu-id="3ba84-129">To Fully Sync RGS Data on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- <span data-ttu-id="3ba84-130">Чтобы полностью синхронизировать файловой магазин RGS в резервном пуле (синхронизируется полная синхронизация данных RGS в резервном пуле).):</span><span class="sxs-lookup"><span data-stu-id="3ba84-130">To Fully Sync the RGS filestore on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- <span data-ttu-id="3ba84-131">Синхронизация данных дельты RGS в резервном пуле (синхронизирует разноналичные данные в резервном пуле только для RGS).):</span><span class="sxs-lookup"><span data-stu-id="3ba84-131">To Sync RGS delta data on the backup pool (This will sync delta data on backup pool for RGS only.):</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- <span data-ttu-id="3ba84-132">Чтобы синхронизировать все данные модуля, включая RGS:</span><span class="sxs-lookup"><span data-stu-id="3ba84-132">To sync all module data including RGS:</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- <span data-ttu-id="3ba84-133">Отключение RGSBackupService (глобальное отключение RGSBackupService.</span><span class="sxs-lookup"><span data-stu-id="3ba84-133">To disable RGSBackupService (This will disable RGSBackupService globally.</span></span> <span data-ttu-id="3ba84-134">Если этот параметр имеет true, RGSBackupService будет отключен во всех сопряженных пулах.):</span><span class="sxs-lookup"><span data-stu-id="3ba84-134">If this parameter is set to true , RGSBackupService will be disabled on all paired pools.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
