---
title: Развертывание управления группами комнат Microsoft с монитором Azure
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Эта статья посвящена процедуре для развертывания управления устройствами комнат группами Майкрософт интегрированная, начала до конца способом, с помощью Azure монитор.
ms.openlocfilehash: 599cbb7abce2b20dac27ffebacb041062a254905
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219526"
---
# <a name="deploy-microsoft-teams-rooms-management-with-azure-monitor"></a>Развертывание управления группами комнат Microsoft с монитором Azure

В этой статье описывается установка и развертывание интегрированная, сквозного управления устройствами комнат группами Майкрософт с использованием монитора Azure.

Можно настроить анализа журнала в рамках монитор Azure для обеспечения базовой телеметрии оповещения, которые помогут вам комнат и управления ими Microsoft группами собрания комнаты устройств. Мере разработки решения по управлению можно развернуть дополнительные данные и возможности управления для создания более подробные представления производительности и доступности устройства.

Выполнив в этом руководстве, можно использовать панели мониторинга как следующий пример, чтобы получить подробные сведения о состоянии отчетов о доступности устройства, приложения и работоспособности оборудования и приложений Microsoft группами комнат и рассылки версии операционной системы.

![Пример журнала анализа представления для комнат группами Майкрософт] (../../media/Deploy-Azure-Monitor-1.png "Пример журнала анализа представления для комнат группами Майкрософт")

В общих чертах вам необходимо выполнить следующие задачи.


