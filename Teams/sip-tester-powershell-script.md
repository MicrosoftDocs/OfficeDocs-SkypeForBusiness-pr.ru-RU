---
title: Сценарий PowerShell для тестирования подключений пограничного контроллера сеанса прямой маршрутизации
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Используйте этот пример сценария PowerShell для тестирования подключений пограничного контроллера сеанса прямой маршрутизации в Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 215edfed535352004c960182bd649721131aedb0
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564137"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Сценарий PowerShell для тестирования подключений пограничного контроллера сеанса прямой маршрутизации

Клиент тестировщика SIP — это пример сценария PowerShell, который можно использовать для тестирования подключений пограничного контроллера сеанса прямой маршрутизации (SBC) в Microsoft Teams. Этот скрипт проверяет основные функциональные возможности магистрали протокола SIP, связываемого с клиентом, с прямой маршрутизациями.

Сценарий отправляет тест SIP в средство выполнения тестов, ожидает результат, а затем представляет его в понятном для человека формате. Этот сценарий можно использовать для тестирования следующих сценариев:

- Исходящие и входящие вызовы
- Одновременный звонок
- Эскалация мультимедиа
- Консультации по передаче

## <a name="download-the-script-and-documentation"></a>Скачивание скрипта и документации

Скачайте [скрипт и документацию клиента SIP Tester](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).

  > [!NOTE]
  > Клиентский скрипт тестатора SIP поддерживает только adal.ps версии 3.19.8.1. Если используется более поздняя версия adal.ps, будет возвращена ошибка.
  
  
