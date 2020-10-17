---
title: 'Lync Server 2013: Приложение A: использование командлетов для развертывания устройства для обеспечения связи в филиалах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix A: Using cmdlets to deploy a Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48184569
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e09cd7e0c5cc8bc20f50ba2c2ae5a1d912f949ab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531626"
---
# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a>Приложение а: использование командлетов для развертывания устройства для обеспечения связи в филиалах в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-07_

В этом разделе описывается, как развернуть устройство для обеспечения связи в филиалах с помощью командной консоли Lync Server. Выполните эту процедуру на центральном сайте.

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a>Удаленное развертывание устройства для обеспечения связи в филиалах

1.  Чтобы добавить новый сайт филиала, выполните процедуру, описанную в разделе [Добавление сайтов филиалов в топологию в Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) .

2.  Присоедините узел филиала к домену.

3.  Добавьте группу RTCUniversalSBATechnicians в локальную группу администраторов.

4.  Перезапустите сервер и войдите в систему в качестве члена группы RTCUniversalSBATechnicians.

5.  В командной консоли Lync Server введите следующие команды, заменив заполнители на правильные сведения для вашей организации:
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

