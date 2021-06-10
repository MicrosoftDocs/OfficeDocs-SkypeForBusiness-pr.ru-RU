---
title: Планирование управления Комнаты Microsoft Teams с помощью Azure Monitor
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
description: В этой статье рассматриваются вопросы планирования использования Azure Monitor для администрирования Комнаты Microsoft Teams устройств в Skype для бизнеса или Teams реализации.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 56b22dddfc475efc83fb5bb3ef5734743b1eb0c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117587"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Планирование управления Комнаты Microsoft Teams с помощью Azure Monitor
 
 В этой статье рассматриваются вопросы планирования использования Azure Monitor для администрирования Комнаты Microsoft Teams устройств в Microsoft Teams или Skype для бизнеса реализации.
  
[Azure Monitor](/azure/azure-monitor/overview) — это набор служб управления, разработанных в облаке с самого начала. Компоненты монитора Azure размещаются в Azure, а не развертываются и управляются локально. Конфигурация минимальна, и вы можете работать в буквальном смысле за считанные минуты. Некоторые настройки помогают управлять системами Комнаты Microsoft Teams конференц-связи, предоставляя в режиме реального времени уведомления о состоянии системы или о неисправностях для отдельных систем комнат, а также могут привести к управлению тысячами Комнаты Microsoft Teams конференц-залов.
  
В этой статье описаны требования, проектирование и архитектура и методики внедрения, необходимые для внедрения системы azure Monitor для управления устройствами конференц-связи Комнаты Microsoft Teams, а также ссылки на подробные статьи о внедрении монитора Azure для Комнаты Microsoft Teams и важные справочные сведения о постоянном мониторинге Комнаты Microsoft Teams помещений. 
  
## <a name="functional-overview"></a>Функциональный обзор

![Схема управления Комнаты Microsoft Teams с помощью Azure Monitor](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Приложение Комнаты Microsoft Teams на устройстве консоли записывает события в журнал Windows событий. После установки агент мониторинга Майкрософт передает сведения в службу Azure Monitor. 
  
После правильной настройки средства аналитики журналов анализирует загрузку JSON, внедренную в описания событий, чтобы описать, как работает система Комнаты Microsoft Teams и какие ошибки обнаружены. 
  
Администратор, использующий Azure Monitor, может получать уведомления о том, что Комнаты Microsoft Teams системы находятся в автономном режиме или столкнулись с ошибками приложения, подключения или оборудования, а также могут быть уведомлены о том, требуется ли перезапустить систему. Состояние системы постоянно обновляется, поэтому эти уведомления близко к обновлениям в режиме реального времени.
  
## <a name="azure-monitor-requirements"></a>Требования к Azure Monitor

Для использования функции аналитики журналов у вас должна быть действительная подписка на Azure Monitor. См. создание подписки для организации в рабочей области ["Аналитика](/azure/azure-monitor/learn/quick-create-workspace) журналов".
  
При необходимости ознакомьтесь с использованием конструктора средств аналитики журналов. Эти [сведения см. в](/azure/azure-monitor/platform/view-designer) области Представления в средстве аналитики журналов.
  
### <a name="related-tasks"></a>Связанные задачи

1. Подписався на azure Monitor Log Analytics, создайте настраиваемые поля (как описано в поле [Карта),](azure-monitor-deploy.md#Custom_fields)необходимые для анализа сведений, которые будут Комнаты Microsoft Teams консолях. Это включает понимание схемы JSON, задокументированной в [окне "Понимание записей журнала".](azure-monitor-manage.md#understand-the-log-entries)
    
2. Разработайте Комнаты Microsoft Teams управления журналами в средстве аналитики журналов. Вы можете создать [панель Комнаты Microsoft Teams](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) с помощью метода импорта или создать Комнаты Microsoft Teams панели [мониторинга вручную.](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Требования Комнаты Microsoft Teams консоли

Каждая консоль Комнаты Microsoft Teams — это приложение, запущенное на устройстве Surface Pro в режиме киоска (обычно оно настроено как единственное приложение, которое может запускаться на устройстве). Как и любое Windows, приложение Комнаты Microsoft Teams записывает такие события, как ошибки запуска и оборудования, в журнал Windows событий. Добавление агента Microsoft Monitor на устройство Комнаты Microsoft Teams позволяет собирать эти события. (Подробные [Подключение Windows в службу аналитики журналов в Azure.](/azure/azure-monitor/platform/agent-windows)
  
## <a name="ongoing-management"></a>Текущее управление

При использовании Azure Monitor для управления устройствами Комнаты Microsoft Teams необходимо понимать сведения, содержащиеся в журналах событий, используемых Azure Monitor. Подробные [сведения об этих сообщениях](azure-monitor-manage.md#understand-the-log-entries) о состоянии см. в статьях Сведения о записях журнала.
  
### <a name="related-tasks"></a>Связанные задачи

- Понимание оповещений, созданных Комнаты Microsoft Teams, и их устранения (см. раздел "Понимание записей [журнала")](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>См. также

[Развертывание Комнаты Microsoft Teams с помощью Azure Monitor](azure-monitor-deploy.md)
  
[Управление устройствами Комнаты Microsoft Teams с помощью Azure Monitor](azure-monitor-manage.md)