1.  [Проверка конфигурации анализа журнала](azure-monitor.md#validate_LogAnalytics)
2.  [Настройка тестовых устройств для настройки управления анализа журнала](azure-monitor.md#configure_test_devices)
3.  [Сопоставление настраиваемых полей](azure-monitor.md#Custom_fields)
4.  [Определение представлений комнат группами Майкрософт в аналитике журнала](azure-monitor.md#Define_Views)
5.  [Определение оповещений](azure-monitor.md#Alerts)
6.  [Настройка всех устройств для наблюдение](azure-monitor.md#configure_all_devices)
7.  [Настройка дополнительных решений монитор Azure](azure-monitor.md#Solutions)

> [!IMPORTANT]
> Несмотря на то, что в минимальной конфигурации анализа журнала монитор Azure можно отслеживать компьютера под управлением операционной системы Windows, по-прежнему существует несколько групп Майкрософт комнат – этапов, которые необходимо выполнить перед началом развертывания агентов для всех групп Майкрософт Комнат устройств.
> Таким образом настоятельно рекомендуется выполнить все действия по настройке в правильном порядке для управляемой установки и настройки. Качество конечный результат сильно зависит от качества начальной настройки.

## <a name="validate-log-analytics-configuration"></a>Проверка конфигурации анализа журнала
<a name="validate_LogAnalytics"> </a>

Необходимо иметь рабочей области для анализа журналов для запуска сбор данных в журналах с помощью устройств комнат группами Майкрософт. Рабочая область — уникальный анализа журнала среды с собственными хранилище данных, источники данных и решения. Если уже существующей рабочей области для анализа журнала, его можно использовать для отслеживания развертывания комнат группами Майкрософт или Кроме того, можно создать выделенные рабочей области для анализа журнала определенного вашей комнат группами Майкрософт мониторинга потребностей.

Если вам необходимо создать новую рабочую область анализа журнала, следуйте инструкциям, представленным в статье [Создание рабочей области для анализа журнала на портале Azure](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Использование журнала анализа с монитором Azure, необходимо иметь active Azure подписки. Если у вас нет Azure подписки, можно создать [бесплатную пробную подписку](https://azure.microsoft.com/free) в качестве отправной точки.

### <a name="configure-log-analytics-to-collect-microsoft-teams-rooms-event-logs"></a>Настройка анализа журнала можно собирать журналы событий Microsoft группами комнат

Аналитика журнала только собирает события в журнале событий Windows, которые указаны в диалоговом окне настройки. Для каждого журнала событий с помощью выбранного серьезности собираются.

Необходимо настроить анализа журнала можно собирать журналы, необходимые для наблюдения за состоянием комнат Microsoft групп устройств и приложений. Устройства комнат группами Майкрософт используют **Скайп комнаты системный** журнал событий.

Настройка анализа журналов для сбора событий комнат группами Майкрософт, в статье [источников данных журнала событий Windows Azure монитора](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Параметры журнала событий] (../../media/Deploy-Azure-Monitor-2.png "Параметры журнала событий")

> [!IMPORTANT]
> Настройка параметров журнала событий Windows и введите **Скайп комнаты системы** в качестве имени журнала событий и установите флажки **ошибки**, **предупреждения**и **сведения** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Настройка тестовых устройств для наблюдение за Azure
<a name="configure_test_devices"> </a>

Необходимо подготовить анализа журнала должны иметь возможность отслеживания событий, связанных с группами комнат Microsoft. Со, необходимые для развертывания Microsoft мониторинг агентов для всего один или два устройства комнат группами Майкрософт, имеющие физический доступ к и получить те тестовых устройств создать некоторые данные и записывать его в рабочую область аналитических журнала.

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a>Установка Microsoft мониторинг агенты для тестирования устройств

Развертывание агента Microsoft мониторинг тестовых устройств с помощью инструкций, приведенных в [компьютеры Windows подключиться к службе анализа журнала в Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows). В этой статье приведены подробные сведения о действиях по развертыванию Microsoft мониторинга агента для Windows, инструкции по получении анализа журнала ***Идентификатор рабочей области*** и ***первичный ключ*** для получения комнат Microsoft групп устройств, подключенных к Развертывание монитор Azure и действий по проверке агента подключения к экземпляру анализа журнала.

### <a name="generate-sample-microsoft-teams-rooms-events"></a>Создавать события комнат группами Майкрософт образца

После развертывания агентов мониторинг Microsoft на тестовых устройств убедитесь, что сбор данных журналов событий монитором Azure.

> [!NOTE]
> Перезагрузите устройство после установки агента мониторинг Microsoft и убедитесь, что запущено приложение Microsoft группами комнат собрания, чтобы он мог создать новые события в журнале событий.

1.  Вход на [портал Microsoft Azure](https://portal.azure.com) и перейдите к журнала аналитика и Выбор рабочей области.

2.  Список событий периодический сигнал от устройства Microsoft группами комнат:
    1.  Выберите рабочую область и перейдите к **Журналы** и использовать запрос для извлечения записей периодический сигнал, которые будут иметь настраиваемые поля для комнат группами Майкрософт.
    2.  Пример запроса:`Event | where Source == "SRS-App" and EventID == 2000`

3.  Убедитесь в том, что запрос возвращает записи журнала, включая события, создаваемые приложения собраний комнат группами Майкрософт.

4.  Создание проблема оборудования и проверить, что необходимые события регистрируются в аналитике журнала Azure.
    1.  Отключите один из периферийных устройств на тестовых комнат группы Microsoft system. Это может быть камера, устройство громкой связи, микрофон или отображения передний план комнаты
    2.  Подождите 10 минут для журнала событий, которые следует добавить в аналитике журнала Azure.
    3.  Использование запроса для списка Список аппаратных предупреждений об ошибках:`Event | where Source == "SRS-App" and EventID == 3001`

5.  Создание проблем приложений и проверки необходимых событий.
    1.  Изменение конфигурации приложения Microsoft группами комнат и введите пара неправильный адрес и пароль Session Initiation Protocol (SIP).
    2.  Подождите 10 минут для журнала событий, которые следует добавить в аналитике журнала Azure.
    3.  Использование запроса на события ошибки приложения списка:`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Эти журналы событий примера требуются перед настраиваемых полей можно настроить. Не переходите к следующему шагу, пока не будут собраны необходимые журналы событий.

## <a name="map-custom-fields"></a>Сопоставление настраиваемых полей
<a name="Custom_fields"> </a>

Использование настраиваемых полей для извлечения данных из журналов событий. Необходимо определить настраиваемые поля, которые будут использоваться позднее представления панели мониторинга, оповещения и заголовков. Просмотреть [настраиваемых полей в аналитике журнала](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) и ознакомиться с понятиями, прежде чем начать создание настраиваемых полей.

Чтобы извлечь настраиваемых полей из него захвата журналы событий, выполните следующие действия:

1.  Вход на [портал Microsoft Azure](https://portal.azure.com) и перейдите к журнала аналитика и Выбор рабочей области.

2. Перечислены события, создаваемые устройства комнат группами Майкрософт:
   1.  Перейдите к **журналам** и запрос используется для извлечения записей, которые будут иметь настраиваемого поля.
   2.  Пример запроса:`Event | where Source == "SRS-App" and EventID == 2000`

3. Выберите один из записей, нажмите кнопку слева и запустите мастер извлечения поля.
4. Выделите данные, которые вы хотите извлечь из RenderedDescription и укажите название поля. В таблице 1 приведены имена полей, которые следует использовать.

   ![Определение настраиваемого поля] (../../media/Deploy-Azure-Monitor-4.png "Определение настраиваемого поля")

5. Использование сопоставлений, показано в *таблице 1*. Журнал анализа автоматически добавляет ** \_CF** строка при определении нового поля.

> [!IMPORTANT]
> Имейте в виду, что все поля журнала аналитические данные и JSON зависят от регистра символов.
> 
> Обратите внимание на запросы, необходимые для каждого настраиваемого поля в таблице ниже. Необходимо использовать правильный запросы для анализа журнала успешно извлечение значения настраиваемых полей.
> 
 ![Определение настраиваемого поля] (../../media/Deploy-Azure-Monitor-5.png "Определение настраиваемого поля")

**В таблице 1**

| **Поле JSON**                   | **Войдите в аналитических настраиваемого поля** | **Идентификатор события** | **Запрос для использования с извлечения**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Описание                      | SRSEventDescription         | **2000**     | Событие \| где источника == «SRS-App» и EventID == 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Событие \| где источника == «SRS-App» и EventID == 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Событие \| где источника == «SRS-App» и EventID == 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Событие \| где источника == «SRS-App» и EventID == 2000 |
| OS                               | SRSOSVersion                | **2000**     | Событие \| где источника == «SRS-App» и EventID == 2000 |
| Версия ОС                        | SRSOSLongVersion            | **2000**     | Событие \| где источника == «SRS-App» и EventID == 2000 |
| Alias                            | SRSAlias                    | **2000**     | Событие \| где источника == «SRS-App» и EventID == 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Событие \| где источника == «SRS-App» и EventID == 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Событие \| где источника == «SRS-App» и EventID == 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Событие \| где источника == «SRS-App» и EventID == 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Событие \| где источника == «SRS-App» и EventID == 2000 |
| Состояние микрофон конференции     | SRSConfMicrophoneStatus     | **3001**     | Событие \| где источника == «SRS-App» и EventID == 3001 |
| Состояние динамик конференции        | SRSConfSpeakerStatus        | **3001**     | Событие \| где источника == «SRS-App» и EventID == 3001 |
| Состояние по умолчанию динамика           | SRSDefaultSpeakerStatus     | **3001**     | Событие \| где источника == «SRS-App» и EventID == 3001 |
| Состояние камеры                    | SRSCameraStatus             | **3001**     | Событие \| где источника == «SRS-App» и EventID == 3001 |
| Передний план комнаты отображения состояния     | SRSFORDStatus               | **3001**     | Событие \| где источника == «SRS-App» и EventID == 3001 |
| Состояние датчиков движения             | SRSMotionSensorStatus       | **3001**     | Событие \| где источника == «SRS-App» и EventID == 3001 |
| Состояние HDMI потребления               | SRSHDMIIngestStatus         | **3001**     | Событие \| где источника == «SRS-App» и EventID == 3001 |


## <a name="define-the-microsoft-teams-rooms-views-in-log-analytics"></a>Определение представлений комнат группами Майкрософт в аналитике журнала
<a name="Define_Views"> </a>

После сбора данных и сопоставлении настраиваемых полей, можно использовать конструктор представлений для разработки панели мониторинга, содержащий различные плиток, чтобы отслеживать события комнат группы Microsoft. Используйте конструктор представлений для создания следующих плиток. Дополнительные сведения можно [создавать настраиваемые представления с помощью конструктора представление в аналитических журнала](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Предыдущие действия, описанные в этом руководстве должны быть выполнены для элементов панели мониторинга для правильной работы.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Создание панели мониторинга комнат группами Майкрософт, используя метод импорта

Можно импортировать комнат группами Майкрософт панели мониторинга и начать наблюдение за устройство быстро. Выполните следующие действия для импорта панели мониторинга.

1.  Получите файл [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) панели мониторинга.
2.  Вход на [портал Microsoft Azure](https://portal.azure.com) и перейдите к журнала аналитика и Выбор рабочей области.
3.  Откройте **Конструктор представлений**.
4.  Выберите **Импорт**, а затем выберите файл **SkypeRoomSystems_v2.omsview** .
5.  Нажмите кнопку **Сохранить**.

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Создание панели мониторинга комнат группами Майкрософт вручную

Кроме того можно создавать свои собственные панели мониторинга и добавление элементов, которые вы хотите отслеживать.

#### <a name="configure-the-overview-tile"></a>Настройка заголовков Обзор

1.  Откройте **Конструктор представлений**.
2.  Выберите **Плитку Обзор**и выберите **двух чисел** из коллекции.
3.  Имя плитку **Комнат группами Майкрософт**.
4.  Определите **первый фрагмент**:<br>
    **Условные обозначения:** Устройства, которые передаются пульса по крайней мере один раз в последний месяц<br>
    **Запроса:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Определите **второй заголовков**:<br>
    **Условные обозначения:** Активных устройств, которые отправлены пульса за последний час<br>
    **Запроса:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Выберите **Применить**.

### <a name="create-a-tile-that-displays-active-devices"></a>Создать элемент, который отображает активных устройств

1.  Выберите **Вид панели мониторинга** для запуска Добавление вашей заголовков.
2.  Выберите **, какой номер & списка** из коллекции
3.  Определение **общих** свойств:<br>
    **Групповой заголовок:** Состояние пульса<br>
    **Новую группу:** Выбранные
4.  Определение свойств **заголовков** :<br>
    **Условные обозначения:** Активных устройств (периодический сигнал, отправленных в последние 20 минут)<br>
    **Запрос для плитки: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Определение свойств **списка** :<br>
    **Список запроса:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Определите **заголовки столбцов**:<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Последний пульса
7.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Выберите **Применить**, а затем **Закрыть**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Создать элемент, который отображает устройств, проблем с подключением

1.  Выберите **, какой номер & списка** из коллекции, а затем добавьте новый фрагмент.
2.  Определение **общих** свойств:<br>
    **Групповой заголовок:** Оставить пустым<br>
    **Новую группу:** Не выбран
3.  Определение свойств **заголовков** :<br>
    **Условные обозначения:** Неактивные устройства (сообщение подтверждения не отправляются в последние 20 минут)<br>
    **Запрос для плитки: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Определение свойств **списка** :<br>
    **Список запроса:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Определите **заголовки столбцов**:<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Последний пульса
6.  Определение **запроса навигации**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Выберите **Применить**, а затем **Закрыть**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Создать элемент, который отображает устройств, которые имеют ошибки оборудования

1.  Выберите **, какой номер & списка** из коллекции, а затем добавьте новый фрагмент.
2.  Определение **общих** свойств:<br>
    **Групповой заголовок:** Состояние оборудования<br>
    **Новую группу:** Выбранные
3.  Определение свойств **заголовков** :<br>
    **Условные обозначения:** Устройства, на которых произошла ошибка оборудования за последний час<br>
    **Запрос для плитки: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Определение свойств **списка** :<br>
    **Список запроса:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Определите **заголовки столбцов**:<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Последняя ошибка
6.  Определение **запроса навигации**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Выберите **Применить**, а затем **Закрыть**.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-operating-system-versions"></a>Создать элемент, который отображает версии операционной системы корпорации Майкрософт группами комнат

1.  Выберите **список & кольцо** из коллекции, а затем добавьте новый фрагмент.
2.  Определение **общих** свойств:<br>
    **Групповой заголовок:** Сведения об операционной системе<br>
    **Новую группу:** Выбранные
3.  Определение свойств **верхнего колонтитула** :<br>
    **Название:** Версии операционной системы<br>
    **Подзаголовка:** Устройств под управлением версии операционной системы
4.  Определите свойства **пончик** :<br>
    **Запроса:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Текста по центру:** Устройства<br>
    **Операции:** Сумма
5.  Определение свойств **списка** .<br>
    **Список запроса:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Скрыть графике:** Выбранные<br>
    **Включение спарклайны:** Не выбран
6.  Определите **заголовки столбцов**.<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Оставить пустым
7.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Выберите **Применить** , а затем **Закрыть**.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-application-versions"></a>Создать элемент, который отображает версии приложений Microsoft группами комнат

1.  Выберите **список & кольцо** из коллекции, а затем добавьте новый фрагмент.
2.  Определение **общих** свойств:<br>
    **Групповой заголовок:** Сведения о приложении комнат группами Майкрософт<br>
    **Новую группу:** Выбранные
3.  Определение свойств **верхнего колонтитула** :<br>
    **Название:** Версии приложений<br>
    **Подзаголовка:** Устройств под управлением версии определенных приложений
4.  Определите свойства **пончик** :<br>
    **Запроса:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Текста по центру:** Устройства<br>
    **Операции:** Сумма
5.  Определение свойств **списка** .<br>
    **Список запроса:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Скрыть графике:** Выбранные<br>
    **Включение спарклайны:** Не выбран
6.  Определите **заголовки столбцов**.<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Оставить пустым
7.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Выберите **Применить** , а затем **Закрыть**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Создать элемент, который отображает устройств, которые имеют ошибки приложения

1.  Выберите **, какой номер & списка** из коллекции, а затем добавьте новый фрагмент.
2.  Определение **общих** свойств.<br>
    **Групповой заголовок:** Оставить пустым<br>
    **Новую группу:** Не выбран
3.  Определение свойств **заголовков** .<br>
    **Условные обозначения:** Устройства, на которых произошла ошибка приложения за последний час<br>
    **Запрос для плитки: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Определение свойств **списка** .<br>
    **Список запроса:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Определите **заголовки столбцов**.<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Последняя ошибка
6.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Выберите **Применить** , а затем **Закрыть**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Создать элемент, который отображает устройства, на которых запущены

1.  Выберите **, какой номер & списка** из коллекции, а затем добавьте новый фрагмент.
2.  Определение **общих** свойств.<br>
    **Групповой заголовок:** Оставить пустым<br>
    **Новую группу:** Не выбран
3.  Определение свойств **заголовков** .<br>
    **Условные обозначения:** Где перезапуска приложения в последние 24 часа и перезапусков устройств<br>
    **Запрос для плитки: ** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Определение свойств **списка** .<br>
    **Список запроса:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Определите **заголовки столбцов**.<br>
    **Имя:** Имя компьютера<br>
    **Значение:** Количество перезапусков
6.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Выберите **Применить** , а затем **Закрыть**.
8.  Выберите команду **Сохранить** для сохранения панели мониторинга.

После завершения создания представлений.

## <a name="configure-alerts-in-azure-monitor"></a>Настройка оповещений в Azure монитор
<a name="Alerts"> </a>

Монитор с Azure может создать оповещения для уведомления администраторов, при обнаружении неполадок консоли комнат группы Microsoft.

Монитор с Azure включает в себя встроенный механизм предупреждения, на котором выполняется через поисков в журнале запланированного через регулярные интервалы времени. Если результаты поиска журнала соответствует некоторые определенным условиям, создается запись оповещения.

Правило можно автоматически выполните одно или несколько действий для заранее уведомлять пользователя об уведомлении или вызвать другим процессом. Имеются следующие параметры оповещения:
-   Отправка сообщения электронной почты
-   Вызов внешний процесс посредством запроса HTTP POST
-   Запуск runbook в службы автоматизации Azure

В разделе [журнал оповещений в Azure монитор](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) для получения дополнительных сведений о оповещения в Azure монитор.

> [!NOTE]
> В приведенных ниже примерах отправлять оповещения по электронной почте при устройства Microsoft группами комнат приводит к возникновению ошибки оборудования или ошибки приложения.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-hardware-issues"></a>Настройка оповещения по электронной почте для проблемы с оборудованием комнат группами Майкрософт

Настройте правило оповещения, которое проверяет наличие устройств комнат группами Майкрософт, которые возникли проблемы с оборудованием за последний час.
1.  Вход на [портал Microsoft Azure](https://portal.azure.com) и перейдите к журнала аналитика и Выбор рабочей области.

2. Перейдите в рабочую область для анализа журнала и выберите **оповещения** , а затем выберите **Создать правило оповещения**

3. Выберите пункт **Добавить условие** , а затем **Custom журнала поиска**

4.  Введите следующий запрос в текстовое поле запроса поиска.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Настройка параметров оповещений логики:<br>
    **На основе:** Число результатов<br>
    **Условие:** Больше<br>
    **Treshold:** 0<br>

6. Настройка параметров оценки и выберите **выполнить**. <br>
    **Периода времени (в минутах):** 60<br>
    **Частоту (в минутах):** 60<br>

7. Настройка группы действий:
    1.  Выберите **Создание нового**
    2.  Задайте подходящие имена для поля *имя группы действие* и *Краткое имя* .
    3.  Укажите уникальное *Имя действия* и выберите **Электронной почты или SMS/Push/голосовой связи**и выберите **Изменение сведений о**.
    4.  Установите флажок электронной почты и укажите адрес электронной почты человека или группы, который будет получать оповещения.
    5.  Также можно указать номер телефона для получения уведомлений с помощью SMS, голосовой звонок или оба.
    6. Нажмите **кнопку OK**.

8. **Настройка действия** , если вы хотите переопределить Тема оповещения по электронной почте.

9. Укажите имя правила и описание.<br>
    **Имя правила:** Оповещение о сбоя оборудования комнат группами Майкрософт<br>
    **Описание:** Список устройств, в которых обнаружены проблемы оборудования за последний час<br>

10. Выберите требуемого серьезность и убедитесь, что правило будет включено.

11. Выберите **Создать правило оповещения**.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-application-issues"></a>Настройка оповещения по электронной почте для проблем приложений Microsoft группами комнат

Повторите ту же процедуру, но используйте следующий запрос в список устройств, которые возникли проблемы с приложениями за последний час.

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

Теперь вы завершили определение оповещения. Можно определить дополнительные предупреждения с помощью приведенных выше примерах.

Когда создается соответствующее уведомление, вы получите сообщение электронной почты, в котором приведены устройства, в которых обнаружены проблемы за последний час.

![Монитор Azure образец сообщения электронной почты] (../../media/Deploy-Azure-Monitor-6.png "Монитор Azure образец сообщения электронной почты")

## <a name="configure-all-devices-for-azure-monitoring"></a>Настройка всех устройств для наблюдение за Azure
<a name="configure_all_devices"></a> После настройки панели мониторинга и оповещения можно Установка и настройка агента Microsoft мониторинг на всех устройствах комнат группами Майкрософт для выполнения мониторинга развертывания.

Несмотря на то, что можно установить и настроить агент Microsoft мониторинг вручную на каждом устройстве, мы настоятельно рекомендуем использовать существующие средств развертывания программного обеспечения и методы.

При создании устройство комнат группами Майкрософт в первый раз, может потребоваться включить шаги установки и настройки агента Microsoft мониторинг как часть процесса построения. Дополнительные сведения можно [установить агент, с помощью командной строки](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Развертывание агента Microsoft мониторинга с помощью объектов групповой политики (GPO)

Если вы уже развернули устройство комнат группами Майкрософт, перед реализацией мониторинга Azure, предоставленного сценария можно использовать для установки и настройки агентов с помощью объектов групповой политики Active Directory.

1.  Создание общей сетевой путь и предоставить ей права чтения для группы **Компьютеров домена** .

2.  Загрузка 64-разрядная версия Microsoft мониторинга агента для Windows из<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Извлеките содержимое пакета установки в сетевой папке.
    1.  Откройте окно командной строки и выполните **MMASetup AMD64.exe/c**
    2.  Укажите папку, которую вы только что создали и извлеките содержимое.

4.  Создание нового объекта групповой политики и назначения ее подразделение, где хранятся учетные записи компьютера комнат группами Майкрософт.

5.  Настройте политику выполнения PowerShell:
    1.  Изменение только что созданный объект групповой политики и выберите пункты Конфигурация компьютера \\ политик \\ административные шаблоны \\ компоненты Windows \\ Windows PowerShell
    2.  Включить **Включить выполнение сценария** и задать **Политику выполнения** **Разрешить локальных сценариев**.

6.  Настройка сценариев загрузки:
    1.  Скопируйте приведенный ниже сценарий и сохраните файл с именем Install MMAgent.ps1.
    2.  Изменение параметров WorkspaceId, WorkspaceKey и SetupPath в соответствии с вашей конфигурации.
    3.  Изменение одного объекта групповой политики и выберите пункты Конфигурация компьютера \\ политик \\ Конфигурация Windows \\ сценарии (запуск и завершение)
    4.  Дважды щелкните параметр **Запуск**, а затем выберите **Скриптов PowerShell**.
    5.  Выберите **Показать файлы**и затем скопируйте файл **Установки MMAgent.ps1** эту папку.
    6.  Выберите **Добавить**, а затем **Обзор**.
    7.  Выберите скрипт ps1, скопированные.

7.  Устройства Microsoft группами комнат следует Установка и настройка агента Microsoft мониторинг второй перезагрузкой.

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
> При необходимости повторно настройте агент, перетащить его в другой рабочей области и изменение параметров прокси-сервера после первоначальной установки можно найти в статье [Управление и обслуживание анализа журнала агента](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) .

## <a name="additional-solutions"></a>Дополнительные решения
<a name="Solutions"> </a>

Azure монитор предоставляет решения для управления встроенных через его [каталог решений](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) для дальнейшей наблюдения за среды. Мы настоятельно рекомендуем добавлять решения для [Управления предупреждениями](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) и [Azure журнала Analytics агента работоспособности](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) в рабочей области.

> [!NOTE]
> Агент работоспособности решения может помочь определить устаревшие или поврежденные агенты мониторинг Microsoft во всей среде и решения управления предупреждениями содержатся сведения о оповещений, которые были созданы в течение заданного периода.

## <a name="see-also"></a>См. также

[Планирование управления группами комнат Microsoft Azure монитор](../../plan-your-deployment/clients-and-devices/azure-monitor.md)

[Управление устройствами комнат группы Microsoft Azure монитор](../../manage/skype-room-systems-v2/azure-monitor.md)