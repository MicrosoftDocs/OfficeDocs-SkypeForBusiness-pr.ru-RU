---
title: Перенос параметров приложения парковки вызовов
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Миграция приложения парковки вызовов включает подготовку пула Skype для бизнеса Server 2019 к работе с любыми пользовательскими файлами музыки на удержании, которые были загружены в устаревшей установке, восстановление параметров уровня обслуживания и перенацеление всех орбит парковки вызовов в пул Skype для бизнеса Server 2019. If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool. Кроме того, рекомендуется резервное копирование всех настроенных файлов музыки при удержании при парковке вызовов из другого места назначения, чтобы сохранить отдельную резервную копию всех настроенных файлов музыки при удержании, загруженных для парковки вызовов. Настраиваемые файлы музыки при удержании для приложения парковки вызовов хранятся в файловом хранилище пула. To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the Xcopy command with the following parameters:'
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752821"
---
# <a name="migrate-call-park-application-settings"></a>Перенос параметров приложения парковки вызовов

Миграция приложения парковки вызовов включает подготовку пула Skype для бизнеса Server 2019 к работе с пользовательскими файлами музыки при удержании, которые были загружены в устаревшей установке, восстановление параметров на уровне службы и перенацеление всех орбит парковки вызовов в пул Skype для бизнеса Server 2019. If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool. Кроме того, рекомендуется резервное копирование всех настроенных файлов музыки при удержании при парковке вызовов в другом месте, чтобы сохранить отдельную резервную копию всех настроенных файлов музыки при удержании, загруженных для парковки вызовов. Настраиваемые файлы музыки при удержании для приложения парковки вызовов хранятся в файловом хранилище пула. To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters: 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

После копирования всех настроенных аудиофайлов в хранилище файлов Skype для бизнеса Server 2019 необходимо настроить параметры приложения парковки вызовов в пуле Skype для бизнеса Server 2019, а диапазоны орбит парковки вызовов, связанные с устаревшим пулом, необходимо перена назначены пулу Skype для бизнеса Server 2019.

Параметры приложения парковки вызовов включают пороговое значение временивызова, включая или отключая музыку при удержании, максимальное количество попыток вызова и запрос на время. Управлять настройками приложения парковки вызовов можно с помощью оболочки управления Skype для бизнеса Server для запуска команды **Set-CsCpsConfiguration.** Невозможно управлять настройками приложения парковки вызовов с помощью панели управления Skype для бизнеса Server. 

## <a name="reconfigure-the-call-park-service-settings"></a>Изменение настроек параметров службы парковки вызовов

1. From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.

2. Введите в командной строке следующую команду:

    > [!NOTE]
    > Если параметры приложения парковки вызовов Skype для бизнеса Server 2019 идентичны старым, этот шаг можно пропустить. If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel

1. Откройте панель управления Skype для бизнеса Server.

2. В области слева выберите **Компоненты голосовой связи**.

3. Перейдите на вкладку **Парковка вызовов**. 

4. Для каждого диапазона орбит парковки вызовов, назначенного устаревшему пулу, отредактируем **FQDN** параметра конечного сервера и выберите пул Skype для бизнеса Server 2019, который будет обрабатывать запросы на парковку вызовов. 

5. Выберите **Зафиксировать**, чтобы сохранить изменения. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Перенаправление всех диапазонов орбит парковки вызовов с помощью оболочки управления Skype для бизнеса Server

1. Откройте Skype для бизнеса Server Management Shell.

2. В командной строке введите следующую команду:

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    Этот командлет выводит список всех диапазонов орбит парковки вызовов в развертывании. Все орбиты парковки вызовов с параметрами **CallParkServiceId** и **CallParkServerFqdn,** заданные в качестве устаревшего пула, должны быть назначены повторно. 

    Чтобы перенаповести устаревшие диапазоны орбит парковки вызовов в пул Skype для бизнеса Server 2019, в командной строке введите следующую команду:

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

После перенастройки всех диапазонов орбит парковки вызовов в пул Skype для бизнеса Server 2019 процесс миграции приложения парковки вызовов будет завершен, и пул Skype для бизнеса Server 2019 будет обрабатывать все последующие запросы на парковку вызовов.


