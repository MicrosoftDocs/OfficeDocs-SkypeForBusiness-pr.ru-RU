---
title: Просмотр сведений о сетевом интерфейсе
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Сведения о сетевом интерфейсе можно просматривать с помощью Windows PowerShell и Get-CsNetworkInterface. Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.
ms.openlocfilehash: a9407000b6941c60e9ae62935b32308285be827a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386627"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Просмотр сведений о сетевом интерфейсе в Skype для бизнеса Server

Сведения о сетевом интерфейсе можно просматривать с помощью Windows PowerShell **и командлета Get-CsNetworkInterface**. Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.

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
