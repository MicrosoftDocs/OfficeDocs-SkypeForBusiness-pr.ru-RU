---
title: Развертывание управления помещениями Microsoft Teams с помощью Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: В этой статье рассмотрено развертывание встроенного и комплексного управления устройствами комнат Microsoft Teams с помощью Azure Monitor.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b05c490c157c9f6530ca79ecdd8df19f15d94c68
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662104"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>Развертывание :::no-loc text="Microsoft Teams Rooms"::: управления с помощью :::no-loc text="Azure Monitor":::

В этой статье речь в этой статье говорится о том, как настроить и развернуть интегрированное комплексное управление устройствами :::no-loc text="Microsoft Teams Rooms"::: с :::no-loc text="Azure Monitor"::: помощью.

Вы можете настроить в этой области основные средства телеметрии и оповещения, которые помогут :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: вам управлять устройствами в комнате для :::no-loc text="Microsoft Teams Rooms"::: собраний. По мере взросления решения управления может потребоваться развернуть дополнительные данные и возможности управления, чтобы получить более подробное представление о доступности и производительности устройства.

Следуя этому руководству, вы можете использовать панель мониторинга, например, в следующем примере, чтобы получить подробные отчеты о доступности устройств, работоспособности приложений и оборудования, а также о распространении версий приложений и :::no-loc text="Microsoft Teams Rooms"::: операционных систем.

![Снимок экрана: образец представления аналитики журнала для комнат Microsoft Teams](../media/Deploy-Azure-Monitor-1.png "Пример представления аналитики журнала для комнат Microsoft Teams")

В общих чертах вам необходимо выполнить следующие задачи.


