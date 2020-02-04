---
title: Использование построителя топологий для настройки высокой доступности и аварийного восстановления
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73bcd2c2892e4e121512ae852d5920d600af91ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="b47a3-102">Использование построителя топологий для настройки высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b47a3-102">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b47a3-103">_**Тема последнего изменения:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="b47a3-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="b47a3-104">Выполните указанные ниже действия в построителе топологии для настройки высокой доступности и аварийного восстановления для постоянного сервера чата.</span><span class="sxs-lookup"><span data-stu-id="b47a3-104">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="b47a3-105">Добавьте зеркальные базы данных и хранилище журналов SQL Server, которые являются получателями.</span><span class="sxs-lookup"><span data-stu-id="b47a3-105">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="b47a3-106">Измените параметры службы сервера для сохраняемого чата следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b47a3-106">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="b47a3-107">Включите зеркальное отображение для базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="b47a3-107">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="b47a3-108">Добавьте основное зеркальное хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b47a3-108">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="b47a3-109">Включите базу данных доставки журналов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b47a3-109">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="b47a3-110">Добавьте хранилище журналов SQL Server с дополнительной доставкой.</span><span class="sxs-lookup"><span data-stu-id="b47a3-110">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="b47a3-111">Добавьте зеркало хранилища SQL Server для базы данных получателя.</span><span class="sxs-lookup"><span data-stu-id="b47a3-111">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="b47a3-112">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="b47a3-112">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

