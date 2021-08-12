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
description: 'Миграция приложения Call Park включает подготовку пула Skype для бизнеса Server 2019 с настраиваемой музыкой для файлов удержания, которые были загружены в устаревшей установке, восстановление параметров уровня обслуживания и перенацеление всех орбит Call Park в пул Skype для бизнеса Server 2019 г. Если настраиваемые файлы музыки на удержании настроены в пуле, эти файлы необходимо скопировать в новый Skype для бизнеса Server 2019. Кроме того, рекомендуется резервное копирование любых настраиваемых файлов Call Park с музыкой на удержании из другого пункта назначения, чтобы сохранить отдельную копию резервного копирования всех настраиваемых файлов на удержании, которые были загружены для Call Park. Настраиваемые файлы музыки при удержании для приложения парковки вызовов хранятся в файловом хранилище пула. Чтобы скопировать аудиофайлы из магазина файлов пула в хранилище файлов Skype для бизнеса Server 2019 г., используйте команду Xcopy со следующими параметрами:'
ms.openlocfilehash: f83e1095361ddd272a35bf9100171c0d06caf003dfae84f19c01b2aa53de7977
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312327"
---
# <a name="migrate-call-park-application-settings"></a>Перенос параметров приложения парковки вызовов

Миграция приложения Call Park включает подготовку пула Skype для бизнеса Server 2019 г. с любыми настраиваемой музыкой-на-удержании файлов, которые были загружены в устаревшей установке, восстановление параметров уровня обслуживания и перенацеление всех орбит Call Park в пул Skype для бизнеса Server 2019 г. Если настраиваемые файлы музыки на удержании настроены в пуле, эти файлы необходимо скопировать в новый Skype для бизнеса Server 2019. Кроме того, рекомендуется резервное копирование любых настраиваемых файлов Call Park с музыкой на удержание в другом месте, чтобы сохранить отдельную копию резервного копирования всех настраиваемых файлов на удержании, которые были загружены для Call Park. Настраиваемые файлы музыки при удержании для приложения парковки вызовов хранятся в файловом хранилище пула. Чтобы скопировать аудиофайлы из магазина файлов пула в хранилище файлов Skype для бизнеса Server 2019 г., используйте команду **Xcopy** со следующими параметрами: 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

При копировании всех настраиваемых аудиофайлов в хранилище файлов Skype для бизнеса Server 2019 года необходимо настроить параметры приложения Call Park пула Skype для бизнеса Server 2019 г., а диапазоны орбиты Call Park, связанные с устаревшим пулом, должны быть перенастрояться в пул Skype для бизнеса Server 2019 г.

Параметры приложения Call Park включают пороговое значение времени отключения при приеме, включение или отключение музыки в удержании, максимальные попытки вызова и запрос на время. Для запуска команды **Set-CsCpsConfiguration** необходимо управлять настройками приложений Call Park с помощью Skype для бизнеса Server-оболочки управления. Вы не можете управлять настройками приложений Call Park с помощью панели Skype для бизнеса Server управления. 

## <a name="reconfigure-the-call-park-service-settings"></a>Изменение настроек параметров службы парковки вызовов

1. С Skype для бизнеса Server 2019 front End Server откройте Skype для бизнеса Server shell.

2. Введите в командной строке следующую команду:

    > [!NOTE]
    > Если параметры Skype для бизнеса Server 2019 года совпадают с устаревшими настройками, этот шаг можно пропустить. Если параметры приложений Call Park отличаются для среды Skype для бизнеса Server 2019 г. и устаревших, используйте см. в качестве шаблона для обновления этих изменений. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Чтобы перенаправление всех орбит Call Park варьируется от устаревшего пула до пула Skype для бизнеса Server 2019 г., можно использовать панель управления Skype для бизнеса Server или Skype для бизнеса Server management Shell. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Перенаменуй все диапазоны орбиты call Park с Skype для бизнеса Server панели управления

1. Откройте панель Skype для бизнеса Server управления.

2. В области слева выберите **Компоненты голосовой связи**.

3. Перейдите на вкладку **Парковка вызовов**. 

4. Для каждого диапазона орбиты Парка вызовов, назначенного устаревшему пулу, изменить **FQDN** параметров сервера назначения и выбрать пул Skype для бизнеса Server 2019 года, который будет обрабатывать запросы call Park. 

5. Выберите **Зафиксировать**, чтобы сохранить изменения. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Перенаправление всех диапазонов орбиты call Park с помощью Skype для бизнеса Server shell управления

1. Откройте Skype для бизнеса Server управленческой оболочки.

2. В командной строке введите следующую команду:

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    Этот командлет выводит список всех диапазонов орбит парковки вызовов в развертывании. Все орбиты Call Park, на которые заданы параметры **CallParkServiceId** и **CallParkServerFqdn** в качестве устаревшего пула, должны быть назначены повторно. 

    Для перенастройки устаревших диапазонов орбиты Call Park в пул Skype для бизнеса Server 2019 г. в командной строке введите следующее:

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

После перенастройки всех диапазонов орбиты Call Park в пул Skype для бизнеса Server 2019 г. процесс миграции приложения Call Park будет завершен, а пул Skype для бизнеса Server 2019 г. будет обрабатывать все будущие запросы call Park.


