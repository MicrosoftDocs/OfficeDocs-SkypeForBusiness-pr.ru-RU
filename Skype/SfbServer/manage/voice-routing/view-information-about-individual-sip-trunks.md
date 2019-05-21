---
title: Просмотр сведений об отдельных магистральных линиях SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В Skype для бизнеса Server для одного шлюза PSTN может быть назначено несколько каналов. Это означает, что шлюзы и магистральные линии не являются одними и теми же, а администраторы должны использовать командлет Get-Кструнк для просмотра сведений о отдельной внешней магистрали SIP.
ms.openlocfilehash: f9199936dd4c9580c95c8b9708df04dcac13e1e8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274879"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Просмотр сведений об отдельных магистральных линиях SIP в Skype для бизнеса Server

В Skype для бизнеса Server для одного шлюза PSTN может быть назначено несколько каналов. Это означает, что шлюзы и магистральные линии — это не один и тот же, и что администраторы должны использовать командлет [Get-кструнк](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) для просмотра сведений о отдельной внешней магистрали SIP.

Командлет Get-Кструнк можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.

**Просмотр сведений о всех магистралях SIP**

Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.

`Get-CsTrunk`

**Просмотр сведений об определенной магистрали SIP**

Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Просмотр сведений для всех магистральных каналов SIP, назначенных пулу**

В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
