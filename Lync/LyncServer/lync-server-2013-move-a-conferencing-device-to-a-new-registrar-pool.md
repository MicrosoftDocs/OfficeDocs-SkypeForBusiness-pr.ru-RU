---
title: 'Lync Server 2013: перемещение устройства конференц-связи в новый пул регистраторов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move a conferencing device to a new Registrar pool
ms:assetid: 26e02ca3-e881-4f90-8bf0-b13649108100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994025(v=OCS.15)
ms:contentKeyID: 51803934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69afbc1dbb33f43f8ed6a1f056f7d4a610b110c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-conferencing-device-to-a-new-registrar-pool-in-lync-server-2013"></a>Перемещение устройства конференц-связи в новый пул регистраторов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-20_

Перемещайте устройства из одного пула регистратора в другой с помощью командлета **Remove-ксмитингрум** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]  
> Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.



</div>

<div>


<div>

## <a name="moving-a-conferencing-device-to-a-new-registrar-pool"></a>Перемещение устройства конференц-связи в новый пул регистраторов

  - Чтобы переместить устройство конференц-связи, необходимо указать удостоверение комнаты для перемещения, а затем задать параметру Target полное доменное имя (FQDN) для пула регистратора, на который будет перемещено устройство. Например:
    
        Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Move-ксмитингрум](https://docs.microsoft.com/powershell/module/skype/Move-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

