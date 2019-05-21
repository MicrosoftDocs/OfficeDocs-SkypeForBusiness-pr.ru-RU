---
title: Просмотр сведений о сетевом интерфейсе
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Вы можете просматривать сведения о сетевом интерфейсе с помощью Windows PowerShell и командлета Get-Кснетворкинтерфаце. Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.
ms.openlocfilehash: ac0df8450b938a377e1325f9c3179b4650b31bdf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279391"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Просмотр сведений о сетевом интерфейсе в Skype для бизнеса Server

Вы можете просматривать сведения о сетевом интерфейсе с помощью Windows PowerShell и командлета **Get-кснетворкинтерфаце** . Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell. 

## <a name="to-view-network-interface-information"></a>Просмотр сведений о сетевом интерфейсе

  - Чтобы просмотреть сведения о сетевом интерфейсе, введите в командной консоли Skype для Business Server указанную ниже команду и нажмите клавишу ВВОД.
    
        Get-CsNetworkInterface
    
    Эта команда возвращает сведения о каждом сетевом интерфейсе, как показано ниже.
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    Подробности можно найти в [статьях Get-кснетворкинтерфаце](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).


