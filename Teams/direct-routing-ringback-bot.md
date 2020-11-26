---
title: Настройка Ringback Bot для прямой маршрутизации
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: В этой статье объясняется, как использовать Ringback Bot для прямой маршрутизации, чтобы предотвратить неожиданные тишины, которые могут возникать при установке звонка.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26738002ab333d2490ef0dac5674a1f7cdc19efd
ms.sourcegitcommit: 8974cd7a693bc879fed8222f551fd7ce3205dd65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420959"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Настройка Ringback Bot для прямой маршрутизации

В этой статье описывается программа Ringback Bot, с помощью которой можно избежать неожиданного замыкания, которое может возникнуть, если для установки звонков требуется больше времени. Ringback Bot доступен для прямой маршрутизации в режиме обхода файлов, не являющихся мультимедийными.

Иногда входящие звонки из телефонной сети общего пользования (КТСОП) для клиентов Teams могут занять больше времени, чем ожидалось. Это может быть вызвано различными причинами. В этом случае абонент может не слышать ничего, так как клиент Teams не позвонит, а некоторые поставщики телекоммуникационных услуг могут отменить звонок.

Ringback Bot помогает избежать неожиданного тишины, которое может возникнуть в этом сценарии. Для входящих звонков от КТСОП к клиентам Teams в Ringback Bot воспроизводится Специальный звуковой сигнал для вызывающего абонента, указывающий на то, что команды находятся в процессе установки звонка.

> [!NOTE]
> Ringback Bot создает ранний носитель из серверной части Teams. В некоторых странах и регионах вам может взиматься плата за звонок, когда вы начнете перетекание материала.

## <a name="configure-the-ringback-bot"></a>Настройка Ringback Bot

Используйте командлет [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) , чтобы изменить ранее определенную конфигурацию (SBC) или командлет [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) , чтобы создать новую конфигурацию SBC вместе с параметром **GenerateRingingWhileLocatingUser** для настройки Ringback Bot.

- Чтобы включить Ringback Bot, задайте для параметра **GenerateRingingWhileLocatingUser** значение " **$true**". Это значение по умолчанию. 

- Чтобы отключить Ringback Bot, задайте для параметра **GenerateRingingWhileLocatingUser** значение " **$false**". 

## <a name="related-topics"></a>Статьи по теме

- [Обзор PowerShell в Teams](teams-powershell-overview.md)
