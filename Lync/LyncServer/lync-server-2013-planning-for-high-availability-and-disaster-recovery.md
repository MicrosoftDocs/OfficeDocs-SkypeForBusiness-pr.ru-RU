---
title: 'Lync Server 2013: Планирование высокой доступности и аварийного восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0ce8135481e283275bab507dfbe813a4fd1117b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-10-31_

Как и в Lync Server 2010, основная схема высокой доступности для большинства ролей серверов в Lync Server 2013 основана на избыточности сервера посредством пула. При сбое сервера с определенными ролями остальные серверы в пуле с такими же ролями берут на себя нагрузку этого сервера. Это касается серверов переднего плана, пограничных серверов, серверов-посредников и Директоров.

Lync Server 2013 добавляет новые меры аварийного восстановления для пулов переднего плана с помощью географических распределения серверов в двух центрах обработки данных, чтобы обеспечить продолжение обслуживания всего одного пула или сайта.

Lync Server 2013 также повышает высокую доступность внутреннего сервера за счет поддержки синхронного зеркального отображения SQL для серверных баз данных.

В этом разделе объясняются основные функции обеспечения высокого уровня доступности и аварийного восстановления, а также описываются действия, которые можно выполнить для обеспечения высокой доступности и аварийного восстановления для других ролей сервера.

<div>

## <a name="in-this-section"></a>Содержание

  - [Аварийное восстановление пула переднего плана в Lync Server 2013](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Аварийное восстановление пограничного сервера в Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

  - [Планирование устойчивости корпоративной голосовой связи в Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Функции управления вызовами для аварийного восстановления в Lync Server 2013](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [Настройка сервера сохраняемого чата для обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Устойчивость сайта Lync Server 2010 для городового сайта](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

