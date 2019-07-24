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
localization_priority: Normal
ms.collection: IT_Skype16
description: Сведения о том, как создавать резервные копии данных службы группы ответа (RGS) в Skype для бизнеса Server 2019.
ms.openlocfilehash: 0a37b4d4771a75513666597de5eb87dedcbcd0c7
ms.sourcegitcommit: 14700a4faab81a294ac794f25b26619a5ed242a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "35821333"
---
# <a name="back-up-response-group-service-rgs-data"></a>Резервное копирование данных службы группы ответа (RGS)

Накопительное обновление для Skype для бизнеса Server 2019 за июль мы включили возможность включения данных RGS в состав стандартной резервной копии.

## <a name="rgs-data-replication"></a>Репликация данных RGS

Чтобы воспользоваться функциональными возможностями репликации данных RGS, выполните указанные ниже действия.

1. Установите накопительный пакет обновления за Июль (Фес) для всех внешних концов вашего Объединенного пула.
1. Установите базу данных RGS для обоих участников Объединенного пула:
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. Выполните следующий командлет на обоих пулах, чтобы реплицировать данные из существующих RGSных данных в таблицы резервного копирования, чтобы эти данные могли быть отобраны с помощью Ргсбаккупсервице:
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. Включите Ргсбаккупсервице (этот параметр включит Ргсбаккупсервице глобально. Если для этого параметра установлено значение true, Ргсбаккупсервице начнет синхронизировать данные RGS в связанных пулах (оба пула должны быть CU1). Подождите несколько минут, чтобы начать работу. Первоначально Баккупсервице состояние RGS будет Нотинитиализед.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. Чтобы проверить Баккупсервицестатус, выполните указанные ниже действия.
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. Для проверки репликации данных между пулами используйте следующие командлеты (эти командлеты содержат данные только о пуле владельцев):
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. Для проверки данных пула владельцев и данных резервной копии сделайте следующее:
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. Проверка функций рабочего процесса путем совершения голосовой связи с рабочим процессом.
1. Отработка отказа пула владельцев RGS.
1. Проверка функций рабочего процесса путем совершения голосовой связи с рабочим процессом.
1. Отказовозвращение пула.
1. Обновите данные RGS в исходном пуле и выполните другой переход, чтобы убедиться, что изменения отражены в пуле резервных копий. RGS должен вести себя так же, как и поведение, прежде чем переход на другой ресурс.

> [!TIP]
> Рекомендуется выполнить эти действия для массовых данных и часто отработки отказа и фаилбаккс. Все новые RGSные данные, созданные после этого обновления SP1, также должны быть реплицированы.

## <a name="rgs-cmdlets"></a>Командлеты RGS

- Чтобы проверить Баккупсервицестатус (состояние экспорта должно находиться в конечном или стабильном состоянии). Состояние импорта должно быть в обычном состоянии. Ргсбаккупсервице должен быть включен.):
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- Полная синхронизация данных RGS в пуле резервных копий (это приведет к синхронизации полных данных RGS в пуле архивации).
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- Чтобы полностью синхронизировать хранилище файлов RGS в пуле резервных копий (это приведет к синхронизации полных данных RGS в пуле резервных копий.):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- Синхронизация данных изменений в пуле для пула резервной копии (это приведет к синхронизации Дельта-данных в пуле резервных копий только для RGS).
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- Чтобы синхронизировать все данные модуля, включая RGS, выполните указанные ниже действия.
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- Чтобы отключить Ргсбаккупсервице (это будет отключаться Ргсбаккупсервице глобально. Если для этого параметра установлено значение true, Ргсбаккупсервице будет отключен для всех сопряженных пулов.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
