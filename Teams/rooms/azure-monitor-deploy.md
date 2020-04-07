---
title: Развертывание управления комнатами Microsoft Teams с помощью монитора Azure
ms.author: v-lanac
author: lanachin
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
description: В этой статье рассказывается, как развернуть управление устройствами в Microsoft Teams с помощью монитора Azure.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0e0e810bb2932918947a011a9d2091858d0819eb
ms.sourcegitcommit: 0fdc60840f45ff5b0a39a8ec4a21138f6cab49c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2020
ms.locfileid: "43160093"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>Управление :::no-loc text="Microsoft Teams Rooms"::: развертыванием с помощью:::no-loc text="Azure Monitor":::

В этой статье рассказывается о том, как настраивать и развертывать интегрированные и законченные средства :::no-loc text="Microsoft Teams Rooms"::: управления устройствами с :::no-loc text="Azure Monitor":::помощью.

Вы можете настроить :::no-loc text="Log Analytics"::: в :::no-loc text="Azure Monitor"::: рамках для предоставления базовой телеметрии и оповещений, которые помогут :::no-loc text="Microsoft Teams Rooms"::: вам управлять устройствами для помещения на собрание. По мере того как ваше решение для управления будет превышено, вы можете развернуть дополнительные возможности данных и управления, чтобы создать более подробное представление о доступности и быстродействии устройства.

Следуя этим инструкциям, вы можете использовать панель мониторинга, как в следующем примере, чтобы получить подробные сведения о состоянии доступности устройства, работоспособности приложения и оборудования :::no-loc text="Microsoft Teams Rooms"::: , а также о распределении версий приложений и операционной системы.

![Снимок экрана: образец аналитического журнала для комнат Microsoft Teams](../media/Deploy-Azure-Monitor-1.png "Образец аналитического журнала для комнат Microsoft Teams")

В общих чертах вам необходимо выполнить следующие задачи.


