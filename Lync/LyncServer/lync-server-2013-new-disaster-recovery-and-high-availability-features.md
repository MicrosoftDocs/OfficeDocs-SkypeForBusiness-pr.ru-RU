---
title: 'Lync Server 2013: новые функции аварийного восстановления и обеспечения высокого уровня доступности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 366b58f05e8567659dc630042494f1ede25cf338
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42124432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>Новые функции аварийного восстановления и обеспечения высокой доступности в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-20_

Как и в Lync Server 2010, основная схема высокой доступности для Lync Server 2013 основана на избыточности сервера посредством пула. При сбое сервера с определенными ролями остальные серверы в пуле с такими же ролями берут на себя нагрузку этого сервера. Это касается серверов переднего плана, пограничных серверов, серверов-посредников и Директоров.

Lync Server 2013 добавляет новые меры аварийного восстановления, позволяя связывать пулы переднего плана, расположенные в двух центрах обработки данных. В случае выхода из строя одного из сопряженных пулов администратор может выполнить отработку отказа для пользователей из этого пула в другой пул из данной пары, обеспечивая таким образом непрерывность обслуживания. Эта функциональная возможность не требует дорогостоящих сетевых или аппаратных решений, таких как сети хранения или общие диски.

Lync Server 2013 также добавляет высокую доступность внутреннего сервера. Это необязательная топология, в которой развертываются два задних сервера переднего плана, а также синхронное зеркальное отображение SQL для всех баз данных Lync, запущенных на внутренних серверах. Вы можете выбрать, следует ли развернуть следящий сервер для зеркала.

<div>

## <a name="see-also"></a>См. также


[Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

