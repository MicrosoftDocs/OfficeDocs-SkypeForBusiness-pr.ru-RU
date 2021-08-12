---
title: Просмотр сведений о сетевом интерфейсе
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
description: Сведения о сетевом интерфейсе можно просматривать с помощью Windows PowerShell и Get-CsNetworkInterface. Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.
ms.openlocfilehash: 482655d36a16158866207e9157d25288e418f7e9ee00dc88ea7a59d653e5c566
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281802"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Просмотр сведений о сетевом интерфейсе в Skype для бизнеса Server

Сведения о сетевом интерфейсе можно просмотреть с помощью Windows PowerShell **и командлета Get-CsNetworkInterface.** Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell. 

## <a name="to-view-network-interface-information"></a>Просмотр сведений о сетевом интерфейсе

  - Чтобы просмотреть сведения о сетевом интерфейсе, введите следующую команду в командной Skype для бизнеса Server, а затем нажмите кнопку ENTER:
    
        Get-CsNetworkInterface
    
    Эта команда возвращает сведения, подобные приведенным ниже, для каждого сетевого интерфейса:
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    Дополнительные сведения см. в разделе [Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface).