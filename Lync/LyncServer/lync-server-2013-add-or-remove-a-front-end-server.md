---
title: 'Lync Server 2013: Добавление или удаление сервера переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e358415b086594b67fabdc5ed74706a510e2f82
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>Добавление или удаление сервера переднего плана в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-01-21_

Когда вы добавляете в пул или удаляете из пула сервер переднего плана, вам необходимо перезапустить пул. Чтобы предотвратить перебои в обслуживании пользователей при добавлении или удалении сервера переднего плана, используйте следующую процедуру.

<div>


> [!NOTE]  
> Если вы добавляете в пул новые серверы, обновите новые серверы пула так, чтобы они были на том же накопительном уровне обновления, что и существующие серверы в пуле.



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>Добавление и удаление серверов переднего плана

1.  Если вы удаляете серверы переднего плана, сначала запретите новые подключения к ним. Для этого вы можете использовать следующий командлет:
    
        Stop-CsWindowsServices -Graceful

2.  Если на удаляемых серверах нет текущих сеансов, остановите на них службы Lync Server.

3.  Откройте построитель топологий и добавьте или удалите требуемые серверы.

4.  Опубликуйте топологию.

5.  Если для пула не было двух серверов переднего плана, более двух, или более двух серверов, в точности два, необходимо ввести следующий командлет:
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    Если в пуле три или более серверов, то по крайней мере три сервера должны работать, когда вы выполняете этот командлет.

6.  Перезапустите все серверы переднего плана в пуле по одному.

</div>

</div>

<span> </span>

</div>

</div>

</div>

