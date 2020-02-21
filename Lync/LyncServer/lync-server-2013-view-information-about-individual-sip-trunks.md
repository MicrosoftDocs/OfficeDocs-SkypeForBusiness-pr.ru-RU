---
title: 'Lync Server 2013: Просмотр сведений об отдельных магистральных магистральных каналах SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9663c6e762143eca572c0343ce21e91ad86b0b6d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a>Просмотр сведений об отдельных магистральных магистральных каналах SIP в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

Магистральные линии SIP используются для подключения телефонной сети Lync Server 2013 для передачи голоса по протоколу IP с телефонной сетью общего пользования. В предыдущих версиях продукта магистрали использовались для маршрутизации исходящих звонков с сервера-посредника на шлюз ТСОП, причем для каждого шлюза использовалась только одна магистраль. Поэтому шлюз ТСОП и магистраль SIP были практически равнозначны. Для администраторов это означало возможность просмотра сведений об отдельной магистрали SIP путем просмотра сведений о связанном шлюзе ТСОП.

Однако в Lync Server 2013 можно назначить несколько магистральных магистральов одному шлюзу PSTN; Это означает, что шлюзы и магистрали больше не являются одними и теми же. В свою очередь, это означает, что администраторам необходимо использовать новый командлет [Get – CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) для просмотра сведений об отдельной магистральной магистральной сети SIP.

Командлет Get – CsTrunk можно запустить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a>Просмотр сведений обо всех магистральных магистральных каналах SIP

  - Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a>Просмотр сведений об определенной магистрали SIP

  - Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Просмотр сведений о всех магистралях SIP, назначенных пулу

  - В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

