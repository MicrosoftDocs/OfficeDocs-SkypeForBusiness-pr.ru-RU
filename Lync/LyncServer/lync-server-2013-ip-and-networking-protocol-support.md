---
title: 'Lync Server 2013: поддержка IP и сетевого протокола'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 285ed0d383b09276979ad6e29c390e2fc22a1caf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a>Поддержка IP и сетевого протокола в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-21_

Lync Server 2013 поддерживает следующие протоколы IP и сети:

  - **IP-протоколы.**    Lync Server 2013 поддерживает IP-версии 4 (IPv4) или IP версии 6 (IPv6) для серверной сети.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 может работать в сети с поддержкой двух стеков IP-адресов.

    
    </div>

  - **Транспортные протоколы SIP.**    В общем случае SIP может использовать по крайней мере три типа транспорта: протокол UDP и протокол управления передачей (TCP), а также TLS-защиту. В конфигурации транспорта SIP по умолчанию TLS выполняется по протоколу TCP. Протокол TLS используется в сети Lync Server 2013. На краю сети Lync Server 2013 может взаимодействовать по протоколу TCP. Lync Server 2013 не поддерживает транспортный протокол UDP для SIP, так как он не соответствует минимальным стандартам безопасности, надежности и масштабируемости для корпоративной связи. Подробные сведения можно найти в статье блога для NextHop: "для UDP, а не в UDP, вопрос которой —" по адресу [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369)".
    
    <div>
    

    > [!NOTE]  
    > Содержимое всех блогов и их URL-адреса могут быть изменены без уведомления.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

