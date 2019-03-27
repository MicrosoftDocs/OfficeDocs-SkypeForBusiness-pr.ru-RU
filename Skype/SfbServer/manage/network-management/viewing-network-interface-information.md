---
title: Просмотр сведений о сетевом интерфейсе
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Можно просмотреть сведений о сетевом интерфейсе с помощью командлета Get-CsNetworkInterface и Windows PowerShell. Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.
ms.openlocfilehash: df4424e33cb42f3c1b2311cc822c762a2c4878f1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888031"
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


