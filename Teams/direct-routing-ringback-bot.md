---
title: Настройка бота Ringback для прямой маршрутки
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Узнайте, как использовать бот Ringback для прямой маршрутки, чтобы предотвратить неожиданные тишины, которые могут возникать при звонках.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91cea9183a85a804ca43464aab08f417ccaff1e8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827519"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Настройка бота Ringback для прямой маршрутки

В этой статье описан бот Ringback, с помощью которого можно предотвратить неожиданные тишины, которые могут возникать, когда звонки устанавливаются дольше. Он доступен для прямой маршрутации в режиме обхода мультимедиа.

Иногда входящие звонки из телефонной сети общего звонков (STN) на клиенты Teams могут занять больше времени, чем ожидалось. Это может произойти по разным причинам. В этом случае звонок может ничего не слышать, клиент Teams не звонит, а некоторые поставщики телекоммуникаций могут отменить звонок.

В этом сценарии бот Ringback помогает избежать неожиданного тишины. Для входящие вызовы из PSTN в клиенты Teams, бот Ringback воспроизводит характерный звуковой сигнал для вызываемого звонка, чтобы показать, что Teams находится в процессе установления звонка.

> [!NOTE]
> Бот Ringback создает мультимедиа на ранних стадиях из backend Teams. В некоторых странах и регионах с вас может взиматься плата за звонок, когда начнется поток мультимедиа.

## <a name="configure-the-ringback-bot"></a>Настройка бота Ringback

Используйте cmdlet [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) для изменения ранее определенной конфигурации граничного контроллера сеанса (SBC) или для создания новой конфигурации SBC с параметром GenerateRingingWhileLocatingUser(New-CsOnlinePSTNGateway), чтобы создать новую конфигурацию SBC, а также параметр **GenerateRingingWhileLocatingUser** для настройки бота Ringback: [](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)

- Чтобы включить бот Ringback, установите для параметра **GenerateRingingWhileLocatingUser** **$True.** Это значение по умолчанию. 

- Чтобы отключить бот Ringback, установите для параметра **GenerateRingingWhileLocatingUser** **$False.** 

## <a name="related-topics"></a>Статьи по теме

- [Обзор PowerShell в Teams](teams-powershell-overview.md)
