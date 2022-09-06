---
title: Планирование Комнаты Microsoft Teams мониторинга с помощью Azure Monitor
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Rooms
description: В этой статье рассматриваются вопросы планирования использования Azure Monitor для отслеживания Комнаты Microsoft Teams в реализации Skype для бизнеса Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5640fd63ac413403105be7d5f23e413b2f19ebdf
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606398"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>Планирование Комнаты Microsoft Teams мониторинга с помощью Azure Monitor
 
 В этой статье рассматриваются рекомендации по планированию использования Azure Monitor для администрирования Комнаты Microsoft Teams устройств в Microsoft Teams или Skype для бизнеса реализации.

> [!NOTE]
> Вы также можете [настроить мониторинг работоспособности Комнаты Teams с помощью](../alerts/device-health-status.md) Центра администрирования Teams.

[!INCLUDE [teams-pro-license-requirement](../includes/teams-pro-license-requirement.md)]

[Azure Monitor](/azure/azure-monitor/overview) — это набор служб мониторинга, которые были разработаны в облаке с начала. Вместо развертывания локальных ресурсов и управления ими компоненты Azure Monitor полностью размещаются в Azure. Конфигурация минимальна, и вы можете быть запущены в течение нескольких минут. С помощью некоторых настроек это может помочь в мониторинге Комнаты Microsoft Teams путем предоставления уведомлений о работоспособности системы или сбоях для отдельных систем помещений, а также может масштабироваться до управления тысячами Комнаты Microsoft Teams.
  
В этой статье рассматриваются требования, проектирование и архитектура, а также рекомендации по реализации, необходимые для реализации мониторинга на основе Azure Monitor Комнаты Microsoft Teams. Здесь также приведены ссылки на подробные статьи о реализации Azure Monitor для Комнаты Microsoft Teams и важные справочные сведения для текущего мониторинга Комнаты Microsoft Teams помещений.
  
## <a name="functional-overview"></a>Функциональный обзор

![схема управления Комнаты Microsoft Teams с помощью Azure Monitor.](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Приложение Комнаты Microsoft Teams записывает события в журнал событий Windows. После установки microsoft Monitoring Agent передает сведения в службу Azure Monitor.
  
После правильной настройки Log Analytics анализирует полезные данные JSON, внедренные в описания событий, чтобы описать, Комнаты Microsoft Teams работает и какие ошибки обнаруживаются.
  
Администратор, использующий Azure Monitor, может получать уведомления о том Комнаты Microsoft Teams которые находятся в автономном режиме или столкнулись с ошибками приложения, подключения или оборудования, а также знать, требуется ли перезапустить систему. Каждое состояние системы обновляется часто, поэтому эти уведомления близки к обновлениям в режиме реального времени.
  
## <a name="azure-monitor-requirements"></a>Требования к Azure Monitor

Для использования функций Log Analytics у вас должна быть действительная подписка Azure для Azure Monitor. Сведения [о создании](/azure/azure-monitor/learn/quick-create-workspace) подписки для организации см. в статье "Начало работы с рабочей областью Log Analytics".
  
Вам следует ознакомиться с использованием конструктора представлений Log Analytics. [Дополнительные сведения см](/azure/azure-monitor/platform/view-designer). в разделе "Представления" в Log Analytics.
  
### <a name="related-tasks"></a>Связанные задачи

1. После подписки на Azure Monitor Log Analytics создайте настраиваемые поля (как описано в [](azure-monitor-deploy.md#Custom_fields)разделе "Сопоставление настраиваемых полей"), необходимые для анализа сведений, которые будут отправляться из Комнаты Microsoft Teams. Это включает в себя понимание схемы JSON, задокументированной в [разделе "Общие сведения о записях журнала"](azure-monitor-manage.md#understand-the-log-entries).
    
2. Разработайте Комнаты Microsoft Teams управления в Log Analytics. Создать панель [мониторинга Комнаты Microsoft Teams вручную](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>Индивидуальные Комнаты Microsoft Teams требования

Комнаты Microsoft Teams — это приложение, работающее на вычислительном устройстве в режиме киоска. Как и любое приложение Windows, Комнаты Microsoft Teams записывает такие события, как сбои при запуске и оборудовании, в журнал событий Windows. Добавление агента Microsoft Monitor в Комнаты Microsoft Teams позволяет собирать эти события. (Дополнительные сведения см. в разделе "Подключение компьютеров Windows к службе [Log Analytics в Azure](/azure/azure-monitor/platform/agent-windows) ".)
  
## <a name="ongoing-management"></a>Текущее управление

При использовании Azure Monitor для мониторинга Комнаты Microsoft Teams необходимо понимать сведения, содержащиеся в журналах событий, используемых Azure Monitor. [Дополнительные сведения об этих сообщениях](azure-monitor-manage.md#understand-the-log-entries) о работоспособности см. в разделе "Общие сведения о записях журнала".
  
### <a name="related-tasks"></a>Связанные задачи

- Общие сведения об оповещениях, созданных Комнаты Microsoft Teams и способах их устранения (см. раздел "Общие сведения о [записях журнала](azure-monitor-manage.md#understand-the-log-entries)")
    
## <a name="see-also"></a>См. также

[Развертывание Комнаты Microsoft Teams с помощью Azure Monitor](azure-monitor-deploy.md)
  
[Управление Комнаты Microsoft Teams устройствами с помощью Azure Monitor](azure-monitor-manage.md)
