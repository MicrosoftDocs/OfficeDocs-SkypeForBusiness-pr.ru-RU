---
title: Настройка сервера сохраняемого чата для обеспечения высокой доступности и аварийного восстановления
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Persistent Chat Server for high availability and disaster recovery
ms:assetid: eebc581c-e3a0-4b69-8a43-80b607b4d8f2
ms:mtpsurl: https://technet.microsoft.com/library/JJ205364(v=OCS.15)
ms:contentKeyID: 48185760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90bb6ee0d9c060787c7b750046f79810aeb0c425
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532416"
---
# <a name="configuring-persistent-chat-server-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="f0c47-102">Настройка сервера сохраняемого чата для обеспечения высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0c47-102">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0c47-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f0c47-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f0c47-104">В Lync Server 2013 службы сервера сохраняемого чата используют конфигурацию *растянутого пула* для аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="f0c47-104">The Lync Server 2013, Persistent Chat Server services use a *stretched pool* configuration for disaster recovery.</span></span> <span data-ttu-id="f0c47-105">Растянутый пул — это пул, который содержит компьютеры, распределенные между двумя физическими центрами обработки данных, но которые находятся на одном логическом сайте Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0c47-105">A stretched pool is a pool that has computers that are distributed between two physical data centers, but are within a single logical Lync Server site.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f0c47-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="f0c47-106">In This Section</span></span>

  - [<span data-ttu-id="f0c47-107">Необходимые ресурсы для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0c47-107">Required resources for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-required-resources-for-persistent-chat-server.md)

  - [<span data-ttu-id="f0c47-108">Использование построителя топологий для настройки высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0c47-108">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-topology-builder-to-configure-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="f0c47-109">Использование растянутого пула серверов сохраняемого чата для аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0c47-109">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-a-stretched-persistent-chat-server-pool-for-disaster-recovery.md)

  - [<span data-ttu-id="f0c47-110">Зеркальное отображение SQL Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0c47-110">SQL Server mirroring in Lync Server 2013</span></span>](lync-server-2013-sql-server-mirroring.md)

  - [<span data-ttu-id="f0c47-111">Настройка доставки журналов SQL Server в Lync Server 2013 для основной базы данных сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f0c47-111">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)

  - [<span data-ttu-id="f0c47-112">Настройка доставки журналов SQL Server между основным зеркалом и базой данных получателя доставки журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0c47-112">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>](lync-server-2013-set-up-log-shipping-secondary-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

