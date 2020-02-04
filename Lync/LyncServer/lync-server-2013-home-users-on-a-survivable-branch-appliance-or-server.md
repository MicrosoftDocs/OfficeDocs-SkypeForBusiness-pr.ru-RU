---
title: 'Lync Server 2013: нользователи, работающие дома на устройстве или сервере для обеспечения связи в филиалах'
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
ms.openlocfilehash: 0c6cca9528e884807f6180d8c99b143eb0041211
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Пользователи, работающие дома на устройстве или сервере для обеспечения связи в филиалах, в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-12-10_

Процесс доступа пользователей к сети с бесперебойной подразделением или работающем на нем сервере аналогичен процессу служб доступа к сети в пуле переднего плана. Проведите бесперебойную подсеть устройства филиалов или бесперебойно работающую процедуру сервера ветвей на центральном сайте.

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>Для домашних пользователей на бесперебойно работающем устройстве филиалов или на сервере, который находится в бесперебойном отделении

1.  Прежде чем переносить пользователей на сервер или бесперебойную подписку, откройте командную консоль Lync Server Management Shell, а затем выполните одно из указанных ниже действий.
    
      - Запустите командлет **Test-кспстнаутбаундкалл** , чтобы убедиться в том, что запущенный сервер филиала работает и настроено подключение к телефонной сети общего пользования (PSTN). Если вам нужно изменить свойства шлюза PSTN, используйте командлет **Set-кспстнгатевай**.
    
      - Запустите командлет **Get-ксвоицеполици** , чтобы убедиться в том, что пользователи, которые будут размещены на сервере для работающего филиала, имеют соответствующую политику маршрутизации VoIP. Если необходимо изменить политику VoIP, используйте командлет **Set-ксвоицеполици**.
    
      - Запустите командлет **Get-ксвоицемаилрераутингконфигуратион** , чтобы убедиться, что параметры перенаправления голосовой почты настроены. Если вам нужно изменить параметры перенаправления голосовой почты, используйте командлет **Set-ксвоицемаилрераутингконфигуратион**.

2.  В командной консоли Lync Server выполните командлет **Move-CsUser** , чтобы переместить домашних пользователей.

<div>


> [!NOTE]  
> Вы также можете использовать панель управления Lync Server для проверки необходимых и домашних пользователей.



</div>

<div>


> [!NOTE]  
> Пользователи, расположенные на устройстве с бесперебойной подразделением Lync Server, не могут создавать новые комнаты чата и просматривать открытку для существующих комнат.



</div>

</div>

<div>

## <a name="see-also"></a>См. также


[Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-Ксвоицеполици](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoicemailReroutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

