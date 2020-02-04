---
title: 'Lync Server 2013: поддержка высокой доступности и аварийного восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73f6605f2fff063858a0180d61a306f7dd2d746
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a>Поддержка высокой доступности и аварийного восстановления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-25_

Lync Server 2013 обеспечивает высокий уровень доступности благодаря резервированию серверов с помощью группировки. При сбое сервера с определенными ролями остальные серверы в пуле с такими же ролями берут на себя нагрузку этого сервера. Это касается серверов переднего плана, пограничных серверов, серверов-посредников и Директоров. Подробнее о ролях сервера можно найти [в разделе роли сервера в Lync server 2013](lync-server-2013-server-roles.md).

Lync Server 2013 также предоставляет меры аварийного восстановления, включая Связывание пула. Если развернуть эту топологию, будут назначены пары интерфейсных пулов, при этом каждый пул из этой пары размещается в отдельном центре обработке данных и в отдельном регионе. Если один пул или сайт завершает работу, можно перенаправить пользователей этого пула в другой пул пары, что приведет к минимальному перерыву в обслуживании.

Lync Server 2013 также поддерживает высокий уровень доступности серверной части. Это необязательная топология, в которой вы развертываете два серверных внешних сервера для пула переднего плана и настроены синхронное зеркальное отображение SQL Server для всех баз данных Lync, запущенных на серверном сервере.

Подробные сведения о связывании и зеркальном отображении серверов можно найти [в разделе Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

<div>

## <a name="see-also"></a>См. также


[Роли сервера в Lync Server 2013](lync-server-2013-server-roles.md)  
[Планирование высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

