---
title: Сценарий PowerShell для проверки соединения с контроллером границ между прямыми сеансами маршрутизации
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Используйте этот пример сценария PowerShell для тестирования подключений между контроллерами границ для сеансов прямого маршрутизации в Microsoft Teams.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9910ac347b5e797ad30ac65e76173ba4024a87c4
ms.sourcegitcommit: fa55f9e3690fcca36b530bd13a9eeaa44120b87c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "37547241"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Сценарий PowerShell для проверки соединения с контроллером границ между прямыми сеансами маршрутизации

Клиент тестеров SIP — это образец сценария PowerShell, который можно использовать для тестирования подключений между однонаправленными контроллерами границ (SBC) для связи в Microsoft Teams. Этот сценарий проверяет основные функциональные возможности магистрального протокола SIP с прямой маршрутизацией.

Сценарий отправляет тест SIP в средство выполнения тестов, ждет результата, а затем представляет его в удобочитаемом формате. Вы можете использовать этот сценарий, чтобы протестировать указанные ниже сценарии.

- Входящие и исходящие звонки
- Одновременный звонок
- Эскалация мультимедиа
- Передача консултативе

## <a name="download-the-script-and-documentation"></a>Скачайте сценарий и документацию

Скачайте [клиентский сценарий тестеров SIP и документацию](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).