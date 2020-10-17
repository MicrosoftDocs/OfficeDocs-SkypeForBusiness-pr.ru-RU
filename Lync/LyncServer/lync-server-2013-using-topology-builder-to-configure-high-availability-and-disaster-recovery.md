---
title: Использование построителя топологий для настройки высокой доступности и аварийного восстановления
description: Использование построителя топологий для настройки высокой доступности и аварийного восстановления.
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
ms.openlocfilehash: 04764a58ac3ae1bbe0df97aadeabb03158ce8100
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547325"
---
# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="540e6-103">Использование построителя топологий для настройки высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="540e6-103">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="540e6-104">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="540e6-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="540e6-105">Выполните указанные ниже действия в построителе топологий, чтобы настроить высокую доступность и аварийное восстановление для сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="540e6-105">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="540e6-106">Добавьте зеркальные базы данных и хранилища SQL Server, которые являются вторичными хранилищами баз данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="540e6-106">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="540e6-107">Измените свойства службы сервера сохраняемого чата следующим образом:</span><span class="sxs-lookup"><span data-stu-id="540e6-107">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="540e6-108">Включите зеркальное отображение для базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="540e6-108">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="540e6-109">Добавьте основное зеркальное хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="540e6-109">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="540e6-110">Включите базу данных доставки журналов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="540e6-110">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="540e6-111">Добавьте дополнительное хранилище SQL Server для доставки журналов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="540e6-111">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="540e6-112">Добавьте зеркало хранилища SQL Server для базы данных получателя.</span><span class="sxs-lookup"><span data-stu-id="540e6-112">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="540e6-113">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="540e6-113">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

