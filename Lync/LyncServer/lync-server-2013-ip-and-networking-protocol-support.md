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

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a><span data-ttu-id="d2277-102">Поддержка протоколов IP и сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2277-102">IP and networking protocol support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2277-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d2277-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d2277-104">Lync Server 2013 поддерживает следующие протоколы IP и сети:</span><span class="sxs-lookup"><span data-stu-id="d2277-104">Lync Server 2013 supports the following IP and networking protocols:</span></span>

  - <span data-ttu-id="d2277-105">**IP-протоколы.**    Lync Server 2013 поддерживает протокол IP версии 4 (IPv4) или IP версии 6 (IPv6) для сети сервера.</span><span class="sxs-lookup"><span data-stu-id="d2277-105">**IP Protocols.**   Lync Server 2013 supports either IP version 4 (IPv4) or IP version 6 (IPv6) for the server network.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d2277-106">Lync Server 2013 может работать в сети с включенным двойным стеком IP.</span><span class="sxs-lookup"><span data-stu-id="d2277-106">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

    
    </div>

  - <span data-ttu-id="d2277-107">**Транспортный протокол SIP.**    В общем случае SIP может использовать по крайней мере три типа транспорта: протокол UDP, протокол управления передачей (TCP) и протокол TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="d2277-107">**SIP Transport Protocols.**   Generically, SIP can use at least three transport types: User Datagram Protocol (UDP), Transmission Control Protocol (TCP), and Transport Layer Security (TLS).</span></span> <span data-ttu-id="d2277-108">В конфигурации SIP по умолчанию TLS запускается поверх TCP.</span><span class="sxs-lookup"><span data-stu-id="d2277-108">In the default SIP transport configuration, TLS runs over TCP.</span></span> <span data-ttu-id="d2277-109">Протокол TLS используется в сети Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d2277-109">TLS is used within the Lync Server 2013 network.</span></span> <span data-ttu-id="d2277-110">На краю сети Lync Server 2013 может взаимодействовать по протоколу TCP.</span><span class="sxs-lookup"><span data-stu-id="d2277-110">At the edge of the network, Lync Server 2013 can interoperate over TCP.</span></span> <span data-ttu-id="d2277-111">Lync Server 2013 не поддерживает транспортный протокол UDP, так как он не соответствует минимальным стандартам безопасности, надежности и масштабируемости для корпоративной связи.</span><span class="sxs-lookup"><span data-stu-id="d2277-111">Lync Server 2013 does not support UDP for SIP transport because it doesn’t meet the minimum standards for enterprise communications security, reliability, and scalability.</span></span> <span data-ttu-id="d2277-112">Дополнительные сведения см. в статье, посвященной записи в блоге, "to UDP, а не UDP, который является вопросом [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369)" по адресу.</span><span class="sxs-lookup"><span data-stu-id="d2277-112">For details, see the NextHop blog article, "To UDP, or not to UDP, that is the question," at [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d2277-113">Содержимое и URL-адрес любого блога могут быть изменены без предварительного уведомления.</span><span class="sxs-lookup"><span data-stu-id="d2277-113">The content of each blog and its URL are subject to change without notice.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

