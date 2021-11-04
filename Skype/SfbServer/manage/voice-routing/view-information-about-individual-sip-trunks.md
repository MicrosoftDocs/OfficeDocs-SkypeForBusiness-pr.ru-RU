---
title: Skype для бизнеса Server - Просмотр сведений об отдельных магистральных магистрали SIP
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: В Skype для бизнеса Server может быть назначено несколько стволов для одного шлюза PSTN. Шлюзы и магистрали не одно и то же, и администраторы должны использовать Get-CsTrunk для просмотра сведений об отдельном магистрали SIP.
ms.openlocfilehash: dc5ccfdb5e248d843fb3a8a4e926a7e462097789
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774719"
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
