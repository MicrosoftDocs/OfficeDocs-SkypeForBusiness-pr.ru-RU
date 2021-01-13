---
title: Skype для бизнеса Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Средство "Нагрузка и производительность Skype для бизнеса Server 2015" используется при планировании емкости и настройке производительности в непроизводивых или тестовых средах.
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814929"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype для бизнеса Server 2015 Stress and Performance Tool
 
Средство "Нагрузка и производительность Skype для бизнеса Server 2015" используется при планировании емкости и настройке производительности в непроизводивых или тестовых средах.
  
Skype для бизнеса Server 2015 Stress and Performance Tool включает средства, которые упростят планирование емкости для Skype для бизнеса Server 2015. Skype для бизнеса Server 2015 Stress and Performance Tool поможет вам:
  
- Упрощение планирования оборудования для Skype для бизнеса Server
    
- Повышение знаний и лучшие методики настройки производительности
    
- Измерение производительности развертывания Skype для бизнеса Server
    
Обычно это средство используется после использования средства планирования Skype для бизнеса [Server 2015](../../management-tools/planning-tool/planning-tool.md) для разработки топологии и уточнения топологии с помощью калькулятора планирования мощности Skype для бизнеса [Server 2015.](../../management-tools/capacity-planning-calculator.md) 

> [!NOTE]
> Это средство не будет обновлено для Skype для бизнеса Server 2019.
  
## <a name="tests"></a>Тесты

Средство Stress and Performance может имитировать эти типы пользовательской нагрузки:
  
|||
|:-----|:-----|
|Обмен мгновенными сообщениями и присутствие  <br/> |Аудиоконференции  <br/> |
|Общий доступ к приложениям  <br/> |VoIP, в том числе имитация телефонной сети общего перейти на тсХН  <br/> |
|Клиентская веб-трансляция  <br/> |Автоконференции  <br/> |
|Группы ответа  <br/> |Расширение списка рассылки  <br/> |
|Запрос на скачивание адресной книги и адресную книгу  <br/> |Вызовы Enhanced 911 (E911) и профиль местоположения (dial plan)  <br/> |
|MultiView  <br/> |Совместная работа с данными  <br/> |
|Мобильность  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Приложения и файлы, включенные в средство Stress and Performance Skype для бизнеса Server 2015

Эти приложения являются частью средства Skype для бизнеса Server Stress and Performance Tool:
  
|**Средство**|**Описание**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |Это средство используется для создания пользователей и контактов.  <br/> |
|UserProfileGenerator.exe  <br/> |Используется для настройки характеристик пользовательской нагрузки, которая вы имитируете.  <br/> |
|LyncPerfTool.exe  <br/> |Средство для имитации пользовательской нагрузки.  <br/> |
|Default.tmx  <br/> |Требуется для использования средства ведения журнала Skype для бизнеса Server 2015.  <br/> |
|Примеры сценариев предоставления  <br/> |Используется для настройки топологии для запуска нагрузок в зависимости от конкретных сценариев. Скорее всего, вам потребуется изменить их, чтобы они были релевантны для конкретной среды.  <br/> |
   
## <a name="topics-in-this-section"></a>Разделы в этом разделе

Если вам нужно узнать больше, просмотрите следующие статьи:
  
- [Prerequisites and setup for the Skype for Busines Stress and Performance Tool](prerequisites-and-setup.md)
    
- [Сценарии производительности для средства Stress and Performance Skype для бизнеса Server 2015](scenarios.md)
    
  - [Подготовка топологии для запуска нагрузки в сценариях stress и Performance](provisioning-the-topology-to-run-load.md)
    
  - [Настройка политик для средства "Нагрузка и производительность Skype для бизнеса Server 2015"](configuring-policies.md)
    
- [Использование средства "Нагрузка и производительность Skype для бизнеса Server 2015"](using-the-tool.md)
    
- [FAQ for the Skype for Business Server 2015 Stress and Performance Tool](faq.md)
    

