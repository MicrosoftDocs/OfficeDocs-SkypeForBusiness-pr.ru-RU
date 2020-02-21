---
title: Управление аварийным восстановлением, высокой доступностью и службой резервного копирования Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89c18076a2bbc34386872a7fbee92c26b8084598
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>Управление аварийным восстановлением, высокой доступностью и службой резервного копирования Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-12_

В данном разделе описываются процедуры по аварийному восстановлению, а также по обслуживанию службы резервного копирования, которая синхронизирует данные в связанных интерфейсных пулах.

Процедуры аварийного восстановления — как отработка отказа, так и восстановление размещения — выполняются вручную. В случае аварии администратор должен вручную вызвать процесс отработки отказа. Это относится и к процессу восстановления размещения после восстановления пула.

В процедурах аварийного восстановления, которые приводятся в этом разделе, предполагается следующее.

  - У вас есть развернутые связанные пулы переднего плана, расположенные на разных сайтах, как описано в статье [Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Служба резервного копирования работает в этих сопряженных пулах для поддержания их синхронизации.

  - Если центральное хранилище управления размещается в любом пуле, оно устанавливается и запускается в обоих связанных пулах, где один из этих пулов размещает активный хозяин и другой пул, в котором размещается ждущий режим.

<div>


> [!IMPORTANT]
> В последующих процедурах параметр <EM>PoolFQDN</EM> указывает на полное доменное имя пула, затронутого аварией, а не того пула, с которого перенаправляются затронутые пользователи. Для одного набора затронутых пользователей он указывает на один и тот же пул в командлетах отработки отказа и восстановления размещения (то есть на пул, который первым принял пользователей перед отработкой отказа).<BR>Например, представьте себе ситуацию, когда для всех пользователей, размещенных в пуле P1, была выполнена отработка отказа в резервный пул P2. Если администратор хочет переместить всех пользователей, в данный момент обслуживаемых пулом P2, в пул P1, ему следует выполнить следующие действия: 
> <OL>
> <LI>
> <P>Выполнить восстановление размещения для всех пользователей, изначально размещенных в пуле P1, из пула P2 в пул P1 с помощью соответствующего командлета. В этом случае параметр <EM>PoolFQDN</EM> обозначает полное доменное имя пула P1.</P>
> <LI>
> <P>Выполнить отработку отказа для всех пользователей, изначально размещенных в пуле P2, в пул P1 с помощью соответствующего командлета. В этом случае параметр <EM>PoolFQDN</EM> обозначает полное доменное имя пула P2.</P>
> <LI>
> <P>Если позднее администратор хочет выполнить восстановление размещения для этих пользователей P2 обратно в пул P2, параметр <EM>PoolFQDN</EM> обозначает полное доменное имя пула P2.</P></LI></OL>Обратите внимание на то, что описанное выше действие 1 следует выполнять перед действием 2 для сохранения целостности пула. Если попытаться выполнить действие 2 перед действием 2, произойдет сбой командлета.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка и мониторинг службы резервного копирования в Lync Server 2013](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Отработка отказа для пула в Lync Server 2013](lync-server-2013-failing-over-a-pool.md)

  - [Отработка отказа пула в Lync Server 2013](lync-server-2013-failing-back-a-pool.md)

  - [Отработка отказа для зеркальной базы данных в Lync Server 2013](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Отработка отказа для пограничного пула, используемого для Федерации Lync Server в Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Отработка отказа для пограничного пула, используемого для Федерации XMPP в Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Отработка отказа пограничного пула, используемого для Федерации Lync Server или Федерации XMPP в Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Изменение пограничного пула, связанного с пулом переднего плана в Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Восстановление содержимого конференций с помощью службы резервного копирования в Lync Server 2013](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

