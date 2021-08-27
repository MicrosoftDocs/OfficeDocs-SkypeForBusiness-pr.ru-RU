---
title: Skype для бизнеса Server - Просмотр сведений об отдельных магистральных магистрали SIP
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: В Skype для бизнеса Server может быть назначено несколько стволов для одного шлюза PSTN. Шлюзы и магистрали не одно и то же, и администраторы должны использовать Get-CsTrunk для просмотра сведений об отдельном магистрали SIP.
ms.openlocfilehash: 2c39a35ee0a42e2f54e87541cec857b3d90cd2c6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617805"
---
# <a name="skype-for-business-server---view-information-about-individual-sip-trunks"></a>Skype для бизнеса Server - Просмотр сведений об отдельных магистральных магистрали SIP

В Skype для бизнеса Server может быть назначено несколько магистральных шлюзов для одного шлюза PSTN; это означает, что шлюзы и магистрали не одно и то же, и администраторы должны использовать [cmdlet Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) для просмотра сведений об отдельном магистрали SIP.

Этот Get-CsTrunk можно запускать из Skype для бизнеса Server или удаленного сеанса Windows PowerShell.

**Просмотр сведений для всех магистральных SIP**

Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.

`Get-CsTrunk`

**Просмотр сведений для определенного магистрали SIP**

Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Просмотр сведений о всех магистралях SIP, назначенных пулу**

В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
