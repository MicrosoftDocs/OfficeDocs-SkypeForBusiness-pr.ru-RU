---
title: Планирование управления комнатами Microsoft Teams с помощью Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: В этой статье рассматриваются вопросы планирования использования azure Monitor для администрирования устройств комнат Microsoft Teams в реализации Skype для бизнеса или Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 56b22dddfc475efc83fb5bb3ef5734743b1eb0c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117587"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Планирование управления комнатами Microsoft Teams с помощью Azure Monitor
 
 В этой статье рассматриваются вопросы планирования использования azure Monitor для администрирования устройств комнат Microsoft Teams в реализации Microsoft Teams или Skype для бизнеса.
  
[Azure Monitor](/azure/azure-monitor/overview) — это набор служб управления, разработанных в облаке с самого начала. Компоненты Azure Monitor размещены в Azure, а не развертываются и управляются ресурсами локальной системы. Конфигурация минимальна, и вы можете работать в буквальном смысле за считанные минуты. Некоторые настройки помогают управлять системами конференц-связи по комнатам Microsoft Teams, предоставляя в режиме реального времени уведомления о состоянии системы или неисправностях отдельных систем комнат, а также могут перенаправляться в управление тысячами конференц-залов Комнат Microsoft Teams.
  
В этой статье описаны требования, проектирование, архитектура и методики внедрения, необходимые для внедрения управления конференц-связью комнат Microsoft Teams на основе Azure, а также ссылки на подробные статьи о внедрении комнат Azure Teams и важные справочные сведения для постоянного контроля комнат Microsoft Teams. 
  
## <a name="functional-overview"></a>Функциональный обзор

![Схема управления помещениями Microsoft Teams с помощью Azure Monitor](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Приложение "Комнаты Microsoft Teams" на устройстве консоли записывает события в журнал событий Windows. После установки агент мониторинга Майкрософт передает сведения в службу Azure Monitor. 
  
После правильной настройки log Analytics анализирует нагрузку JSON, внедренную в описания событий, чтобы описать, как работает каждая система комнат Microsoft Teams и какие ошибки выявляются. 
  
Администратор, использующий Azure Monitor, может получать уведомления о том, что системы комнат Microsoft Teams работают в автономном режиме, имеют проблемы с приложением, подключением или оборудованием, а также могут быть уведомлены о том, требуется ли перезапустить систему. Состояние системы постоянно обновляется, поэтому эти уведомления близко к обновлениям в режиме реального времени.
  
## <a name="azure-monitor-requirements"></a>Требования Azure Monitor

Для использования функции аналитики журналов вам необходимо иметь действиическую подписку Azure для Azure Monitor. Дополнительные [действия по созданию подписки](/azure/azure-monitor/learn/quick-create-workspace) для организации см. в рабочей области "Аналитика журналов".
  
При необходимости вы должны ознакомиться с использованием конструктора средств аналитики журналов. Эти [сведения см. в области "Представления"](/azure/azure-monitor/platform/view-designer) в средстве аналитики журналов.
  
### <a name="related-tasks"></a>Связанные задачи

1. После подписки на службу аналитики журналов Azure [](azure-monitor-deploy.md#Custom_fields)Monitor создавайте настраиваемые поля (как описано в полях "Карта"), необходимые для анализа сведений, которые отправляются с консолей комнат Microsoft Teams. Это включает понимание схемы JSON, описанной [в описании записей журнала.](azure-monitor-manage.md#understand-the-log-entries)
    
2. Разработка представления управления комнатами Microsoft Teams в средстве аналитики журналов. Вы можете создать [панель мониторинга комнат Microsoft Teams](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) с помощью метода импорта или создать панель мониторинга комнат Microsoft Teams [вручную.](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Требования к консоли для отдельных комнат Microsoft Teams

Каждая консоль комнат Microsoft Teams — это приложение, которое работает на устройстве Surface Pro в киоске (обычно оно настроено как единственное приложение, которое может работать на устройстве). Как и любое приложение Для Windows, приложение Microsoft Teams Rooms записывает такие события, как неисправности запуска и оборудования, в журнал событий Windows. Добавление агента Microsoft Monitor на устройство комнат Microsoft Teams позволяет собирать эти события. (Подробные [сведения см. в подключении](/azure/azure-monitor/platform/agent-windows) компьютеров Windows к службе Log Analytics в Azure.)
  
## <a name="ongoing-management"></a>Текущее управление

При использовании azure Monitor для управления устройствами комнат Microsoft Teams необходимо понимать, что содержится в журналах событий, используемых Azure Monitor. Подробные [сведения об этих сообщениях о](azure-monitor-manage.md#understand-the-log-entries) состоянии см. в записях журнала.
  
### <a name="related-tasks"></a>Связанные задачи

- Понимание оповещений, созданных комнатами Microsoft Teams, и их устранения (см. раздел "Понимание записей [журнала")](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>См. также

[Развертывание управления помещениями Microsoft Teams с помощью Azure Monitor](azure-monitor-deploy.md)
  
[Управление устройствами комнат Microsoft Teams с помощью Azure Monitor](azure-monitor-manage.md)