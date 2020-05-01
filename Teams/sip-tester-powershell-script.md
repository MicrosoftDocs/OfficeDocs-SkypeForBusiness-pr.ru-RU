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
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43d1514eff811461ac8b6ad73f7c2a215205f4e3
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951264"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Сценарий PowerShell для проверки соединения с контроллером границ между прямыми сеансами маршрутизации

Клиент тестеров SIP — это образец сценария PowerShell, который можно использовать для тестирования подключений между однонаправленными контроллерами границ (SBC) для связи в Microsoft Teams. Этот сценарий проверяет основные функциональные возможности магистрального протокола SIP с прямой маршрутизацией.

Сценарий отправляет тест SIP в средство выполнения тестов, ждет результата, а затем представляет его в удобочитаемом формате. Вы можете использовать этот сценарий, чтобы протестировать указанные ниже сценарии.

- Входящие и исходящие звонки
- Одновременный звонок
- Эскалация мультимедиа
- Передача consultative

## <a name="download-the-script-and-documentation"></a>Скачайте сценарий и документацию

Скачайте [клиентский сценарий тестеров SIP и документацию](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).

  > [!NOTE]
  > Клиентский сценарий тестера SIP поддерживает только adal.ps версии 3.19.8.1. Если используется более поздняя версия adal.ps, будет возвращена ошибка.
  
  
