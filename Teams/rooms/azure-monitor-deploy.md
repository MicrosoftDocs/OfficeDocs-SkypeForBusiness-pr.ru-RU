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
- Teams_ITAdmin_Rooms
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: В этой статье описывается, как развернуть мониторинг Комнаты Microsoft Teams интегрированным и сквозным способом с помощью Azure Monitor.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5dbea45008024762f30d9555f4762c4377d2ed1f
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606418"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-monitoring-with-no-loc-textazure-monitor"></a>Развертывание :::no-loc text="Microsoft Teams Rooms"::: мониторинга с помощью :::no-loc text="Azure Monitor":::

В этой статье описывается, как настроить и развернуть :::no-loc text="Microsoft Teams Rooms"::: интегрированный сквозной мониторинг устройств с помощью :::no-loc text="Azure Monitor":::.

[!INCLUDE [teams-pro-license-requirement](../includes/teams-pro-license-requirement.md)]

Вы можете настроить в :::no-loc text="Log Analytics"::: пределах для :::no-loc text="Azure Monitor"::: предоставления базовой телеметрии и оповещений, которые помогут вам управлять :::no-loc text="Microsoft Teams Rooms":::. По мере развития решения для управления вы можете развернуть дополнительные возможности управления данными и данными, чтобы получить более подробное представление о доступности и производительности устройств.

Следуя этому руководству, вы можете использовать панель мониторинга, как в следующем примере, чтобы получить подробные отчеты о состоянии для доступности устройств, работоспособности приложений и оборудования, :::no-loc text="Microsoft Teams Rooms"::: а также распространения версий приложений и операционных систем.

![Снимок экрана: пример представления Log Analytics для Комнаты Microsoft Teams.](../media/Deploy-Azure-Monitor-1.png "Пример представления Log Analytics для Комнаты Microsoft Teams")

В общих чертах вам необходимо выполнить следующие задачи.


