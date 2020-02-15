---
title: 'Lync Server 2013: Поддержка высокой доступности и аварийного восстановления'
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
ms.openlocfilehash: 6d3be41dd4ca3f942d5b57e1954cecf105fcc714
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a>Поддержка высокого уровня доступности и аварийного восстановления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-25_

Lync Server 2013 обеспечивает высокий уровень доступности при резервировании серверов с помощью пула. При сбое сервера с определенными ролями остальные серверы в пуле с такими же ролями берут на себя нагрузку этого сервера. Это касается серверов переднего плана, пограничных серверов, серверов-посредников и Директоров. Дополнительные сведения о ролях серверов приведены [в статье Server Roles in Lync server 2013](lync-server-2013-server-roles.md).

Lync Server 2013 также предоставляет меры аварийного восстановления, позволяя использовать функции связывания пула. Если развернуть эту топологию, будут назначены пары интерфейсных пулов, при этом каждый пул из этой пары размещается в отдельном центре обработке данных и в отдельном регионе. Если один пул или сайт завершает работу, можно перенаправить пользователей этого пула в другой пул пары, что приведет к минимальному перерыву в обслуживании.

Lync Server 2013 также поддерживает высокую доступность внутреннего сервера. Это необязательная топология, в которой развертываются два задних сервера переднего плана, а также выполняется настройка синхронного зеркального отображения SQL Server для всех баз данных Lync, запущенных на внутренних серверах.

Сведения о подключении к пулам и зеркальном отображении внутреннего сервера приведены [в статье Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

<div>

## <a name="see-also"></a>См. также


[Роли сервера в Lync Server 2013](lync-server-2013-server-roles.md)  
[Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

