---
title: Просмотр сведений об отдельных магистральных серверах SIP в Skype для бизнеса Server
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
description: В Skype для бизнеса Server несколько магистральных серверов могут быть назначены одному шлюзу PSTN; это означает, что шлюзы и магистрали не одно и то же, и администраторы должны использовать Get-CsTrunk для просмотра сведений об отдельном стволе SIP.
ms.openlocfilehash: eebba2982a6f574ca2af99609f19ba5426139acb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103005"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Просмотр сведений об отдельных магистральных серверах SIP в Skype для бизнеса Server

В Skype для бизнеса Server несколько магистральных серверов могут быть назначены одному шлюзу PSTN; это означает, что шлюзы и магистрали не одно и то же, и администраторы должны использовать [cmdlet Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) для просмотра сведений об отдельном магистрали SIP.

Этот Get-CsTrunk можно запускать из оболочки управления Skype для бизнес-серверов или удаленного сеанса Windows PowerShell.

**Просмотр сведений для всех магистральных SIP**

Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.

`Get-CsTrunk`

**Просмотр сведений для определенного магистрали SIP**

Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Просмотр сведений о всех магистралях SIP, назначенных пулу**

В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`