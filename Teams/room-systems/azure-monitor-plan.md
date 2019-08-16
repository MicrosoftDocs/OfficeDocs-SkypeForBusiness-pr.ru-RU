---
title: Планирование управления комнатами в Microsoft Teams с помощью монитора Azure
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection: M365-voice
description: В этой статье рассказывается о том, как использовать монитор Azure для управления устройствами в Microsoft Teams, а также в реализации Skype для бизнеса или рабочих групп.
ms.openlocfilehash: bdd028417ff8234a10173de7b5512faff8455629
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "36428093"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Планирование управления комнатами в Microsoft Teams с помощью монитора Azure
 
 В этой статье рассказывается о том, как использовать монитор Azure для управления устройствами в Microsoft Teams, а также в реализации Microsoft Teams или Skype для бизнеса.
  
[Монитор Azure](https://docs.microsoft.com/azure/azure-monitor/overview) — это набор служб управления, разработанных в облаке с начала. Вместо того, чтобы развертывать локальные ресурсы и управлять ими, компоненты монитора Azure полностью размещаются в Azure. Настройка минимальна, и вы можете работать буквально в течение минут. С помощью некоторых параметров настройки можно управлять системами конференц-связи Microsoft Teams, обеспечивая уведомления о работоспособности системы или сбоях для отдельных систем помещения, а также может значительно увеличить масштаб для управления тысячами Microsoft Teams. Комнаты для конференц-связи.
  
В этой статье приводятся рекомендации о требованиях, проектировании, архитектуре и реализации, необходимые для реализации управления с помощью монитора Azure на основе Microsoft Teams, а также ссылки на подробные статьи с подробными сведениями о реализация монитора Azure для комнат Microsoft Teams и важные справочные сведения для текущего мониторинга комнат комнат Microsoft Teams. 
  
## <a name="functional-overview"></a>Функциональный обзор

![Схема управления комнатами Microsoft Teams с помощью монитора Azure](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Приложение Microsoft Teams комнаты на консольном устройстве выполняет запись событий в журнал событий Windows. После установки агент Microsoft Monitoring передает данные в службу мониторинга Azure. 
  
После правильной настройки Analytics log анализирует полезные данные JSON, внедренные в описания событий, для описания того, как работает каждая система комнат Microsoft Teams и какие ошибки обнаружены. 
  
Администратор, использующий монитор Azure, может получать уведомления о системах Microsoft Teams, которые находятся в автономном режиме или испытывают сбои в работе приложений, подключений и оборудования, а также знать, требуется ли перезагрузка системы. Каждый статус системы обновляется часто, поэтому эти уведомления близки к обновлениям в реальном времени.
  
## <a name="azure-monitor-requirements"></a>Требования к монитору Azure

Для использования функции Analytics log на мониторе Azure требуется действительная подписка на Azure. Чтобы создать подписку для своей организации, ознакомьтесь [со статьей начало работы с аналитической рабочей областью](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) .
  
Вы должны ознакомиться с нужными сведениями о том, как пользоваться конструктором аналитических представлений журналов. Ознакомьтесь [с представлениями в службе аналитики журнала](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) для этих сведений.
  
### <a name="related-tasks"></a>Связанные задачи

1. После того как вы подписались на службу Azure Monitoring log, создайте пользовательские поля (как описано в разделе [соответствие настраиваемых полей](azure-monitor-deploy.md#Custom_fields)), необходимые для анализа данных, которые будут отправляться из консолей Microsoft Teams. Сюда входит понимание схемы JSON, описанной в разделе [Общие сведения](azure-monitor-manage.md#understand-the-log-entries)о журнальных записях.
    
2. Разработайте представление для управления комнатами Microsoft Teams в службе анализа журналов. Вы можете либо [создать панель мониторинга Microsoft Teams, используя метод импорта,](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) либо [создать панель мониторинга Microsoft Teams на панели управления комнат вручную](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Требования к отдельным консольным комнатам Microsoft Teams

Каждая консоль из комнат Microsoft Teams — это приложение, работающее на устройстве Surface Pro в режиме киоска (обычно оно настроено как единственное приложение, которое может работать на устройстве). Как и в случае с любым приложением Windows, приложение Microsoft Teams комнаты записывает события, такие как запуск и сбои оборудования, в журнал событий Windows. Добавление агента монитора Microsoft Monitor на устройстве с Microsoft Teams позволяет собирать эти события. (Дополнительные сведения [можно найти в разделе Подключение компьютеров с Windows к службе Analytics log в Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) .)
  
## <a name="ongoing-management"></a>Текущее управление

При использовании монитора Azure для управления устройствами в Microsoft Teams для работы с ними необходимо знать, какие данные содержатся в журналах событий, используемых монитором Azure. Сведения об этих сообщениях о работоспособности можно найти [в разделе Знакомство с записями журнала](azure-monitor-manage.md#understand-the-log-entries) .
  
### <a name="related-tasks"></a>Связанные задачи

- Обучите оповещения, созданные в помещениях Microsoft Teams, и способы их устранения (ознакомьтесь с разделом ["Знакомство с записями журнала](azure-monitor-manage.md#understand-the-log-entries)").
    
## <a name="see-also"></a>См. также

[Развертывание управления комнатами Microsoft Teams с помощью монитора Azure](azure-monitor-deploy.md)
  
[Управление устройствами в Microsoft Teams с помощью монитора Azure](azure-monitor-manage.md)