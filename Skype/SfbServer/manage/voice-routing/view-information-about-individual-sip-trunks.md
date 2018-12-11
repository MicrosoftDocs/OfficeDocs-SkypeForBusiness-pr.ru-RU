---
title: Просмотр сведений об отдельных магистралях SIP в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В Скайп для Business Server несколько магистралей можно назначить один шлюз ТСОП; Это означает, что шлюзов и магистральных линий связи не одной и той же, что администраторы должны использовать командлет Get-CsTrunk для просмотра сведений об отдельных канала SIP.
ms.openlocfilehash: c8463fb23ea09167d760a1b9068235da871792c2
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222795"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Просмотр сведений об отдельных магистралях SIP в Скайп для Business Server

В Скайп для Business Server несколько магистралей можно назначить один шлюз ТСОП; Это означает, что шлюзов и магистральных линий связи не одной и той же и, что администраторы должны использовать командлет [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) для просмотра сведений об отдельных канала SIP.

Командлет Get-CsTrunk можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.

**Просмотр сведений о всех магистралях SIP**

Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.

`Get-CsTrunk`

**Просмотр сведений об определенной магистрали SIP**

Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Просмотр сведений о всех магистралях SIP, назначенных пулу**

В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`