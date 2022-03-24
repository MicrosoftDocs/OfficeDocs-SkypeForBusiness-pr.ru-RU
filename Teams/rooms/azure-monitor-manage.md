---
title: Мониторинг Комнаты Microsoft Teams устройств с помощью Azure Monitor
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: В этой статье рассмотрено, как Комнаты Microsoft Teams устройства с помощью Azure Monitor.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a19a6be8f48bedca228457f7e5c2c85be1ef8374
ms.sourcegitcommit: b878c57b8e822913b7aac8c105f476bc4ebfcd7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2022
ms.locfileid: "63761903"
---
# <a name="monitor-microsoft-teams-rooms-devices-with-azure-monitor"></a>Мониторинг Комнаты Microsoft Teams устройств с помощью Azure Monitor

В этой статье рассмотрено, как Комнаты Microsoft Teams с помощью azure Monitor.

Вы можете настроить Azure Monitor для предоставления базовой телеметрии, которая помогает отслеживать Microsoft Teams устройствах комнаты собраний. [Дополнительные сведения см. в Комнаты Microsoft Teams управления](azure-monitor-plan.md) проектами с помощью Azure Monitor и Развертывание Комнаты Microsoft Teams [с помощью Azure Monitor](azure-monitor-deploy.md). По мере зрелости решения для мониторинга вы можете использовать дополнительные возможности мониторинга и данные для создания более подробного представления производительности устройства.

## <a name="understand-the-log-entries"></a>Общие сведения о записях журнала

Следующие описания событий вставляются в поле описание журнала событий каждые пять минут, когда Комнаты Microsoft Teams записи соответствующих сведений в журнале Windows событий. Служба Microsoft Monitoring Agent эти записи в средстве аналитики журналов в Azure Monitor, которая их анализирует на панели мониторинга, созданной в Комнаты Microsoft Teams мониторинга с помощью [Azure Monitor](azure-monitor-deploy.md). С помощью панели мониторинга вы можете при необходимости посмотреть на отдельные записи журнала, чтобы определить курсы действий.

ИД событий 2000 и 3000 указывают, что Комнаты Teams работает как ожидалось. ИД событий 2001 и 3001 указывают на то, что проблема обнаружена. Если событие ID 4000 видно чаще, чем вы ожидаете, могут потребоваться действия по сравнению с базовым планом или другими развернутными устройствами в организации.

Имея общее представление об этих оповещениях о событиях, вы сможете быстрее выявлять источник проблем и определять начальные данные для дальнейшего устранения неполадок.

| EventIDlevel&nbsp;&nbsp;|Eventbehavior&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|EventDescription&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Информация | Периодическое событие, свидетельствующее о нормальном функционировании системы. Каждые 5 минут Комнаты Microsoft Teams проверяет, что он в Microsoft Teams или Skype для бизнеса подключен к сети и Exchange подключения. <br> Если все три фактора истинны, каждые 5 минут в журнал событий записывается ИД события 2000, пока устройство не будет отключено или не будет выполнены хотя бы одно из условий. | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> В этом примере были выполнены все условия пульса, Комнаты Microsoft Teams устройство помечено как работоспособное. При возникновении ошибок в журнал записывается идентификатор события 2001. |
| 2001  <br> Ошибка | Событие, свидетельствующее об ошибке приложения. Каждые 5 минут Комнаты Microsoft Teams проверяет, что он в Microsoft Teams или Skype для бизнеса с помощью сетевого и Exchange подключения. Если один или несколько факторов не истинны, он записывает EventID 2001 в журнал событий каждые 5 минут, пока устройство не будет отключено или все условия будут выполнены еще раз.  | `{"Description":"Network status : Healthy. Exchange status : Connected. Signin status: Unhealthy. Teams Signin status: Healthy.", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  В этом примере Комнаты Microsoft Teams, что сетевое подключение было полезным, и приложение было подключено к Exchange, но выделенный полужирным шрифтом означает, что приложение не подключено. Это может быть связано с проблемами конфигурации на устройстве или хосте.  <br> <br> Состояние сети указывается как "Неработоспособный" или "Неработоспособный". Если состояние неработоспособно, возможно, у вас проблема с сетью или устройство было отключилось (но в этом случае, вероятно, у вас также были Exchange и Microsoft Teams или Skype для бизнеса).  <br><br> Состояние Exchange как подключенное или одно из следующих: "Отключено", "Подключение", "АвтооткрытиеError" (наиболее распространенная ошибка), "ОбщийError" или "ServerVersionNotSupported". Если имеется состояние Подключается, подождите, пока не будет отправлено следующее сообщение о состоянии. Другие ошибки отправляются администратору, который имеет опыт Exchange проблем.  <br><br>  Состояние _при входе_/ _Teams_ (указывающее на то, что приложение вход в приложение) имеет состояние "Здоровое _" или "__Неработоспособное"_. Если система неработоспособна, обратитесь к техническому специалисту для устранения неполадок. |
| 3000  <br> Информация | Это событие проверяет, что проверка оборудования была установлена и была признана нормальной. Каждые 5 минут Комнаты Microsoft Teams проверяет, подключены и работают ли настроенные аппаратные компоненты, такие как экран комнаты, микрофон, динамик и камера. Если все компоненты полезны, в журнал событий записывается EventID 3000. Это событие пишется каждые 5 минут, если только нет проблем с подключенным устройством.  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> В этом примере все проверки оборудования пройдены успешно. При ошибках приложение будет записывать вместо этого ИД события 3001. |
| 3001  <br> Событие ошибки  | Событие, свидетельствующее об ошибке оборудования. В Комнаты Microsoft Teams есть процесс, который проверяет состояние подключенных аппаратных компонентов (перед комнатой, микрофоном, динамиком, камерой) каждые 5 минут. Если один или несколько компонентов неработоспособы, в журнале событий записывается EventID 3001. Это событие фиксируется каждые 5 минут, пока не будет устранена проблема с устройством.   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>   В параметрах, соответствующих периферийным компонентам оборудования, может отображаться значение "Healthy" (Работоспособно) или "Unhealthy" (Неработоспособно).  <br> В этом примере настроены два  монитора комнаты, которые в настоящее время недоступны. Состояние _микрофона конференции_ _неработоспособно_, что может быть причиной возникновения нескольких причин. Так как не все компоненты прошли проверку, в параметре "ResourceState" (Состояние ресурса) содержится значение "Unhealthy" (Неработоспособно). В этом случае необходимо обратиться к техническому специалисту для дальнейшего анализа причин неполадок. |
| 4000  <br> Информация  <br> | Событие, свидетельствующее о перезапуске приложения. Записывается в журнал событий Windows при каждом перезапуске приложения.  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> Приложение может перезапуститься по разным причинам. Сравните частоту перезапуска устройств в одном здании и в разных зданиях. Помните об известных проблемах, таких как колебания питания и сбои, так как это может оказаться подсказкой к проблемам с инфраструктурой.|

## <a name="related-topics"></a>Статьи по теме
 

[Планирование Комнаты Microsoft Teams мониторинга с помощью Azure Monitor](azure-monitor-plan.md)

[Развертывание Комнаты Microsoft Teams мониторинга с помощью Azure Monitor](azure-monitor-deploy.md)