1. [Проверка :::no-loc text="Log Analytics"::: конфигурации](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Настройка тестовых устройств для :::no-loc text="Log Analytics"::: настройки управления](azure-monitor-deploy.md#configure_test_devices)
3. [Сопоставление настраиваемых полей](azure-monitor-deploy.md#Custom_fields)
4. [Определение :::no-loc text="Microsoft Teams Rooms"::: представлений в :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Определение оповещений](azure-monitor-deploy.md#Alerts)
6. [Настройка всех устройств для мониторинга](azure-monitor-deploy.md#configure_all_devices)
7. [Настройка дополнительных :::no-loc text="Azure Monitor"::: решений](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Хотя конфигурация минимальна, можно отслеживать компьютер с операционной системой, но перед развертыванием агентов на всех устройствах необходимо предпринять некоторые конкретные :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: :::no-loc text="Windows"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Teams Rooms"::: действия.
> Поэтому настоятельно рекомендуется выполнить все действия конфигурации в правильном порядке для управляемой настройки и настройки. Качество конечного результата во многом зависит от качества исходной конфигурации.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Проверка :::no-loc text="Log Analytics"::: конфигурации
<a name="validate_LogAnalytics"> </a>

Для сбора журналов с устройств необходимо иметь рабочее :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: пространство. Рабочее пространство — это уникальная среда со своим репозиторием :::no-loc text="Log Analytics"::: данных, источниками данных и решениями. Если у вас уже есть рабочее пространство, вы можете использовать его для отслеживания развертывания или как вариант, вы можете создать специальную рабочее пространство, предназначенное для :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: мониторинга.

Если вам нужно создать новую область, следуйте инструкциям в статье "Создание рабочей области :::no-loc text="Log Analytics"::: [на :::no-loc text="Log Analytics"::: :::no-loc text="Azure"::: портале".](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Для использования :::no-loc text="Log Analytics"::: с :::no-loc text="Azure Monitor"::: ним необходима активная :::no-loc text="Azure"::: подписка. Если у вас нет подписки, вы можете создать бесплатную пробную подписку :::no-loc text="Azure"::: в качестве отправной точки. [](https://azure.microsoft.com/free)

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Настройка сбора :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: журналов событий

:::no-loc text="Log Analytics"::: только собирает события из :::no-loc text="Windows"::: журналов событий, заданных в параметрах. Для каждого журнала собираются только события с выбранной серьезности.

Необходимо настроить сбор журналов, необходимых для отслеживания состояния устройства :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: и приложения. :::no-loc text="Microsoft Teams Rooms"::: используют журнал **:::no-loc text="Skype Room System":::** событий.

Сведения о :::no-loc text="Log Analytics"::: настройке сбора событий см. в источниках данных :::no-loc text="Microsoft Teams Rooms"::: журнала событий [ :::no-loc text="Windows"::: в :::no-loc text="Azure Monitor"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Снимок экрана: параметры журнала событий](../media/Deploy-Azure-Monitor-2.png "Параметры журнала событий")

> [!IMPORTANT]
> Настройте параметры журнала событий и введите его имя, а затем выберите флажки "Ошибка", "Предупреждение" и :::no-loc text="Windows"::: **:::no-loc text="Skype Room System":::** "Сведения".   

## <a name="configure-test-devices-for-azure-monitoring"></a>Настройка тестовых устройств для мониторинга Azure
<a name="configure_test_devices"> </a>

Вам нужно подготовиться :::no-loc text="Log Analytics"::: к отслеживанию :::no-loc text="Microsoft Teams Rooms"::: связанных событий. Для начала необходимо развернуть агентов только на одном или двух устройствах, к которые вы имеете физический доступ, и получить эти тестовые устройства, чтобы получить определенные данные и задвинуть их в :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: рабочее :::no-loc text="Log Analytics"::: пространство.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Установка :::no-loc text="Microsoft Monitoring"::: агентов для тестирования устройств

Развернйте агента на тестовых устройствах, используя инструкции, предоставленные в окне подключения компьютеров :::no-loc text="Microsoft Monitoring"::: [к :::no-loc text="Windows"::: :::no-loc text="Log Analytics"::: службе. :::no-loc text="Azure"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) В этой статье подробно описаны действия по развертыванию агента, инструкции по получению ИД рабочей области_ и первичный ключ для подключения устройств к развертыванию, а также инструкции по проверке подключения агента к :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows"::: :::no-loc text="Log Analytics":::  * ** _**_ :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: экземпляру.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Создание примеров :::no-loc text="Microsoft Teams Rooms"::: событий

После развертывания агента на тестовых устройствах убедитесь, что необходимые данные журнала событий :::no-loc text="Microsoft Monitoring"::: собраны. :::no-loc text="Azure Monitor":::

> [!NOTE]
> После установки агента перезагружаем устройство и убедитесь, что приложение "Собрание" запущено, чтобы создавать новые события :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: в журнале событий.

1.  Войдите на [ :::no-loc text="Microsoft Azure"::: портал, перейдите](https://portal.azure.com) к :::no-loc text="Log Analytics"::: рабочей области и выберите ее.

2.  Перечислить события пульса, созданные :::no-loc text="Microsoft Teams Rooms"::: устройством:
    1.  Выберите рабочее пространство, перейдите в поле *_Logs** и воспользуйтесь запросом для получения записей пульса, для которые будут иметься настраиваемые :::no-loc text="Microsoft Teams Rooms"::: поля.
    2.  Пример запроса: `Event | where Source == "SRS-App" and EventID == 2000`

3.  Убедитесь, что запрос возвращает записи журнала, включаемые события, созданные :::no-loc text="Microsoft Teams Rooms"::: приложением "Собрания".

4.  Создание проблемы с оборудованием и проверка входа в необходимые :::no-loc text="Azure Log Analytics"::: события.
    1.  Отключить одно из периферийных устройств в тестовой :::no-loc text="Microsoft Teams Rooms"::: системе. Это может быть камера, динамик, микрофон или экран переднего зала.
    2.  Подождите 10 минут, пока журнал событий не будет :::no-loc text="Azure Log Analytics"::: заполнен.
    3.  Использование запроса для перечислять события ошибок оборудования: `Event | where Source == "SRS-App" and EventID == 3001`

5.  Создание проблемы с приложением и проверка записи необходимых событий в журнале.
    1.  Измените конфигурацию приложения и введите неправильную пару адреса и пароля :::no-loc text="Microsoft Teams Rooms"::: протокола SIP.
    2.  Подождите 10 минут, пока журнал событий не будет :::no-loc text="Azure Log Analytics"::: заполнен.
    3.  Использование запроса для списка событий ошибок приложения: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Эти образцы журналов событий необходимы для настройки настраиваемых полей. Не переходите к следующему шагу, пока не соберет необходимые журналы событий.

## <a name="map-custom-fields"></a>Сопоставление настраиваемых полей
<a name="Custom_fields"> </a>

Настраиваемые поля используются для извлечения определенных данных из журналов событий. Необходимо определить настраиваемые поля, которые будут использоваться позже с плитками, представлениями панели мониторинга и оповещениями. Ознакомьтесь [с :::no-loc text="Log Analytics"::: настраиваемыми](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) полями и ознакомьтесь с понятиями, прежде чем приступить к созданию настраиваемой поля.

Чтобы извлечь настраиваемые поля из журналов событий:

1.  Войдите на [ :::no-loc text="Microsoft Azure"::: портал, перейдите](https://portal.azure.com) к :::no-loc text="Log Analytics"::: рабочей области и выберите ее.

2. Перечислить события, созданные :::no-loc text="Microsoft Teams Rooms"::: устройством:
   1.  Перейдите **в журналы** и используйте запрос для получения записей, которые будут иметь настраиваемые поля.
   2.  Пример запроса: `Event | where Source == "SRS-App" and EventID == 2000`

3. Выберите одну из записей, выберите кнопку слева и запустите мастер извлечения полей.
4. Выделение данных, которые нужно извлечь из renderedDescription, и предоставление названия поля. Имена полей, которые следует использовать, предоставляются в таблице 1.
5. Используйте сопоставления, показанные в *таблице 1.* :::no-loc text="Log Analytics":::будет автоматически включаем **\_ строку CF** при определении нового поля.

> [!IMPORTANT]
> Помните, что все поля jSON и JSON :::no-loc text="Log Analytics"::: в нихчувствительны к делу.
> 
> Обратите внимание на запросы, необходимые для каждого настраиваемного поля в таблице ниже. Для успешного извлечения значений настраиваемого поля необходимо использовать :::no-loc text="Log Analytics"::: правильные запросы.
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
| Состояние выступающего конференции        | SRSConfSpeakerStatus        | **3001**     | Событие, \| где Source == "SRS-App" и EventID == 3001 |
| Состояние динамика по умолчанию           | SRSDefaultSpeakerStatus     | **3001**     | Событие, \| где Source == "SRS-App" и EventID == 3001 |
| Состояние камеры                    | SRSCameraStatus             | **3001**     | Событие, \| где Source == "SRS-App" и EventID == 3001 |
| Перед состоянием "Отображение комнаты"     | SRSFORDStatus               | **3001**     | Событие, \| где Source == "SRS-App" и EventID == 3001 |
| Состояние датчика движений             | SRSMotionSensorStatus       | **3001**     | Событие, \| где Source == "SRS-App" и EventID == 3001 |
| Состояние "Ingest" в HDMI               | SRSHDMIIngestStatus         | **3001**     | Событие, \| где Source == "SRS-App" и EventID == 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Определение :::no-loc text="Microsoft Teams Rooms"::: представлений в :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

После сбора данных и применения настраиваемые поля можно использовать конструктор представлений для создания панелей мониторинга, содержащих различные плитки для отслеживания :::no-loc text="Microsoft Teams Rooms"::: событий. С помощью конструктора представлений можно создать следующие плитки: Дополнительные сведения см. в [теме :::no-loc text="Log Analytics"::: "Создание настраиваемой области с помощью конструктора представлений в"](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Чтобы плитки панелей мониторинга работали правильно, необходимо было завершить предыдущие шаги, как по этому руководству.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Создание панели мониторинга комнат Microsoft Teams с помощью метода импорта

Вы можете импортировать :::no-loc text="Microsoft Teams Rooms"::: панель мониторинга и быстро следить за своими устройствами. Чтобы импортировать панель мониторинга, с ее можно сделать следующее:

1.  Получите файл [SkypeRoomSystems_v2.omsview.](https://go.microsoft.com/fwlink/?linkid=835675)
2.  Войдите на [ :::no-loc text="Microsoft Azure"::: портал, перейдите](https://portal.azure.com) к :::no-loc text="Log Analytics"::: рабочей области и выберите ее.
3.  Открыть **конструктор представлений.**
4.  Выберите **"Импорт",** а затем выберите **файл SkypeRoomSystems_v2.omsview.**
5.  Выберите **"Сохранить".**

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Создание панели мониторинга комнат Microsoft Teams вручную

Кроме того, вы можете создать собственную информационную панель и добавить только плитки, которые вы хотите отслеживать.

#### <a name="configure-the-overview-tile"></a>Настройка плитки "Обзор"

1.  Открыть **конструктор представлений.**
2.  Выберите **плитку Overview** и выберите два **числа** из коллекции.
3.  Привязать плитку **:::no-loc text="Microsoft Teams Rooms":::** к имени.
4.  Определение **первой плитки:**<br>
    **Легенда:** Устройства, которые отправляли пульс по крайней мере один раз в течение последнего месяца<br>
    **Запрос:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Определение второй **плитки:**<br>
    **Легенда:** Активные устройства, отправив пульс в течение последнего часа<br>
    **Запрос:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Выберите **"Применить".**

### <a name="create-a-tile-that-displays-active-devices"></a>Создание плитки для отображения активных устройств

1.  Чтобы **добавить плитки,** выберите "Просмотр панели мониторинга".
2.  Выбор **& номера из** коллекции
3.  Определите **общие** свойства:<br>
    **Название группы:** Состояние Пульса<br>
    **Новая группа:** Выбрано
4.  Определите **свойства** плитки:<br>
    **Легенда:** Активные устройства (пульс, отправленный в течение последних 20 минут)<br>
    **Запрос для плитки:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Определите **свойства** списка:<br>
    **Запрос списка:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Определение **названий столбцов:**<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Last Heartbeat
7.  Определение **запроса навигации.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Выберите **"Применить"** и **"Закрыть".**

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Создание плитки, отображаемой для устройств с проблемой подключения

1.  Выберите **число & в** коллекции, а затем добавьте новую плитку.
2.  Определите **общие** свойства:<br>
    **Название группы:** Оставьте пустым<br>
    **Новая группа:** Не выбрано
3.  Определите **свойства** плитки:<br>
    **Легенда:** Неактивные устройства (за последние 20 минут не было отправлено сообщение пульса)<br>
    **Запрос для плитки:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Определите **свойства** списка:<br>
    **Запрос списка:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Определение **названий столбцов:**<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Last Heartbeat
6.  Определение **запроса навигации:**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Выберите **"Применить"** и **"Закрыть".**

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Создание плитки с отображением устройств с аппаратной ошибкой

1.  Выберите **число & в** коллекции, а затем добавьте новую плитку.
2.  Определите **общие** свойства:<br>
    **Название группы:** Состояние оборудования<br>
    **Новая группа:** Выбрано
3.  Определите **свойства** плитки:<br>
    **Легенда:** Устройства, на которые в последний час произошла ошибка оборудования<br>
    **Запрос для плитки:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Определите **свойства** списка:<br>
    **Запрос списка:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Определение **названий столбцов:**<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Последняя ошибка
6.  Определение **запроса навигации:**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Выберите **"Применить"** и **"Закрыть".**

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Создание плитки с :::no-loc text="Microsoft Teams Rooms"::: версиями операционной системы

1.  Выберите **"& из** коллекции", а затем добавьте новую плитку.
2.  Определите **общие** свойства:<br>
    **Название группы:** Сведения об операционной системе<br>
    **Новая группа:** Выбрано
3.  Определите **свойства загона:**<br>
    **Название:** Версии операционной системы<br>
    **Подзаголовок:** Устройства с определенными версиями ОС
4.  Определите **свойства donut:**<br>
    **Запрос:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Текст по центру:** Устройства<br>
    **Операция:** Сумма
5.  Определите **свойства** списка.<br>
    **Запрос списка:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Скрытие графика:** Выбрано<br>
    **В включить спарклины:** Не выбрано
6.  Определение **названий столбцов.**<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Оставьте пустым
7.  Определение **запроса навигации.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Выберите **"Применить",** а затем **"Закрыть".**

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Создание плитки с :::no-loc text="Microsoft Teams Rooms"::: версиями приложений

1.  Выберите **"& из** коллекции", а затем добавьте новую плитку.
2.  Определите **общие** свойства:<br>
    **Название группы:** :::no-loc text="Microsoft Teams Rooms"::: сведения о приложении<br>
    **Новая группа:** Выбрано
3.  Определите **свойства загона:**<br>
    **Название:** Версии приложений<br>
    **Подзаголовок:** Устройства с определенными версиями приложений
4.  Определите **свойства donut:**<br>
    **Запрос:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Текст по центру:** Устройства<br>
    **Операция:** Сумма
5.  Определите **свойства** списка.<br>
    **Запрос списка:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Скрытие графика:** Выбрано<br>
    **В включить спарклины:** Не выбрано
6.  Определение **названий столбцов.**<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Оставьте пустым
7.  Определение **запроса навигации.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Выберите **"Применить",** а затем **"Закрыть".**

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Создание плитки с отображением устройств с ошибкой приложения

1.  Выберите **число & в** коллекции, а затем добавьте новую плитку.
2.  Определите **общие** свойства.<br>
    **Название группы:** Оставьте пустым<br>
    **Новая группа:** Не выбрано
3.  Определите **свойства** плитки.<br>
    **Легенда:** Устройства, на которые в последний час произошла ошибка приложения<br>
    **Запрос для плитки:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Определите **свойства** списка.<br>
    **Запрос списка:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Определение **названий столбцов.**<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Последняя ошибка
6.  Определение **запроса навигации.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Выберите **"Применить",** а затем **"Закрыть".**

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Создание плитки для отображения перезагруженных устройств

1.  Выберите **число & в** коллекции, а затем добавьте новую плитку.
2.  Определите **общие** свойства.<br>
    **Название группы:** Оставьте пустым<br>
    **Новая группа:** Не выбрано
3.  Определите **свойства** плитки.<br>
    **Легенда:** Устройства, на которых приложение было перезапущено за последние 24 часа, и количество перезапусков<br>
    **Запрос для плитки:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Определите **свойства** списка.<br>
    **Запрос списка:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Определение **названий столбцов.**<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Количество перезапусков
6.  Определение **запроса навигации.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Выберите **"Применить",** а затем **"Закрыть".**
8.  Выберите **"Сохранить",** чтобы сохранить панель мониторинга.

Теперь вы завершили создание представлений.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Настройка оповещений в :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: может оповещать администраторов о проблеме с :::no-loc text="Microsoft Teams Rooms"::: консолью.

:::no-loc text="Azure Monitor"::: включает в себя встроенный механизм оповещения, который регулярно выполняется через запланированные поиски в журнале. Если результаты поиска по журналу соответствуют определенным условиям, создается запись оповещения.

После этого правило может автоматически выполнить одно или несколько действий, чтобы заблаговременно уведомить вас об оповещении или вызвать другой процесс. Возможные варианты оповещений:
-   Отправка сообщения электронной почты
-   Обращение к внешнему процессу с помощью HTTP-запроса POST
-   Запуск книги в :::no-loc text="Azure Automation"::: службе

Дополнительные [информацию :::no-loc text="Azure Monitor"::: об оповещениях см.](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) в журнале. :::no-loc text="Azure Monitor":::

> [!NOTE]
> В следующих примерах оповещения отправляются по электронной почте, если устройство вызывает :::no-loc text="Microsoft Teams Rooms"::: аппаратное оборудование или ошибку приложения.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Настройка оповещений электронной почты :::no-loc text="Microsoft Teams Rooms"::: о проблемах с оборудованием

Настройте правило оповещения, которое проверяет наличие устройств, на устройствах с которыми были проблемы с оборудованием :::no-loc text="Microsoft Teams Rooms"::: в течение последнего часа.
1.  Войдите на [ :::no-loc text="Microsoft Azure"::: портал, перейдите](https://portal.azure.com) к :::no-loc text="Log Analytics"::: рабочей области и выберите ее.

2. Перейдите в :::no-loc text="Log Analytics"::: свою область и выберите **"Оповещения",** а затем выберите **"Новое правило оповещения"**

3. Выберите **"Добавить условие",** а затем **"Настраиваемый поиск в журнале"**

4.  В текстовом поле "Поисковый запрос" введите следующий запрос:<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Настройте параметры логики оповещения.<br>
    **В зависимости от:** Количество результатов<br>
    **Условие:** Больше, чем<br>
    **Пороговое значение:** 0<br>

6. Настройте параметры оценки и выберите **"Готово":** <br>
    **Период (в минутах):** 60<br>
    **Частота (в минутах):** 60<br>

7. Настройка групп действий
    1.  Выберите **"Создать"**
    2.  В полях "Имя группы *действий"* и *"Короткое имя" в качестве подходящих имен в поле "Имя группы* действий".
    3.  Укажите уникальное имя *действия, выберите* "Электронная почта/SMS/Push/Голосовая почта", а затем выберите "Изменить  **сведения".**
    4.  Выберите **почтовый ящик** и укайте адрес электронной почты человека или группы, которые будут получать оповещения.
    5.  Вы также можете увести свой номер телефона, чтобы получать уведомления через SMS, голосовой звонок или и то, и другое.
    6. Выберите **"ОК".**

8. **Настройте действия,** если вам нравится переопределять тему сообщений электронной почты.

9. Укажите имя и описание правила.<br>
    **Имя правила:** :::no-loc text="Microsoft Teams Rooms"::: Оповещение о сбое оборудования<br>
    **Описание:** Список устройств, которые за последний час столкнулись с проблемой оборудования<br>

10. Выберите серьезность и убедитесь, что правило включено.

11. Выберите **"Создать правило оповещения".**

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Настройка оповещений по электронной почте :::no-loc text="Microsoft Teams Rooms"::: о проблемах с приложением

Повторите эту же процедуру, но используйте следующий запрос для списка устройств, на устройствах с которыми были проблемы с приложением в течение последнего часа.

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

Теперь вы завершили определение оповещений. Дополнительные оповещения можно определить с помощью примеров выше.

При этом вы получите сообщение электронной почты со списком устройств, с которыми у вас была проблема в течение последнего часа.

! [Пример :::no-loc text="Azure Monitor"::: сообщения электронной почты](.). /media/Deploy-Azure-Monitor-6.png "Sample :::no-loc text="Azure Monitor"::: alert email")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Настройка всех устройств для :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"></a> После настройки панелей мониторинга и оповещений вы можете настроить агент на всех устройствах для :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: завершения развертывания мониторинга.

Хотя агент можно установить и настроить вручную на каждом устройстве, настоятельно рекомендуется использовать существующие :::no-loc text="Microsoft Monitoring"::: средства развертывания программного обеспечения и методы.

Если вы создаете устройства в первый раз, в процессе сборки может потребоваться включить действия по настройке и настройке :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Monitoring"::: агента. Дополнительные сведения см. [в сведениях об установке агента с помощью командной строки.](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Развертывание :::no-loc text="Microsoft Monitoring"::: агента с помощью объекта групповой политики (GPO)

Если вы уже развернули свои устройства перед внедрением, вы можете использовать предоставленный сценарий для настройки агентов с помощью объектов :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring"::: :::no-loc text="Active Directory"::: групповой политики.

1.  Создайте общий сетевой путь и предоставить группе **Domain Computers** доступ для чтения.

2.  Скачайте 64-битную версию :::no-loc text="Microsoft Monitoring"::: агента из :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Извлекать содержимое пакета установки в обойму сети.
    1.  Откройте окно командной подсказки и выполните командуMMASetup-AMD64.exe **/c**
    2.  Укажите только что созданную обилие и извлекать содержимое.

4.  Создайте объект групповой политики и назначьте его подразделению, в котором находятся учетные :::no-loc text="Microsoft Teams Rooms"::: записи компьютера.

5.  Настройка политики выполнения PowerShell:
    1.  Изменение созданного объекта групповой политики и переход к компонентам административных шаблонов "Политики конфигурации \\ \\ \\ :::no-loc text="Windows"::: компьютера" \\:::no-loc text="Windows PowerShell":::
    2.  Включив **выполнение сценария и** заключив политику **выполнения,** **разрешив локальные сценарии.**

6.  Настройте сценарий запуска:
    1.  Скопируйте следующий сценарий и сохраните его как Install-MMAgent.ps1.
    2.  Измените параметры WorkspaceId, WorkspaceKey и SetupPath в соответствие с конфигурацией.
    3.  Изменение того же объекта групповой политики и переход к сценариям параметров политики конфигурации компьютера \\ \\ :::no-loc text="Windows"::: \\ (запуск и завершение работы)
    4.  Дважды щелкните, чтобы выбрать **"Запуск",** а затем — **"Сценарии PowerShell".**
    5.  Выберите **"Показать файлы"** и скопируйте **Install-MMAgent.ps1** файл в эту папку.
    6.  Выберите **"Добавить"** и **"Обзор".**
    7.  Выберите скопированный сценарий PS1.

7.  :::no-loc text="Microsoft Teams Rooms"::: необходимо установить и настроить агент :::no-loc text="Microsoft Monitoring"::: с помощью второй перезагрузки.

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
> Если вам нужно [ :::no-loc text="Log Analytics"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) перенастроить агент, переместить его в другую область или изменить параметры прокси-сервера после первоначальной установки, обратитесь к статье "Управление агентом и его обслуживанием".

## <a name="additional-solutions"></a>Дополнительные решения
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: содержит встроенные решения для управления с помощью [коллекции](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) решений, которые помогут вам следить за средой. Настоятельно рекомендуем также добавить в [ :::no-loc text="Azure Log Analytics"::: ](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) свою область решения [для](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) управления оповещениями и агентов.

> [!NOTE]
> Решение agent Health может помочь вам определить устаревших агентов в вашей среде, а решение для управления оповещениями предоставляет подробные сведения о оповещениях, которые были сдвещены в течение :::no-loc text="Microsoft Monitoring"::: данного периода.

## <a name="see-also"></a>См. также

[Управление :::no-loc text="Microsoft Teams Rooms"::: планами с помощью :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Управление :::no-loc text="Microsoft Teams Rooms"::: устройствами с помощью :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
