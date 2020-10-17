---
title: Использование растянутого пула серверов сохраняемого чата для аварийного восстановления
description: Использование растянутого пула серверов сохраняемого чата для аварийного восстановления.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b83a7226f7b9a49a2676b6222505f53247bd5abf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548545"
---
# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>Использование растянутого пула серверов сохраняемого чата для аварийного восстановления в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-06_

Решение по аварийному восстановлению для сервера сохраняемого чата основано на растянутом пуле серверов сохраняемого чата. Эта функция аналогична устойчивости сайта на месте в Lync Server 2010; Однако для растянутой виртуальной локальной сети не требуется никаких требований. По мере растягиванием пула серверов сохраняемого чата вы, по сути, настраиваете один пул в топологии логически, но серверы в пуле физически размещаются в двух разных центрах обработки данных. Настройка зеркального отображения SQL Server для базы данных аналогичным образом и развертывание базы данных и зеркальной копии в одном центре обработки данных. Необходимо настроить резервную базу данных в дополнительном центре обработки данных (с дополнительным зеркалом для обеспечения высокой доступности во время аварийного восстановления). Это резервная база данных, используемая для отработки отказа при аварийном восстановлении.

Сведения о том, как настроить зеркальное отображение SQL Server для обеспечения высокой доступности, можно найти [в разделе зеркалирование SQL Server в Lync server 2013](lync-server-2013-sql-server-mirroring.md). Сведения о том, как отработка отказа базы данных для аварийного восстановления, приведены [в статье Настройка доставки журналов SQL Server в Lync server 2013 для основной базы данных сервера сохраняемого чата](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) и [Настройка доставки журналов SQL Server между основным зеркалом и базой данных доставки журналов в Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).

</div>

<span> </span>

</div>

</div>

</div>

