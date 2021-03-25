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
ms.openlocfilehash: 0e72b2550413004038b110292b693dda25affaf8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122423"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Просмотр сведений о сетевом интерфейсе в Skype для бизнеса Server

Сведения о сетевом интерфейсе можно просматривать с помощью Windows PowerShell и **командлета Get-CsNetworkInterface.** Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell. 

## <a name="to-view-network-interface-information"></a>Просмотр сведений о сетевом интерфейсе

  - Чтобы просмотреть сведения о сетевом интерфейсе, введите следующую команду в командной оболочке Skype для бизнес-серверов и нажмите кнопку ENTER:
    
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