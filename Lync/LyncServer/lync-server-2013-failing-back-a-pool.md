---
title: 'Lync Server 2013: отработка отказа пула'
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
ms.openlocfilehash: c5929ed5fc3d29c0a42c223403a78f83154c5bef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a>Отработка отказа пула в Lync Server 2013

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

