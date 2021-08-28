---
title: Настройка политик для средства Skype для бизнеса Server 2015 года
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Конфигурация политики для Skype для бизнеса Server 2015 года.
ms.openlocfilehash: 9523dff4a2db09b229ef1500e6634674d85c1472
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611958"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Настройка политик для средства Skype для бизнеса Server 2015 года
 
Конфигурация политики для Skype для бизнеса Server 2015 года.
  
Существует несколько политик и других областей, которые можно настроить в Skype для бизнеса Server 2015 г., прежде чем запускать Средство стресса и производительности:
  
- [Archiving policy](configuring-policies.md#ArchivingPolicy) (Политика архивации),
    
- [Политика конференц-связи](configuring-policies.md#ConferencingPolicy),
    
- [Политика контактов](configuring-policies.md#ContactsPolicy)
    
- [Политика Федерации](configuring-policies.md#FederationPolicy)
    
- [Политика управления приемом вызовов](configuring-policies.md#CACPolicy)
    
- [Правила маршрутивки голосовой почты](configuring-policies.md#VoiceRoutingRules)
    
- [Приложение-помощник конференции](configuring-policies.md#ConfAttendantApp)
    
- [Служба "Парк вызовов сервера"](configuring-policies.md#ServerCallParkServ)
    
- [Вызовы экстренных служб](configuring-policies.md#EmergencyCalls)
    
- [Настройка приложения Группы реагирования](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Политика архивации
<a name="ArchivingPolicy"> </a>

Если в топологии Skype для бизнеса Server сервер архива, можно ArchivingPolicy.ps1 сценарий. Если вам нужна дополнительная помощь, ознакомьтесь с cmdlets архива и веб-конференций.
  
## <a name="conferencing-policy"></a>Политика конференц-связи
<a name="ConferencingPolicy"> </a>

Для conferencing у нас есть MeetingPolicy.ps1 скрипт. Если вам нужна дополнительная помощь, ознакомьтесь с веб-сайтом веб-конференций.
  
## <a name="contacts-policy"></a>Политика контактов
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1 сценарий будет образцом, который необходимо просмотреть. В случае необходимости дополнительных ссылок вам помогут комлеты im и Presence.
  
## <a name="federation-policy"></a>Политика Федерации
<a name="FederationPolicy"> </a>

Пример сценария федерации — FederationPolicy.ps1. Для проверки, если требуется дополнительная информация, будут использоваться edge Server, федерация и внешний доступ.
  
## <a name="call-admission-control-policy"></a>Политика управления приемом вызовов
<a name="CACPolicy"> </a>

Для этой политики BandwidthPolicy.ps1 ссылки. Кроме того, дополнительные сведения будут иметь и в комлетах управления приемом вызовов.
  
## <a name="voice-routing-rules"></a>Правила маршрутивки голосовой почты
<a name="VoiceRoutingRules"> </a>

Вам понадобится сценарий RoutingRules.ps1 для голосовой маршрутивки. При настройке этих правил обратите внимание на контекст телефона (то есть /Профиль расположения или /SimpleName) и коды внутренних и внешних площадей, чтобы можно было указать их при создании пользователей. Они также будут нужны во время конфигурации LyncPerfTool (в частности, для PSTN-UC и UC-PSTN).
  
Например, параметр SimpleName в вызове к комлету **New-CsDialPlan** в примере RoutingRules.ps1 должен использоваться для значения LocationProfile в следующем рисунке UserProfileGenerator.exe:
  
![Skype для бизнеса для загрузки, вкладка сценариев голосовой связи, расширенные параметры для бесед.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Подробные сведения см. в Корпоративная голосовая связь.
  
## <a name="conference-attendant-application"></a>Приложение-помощник конференции
<a name="ConfAttendantApp"> </a>

Сначала просмотрите ConferenceAutoAttendantConfiguration.ps1 сценарий. Вы хотите принять к сведению номер телефона ConferencingAutoAttendant (1121111111 по умолчанию), чтобы вы могли ввести его в средство конфигурации LyncPerfTool для создания конфигурации, как ниже:
  
![Вкладка Сценарии голосовой связи с уровнем нагрузки на конференцию и номером телефона.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Дополнительные сведения вы найдете в cmdlets Conferencing и Dial-in Conferencing.
  
## <a name="server-call-park-service"></a>Служба "Парк вызовов сервера"
<a name="ServerCallParkServ"> </a>

Это фактически отключено по умолчанию. Вы можете просмотреть CallParkConfiguration.ps1 пример сценария, если вам нужно проверить это. Кроме того, ознакомьтесь с кодлетами приложения Call Park по мере необходимости.
  
## <a name="emergency-calls"></a>Вызовы экстренных служб
<a name="EmergencyCalls"> </a>

Чтобы настроить стресс и тестирование производительности для экстренных вызовов, необходимо выполнить следующие действия:
  
1. Настройка голосового маршрута для экстренных вызовов. Вы можете использовать сценарий RoutingRules.ps1 и проверить в комментарии **"Route E911 to PSTN"** для примера создания этого голосового маршрута.
    
    > [!CAUTION]
    > В примере команды RoutingRules.ps1 имеется шаблон номеров, который включает число 119, а не 911. Чтобы предотвратить случайные вызовы локальных экстренных операторов во время тестирования нагрузки, следует избегать использования 911 (или фактического локального номера экстренных служб). Помните, что эта конфигурация предназначена только для имитации! 
  
2. Настройка адресов путем заполнения значений на вкладке **Config** службы информации о расположении в UserProvisioningTool, как показано на следующем рисунке:
    
     ![Средство предварительного обеспечения пользователей с указанием количества адресов, подсетей, коммутаторов и портов.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Когда вы ввели все в UserProvisioningTool, нажмите кнопку **Создание файлов config LIS.**
    
4. Теперь будут созданы CSV-файлы для портов, подсетей, коммутаторов и точек беспроводного доступа (WAP), а также XML-файл для средства Stress и Performance. Вы можете использовать CSV-файлы для входных данных при настройке службы сведений о местоположении (LIS) с помощью LisConfiguration.ps1 скрипта. Для этого необходимо переместить файл Locations0.xml в ту же папку, что и исполняемый инструмент стресс и производительность (LyncPerfTool.exe). Это позволит запускать сценарии профиля расположения (dial plan).
    
## <a name="configuring-response-group-application"></a>Настройка приложения Группы реагирования
<a name="ConfigResponseGroupApp"> </a>

Пример сценария ResponseGroupConfiguration.ps1. Кроме того, для просмотра дополнительных сведений о конфигурации необходимо просмотреть приложения группы реагирования. На следующей схеме покажут некоторые сведения о конфигурации:
  
![Средство config группы реагирования, показывающая существующие рабочий процессы для тестирования.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

