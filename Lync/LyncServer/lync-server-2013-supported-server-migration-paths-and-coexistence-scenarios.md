---
title: 'Lync Server 2013: Поддерживаемые пути миграции серверов и сценарии сосуществования'
description: 'Lync Server 2013: Поддерживаемые пути миграции серверов и сценарии сосуществования.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44d0a40ac6cc6570cf79b56dc896277c83909b5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560235"
---
# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a><span data-ttu-id="a9cf2-103">Поддерживаемые пути миграции и сценарии сосуществования серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9cf2-103">Supported server migration paths and coexistence scenarios in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9cf2-104">_**Последнее изменение темы:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="a9cf2-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="a9cf2-105">Lync Server 2013 поддерживает миграцию из одного из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="a9cf2-105">Lync Server 2013 supports migration from either of the following:</span></span>

  - <span data-ttu-id="a9cf2-106">Microsoft Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a9cf2-106">Microsoft Lync Server 2010</span></span>

  - <span data-ttu-id="a9cf2-107">Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="a9cf2-107">Microsoft Office Communications Server 2007 R2</span></span>

<span data-ttu-id="a9cf2-108">Миграция из среды, где запущены обе эти предыдущие версии, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-108">Migration from an environment running both of these previous versions is not supported.</span></span> <span data-ttu-id="a9cf2-109">Миграция с более ранних версий, например, Microsoft Office Communications Server 2007 или Live Communications Server 2005, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-109">Migration from earlier versions, such as Microsoft Office Communications Server 2007 or Live Communications Server 2005, is not supported.</span></span> <span data-ttu-id="a9cf2-110">Если предыдущее развертывание включало групповой чат, его необходимо перенести отдельно.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-110">If your previous deployment included Group Chat, you must migrate it separately.</span></span>

<div>

## <a name="migration-methods"></a><span data-ttu-id="a9cf2-111">Способы миграции</span><span class="sxs-lookup"><span data-stu-id="a9cf2-111">Migration Methods</span></span>

<span data-ttu-id="a9cf2-112">Поддерживается миграция всех топологий Lync Server и ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-112">Migration of all Lync Server topologies and server roles is supported.</span></span> <span data-ttu-id="a9cf2-113">Вы можете выполнять миграцию с одной топологии на другую, включая миграцию с сервера Standard Edition на сервер Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-113">You can migrate from one topology to a different topology, including from Standard Edition server to Enterprise Edition server.</span></span>

<span data-ttu-id="a9cf2-114">Lync Server 2013 поддерживает только следующий метод миграции:</span><span class="sxs-lookup"><span data-stu-id="a9cf2-114">Lync Server 2013 supports only the following migration method:</span></span>

  - <span></span>  
    <span data-ttu-id="a9cf2-115">**Параллельная миграция.**</span><span class="sxs-lookup"><span data-stu-id="a9cf2-115">**Side-by-side migration.**</span></span> <span data-ttu-id="a9cf2-116">При параллельной миграции Lync Server 2013 разворачивается вместе с существующим развертыванием Microsoft Lync Server 2010 или Office Communications Server 2007 R2, а затем выполняется передача операций на новые серверы и перемещение пользователей на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-116">In side-by-side migration, Lync Server 2013 is deployed alongside an existing Microsoft Lync Server 2010 or Office Communications Server 2007 R2 deployment, and then you transfer operations to the new servers and move users to Lync Server 2013.</span></span> <span data-ttu-id="a9cf2-117">При использовании этого способа миграции требуются дополнительные серверные платформы, включая оборудование и программное обеспечение, а имена систем и пулов в новой конфигурации отличаются.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-117">This method requires additional server platforms, including hardware and software, during migration, and system names and pool names are different in the new configuration.</span></span> <span data-ttu-id="a9cf2-118">Если требуется выполнить откат до предыдущей версии, операции можно перенести обратно на предыдущие серверы.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-118">If it becomes necessary to roll back to the previous version, you can shift operations back to the previous servers.</span></span>

<span data-ttu-id="a9cf2-119">Миграция между лесами доменных служб Active Directory не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-119">Migration across Active Directory Domain Services forests is not supported.</span></span>