1. [Проверка конфигурации :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Настройка тестовых устройств для настройки :::no-loc text="Log Analytics"::: управления](azure-monitor-deploy.md#configure_test_devices)
3. [Сопоставление настраиваемых полей](azure-monitor-deploy.md#Custom_fields)
4. [Определение представлений :::no-loc text="Microsoft Teams Rooms"::: в :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Определение оповещений](azure-monitor-deploy.md#Alerts)
6. [Настройка всех устройств для мониторинга](azure-monitor-deploy.md#configure_all_devices)
7. [Настройка дополнительных решений :::no-loc text="Azure Monitor":::](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Несмотря на минимальную конфигурацию, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: :::no-loc text="Windows"::: можно отслеживать компьютер под управлением операционной системы, :::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Microsoft Teams Rooms"::: но перед началом развертывания агентов на всех устройствах необходимо выполнить определенные действия.
> Поэтому мы настоятельно рекомендуем выполнить все действия по настройке в правильном порядке для управляемой настройки и конфигурации. Качество конечного результата во многом зависит от качества начальной конфигурации.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Проверка конфигурации :::no-loc text="Log Analytics":::
<a name="validate_LogAnalytics"> </a>

Для начала сбора :::no-loc text="Log Analytics"::: журналов необходимо иметь рабочую область :::no-loc text="Microsoft Teams Rooms":::. Рабочая область — это уникальная среда :::no-loc text="Log Analytics"::: с собственным репозиторием данных, источниками данных и решениями. Если у вас уже есть :::no-loc text="Log Analytics"::: рабочая область, :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: вы можете использовать ее для мониторинга развертывания или создать выделенную рабочую область, относящуюся к вашим потребностям мониторинга.

Если необходимо создать рабочую :::no-loc text="Log Analytics"::: область, [:::no-loc text="Log Analytics"::: следуйте инструкциям в статье "Создание рабочей области на портале:::no-loc text="Azure":::".](/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Чтобы использовать :::no-loc text="Log Analytics"::: его :::no-loc text="Azure Monitor":::, необходимо иметь активную подписку :::no-loc text="Azure"::: . Если у вас нет подписки :::no-loc text="Azure"::: , вы можете создать бесплатную пробную подписку [в качестве](https://azure.microsoft.com/free) отправной точки.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Настройка сбора :::no-loc text="Log Analytics"::: журналов :::no-loc text="Microsoft Teams Rooms"::: событий

:::no-loc text="Log Analytics"::: собирает только события из журналов :::no-loc text="Windows"::: событий, указанных в параметрах. Для каждого журнала собираются только события с выбранными уровнями серьезности.

Необходимо настроить сбор журналов :::no-loc text="Log Analytics"::: , необходимых для :::no-loc text="Microsoft Teams Rooms"::: мониторинга состояния устройства и приложения. :::no-loc text="Microsoft Teams Rooms"::: используйте журнал **:::no-loc text="Skype Room System":::** событий.

Сведения о настройке :::no-loc text="Log Analytics"::: сбора событий см :::no-loc text="Microsoft Teams Rooms"::: [:::no-loc text="Windows"::: . в источниках данных журнала событий в :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/data-sources-windows-events)

![Снимок экрана: параметры журнала событий.](../media/Deploy-Azure-Monitor-2.png "Параметры журнала событий")

> [!IMPORTANT]
> Настройте :::no-loc text="Windows"::: параметры журнала событий **:::no-loc text="Skype Room System":::** и введите имя журнала событий, а затем установите флажки **"** Ошибка", **"** Предупреждение **" и "** Сведения".

## <a name="configure-test-devices-for-azure-monitoring"></a>Настройка тестовых устройств для мониторинга Azure
<a name="configure_test_devices"> </a>

Необходимо подготовиться, :::no-loc text="Log Analytics"::: чтобы иметь возможность отслеживать связанные :::no-loc text="Microsoft Teams Rooms":::события. Для начала необходимо :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: развернуть агенты на одном или двух устройствах, к которых у вас есть физический доступ, :::no-loc text="Log Analytics"::: и получить эти тестовые устройства для создания некоторых данных и отправки их в рабочую область.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Установка агентов :::no-loc text="Microsoft Monitoring"::: для тестирования устройств

Разверните :::no-loc text="Microsoft Monitoring"::: агент на тестовых устройствах[:::no-loc text="Windows":::, следуя инструкциям, приведенным в разделе "Подключение компьютеров к службе:::no-loc text="Log Analytics":::":::no-loc text="Azure":::](/azure/azure-monitor/platform/agent-windows). В этой статье приводятся подробные сведения о действиях по развертыванию агента для, :::no-loc text="Log Analytics"::: * инструкции по получении идентификатора рабочей **области и _***_первичного_* ключа* :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: для подключения устройств к развертыванию, :::no-loc text="Log Analytics"::: а также инструкции по проверке подключения агента к экземпляру.:::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows":::

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Создание примеров :::no-loc text="Microsoft Teams Rooms"::: событий

После развертывания :::no-loc text="Microsoft Monitoring"::: агента на тестовых устройствах убедитесь, что необходимые данные журнала событий собираются :::no-loc text="Azure Monitor":::.

> [!NOTE]
> Перезагрузите :::no-loc text="Microsoft Monitoring"::: устройство после установки агента и убедитесь, :::no-loc text="Microsoft Teams Rooms"::: что приложение для собраний запущено, чтобы оно можно было создавать новые события в журнале событий.

1.  Войдите на портал [:::no-loc text="Microsoft Azure"::: и](https://portal.azure.com) перейдите в :::no-loc text="Log Analytics"::: рабочую область и выберите ее.

2.  Список событий пульса, созданных устройством :::no-loc text="Microsoft Teams Rooms"::: :
    1.  Выберите рабочую область, перейдите **в** журналы и используйте запрос для получения записей пульса, для которых будут использоваться настраиваемые поля :::no-loc text="Microsoft Teams Rooms":::.
    2.  Пример запроса: `Event | where Source == "SRS-App" and EventID == 2000`

3.  Убедитесь, что запрос возвращает записи журнала, включаемые события, созданные приложением :::no-loc text="Microsoft Teams Rooms"::: для собраний.

4.  Создайте проблему с оборудованием и убедитесь, что необходимые события вошли в систему :::no-loc text="Azure Log Analytics":::.
    1.  Отключите одно из периферийных устройств в тестовой :::no-loc text="Microsoft Teams Rooms"::: системе. Это может быть камера, динамик, микрофон или экран передней комнаты.
    2.  Подождите 10 минут, пока журнал событий будет заполнен :::no-loc text="Azure Log Analytics":::.
    3.  Используйте запрос для перечисления событий ошибок оборудования: `Event | where Source == "SRS-App" and EventID == 3001`

5.  Создайте проблему с приложением и убедитесь, что необходимые события регистрируются в журнале.
    1.  Измените :::no-loc text="Microsoft Teams Rooms"::: конфигурацию учетной записи и введите неправильную пару Email/пароль.
    2.  Подождите 10 минут, пока журнал событий будет заполнен :::no-loc text="Azure Log Analytics":::.
    3.  Используйте запрос для перечисления событий ошибок приложения: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Эти примеры журналов событий необходимы для настройки настраиваемых полей. Не переходите к следующему шагу, пока не соберите необходимые журналы событий.

## <a name="map-custom-fields"></a>Сопоставление настраиваемых полей
<a name="Custom_fields"> </a>

Пользовательские поля используются для извлечения определенных данных из журналов событий. Необходимо определить настраиваемые поля, которые будут использоваться позже с плитками, представлениями панели мониторинга и оповещениями. [Ознакомьтесь с настраиваемыми полями :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/custom-fields) и ознакомьтесь с основными понятиями, прежде чем приступить к созданию настраиваемых полей.

Чтобы извлечь настраиваемые поля из записанных журналов событий, выполните следующие действия.

1.  Войдите на портал [:::no-loc text="Microsoft Azure"::: и](https://portal.azure.com) перейдите в :::no-loc text="Log Analytics"::: рабочую область и выберите ее.

2. Список событий, созданных устройством :::no-loc text="Microsoft Teams Rooms"::: :
   1.  Перейдите **в раздел "** Журналы" и используйте запрос для получения записей, которые будут иметь настраиваемое поле.
   2.  Пример запроса: `Event | where Source == "SRS-App" and EventID == 2000`

3. Выберите одну из записей, нажмите кнопку слева и запустите мастер извлечения полей.
4. Выделите данные, которые вы хотите извлечь из renderedDescription, и укажите заголовок поля. Имена полей, которые следует использовать, указаны в таблице 1.
5. Используйте сопоставления, показанные *в таблице 1*. :::no-loc text="Log Analytics"::: автоматически добавляет строку **\_CF** при создании нового поля.

> [!IMPORTANT]
> Помните, что все JSON и :::no-loc text="Log Analytics"::: поля чувствительны к регистру.
> 
> Обратите внимание на запросы, необходимые для каждого настраиваемого поля в таблице ниже. Для успешного извлечения :::no-loc text="Log Analytics"::: значений настраиваемых полей необходимо использовать правильные запросы.
> 
**Таблица 1**

| **Поле JSON**                   | **:::no-loc text="Log Analytics"::: настраиваемое поле** | **Идентификатор события** | **Запрос для использования с извлечением**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Описание                      | SRSEventDescription         | **2000**     | Событие \| , где source == "SRS-App" и EventID == 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Событие \| , где source == "SRS-App" и EventID == 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Событие \| , где source == "SRS-App" и EventID == 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Событие \| , где source == "SRS-App" и EventID == 2000 |
| OS                               | SRSOSVersion                | **2000**     | Событие \| , где source == "SRS-App" и EventID == 2000 |
| Версия ОС                        | SRSOSLongVersion            | **2000**     | Событие \| , где source == "SRS-App" и EventID == 2000 |
| Alias                            | SRSAlias                    | **2000**     | Событие \| , где source == "SRS-App" и EventID == 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Событие \| , где source == "SRS-App" и EventID == 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Событие \| , где source == "SRS-App" и EventID == 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Событие \| , где source == "SRS-App" и EventID == 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Событие \| , где source == "SRS-App" и EventID == 2000 |
| Состояние микрофона конференции     | SRSConfMicrophoneStatus     | **3001**     | Событие \| , где source == "SRS-App" и EventID == 3001 |
| Состояние докладчика конференции        | SRSConfSpeakerStatus        | **3001**     | Событие \| , где source == "SRS-App" и EventID == 3001 |
| Состояние говорящего по умолчанию           | SRSDefaultSpeakerStatus     | **3001**     | Событие \| , где source == "SRS-App" и EventID == 3001 |
| Состояние камеры                    | SRSCameraStatus             | **3001**     | Событие \| , где source == "SRS-App" и EventID == 3001 |
| Состояние отображения в передней части комнаты     | SRSFORDStatus               | **3001**     | Событие \| , где source == "SRS-App" и EventID == 3001 |
| Состояние датчика движения             | SRSMotionSensorStatus       | **3001**     | Событие \| , где source == "SRS-App" и EventID == 3001 |
| Состояние приема HDMI               | SRSHDMIIngestStatus         | **3001**     | Событие \| , где source == "SRS-App" и EventID == 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Определение представлений :::no-loc text="Microsoft Teams Rooms"::: в :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

После сбора данных и сопоставления настраиваемых полей можно использовать конструктор представлений для разработки панели мониторинга, содержащей различные плитки для мониторинга :::no-loc text="Microsoft Teams Rooms"::: событий. Используйте конструктор представлений для создания следующих плиток. Дополнительные сведения см. в разделе ["Создание пользовательских представлений с помощью конструктора представлений в :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Для правильной работы плиток панели мониторинга должны быть выполнены предыдущие шаги в этом руководстве.
>
> [!IMPORTANT]
> [Конструктор представлений в Azure Monitor прекращает работу 31 августа 2023](https://azure.microsoft.com/updates/view-designer-in-azure-monitor-is-retiring-on-31-august-2023/) г., а функции создания и клонирования отключены 30 ноября 2020 г. Вместо этого можно использовать книги. Дополнительные сведения о переходе конструктора представлений на книги см. в кратком руководстве по шаблонам конструктора [предустановки представлений](/azure/azure-monitor/visualize/view-designer-conversion-tasks#quickstart-with-preset-view-designer-templates).

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Создание панели мониторинга Комнаты Microsoft Teams вручную

Кроме того, можно создать собственную панель мониторинга и добавить только плитки, которые вы хотите отслеживать.

#### <a name="configure-the-overview-tile"></a>Настройка плитки "Обзор"

1.  Откройте **конструктор представлений**.
2.  Выберите **плитку "Обзор**", а затем выберите **два числа** из коллекции.
3.  Приведите имя плитке **:::no-loc text="Microsoft Teams Rooms":::**.
4.  Определите **первую плитку**:<br>
    **Легенда:** Устройства, отправив пульс по крайней мере один раз в течение последнего месяца<br>
    **Запроса:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Определите **вторую плитку**:<br>
    **Легенда:** Активные устройства, отправив пульс за последний час<br>
    **Запроса:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Нажмите **Применить**.

### <a name="create-a-tile-that-displays-active-devices"></a>Создание плитки, отображаемой на активных устройствах

1.  Выберите **"Просмотреть панель мониторинга** ", чтобы начать добавлять плитки.
2.  Выбор **списка & номеров** из коллекции
3.  Определите **общие** свойства:<br>
    **Название группы:** Состояние пульса<br>
    **Новая группа:** Выбранного
4.  Определите **свойства** плитки:<br>
    **Легенда:** Активные устройства (пакет пульса отправлен за последние 20 минут)<br>
    **Запрос для плитки:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Определите **свойства** списка:<br>
    **Запрос списка:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Определение **заголовков столбцов**:<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Последний пульс
7.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Нажмите **кнопку "Применить**", а затем **закройте.**

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Создание плитки, отображающее устройства, у которых есть проблемы с подключением

1.  Выберите **"&" из** коллекции, а затем добавьте новую плитку.
2.  Определите **общие** свойства:<br>
    **Название группы:** Оставьте пустым<br>
    **Новая группа:** Не выбрано
3.  Определите **свойства** плитки:<br>
    **Легенда:** Неактивные устройства (за последние 20 минут сообщение пульса не отправлялся)<br>
    **Запрос для плитки:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Определите **свойства** списка:<br>
    **Запрос списка:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Определение **заголовков столбцов**:<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Последний пульс
6.  Определение **запроса навигации**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Нажмите **кнопку "Применить**", а затем **закройте.**

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Создание плитки, отображаемой на устройствах с аппаратной ошибкой

1.  Выберите **"&" из** коллекции, а затем добавьте новую плитку.
2.  Определите **общие** свойства:<br>
    **Название группы:** Состояние оборудования<br>
    **Новая группа:** Выбранного
3.  Определите **свойства** плитки:<br>
    **Легенда:** Устройства, на которых произошла ошибка оборудования за последний час<br>
    **Запрос для плитки:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Определите **свойства** списка:<br>
    **Запрос списка:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Определение **заголовков столбцов**:<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Последняя ошибка
6.  Определение **запроса навигации**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Нажмите **кнопку "Применить**", а затем **закройте.**

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Создание плитки с версиями :::no-loc text="Microsoft Teams Rooms"::: операционной системы

1.  Выберите **donut & из** коллекции, а затем добавьте новую плитку.
2.  Определите **общие** свойства:<br>
    **Название группы:** Сведения об операционной системе<br>
    **Новая группа:** Выбранного
3.  Определите **свойства заголовка** :<br>
    **Название:** Версии операционной системы<br>
    **Субтитров:** Устройства под управлением определенных версий ОС
4.  Определите **свойства кольцевой** диаграммы:<br>
    **Запроса:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Текст по центру:** Устройств<br>
    **Операции:** Сумма
5.  Определите **свойства** списка.<br>
    **Запрос списка:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Скрыть граф:** Выбранного<br>
    **Включите спарклайны:** Не выбрано
6.  Определение **заголовков столбцов**.<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Оставьте пустым
7.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Нажмите **кнопку "Применить**", а затем **закройте.**

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Создание плитки, отображаемой в :::no-loc text="Microsoft Teams Rooms"::: версиях приложения

1.  Выберите **donut & из** коллекции, а затем добавьте новую плитку.
2.  Определите **общие** свойства:<br>
    **Название группы:** :::no-loc text="Microsoft Teams Rooms"::: сведения о приложении<br>
    **Новая группа:** Выбранного
3.  Определите **свойства заголовка** :<br>
    **Название:** Версии приложений<br>
    **Субтитров:** Устройства под управлением определенных версий приложений
4.  Определите **свойства кольцевой** диаграммы:<br>
    **Запроса:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Текст по центру:** Устройств<br>
    **Операции:** Сумма
5.  Определите **свойства** списка.<br>
    **Запрос списка:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Скрыть граф:** Выбранного<br>
    **Включите спарклайны:** Не выбрано
6.  Определение **заголовков столбцов**.<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Оставьте пустым
7.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Нажмите **кнопку "Применить**", а затем **закройте.**

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Создание плитки, отображаемой на устройствах с ошибкой приложения

1.  Выберите **"&" из** коллекции, а затем добавьте новую плитку.
2.  Определите **общие** свойства.<br>
    **Название группы:** Оставьте пустым<br>
    **Новая группа:** Не выбрано
3.  Определите **свойства** плитки.<br>
    **Легенда:** Устройства, на которых произошла ошибка приложения за последний час<br>
    **Запрос для плитки:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Определите **свойства** списка.<br>
    **Запрос списка:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Определение **заголовков столбцов**.<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Последняя ошибка
6.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Нажмите **кнопку "Применить**", а затем **закройте.**

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Создание плитки, отображающее устройства, которые были перезапущены

1.  Выберите **"&" из** коллекции, а затем добавьте новую плитку.
2.  Определите **общие** свойства.<br>
    **Название группы:** Оставьте пустым<br>
    **Новая группа:** Не выбрано
3.  Определите **свойства** плитки.<br>
    **Легенда:** Устройства, на которых приложение было перезапущено за последние 24 часа, и количество перезапусков<br>
    **Запрос для плитки:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Определите **свойства** списка.<br>
    **Запрос списка:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Определение **заголовков столбцов**.<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Число перезапусков
6.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Нажмите **кнопку "Применить**", а затем **закройте.**
8.  Нажмите **кнопку "** Сохранить", чтобы сохранить панель мониторинга.

Теперь вы завершили создание представлений.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Настройка оповещений в :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: может создавать оповещения для уведомления администраторов при :::no-loc text="Microsoft Teams Rooms"::: возникновении проблемы в консоли.

:::no-loc text="Azure Monitor"::: включает встроенный механизм генерации оповещений, который выполняется через запланированные поиски по журналам через регулярные интервалы. Если результаты поиска по журналам соответствуют определенным критериям, создается запись оповещения.

Затем правило может автоматически выполнить одно или несколько действий, чтобы заранее уведомить вас об оповещении или вызвать другой процесс. Возможные варианты с оповещениями:
-   Отправка сообщения электронной почты
-   Вызов внешнего процесса с помощью HTTP-запроса POST
-   Запуск модуля Runbook в службе :::no-loc text="Azure Automation":::

[Дополнительные сведения об оповещениях см:::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/alerts-unified-log). в разделе "Оповещения журнала":::no-loc text="Azure Monitor":::.

> [!NOTE]
> В следующих примерах отправляются оповещения по электронной :::no-loc text="Microsoft Teams Rooms"::: почте, когда устройство создает ошибку оборудования или приложения.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Настройка оповещения по электронной почте для проблем :::no-loc text="Microsoft Teams Rooms"::: с оборудованием

Настройте правило генерации оповещений, которое проверяет устройства :::no-loc text="Microsoft Teams Rooms"::: , на которых возникли проблемы с оборудованием за последний час.
1.  Войдите на портал [:::no-loc text="Microsoft Azure"::: и](https://portal.azure.com) перейдите в :::no-loc text="Log Analytics"::: рабочую область и выберите ее.

2. Перейдите в рабочую :::no-loc text="Log Analytics"::: область, выберите **"Оповещения**", а затем выберите **"Новое правило генерации оповещений"**.

3. Выберите **"Добавить условие"** , а затем **пользовательский поиск по журналам**

4.  Введите следующий запрос в текстовое поле поискового запроса.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Настройте параметры логики оповещений:<br>
    **На основе:** Количество результатов<br>
    **Состояние:** Больше<br>
    **Пороговое значение:** 0<br>

6. Настройте параметры оценки и выберите " **Готово"**: <br>
    **Период (в минутах):** 60<br>
    **Частота (в минутах):** 60<br>

7. Настройте группы действий:
    1.  Выберите **"Создать"**
    2.  Укажите подходящие имена для полей *"Имя группы действий"* *и "Короткое имя* ".
    3.  Укажите уникальное *имя действия и* выберите **Email/ SMS/Push/Voice**, а затем нажмите кнопку **"Изменить сведения"**.
    4.  Установите **флажок Email** и укажите адрес электронной почты пользователя или группы, которые будут получать оповещения.
    5.  Вы также можете указать свой номер телефона, чтобы получать уведомления с помощью SMS, голосового звонка или обоих звонков.
    6. Нажмите **кнопку "ОК"**.

8. **Настройте действия** , если хотите переопределить строку темы оповещений.

9. Укажите имя и описание правила.<br>
    **Имя правила:** :::no-loc text="Microsoft Teams Rooms"::: Оповещение об ошибке оборудования<br>
    **Описание:** Список устройств, на которых возникла проблема с оборудованием за последний час<br>

10. Выберите требуемую серьезность и убедитесь, что правило включено.

11. Выберите " **Создать правило генерации оповещений"**.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Настройка оповещения по электронной почте для проблем :::no-loc text="Microsoft Teams Rooms"::: с приложением

Повторите ту же процедуру, но используйте следующий запрос, чтобы получить список устройств, на которых возникли проблемы с приложением в течение последнего часа.

 ```
 Event
 | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
 | summarize arg_max(TimeGenerated, *) by Computer
 | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
 | sort by TimeGenerated desc
 ```

Теперь вы завершили определение оповещений. Дополнительные оповещения можно определить с помощью приведенных выше примеров.

При создании оповещения вы получите сообщение электронной почты, в котором перечислены устройства, на которых возникла проблема в течение последнего часа.

! [Пример сообщения :::no-loc text="Azure Monitor"::: электронной почты с оповещением](.. /media/Deploy-Azure-Monitor-6.png "Sample :::no-loc text="Azure Monitor"::: alert email")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Настройка всех устройств для :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a> После настройки панелей мониторинга и оповещений можно :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: настроить агент на всех устройствах для завершения развертывания мониторинга.

Хотя агент можно установить и настроить :::no-loc text="Microsoft Monitoring"::: вручную на каждом устройстве, настоятельно рекомендуется использовать существующие средства и методы развертывания программного обеспечения.

Если вы создаете устройства :::no-loc text="Microsoft Teams Rooms"::: в первый раз, :::no-loc text="Microsoft Monitoring"::: вам может потребоваться включить в процесс сборки этапы настройки и настройки агента. Дополнительные сведения см. в [статье "Установка агента с помощью командной строки"](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Развертывание :::no-loc text="Microsoft Monitoring"::: агента с помощью объекта групповая политика (GPO)

Если вы уже развернули :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring":::устройства перед реализацией, :::no-loc text="Active Directory"::: можно использовать предоставленный скрипт для настройки агентов с помощью объектов групповой политики.

1.  Создайте общий сетевой путь и предоставьте доступ на чтение группе **"Компьютеры домена** ".

2.  Скачайте 64-разрядную версию :::no-loc text="Microsoft Monitoring"::: агента из :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Извлеките содержимое пакета установки в сетевую папку.
    1.  Откройте окно командной строки и выполните команду **MMASetup-AMD64.exe /c**
    2.  Укажите только что созданную общую папку и извлеките содержимое.

4.  Создайте новый объект групповая политика и назначьте его :::no-loc text="Microsoft Teams Rooms"::: подразделению, в котором находятся учетные записи компьютеров.

5.  Настройте политику выполнения PowerShell:
    1.  Измените только что созданный объект групповая политика и перейдите к компонентам административных \\ \\ шаблонов политик конфигурации \\ :::no-loc text="Windows"::: компьютеров \\ :::no-loc text="Windows PowerShell":::
    2.  **Включите включение выполнения скрипта и** **задайте для политики выполнения** разрешение **локальных скриптов**.

6.  Настройте скрипт запуска:
    1.  Скопируйте следующий скрипт и сохраните его как Install-MMAgent.ps1.
    2.  Измените параметры WorkspaceId, WorkspaceKey и SetupPath в соответствии с конфигурацией.
    3.  Измените тот же групповая политика и перейдите к скриптам \\ \\ :::no-loc text="Windows"::: \\ параметров политик конфигурации компьютера (запуск и завершение работы)
    4.  Дважды щелкните, чтобы выбрать **"Запуск**", а затем **выберите сценарии PowerShell**.
    5.  Выберите **"Показать файлы**", а затем **скопируйтеInstall-MMAgent.ps1** в эту папку.
    6.  Нажмите **кнопку "** Добавить" и выберите " **Обзор"**.
    7.  Выберите сценарий ps1, который вы только что скопировали.

7.  :::no-loc text="Microsoft Teams Rooms"::: следует установить и настроить агент :::no-loc text="Microsoft Monitoring"::: со второй перезагрузкой.

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
> Если необходимо [:::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/agent-manage) перенастроить агент, переместить его в другую рабочую область или изменить параметры прокси-сервера после начальной установки, см. статью об управлении агентом и его обслуживании.

## <a name="additional-solutions"></a>Дополнительные решения
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: предоставляет встроенные решения по управлению с [помощью коллекции](/azure/azure-monitor/insights/solutions) решений для дальнейшего мониторинга среды. Настоятельно рекомендуется также добавить в рабочую область решения [для](/azure/azure-monitor/platform/alert-management-solution) [:::no-loc text="Azure Log Analytics":::](/azure/azure-monitor/insights/solution-agenthealth) управления оповещениями и работоспособности агентов.

> [!NOTE]
> Решение " :::no-loc text="Microsoft Monitoring"::: Работоспособность агента" может помочь определить устаревшие или неработающие агенты в вашей среде, а решение "Управление оповещениями" предоставляет сведения об оповещениях, которые были вызваны в течение заданного периода.

## <a name="see-also"></a>См. также

[Управление планами :::no-loc text="Microsoft Teams Rooms"::: с помощью :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Управление устройствами :::no-loc text="Microsoft Teams Rooms"::: с помощью :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
