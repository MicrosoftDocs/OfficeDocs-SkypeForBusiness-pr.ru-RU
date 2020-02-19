---
title: 'Lync Server 2013: компоненты и топологии для мониторинга'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d93920040ff18d623748b375849f5639a831772a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="30acb-102">Компоненты и топологии для мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30acb-102">Components and topologies for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30acb-103">_**Последнее изменение темы:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="30acb-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="30acb-104">Поскольку агенты сбора универсальных данных автоматически устанавливаются и активируются на каждом сервере переднего плана, не требуется настраивать сервер для работы в качестве сервера мониторинга; каждый сервер переднего плана уже функционирует как сервер мониторинга.</span><span class="sxs-lookup"><span data-stu-id="30acb-104">Because the unified data collection agents are automatically installed and activated on each Front End server you do not need to configure a server to act as the Monitoring server; each Front End server already functions as a Monitoring server.</span></span> <span data-ttu-id="30acb-105">Однако потребуется установить и настроить базу данных для работы в качестве внутреннего хранилища данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="30acb-105">However, you will need to install and configure a database to act as the backend data store for your monitoring data.</span></span> <span data-ttu-id="30acb-106">Microsoft Lync Server 2013 может использовать любую из следующих баз данных в качестве серверного хранилища для мониторинга.</span><span class="sxs-lookup"><span data-stu-id="30acb-106">Microsoft Lync Server 2013 can use any of the following databases as the backend store for monitoring:</span></span>

  - <span data-ttu-id="30acb-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="30acb-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span></span>

  - <span data-ttu-id="30acb-108">Microsoft SQL Server 2008 R2 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="30acb-108">Microsoft SQL Server 2008 R2 Standard Edition</span></span>

  - <span data-ttu-id="30acb-109">Microsoft SQL Server 2012 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="30acb-109">Microsoft SQL Server 2012 Enterprise Edition</span></span>

  - <span data-ttu-id="30acb-110">Microsoft SQL Server 2012 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="30acb-110">Microsoft SQL Server 2012 Standard Edition</span></span>

<span data-ttu-id="30acb-111">Обратите внимание, что вы должны использовать 64-разрядные выпуски этих баз данных; 32-разрядные выпуски SQL Server не могут использоваться в качестве внутреннего хранилища данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="30acb-111">Note that you must use the 64-bit editions of these databases; 32-bit versions of SQL Server cannot be used as the backend store for monitoring.</span></span> <span data-ttu-id="30acb-112">Аналогично, Lync Server 2013 не поддерживает Экспресс выпуски SQL Server 2008 или SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="30acb-112">Likewise, Lync Server 2013 does not support the Express Editions of SQL Server 2008 or SQL Server 2012.</span></span> <span data-ttu-id="30acb-113">Дополнительные сведения о требованиях к базе данных для Lync Server 2013 приведены в статье [Поддержка программного обеспечения баз данных в Lync server 2013](lync-server-2013-database-software-support.md) в руководстве по поддержке lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30acb-113">For more information on database requirements for Lync Server 2013 see the topic [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Lync Server 2013 Supportability guide.</span></span>

<span data-ttu-id="30acb-114">Помните, что SQL Server необходимо установить и настроить до развертывания и настройки мониторинга.</span><span class="sxs-lookup"><span data-stu-id="30acb-114">Keep in mind that SQL Server must be installed and configured before you deploy and configure monitoring.</span></span> <span data-ttu-id="30acb-115">Однако достаточно развернуть сам SQL Server; не нужно заранее настраивать базы данных наблюдения.</span><span class="sxs-lookup"><span data-stu-id="30acb-115">However, you only need to deploy SQL Server itself; you do not have to setup the monitoring databases in advance.</span></span> <span data-ttu-id="30acb-116">Вместо этого эти базы данных будут автоматически созданы при публикации топологии Lync Server.</span><span class="sxs-lookup"><span data-stu-id="30acb-116">Instead, those databases will automatically be created for you when you publish your Lync Server topology.</span></span>

<span data-ttu-id="30acb-p104">Данные наблюдения могут совместно использовать экземпляр SQL Server с другими типами данных. Обычно база данных регистрации вызовов (LcsCdr) и база данных качества взаимодействия (QoEMetrics) совместно используют один экземпляр SQL; также распространены случаи, когда две базы данных мониторинга находятся в одном экземпляре SQL с базой данных архивации (LcsLog). Единственное реальное требование к экземплярам SQL Server заключается в том, что каждый экземпляр SQL Server должен иметь следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="30acb-p104">Monitoring data can share a SQL Server instance with other types of data. Typically, the call detail recording database (LcsCdr) and the Quality of Experience database (QoEMetrics) share the same SQL instance; it is also common for the two monitoring databases to be in the same SQL instance as the archiving database (LcsLog). About the only real requirement with SQL Server instances is that any one instance of SQL Server is limited to the following:</span></span>

  - <span data-ttu-id="30acb-120">Один экземпляр внутренней базы данных Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30acb-120">One instance of the Lync Server 2013 backend database.</span></span> <span data-ttu-id="30acb-121">(Как правило, не рекомендуется, чтобы база данных мониторинга размещалась в том же экземпляре SQL или даже на том же компьютере, что и внутренняя база данных.</span><span class="sxs-lookup"><span data-stu-id="30acb-121">(As a general rule, it is not recommended that your monitoring database be collocated in the same SQL instance, or even on the same computer, as the backend database.</span></span> <span data-ttu-id="30acb-122">Хотя технически это возможно, существует риск того, что база данных мониторинга займет пространство диска, необходимое для внутренней базы данных.)</span><span class="sxs-lookup"><span data-stu-id="30acb-122">Although technically possible, you run the risk of the monitoring database using up disk space needed by the backend database.)</span></span>

  - <span data-ttu-id="30acb-123">Один экземпляр базы данных регистрации вызовов.</span><span class="sxs-lookup"><span data-stu-id="30acb-123">One instance of the call detail recording database.</span></span>

  - <span data-ttu-id="30acb-124">Один экземпляр базы данных качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="30acb-124">One instance of the Quality of Experience database.</span></span>

  - <span data-ttu-id="30acb-125">Один экземпляр базы данных архивации.</span><span class="sxs-lookup"><span data-stu-id="30acb-125">One instance of the archiving database.</span></span>

<span data-ttu-id="30acb-p106">Другими словами, нельзя иметь два экземпляра базы данных LcsCdr в одном экземпляре SQL Server. Если требуется несколько экземпляров базы данных LcsCdr, придется настроить несколько экземпляров SQL Server.</span><span class="sxs-lookup"><span data-stu-id="30acb-p106">In other words, you cannot have two instances of the LcsCdr database in the same instance of SQL Server. If you need multiple instances of the LcsCdr database then you will need to configure multiple instances of SQL Server.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="30acb-128">См. также</span><span class="sxs-lookup"><span data-stu-id="30acb-128">See Also</span></span>


[<span data-ttu-id="30acb-129">Развертывание мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30acb-129">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

