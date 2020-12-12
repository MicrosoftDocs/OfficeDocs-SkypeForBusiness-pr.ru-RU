---
title: Управление устройствами комнат Microsoft Teams с помощью Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: В этой статье рассмотрено интегрированное управление устройствами комнат Microsoft Teams с помощью Azure Monitor.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16105e77c8e66afa00f089d1337984b7e7d9a502
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662054"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>Управление устройствами комнат Microsoft Teams с помощью Azure Monitor

В этой статье рассмотрено интегрированное управление устройствами комнат Microsoft Teams с помощью Azure Monitor.

Вы можете настроить Azure Monitor так, чтобы предоставлять базовую телеметрию для управления устройствами в комнате собраний Skype. Дополнительные [сведения см.](azure-monitor-plan.md) в плане управления комнатами Microsoft Teams с помощью azure Monitor и развертывании управления комнатами [Microsoft Teams с помощью Azure Monitor.](azure-monitor-deploy.md) По мере взросления решения для управления вы можете использовать дополнительные данные и возможности управления для создания более подробного представления о производительности устройства.

## <a name="understand-the-log-entries"></a>Общие сведения о записях журнала

Следующие описания событий вставляются в поле описания журнала событий каждые пять минут, когда приложение Microsoft Teams Rooms записит соответствующие сведения в журнал событий Windows. Агент мониторинга Майкрософт передает эти записи в средство аналитики журнала в Azure Monitor, который анализирует их на панели мониторинга, созданной при развертывании комнат Microsoft Teams с помощью [Azure Monitor.](azure-monitor-deploy.md) С помощью панели мониторинга можно использовать отдельные записи журнала, чтобы при необходимости определить курсы действий.

ИД событий 2000 и 3000 указывают на то, что устройство работает, как ожидалось. ИД событий 2001 и 3001 указывают на то, что проблема обнаружена. По сравнению с базовым показателем или другими развернутными устройствами в организации, если он виден чаще, чем вы ожидаете, может потребоваться действие.

Имея общее представление об этих оповещениях о событиях, вы сможете быстрее выявлять источник проблем и определять начальные данные для дальнейшего устранения неполадок.

| Уровень &nbsp; ИД &nbsp; события|Поведение &nbsp; события&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Описание &nbsp; события&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Информация | Периодическое событие, свидетельствующее о нормальном функционировании системы. Каждые 5 минут комнаты Microsoft Teams проверяют, что они подключены к Microsoft Teams или Skype для бизнеса и подключены к сети и Exchange. <br> Если все три фактора истинны, он записывает В журнал событий 2000 каждые 5 минут, пока устройство не будет отключено или одно или несколько условий не будут выполнены. | {"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias <span></span> @contoso.com", "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IP v6 address"} <br><br> В этом примере все условия пульса были выполнены, а устройство Microsoft Teams Rooms было помечено как работоспособное. При возникновении ошибок в журнал записывается идентификатор события 2001. |
| 2001  <br> Ошибка | Событие, свидетельствующее об ошибке приложения. Каждые 5 минут комнаты Microsoft Teams проверяют, что они подключены к Microsoft Teams или Skype для бизнеса с подключением к сети и Exchange. Если один или несколько факторов не истинны, он записывает EventID 2001 в журнал событий каждые 5 минут, пока устройство не будет выключено или все условия будут выполнены снова.  | {"Description":"Network status : Healthy. Exchange status : Connected. **Signin status: Unhealthy.** ", "ResourceState":"Неработоспособное", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"} <br><br>  В этом примере комнаты Microsoft Teams определили, что сетевое подключение было полезным, а приложение было подключено к Exchange, но в области, выделенный полужирным шрифтом, указано, что приложение не подключено. Это может быть связано с проблемами конфигурации на устройстве или хосте.  <br> <br> Состояние сети указывается как "Неработоспособная" или "Неработоспособная". Если состояние неработоспособное, возможно, у вас проблема с сетью или устройство было отключилось (но в этом случае могли возникнуть ошибки Exchange, Microsoft Teams или Skype для бизнеса).  <br><br> Состояние Exchange указывается как "Подключено" или одно из следующих: "Отключено", "Подключение", "АвтообнаружениеError" (наиболее распространенная ошибка), "ОбщийError" или "ServerVersionNotSupported". Если состояние подключено, подождите, пока не будет отправлено следующее сообщение о состоянии. Другие ошибки отправляются администратору, который имеет опыт устранения проблем с Exchange.  <br><br>  Состояние при входе (указывающее на то, что приложение было входом) указывает на состояние "Неработоспособные" или "Неработоспособное". Если система неработоспособна, обратитесь к техническому специалисту для устранения неполадок. |
| 3000  <br> Информация | Это событие проверяет, было ли оборудование установлено и работает нормально. Каждые 5 минут в комнатах Microsoft Teams проверяется, подключены и работают ли настроенные аппаратные компоненты, такие как экран комнаты, микрофон, динамики и камера. Если все компоненты полезны, в журнал событий записывается eventID 3000. Это событие пишется каждые 5 минут, если только не существует проблем с подключенным устройством.  <br> | {"Description":"HardwareCheckEngine is healthy.", "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias <span></span> @contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}  <br><br> В этом примере все проверки оборудования пройдены успешно. Если были ошибки, приложение будет записывать ИД события 3001. |
| 3001  <br> Событие ошибки  | Событие, свидетельствующее об ошибке оборудования. В приложении "Комнаты Microsoft Teams" есть процесс, который проверяет состояние подключенных аппаратных компонентов (переднего вида помещения, микрофона, динамика, камеры) каждые 5 минут. Если один или несколько компонентов неработоспособны, он записывает в журнал событий событие EventID 3001. Это событие фиксируется каждые 5 минут, пока не будет устранена проблема с устройством.   | {"Description":" **Front of Room Display status : Неработоспособное.** Configured display count is 2. Real display count is 0. **Conference Microphone status : Unhealthy.** Conference Speaker status : Healthy. Default Speaker status : Healthy. Состояние камеры: "Здоровое", "Состояние ресурсов":"Неработоспособное", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias <span></span> @contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"} <br><br>  В параметрах, соответствующих периферийным компонентам оборудования, может отображаться значение "Healthy" (Работоспособно) или "Unhealthy" (Неработоспособно). <br> В этом примере в системе настроены два фронтальных дисплея, ни один из которых на данный момент не доступен. Состояние микрофона конференции неработоспособно, что может быть причиной нескольких причин. Так как не все компоненты прошли проверку, в параметре "ResourceState" (Состояние ресурса) содержится значение "Unhealthy" (Неработоспособно). В этом случае необходимо обратиться к техническому специалисту для дальнейшего анализа причин неполадок. |
| 4000  <br> Информация  <br> | Событие, свидетельствующее о перезапуске приложения. Записывается в журнал событий Windows при каждом перезапуске приложения.  <br> | {"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias <span></span> @domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"} <br><br> Приложение может быть перезапущено по разным причинам. Сравните частоту перезапуска устройств в одном здании и в разных зданиях. Помните об известных проблемах, например колебаниях питания и сбоях, так как это может оказаться подсказкой к проблемам в инфраструктуре.|

## <a name="related-topics"></a>Статьи по теме
 

[Планирование управления комнатами Microsoft Teams с помощью Azure Monitor](azure-monitor-plan.md)

[Развертывание управления помещениями Microsoft Teams с помощью Azure Monitor](azure-monitor-deploy.md)
