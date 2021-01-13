---
title: Настройка политик для средства skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Настройка политики для средства Stress and Performance Skype для бизнеса Server 2015.
ms.openlocfilehash: bb049d5740d74e5ebeacd8a21d00e2644da61a7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815039"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Настройка политик для средства skype for Business Server 2015 Stress and Performance Tool
 
Настройка политики для средства Stress and Performance Skype для бизнеса Server 2015.
  
Существует несколько политик и других областей, которые можно настроить в Skype для бизнеса Server 2015 перед запуском средства Stress and Performance.
  
- [Archiving policy](configuring-policies.md#ArchivingPolicy) (Политика архивации),
    
- [Политика конференц-связи](configuring-policies.md#ConferencingPolicy),
    
- [Политика контактов](configuring-policies.md#ContactsPolicy)
    
- [Политика федерации](configuring-policies.md#FederationPolicy)
    
- [Политика контроля допуска вызовов](configuring-policies.md#CACPolicy)
    
- [Правила маршрутки голосовой почты](configuring-policies.md#VoiceRoutingRules)
    
- [Приложение "Помощник по конференц-залу"](configuring-policies.md#ConfAttendantApp)
    
- [Служба парковки вызовов сервера](configuring-policies.md#ServerCallParkServ)
    
- [Экстренные вызовы](configuring-policies.md#EmergencyCalls)
    
- [Настройка приложения группы ответа](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Политика архивации
<a name="ArchivingPolicy"> </a>

If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script. Если вам нужна дополнительная помощь, ознакомьтесь с дополнительными службами архива и веб-конференций.
  
## <a name="conferencing-policy"></a>Политика конференц-связи
<a name="ConferencingPolicy"> </a>

Для conferencing у нас есть MeetingPolicy.ps1 сценарий. Если вам нужна дополнительная помощь, ознакомьтесь с помощью веб-служб.
  
## <a name="contacts-policy"></a>Политика контактов
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1 сценарий будет образцом, который необходимо просмотреть. Если вам нужны дополнительные ссылки, вам помогут эти дополнительные данные.
  
## <a name="federation-policy"></a>Политика федерации
<a name="FederationPolicy"> </a>

Пример сценария для федерации — FederationPolicy.ps1. Если вам нужны дополнительные сведения, это будет edge Server, федерация и внешний доступ.
  
## <a name="call-admission-control-policy"></a>Политика контроля допуска вызовов
<a name="CACPolicy"> </a>

Вы можете ссылаться на BandwidthPolicy.ps1 для этой политики. Кроме того, дополнительные сведения будут иметься в дополнительных сведениях о диспетчере контроля допуска вызовов.
  
## <a name="voice-routing-rules"></a>Правила маршрутки голосовой почты
<a name="VoiceRoutingRules"> </a>

Вам потребуется пример сценария RoutingRules.ps1 для маршрутной голосовой почты. При настройке этих правил заметьте контекст телефона (то есть /Location Profile или /SimpleName) и коды внутренней и внешней области, чтобы указать их при создании пользователей. Они также потребуется во время настройки LyncPerfTool (в частности, для PSTN-UC и UC-PSTN).
  
Например, параметр SimpleName в вызове для параметра **New-CsDialPlan** в примере RoutingRules.ps1 следует использовать для значения LocationProfile на следующем рисунке UserProfileGenerator.exe:
  
![Средство настройки нагрузки Skype для бизнеса, вкладка "Сценарии голосовой связи", дополнительные параметры для бесед.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Подробные сведения см. в Корпоративная голосовая связь управления.
  
## <a name="conference-attendant-application"></a>Приложение "Помощник по конференц-залу"
<a name="ConfAttendantApp"> </a>

Сначала просмотрите сценарий ConferenceAutoAttendantConfiguration.ps1. Обратите внимание на номер телефона conferencingAutoAttendant (1121111111 по умолчанию), чтобы ввести его в средство настройки LyncPerfTool для создания конфигурации, как по умолчанию:
  
![Вкладка "Сценарии голосовой связи" с уровнем нагрузки на conferencing и номером телефона.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Дополнительные сведения см. в дополнительных сведениях в cmdlets conferencing and Dial-in Conferencing.
  
## <a name="server-call-park-service"></a>Служба парковки вызовов сервера
<a name="ServerCallParkServ"> </a>

По умолчанию этот режим отключен. Вы можете просмотреть пример CallParkConfiguration.ps1, если вам нужно проверить этот сценарий. Кроме того, ознакомьтесь с необходимыми cmdlets приложения парковки вызовов.
  
## <a name="emergency-calls"></a>Экстренные вызовы
<a name="EmergencyCalls"> </a>

Чтобы настроить тестирование нагрузки и производительности для экстренных вызовов, необходимо выполнить следующие действия:
  
1. Настройка маршрута голосовой почты для экстренных вызовов. Вы можете использовать сценарий RoutingRules.ps1 и проверить в комментарии **"Route E911 to PSTN"** пример того, как настроить этот маршрут голосовой связи.
    
    > [!CAUTION]
    > Пример команды в RoutingRules.ps1 имеет шаблон числа, который включает число 119, а не 911. Не следует использовать номер 911 (или фактический локальный номер экстренного вызова), чтобы предотвратить случайные вызовы локальных операторов экстренных служб во время нагрузок. Помните, что эта конфигурация предназначена только для имитации! 
  
2. Настройте адреса, заполнив значения на вкладке **"Конфигурация** службы информации о расположении" в UserProvisioningTool, как показано на следующем рисунке:
    
     ![Средство пользовательской подготовка, показывающая количество адресов, подсетей, коммутаторов и портов.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. После того как вы ввели все данные в UserProvisioningTool, нажмите кнопку **"Создать файлы config lis".**
    
4. Теперь будут созданы CSV-файлы для портов, подсетей, коммутаторов и беспроводных точек доступа (WAP), а также XML-файл для средства Stress and Performance. CSV-файлы можно использовать для ввода при настройке службы сведений о местонахождении (LIS) с помощью LisConfiguration.ps1 сценария. Для этого необходимо переместить файл Locations0.xml в ту же папку, что и исполняемый файл средства stress and Performance Tool (LyncPerfTool.exe). Это позволит вам запускать сценарии профилей местоположений (телефонных планов).
    
## <a name="configuring-response-group-application"></a>Настройка приложения группы ответа
<a name="ConfigResponseGroupApp"> </a>

Пример скрипта ResponseGroupConfiguration.ps1. Кроме того, для получения дополнительных сведений о конфигурации необходимо просмотреть дополнительные сведения о приложениях группы ответа. На следующей схеме покажем некоторые сведения о конфигурации:
  
![Средство проверки группы ответа, показывающая существующие процессы для тестирования.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

