---
title: Просмотр сведений о сетевом интерфейсе
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Сведения о сетевом интерфейсе можно просматривать с помощью Windows PowerShell и Get-CsNetworkInterface. Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.
ms.openlocfilehash: 6031b1548b5c6d4fb83f9392a59f742bed98d9a4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838581"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Просмотр сведений о сетевом интерфейсе в Skype для бизнеса Server

Сведения о сетевом интерфейсе можно просмотреть с помощью Windows PowerShell **и командлета Get-CsNetworkInterface.** Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.

## <a name="to-view-network-interface-information"></a>Просмотр сведений о сетевом интерфейсе

Чтобы просмотреть сведения о сетевом интерфейсе, введите следующую команду в командной Skype для бизнеса Server, а затем нажмите кнопку ENTER:
    
`Get-CsNetworkInterface`

Эта команда возвращает сведения, подобные приведенным ниже, для каждого сетевого интерфейса:

```console    
Identity              : dc.vdomain.com/Primary/1
ComputerFqdn          : dc.vdomain.com
IPAddress             : 0.0.0.0
IPv6Address           :
Interface             : Primary
InterfaceNumber       : 1
ConfiguredFqdn        :
ConfiguredIPAddress   :
ConfiguredIPv6Address :
```

Дополнительные сведения см. в разделе [Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface).
