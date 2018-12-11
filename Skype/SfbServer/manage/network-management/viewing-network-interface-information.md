---
title: Просмотр сведений о сетевом интерфейсе
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Можно просмотреть сведений о сетевом интерфейсе с помощью командлета Get-CsNetworkInterface и Windows PowerShell. Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.
ms.openlocfilehash: b3f1217c53176ae2a67ba81893864e1fb3a4e384
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222767"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Просмотр сведений о сетевом интерфейсе в Скайп для Business Server

Можно просмотреть сведений о сетевом интерфейсе с помощью командлета **Get-CsNetworkInterface** и Windows PowerShell. Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell. 

## <a name="to-view-network-interface-information"></a>Для просмотра сведений о сетевом интерфейсе

  - Для просмотра сведений о сетевом интерфейсе, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:
    
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
    
    Дополнительные сведения см [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).


