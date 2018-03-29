---
title: Развертывание управления системами комнат Skype версии 2 с помощью OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Эта статья посвящена процедуре для развертывания управления устройствами v2 систем комнаты Скайп интегрированная, начала до конца способом, с помощью Microsoft Operations Management Suite.
ms.openlocfilehash: 0d0490d92a5513dad38a9ff6348a957204274878
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a>Развертывание управления системами комнат Skype версии 2 с помощью OMS
 
Эта статья посвящена процедуре для развертывания управления устройствами v2 систем комнаты Скайп интегрированная, начала до конца способом, с помощью Microsoft Operations Management Suite. 
  
Microsoft Operations Management Suite (OMS) можно настроить для предоставления базовых данных телеметрии, которые помогут управлять устройствами для конференц-залов Skype. По мере повышения эффективности решения для управления можно приобрести дополнительные данные и возможности управления для создания более подробного представления о производительности устройств.
  
В общих чертах вам необходимо выполнить следующие задачи.
  
1. [Настройка устройств для управления с помощью OMS ](with-oms.md#config_devices)
    
2. [Сопоставление настраиваемых полей](with-oms.md#Custom_fields)
    
3. [Определение представлений SRS версии 2 в OMS](with-oms.md#Views)
    
## <a name="find-and-record-device-locations-capabilities-and-configurations"></a>Поиск и запись расположений, возможностей и конфигураций устройств
<a name="find_devices"> </a>

Первым шагом является создание подробной базы данных всего оборудования в системе с указанием сведений о его возможностях, конфигурациях и расположении. Для выполнения этой задачи в малых и средних организациях может быть достаточно сформировать электронную таблицу. В более крупной организации, возможно, потребуется рассмотреть использование средств управления активами и сторонних служб. Важно записать расположение каждого устройства и все относящиеся к нему сведения.
  
После выполнения этой задачи вы можете использовать эту информацию для отправки технических специалистов на место, а также для управления исправлениями и обновлениями устройств.
  
## <a name="configure-devices-for-oms-management"></a>Настройка устройств для управления с помощью OMS 
<a name="config_devices"> </a>

Для каждого устройства SRS следуйте инструкциям на компьютерах [Windows подключиться к службе анализа журнала в Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents).
  
## <a name="configure-oms-to-collect-device-event-logs"></a>Настройка OMS для сбора журналов событий устройств
<a name="config_devices"> </a>

Необходимо будет специально настроить OMS собирать журналы событий с помощью SRS устройств с помощью действия, описанные в [Источники данных журнала событий Windows в аналитике журнала](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events). В журнал событий SRS для выбора — «Система комнаты Скайп» и должен установите флажки параметр для всех типов: ошибки, предупреждения и информации.
  
## <a name="map-custom-fields"></a>Сопоставление настраиваемых полей
<a name="Custom_fields"> </a>

Прежде чем можно будет использовать заголовков, созданные в [версии 2 SRS определение представления в OMS](with-oms.md#Views) , вам потребуется создать настраиваемые поля для представления. Просмотрите [настраиваемых полей в аналитике журнала](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields) для получения дополнительных сведений о создании настраиваемых полей.
  
Использование сопоставления, показанного ниже, OMS автоматическое добавление _CF при определении нового поля. 
  
> [!IMPORTANT]
> Обратите внимание, что во всех полях JSON и OMS учитывается регистр символов. 
  
**Сопоставление настраиваемого поля**

|**Поле JSON**|**Настраиваемое поле OMS**|
|:-----|:-----|
|Описание  <br/> |SRSEventDescription_CF  <br/> |
|ResourceState  <br/> |SRSResourceState_CF  <br/> |
|Имя_операции  <br/> |SRSOperationName_CF  <br/> |
|OperationResult  <br/> |SRSOperationResult_CF  <br/> |
|OS  <br/> |SRSOSVersion_CF  <br/> |
|OSVersion  <br/> |SRSOSLongVersion_CF  <br/> |
|Alias  <br/> |SRSAlias_CF  <br/> |
|Отображаемое имя  <br/> |SRSDisplayName_CF  <br/> |
|AppVersion  <br/> |SRSAppVersion_CF  <br/> |
|IPv4-адрес  <br/> |SRSIPv4Address_CF  <br/> |
|IPv6-адрес  <br/> |SRSIPv6Address_CF  <br/> |
   
## <a name="define-the-srs-v2-views-in-oms"></a>Определение представлений SRS версии 2 в OMS
<a name="Views"> </a>

После сбора данных и сопоставления настраиваемых полей можно использовать конструктор представлений OMS для разработки панели мониторинга с плитками для мониторинга событий SRS версии 2. Используйте конструктор представлений для создания следующих плиток, обратитесь к [Открыть в конструкторе используется для создания настраиваемых представлений в аналитике журнала](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer) при необходимости.
  
### <a name="create-a-tile-that-shows-healthy-devices"></a>Создание плитки, отображающей работоспособные устройства

1. Определите ситуацию использования.  
    
    На этой плитке отображаются все устройства, отправившие сообщение периодического сигнала в течение последних 10 минут.
    
2. Укажите заголовок группы.  
    
   ```
   SRS v2
   ```

3. Установите флажок для новой группы.
    
4. Добавьте текст условных обозначений для плитки.
    
   ```
   All healthy devices (Heartbeat sent in last 10 minutes)
   ```

5. Введите запрос для плитки.
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" TimeGenerated >NOW-10MINUTES|measure count() by SRSDisplayName_CF 
   ```

6. Введите запрос для списка.
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by SRSDisplayName_CF |Where LastHB>NOW-10MINUTES
   ```

7. Определите имя заголовков столбцов.
    
   ```
   Display Name
   ```

8. Определите значение заголовков столбцов.
    
   ```
   Last HB
   ```

9. Введите запрос навигации.
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat"|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="create-the-tile-that-shows-devices-with-connectivity-issues"></a>Создание плитки, отображающей устройства с проблемами подключения

1. Определите ситуацию использования.  
    
    На этой плитке отображаются все устройства, не отправившие сообщение периодического сигнала в течение последних 10 минут. Возможно, у этих устройств возникли проблемы с сетевым подключением, подключением к Exchange или подключением к Skype для бизнеса.
    
2. Укажите заголовок группы.  
    
   ```
   SRS v2
   ```

3. Не устанавливайте флажок для новой группы. Вы уже сделали это при создании плитки 1, поэтому выполнять это действие повторно не нужно.
    
4. Добавьте текст условных обозначений для плитки.
    
   ```
   Devices no longer sending Heartbeat messages
   ```

5. Введите запрос для плитки.
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

6. Введите запрос для списка.
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

7. Определите имя заголовков столбцов.
    
   ```
   Device Name
   ```

8. Определите значение заголовков столбцов.  
    
   ```
   Last HB
   ```

9. Введите запрос навигации.
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-a-hardware-error"></a>Выведите список устройств с ошибкой оборудования. 

1. Определите ситуацию использования.  
    
   В этом плитки отображаются все устройства, которые отправлены сообщение, указывающее один или несколько компонентов неполадки с оборудованием в течение последних 10 минут. 
    
2. Укажите заголовок группы.  
    
   ```
   SRS v2
   ```

3. Не устанавливайте флажок для новой группы. Вы уже сделали это при создании плитки 1, поэтому выполнять это действие повторно не нужно.
    
4. Условные обозначения для плитки:  
    
   ```
   Devices with a Hardware Error
   ```

5. Запрос для плитки
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure count() by SRSDisplayName_CF
   ```

6. Запрос для списка:
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by SRSDisplayName_CF
   ```

7. Имя заголовков столбцов:  
    
   ```
   Display Name
   ```

8. Значение заголовков столбцов:  
    
   ```
   Last Error
   ```

9. Запрос навигации:  
    
   ```
   {selected item}  EventLevelName:Error EventID:3001|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-an-app-error"></a>Выведите список устройств с ошибкой приложения. 

1. Определите ситуацию использования. 
    
   На этой плитке отображаются все устройства SRS, сообщившие об одной или нескольких ошибках компонента приложения в течение последних 10 минут
    
2. Укажите заголовок группы.  
    
   ```
   SRS v2
   ```

3. Не устанавливайте флажок для новой группы. Вы уже сделали это при создании плитки 1, поэтому выполнять это действие повторно не нужно.
    
4. Условные обозначения для плитки:  
   ``` 
    Device with App Errors (in prior 10 minutes)
   ``` 
5. Запрос для плитки:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure count() by Computer
   ```

6. Запрос для списка:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by Computer
   ```

7. Имя заголовков столбцов:  
    
   ```
   Device Name
   ```

8. Значение заголовков столбцов:  
    
   ```
   Last Error
   ```

9. Запрос навигации:
    
   ```
   {selected item} EventLevelName:Error|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-requiring-a-restart"></a>Вывод списка устройств, требующих перезапуска

1. Определите ситуацию использования.  
    
   На этой плитке отображаются все устройства SRS, которые были перезапущены в течение последних 24 часов, и количество перезапусков
    
2. Укажите заголовок группы.  
    
  ```
  SRS v2
  ```

3. Не устанавливайте флажок для новой группы. Вы уже сделали это при создании плитки 1, поэтому выполнять это действие повторно не нужно.
    
4. Условные обозначения для плитки:  
    
   ```
   Devices with App restarted (past 24 hours)
   ```

5. Запрос для плитки:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count() by Computer
   ```

6. Запрос для списка:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count(EventID) by SRSDisplayName_CF
   ```

7. Имя заголовков столбцов:  
    
   ```
   Display Name
   ```

8. Значение заголовков столбцов:  
    
   ```
   Number of restarts
   ```

9. Запрос навигации:  
    
   ```
   {selected item} EventID:4000 TimeGenerated >NOW-24HOURS|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

На этом создание представления завершено. Все доступные на данный момент оповещения отображаются на одной или нескольких этих плитках.
## <a name="see-also"></a>Были ли эти инструкции полезны? Если да, укажите это в конце статьи. Если нет, сообщите нам о недочетах, и мы постараемся найти решение.
<a name="Views"> </a>

#### 

[Планирование управления системами комнаты Скайп версии 2 с OMS](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[Управление устройствами систем комнаты Скайп версии 2 с OMS](../../manage/skype-room-systems-v2/oms.md)

