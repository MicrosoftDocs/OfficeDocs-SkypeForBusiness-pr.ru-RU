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
ms.openlocfilehash: 75117cd8a88b5ff5f333457033b5af49c5464f53
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42116732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="8bc57-102">Использование построителя топологий для настройки высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bc57-102">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bc57-103">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="8bc57-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="8bc57-104">Выполните указанные ниже действия в построителе топологий, чтобы настроить высокую доступность и аварийное восстановление для сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="8bc57-104">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="8bc57-105">Добавьте зеркальные базы данных и хранилища SQL Server, которые являются вторичными хранилищами баз данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8bc57-105">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="8bc57-106">Измените свойства службы сервера сохраняемого чата следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8bc57-106">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="8bc57-107">Включите зеркальное отображение для базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="8bc57-107">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="8bc57-108">Добавьте основное зеркальное хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8bc57-108">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="8bc57-109">Включите базу данных доставки журналов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8bc57-109">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="8bc57-110">Добавьте дополнительное хранилище SQL Server для доставки журналов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8bc57-110">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="8bc57-111">Добавьте зеркало хранилища SQL Server для базы данных получателя.</span><span class="sxs-lookup"><span data-stu-id="8bc57-111">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="8bc57-112">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="8bc57-112">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

