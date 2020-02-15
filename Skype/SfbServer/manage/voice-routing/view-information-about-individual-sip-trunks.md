---
title: Просмотр сведений об отдельных магистральных магистральных каналах SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: В Skype для бизнеса Server несколько магистральных каналов можно назначить одному шлюзу PSTN; Это означает, что шлюзы и магистрали не относятся к одному и тому же, а администраторы должны использовать командлет Get – CsTrunk для просмотра сведений об отдельной магистральной магистральной сети SIP.
ms.openlocfilehash: c5288e676f546e07504f4d8609fcea63913b6457
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048182"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Просмотр сведений об отдельных магистральных магистральных каналах SIP в Skype для бизнеса Server

В Skype для бизнеса Server несколько магистральных каналов можно назначить одному шлюзу PSTN; Это означает, что шлюзы и магистральные линии не относятся к одному и тому же, а администраторы должны использовать командлет [Get – CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) для просмотра сведений об отдельной магистральной магистральной сети SIP.

Командлет Get-CsTrunk можно выполнить из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.

**Просмотр сведений обо всех магистральных магистральных каналах SIP**

Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.

`Get-CsTrunk`

**Просмотр сведений об определенной магистрали SIP**

Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Просмотр сведений о всех магистралях SIP, назначенных пулу**

В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
