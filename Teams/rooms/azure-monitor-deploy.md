---
title: Развертывание Комнаты Microsoft Teams мониторинга с помощью Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: В этой статье рассмотрено развертывание мониторинга Комнаты Microsoft Teams мониторинга с помощью azure Monitor интегрированного комплексного развертывания.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1520e9a4c9eced048634a0fdc457bb2fd0ea0edb
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015219"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-monitoring-with-no-loc-textazure-monitor"></a>Развертывание :::no-loc text="Microsoft Teams Rooms"::: мониторинга с помощью :::no-loc text="Azure Monitor":::

В этой статье рассмотрено, как настроить и развернуть интегрированный комплексный мониторинг устройств :::no-loc text="Microsoft Teams Rooms"::: с помощью :::no-loc text="Azure Monitor"::: .

Вы можете настроить внутри для предоставления базовой телеметрии и оповещений, :::no-loc text="Log Analytics"::: которые помогут вам управлять :::no-loc text="Azure Monitor"::: :::no-loc text="Microsoft Teams Rooms"::: . По мере зрелости решения для управления вы можете развернуть дополнительные данные и возможности управления, чтобы получить более подробное представление о доступности и производительности устройства.

Следуя этому руководству, вы можете использовать панель мониторинга, например, в следующем примере, чтобы получить подробные отчеты о доступности устройств, работоспособности приложений и оборудования, а также о распространении версий приложений и операционных :::no-loc text="Microsoft Teams Rooms"::: систем.

![Снимок экрана: образец представления аналитики журналов для Комнаты Microsoft Teams.](../media/Deploy-Azure-Monitor-1.png "Пример представления аналитики журналов для Комнаты Microsoft Teams")

В общих чертах вам необходимо выполнить следующие задачи.


