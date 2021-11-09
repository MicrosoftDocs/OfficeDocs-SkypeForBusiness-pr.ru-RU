---
title: Сценарий PowerShell для тестирования подключений к контроллеру границ сеанса прямой маршрутии
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Используйте этот пример сценария PowerShell, чтобы проверить прямое подключение к контроллеру границы сеанса маршрутинга в Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd2d0aa4a22e306d08ce215341e6e0a32efb100c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837471"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Сценарий PowerShell для тестирования подключений к контроллеру границ сеанса прямой маршрутии

Клиент SIP Tester — это пример сценария PowerShell, который можно использовать для проверки подключений Кграничный контроллер сеанса маршрутной маршрутии (SBC) в Microsoft Teams. Этот сценарий проверяет основные функции связи с клиентом линии связи с протоколом SIP с прямой маршрутией.

Сценарий сообщает тест SIP тест-тест-тесту, ждет результата, а затем представляет его в понятном для человека формате. Этот сценарий можно использовать для проверки следующих сценариев:

- Исходящие и входящие звонки
- Одновременный звонок
- Медиаумеха
- Консультационая передача

## <a name="download-the-script-and-documentation"></a>Скачивание сценария и документации

Скачайте сценарий клиента [SIP Tester и документацию.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)

  > [!NOTE]
  > Сценарий клиента SIP Tester adal.ps версии 3.19.8.1. Если используется более поздней версии adal.ps возвращается ошибка.
  
  
