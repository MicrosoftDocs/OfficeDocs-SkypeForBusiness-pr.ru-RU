---
title: Backing up Response Group Service (RGS) data in Skype для бизнеса Server 2019
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
description: Сведения о том, как сделать личные данные группы реагирования (RGS) в Skype для бизнеса Server 2019 г.
ms.openlocfilehash: 8b0cbbb41c7bf2a61d21043141d2475a8c69a79696e8cf5cbde6709e2d196c52
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280474"
---
# <a name="back-up-response-group-service-rgs-data"></a>Back up Response Group Service (RGS) data

В Skype для бизнеса Server 2019 июля мы включили возможность включить данные RGS в качестве части стандартного резервного копирования.

## <a name="rgs-data-replication"></a>Репликация данных RGS

Чтобы попробовать функции репликации данных RGS, выполните следующие действия:

1. Установите накопительное обновление июля во всех передних концах (FEs) вашего парного пула.
1. Установите базу данных RGS на обоих членах парного пула:
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. Запустите следующий комдлет в обоих пулах для репликации существующих данных RGS в таблицы резервного копирования, чтобы данные могли быть подхвалены RGSBackupService:
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. Включить RGSBackupService (Это позволит RGSBackupService глобально. Если этот параметр задан для true, RGSBackupService начнет синхронизировать данные RGS в парных пулах (оба пула должны быть cu1). Подождите несколько минут, чтобы начать работу. Изначально состояние резервного копирования RGS будет notInitialized.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. Чтобы проверить BackupServiceStatus:
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. Чтобы проверить DataReplication в пулах, используйте эти кодлеты (в этих кодлетах покажут только данные пула владельцев):
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. Чтобы проверить данные пула владельцев RGS и данные резервного копирования:
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. Проверьте функциональность рабочего процесса, сделав звуковой вызов в рабочий процесс.
1. Сбой пула владельца RGS.
1. Проверьте функциональность рабочего процесса, сделав звуковой вызов в рабочий процесс.
1. Отбой пула.
1. Обнови данные RGS в пуле исходных данных и выполните еще один сбой, чтобы проверить, отражаются ли изменения в пуле резервного копирования. RGS должна вести себя так же, как и перед сбойом.

> [!TIP]
> Рекомендуется выполнять эти действия на больших объемах данных и выполнять частые сбой и сбой. Любые новые RGS, созданные после этого обновления CU, также должны быть реплицированы.

## <a name="rgs-cmdlets"></a>Комлеты RGS

- Чтобы проверить BackupServiceStatus (состояние экспорта должно быть в окончательном или стабильном состоянии. Состояние импорта должно быть в нормальном состоянии. Необходимо включить RGSBackupservice.):
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- Чтобы полностью синхронизировать данные RGS в резервном пуле (это будет синхронизировать полные данные RGS в пуле резервного копирования.):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- Чтобы полностью синхронизировать файлохранилище RGS в пуле резервного копирования (это позволит синхронизировать полные данные RGS в пуле резервного копирования.):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- Синхронизация данных дельты RGS в пуле резервного копирования (это будет синхронизировать данные дельты в пуле резервного копирования только для RGS.):
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- Синхронизация всех данных модуля, включая RGS:
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- Отключение RGSBackupService (Это отключит RGSBackupService во всем мире. Если этот параметр задан для true, RGSBackupService будет отключен во всех парных пулах.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
