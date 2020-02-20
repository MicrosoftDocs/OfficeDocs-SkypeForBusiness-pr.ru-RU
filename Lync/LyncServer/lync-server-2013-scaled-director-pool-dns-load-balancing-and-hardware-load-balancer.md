---
title: Масштабируемый пул директоров — балансировка нагрузки на DNS и аппаратный балансировщик нагрузки
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e36cb2036a15dd18263e8714a10122b76aaebace
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>Масштабируемый пул директоров — балансировка нагрузки на DNS и аппаратный балансировщик нагрузки в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-22_

Масштабируемый пул директоров, где существует несколько развернутых директоров для обработки дополнительной емкости и обеспечения высокой доступности, требует балансировки нагрузки для распространения связи клиента и сервера со всеми участниками пула. В директоре размещены веб-службы, как и пул переднего плана. Для балансировки нагрузки можно использовать аппаратную балансировку нагрузки либо балансировку нагрузки на DNS и аппаратную балансировку нагрузки. Поскольку балансировка нагрузки на DNS не удовлетворяет потребности веб-служб, в дополнении к ней используется аппаратная балансировка нагрузки.

В следующих разделах описываются рекомендации по планированию развертывания пула директоров с использованием балансировки нагрузки на DNS в сочетании с аппаратной балансировкой нагрузки. Если вы планируете использовать аппаратную балансировку нагрузки, но не балансировку нагрузки на DNS для пула директоров, ознакомьтесь с разделом [масштабируемый пул директоров — аппаратный балансировщик нагрузки в Lync Server 2013, в](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) котором описываются требования к планированию для этой топологии.

![Масштабируемый пул директоров](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Масштабируемый пул директоров")

<div>

## <a name="in-this-section"></a>Содержание

  - [Сводка по сертификатам: Балансировка нагрузки на DNS и HLB в Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Сводка по портам — балансировка нагрузки на DNS и HLB в Lync Server 2013](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Сводка по DNS — балансировка нагрузки на DNS и HLB в Lync Server 2013](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

