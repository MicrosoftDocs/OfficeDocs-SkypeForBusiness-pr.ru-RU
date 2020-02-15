---
title: 'Lync Server 2013: удаление файлов обновления устройств, не связанных с устройством'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c456deb3b3cb72df0bd6e8ac2dd70e926bb0769
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a>Удаление файлов обновления устройств, не связанных с устройством, в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-20_

При каждом поступлении новых обновлений устройства в систему создается соответствующее правило обновления устройства. По умолчанию эти новые правила обновления устройств назначены состоянию ожидания. Это означает, что правила можно загружать и устанавливать на тестовые устройства, но не на рабочих устройствах, что позволяет протестировать обновления, прежде чем сделать их доступными для пользователей. На основе тестов вы принимаете и развертываете или отклоняете и удаляете обновление. Когда вы отклоняете обновление, обновление устройства не связано с правилом обновления устройства.

<div>


Файлы обновления устройств, которые больше не связаны с устройством, можно удалить с помощью Windows PowerShell и командлета **clear – ксдевицеупдатефиле** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]  
> Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>статье Lync Server Windows PowerShell в блоге.



</div>

<div>


  - Например, следующая команда удаляет все правила обновления устройств на веб-сервере atl-cs-001.litwareinc.com, которые больше не связаны с устройством:
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

Дополнительные сведения см. в разделе справки для командлета [clear – ксдевицеупдатефиле](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

