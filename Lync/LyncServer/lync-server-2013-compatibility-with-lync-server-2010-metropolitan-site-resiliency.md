---
title: Совместимость Lync Server 2013 с устойчивостью главного сайта Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 395ec568ebafea5c7a06e19340ff5ad10158ffb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a>Устойчивость главного сайта Lync Server 2010

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-03-19_

Решение для обеспечения устойчивости сайтов, поддерживающее для Lync Server 2010, не поддерживается для Lync Server 2013. Это решение вовлечено в объединение одного пула переднего плана в двух центрах обработки данных в одном регионе города.

Решение для обеспечения устойчивости сайтов с помощью этого типа разработано для восстановления после утраты полного центра обработки данных. При охвате пула в двух центрах обработки данных обычно размещается половина переднего плана в одном центре обработки данных и вторая половина во втором центре обработки данных. Если вы потеряли весь центр обработки данных, вы потеряли половину серверов переднего плана. Это может привести к возникновению проблем с новой моделью распределенной системы для пулов интерфейсов в Lync Server 2013. Дополнительные сведения можно найти [в разделе топологии и компоненты для серверов переднего плана, обмена мгновенными сообщениями и присутствия в Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

</div>

<span> </span>

</div>

</div>

</div>

