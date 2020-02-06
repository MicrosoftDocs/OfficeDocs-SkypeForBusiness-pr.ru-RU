---
title: Резервное копирование данных службы группы ответа (RGS) в Skype для бизнеса Server 2019
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
description: Сведения о том, как создавать резервные копии данных службы группы ответа (RGS) в Skype для бизнеса Server 2019.
ms.openlocfilehash: f9c62953dcb859be2aa34bdee84ca76e3303d738
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824073"
---
# <a name="back-up-response-group-service-rgs-data"></a><span data-ttu-id="cf677-103">Резервное копирование данных службы группы ответа (RGS)</span><span class="sxs-lookup"><span data-stu-id="cf677-103">Back up Response Group Service (RGS) data</span></span>

<span data-ttu-id="cf677-104">Накопительное обновление для Skype для бизнеса Server 2019 за июль мы включили возможность включения данных RGS в состав стандартной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="cf677-104">With the Skype for Business Server 2019 July cumulative update, we’ve included the ability to include RGS data as part of the standard backup.</span></span>

## <a name="rgs-data-replication"></a><span data-ttu-id="cf677-105">Репликация данных RGS</span><span class="sxs-lookup"><span data-stu-id="cf677-105">RGS data replication</span></span>

<span data-ttu-id="cf677-106">Чтобы воспользоваться функциональными возможностями репликации данных RGS, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="cf677-106">To try RGS data replication functionality, please follow the steps below:</span></span>