<span data-ttu-id="a9cf2-p104">Рекомендуемый путь миграции представляет собой поэтапный подход. Дополнительные сведения о миграции с предыдущего выпуска, включая правильное разделение развертывания компонентов на этапы, см. в следующих разделах документации по миграции:</span><span class="sxs-lookup"><span data-stu-id="a9cf2-p104">The recommended migration path is a phased approach. For details about migrating from a previous release, including the appropriate phasing of component deployment, see the following topics in the Migration documentation:</span></span>

  - [<span data-ttu-id="a9cf2-122">Миграция с Lync Server 2010 на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9cf2-122">Migration from Lync Server 2010 to Lync Server 2013</span></span>](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [<span data-ttu-id="a9cf2-123">Миграция с Office Communications Server 2007 R2 на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9cf2-123">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [<span data-ttu-id="a9cf2-124">Миграция с групповой беседы в Lync Server 2010 или Office Communications Server 2007 R2 на сервер сохраняемого сеанса беседы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9cf2-124">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a><span data-ttu-id="a9cf2-125">Сценарии сосуществования</span><span class="sxs-lookup"><span data-stu-id="a9cf2-125">Coexistence Scenarios</span></span>

<span data-ttu-id="a9cf2-126">Lync Server 2013 может сосуществовать с компонентами или развертыванием Lync Server 2010 или Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-126">Lync Server 2013 can coexist with components of either a Lync Server 2010 deployment or an Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="a9cf2-127">Параллельное развертывание Lync Server 2013 со средой Lync Server 2010 и Office Communications Server 2007 R2 (параллельное развертывание всех трех версий) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-127">Concurrent deployment of Lync Server 2013 with both Lync Server 2010 and Office Communications Server 2007 R2 (concurrent deployment of all three versions) is not supported.</span></span>

<span data-ttu-id="a9cf2-128">При поэтапной миграции, когда предыдущее развертывание Lync Server 2010 или Office Communications Server 2007 R2 временно существует с новым развертыванием Lync Server 2013, поддержка маршрутизации смешанных версий ограничена.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-128">During a phased migration in which a previous Lync Server 2010 or Office Communications Server 2007 R2 deployment coexists temporarily with the new Lync Server 2013 deployment, support for mixed version routing is limited.</span></span> <span data-ttu-id="a9cf2-129">Дополнительные сведения см. в документации по миграции.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-129">For details, see the Migration documentation.</span></span>

<span data-ttu-id="a9cf2-130">Для экземпляров базы данных Lync Server 2013 необходимо использовать отдельные и разные компьютеры, на которых работает Microsoft SQL Server 2008 R2 или Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-130">You must use separate and distinct computers running Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for your Lync Server 2013 database instances.</span></span> <span data-ttu-id="a9cf2-131">Нельзя использовать один и тот же экземпляр SQL Server для интерфейсного пула Lync Server 2013, который используется для интерфейсного пула Lync Server 2010 или Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-131">You cannot use the same instance of SQL Server for a Lync Server 2013 Front End pool that you use for a Lync Server 2010 or Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="a9cf2-132">Если вы определили и настроили Lync Server 2013 в построителе топологий для развертывания, в котором уже есть Lync Server 2010 или Office Communications Server 2007 R2, построитель топологий не позволит определить экземпляр сервера Lync Server 2013, который уже используется в топологии.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-132">If you define and configure Lync Server 2013 in Topology Builder for a deployment that already has Lync Server 2010 or Office Communications Server 2007 R2 deployed, Topology Builder will not allow you to define an instance of a Lync Server 2013 that is already in use in the topology.</span></span>

<span data-ttu-id="a9cf2-133">В построителе топологий отобразится следующее сообщение об этой ошибке: " \[ полное доменное имя SQL Server \] уже содержит роль размещения экземпляра SQL" хранилище пользователей ".</span><span class="sxs-lookup"><span data-stu-id="a9cf2-133">Topology Builder will display the following message to inform you of this issue: "The SQL server \[FQDN of the server\] already contains a SQL instance hosting role 'User Store."</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a9cf2-134">Если вы планируете развертывать роли сервера, которые являются новыми для развертывания Lync Server 2013, необходимо сначала обновить существующее развертывание, как описано в документации по миграции и в документации по развертыванию, а затем развернуть новые роли сервера, как описано в документации по планированию и документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-134">If you intend to deploy server roles that are new to your Lync Server 2013 deployment, you should first upgrade your existing deployment as described in the Migration documentation and the Deployment documentation, and then deploy the new server roles as described in the Planning documentation and Deployment documentation.</span></span> <span data-ttu-id="a9cf2-135">Если вы переносите предыдущую версию группового чата, перенесите ее последним, после завершения процесса переноса всех остальных компонентов с Lync Server 2010 или Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-135">If you are migrating a previous version of Group Chat, migrate it last, after completing the process for migrating all other components from Lync Server 2010 or Office Communications Server 2007 R2.</span></span>



</div>

<span data-ttu-id="a9cf2-136">Сведения о специальных требованиях к сосуществованию и других сведениях о сосуществовании и переносе компонентов Lync Server 2010 или Office Communications Server 2007 R2 и Lync Server 2013 приведены в статье [Миграция с Lync server 2010 to Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) и [Миграция с Office Communications Server 2007 R2 на Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) в документации по миграции.</span><span class="sxs-lookup"><span data-stu-id="a9cf2-136">For specific coexistence requirements and other details about coexistence and migration of Lync Server 2010 or Office Communications Server 2007 R2 and Lync Server 2013 components, see [Migration from Lync Server 2010 to Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) and [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) in the Migration documentation.</span></span> <span data-ttu-id="a9cf2-137">Подробные сведения о поддержке разных версий для клиентов приведены [в статье Поддерживаемые клиенты из предыдущих развертываний в Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="a9cf2-137">For details about mixed version support for clients, see [Supported clients from previous deployments in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

