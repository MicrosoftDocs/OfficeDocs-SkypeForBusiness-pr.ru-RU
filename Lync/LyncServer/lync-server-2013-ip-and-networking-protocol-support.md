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
ms.openlocfilehash: 8a9792ea8365dcd8941b831c43ab0406f9e33b90
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a>Поддержка протоколов IP и сети в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Lync Server 2013 поддерживает следующие протоколы IP и сети:

  - **IP-протоколы.**    Lync Server 2013 поддерживает протокол IP версии 4 (IPv4) или IP версии 6 (IPv6) для сети сервера.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 может работать в сети с включенным двойным стеком IP.

    
    </div>

  - **Транспортный протокол SIP.**    В общем случае SIP может использовать по крайней мере три типа транспорта: протокол UDP, протокол управления передачей (TCP) и протокол TLS (Transport Layer Security). В конфигурации SIP по умолчанию TLS запускается поверх TCP. Протокол TLS используется в сети Lync Server 2013. На краю сети Lync Server 2013 может взаимодействовать по протоколу TCP. Lync Server 2013 не поддерживает транспортный протокол UDP, так как он не соответствует минимальным стандартам безопасности, надежности и масштабируемости для корпоративной связи. Дополнительные сведения см. в статье, посвященной записи в блоге, "to UDP, а не UDP, который является вопросом [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369)" по адресу.
    
    <div>
    

    > [!NOTE]  
    > Содержимое и URL-адрес любого блога могут быть изменены без предварительного уведомления.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