1. <span data-ttu-id="cf677-107">Установите накопительный пакет обновления за Июль (Фес) для всех внешних концов вашего Объединенного пула.</span><span class="sxs-lookup"><span data-stu-id="cf677-107">Install the July cumulative update on all front-ends (FEs) of your paired pool.</span></span>
1. <span data-ttu-id="cf677-108">Установите базу данных RGS для обоих участников Объединенного пула:</span><span class="sxs-lookup"><span data-stu-id="cf677-108">Install the RGS database on both members of the paired pool:</span></span>
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. <span data-ttu-id="cf677-109">Выполните следующий командлет на обоих пулах, чтобы реплицировать данные из существующих RGSных данных в таблицы резервного копирования, чтобы эти данные могли быть отобраны с помощью Ргсбаккупсервице:</span><span class="sxs-lookup"><span data-stu-id="cf677-109">Run the following cmdlet on both pools to replicate existing RGS Data to the backup tables so that the data can be picked up by RGSBackupService:</span></span>
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. <span data-ttu-id="cf677-110">Включите Ргсбаккупсервице (этот параметр включит Ргсбаккупсервице глобально.</span><span class="sxs-lookup"><span data-stu-id="cf677-110">Enable RGSBackupService (This will enable RGSBackupService globally.</span></span> <span data-ttu-id="cf677-111">Если для этого параметра установлено значение true, Ргсбаккупсервице начнет синхронизировать данные RGS в связанных пулах (оба пула должны быть CU1).</span><span class="sxs-lookup"><span data-stu-id="cf677-111">If this parameter is set to true , RGSBackupService will start syncing RGS data on paired pools (both pools needs to be CU1).</span></span> <span data-ttu-id="cf677-112">Подождите несколько минут, чтобы начать работу.</span><span class="sxs-lookup"><span data-stu-id="cf677-112">Wait for a few minutes to get it started.</span></span> <span data-ttu-id="cf677-113">Первоначально Баккупсервице состояние RGS будет Нотинитиализед.):</span><span class="sxs-lookup"><span data-stu-id="cf677-113">Initially, RGS BackupService status will be NotInitialized.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. <span data-ttu-id="cf677-114">Чтобы проверить Баккупсервицестатус, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="cf677-114">To check BackupServiceStatus:</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. <span data-ttu-id="cf677-115">Для проверки репликации данных между пулами используйте следующие командлеты (эти командлеты содержат данные только о пуле владельцев):</span><span class="sxs-lookup"><span data-stu-id="cf677-115">To check DataReplication across pools, use these cmdlets (These cmdlets show only owner pool data):</span></span>
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. <span data-ttu-id="cf677-116">Для проверки данных пула владельцев и данных резервной копии сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="cf677-116">To check Owner pool RGS data and its backup data:</span></span>
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. <span data-ttu-id="cf677-117">Проверка функций рабочего процесса путем совершения голосовой связи с рабочим процессом.</span><span class="sxs-lookup"><span data-stu-id="cf677-117">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="cf677-118">Отработка отказа пула владельцев RGS.</span><span class="sxs-lookup"><span data-stu-id="cf677-118">Failover your RGS Owner pool.</span></span>
1. <span data-ttu-id="cf677-119">Проверка функций рабочего процесса путем совершения голосовой связи с рабочим процессом.</span><span class="sxs-lookup"><span data-stu-id="cf677-119">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="cf677-120">Отказовозвращение пула.</span><span class="sxs-lookup"><span data-stu-id="cf677-120">Failback the pool.</span></span>
1. <span data-ttu-id="cf677-121">Обновите данные RGS в исходном пуле и выполните другой переход, чтобы убедиться, что изменения отражены в пуле резервных копий.</span><span class="sxs-lookup"><span data-stu-id="cf677-121">Update RGS Data on source pool and perform another failover to check that changes are reflected on backup pool.</span></span> <span data-ttu-id="cf677-122">RGS должен вести себя так же, как и поведение, прежде чем переход на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="cf677-122">RGS should behave in same way as it was behaving before failover.</span></span>

> [!TIP]
> <span data-ttu-id="cf677-123">Рекомендуется выполнить эти действия для массовых данных и часто отработки отказа и фаилбаккс.</span><span class="sxs-lookup"><span data-stu-id="cf677-123">It is recommended you perform these steps on a bulk of data and do frequent failover and failbacks.</span></span> <span data-ttu-id="cf677-124">Все новые RGSные данные, созданные после этого обновления SP1, также должны быть реплицированы.</span><span class="sxs-lookup"><span data-stu-id="cf677-124">Any new RGS created after this CU update should also be replicated.</span></span>

## <a name="rgs-cmdlets"></a><span data-ttu-id="cf677-125">Командлеты RGS</span><span class="sxs-lookup"><span data-stu-id="cf677-125">RGS cmdlets</span></span>

- <span data-ttu-id="cf677-126">Чтобы проверить Баккупсервицестатус (состояние экспорта должно находиться в конечном или стабильном состоянии).</span><span class="sxs-lookup"><span data-stu-id="cf677-126">To check BackupServiceStatus (The export status should be in the Final or Steady state.</span></span> <span data-ttu-id="cf677-127">Состояние импорта должно быть в обычном состоянии.</span><span class="sxs-lookup"><span data-stu-id="cf677-127">The import status should be in the Normal state.</span></span> <span data-ttu-id="cf677-128">Ргсбаккупсервице должен быть включен.):</span><span class="sxs-lookup"><span data-stu-id="cf677-128">RGSBackupservice should be enabled.):</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- <span data-ttu-id="cf677-129">Полная синхронизация данных RGS в пуле резервных копий (это приведет к синхронизации полных данных RGS в пуле архивации).</span><span class="sxs-lookup"><span data-stu-id="cf677-129">To Fully Sync RGS Data on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- <span data-ttu-id="cf677-130">Чтобы полностью синхронизировать хранилище файлов RGS в пуле резервных копий (это приведет к синхронизации полных данных RGS в пуле резервных копий.):</span><span class="sxs-lookup"><span data-stu-id="cf677-130">To Fully Sync the RGS filestore on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- <span data-ttu-id="cf677-131">Синхронизация данных изменений в пуле для пула резервной копии (это приведет к синхронизации Дельта-данных в пуле резервных копий только для RGS).</span><span class="sxs-lookup"><span data-stu-id="cf677-131">To Sync RGS delta data on the backup pool (This will sync delta data on backup pool for RGS only.):</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- <span data-ttu-id="cf677-132">Чтобы синхронизировать все данные модуля, включая RGS, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="cf677-132">To sync all module data including RGS:</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- <span data-ttu-id="cf677-133">Чтобы отключить Ргсбаккупсервице (это будет отключаться Ргсбаккупсервице глобально.</span><span class="sxs-lookup"><span data-stu-id="cf677-133">To disable RGSBackupService (This will disable RGSBackupService globally.</span></span> <span data-ttu-id="cf677-134">Если для этого параметра установлено значение true, Ргсбаккупсервице будет отключен для всех сопряженных пулов.):</span><span class="sxs-lookup"><span data-stu-id="cf677-134">If this parameter is set to true , RGSBackupService will be disabled on all paired pools.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
