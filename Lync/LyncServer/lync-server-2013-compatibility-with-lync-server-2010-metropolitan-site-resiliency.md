---
title: Совместимость Lync Server 2013 с использованием устойчивости сайта Lync Server 2010 для микрогородка
description: Совместимость Lync Server 2013 с устойчивостью сайта Lync Server 2010 для микрогородка.
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
ms.openlocfilehash: ec72f261ac593b24bad13dcd400f495ba7ba0722
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576935"
---
# <a name="lync-server-2010-metropolitan-site-resiliency"></a>Устойчивость сайта Lync Server 2010 для городового сайта

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-03-19_

Решение устойчивости сайта, поддерживаемое для Lync Server 2010, не поддерживается для Lync Server 2013. Это решение включает расширение одного пула переднего плана для охвата двух центров обработки данных в одном и том же регионе.

Решение устойчивости сайта с использованием объекта, предназначенное для восстановления после потери полного центра обработки данных. При охвате пула на два центра обработки данных вы обычно располагаете половину интерфейсных концов в одном центре обработки данных, а вторая половина — в другом. Если вы потеряете весь центр обработки данных, вы потеряли половину серверов переднего плана. Это может привести к проблемам с новой моделью распределенной системы для пулов переднего плана в Lync Server 2013. Для получения дополнительных сведений см [топология и компоненты для серверов переднего плана, обмена мгновенными сообщениями и сведений о присутствии в Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

</div>

<span> </span>

</div>

</div>

</div>

