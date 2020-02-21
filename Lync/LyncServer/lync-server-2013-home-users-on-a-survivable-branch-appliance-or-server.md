---
title: 'Lync Server 2013: домашние пользователи на устройстве или сервере для обеспечения связи в филиалах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f6fb176025dd7f075429833e48b53eb1f7a5b07
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Домашние пользователи на устройстве или сервере для обеспечения связи в филиалах в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-12-10_

Процесс, который пользователи могут обслуживать для обеспечения связи в филиалах или на сервере для обеспечения связи в филиалах, аналогичен процессу "пользователи из пула переднего плана". Выполните на центральном сайте устройство для обеспечения связи в филиалах или процесс обеспечения связи в филиалах.

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>Размещение пользователей на устройстве для обеспечения связи в филиалах или сервере для обеспечения связи в филиалах

1.  Перед перемещением пользователей на сервер для обеспечения связи в филиалах или для обеспечения связи в филиалах откройте командную консоль Lync Server, а затем выполните все указанные ниже действия.
    
      - Запустите командлет **Test-CsPstnOutboundCall** , чтобы убедиться в том, что сервер для обеспечения связи работает и настроено подключение к телефонной сети общего пользования (PSTN). Если требуется изменить свойства шлюза ТСОП, используйте командлет **Set-CsPstnGateway**.
    
      - Выполните командлет **Get – CsVoicePolicy** , чтобы убедиться, что пользователи, которые будут размещены на сервере для обеспечения связи в филиале, имеют соответствующую политику маршрутизации VoIP. Если требуется изменить политику VoIP, используйте командлет **Set-CsVoicePolicy**.
    
      - Запустите командлет **Get-CsVoicemailReroutingConfiguration**, чтобы убедиться, что настроены параметры перенаправления голосовой почты. Если требуется изменить параметры перенаправления голосовой почты, используйте командлет **Set-CsVoicemailReroutingConfiguration**.

2.  В командной консоли Lync Server выполните командлет **Move – CsUser** , чтобы переместить домашние пользователи.

<div>


> [!NOTE]  
> Вы также можете использовать панель управления Lync Server, чтобы проверить необходимые компоненты и домашние пользователи.



</div>

<div>


> [!NOTE]  
> Пользователи, размещенные на устройстве для обеспечения связи в филиалах Lync Server, не могут создавать новые комнаты чата или просматривать карточку комнаты для существующих комнат.



</div>

</div>

<div>

## <a name="see-also"></a>См. также


[Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get — Ксвоицемаилрераутингконфигуратион](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move — CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

