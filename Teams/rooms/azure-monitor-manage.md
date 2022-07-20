---
title: Мониторинг Комнаты Microsoft Teams устройств с помощью Azure Monitor
ms.author: dstrome
author: dstrome
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
description: В этой статье описывается, как Комнаты Microsoft Teams устройства с помощью Azure Monitor.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 38238d4b1d0bc33182f002e7dcf6389028315c48
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880213"
---
# <a name="monitor-microsoft-teams-rooms-devices-with-azure-monitor"></a>Мониторинг Комнаты Microsoft Teams устройств с помощью Azure Monitor

В этой статье описывается, как Комнаты Microsoft Teams с помощью Azure Monitor.

Вы можете настроить Azure Monitor для предоставления базовых данных телеметрии, которые помогут отслеживать устройства комнат собраний Microsoft Teams. [Дополнительные сведения см. в статье Комнаты Microsoft Teams](azure-monitor-plan.md) управления планами с помощью Azure Monitor [и развертывания Комнаты Microsoft Teams с помощью Azure Monitor](azure-monitor-deploy.md). По мере развития решения для мониторинга можно использовать другие возможности мониторинга и данных, чтобы получить более подробное представление о производительности устройства.

## <a name="understand-the-log-entries"></a>Общие сведения о записях журнала

Следующие описания событий вставляются в поле описания журнала событий каждые пять минут, когда приложение Комнаты Microsoft Teams записывает соответствующие сведения в журнал событий Windows. Microsoft Monitoring Agent передает эти записи в Log Analytics в Azure Monitor, который анализирует их на панели мониторинга, созданной при развертывании Комнаты Microsoft Teams мониторинга [с помощью Azure Monitor](azure-monitor-deploy.md). С помощью панели мониторинга можно просмотреть отдельные записи журнала, чтобы определить курсы действий при необходимости.

Идентификаторы событий 2000 и 3000 указывают, что Комнаты Teams работает должным образом. Идентификаторы событий 2001 и 3001 указывают на то, что обнаружена проблема. Для события с идентификатором 4000 может потребоваться действие, если оно отображается чаще, чем ожидалось, по сравнению с заданным базовым показателем или другими развернутными устройствами в организации.

Имея общее представление об этих оповещениях о событиях, вы сможете быстрее выявлять источник проблем и определять начальные данные для дальнейшего устранения неполадок.

| Уровень&nbsp;идентификатора&nbsp;события|Поведение&nbsp;события&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Описание&nbsp;события&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Информация | Периодическое событие, свидетельствующее о нормальном функционировании системы. Каждые 5 минут Комнаты Microsoft Teams, что он выполнил вход в Microsoft Teams или Skype для бизнеса подключен к сети и Exchange. <br> Если все три фактора верны, он записывает код события 2000 в журнал событий каждые 5 минут, пока устройство не будет отключено или одно или несколько условий больше не будут выполнены. | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> В этом примере выполнены все условия пульса, и устройство Комнаты Microsoft Teams было помечено как работоспособное. При возникновении ошибок в журнал записывается идентификатор события 2001. |
| 2001  <br> Ошибка | Событие, свидетельствующее об ошибке приложения. Каждые 5 минут Комнаты Microsoft Teams, что он вход в Microsoft Teams или Skype для бизнеса с подключением к сети и Exchange. Если один или несколько факторов не выполняются, событие EventID 2001 записывается в журнал событий каждые 5 минут, пока устройство не будет отключено или все условия будут выполнены еще раз.  | `{"Description":"Network status : Healthy. Exchange status : Connected. Sign in status: Unhealthy. Teams sign in status: Healthy.", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  В этом примере Комнаты Microsoft Teams, что сетевое подключение было работоспособным и приложение было подключено к Exchange, но выделенная полужирным шрифтом часть означает, что приложение не подключено. Это может быть связано с проблемами конфигурации на устройстве или хосте.  <br> <br> Состояние сети отображается как "Работоспособное" или "Неработоспособное". Если состояние неработоспособно, возможно, у вас возникли проблемы с сетью или устройство было отключено (но в этом случае, вероятно, также будут возникать ошибки Exchange и Microsoft Teams или Skype для бизнеса ошибки).  <br><br> Состояние Exchange отображается как подключенное или одно из следующих значений: Disconnected, Connecting, AutodiscoveryError (наиболее распространенная ошибка), GeneralError или ServerVersionNotSupported. Если состояние подключено, подождите, пока не будет отправлено следующее сообщение о работоспособности. Другие ошибки обратитесь к администратору с опытом решения проблем с Exchange.  <br><br>  Состояние _входа_/_в Teams_ (указывающее, что приложение войдите в Skype для бизнеса Или Teams) отображается как "Работоспособное" или "_Неработоспособное"_. Если система неработоспособна, обратитесь к техническому специалисту для устранения неполадок. |
| 3000  <br> Информация | Это событие проверяет, что проверка оборудования была выполнена и обнаружена как работоспособная. Каждые 5 минут Комнаты Microsoft Teams, что настроенные компоненты оборудования, такие как внешний интерфейс комнаты, микрофон, динамик и камера, подключены и выполняются. Если все компоненты работоспособны, он записывает EventID 3000 в журнал событий. Это событие записывается каждые 5 минут, если не возникла проблема с подключенным устройством.  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> В этом примере все проверки оборудования пройдены успешно. При возникновении ошибок приложение будет записывать идентификатор события 3001. |
| 3001  <br> Событие ошибки  | Событие, свидетельствующее об ошибке оборудования. В Комнаты Microsoft Teams есть процесс, который каждые 5 минут проверяет работоспособность подключенных аппаратных компонентов (перед комнатой, микрофоном, динамиком, камерой). Если один или несколько компонентов неработоспособны, он записывает EventID 3001 в журнал событий. Это событие записывается каждые 5 минут, пока проблема с устройством не будет устранена.   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>   В параметрах, соответствующих периферийным компонентам оборудования, может отображаться значение "Healthy" (Работоспособно) или "Unhealthy" (Неработоспособно).  <br> В этом примере настроены два  дисплея переднего плана комнаты, и в настоящее время ни один из них не доступен. Состояние _микрофона конференции_ _неработоспособно_, что может иметь несколько возможных причин. Так как не все компоненты прошли проверку, в параметре "ResourceState" (Состояние ресурса) содержится значение "Unhealthy" (Неработоспособно). В этом случае необходимо обратиться к техническому специалисту для дальнейшего анализа причин неполадок. |
| 4000  <br> Информация  <br> | Событие, свидетельствующее о перезапуске приложения. Записывается в журнал событий Windows при каждом перезапуске приложения.  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> Приложение может быть перезапущено по различным причинам. Сравните частоту перезапуска устройств в одном и том же здании и в разных зданиях. Помните об известных проблемах, таких как колебания мощности и сбои, так как это может оказаться подсказкой для проблем инфраструктуры.|

## <a name="related-topics"></a>Связанные статьи
 

[Планирование Комнаты Microsoft Teams мониторинга с помощью Azure Monitor](azure-monitor-plan.md)

[Развертывание Комнаты Microsoft Teams мониторинга с помощью Azure Monitor](azure-monitor-deploy.md)
