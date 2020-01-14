---
title: Использование растянутого пула серверов сохраняемого чата для аварийного восстановления
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ae23ed2d12548388cd1462aad653de4652633dc
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>Использование растянутого пула серверов сохраняемого чата для аварийного восстановления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-06_

Решение для аварийного восстановления для сервера сохраняемого чата формируется на основе подтянутого пула серверов для постоянного чата. Это похоже на устойчивость сайта в том, что и в Lync Server 2010; Тем не менее, для растянутых виртуальных локальных сетей (VLAN) это не требуется. За счет растяжения пула серверов для постоянного чата вы, по сути, настраиваете один пул в топологии логически, но вы физически размещаете серверы в пуле в двух разных центрах обработки данных. Настройте зеркальное отображение SQL Server для базы данных таким же образом и разместите базу данных и зеркало в том же центре обработки данных. You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery). This is the backup database used for failover during disaster recovery.

Подробнее о том, как настроить зеркальное отображение SQL Server для обеспечения высокой доступности, можно найти [в разделе Зеркальное отображение SQL Server в Lync server 2013](lync-server-2013-sql-server-mirroring.md). Подробные сведения о том, как возвращать базу данных для аварийного восстановления, приведены [в разделе Настройка доставки журналов SQL Server в Lync Server 2013 для базы данных сервера сохраняемого чата](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) , а также [Настройка доставки журналов SQL Server между основной зеркальной базой данных и получателем доставки журналов в Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).

</div>

<span> </span>

</div>

</div>

</div>

