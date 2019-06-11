---
title: 'Lync Server 2013: планирование высокой доступности и аварийного восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 092e59813f76690233a950cd8ce914df47146d37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Планирование высокой доступности и аварийного восстановления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-10-31_

Как и в Lync Server 2010, основная схема высокой доступности для большинства ролей сервера в Lync Server 2013 базируется на избыточности сервера посредством группировки. Если сервер, на котором работает определенная роль, завершает работу со сбоем, другие серверы в пуле, выполняющие ту же самую роль, берут на себя нагрузку первого сервера. Это применимо к интерфейсным серверам, пограничным серверам, серверам-посредникам и директорам.

Lync Server 2013 добавляет новые показатели аварийного восстановления для пулов переднего плана с помощью географических дисперсемент серверов в двух центрах обработки данных для предоставления услуг по продолжению всего пула или сайта.

Lync Server 2013 также повышает уровень высокой доступности сервера благодаря поддержке синхронного зеркального отображения SQL для серверных баз данных.

В этом разделе объясняются основные возможности высокой доступности и аварийного восстановления, а также описаны действия, которые можно выполнить для обеспечения высокой доступности и аварийного восстановления для других ролей сервера.

<div>

## <a name="in-this-section"></a>Содержание

  - [Аварийное восстановление пула переднего плана в Lync Server 2013](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Аварийное восстановление пограничного сервера в Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

  - [Планирование устойчивости корпоративной голосовой связи в Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Функции управления вызовами для аварийного восстановления в Lync Server 2013](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [Настройка сервера сохраняемого чата для обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Устойчивость главного сайта Lync Server 2010](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

