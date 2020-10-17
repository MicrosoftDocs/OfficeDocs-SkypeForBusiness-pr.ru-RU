---
title: Использование растянутого пула серверов сохраняемого чата для аварийного восстановления
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
ms.openlocfilehash: 1c09231abfae7bbcc32083d7db72d8a4be79ecff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535926"
---
# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="0107a-102">Использование растянутого пула серверов сохраняемого чата для аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0107a-102">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0107a-103">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="0107a-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="0107a-104">Решение по аварийному восстановлению для сервера сохраняемого чата основано на растянутом пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="0107a-104">The disaster recovery solution for Persistent Chat Server is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="0107a-105">Эта функция аналогична устойчивости сайта на месте в Lync Server 2010; Однако для растянутой виртуальной локальной сети не требуется никаких требований.</span><span class="sxs-lookup"><span data-stu-id="0107a-105">This is similar to metropolitan site resiliency in Lync Server 2010; however, there is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="0107a-106">По мере растягиванием пула серверов сохраняемого чата вы, по сути, настраиваете один пул в топологии логически, но серверы в пуле физически размещаются в двух разных центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="0107a-106">By stretching Persistent Chat Server pool, you essentially configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="0107a-107">Настройка зеркального отображения SQL Server для базы данных аналогичным образом и развертывание базы данных и зеркальной копии в одном центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="0107a-107">Configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="0107a-108">Необходимо настроить резервную базу данных в дополнительном центре обработки данных (с дополнительным зеркалом для обеспечения высокой доступности во время аварийного восстановления).</span><span class="sxs-lookup"><span data-stu-id="0107a-108">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="0107a-109">Это резервная база данных, используемая для отработки отказа при аварийном восстановлении.</span><span class="sxs-lookup"><span data-stu-id="0107a-109">This is the backup database used for failover during disaster recovery.</span></span>

<span data-ttu-id="0107a-110">Сведения о том, как настроить зеркальное отображение SQL Server для обеспечения высокой доступности, можно найти [в разделе зеркалирование SQL Server в Lync server 2013](lync-server-2013-sql-server-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="0107a-110">For details about how to configure SQL Server mirroring for high availability, see [SQL Server mirroring in Lync Server 2013](lync-server-2013-sql-server-mirroring.md).</span></span> <span data-ttu-id="0107a-111">Сведения о том, как отработка отказа базы данных для аварийного восстановления, приведены [в статье Настройка доставки журналов SQL Server в Lync server 2013 для основной базы данных сервера сохраняемого чата](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) и [Настройка доставки журналов SQL Server между основным зеркалом и базой данных доставки журналов в Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).</span><span class="sxs-lookup"><span data-stu-id="0107a-111">For details about failing over the database for disaster recovery, see [Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) and [Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

