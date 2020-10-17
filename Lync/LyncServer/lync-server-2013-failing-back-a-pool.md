---
title: 'Lync Server 2013: отработка отказа пула'
description: 'Lync Server 2013: отработка отказа пула.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c1fc0ea4514d2f951dd936521590d47b809db38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567745"
---
# <a name="failing-back-a-pool-in-lync-server-2013"></a>Отработка отказа пула в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

После возврата пула, в котором возникла аварийная ситуация, в режим работы (в данном примере это Pool1) выполните следующие действия для восстановления обычного рабочего состояния развертывания.

Обратите внимание, что процедура отработки отказа занимает несколько минут. В качестве справки: отработка отказа для пула в 20000 пользователей занимает до 60 минут.

1.  Восстановите размещение пользователей, которые изначально размещались в пуле Pool1 и были переключены на пул Pool2; для этого введите следующий командлет:
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Другие действия не требуются. Если вы отработка отказа на центральном сервере управления, вы можете оставить ее в Pool2.

</div>

<span> </span>

</div>

</div>

</div>

