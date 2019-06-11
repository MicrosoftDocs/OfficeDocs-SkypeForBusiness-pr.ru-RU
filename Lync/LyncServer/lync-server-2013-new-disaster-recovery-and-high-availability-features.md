---
title: 'Lync Server 2013: новые возможности высокой доступности и аварийного восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e93e2265d401c6dca16f5c00c339fbdc893aba0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>Новые возможности высокой доступности и аварийного восстановления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-20_

Как и в Lync Server 2010, основная схема высокой доступности для Lync Server 2013 основывается на избыточности сервера посредством группировки. Если сервер, на котором работает определенная роль, завершает работу со сбоем, другие серверы в пуле, выполняющие ту же самую роль, берут на себя нагрузку первого сервера. Это применимо к интерфейсным серверам, пограничным серверам, серверам-посредникам и директорам.

Lync Server 2013 добавляет новые показатели аварийного восстановления, позволяя связывать пулы интерфейсов, расположенные в двух центрах обработки данных. Если один из сопоставленных пулов выходит из строя, администратор может перенести пользователей из этого пула в другой пул в паре для предоставления возможности продолжения обслуживания. Эта функция не требует дорогостоящих сетевых и аппаратных решений, таких как сети хранения данных или общие диски.

Lync Server 2013 также добавляет полную доступность сервера для серверной части. Это необязательная топология, в которой развертывается два серверных сервера для пула переднего плана, а также синхронное зеркальное отображение SQL для всех баз данных Lync, запущенных на серверном сервере. Вы можете выбрать, нужно ли развертывать следящий сервер для зеркала.

<div>

## <a name="see-also"></a>См. также


[Планирование высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

