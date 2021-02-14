---
title: Просмотр сведений об отдельных магистрали SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: В Skype для бизнеса Server одному шлюзу STN может быть назначено несколько магистральных магистральных звонков; это означает, что шлюзы и магистрали не являются одинаковыми, и администраторы должны использовать Get-CsTrunk для просмотра сведений об отдельной магистрали SIP.
ms.openlocfilehash: b49846ed7244dec2f51f51f262becc440662026c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826179"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Просмотр сведений об отдельных магистрали SIP в Skype для бизнеса Server

В Skype для бизнеса Server одному шлюзу STN может быть назначено несколько магистральных магистральных звонков; это означает, что шлюзы и магистрали не являются одинаковыми и администраторы должны использовать для просмотра сведений об отдельной магистрали SIP с помощью [get-CsTrunk.](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)

The Get-CsTrunk cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.

**Просмотр сведений о всех магистрали SIP**

Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.

`Get-CsTrunk`

**Просмотр сведений для определенной магистрали SIP**

Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Просмотр сведений о всех магистралях SIP, назначенных пулу**

В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
