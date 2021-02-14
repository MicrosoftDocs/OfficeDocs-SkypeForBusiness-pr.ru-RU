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
# <a name="back-up-response-group-service-rgs-data"></a>Back up Response Group Service (RGS) data

В накопительном обновлении Skype для бизнеса Server 2019 за июль мы включили возможность включать данные RGS в стандартное резервное копирование.

## <a name="rgs-data-replication"></a>Репликация данных RGS

Чтобы попробовать функции репликации данных RGS, выполните следующие действия:

1. Установите накопительное обновление за июль на всех переднем конце сопряженного пула.
1. Установите базу данных RGS на обоих членах сопряженного пула:
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. Чтобы реплицировать существующие данные RGS в резервные таблицы, чтобы их можно было получить с помощью RGSBackupService, запустите следующий в обоих пулах:
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. В включить RGSBackupService (это позволит включить RGSBackupService глобально. Если для этого параметра установлено true, RGSBackupService начнет синхронизировать данные RGS в сопряженных пулах (оба пула должны быть cu1). Подождите несколько минут, чтобы начать работу. Изначально состояние RGS BackupService будет notInitialized.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. Чтобы проверить BackupServiceStatus:
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. Чтобы проверить DataReplication в пулах, используйте эти cmdlets (эти данные показывают только данные пула владельца):
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. Чтобы проверить данные RGS пула владельца и их резервные данные:
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. Проверьте функциональность рабочего процесса, выполнив звуковой вызов рабочего процесса.
1. Отладка пула владельцев RGS.
1. Проверьте функциональность рабочего процесса, выполнив звуковой вызов рабочего процесса.
1. Откат пула.
1. Обновим данные RGS в пуле источника и выполните еще одну отбойную передачу, чтобы проверить, отражаются ли изменения в резервном пуле. RGS должна вести себя так же, как и до отката.

> [!TIP]
> Рекомендуется выполнить эти действия для больших объемов данных и выполнять частые откаты и откаты. Все новые RGS, созданные после этого обновления CU, также должны быть реплицированы.

## <a name="rgs-cmdlets"></a>RGS cmdlets

- Чтобы проверить BackupServiceStatus (состояние экспорта должно быть в окончательном или стабильном состоянии. Состояние импорта должно быть в обычном состоянии. Должна быть включена RGSBackupservice.):
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- Чтобы полностью синхронизировать данные RGS в резервном пуле (синхронизируется полная синхронизация данных RGS в резервном пуле).):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- Чтобы полностью синхронизировать файловой магазин RGS в резервном пуле (синхронизируется полная синхронизация данных RGS в резервном пуле).):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- Синхронизация данных дельты RGS в резервном пуле (синхронизирует разноналичные данные в резервном пуле только для RGS).):
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- Чтобы синхронизировать все данные модуля, включая RGS:
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- Отключение RGSBackupService (глобальное отключение RGSBackupService. Если этот параметр имеет true, RGSBackupService будет отключен во всех сопряженных пулах.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
