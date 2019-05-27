---
title: Развертывание управления комнатами Microsoft Teams с помощью монитора Azure
ms.author: v-lanac
author: lanachin
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: В этой статье рассказывается, как развернуть управление устройствами в Microsoft Teams с помощью монитора Azure.
ms.openlocfilehash: fd1f1b32bd999c18144831e2458b426bf55ca1a9
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433377"
---
# <a name="deploy-microsoft-teams-rooms-management-with-azure-monitor"></a>Развертывание управления комнатами Microsoft Teams с помощью монитора Azure

В этой статье объясняется, как настроить и развернуть объединенное и конечное Управление устройствами Microsoft Teams с помощью монитора Azure.

Вы можете настроить службу журналов в службе Azure для предоставления базовой телеметрии и оповещений, которые помогут вам управлять комнатами в Microsoft Teams, где находятся устройства для Конференц зал. По мере того как ваше решение для управления будет превышено, вы можете развернуть дополнительные возможности данных и управления, чтобы создать более подробное представление о доступности и быстродействии устройства.

Следуя этим инструкциям, вы можете использовать панель мониторинга, как в следующем примере, для получения подробных отчетов о состоянии доступности устройства, работоспособности приложения и оборудования, а также Microsoft Teams для распространения версий приложений и операционной системы.

![Снимок экрана, на котором показан пример аналитического анализа журнала для комнат Microsoft Teams] (../media/Deploy-Azure-Monitor-1.png "Образец аналитического журнала для комнат Microsoft Teams")

В общих чертах вам необходимо выполнить следующие задачи.


