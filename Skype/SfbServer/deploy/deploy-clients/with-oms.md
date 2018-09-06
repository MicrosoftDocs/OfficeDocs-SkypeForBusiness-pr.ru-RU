---
title: Развертывание управления системами комнат Skype версии 2 с помощью OMS
ms.author: jambirk
author: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Эта статья посвящена процедуре для развертывания управления устройствами v2 систем комнаты Скайп интегрированная, начала до конца способом, с помощью Microsoft Operations Management Suite.
ms.openlocfilehash: 0d1cd51bb80a287078ca4d85bdaec721e78d24ff
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "23256352"
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a>Развертывание управления системами комнат Skype версии 2 с помощью OMS

В этой статье описывается установка и развертывание интегрированная, сквозного управления устройствами версии 2 Скайп комнаты систем с помощью Microsoft Operations Management Suite.

Можно настроить пакет управления Microsoft операций для обеспечения базовой телеметрии и оповещения, которые помогут вам управлять Скайп собрания комнаты устройств. Мере разработки решения по управлению можно развернуть дополнительные данные и возможности управления для создания более подробные представления производительности и доступности устройства.

Выполнив в этом руководстве, можно использовать панели мониторинга как следующий пример, чтобы получить подробные сведения о состоянии отчетов о доступности устройства, приложения и работоспособности оборудования и распространения версии приложений систем комнаты Скайп версии 2.

![Пример OMS представления для SRS версии 2] (../../media/Deploy_OMS_1.png "Пример OMS представления для SRS версии 2")

В общих чертах вам необходимо выполнить следующие задачи.


