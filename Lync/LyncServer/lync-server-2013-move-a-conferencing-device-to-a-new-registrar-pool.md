---
title: 'Lync Server 2013: перемещение устройства конференц-связи в новый пул регистратора'
description: 'Lync Server 2013: перемещение устройства конференц-связи в новый пул регистратора.'
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
ms.openlocfilehash: 852e6c53ce86129a25e5831d54b1afb2c87828d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548045"
---
# <a name="move-a-conferencing-device-to-a-new-registrar-pool-in-lync-server-2013"></a>Перемещение устройства конференц-связи в новый пул регистратора в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-20_

Переместите устройство конференц-связи из одного пула регистратора в другой с помощью командлета **Move-CsMeetingRoom** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]  
> Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>


<div>

## <a name="moving-a-conferencing-device-to-a-new-registrar-pool"></a>Перемещение устройства конференц-связи в новый пул регистратора

  - Чтобы переместить устройство конференц-связи, необходимо указать идентификатор помещения для перемещения, а затем задать для параметра target полное доменное имя (FQDN) пула регистратора, в который будет перемещено устройство. Например:
    
        Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

</div>

Дополнительные сведения см. в разделе справки для командлета [Move – CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Move-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

