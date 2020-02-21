---
title: 'Lync Server 2013: Включение или отключение устройства для конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a conferencing device
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994070(v=OCS.15)
ms:contentKeyID: 51803981
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27a5ed5c138d1389f0a3d4882bcdd437b5e7919e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a>Включение или отключение устройства конференц-связи в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-20_

Включите или отключите устройство конференц-связи с помощью командлета **Enable-CsMeetingRoom** и командлета **Disable-CsMeetingRoom** . Эти командлеты можно запускать из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]  
> Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>статье Lync Server Windows PowerShell в блоге.



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a>Включение устройства для конференц-связи

  - Чтобы включить устройство для конференц-связи, используйте командлет **Enable-CsMeetingRoom** . При включении устройства для конференц-связи необходимо включить в него идентификатор устройства конференц-связи, b) пул регистратора, в котором будет размещена учетная запись комнаты, и c) SIP-адрес, назначаемый этой учетной записи.
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a>Отключение устройства конференц-связи

  - Чтобы отключить устройство для конференц-связи, используйте командлет **Disable-CsMeetingRoom** . Убедитесь, что вы указали идентификатор отключенного устройства конференц-связи:
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

Дополнительные сведения можно найти в разделах справки о командлетах [Enable – CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) и командлете [Disable – CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

