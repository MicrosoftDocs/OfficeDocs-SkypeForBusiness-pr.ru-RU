---
title: Управление аварийным восстановлением Lync Server, высокой доступностью и службой резервного копирования
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
ms.openlocfilehash: d7adc4086ac8ac6b8e5ad33c2e4c1dc131d357e0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>Управление аварийным восстановлением, высокой доступностью и службой резервного копирования Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-12_

В этом разделе содержатся процедуры для операций аварийного восстановления, а также обслуживания службы резервного копирования, которая синхронизирует данные в связанных пулах серверных интерфейсов.

Процедуры аварийного восстановления, как в случае сбоя, так и для перемещения после сбоя, выполняются вручную. При возникновении аварии администратор должен вручную вызвать процедуры перемещения. Это применимо к восстановлению после восстановления пула.

Процедуры аварийного восстановления в оставшейся части этого раздела предполагают следующее:

  - У вас есть развертывание с подключенными пулами переднего плана, расположенными на разных сайтах, как описано в разделе [Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Служба архивации запущена на этих подключенных пулах, чтобы синхронизировать их.

  - Если хранилище Центрального управления размещено на любом из пулов, оно установлено и запущено на обоих из них, с одним из них, где размещается активный хозяин, и другой пул, на котором размещается резерв.

<div>


> [!IMPORTANT]
> В описанных ниже процедурах параметр <EM>пулфкдн</EM> указывает на полное доменное имя пула, на которое влияет авария, а не тот, на который перенаправлены пользователи, а не в пул. Для одного и того же набора затронутых пользователей он ссылается на один и тот же пул командлетов перемещения при сбое и восстановления размещения (то есть, пул, который сначала размещает пользователей перед переходом на другой ресурс).<BR>Например, предположим, что для всех пользователей, использующих пул P1, не удалось выполнить резервное копирование в распределенный пул P2. Если администратор хочет переместить всех пользователей, обслуживаемых в P2, для обслуживания с помощью P1, администратор должен выполнить указанные ниже действия. 
> <OL>
> <LI>
> <P>Не удается вернуть все пользователи, изначально размещенные в P1, из P2 в P1 с помощью командлета восстановления размещения. В этом случае <EM>пулфкдн</EM> — P1's FQDN.</P>
> <LI>
> <P>Отработка отказа всех пользователей, первоначально подключенных к P2, с помощью командлета failover. В этом случае <EM>пулфкдн</EM> — P2's FQDN.</P>
> <LI>
> <P>Если в дальнейшем администратор хочет вернуть пользователей P2 в P2, <EM>пулфкдн</EM> — P2's FQDN.</P></LI></OL>Обратите внимание, что шаг 1 описанный выше должен выполняться перед шагом 2, чтобы сохранить целостность пула. Если вы попытаетесь выполнить действие 2 перед шагом 1, командлет Step 2 завершится сбоем.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка и мониторинг службы резервного копирования в Lync Server 2013](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Отработка отказа для пула в Lync Server 2013](lync-server-2013-failing-over-a-pool.md)

  - [Отработка отказа для пула в Lync Server 2013](lync-server-2013-failing-back-a-pool.md)

  - [Отработка отказа с использованием зеркальной базы данных в Lync Server 2013](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Отработка отказа для пограничного пула, используемого для федерации Lync Server в Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Отработка отказа для пограничного пула, используемого для федерации XMPP в Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Отработка отказа для пограничного пула, используемого для федерации Lync Server или федерации XMPP в Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Изменение пограничного пула, связанного с пулом переднего плана в Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Восстановление содержимого конференций с помощью службы резервного копирования в Lync Server 2013](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Планирование высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

