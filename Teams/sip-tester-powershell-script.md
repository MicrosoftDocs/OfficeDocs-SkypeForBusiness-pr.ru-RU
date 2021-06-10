---
title: Сценарий PowerShell для тестирования подключений к контроллеру границ сеанса прямой маршрутии
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Используйте этот пример сценария PowerShell, чтобы проверить прямое подключение к контроллеру границы сеанса маршрутинга в Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c52febae3d734af49d1b23c7c65ceb0c2f746f7a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834279"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Сценарий PowerShell для тестирования подключений к контроллеру границ сеанса прямой маршрутии

Клиент SIP Tester — это пример сценария PowerShell, который можно использовать для проверки подключений к контроллеру границы сеанса прямой маршрутии (SBC) в Microsoft Teams. Этот сценарий проверяет основные функции связи с клиентом линии связи с протоколом SIP с прямой маршрутией.

Сценарий подает тест SIP тест-тестю, ждет результата, а затем представляет его в понятном для человека формате. Этот сценарий можно использовать для проверки следующих сценариев:

- Исходящие и входящие звонки
- Одновременный звонок
- Медиаумеха
- Консультационая передача

## <a name="download-the-script-and-documentation"></a>Скачивание сценария и документации

Скачайте сценарий клиента [SIP Tester и документацию.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)

  > [!NOTE]
  > Сценарий клиента SIP Tester adal.ps версии 3.19.8.1. Если используется более поздней версии adal.ps возвращается ошибка.
  
  
