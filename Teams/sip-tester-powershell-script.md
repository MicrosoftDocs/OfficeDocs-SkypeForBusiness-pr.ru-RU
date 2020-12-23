---
title: Сценарий PowerShell для тестирования подключений к контроллеру границ прямого сеанса маршрутинга
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Используйте этот пример сценария PowerShell, чтобы протестировать прямое подключение к контроллеру границ сеанса маршрутинга в Microsoft Teams.
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
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Сценарий PowerShell для тестирования подключений к контроллеру границ прямого сеанса маршрутинга

Клиент SIP Tester — это пример сценария PowerShell, который можно использовать для проверки подключений граничного контроллера SBC к прямой маршрутике в Microsoft Teams. Этот сценарий проверяет основные функции связи SIP с прямой маршрутицией, сопряженной с клиентом.

Сценарий сообщает тест SIP тест-тесту, ждет результат, а затем представляет его в учитываемом для человека формате. Этот сценарий можно использовать для проверки следующих сценариев:

- Исходящие и входящие звонки
- Одновременный звонок
- Медианаука
- Консультация и передача

## <a name="download-the-script-and-documentation"></a>Скачивание сценария и документации

Скачайте сценарий клиента [SIP Tester и документацию.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)

  > [!NOTE]
  > Сценарий клиента SIP Tester поддерживает только adal.ps версии 3.19.8.1. Если используется более поздней версии adal.ps возвращается ошибка.
  
  
