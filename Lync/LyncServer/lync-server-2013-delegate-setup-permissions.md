---
title: 'Lync Server 2013: Делегирование разрешений на установку'
description: 'Lync Server 2013: Делегирование разрешений на установку.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7038cf729bad459dbcd2a84a308b14aa56b68dd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545345"
---
# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Делегирование разрешений на установку в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-02-05_

Если вы не хотите предоставлять членство в группе "Администраторы домена" пользователям или группам, которые развертывают Lync Server 2013, можно включить членов группы RTCUniversalServerAdmins для запуска командлета Windows PowerShell **Enable – CsTopology**   на серверах, на которых работает Lync Server 2013. По умолчанию члены группы RTCUniversalServerAdmins не имеют прав на выполнение этого командлета. Права и разрешения администратора предоставляются для запуска командлета **Enable-CsTopology** на серверах, работающих под управлением Lync Server, с помощью командлета **Grant-CsSetupPermission** и указания подразделения, в котором расположены объекты-компьютеры для сервера, на котором работает Lync Server 2013.

Подготовка домена, которая выполняется при установке Lync Server, не добавляет разрешения, которые позволяют членам группы RTCUniversalServerAdmins выполнять командлет Enable-CsTopology. Это значит, что по умолчанию нужны права администратора домена для включения топологии. Чтобы дать членам группы RTCUniversalServerAdmins право включать топологию, следует запустить командлет Grant-CsSetupPermissions. Кроме того, этот командлет необходимо выполнить для каждого контейнера Active Directory, в котором разработаны компьютеры, работающие под управлением Lync Server.

Помните, что данный командлет дает права только членам группы RTCUniversalServerAdmins; права не могут быть предоставлены другим группам безопасности или отдельным пользователям.

<div>


> [!NOTE]  
> <STRONG>Enable-CsTopology</STRONG> — это ключевой командлет, позволяющий членам группы RTCUniversalServerAdmins настраивать и развертывать Lync Server 2013.



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>Добавление возможности выполнения командлета Enable-CsTopology группе RTCUniversalServerAdmins

1.  Войдите на сервер как член группы администраторов домена того домена, в котором делегированный пользователь будет выполнять командлет **Enable-CsTopology**.

2.  Откройте консоль управления Lync Server 2013. Командная консоль Lync Server 2013 автоматически устанавливается на каждом сервере переднего плана или на любом компьютере, на котором установлены средства администрирования Lync Server 2013. Подробные сведения о командной консоли Lync Server 2013 можно найти в документации по [управлению Lync server 2013](lync-server-2013-lync-server-management-shell.md) в документации по операциям.

3.  Выполните следующий командлет из консоли управления Lync Server 2013:
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > Если подразделение находится не на верхнем уровне, необходимо предоставить полное доменное имя.

    
    </div>
    
    В следующем примере подразделение — это “Lync Servers”, и находится оно в домене contoso.com.
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

