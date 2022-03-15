---
title: Планирование Комнаты Microsoft Teams мониторинга с помощью Azure Monitor
ms.author: czawideh
author: cazawideh
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: В этой статье рассматриваются вопросы планирования использования Azure Monitor для отслеживания Комнаты Microsoft Teams в Skype для бизнеса или Teams реализации.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 510f249ea4aef78b898294db0a2c3fbeef8fc283
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504126"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>Планирование Комнаты Microsoft Teams мониторинга с помощью Azure Monitor
 
 В этой статье рассматриваются вопросы планирования использования Azure Monitor для администрирования Комнаты Microsoft Teams устройств в Microsoft Teams или Skype для бизнеса реализации.

> [!NOTE]
> Вы также можете [настроить мониторинг состояния Комнаты Teams](../alerts/device-health-status.md) с помощью Teams администрирования.

[Azure Monitor](/azure/azure-monitor/overview) — это набор служб мониторинга, разработанных в облаке с самого начала. Компоненты монитора Azure размещаются в Azure, а не развертываются и управляются локально. Конфигурация минимальна, и вы можете работать в течение нескольких минут. С помощью некоторых настроек можно контролировать Комнаты Microsoft Teams за счет уведомлений о состоянии системы или о неисправностях отдельных систем комнат, а также управлять тысячами Комнаты Microsoft Teams.
  
В этой статье данная статья содержит информацию о требованиях, проектировании и архитектуре и методиках внедрения, необходимых для внедрения мониторинга на основе монитора Azure Комнаты Microsoft Teams. Кроме того, здесь вы можете найти ссылки на подробные статьи о внедрении azure Monitor для Комнаты Microsoft Teams и важные справочные сведения для постоянного мониторинга Комнаты Microsoft Teams помещений.
  
## <a name="functional-overview"></a>Функциональный обзор

![схема управления Комнаты Microsoft Teams с помощью Azure Monitor.](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Приложение Комнаты Microsoft Teams записывает события в журнал Windows событий. После установки агент мониторинга Майкрософт передает сведения в службу Azure Monitor.
  
После правильной настройки средства аналитики журналов анализирует загрузку JSON, внедренную в описания событий, чтобы описать, как Комнаты Microsoft Teams работает и какие ошибки обнаружены.
  
Администратор, использующий Azure Monitor, может получать уведомления о том Комнаты Microsoft Teams которые находятся в автономном режиме или столкнулись с ошибками приложения, подключения или оборудования, а также о том, требуется ли перезапустить систему. Состояние системы постоянно обновляется, поэтому эти уведомления близко к обновлениям в режиме реального времени.
  
## <a name="azure-monitor-requirements"></a>Требования к Azure Monitor

Для использования функций аналитики журналов у вас должна быть действительная подписка на Azure Monitor. См [. создание](/azure/azure-monitor/learn/quick-create-workspace) подписки для организации в рабочей области "Аналитика журналов".
  
Вам следует ознакомиться с использованием конструктора представления "Аналитика журналов". Эти [сведения см. в области Представления в средстве](/azure/azure-monitor/platform/view-designer) аналитики журналов.
  
### <a name="related-tasks"></a>Связанные задачи

1. Подписався на azure Monitor Log Analytics, создайте настраиваемые поля (как описано в поле [Карта),](azure-monitor-deploy.md#Custom_fields) необходимые для анализа сведений, которые будут Комнаты Microsoft Teams. Это включает в себя понимание схемы JSON, описанной в [описании записей журнала](azure-monitor-manage.md#understand-the-log-entries).
    
2. Разработайте Комнаты Microsoft Teams управления журналами в средстве аналитики журналов. Вы можете [создать панель Комнаты Microsoft Teams вручную](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>Индивидуальные Комнаты Microsoft Teams требованиям

Комнаты Microsoft Teams — это приложение, запущенное на компьютере в режиме киоска. Как и любое Windows, приложение Комнаты Microsoft Teams записывает такие события, как ошибки запуска и оборудования, в журнал Windows событий. Добавление агента Microsoft Monitor Комнаты Microsoft Teams позволяет собирать эти события. (Подробные Подключение Windows см. в Подключение Windows службе [Log Analytics в Azure](/azure/azure-monitor/platform/agent-windows).)
  
## <a name="ongoing-management"></a>Текущее управление

При использовании azure Monitor для отслеживания Комнаты Microsoft Teams необходимо понимать сведения, содержащиеся в журналах событий, используемых Azure Monitor. [Подробные сведения об этих сообщениях](azure-monitor-manage.md#understand-the-log-entries) о состоянии см. в статьях Сведения о записях журнала.
  
### <a name="related-tasks"></a>Связанные задачи

- Понимание оповещений, созданных Комнаты Microsoft Teams, и их устранения (см. раздел "Понимание записей [журнала")](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>См. также

[Развертывание Комнаты Microsoft Teams с помощью Azure Monitor](azure-monitor-deploy.md)
  
[Управление устройствами Комнаты Microsoft Teams с помощью Azure Monitor](azure-monitor-manage.md)