1.  [Проверка конфигурации Analytics log](azure-monitor-deploy.md#validate_LogAnalytics)
2.  [Настройка тестовых устройств для настройки службы управления журналом](azure-monitor-deploy.md#configure_test_devices)
3.  [Сопоставление настраиваемых полей](azure-monitor-deploy.md#Custom_fields)
4.  [Определение представлений комнат Microsoft Teams в службе анализа журналов](azure-monitor-deploy.md#Define_Views)
5.  [Определение оповещений](azure-monitor-deploy.md#Alerts)
6.  [Настройка наблюдения для всех устройств](azure-monitor-deploy.md#configure_all_devices)
7.  [Настройка дополнительных решений для монитора Azure](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Несмотря на то, что в минимальной конфигурации служба Azure log Analytics может отслеживать компьютер под управлением операционной системы Windows, по-прежнему некоторые комнаты Microsoft Teams — конкретные действия, которые необходимо выполнить, прежде чем приступить к развертыванию агентов для всех Microsoft Teams. Устройства комнаты.
> Поэтому мы настоятельно рекомендуем выполнить все действия по настройке в правильном порядке для управления установкой и конфигурацией. Качество конечного результата очень сильно зависит от качества начальной конфигурации.

## <a name="validate-log-analytics-configuration"></a>Проверка конфигурации Analytics log
<a name="validate_LogAnalytics"> </a>

Для сбора журналов из комнат Microsoft Teams необходимо иметь рабочую область "анализ журналов". Рабочая область — это уникальная среда для анализа журналов с собственным хранилищем данных, источниками данных и решениями. Если у вас уже есть рабочая область с аналитическим журналом, вы можете использовать ее для наблюдения за развертыванием комнат Microsoft Teams, а также создать специальную рабочую область для анализа журналов, относящуюся к потребностям мониторинга Microsoft Teams.

Если вам нужно создать новую рабочую область для анализа журналов, следуйте инструкциям в статье [Создание рабочей области для службы анализа журналов на портале Azure](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Для использования службы анализа журналов с монитором Azure необходимо иметь активную подписку на Azure. Если у вас нет подписки на Azure, вы можете создать [бесплатную пробную подписку](https://azure.microsoft.com/free) в качестве отправной точки.

### <a name="configure-log-analytics-to-collect-microsoft-teams-rooms-event-logs"></a>Настройка службы журнала для сбора журналов событий Microsoft Teams

Аналитика журнала собирает только события из журналов событий Windows, указанных в параметрах. Для каждого журнала собираются только события, для которых выбраны определенные серьезности.

Для сбора журналов, необходимых для отслеживания состояния устройства и приложения Microsoft Teams, необходимо настроить Analytics log. В Microsoft Teams комнаты используются для работы с журналом событий **системы комнаты Skype** .

Настройка службы журнала для сбора событий в комнатах Microsoft Teams в разделе " [Источники данных журнала событий Windows" на мониторе Azure](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Снимок экрана с параметрами журнала событий] (../media/Deploy-Azure-Monitor-2.png "Параметры журнала событий")

> [!IMPORTANT]
> Настройте параметры журнала событий Windows и введите в качестве имени журнала событий **систему Skype Room** , а затем установите флажки **Ошибка**, **предупреждение**и **сведения** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Настройка тестовых устройств для мониторинга Azure
<a name="configure_test_devices"> </a>

Для отслеживания событий, связанных с комнатами Microsoft Teams, необходимо подготовить аналитический журнал, чтобы получить доступ к ним. Для начала вам потребуется развернуть агенты наблюдения (Майкрософт) только в одной или двух комнатах Microsoft Teams, к которым у вас есть физический доступ, и получить эти тестовые устройства для создания данных и их последующего помещения в рабочую область "анализ журналов".

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a>Установка агентов наблюдения (Майкрософт) на тестирование устройств

Развертывание агента Microsoft Monitoring Agent на тестовом устройстве с помощью инструкций, приведенных в разделе [Подключение компьютеров с Windows к службе Analytics log в Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows). В этой статье приведены подробные сведения о процедуре развертывания Microsoft Monitoring Agent для Windows, инструкции по получению ***идентификатора рабочей области*** для анализа журналов и ***первичному ключу*** для получения данных о том, к которым подключены устройства Microsoft Teams. Развертывание монитора Azure и инструкции по проверке соединения агента с экземпляром службы журнала.

### <a name="generate-sample-microsoft-teams-rooms-events"></a>Создание образцов событий комнат Microsoft Teams

После развертывания агента Microsoft Monitoring на тестовом устройстве убедитесь, что данные о необходимых данных журнала событий собраны монитором Azure.

> [!NOTE]
> После установки Microsoft Monitoring Agent перезагрузите устройство и убедитесь, что запущено приложение собрания Microsoft Teams, в котором можно создать новые события в журнале событий.

1.  Войдите на [портал Microsoft Azure](https://portal.azure.com) и выберите рабочую область в службе аналитики журнала.

2.  Перечислите события пульса, созданные с помощью устройства Microsoft Teams (комната):
    1.  Выберите рабочую область и перейдите в раздел **журналы** и используйте запрос, чтобы получить записи пульса, для которых будут использоваться пользовательские поля для комнат Microsoft Teams.
    2.  Образец запроса:`Event | where Source == "SRS-App" and EventID == 2000`

3.  Убедитесь в том, что запрос возвращает записи журнала, которые содержат события, созданные приложением "собрания комнат Microsoft Teams".

4.  Создавайте аппаратные ошибки и проверяйте, зарегистрированы в службе аналитики журнала Azure необходимые события.
    1.  Отключите один из периферийных устройств в разделе Проверка системы комнат Microsoft Teams. Это может быть экран камеры, динамика, микрофона или передней комнаты
    2.  Подождите 10 минут, пока журнал событий не будет заполнен службой Azure log Analytics.
    3.  Перечислите события об ошибках оборудования с помощью запроса:`Event | where Source == "SRS-App" and EventID == 3001`

5.  Создание ошибки приложения и проверка того, что в журнал записываются необходимые события.
    1.  Измените конфигурацию приложения Microsoft Teams, а затем введите неверный адрес (SIP) и пароль для протокола запуска сеанса.
    2.  Подождите 10 минут, пока журнал событий не будет заполнен службой Azure log Analytics.
    3.  Использование запроса для перечисления событий, возникающих при ошибке приложения:`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Эти журналы событий являются обязательными, прежде чем можно будет настроить настраиваемые поля. Не переходите к следующему шагу, пока не соберете нужные журналы событий.

## <a name="map-custom-fields"></a>Сопоставление настраиваемых полей
<a name="Custom_fields"> </a>

Пользовательские поля используются для извлечения определенных данных из журналов событий. Необходимо определить пользовательские поля, которые будут использоваться позже с плитками, представлениями панели мониторинга и оповещениями. Прежде чем приступить к созданию настраиваемых полей, просмотрите [пользовательские поля в службе анализа журналов](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) и ознакомьтесь с концепциями.

Чтобы извлечь пользовательские поля из журналов записанных событий, выполните указанные ниже действия.

1.  Войдите на [портал Microsoft Azure](https://portal.azure.com) и выберите рабочую область в службе аналитики журнала.

2. Перечислите события, созданные с помощью устройства Microsoft Teams комнаты:
   1.  Перейдите в раздел **журналы** и используйте запрос, чтобы получить записи, для которых будет задано настраиваемое поле.
   2.  Образец запроса:`Event | where Source == "SRS-App" and EventID == 2000`

3. Выберите одну из записей, нажмите кнопку слева и запустите Мастер извлечения полей.
4. Выделим данные, которые вы хотите извлечь из Рендереддескриптион, и укажите название поля. Имена полей, которые следует использовать, приведены в таблице 1.

   ![Определение настраиваемого поля] (../media/Deploy-Azure-Monitor-4.png "Определение настраиваемого поля")

5. Используйте сопоставления, показанные в *таблице 1*. После того как вы определите новое ** \_** поле, в службе аналитики журнала будет автоматически добавлена строка CF.

> [!IMPORTANT]
> Помните, что в полях JSON и Analytics журнала учитывается регистр.
> 
> Обратите внимание на запросы, необходимые для каждого настраиваемого поля в приведенной ниже таблице. Для того чтобы успешно извлекать пользовательские значения полей, необходимо использовать правильные запросы для службы анализа журнала.
> 
 ![Определение настраиваемого поля] (../media/Deploy-Azure-Monitor-5.png "Определение настраиваемого поля")

**Таблица 1**

| **Поле JSON**                   | **Настраиваемое поле "анализ журнала"** | **Идентификатор события** | **Запрос, используемый для извлечения**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Описание                      | Срсевентдескриптион         | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| ResourceState                    | Срсресаурцестате            | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| OperationName                    | Срсоператионнаме            | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| OperationResult                  | Срсоператионресулт          | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| OS                               | Срсосверсион                | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| Версия ОС                        | Срсослонгверсион            | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| Alias                            | Срсалиас                    | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| DisplayName                      | Срсдисплайнаме              | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| AppVersion                       | Срсаппверсион               | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 2000 |
| Состояние микрофона конференции     | Срсконфмикрофонестатус     | **3001**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 3001 |
| Состояние динамика Конференции        | Срсконфспеакерстатус        | **3001**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 3001 |
| Состояние динамика по умолчанию           | Срсдефаултспеакерстатус     | **3001**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 3001 |
| Состояние камеры                    | Срскамерастатус             | **3001**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 3001 |
| Состояние отображения на передней стороне комнаты     | Срсфордстатус               | **3001**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 3001 |
| Состояние датчика движения             | Срсмотионсенсорстатус       | **3001**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 3001 |
| Состояние приема HDMI               | Сршдмиинжестстатус         | **3001**     | Событие \| , в котором Source = = "SRS-App" и EventID = = 3001 |


## <a name="define-the-microsoft-teams-rooms-views-in-log-analytics"></a>Определение представлений комнат Microsoft Teams в службе анализа журналов
<a name="Define_Views"> </a>

После сбора данных и сопоставления настраиваемых полей можно использовать конструктор представлений для разработки панели мониторинга с различными плитками для наблюдения за событиями комнат Microsoft Teams. Используйте конструктор представлений для создания следующих плиток. Дополнительные сведения можно найти [в разделе Создание настраиваемых представлений с помощью конструктора представлений в службе анализа журналов](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Предыдущие шаги в этом руководстве должны быть выполнены для правильной работы плиток панели мониторинга.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Создание панели мониторинга Microsoft Teams с помощью метода импорта

Вы можете импортировать панель мониторинга Microsoft Teams, чтобы быстро начать наблюдать за вашими устройствами. Чтобы импортировать панель мониторинга, выполните указанные ниже действия.

1.  Скачайте файл панели мониторинга [SkypeRoomSystems_v2. омсвиев](https://go.microsoft.com/fwlink/?linkid=835675) .
2.  Войдите на [портал Microsoft Azure](https://portal.azure.com) и выберите рабочую область в службе аналитики журнала.
3.  Откройте **Конструктор представлений**.
4.  Нажмите кнопку **Импорт**, а затем выберите файл **SkypeRoomSystems_v2. омсвиев** .
5.  Нажмите кнопку **сохранить**.

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Создание панели мониторинга Microsoft Teams в помещениях вручную

Кроме того, вы можете создать собственную панель мониторинга и добавить только плитки, которые вы хотите отслеживать.

#### <a name="configure-the-overview-tile"></a>Настройка плитки обзора

1.  Откройте **Конструктор представлений**.
2.  Щелкните **плитку обзор**и выберите в коллекции **два числа** .
3.  Назовите плитку " **комнаты Microsoft Teams**".
4.  Определите **первый фрагмент**:<br>
    **Условные обозначения:** Устройства, которые отправили пакеты пульса хотя бы один раз в течение прошлого месяца<br>
    **Запрос:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Определите **вторую плитку**.<br>
    **Условные обозначения:** Активные устройства, которые отправили пульс за последний час<br>
    **Запрос:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Нажмите кнопку **Применить**.

### <a name="create-a-tile-that-displays-active-devices"></a>Создание плитки, отображающей активные устройства

1.  Нажмите кнопку **Просмотр панели мониторинга** , чтобы начать добавление плиток.
2.  Выберите в коллекции **номер _амп_ списка** .
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

1.  В коллекции выберите **число _амп_ списка** и добавьте новую плитку.
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

1.  В коллекции выберите **число _амп_ списка** и добавьте новую плитку.
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

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-operating-system-versions"></a>Создание плитки, отображающей операционные системы комнат Microsoft Teams

1.  Выберите в коллекции **_амп_ список кольца** и добавьте новую плитку.
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

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-application-versions"></a>Создание плитки, отображающей версии приложений Microsoft Teams

1.  Выберите в коллекции **_амп_ список кольца** и добавьте новую плитку.
2.  Определите **Общие** свойства:<br>
    **Название группы:** Сведения о приложениях в комнатах Microsoft Teams<br>
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

1.  В коллекции выберите **число _амп_ списка** и добавьте новую плитку.
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

1.  В коллекции выберите **число _амп_ списка** и добавьте новую плитку.
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

## <a name="configure-alerts-in-azure-monitor"></a>Настройка оповещений на мониторе Azure
<a name="Alerts"> </a>

Монитор Azure может создавать оповещения для уведомления администраторов об ошибке при возникновении проблем с консолью комнат Microsoft Teams.

Монитор Azure включает встроенный механизм предупреждений, который выполняется через запланированные операции поиска по журналу через регулярные интервалы. Если результаты поиска в журнале совпадают с определенными критериями, создается запись оповещения.

После этого правило может автоматически запускать одно или несколько действий для упреждающего уведомления о предупреждении или вызова другого процесса. Ниже перечислены возможные параметры оповещения.
-   Отправка сообщения электронной почты
-   Вызов внешнего процесса посредством запроса HTTP POST
-   Запуск Runbook в службе автоматизации Azure

Дополнительные сведения об оповещениях на мониторе Azure см. в разделе [оповещения журнала на мониторе Azure](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) .

> [!NOTE]
> В следующих примерах отправляются уведомления по электронной почте о том, что устройство Microsoft Teams комнаты генерирует оборудование или ошибку приложения.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-hardware-issues"></a>Настройка оповещений по электронной почте в Microsoft Teams для помещения проблем с оборудованием

Настройте правило оповещения, проверяющее Microsoft Teams комнаты, в которых возникли проблемы с оборудованием за последний час.
1.  Войдите на [портал Microsoft Azure](https://portal.azure.com) и выберите рабочую область в службе аналитики журнала.

2. Перейдите в рабочую область службы анализа журналов и выберите пункт **оповещения** , а затем — **новое правило оповещения** .

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
    **Трешолд:** 0<br>

6. Настройте параметры оценки и нажмите кнопку **Готово**. <br>
    **Период (в минутах):** 60<br>
    **Частота (в минутах):** 60<br>

7. Настройка групп действий:
    1.  Нажмите кнопку " **создать новый** ".
    2.  Укажите подходящие имена для полей " *имя группы действий* " и " *Краткое имя* ".
    3.  Укажите уникальное *имя действия* и выберите **Электронная почта, SMS/Push/Voice**и нажмите кнопку **изменить сведения**.
    4.  Установите флажок Электронная почта и укажите адрес электронной почты пользователя или группы, которые будут получать оповещения.
    5.  Кроме того, вы можете указать свой номер телефона, чтобы получать уведомления с помощью SMS, голосового звонка или и того, и другого.
    6. Нажмите кнопку **ОК**.

8. **Настройте действия** , чтобы перекрыть строку темы сообщений с оповещениями.

9. Укажите имя и описание правила.<br>
    **Имя правила:** Оповещение о сбоях оборудования в Microsoft Teams<br>
    **Описание:** Список устройств, для которых возникла неполадка с оборудованием в течение последнего часа<br>

10. Выберите предполагаемый уровень важности и убедитесь, что правило включено.

11. Выберите **создать правило оповещения**.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-application-issues"></a>Настройка оповещений по электронной почте для Microsoft Teams в помещениях о проблемах с приложениями

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

![Пример сообщения с оповещением монитора Azure] (../media/Deploy-Azure-Monitor-6.png "Пример сообщения с оповещением монитора Azure")

## <a name="configure-all-devices-for-azure-monitoring"></a>Настройка всех устройств для мониторинга Azure
<a name="configure_all_devices"></a> После настройки панелей мониторинга и оповещений вы можете настроить и настроить Microsoft Monitoring Agent на всех устройствах Microsoft Teams, чтобы завершить развертывание мониторинга.

Несмотря на то, что вы можете установить и настроить агент наблюдения Майкрософт вручную на каждом устройстве, мы настоятельно рекомендуем использовать существующие инструменты и методы развертывания программного обеспечения.

Если вы создаете устройства в Microsoft Teams в первый раз, вам может потребоваться включить настройку агента наблюдения (Майкрософт) и этапы настройки в процессе сборки. Дополнительные сведения можно найти в разделе [Установка агента с помощью командной строки](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Развертывание агента наблюдения (Майкрософт) с помощью объекта групповой политики (GPO)

Если вы уже развернули устройства Microsoft Teams для работы со службой наблюдения за Azure, вы можете использовать предоставленный сценарий для настройки и настройки агентов с помощью объектов групповой политики Active Directory.

1.  Создание общего сетевого пути и предоставление доступа на чтение к группе **доменные компьютеры** .

2.  Загрузите 64-разрядную версию Microsoft Monitoring Agent для Windows из<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Извлеките содержимое установочного пакета в сетевую папке.
    1.  Открытие окна командной строки с последующим выполнением **MMASetup-AMD64. exe/c**
    2.  Укажите только что созданный общий доступ и извлеките содержимое.

4.  Создайте новый объект групповой политики и назначьте его организационному подразделению, в котором находятся учетные записи компьютеров Microsoft Teams.

5.  Настройка политики выполнения PowerShell.
    1.  Редактирование только \\ что созданного объекта групповой политики и переход к параметрам \\ политики конфигурации \\ компьютера. \\ шаблоны Windows PowerShell
    2.  Включите **выполнение сценария включения** и настройте **политику выполнения** , чтобы **Разрешить локальные сценарии**.

6.  Настройте сценарий запуска.
    1.  Скопируйте приведенный ниже сценарий и сохраните его как Инсталл-ммажент. ps1.
    2.  Измените параметры Воркспацеид, Воркспацекэй и Сетуппас, чтобы они соответствовали вашей конфигурации.
    3.  Измените один и тот же объект групповой политики и перейдите в \\ раздел \\ политики конфигурации \\ компьютера сценарии настройки Windows (запуск и завершение)
    4.  Дважды щелкните, чтобы выбрать **Запуск**, и выберите пункт **сценарии PowerShell**.
    5.  Выберите пункт **Показать файлы**, а затем скопируйте файл **Инсталл-ммажент. ps1** в эту папку.
    6.  Нажмите кнопку **Добавить**, а затем — **Обзор**.
    7.  Выберите только что скопированный сценарий PS1.

7.  В Microsoft Teams для работы с устройствами следует установить и настроить агент наблюдения (Майкрософт) со второй перезагрузкой.

```
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
> Вы можете обратиться к статье, которая [управляет агентом аналитики журналов и его обслуживанием](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) , если вам нужно перенастроить агент, переместить его в другую рабочую область или изменить параметры прокси-сервера после первоначальной установки.

## <a name="additional-solutions"></a>Дополнительные решения
<a name="Solutions"> </a>

Монитор Azure предоставляет встроенные решения для управления с помощью [коллекции решений](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) для дальнейшей помощи в наблюдении за вашей средой. Настоятельно рекомендуем также добавить в рабочую область решения для [управления оповещениями](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) и проверки [работоспособности агента аналитики Azure](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) .

> [!NOTE]
> Решение для проверки работоспособности агента помогает идентифицировать устаревшие или неработающие агенты наблюдения за корпорацией Майкрософт в среде, а решение для управления оповещениями — сведения об оповещениях, которые были созданы в течение заданного периода.

## <a name="see-also"></a>См. также

[Планирование управления комнатами в Microsoft Teams с помощью монитора Azure](azure-monitor-plan.md)

[Управление устройствами в Microsoft Teams с помощью монитора Azure](azure-monitor-manage.md)