1.  [Проверка конфигурации пакет управления Operations](with-oms.md#validate_OMS)
2.  [Настройка тестовых устройств для настройки управления Operations Management Suite](with-oms.md#configure_test_devices)
3.  [Сопоставление настраиваемых полей](with-oms.md#Custom_fields)
4.  [Определение представлений систем комнаты Скайп версии 2 в пакет управления Operations](with-oms.md#Define_Views)
5.  [Определение оповещений](with-oms.md#Alerts)
6.  [Настройка всех устройств для управления набора операций](with-oms.md#configure_all_devices)
7.  [Настройка дополнительных операций Management Suite решений](with-oms.md#Solutions)

> [!IMPORTANT]
> Несмотря на то, что в минимальной конфигурации пакет управления Operations можно отслеживать компьютера под управлением операционной системы Windows, по-прежнему существует некоторых систем комнаты Скайп версии 2 – этапов, которые необходимо выполнить перед началом развертывания агентов всех Скайп комнаты Устройства системы.
> Таким образом настоятельно рекомендуется выполнить все действия по настройке в правильном порядке для управляемой установки и настройки. Качество конечный результат сильно зависит от качества начальной настройки.

## <a name="validate-operations-management-suite-configuration"></a>Проверка конфигурации пакет управления Operations
<a name="validate_OMS"> </a>

Необходимо установить пакет управления Operations рабочей области для запуска сбор данных в журналах с системами комнаты Скайп v2 устройств. Рабочая область — уникальный анализа журнала среды с собственными хранилище данных, источники данных и решения. Если у вас уже есть существующей рабочей области для анализа журнала, его можно использовать для отслеживания развертывания систем комнаты Скайп версии 2 или можно создать должно выделенного анализа журнала рабочую область для наблюдение за системами комнаты Скайп версии 2.

Если вам необходимо создать новую рабочую область анализа журнала, следуйте инструкциям, представленным в статье [Создание рабочей области для анализа журнала на портале Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-quick-create-workspace)

> [!NOTE]
> Для использования журнала аналитики с помощью пакета управления Operations, необходимо иметь active Azure подписки. Если у вас нет Azure подписки, можно создать [бесплатную пробную подписку](https://azure.microsoft.com/free) в качестве отправной точки.


### <a name="configure-operations-management-suite-to-collect-skype-room-systems-v2-event-logs"></a>Настройка операций Management Suite собирать систем комнаты Скайп версии 2

Аналитика журнала только собирает события в журнале событий Windows, которые указаны в диалоговом окне настройки. Для каждого журнала событий с помощью выбранного серьезности собираются.

Необходимо настроить Operations Management Suite собирать журналы, требуемые для отслеживания состояния устройства и приложение-версии 2 Скайп комнаты систем. Устройства v2 систем комнаты Скайп используют **Скайп комнаты системный** журнал событий.

Настройка набора операций управления для сбора событий версии 2 Скайп комнаты систем, в статье [источников данных журнала событий Windows в аналитике журнала](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

![Параметры журнала событий] (../../media/Deploy_OMS_2.png "Параметры журнала событий")


> [!IMPORTANT]
> Выберите **Скайп комнаты системный** журнал событий и затем установите флажки **ошибки**, **предупреждения**и **сведения** .

## <a name="configure-test-devices-for-operations-management-suite-setup"></a>Настройка тестовых устройств для установки пакетов управления Operations
<a name="configure_test_devices"> </a>

Необходимо подготовить набор операций управления должны иметь возможность отслеживания событий, связанных с версии 2 Скайп комнаты систем. Начать с, необходимо выполнить развертывание агентов пакет управления Operations устройств версии 2 систем комнаты Скайп только один или два физических доступ к и передавать эти устройства проверки создания некоторых данных и записывать его в рабочую область аналитических журнала.

### <a name="install-operations-management-suite-agents-to-test-devices"></a>Установить пакет управления Operations агенты для тестирования устройств

Развертывание агента Operations Management Suite тестовых устройств с помощью инструкций, приведенных в [компьютеры Windows подключиться к службе анализа журнала в Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows). В этой статье приводятся подробные сведения о действиях, которые для развертывания Microsoft мониторинга агента для Windows, инструкции по получении пакет управления Operations *Идентификатор рабочей области* и *первичный ключ* для получения устройств систем комнаты Скайп версии 2 подключена к развертывания пакета управления операции и действия для проверки подключения агента анализа журнала.

### <a name="generate-sample-skype-room-systems-events"></a>Создание образца Скайп комнаты системных событий

После развертывания агентов управления набор операций на тестовых устройств убедитесь, что аналитика журнала собирают данные журналов событий.

1.  Войдите в [портал Microsoft Operations Management Suite](https://aka.ms/omsportal).

2.  Перечислены события, создаваемые устройства версии 2 Скайп комнаты систем:
    1.  Перейти к **Поиску журнала** и использовать запрос для извлечения записей, которые будут иметь настраиваемого поля.
    2.  Пример запроса:`Event | where Source == "SRS-App"`

3.  Убедитесь в том, что запрос возвращает записи журнала, включая успешные пульса события.

4.  Создание проблема оборудования и проверить, что необходимые события регистрируются в пакет управления Operations.
    1.  Отключите один из периферийных устройств на тестовых систем комнаты Скайп v2 системы. Это может быть камера, устройство громкой связи, микрофон или отображения передний план комнаты
    2.  Подождите 10 минут для журнала событий, которые следует добавить в пакет управления Operations.
    3.  Использование запроса для списка Список аппаратных предупреждений об ошибках:`Event | where EventID == 3001`

5.  Создание проблем приложений и проверки необходимых событий.
    1.  Изменение конфигурации приложения v2 Скайп комнаты систем и введите пара неправильный адрес и пароль Session Initiation Protocol (SIP).
    2.  Подождите 10 минут для журнала событий, которые следует добавить в пакет управления Operations.
    3.  Использование запроса на события ошибки приложения списка:`Event | where EventID == 2001`

> [!IMPORTANT]
> Эти журналы событий примера требуются перед настраиваемых полей можно настроить. Не переходите к следующему шагу, пока не будут собраны необходимые журналы событий.

## <a name="map-custom-fields"></a>Сопоставление настраиваемых полей
<a name="Custom_fields"> </a>

Использование настраиваемых полей для извлечения данных из журналов событий. Необходимо определить настраиваемые поля, которые будут использоваться позднее представления панели мониторинга, оповещения и заголовков. Просмотреть [настраиваемых полей в аналитике журнала](https://docs.microsoft.com/azure/log-analytics/log-analytics-custom-fields) и ознакомиться с понятиями, прежде чем начать создание настраиваемых полей.

Чтобы извлечь настраиваемых полей из него захвата журналы событий, выполните следующие действия:

1.  Войдите в [портал Microsoft Operations Management Suite](https://aka.ms/omsportal).

2.  Перечислены события, создаваемые устройства версии 2 Скайп комнаты систем:
    1.  Перейти к **Поиску журнала** и использовать запрос для извлечения записей, которые будут иметь настраиваемого поля.
    2.  Пример запроса:`Event | where Source == "SRS-App"`

3.  Выберите один из записей, нажмите кнопку слева и запустите мастер извлечения поля.

   ![Мастер извлечения поля] (../../media/Deploy_OMS_3.png "Мастер извлечения поля")

4.  Выделите данные, которые вы хотите извлечь из RenderedDescription и укажите название поля. В таблице 1 приведены имена полей, которые следует использовать.

   ![Определение настраиваемого поля] (../../media/Deploy_OMS_4.png "Определение настраиваемого поля")

5.  Использование сопоставлений, показано в *таблице 1*. Пакет управления Operations автоматически добавляет ** \_CF** строка при определении нового поля.

> [!IMPORTANT]
> Имейте в виду, что все поля JSON и пакет управления Operations зависят от регистра символов.

> Обратите внимание на состояние флажка EventID в таблице ниже. Убедитесь, что проверить состояние этого флажка для операций Management Suite успешно извлечение значения настраиваемых полей.
>
> ![Определение настраиваемого поля] (../../media/Deploy_OMS_5.png "Определение настраиваемого поля")

**В таблице 1**

| Поле JSON                   | Настраиваемое поле OMS           | Идентификатор события        |
|:-----------------------------|:---------------------------|:----------------|
| Описание                  | SRSEventDescription_CF     | Не выбран    |
| ResourceState                | SRSResourceState_CF        | Не выбран    |
| Имя_операции                | SRSOperationName_CF        | Не выбран    |
| OperationResult              | SRSOperationResult_CF      | Не выбран    |
| OS                           | SRSOSVersion_CF            | Не выбран    |
| OSVersion                    | SRSOSLongVersion_CF        | Не выбран    |
| Alias                        | SRSAlias_CF                | Не выбран    |
| Отображаемое имя                  | SRSDisplayName_CF          | Не выбран    |
| AppVersion                   | SRSAppVersion_CF           | Не выбран    |
| IPv4-адрес                  | SRSIPv4Address_CF          | Не выбран    |
| IPv6-адрес                  | SRSIPv6Address_CF          | Не выбран    |
| Передний план комнаты отображения состояния | SRSFORDStatus_CF           | 3001            |
| Состояние камеры                | SRSCameraStatus_CF         | 3001            |
| Состояние микрофон конференции | SRSConfMicrophoneStatus_CF | 3001            |
| Состояние динамик конференции    | SRSConfSpeakerStatus_CF    | 3001            |
| Состояние по умолчанию динамика       | SRSDefaultSpeakerStatus_CF | 3001            |
| Состояние датчиков движения         | SRSMotionSensorStatus_CF   | 3001            |
| Состояние HDMI потребления           | SRSHDMIIngestStatus_CF     | 3001            |


## <a name="define-the-skype-room-systems-v2-views-in-operations-management-suite"></a>Определение представлений систем комнаты Скайп версии 2 в пакет управления Operations
<a name="Define_Views"> </a>

После сбора данных и сопоставлении настраиваемых полей, управления набор операций открыть в конструкторе можно использовать для разработки панели мониторинга, содержащий различных заголовков отслеживания событий систем комнаты Скайп версии 2. С помощью конструктора представлений создайте следующие плитки. Дополнительные сведения можно [Открыть в конструкторе используется для создания настраиваемых представлений в аналитике журнала](https://docs.microsoft.com/azure/log-analytics/log-analytics-view-designer)

> [!NOTE]
> Более ранних действия, описанные в этом руководстве должны быть выполнены для элементов панели мониторинга для правильной работы.


### <a name="create-a-skype-room-systems-v2-dashboard-by-using-the-import-method"></a>Создание панели мониторинга системы комнаты Скайп версии 2 с помощью метода импорта

Можно импортировать пакет управления Operations панели мониторинга и начать наблюдение за устройство немедленно. Выполните следующие действия для импорта панели мониторинга.

1.  Получите файл [SkypeRoomSystems_v2.omsview](https://download.microsoft.com/download/9/0/D/90D4826A-9FD2-47D2-B911-97BF1737F4F7/SkypeRoomSystems_v2.omsview) панели мониторинга.
2.  Войдите в [портал Microsoft Operations Management Suite](https://aka.ms/omsportal).
3.  Откройте **Конструктор представлений**.
4.  Выберите **Импорт**, а затем выберите файл **SkypeRoomSystems_v2.omsview** .
5.  Нажмите кнопку **Сохранить**.

### <a name="create-a-skype-room-systems-v2-dashboard-manually"></a>Создание панели мониторинга v2 систем комнаты Скайп вручную

Кроме того можно создавать свои собственные панели мониторинга и добавление элементов, которые вы хотите отслеживать.

#### <a name="configure-the-overview-tile"></a>Настройка заголовков Обзор
1.  Откройте **Конструктор представлений**.
2.  Выберите **Плитку Обзор**и выберите **двух чисел** из коллекции.
3.  Имя плитку **систем комнаты Скайп версии 2**.
4.  Определите **первый фрагмент**:<br>
    **Условные обозначения:** Устройства, которые передаются пульса по крайней мере один раз в последний месяц<br>
    **Запроса:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Определите **второй заголовков**:<br>
    **Условные обозначения:** Активных устройств, которые отправлены пульса за последний час<br>
    **Запроса:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Выберите **Применить**.

### <a name="create-a-tile-that-displays-active-devices"></a>Создать элемент, который отображает активных устройств
1.  Выберите **Вид панели мониторинга** для запуска Добавление вашей заголовков.
2.  Выберите **номер & списка** из коллекции
3.  Определение **общих** свойств:<br>
    **Групповой заголовок:** Состояние пульса<br>
    **Новую группу:** Выбранные
4.  Определение свойств **заголовков** :<br>
    **Условные обозначения:** Активных устройств (периодический сигнал, отправленных в последние 20 минут)<br>
    **Запрос для плитки: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Определение свойств **списка** :<br>
    **Список запроса:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Определите **заголовки столбцов**:<br>
    **Имя:** Отображаемое имя<br>
    **Значение:** Последний пульса
7.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Выберите **Применить**, а затем **Закрыть**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Создать элемент, который отображает устройств, проблем с подключением
1.  Выберите **номер & списка** из коллекции, а затем добавьте новый фрагмент.
2.  Определение **общих** свойств:<br>
    **Групповой заголовок:** Оставить пустым<br>
    **Новую группу:** Не выбран
3.  Определение свойств **заголовков** :<br>
    **Условные обозначения:** Неактивные устройства (сообщение подтверждения не отправляются в последние 20 минут)<br>
    **Запрос для плитки: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Определение свойств **списка** :<br>
    **Список запроса:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Определите **заголовки столбцов**:<br>
    **Имя:** Отображаемое имя<br>
    **Значение:** Последний пульса
6.  Определение **запроса навигации**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Выберите **Применить**, а затем **Закрыть**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Создать элемент, который отображает устройств, которые имеют ошибки оборудования

1.  Выберите **номер & списка** из коллекции, а затем добавьте новый фрагмент.
2.  Определение **общих** свойств:<br>
    **Групповой заголовок:** Состояние оборудования<br>
    **Новую группу:** Выбранные
3.  Определение свойств **заголовков** :<br>
    **Условные обозначения:** Устройства, на которых произошла ошибка оборудования за последний час <br>
    **Запрос для плитки: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Определение свойств **списка** :<br>
    **Список запроса:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer```
5.  Определите **заголовки столбцов**:<br>
    **Имя:** Отображаемое имя<br>
    **Значение:** Последняя ошибка
6.  Определение **запроса навигации**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Выберите **Применить**, а затем **Закрыть**.

### <a name="create-a-tile-that-displays-skype-room-systems-v2-operating-system-versions"></a>Создать элемент, который отображает версии операционной системы Скайп комнаты систем версии 2

1.  Выберите **список & пончик** из коллекции, а затем добавьте новый фрагмент.
2.  Определение **общих** свойств:<br>
    **Групповой заголовок:** Сведения о операционной системы <br>
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
    **Имя:** Отображаемое имя<br>
    **Значение:** Оставить пустым
7.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Выберите **Применить** , а затем **Закрыть**.

### <a name="create-a-tile-that-displays-skype-room-systems-v2-application-versions"></a>Создать элемент, который отображает версии приложений системы комнаты Скайп версии 2

1.  Выберите **список & пончик** из коллекции, а затем добавьте новый фрагмент.
2.  Определение **общих** свойств:<br>
    **Групповой заголовок:** Сведения о приложении систем комнаты Скайп версии 2 <br>
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
    **Имя:** Отображаемое имя<br>
    **Значение:** Оставить пустым
7.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Выберите **Применить** , а затем **Закрыть**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Создать элемент, который отображает устройств, которые имеют ошибки приложения

1.  Выберите **номер & списка** из коллекции, а затем добавьте новый фрагмент.
2.  Определение **общих** свойств.<br>
    **Групповой заголовок:** Оставить пустым<br>
    **Новую группу:** Не выбран
3.  Определение свойств **заголовков** .<br>
    **Условные обозначения:** Устройства, на которых произошла ошибка приложения за последний час<br>
    **Запрос для плитки: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Определение свойств **списка** .<br>
    **Список запроса:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Определите **заголовки столбцов**.<br>
    **Имя:** Отображаемое имя<br>
    **Значение:** Последняя ошибка
6.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Выберите **Применить** , а затем **Закрыть**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Создать элемент, который отображает устройства, на которых запущены

1.  Выберите **номер & списка** из коллекции, а затем добавьте новый фрагмент.
2.  Определение **общих** свойств.<br>
    **Групповой заголовок:** Оставить пустым<br>
    **Новую группу:** Не выбран
3.  Определение свойств **заголовков** .<br>
    **Условные обозначения:** Где перезапуска приложения в последние 24 часа и перезапусков устройств<br>
    **Запрос для плитки: ** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Определение свойств **списка** .<br>
    **Список запроса:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Определите **заголовки столбцов**.<br>
    **Имя:** Отображаемое имя<br>
    **Значение:** Количество перезапусков
6.  Определение **запроса навигации**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Выберите **Применить** , а затем **Закрыть**.
8.  Выберите команду **Сохранить** для сохранения панели мониторинга.

После завершения создания представлений.

Пакет управления Microsoft Operations портала или пакет управления Operations мобильных клиентов для [Windows Phone](https://www.microsoft.com/en-us/store/p/microsoft-operations-management-suite/9wzdncrfjz2r), [iOS](https://itunes.apple.com/us/app/microsoft-operations-management-suite/id1042424859)и [Android](https://play.google.com/store/apps/details?id=com.microsoft.operations.AndroidPhone) можно использовать для доступа к вашей представлений.

## <a name="configure-alerts-in-operations-management-suite"></a>Настройка оповещений в пакет управления Operations
<a name="Alerts"></a> Устройства при систем комнаты Скайп версии 2 обнаруживает ошибку, пакет управления Microsoft Operations может создать оповещения для уведомления администраторов подробные сведения о проблеме.

Пакет управления Operations включает в себя встроенный механизм предупреждения, на котором выполняется через поисков в журнале запланированного через регулярные интервалы времени. Если результаты поиска журнала соответствует некоторые определенным условиям, создается запись оповещения.

![Механизм предупреждения OMS] (../../media/Deploy_OMS_6.png "Механизм предупреждения OMS")

Правило можно автоматически выполните одно или несколько действий для заранее уведомлять пользователя об уведомлении или вызвать другим процессом. Имеются следующие параметры с оповещениями пакет управления Operations:
-   Отправка сообщения электронной почты
-   Вызов внешний процесс посредством запроса HTTP POST
-   Запуск runbook в службы автоматизации Azure

В разделе [Общие сведения о оповещений в аналитике журнала](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts) для получения дополнительных сведений о оповещения в пакет управления Operations.

> [!NOTE]
> В приведенных ниже примерах отправлять оповещения по электронной почте, если устройство v2 систем комнаты Скайп создает оборудования или ошибки приложения.


### <a name="configure-an-email-alert-for-skype-room-systems-v2-hardware-issues"></a>Настройка оповещения по электронной почте для проблемы с оборудованием систем комнаты Скайп версии 2

Настройте правило оповещения, которое проверяет наличие устройства версии 2 Скайп комнаты систем, которые были применены неполадки с оборудованием за последний час.
1.  Войдите в [портал Microsoft Operations Management Suite](https://aka.ms/omsportal).

2.  Выберите **Журнал поиска**.

3.  Введите следующий запрос и затем выберите команду **выполнить**.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

4.  После выполнения запроса выберите **оповещения**. Откроется страница **Добавить правило оповещения** .

5.  Настройка параметров оповещений с помощью следующие сведения:<br>
    **Имя правила:** Оповещение о сбоя оборудования комнаты Скайп систем версии 2<br>
    **Описание:** Список устройств, в которых обнаружены проблемы оборудования за последний час<br>
    **Уровень серьезности:** Критические<br>
    **Запроса:** Использовать предварительно заполненными поискового запроса<br>
    **Временной интервал:** 1 час<br>
    **Частота оповещений:** 1 час<br>
    **Количество результатов:** Больше 0<br>
    **Электронной почты субъекта:** Оповещение о сбоя оборудования комнаты Скайп систем версии 2<br>
    **Получателей:** Укажите адреса электронной почты, используя точку с запятой в качестве разделителей<br>

6.  Нажмите кнопку **Сохранить**.

### <a name="configure-an-email-alert-for-skype-room-systems-v2-application-issues"></a>Настройка оповещения по электронной почте для проблем приложений системы комнаты Скайп версии 2

Настройка оповещений правила, которое проверяет наличие систем комнаты Скайп v2 устройств, которые были применены проблем приложений за последний час.
1.  Выберите **Журнал поиска**.

2.  Введите следующий запрос и затем выберите команду **выполнить**.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(10h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

3.  После выполнения запроса выберите **оповещения**. Откроется страница **Добавить правило оповещения** .

4.  Настройка параметров оповещений с помощью следующие сведения:<br>
    **Имя правила:** Оповещение о сбое при Скайп комнаты систем версии 2 приложения<br>
    **Описание:** Список устройств, в которых обнаружены проблемы приложения за последний час<br>
    **Уровень серьезности:** Критические<br>
    **Запроса:** Использовать предварительно заполненными поискового запроса<br>
    **Временной интервал:** 1 час<br>
    **Частота оповещений:** 1 час<br>
    **Количество результатов:** Больше 0<br>
    **Электронной почты субъекта:** Оповещение о сбое при Скайп комнаты систем версии 2 приложения<br>
    **Получателей:** Укажите адреса электронной почты, используя точку с запятой в качестве разделителей

5.  Нажмите кнопку **Сохранить**.

Теперь вы завершили определение оповещения. Можно определить дополнительные предупреждения с помощью приведенных выше примерах.

Когда создается соответствующее уведомление, вы получите сообщение электронной почты, в котором приведены устройства, в которых обнаружены проблемы за последний час.

![Пример OMS оповещения по электронной почте] (../../media/Deploy_OMS_7.png "Пример OMS оповещения по электронной почте")

Используйте страницу параметров оповещений для изменения существующей конфигурации оповещений, или для отключения или удаления оповещения.

![Параметры оповещений OMS] (../../media/Deploy_OMS_8.png "Параметры оповещений OMS")

> [!NOTE]
> Может потребоваться использовать Azure портала для добавления или изменения пакет управления Operations оповещения, если в рабочей области пакет управления Operations настроена для расширения пакет управления Operations оповещений в Azure. Для получения дополнительных сведений см. [оповещения расширить с портала OMS в Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-alerts-extend).

## <a name="configure-all-devices-for-operations-management-suite"></a>Настройка всех устройств для управления набора операций
<a name="configure_all_devices"></a> После настройки панели мониторинга и оповещения можно Установка и настройка агенты управления набор операций на всех устройствах систем комнаты Скайп v2 для выполнения мониторинга развертывания.

Несмотря на то, что можно установить и настроить пакет управления Operations агенты вручную на каждом устройстве, мы настоятельно рекомендуем использовать существующие средств развертывания программного обеспечения и методы.

При создании устройство систем комнаты Скайп версии 2 в первый раз, может потребоваться включить шагов установки и настройки агента Operations Management Suite как часть процесса построения. Дополнительные сведения можно [установить агент, с помощью командной строки](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-operations-management-suite-agents-by-using-a-group-policy-object"></a>Развертывание пакета управления Operations агентов с помощью объекта групповой политики

Если вы уже развернули устройство v2 систем комнаты Скайп перед реализацией операций Management Suite, предоставленного сценария можно использовать для установки и настройки агентов с помощью групповых политик Active Directory.

1.  Создание общей сетевой путь и предоставить ей права чтения для группы **Компьютеров домена** .

2.  Загрузка 64-разрядная версия операции управления набор агентов для Windows из<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Извлеките содержимое пакета установки в сетевой папке.
    1.  Откройте окно командной строки и выполните **MMASetup AMD64.exe/c**
    2.  Укажите папку, которую вы только что создали и извлеките содержимое.

4.  Создание нового объекта групповой политики и назначения ее подразделение, где хранятся учетные записи компьютера систем комнаты Скайп версии 2.

5.  Настройте политику выполнения PowerShell:
    1.  Изменение только что созданный объект групповой политики и выберите пункты Конфигурация компьютера \\ политик \\ административные шаблоны \\ компоненты Windows \\ Windows PowerShell
    2.  Включить **Включить выполнение сценария** и задать **Политику выполнения** **Разрешить локальных сценариев**.

6.  Настройка сценариев загрузки:
    1.  Скопируйте приведенный ниже сценарий и сохраните файл с именем Install OMSAgent.ps1.
    2.  Изменение параметров WorkspaceId, WorkspaceKey и SetupPath в соответствии с вашей конфигурации.
    3.  Изменение одного объекта групповой политики и выберите пункты Конфигурация компьютера \\ политик \\ Конфигурация Windows \\ сценарии (запуск и завершение)
    4.  Дважды щелкните параметр **Запуск**, а затем выберите **Скриптов PowerShell**.
    5.  Выберите **Показать файлы**и затем скопируйте файл **Установки OMSAgent.ps1** эту папку.
    6.  Выберите **Добавить**, а затем **Обзор**.
    7.  Выберите скрипт ps1, скопированные.

7.  Устройств систем комнаты Скайп версии 2 следует Установка и настройка агента мониторинг Microsoft с второй перезагрузки.


    ```
    # Install-OMSAgent.ps1
    <#
    Date:        04/20/2018
    Script:      Install-OMSAgent.ps1
    Version:     1.0
    #>

    # Set the parameters
    $WorkspaceId = "<your workspace id>"
    $WorkspaceKey = "<your workspace key>"
    $SetupPath = "\\Server\Share"

    $SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"

    # $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"

    # Start PowerShell logging
    Start-Transcript -Path C:\OMSAgentInstall.Log

    # Check if the Microsoft Monitoring Agent is installed
    $mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'

    # Check if the Microsoft Monitoring agent is installed
    if (!$mma)
    {
        #Install agent
        Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
    }

    # Check if the agent has a valid configuration
    $CheckOMS = $mma.GetCloudWorkspace($WorkspaceId).AgentId
    if (!$CheckOMS)
    {
        # Apply new configuration
        $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
        $mma.ReloadConfiguration()
    }

    Stop-Transcript

    ```

> [!NOTE]
> При необходимости повторно настройте агент, перетащить его в другой рабочей области и изменение параметров прокси-сервера после первоначальной установки можно найти в статье [Управление и обслуживание анализа журнала агента](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-manage) .

## <a name="additional-solutions"></a>Дополнительные решения
<a name="Solutions"> </a>

Пакет управления Operations предоставляет встроенные решения по его [каталог решений](https://docs.microsoft.com/azure/log-analytics/log-analytics-add-solutions) для дальнейшей наблюдения за среды. Мы настоятельно рекомендуем добавлять решения для [Управления предупреждениями](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) и [Агент работоспособности](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-agenthealth) в рабочую область пакет управления Operations.

![Представления OMS] (../../media/Deploy_OMS_9.png "Представления OMS")

> [!NOTE]
> Агент работоспособности решения может помочь определить устаревшие или поврежденные агенты управления набор операций во всей среде и решения управления предупреждениями содержатся сведения о оповещений, которые были созданы в течение заданного периода.

## <a name="see-also"></a>См. также

[Планирование управления системами комнат Skype версии 2 с помощью OMS](../../plan-your-deployment/clients-and-devices/oms-management.md)

[Управление устройствами Систем комнат Skype версии 2 с помощью OMS](../../manage/skype-room-systems-v2/oms.md)