1. [Проверка :::no-loc text="Log Analytics"::: конфигурации](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Настройка тестовых устройств для :::no-loc text="Log Analytics"::: настройки управления](azure-monitor-deploy.md#configure_test_devices)
3. [Сопоставление настраиваемых полей](azure-monitor-deploy.md#Custom_fields)
4. [Определение :::no-loc text="Microsoft Teams Rooms"::: представлений в :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Определение оповещений](azure-monitor-deploy.md#Alerts)
6. [Настройка всех устройств для мониторинга](azure-monitor-deploy.md#configure_all_devices)
7. [Настройка дополнительных :::no-loc text="Azure Monitor"::: решений](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Несмотря на минимальную конфигурацию, можно отслеживать компьютер с операционной системой, но перед развертыванием агентов на всех устройствах необходимо предпринять определенные :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: :::no-loc text="Windows"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Teams Rooms"::: действия.
> Поэтому мы настоятельно рекомендуем выполнить все действия конфигурации в правильном порядке для управляемой настройки и настройки. Качество конечного результата во многом зависит от качества исходной конфигурации.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Проверка :::no-loc text="Log Analytics"::: конфигурации
<a name="validate_LogAnalytics"> </a>

Для начала сбора журналов из :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: . Рабочее пространство — это уникальная среда с собственным репозиторием :::no-loc text="Log Analytics"::: данных, источниками данных и решениями. Если у вас уже есть рабочее пространство, вы можете использовать его для отслеживания развертывания или же создать специальную область для :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: мониторинга.

Если вам нужно создать новую область, следуйте инструкциям в статье Создание рабочей области :::no-loc text="Log Analytics"::: [на :::no-loc text="Log Analytics"::: :::no-loc text="Azure"::: портале](/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Для использования :::no-loc text="Log Analytics"::: с , у вас должна быть :::no-loc text="Azure Monitor"::: активная :::no-loc text="Azure"::: подписка. Если у вас нет подписки, вы можете создать бесплатную пробную подписку :::no-loc text="Azure"::: в качестве отправной точки. [](https://azure.microsoft.com/free)

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Настройка сбора :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: журналов событий

:::no-loc text="Log Analytics"::: только собирает события из :::no-loc text="Windows"::: журналов событий, указанных в параметрах. Для каждого журнала собираются только события с выбранными серьезности.

Необходимо настроить сбор журналов, необходимых для отслеживания состояния :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: устройства и приложения. :::no-loc text="Microsoft Teams Rooms"::: используйте **:::no-loc text="Skype Room System":::** журнал событий.

Сведения о настройке сбора событий см. в источниках данных :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: журнала событий [ :::no-loc text="Windows"::: в :::no-loc text="Azure Monitor"::: ](/azure/azure-monitor/platform/data-sources-windows-events)

![Снимок экрана: параметры журнала событий.](../media/Deploy-Azure-Monitor-2.png "Параметры журнала событий")

> [!IMPORTANT]
> Настройте параметры журнала событий и введите имя журнала событий, а затем выберите флажки Ошибка, Предупреждение и :::no-loc text="Windows"::: **:::no-loc text="Skype Room System":::** Сведения.   

## <a name="configure-test-devices-for-azure-monitoring"></a>Настройка тестовых устройств для мониторинга Azure
<a name="configure_test_devices"> </a>

Вам нужно подготовиться :::no-loc text="Log Analytics"::: к отслеживанию :::no-loc text="Microsoft Teams Rooms"::: связанных событий. Для начала необходимо развернуть агентов на одном или двух устройствах, к которые у вас есть физический доступ, и получить эти тестовые устройства для получения определенных данных и их передачи в :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: рабочее :::no-loc text="Log Analytics"::: пространство.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Установка :::no-loc text="Microsoft Monitoring"::: агентов для тестирования устройств

Разместите агента на тестовых устройствах, используя инструкции, предоставленные в Подключение :::no-loc text="Microsoft Monitoring"::: [ :::no-loc text="Windows"::: компьютерах :::no-loc text="Log Analytics"::: службы в :::no-loc text="Azure"::: ](/azure/azure-monitor/platform/agent-windows). В этой статье подробно описаны действия по развертыванию агента для , инструкции по получению :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows"::: :::no-loc text="Log Analytics":::  * **workspace ID** _ и *__primary key_** :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: для :::no-loc text="Log Analytics"::: подключения устройств к развертыванию, а также инструкции по проверке подключения агентов к экземпляру.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Создание примеров :::no-loc text="Microsoft Teams Rooms"::: событий

После развертывания агента на тестовых устройствах убедитесь, что необходимые данные журнала событий собраны в :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Azure Monitor"::: .

> [!NOTE]
> После установки агента перезагружаем устройство и убедитесь, что приложение "Собрание" запущено, чтобы оно генерируло новые события :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: в журнале событий.

1.  Войдите на [ :::no-loc text="Microsoft Azure"::: портал,](https://portal.azure.com) перейдите к :::no-loc text="Log Analytics"::: рабочей области и выберите ее.

2.  Перечислить события пульса, созданные :::no-loc text="Microsoft Teams Rooms"::: устройством:
    1.  Выберите свою рабочее пространство и перейдите в **журналы** и используйте запрос для получения записей пульса, для которые будут иметься настраиваемые поля :::no-loc text="Microsoft Teams Rooms"::: .
    2.  Пример запроса: `Event | where Source == "SRS-App" and EventID == 2000`

3.  Убедитесь, что запрос возвращает записи журнала, включаемые события, созданные :::no-loc text="Microsoft Teams Rooms"::: приложением для собраний.

4.  Создание проблемы с оборудованием и проверка входа в систему необходимых :::no-loc text="Azure Log Analytics"::: событий.
    1.  Отключить одно из периферийных устройств в тестовой :::no-loc text="Microsoft Teams Rooms"::: системе. Это может быть камера, динамик, микрофон или экран передней комнаты.
    2.  Подождите 10 минут, пока журнал событий будет :::no-loc text="Azure Log Analytics"::: заполнен.
    3.  Использование запроса для списка событий ошибок оборудования: `Event | where Source == "SRS-App" and EventID == 3001`

5.  Создание проблемы с приложением и проверка записи необходимых событий.
    1.  Измените :::no-loc text="Microsoft Teams Rooms"::: конфигурацию учетной записи и введите неправильную пару Адрес электронной почты и пароль.
    2.  Подождите 10 минут, пока журнал событий будет :::no-loc text="Azure Log Analytics"::: заполнен.
    3.  Использование запроса для списка событий ошибок приложения: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Эти образцы журналов событий необходимы для настройки настраиваемых полей. Не переходите к следующему шагу, пока не соберет необходимые журналы событий.

## <a name="map-custom-fields"></a>Сопоставление настраиваемых полей
<a name="Custom_fields"> </a>

Настраиваемые поля используются для извлечения определенных данных из журналов событий. Необходимо определить настраиваемые поля, которые будут использоваться позже с плитками, представлениями панели мониторинга и оповещениями. См. [статью :::no-loc text="Log Analytics"::: ](/azure/azure-monitor/platform/custom-fields) Настраиваемые поля в и знакомство с понятиями, прежде чем приступить к созданию настраиваемых полей.

Чтобы извлечь настраиваемые поля из журналов событий, выполните указанные здесь действия.

1.  Войдите на [ :::no-loc text="Microsoft Azure"::: портал,](https://portal.azure.com) перейдите к :::no-loc text="Log Analytics"::: рабочей области и выберите ее.

2. Перечислить события, созданные :::no-loc text="Microsoft Teams Rooms"::: устройством:
   1.  Перейдите **в журналы** и воспользуйтесь запросом для извлечения записей, которые будут иметь настраиваемые поля.
   2.  Пример запроса: `Event | where Source == "SRS-App" and EventID == 2000`

3. Выберите одну из записей, выберите кнопку слева и запустите мастер извлечения полей.
4. Выделение данных, которые нужно извлечь из renderedDescription, и присвоение заголовка поля. Имена полей, которые следует использовать, предоставляются в таблице 1.
5. Используйте сопоставления, показанные в *таблице 1*. :::no-loc text="Log Analytics":::будет автоматически включаемая **\_ строка CF** при определении нового поля.

> [!IMPORTANT]
> Помните, что все поля jSON :::no-loc text="Log Analytics"::: и JSON с чувствительностью к делу.
> 
> Обратите внимание на запросы, необходимые для каждого настраиваемного поля в таблице ниже. Для успешного извлечения значений настраиваемого поля необходимо :::no-loc text="Log Analytics"::: использовать правильные запросы.
> 
**Таблица 1**

| **Поле JSON**                   | **:::no-loc text="Log Analytics"::: настраиваемые поля** | **Идентификатор события** | **Запрос для использования с извлечением**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Описание                      | SRSEventDescription         | **2000**     | Событие, \| где Source == "SRS-App" и EventID == 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Событие, \| где Source == "SRS-App" и EventID == 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Событие, \| где Source == "SRS-App" и EventID == 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Событие, \| где Source == "SRS-App" и EventID == 2000 |
| OS                               | SRSOSVersion                | **2000**     | Событие, \| где Source == "SRS-App" и EventID == 2000 |
| Версия ОС                        | SRSOSLongVersion            | **2000**     | Событие, \| где Source == "SRS-App" и EventID == 2000 |
| Alias                            | SRSAlias                    | **2000**     | Событие, \| где Source == "SRS-App" и EventID == 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Событие, \| где Source == "SRS-App" и EventID == 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Событие, \| где Source == "SRS-App" и EventID == 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Событие, \| где Source == "SRS-App" и EventID == 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Событие, \| где Source == "SRS-App" и EventID == 2000 |
| Состояние микрофона конференции     | SRSConfMicrophoneStatus     | **3001**     | Событие, \| где Source == "SRS-App" и EventID == 3001 |
| Состояние выступающего на конференции        | SRSConfSpeakerStatus        | **3001**     | Событие, \| где Source == "SRS-App" и EventID == 3001 |
| Состояние выступающего по умолчанию           | SRSDefaultSpeakerStatus     | **3001**     | Событие, \| где Source == "SRS-App" и EventID == 3001 |
| Состояние камеры                    | SRSCameraStatus             | **3001**     | Событие, \| где Source == "SRS-App" и EventID == 3001 |
| Перед состоянием "Отображение комнаты"     | SRS ПЕРЕУЛОВ.СТАТ               | **3001**     | Событие, \| где Source == "SRS-App" и EventID == 3001 |
| Состояние датчика движений             | SRSMotionSensorStatus       | **3001**     | Событие, \| где Source == "SRS-App" и EventID == 3001 |
| Состояние HDMI Ingest               | SRSHDMIIngestStatus         | **3001**     | Событие, \| где Source == "SRS-App" и EventID == 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Определение :::no-loc text="Microsoft Teams Rooms"::: представлений в :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

После сбора данных и карточек настраиваемые поля можно использовать конструктор представлений для разработки панели мониторинга, содержащей различные плитки для отслеживания :::no-loc text="Microsoft Teams Rooms"::: событий. С помощью конструктора представлений можно создать следующие плитки: Дополнительные сведения см. в [теме :::no-loc text="Log Analytics"::: Создание пользовательских представлений с помощью конструктора представлений в](/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Чтобы плитки панелей мониторинга работали правильно, необходимо было завершить предыдущие действия, которые были выполнены в этом руководстве.
>
> [!IMPORTANT]
> [31 августа 2023](https://azure.microsoft.com/updates/view-designer-in-azure-monitor-is-retiring-on-31-august-2023/) г. будет отключен конструктор представлений в Azure Monitor, а 30 ноября 2020 г. функции создания и клонирования отключены. Вместо этого можно использовать книги. Дополнительные сведения о руководстве по переходу на книги в конструкторе представлений см. в кратком руководстве с заранее задав [шаблоны конструктора представлений.](/azure/azure-monitor/visualize/view-designer-conversion-tasks#quickstart-with-preset-view-designer-templates)

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Создание информационной панели Комнаты Microsoft Teams вручную

Кроме того, вы можете создать собственную информационную панель и добавить только плитки, которые вы хотите отслеживать.

#### <a name="configure-the-overview-tile"></a>Настройка плитки "Обзор"

1.  Откройте **конструктор представлений**.
2.  Выберите **Плитка обзора**, а затем выберите **два числа** из коллекции.
3.  Привязать **:::no-loc text="Microsoft Teams Rooms":::** плитке имя .
4.  Определение **первой плитки:**<br>
    **Легенда:** Устройства, которые отправляли пульс хотя бы один раз в течение последнего месяца<br>
    **Запроса:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Определение второй **плитки:**<br>
    **Легенда:** Активные устройства, которые отправляли пульс в течение последнего часа<br>
    **Запроса:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Выберите **Применить**.

### <a name="create-a-tile-that-displays-active-devices"></a>Создание плитки с активными устройствами

1.  Выберите **Просмотреть панель мониторинга,** чтобы приступить к добавлению плиток.
2.  Выбор **списка & номера** из коллекции
3.  Определите **общие** свойства:<br>
    **Название группы:** Состояние heartbeat<br>
    **Новая группа:** Выбранного
4.  Определите **свойства** плитки.<br>
    **Легенда:** Активные устройства (отправленные в течение последних 20 минут)<br>
    **Запрос для плитки:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Определите **свойства** списка:<br>
    **Запрос списка:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Определение **названий столбцов:**<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Last Heartbeat
7.  Определить **запрос навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Выберите **Применить**, а затем **Закрыть**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Создание плитки, отображаемой на устройствах с проблемой подключения

1.  Выберите **& в коллекции,** а затем добавьте новую плитку.
2.  Определите **общие** свойства:<br>
    **Название группы:** Оставьте пустым<br>
    **Новая группа:** Не выбрано
3.  Определите **свойства** плитки.<br>
    **Легенда:** Неактивные устройства (за последние 20 минут сообщение не было отправлено)<br>
    **Запрос для плитки:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Определите **свойства** списка:<br>
    **Запрос списка:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Определение **названий столбцов:**<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Last Heartbeat
6.  Определение **запроса навигации:**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Выберите **Применить**, а затем **Закрыть**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Создание плитки для устройств с ошибкой оборудования

1.  Выберите **& в коллекции,** а затем добавьте новую плитку.
2.  Определите **общие** свойства:<br>
    **Название группы:** Состояние оборудования<br>
    **Новая группа:** Выбранного
3.  Определите **свойства** плитки.<br>
    **Легенда:** Устройства, на которые в последний час произошла ошибка оборудования<br>
    **Запрос для плитки:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Определите **свойства** списка:<br>
    **Запрос списка:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Определение **названий столбцов:**<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Последняя ошибка
6.  Определение **запроса навигации:**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Выберите **Применить**, а затем **Закрыть**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Создание плитки с версиями :::no-loc text="Microsoft Teams Rooms"::: операционной системы

1.  Выберите **& в коллекции,** а затем добавьте новую плитку.
2.  Определите **общие** свойства:<br>
    **Название группы:** Сведения об операционной системе<br>
    **Новая группа:** Выбранного
3.  Определите **свойства загона:**<br>
    **Название:** Версии операционной системы<br>
    **Субтитров:** Устройства с определенными версиями ОС
4.  Определите **свойства Donut:**<br>
    **Запроса:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Текст по центру:** Устройств<br>
    **Операции:** Сумма
5.  Определите **свойства** списка.<br>
    **Запрос списка:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Скрыть Graph:** выбрано<br>
    **Включить спарклины.** Не выбрано
6.  Определение **названий столбцов**.<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Оставьте пустым
7.  Определить **запрос навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Выберите **Применить,** а затем **Закрыть**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Создание плитки с :::no-loc text="Microsoft Teams Rooms"::: версиями приложений

1.  Выберите **& в коллекции,** а затем добавьте новую плитку.
2.  Определите **общие** свойства:<br>
    **Название группы:** :::no-loc text="Microsoft Teams Rooms"::: сведения о приложении<br>
    **Новая группа:** Выбранного
3.  Определите **свойства загона:**<br>
    **Название:** Версии приложений<br>
    **Субтитров:** Устройства с определенными версиями приложений
4.  Определите **свойства Donut:**<br>
    **Запроса:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Текст по центру:** Устройств<br>
    **Операции:** Сумма
5.  Определите **свойства** списка.<br>
    **Запрос списка:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Скрыть Graph:** выбрано<br>
    **Включить спарклины.** Не выбрано
6.  Определение **названий столбцов**.<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Оставьте пустым
7.  Определить **запрос навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Выберите **Применить,** а затем **Закрыть**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Создание плитки с отображением устройств с ошибкой приложения

1.  Выберите **& в коллекции,** а затем добавьте новую плитку.
2.  Определите **общие** свойства.<br>
    **Название группы:** Оставьте пустым<br>
    **Новая группа:** Не выбрано
3.  Определите **свойства** плитки.<br>
    **Легенда:** Устройства, на которые в последний час произошла ошибка приложения<br>
    **Запрос для плитки:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Определите **свойства** списка.<br>
    **Запрос списка:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Определение **названий столбцов**.<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Последняя ошибка
6.  Определить **запрос навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Выберите **Применить,** а затем **Закрыть**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Создание плитки для отображения перезапущенных устройств

1.  Выберите **& в коллекции,** а затем добавьте новую плитку.
2.  Определите **общие** свойства.<br>
    **Название группы:** Оставьте пустым<br>
    **Новая группа:** Не выбрано
3.  Определите **свойства** плитки.<br>
    **Легенда:** Устройства, на которых приложение было перезапущено за последние 24 часа, и количество перезапусков<br>
    **Запрос для плитки:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Определите **свойства** списка.<br>
    **Запрос списка:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Определение **названий столбцов**.<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Количество перезапусков
6.  Определить **запрос навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Выберите **Применить,** а затем **Закрыть**.
8.  Чтобы **сохранить панель** мониторинга, выберите сохранить ее.

Теперь вы завершили создание представлений.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Настройка оповещений в :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: может оповещать администраторов о проблеме с :::no-loc text="Microsoft Teams Rooms"::: консолью.

:::no-loc text="Azure Monitor"::: Включает встроенный механизм оповещения, который регулярно выполняется через запланированные поиски в журнале. Если результаты поиска по журналу соответствуют определенным условиям, создается запись оповещения.

После этого правило может автоматически выполнить одно или несколько действий, чтобы заблаговременно уведомить вас об оповещении или вызвать другой процесс. Возможные варианты с оповещениями:
-   Отправка сообщения электронной почты
-   Обращение к внешнему процессу с помощью запроса HTTP POST
-   Запуск книги в :::no-loc text="Azure Automation"::: службе

Дополнительные [данные :::no-loc text="Azure Monitor"::: об оповещениях](/azure/azure-monitor/platform/alerts-unified-log) см. в . :::no-loc text="Azure Monitor":::

> [!NOTE]
> В следующих примерах оповещения отправляются по электронной почте, когда устройство создает оборудование :::no-loc text="Microsoft Teams Rooms"::: или ошибку приложения.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Настройка оповещений электронной почты :::no-loc text="Microsoft Teams Rooms"::: для проблем с оборудованием

Настройте правило оповещения для проверки устройств, на устройствах с которыми у вас были проблемы с оборудованием :::no-loc text="Microsoft Teams Rooms"::: в течение последнего часа.
1.  Войдите на [ :::no-loc text="Microsoft Azure"::: портал,](https://portal.azure.com) перейдите к :::no-loc text="Log Analytics"::: рабочей области и выберите ее.

2. Перейдите в :::no-loc text="Log Analytics"::: свою workspace и выберите **Оповещения,** а затем выберите **Новое правило оповещения**

3. Выберите **Добавить условие,** а затем **Настраиваемый поиск в журнале**

4.  В текстовом поле Поисковый запрос введите следующий запрос:<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Настройте параметры логики оповещения.<br>
    **На основе:** Количество результатов<br>
    **Состояние:** Больше<br>
    **Пороговое значение:** 0<br>

6. Настройте параметры оценки и выберите **Готово:** <br>
    **Период (в минутах):** 60<br>
    **Частота (в минутах):** 60<br>

7. Настройка групп действий
    1.  Выберите **"Создать"**
    2.  В поле Имя  группы действий и Поля "Короткое *имя" укажив подходящие* имена.
    3.  Укажите уникальное имя *действия, выберите* Электронная почта, **SMS/Push/Голосовая** почта , а затем нажмите **Изменить сведения**.
    4.  Выберите **почтовый ящик** и укайте адрес электронной почты человека или группы, которые будут получать оповещения.
    5.  Вы также можете увести свой номер телефона, чтобы получать уведомления с помощью SMS, голосового звонка или того и другого.
    6. Выберите **ОК**.

8. **Настройте действия,** если вам нравится переопределять тему сообщений электронной почты.

9. Укажите имя и описание правила.<br>
    **Имя правила:** :::no-loc text="Microsoft Teams Rooms"::: Оповещение о сбое оборудования<br>
    **Описание:** Список устройств, которые столкнулись с проблемой оборудования в течение последнего часа<br>

10. Выберите серьезность и убедитесь, что правило включено.

11. Выберите **Создать правило оповещения**.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Настройка оповещений по электронной почте :::no-loc text="Microsoft Teams Rooms"::: для проблем с приложениями

Повторите эту же процедуру, но используйте следующий запрос для списка устройств, на устройствах с которыми в последний час были проблемы с приложением.

 ```
 Event
 | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
 | summarize arg_max(TimeGenerated, *) by Computer
 | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
 | sort by TimeGenerated desc
 ```

Теперь вы завершили определение оповещений. Вы можете определить дополнительные оповещения, используя примеры выше.

При оповещении вы получите сообщение электронной почты со списком устройств, которые столкнулись с проблемой в течение последнего часа.

! [Пример :::no-loc text="Azure Monitor"::: сообщения электронной почты с оповещением](.. /media/Deploy-Azure-Monitor-6.png "Пример :::no-loc text="Azure Monitor"::: сообщения электронной почты с оповещением")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Настройка всех устройств для :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"></a> После настройки панелей мониторинга и оповещений вы можете настроить агент на всех устройствах для :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: завершения развертывания мониторинга.

Хотя вы можете установить и настроить агент вручную на каждом устройстве, настоятельно рекомендуем использовать существующие средства :::no-loc text="Microsoft Monitoring"::: развертывания программного обеспечения и методы.

Если вы создаете устройства в первый раз, вам может потребоваться включить действия по настройке и настройке агента в процессе :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Monitoring"::: сборки. Дополнительные сведения см. [в установке агента с помощью командной строки.](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Развертывание :::no-loc text="Microsoft Monitoring"::: агента с помощью объекта групповой политики

Если вы уже развернули свои устройства перед внедрением , вы можете использовать предоставленный сценарий для настройки агентов с помощью :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring"::: объектов :::no-loc text="Active Directory"::: групповой политики.

1.  Создайте общий сетевой путь и придайте группе Domain Computers доступ **для чтения.**

2.  Скачать 64-битную версию :::no-loc text="Microsoft Monitoring"::: агента для :::no-loc text="Windows"::: из <https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Извлекать содержимое пакета установки в сетевую обетовую долю.
    1.  Откройте окно командной подсказки и выполните команду **MMASetup-AMD64.exe /c**
    2.  Укажите только что созданный вами поделиться и извлекать содержимое.

4.  Создайте объект групповой политики и назначьте его подразделению, в котором находятся учетные :::no-loc text="Microsoft Teams Rooms"::: записи компьютера.

5.  Настройте политику выполнения PowerShell.
    1.  Изменение созданного объекта групповой политики и переход к компонентам административных шаблонов политики конфигурации \\ \\ \\ :::no-loc text="Windows"::: компьютера \\ :::no-loc text="Windows PowerShell":::
    2.  Включив **выполнение сценария и** заключив для политики **выполнения** разрешение **локальных сценариев.**

6.  Настройте сценарий запуска:
    1.  Скопируйте следующий сценарий и сохраните его как Install-MMAgent.ps1.
    2.  Измените параметры WorkspaceId, WorkspaceKey и SetupPath в соответствие с конфигурацией.
    3.  Изменение того же объекта групповой политики и переход к политике конфигурации компьютера \\ \\ :::no-loc text="Windows"::: Параметры \\ сценариев (запуск и завершение работы)
    4.  Дважды щелкните, чтобы **выбрать Запуск**, а затем выберите **Сценарии PowerShell**.
    5.  Выберите **Показать файлы** и скопируйте **Install-MMAgent.ps1** в эту папку.
    6.  Выберите **Добавить**, а затем **Обзор**.
    7.  Выберите сценарий ps1, который вы только что скопировали.

7.  :::no-loc text="Microsoft Teams Rooms"::: следует установить и настроить агент :::no-loc text="Microsoft Monitoring"::: с помощью второй перезагрузки.

```PowerShell
# Install-MMAgent.ps1
<#
Date:        04/20/2018
Script:      Install-MMAgent.ps1
Version:     1.0
#>

# Set the parameters
$WorkspaceId = "<your workspace id>"
$WorkspaceKey = "<your workspace key>"
$SetupPath = "\\Server\Share"

$SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"

# $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"

# Start PowerShell logging
Start-Transcript -Path C:\Temp\MMA-Install.Log

# Check if the Microsoft Monitoring Agent is installed
$mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'

# Check if the Microsoft Monitoring agent is installed
if (!$mma)
{
    #Install agent
    Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
}

# Check if the agent has a valid configuration
$CheckMMA = $mma.GetCloudWorkspace($WorkspaceId).AgentId
if (!$CheckMMA)
{
    # Apply new configuration
    $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
    $mma.ReloadConfiguration()
}

Stop-Transcript
```

> [!NOTE]
> Если вам нужно [ :::no-loc text="Log Analytics"::: ](/azure/azure-monitor/platform/agent-manage) перенастроить агент, переместить его в другую область или изменить параметры прокси-сервера после первоначальной установки, обратитесь к статье Управление агентом и его обслуживание.

## <a name="additional-solutions"></a>Дополнительные решения
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: предоставляет встроенные решения для управления в [коллекции](/azure/azure-monitor/insights/solutions) решений, которые помогут вам следить за вашей средой. Настоятельно рекомендуется также добавить в [ :::no-loc text="Azure Log Analytics"::: ](/azure/azure-monitor/insights/solution-agenthealth) свою область [решения для](/azure/azure-monitor/platform/alert-management-solution) управления оповещениями и работы агентов.

> [!NOTE]
> Решение "Здоровье агента" помогает выявлять устаревшие или неавтоматные агенты в вашей среде, а решение для управления оповещениями содержит подробные сведения о оповещениях, которые были выданы в течение :::no-loc text="Microsoft Monitoring"::: определенного периода.

## <a name="see-also"></a>См. также

[Управление :::no-loc text="Microsoft Teams Rooms"::: планами с помощью :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Управление :::no-loc text="Microsoft Teams Rooms"::: устройствами с помощью :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
