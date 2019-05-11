---
title: Просмотр сведений об отдельных магистралях SIP в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В Скайп для Business Server несколько магистралей можно назначить один шлюз ТСОП; Это означает, что шлюзов и магистральных линий связи не одной и той же, что администраторы должны использовать командлет Get-CsTrunk для просмотра сведений об отдельных канала SIP.
ms.openlocfilehash: bf9229dba17b7b2e49eb9a05d9469f42c0b9b998
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930822"
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
