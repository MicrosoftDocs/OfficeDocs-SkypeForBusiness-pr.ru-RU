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
ms.openlocfilehash: 3ec53f1d4f9cd21d3b28c87c07c1bc91d48b9b58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098425"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Настройка бота Ringback для прямой маршрутки

В этой статье описан бот Ringback, с помощью которого можно предотвратить неожиданные тишины, которые могут возникать, когда звонки устанавливаются дольше. Он доступен для прямой маршрутации в режиме обхода мультимедиа.

Иногда входящие звонки из телефонной сети общего звонков (STN) на клиенты Teams могут занять больше времени, чем ожидалось. Это может произойти по разным причинам. В этом случае звонок может ничего не слышать, клиент Teams не звонит, а некоторые поставщики телекоммуникаций могут отменить звонок.

В этом сценарии бот Ringback помогает избежать неожиданного тишины. Для входящие звонки из STN в клиенты Teams, бот Ringback воспроизводит характерный звуковой сигнал для вызываемого звонка, чтобы показать, что Teams находится в процессе установления звонка.

> [!NOTE]
> Бот Ringback создает мультимедиа на ранних стадиях из backend Teams. В некоторых странах и регионах при потоке мультимедиа с вас может взиматься плата за звонок.

## <a name="configure-the-ringback-bot"></a>Настройка бота Ringback

Используйте cmdlet [Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) для изменения ранее определенной конфигурации граничного контроллера сеанса (SBC) или для создания новой конфигурации SBC с параметром GenerateRingingWhileLocatingUser(New-CsOnlinePSTNGateway), чтобы создать новую конфигурацию SBC, а также параметр **GenerateRingingWhileLocatingUser** для настройки бота Ringback: [](/powershell/module/skype/new-csonlinepstngateway)

- Чтобы включить бот Ringback, установите для параметра **GenerateRingingWhileLocatingUser** **$True.** Это значение по умолчанию. 

- Чтобы отключить бот Ringback, установите для параметра **GenerateRingingWhileLocatingUser** **$False.** 

## <a name="related-topics"></a>Статьи по теме

- [Обзор PowerShell в Teams](teams-powershell-overview.md)