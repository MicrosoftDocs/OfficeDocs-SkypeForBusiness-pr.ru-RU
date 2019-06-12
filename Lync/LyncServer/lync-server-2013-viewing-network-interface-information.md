---
title: 'Lync Server 2013: Просмотр сведений о сетевом интерфейсе'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network interface information
ms:assetid: e7dbb1ec-62b3-48be-a419-c493df5740e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721916(v=OCS.15)
ms:contentKeyID: 49733850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f15cf34c7a6743fdd3dbf23558e0c747a1c237bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-interface-information-in-lync-server-2013"></a>Просмотр сведений о сетевом интерфейсе в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Вы можете просматривать сведения о сетевом интерфейсе с помощью Windows PowerShell и командлета **Get-кснетворкинтерфаце** . Этот командлет можно выполнить из управляющей оболочки Lync Server 2013 или из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-view-network-interface-information"></a>Просмотр сведений о сетевом интерфейсе

  - Чтобы просмотреть сведения о сетевом интерфейсе, введите следующую команду в командной консоли Lync Server Management Shell и нажмите клавишу ВВОД.
    
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

</div>

</div>

<span> </span>

</div>

</div>

</div>