1. [Проверка :::no-loc text="Log Analytics"::: конфигурации](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Настройка тестовых устройств :::no-loc text="Log Analytics"::: для настройки управления](azure-monitor-deploy.md#configure_test_devices)
3. [Сопоставление настраиваемых полей](azure-monitor-deploy.md#Custom_fields)
4. [Определение :::no-loc text="Microsoft Teams Rooms"::: представлений в:::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Определение оповещений](azure-monitor-deploy.md#Alerts)
6. [Настройка наблюдения для всех устройств](azure-monitor-deploy.md#configure_all_devices)
7. [Настройка дополнительных :::no-loc text="Azure Monitor"::: решений](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Несмотря на то, что :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: с минимальной конфигурацией может наблюдать :::no-loc text="Windows"::: за компьютером под управлением операционной системы, :::no-loc text="Microsoft Teams Rooms":::некоторые действия, которые необходимо выполнить перед развертыванием агентов на всех :::no-loc text="Microsoft Teams Rooms"::: устройствах, не зависят от того, что нужно сделать.
> Поэтому мы настоятельно рекомендуем выполнить все действия по настройке в правильном порядке для управления установкой и конфигурацией. Качество конечного результата очень сильно зависит от качества начальной конфигурации.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Проверка :::no-loc text="Log Analytics"::: конфигурации
<a name="validate_LogAnalytics"> </a>

Для сбора журналов с :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: устройств необходимо иметь рабочую область. Рабочая область — это уникальная :::no-loc text="Log Analytics"::: среда с собственным хранилищем данных, источниками данных и решениями. Если у вас уже :::no-loc text="Log Analytics"::: есть рабочая область, вы можете использовать ее для наблюдения за :::no-loc text="Microsoft Teams Rooms"::: развертыванием, а также создать специальную :::no-loc text="Log Analytics"::: рабочую область, относящуюся к :::no-loc text="Microsoft Teams Rooms"::: вашим потребностям мониторинга.

Если вам нужно создать :::no-loc text="Log Analytics"::: рабочую область, следуйте инструкциям, приведенным в статье [Создание :::no-loc text="Log Analytics"::: рабочей области на :::no-loc text="Azure"::: портале](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Для использования :::no-loc text="Log Analytics"::: с :::no-loc text="Azure Monitor":::этим вам необходимо иметь активную :::no-loc text="Azure"::: подписку. Если у вас нет :::no-loc text="Azure"::: подписки на план, вы можете создать [бесплатную пробную подписку](https://azure.microsoft.com/free) в качестве отправной точки.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Настройка :::no-loc text="Log Analytics"::: сбора :::no-loc text="Microsoft Teams Rooms"::: журналов событий

:::no-loc text="Log Analytics":::собирает только события из журналов :::no-loc text="Windows"::: событий, указанных в параметрах. Для каждого журнала собираются только события, для которых выбраны определенные серьезности.

Необходимо настроить :::no-loc text="Log Analytics"::: для сбора журналов, необходимых для наблюдения за :::no-loc text="Microsoft Teams Rooms"::: состоянием устройства и приложения. :::no-loc text="Microsoft Teams Rooms":::устройства используют журнал **:::no-loc text="Skype Room System":::** событий.

Чтобы настроить :::no-loc text="Log Analytics"::: сбор :::no-loc text="Microsoft Teams Rooms"::: событий, просмотрите [ :::no-loc text="Windows"::: источники данных журнала событий в :::no-loc text="Azure Monitor"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Снимок экрана: параметры журнала событий](../media/Deploy-Azure-Monitor-2.png "Параметры журнала событий")

> [!IMPORTANT]
> Настройте :::no-loc text="Windows"::: параметры журнала событий и введите **:::no-loc text="Skype Room System":::** имя журнала событий, а затем установите флажки **Ошибка**, **предупреждение**и **сведения** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Настройка тестовых устройств для мониторинга Azure
<a name="configure_test_devices"> </a>

Вам необходимо подготовиться :::no-loc text="Log Analytics"::: к отслеживанию событий :::no-loc text="Microsoft Teams Rooms":::, связанных с отслеживанием. Для начала необходимо развернуть :::no-loc text="Microsoft Monitoring"::: агенты только для одного или двух :::no-loc text="Microsoft Teams Rooms"::: устройств, к которым у вас есть физический доступ, и получить эти тестовые устройства для создания данных и помещения их в :::no-loc text="Log Analytics"::: рабочую область.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Установка :::no-loc text="Microsoft Monitoring"::: агентов на тестирование устройств

:::no-loc text="Microsoft Monitoring"::: Разверните агент на тестовом устройстве, используя инструкции, предоставленные в [разделе :::no-loc text="Windows"::: подключение компьютеров к :::no-loc text="Log Analytics"::: службе :::no-loc text="Azure"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows). :::no-loc text="Windows":::В этой статье приведены :::no-loc text="Log Analytics"::: подробные сведения о процедуре развертывания :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Microsoft Monitoring"::: агента, инструкции по получению ***идентификатора рабочей области*** и ***первичному ключу*** для получения устройств, подключенных к развертыванию, и инструкции по проверке соединения с :::no-loc text="Log Analytics"::: агентом к экземпляру.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Создание образцов :::no-loc text="Microsoft Teams Rooms"::: событий

После развертывания :::no-loc text="Microsoft Monitoring"::: агента на тестовом устройстве убедитесь в том, что данные, необходимые для записи журнала событий, :::no-loc text="Azure Monitor":::собраны.

> [!NOTE]
> Перезагрузите устройство после установки :::no-loc text="Microsoft Monitoring"::: агента и убедитесь, что приложение для :::no-loc text="Microsoft Teams Rooms"::: собраний запущено, чтобы он мог создавать новые события в журнале событий.

1.  Войдите на [ :::no-loc text="Microsoft Azure"::: портал](https://portal.azure.com) и перейдите в :::no-loc text="Log Analytics"::: рабочую область и выберите ее.

2.  Перечислите события пульса, :::no-loc text="Microsoft Teams Rooms"::: созданные устройством.
    1.  Выберите рабочую область и перейдите в раздел **журналы** и используйте запрос для получения записей пульса, для :::no-loc text="Microsoft Teams Rooms":::которых будут использоваться пользовательские поля.
    2.  Образец запроса:`Event | where Source == "SRS-App" and EventID == 2000`

3.  Убедитесь в том, что запрос возвращает записи журнала, которые содержат события, :::no-loc text="Microsoft Teams Rooms"::: созданные приложением "собрания".

4.  Создание аппаратной ошибки и проверка того, что необходимые события зарегистрированы :::no-loc text="Azure Log Analytics":::.
    1.  Отключите один из периферийных устройств в тестовой :::no-loc text="Microsoft Teams Rooms"::: системе. Это может быть экран камеры, динамика, микрофона или передней комнаты
    2.  Подождите 10 минут, пока журнал событий не будет заполнен :::no-loc text="Azure Log Analytics":::.
    3.  Перечислите события об ошибках оборудования с помощью запроса:`Event | where Source == "SRS-App" and EventID == 3001`

5.  Создание ошибки приложения и проверка того, что в журнал записываются необходимые события.
    1.  Измените :::no-loc text="Microsoft Teams Rooms"::: конфигурацию приложения и введите неверный адрес (SIP) и пароль для протокола запуска сеанса.
    2.  Подождите 10 минут, пока журнал событий не будет заполнен :::no-loc text="Azure Log Analytics":::.
    3.  Использование запроса для перечисления событий, возникающих при ошибке приложения:`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Эти журналы событий являются обязательными, прежде чем можно будет настроить настраиваемые поля. Не переходите к следующему шагу, пока не соберете нужные журналы событий.

## <a name="map-custom-fields"></a>Сопоставление настраиваемых полей
<a name="Custom_fields"> </a>

Пользовательские поля используются для извлечения определенных данных из журналов событий. Необходимо определить пользовательские поля, которые будут использоваться позже с плитками, представлениями панели мониторинга и оповещениями. Прежде чем приступить к созданию настраиваемых полей, просмотрите [пользовательские поля в :::no-loc text="Log Analytics"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) и ознакомьтесь с концепциями.

Чтобы извлечь пользовательские поля из журналов записанных событий, выполните указанные ниже действия.

1.  Войдите на [ :::no-loc text="Microsoft Azure"::: портал](https://portal.azure.com) и перейдите в :::no-loc text="Log Analytics"::: рабочую область и выберите ее.

2. Перечислите события, созданные :::no-loc text="Microsoft Teams Rooms"::: устройством.
   1.  Перейдите в раздел **журналы** и используйте запрос, чтобы получить записи, для которых будет задано настраиваемое поле.
   2.  Образец запроса:`Event | where Source == "SRS-App" and EventID == 2000`

3. Выберите одну из записей, нажмите кнопку слева и запустите Мастер извлечения полей.
4. Выделим данные, которые вы хотите извлечь из RenderedDescription, и укажите название поля. Имена полей, которые следует использовать, приведены в таблице 1.

   ![Определение настраиваемого поля](../media/Deploy-Azure-Monitor-4.png "Определение настраиваемого поля")

5. Используйте сопоставления, показанные в *таблице 1*. :::no-loc text="Log Analytics":::автоматически добавит строку ** \_CF** при определении нового поля.

> [!IMPORTANT]
> Помните о том, что :::no-loc text="Log Analytics"::: все JSON и поля чувствительны к регистру.
> 
> Обратите внимание на запросы, необходимые для каждого настраиваемого поля в приведенной ниже таблице. Для успешного извлечения значений настраиваемых полей необходимо :::no-loc text="Log Analytics"::: использовать правильные запросы.
> 
 ![Определение настраиваемого поля](../media/Deploy-Azure-Monitor-5.png "Определение настраиваемого поля")

**Таблица 1**

| **Поле JSON**                   | **:::no-loc text="Log Analytics":::настраиваемое поле** | **Идентификатор события** | **Запрос, используемый для извлечения**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Описание                      | SRSEventDescription         | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| OS                               | SRSOSVersion                | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| Версия ОС                        | SRSOSLongVersion            | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| Alias                            | SRSAlias                    | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| Состояние микрофона конференции     | SRSConfMicrophoneStatus     | **3001**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 3001 |
| Состояние динамика Конференции        | SRSConfSpeakerStatus        | **3001**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 3001 |
| Состояние динамика по умолчанию           | SRSDefaultSpeakerStatus     | **3001**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 3001 |
| Состояние камеры                    | SRSCameraStatus             | **3001**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 3001 |
| Состояние отображения на передней стороне комнаты     | SRSFORDStatus               | **3001**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 3001 |
| Состояние датчика движения             | SRSMotionSensorStatus       | **3001**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 3001 |
| Состояние приема HDMI               | SRSHDMIIngestStatus         | **3001**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Определение :::no-loc text="Microsoft Teams Rooms"::: представлений в:::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

После сбора данных и сопоставления настраиваемых полей можно использовать конструктор представлений для разработки панели мониторинга с различными плитками для наблюдения за :::no-loc text="Microsoft Teams Rooms"::: событиями. Используйте конструктор представлений для создания следующих плиток. Дополнительные сведения можно найти [в разделе Создание настраиваемых представлений с помощью конструктора :::no-loc text="Log Analytics"::: представлений в](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Предыдущие шаги в этом руководстве должны быть выполнены для правильной работы плиток панели мониторинга.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Создание панели мониторинга Microsoft Teams с помощью метода импорта

Вы можете импортировать :::no-loc text="Microsoft Teams Rooms"::: панель мониторинга и быстро начать наблюдение за устройствами. Чтобы импортировать панель мониторинга, выполните указанные ниже действия.

1.  Скачайте файл панели мониторинга [SkypeRoomSystems_v2. omsview](https://go.microsoft.com/fwlink/?linkid=835675) .
2.  Войдите на [ :::no-loc text="Microsoft Azure"::: портал](https://portal.azure.com) и перейдите в :::no-loc text="Log Analytics"::: рабочую область и выберите ее.
3.  Откройте **Конструктор представлений**.
4.  Нажмите кнопку **Импорт**, а затем выберите файл **SkypeRoomSystems_v2. omsview** .
5.  Нажмите кнопку **сохранить**.

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Создание панели мониторинга Microsoft Teams в помещениях вручную

Кроме того, вы можете создать собственную панель мониторинга и добавить только плитки, которые вы хотите отслеживать.

#### <a name="configure-the-overview-tile"></a>Настройка плитки обзора

1.  Откройте **Конструктор представлений**.
2.  Щелкните **плитку обзор**и выберите в коллекции **два числа** .
3.  Присвойте плитке **:::no-loc text="Microsoft Teams Rooms":::** имя.
4.  Определите **первый фрагмент**:<br>
    **Условные обозначения:** Устройства, которые отправили пакеты пульса хотя бы один раз в течение прошлого месяца<br>
    **Запрос:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Определите **вторую плитку**.<br>
    **Условные обозначения:** Активные устройства, которые отправили пульс за последний час<br>
    **Запрос:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Нажмите кнопку **Применить**.

### <a name="create-a-tile-that-displays-active-devices"></a>Создание плитки, отображающей активные устройства

1.  Нажмите кнопку **Просмотр панели мониторинга** , чтобы начать добавление плиток.
2.  Выберите **число & списка** из коллекции
3.  Определите **Общие** свойства:<br>
    **Название группы:** Состояние пульса<br>
    **Новая Группа:** Выбрал
4.  Определите свойства **плитки** .<br>
    **Условные обозначения:** Активные устройства (пакеты пульса, отправленные за последние 20 минут)<br>
    **Запрос для плитки: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Определите свойства **списка** .<br>
    **Запрос списка:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Определение **заголовков столбцов**:<br>
    **Name (имя):** Имя компьютера<br>
    **Value (значение):** Последний периодических сигналов
7.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Нажмите кнопку **Применить**, а затем — **Закрыть**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Создание плитки, на которой отображаются устройства с неполадками подключения

1.  В коллекции выберите **число & список** и добавьте новую плитку.
2.  Определите **Общие** свойства:<br>
    **Название группы:** Оставьте пустым<br>
    **Новая Группа:** Не выбрано
3.  Определите свойства **плитки** .<br>
    **Условные обозначения:** Неактивные устройства (за последние 20 минут не отправлялись пакеты пульса)<br>
    **Запрос для плитки: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Определите свойства **списка** .<br>
    **Запрос списка:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Определение **заголовков столбцов**:<br>
    **Name (имя):** Имя компьютера<br>
    **Value (значение):** Последний периодических сигналов
6.  Определение **запроса навигации**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Нажмите кнопку **Применить**, а затем — **Закрыть**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Создание плитки, на которой выводятся устройства с аппаратной ошибкой

1.  В коллекции выберите **число & список** и добавьте новую плитку.
2.  Определите **Общие** свойства:<br>
    **Название группы:** Состояние оборудования<br>
    **Новая Группа:** Выбрал
3.  Определите свойства **плитки** .<br>
    **Условные обозначения:** Устройства, на которых произошла ошибка оборудования за последний час<br>
    **Запрос для плитки: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Определите свойства **списка** .<br>
    **Запрос списка:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Определение **заголовков столбцов**:<br>
    **Name (имя):** Имя компьютера<br>
    **Value (значение):** Последняя ошибка
6.  Определение **запроса навигации**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Нажмите кнопку **Применить**, а затем — **Закрыть**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Создание плитки, в которой :::no-loc text="Microsoft Teams Rooms"::: выводятся версии операционной системы

1.  Выберите в коллекции **& список "кольца** ", а затем добавьте новую плитку.
2.  Определите **Общие** свойства:<br>
    **Название группы:** Сведения об операционной системе<br>
    **Новая Группа:** Выбрал
3.  Определите свойства **верхнего колонтитула** .<br>
    **Название:** Версии операционной системы<br>
    **Подзаголовок:** Устройства с определенными версиями ОС
4.  Определите свойства **кольца** :<br>
    **Запрос:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Выровнять текст по центру:** Устройств<br>
    **Операция:** Сумма
5.  Определите свойства **списка** .<br>
    **Запрос списка:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Скрыть диаграмму:** Выбрал<br>
    **Включите спарклайны:** Не выбрано
6.  Определение **заголовков столбцов**.<br>
    **Name (имя):** Имя компьютера<br>
    **Value (значение):** Оставьте пустым
7.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Нажмите кнопку **Применить** , а затем — **Закрыть**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Создание плитки, отображающей :::no-loc text="Microsoft Teams Rooms"::: версии приложения

1.  Выберите в коллекции **& список "кольца** ", а затем добавьте новую плитку.
2.  Определите **Общие** свойства:<br>
    **Заголовок группы:** :::no-loc text="Microsoft Teams Rooms"::: сведения о приложении<br>
    **Новая Группа:** Выбрал
3.  Определите свойства **верхнего колонтитула** .<br>
    **Название:** Версии приложения<br>
    **Подзаголовок:** Устройства, на которых выполняются определенные версии приложений
4.  Определите свойства **кольца** :<br>
    **Запрос:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Выровнять текст по центру:** Устройств<br>
    **Операция:** Сумма
5.  Определите свойства **списка** .<br>
    **Запрос списка:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Скрыть диаграмму:** Выбрал<br>
    **Включите спарклайны:** Не выбрано
6.  Определение **заголовков столбцов**.<br>
    **Name (имя):** Имя компьютера<br>
    **Value (значение):** Оставьте пустым
7.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Нажмите кнопку **Применить** , а затем — **Закрыть**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Создание плитки, на которой отображаются устройства с ошибкой приложения

1.  В коллекции выберите **число & список** и добавьте новую плитку.
2.  Определите **Общие** свойства.<br>
    **Название группы:** Оставьте пустым<br>
    **Новая Группа:** Не выбрано
3.  Определите свойства **плитки** .<br>
    **Условные обозначения:** Устройства, на которых возникла ошибка приложения за последний час<br>
    **Запрос для плитки: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Определите свойства **списка** .<br>
    **Запрос списка:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Определение **заголовков столбцов**.<br>
    **Name (имя):** Имя компьютера<br>
    **Value (значение):** Последняя ошибка
6.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Нажмите кнопку **Применить** , а затем — **Закрыть**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Создание плитки, отображающей устройства, которые были перезапущены

1.  В коллекции выберите **число & список** и добавьте новую плитку.
2.  Определите **Общие** свойства.<br>
    **Название группы:** Оставьте пустым<br>
    **Новая Группа:** Не выбрано
3.  Определите свойства **плитки** .<br>
    **Условные обозначения:** Устройства, на которых приложение было перезагружено за последние 24 часа, и количество перезапусков<br>
    **Запрос для плитки: ** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Определите свойства **списка** .<br>
    **Запрос списка:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Определение **заголовков столбцов**.<br>
    **Name (имя):** Имя компьютера<br>
    **Value (значение):** Количество перезапусков
6.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Нажмите кнопку **Применить** , а затем — **Закрыть**.
8.  Нажмите кнопку **сохранить** , чтобы сохранить панель мониторинга.

Теперь вы закончите создание представлений.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Настройка оповещений в:::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor":::может создавать оповещения, уведомляющие администраторов о проблемах, :::no-loc text="Microsoft Teams Rooms"::: возникающие при возникновении проблем с консолью.

:::no-loc text="Azure Monitor":::включает встроенный механизм предупреждений, который запускается через запланированные операции поиска по журналу через регулярные интервалы. Если результаты поиска в журнале совпадают с определенными критериями, создается запись оповещения.

После этого правило может автоматически запускать одно или несколько действий для упреждающего уведомления о предупреждении или вызова другого процесса. Ниже перечислены возможные параметры оповещения.
-   Отправка сообщения электронной почты
-   Вызов внешнего процесса посредством запроса HTTP POST
-   Запуск Runbook в :::no-loc text="Azure Automation"::: службе

Дополнительные сведения об оповещениях можно найти в разделе [оповещения :::no-loc text="Azure Monitor"::: журнала.](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) :::no-loc text="Azure Monitor":::

> [!NOTE]
> Ниже приведены примеры отправки уведомлений по электронной почте :::no-loc text="Microsoft Teams Rooms"::: о том, что устройство генерирует оборудование или ошибку приложения.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Настройка оповещений по электронной :::no-loc text="Microsoft Teams Rooms"::: почте для устранения проблем с оборудованием

Настройте правило оповещения, проверяющее наличие :::no-loc text="Microsoft Teams Rooms"::: проблем с оборудованием в течение последнего часа.
1.  Войдите на [ :::no-loc text="Microsoft Azure"::: портал](https://portal.azure.com) и перейдите в :::no-loc text="Log Analytics"::: рабочую область и выберите ее.

2. Перейдите в :::no-loc text="Log Analytics"::: рабочую область и выберите **оповещения** , а затем — **новое правило оповещения** .

3. Нажмите кнопку **Добавить условие** , а затем — **Настраиваемый поиск журнала** .

4.  Введите следующий запрос в текстовое поле поискового запроса.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Настройте параметры логики оповещений.<br>
    На **основе:** Число результатов<br>
    **Условие:** Больше<br>
    **Пороговое значение:** 0<br>

6. Настройте параметры оценки и нажмите кнопку **Готово**. <br>
    **Период (в минутах):** 60<br>
    **Частота (в минутах):** 60<br>

7. Настройка групп действий:
    1.  Нажмите кнопку " **создать новый** ".
    2.  Укажите подходящие имена для полей " *имя группы действий* " и " *Краткое имя* ".
    3.  Укажите уникальное *имя действия* и выберите **Электронная почта, SMS/Push/Voice**и нажмите кнопку **изменить сведения**.
    4.  Установите флажок **Электронная почта** и укажите адрес электронной почты пользователя или группы, которые будут получать оповещения.
    5.  Кроме того, вы можете указать свой номер телефона, чтобы получать уведомления с помощью SMS, голосового звонка или и того, и другого.
    6. Нажмите кнопку **ОК**.

8. **Настройте действия** , чтобы перекрыть строку темы сообщений с оповещениями.

9. Укажите имя и описание правила.<br>
    **Имя правила:** :::no-loc text="Microsoft Teams Rooms"::: оповещение о сбое оборудования<br>
    **Описание:** Список устройств, для которых возникла неполадка с оборудованием в течение последнего часа<br>

10. Выберите предполагаемый уровень важности и убедитесь, что правило включено.

11. Выберите **создать правило оповещения**.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Настройка оповещений по электронной :::no-loc text="Microsoft Teams Rooms"::: почте для проблем с приложениями

Повторите эту процедуру, но используйте следующий запрос, чтобы вывести список устройств, в которых возникли проблемы с приложением за последний час.

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

Теперь вы завершили определение оповещений. Вы можете определить дополнительные оповещения, выполнив приведенные выше примеры.

При создании оповещения вы получите сообщение электронной почты со списком устройств, в которых возникла ошибка в течение последнего часа.

! [Образец :::no-loc text="Azure Monitor"::: оповещения по электронной почте] (.. /media/Deploy-Azure-Monitor-6.png "образец :::no-loc text="Azure Monitor"::: оповещения по электронной почте")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Настройка всех устройств для:::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a> После настройки панелей мониторинга и оповещений вы можете настроить и настроить :::no-loc text="Microsoft Monitoring"::: агент на всех :::no-loc text="Microsoft Teams Rooms"::: устройствах, чтобы завершить развертывание мониторинга.

Несмотря на то, что вы можете :::no-loc text="Microsoft Monitoring"::: установить и настроить агент вручную на каждом устройстве, мы настоятельно рекомендуем использовать существующие инструменты и методы развертывания программного обеспечения.

Если вы создаете :::no-loc text="Microsoft Teams Rooms"::: устройства в первый раз, вам может потребоваться включить настройку :::no-loc text="Microsoft Monitoring"::: агента и шаги по настройке в рамках процесса сборки. Дополнительные сведения можно найти в разделе [Установка агента с помощью командной строки](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Развертывание :::no-loc text="Microsoft Monitoring"::: агента с помощью объекта групповой политики (GPO)

Если вы уже развернули :::no-loc text="Microsoft Teams Rooms"::: устройства перед реализацией :::no-loc text="Azure Monitoring":::, вы можете использовать предоставленный сценарий, чтобы настроить агенты и настроить их с :::no-loc text="Active Directory"::: помощью объектов групповой политики.

1.  Создание общего сетевого пути и предоставление доступа на чтение к группе **доменные компьютеры** .

2.  Скачайте версию :::no-loc text="Microsoft Monitoring"::: агента 64-bit для :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Извлеките содержимое установочного пакета в сетевую папке.
    1.  Открытие окна командной строки с последующим выполнением **MMASetup-AMD64. exe/c**
    2.  Укажите только что созданный общий доступ и извлеките содержимое.

4.  Создайте новый объект групповой политики и назначьте его организационному подразделению, :::no-loc text="Microsoft Teams Rooms"::: в котором находятся учетные записи компьютера.

5.  Настройка политики выполнения PowerShell.
    1.  Изменение созданного объекта групповой политики и переход к параметрам политики \\ \\ конфигурации компьютера компоненты \\ :::no-loc text="Windows"::: \\ административных шаблонов:::no-loc text="Windows PowerShell":::
    2.  Включите **выполнение сценария включения** и настройте **политику выполнения** , чтобы **Разрешить локальные сценарии**.

6.  Настройте сценарий запуска.
    1.  Скопируйте приведенный ниже сценарий и сохраните его как Install-MMAgent. ps1.
    2.  Измените параметры WorkspaceId, WorkspaceKey и SetupPath, чтобы они соответствовали вашей конфигурации.
    3.  Изменение одного и того же объекта групповой политики и переход к \\ \\ :::no-loc text="Windows"::: параметрам \\ политик конфигурации компьютера (запуск и завершение)
    4.  Дважды щелкните, чтобы выбрать **Запуск**, и выберите пункт **сценарии PowerShell**.
    5.  Выберите пункт **Показать файлы**, а затем скопируйте файл **Install-MMAgent. ps1** в эту папку.
    6.  Нажмите кнопку **Добавить**, а затем — **Обзор**.
    7.  Выберите только что скопированный сценарий PS1.

7.  :::no-loc text="Microsoft Teams Rooms":::устройства должны устанавливать и настраивать :::no-loc text="Microsoft Monitoring"::: агент со второй перезагрузкой.

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
> Вы можете обратиться к статье, которая [ :::no-loc text="Log Analytics"::: управляет агентом](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) , когда вам требуется перенастроить агент, переместить его в другую рабочую область или изменить параметры прокси-сервера после первоначальной установки.

## <a name="additional-solutions"></a>Дополнительные решения
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor":::предоставляет встроенные решения для управления с помощью [коллекции решений](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) для дальнейшей помощи в наблюдении за вашей средой. Настоятельно рекомендуется также добавить решения для [управления оповещениями](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) и [ :::no-loc text="Azure Log Analytics"::: проверки работоспособности агентов](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) в рабочую область.

> [!NOTE]
> Решение для проверки работоспособности агента может помочь в определении устаревших или поврежденных :::no-loc text="Microsoft Monitoring"::: агентов в среде, а решение для управления оповещениями — сведения об оповещениях, которые были созданы в течение заданного периода.

## <a name="see-also"></a>См. также

[Управление :::no-loc text="Microsoft Teams Rooms"::: планированием с помощью:::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Управление :::no-loc text="Microsoft Teams Rooms"::: устройствами с помощью:::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
