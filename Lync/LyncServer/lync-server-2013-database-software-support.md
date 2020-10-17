---
title: Поддержка программного обеспечения баз данных Lync Server 2013
description: Поддержка программного обеспечения баз данных Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c5d7b44e5febc4123dbcdf7072b98fcfd004609
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558155"
---
# <a name="database-software-support-in-lync-server-2013"></a><span data-ttu-id="74cf4-103">Поддержка программного обеспечения баз данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74cf4-103">Database software support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74cf4-104">_**Последнее изменение темы:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="74cf4-104">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="74cf4-105">Lync Server 2013 поддерживает следующие системы управления базами данных:</span><span class="sxs-lookup"><span data-stu-id="74cf4-105">Lync Server 2013 supports the following database management systems:</span></span>

  - <span data-ttu-id="74cf4-106">**Серверная база данных интерфейсного пула, база данных архивации, база данных мониторинга, база данных сохраняемого чата и база данных соответствия сохраняемого чата**</span><span class="sxs-lookup"><span data-stu-id="74cf4-106">**Back-end database of a Front End pool, Archiving database, Monitoring database, persistent chat database, and persistent chat compliance database**</span></span>
    
      - <span data-ttu-id="74cf4-p101">Программное обеспечение для баз данных Microsoft SQL Server 2008 R2 Enterprise (64-разрядная версия). Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="74cf4-p101">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="74cf4-p102">Microsoft SQL Server 2008 R2 Standard (64-разрядная версия). Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="74cf4-p102">Microsoft SQL Server 2008 R2 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="74cf4-p103">Microsoft SQL Server 2012 Enterprise (64-разрядная версия). Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="74cf4-p103">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="74cf4-p104">Microsoft SQL Server 2012 Standard (64-разрядная версия). Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="74cf4-p104">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="74cf4-115">**Базы данных сервера Standard Edition и сервера переднего плана**</span><span class="sxs-lookup"><span data-stu-id="74cf4-115">**Standard Edition server database and Front End Server databases**</span></span>
    
      - <span data-ttu-id="74cf4-116">Microsoft SQL Server 2012 Express (64-разрядный выпуск).</span><span class="sxs-lookup"><span data-stu-id="74cf4-116">Microsoft SQL Server 2012 Express (64-bit edition).</span></span> <span data-ttu-id="74cf4-117">Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="74cf4-117">Additionally running the latest service pack is recommended.</span></span>
        
        <span data-ttu-id="74cf4-118">Мы поддерживаем обновление и обновление Microsoft SQL Server на серверах переднего плана и серверах Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="74cf4-118">We support the patching and upgrade of Microsoft SQL Server on Front End Servers and Standard Edition servers.</span></span> <span data-ttu-id="74cf4-119">Однако при любом типе обновления или исправления на серверах переднего плана необходимо учитывать требования к кворуму.</span><span class="sxs-lookup"><span data-stu-id="74cf4-119">However, when you make any kind of upgrade or patch on Front End Servers, you must account for quorum requirements.</span></span> <span data-ttu-id="74cf4-120">Для получения дополнительных сведений см. [обновление или обновление серверов переднего плана в Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) и [топологиях и компонентах для серверов переднего плана, обмена мгновенными сообщениями и сведений о присутствии в Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="74cf4-120">For more information, see [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) and [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74cf4-121">Microsoft SQL Server 2012 Express (64-разрядная версия) автоматически устанавливается в Lync Server 2013 на каждом сервере Standard Edition и на каждом сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="74cf4-121">Microsoft SQL Server 2012 Express (64-bit edition) is automatically installed by Lync Server 2013 on each Standard Edition server and each Front End Server server.</span></span>

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="74cf4-122">Lync Server 2013 не поддерживает 32 — разрядный выпуск SQL Server.</span><span class="sxs-lookup"><span data-stu-id="74cf4-122">Lync Server 2013 does not support the 32-bit edition of SQL Server.</span></span> <span data-ttu-id="74cf4-123">Вам следует использовать 64-разрядную версию.</span><span class="sxs-lookup"><span data-stu-id="74cf4-123">You must use the 64-bit edition.</span></span></P>
> <LI>
> <P><span data-ttu-id="74cf4-124">SQL Server Web Edition и SQL Server Workgroup Edition не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="74cf4-124">SQL Server Web edition and SQL Server Workgroup edition are not supported.</span></span> <span data-ttu-id="74cf4-125">Вы не можете использовать их с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74cf4-125">You cannot use them with Lync Server 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="74cf4-126">Lync Server 2013 поддерживает встроенное зеркальное отображение баз данных.</span><span class="sxs-lookup"><span data-stu-id="74cf4-126">Lync Server 2013 does support native database mirroring.</span></span></P>
> <LI>
> <P><span data-ttu-id="74cf4-127">Чтобы использовать роль сервера мониторинга, необходимо установить службы SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="74cf4-127">To use the Monitoring Server role, you should install SQL Server Reporting Services.</span></span></P></LI></UL>



</div>

<span data-ttu-id="74cf4-128">В интерфейсном пуле серверная база данных может быть одним компьютером SQL Server.</span><span class="sxs-lookup"><span data-stu-id="74cf4-128">In a Front End pool, the back-end database can be a single SQL Server computer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="74cf4-129">При совместном размещении баз данных Lync Server с другими базами данных мы настоятельно рекомендуем оценить все факторы, которые могут повлиять на доступность и производительность, а также гарантируя, что при сбое одного узла оставшийся узел может обработать нагрузку.</span><span class="sxs-lookup"><span data-stu-id="74cf4-129">If you collocate Lync Server databases with other databases, we highly recommend assessing all factors that might affect availability and performance, as well as ensuring that, if one node fails, the remaining node can handle the load.</span></span> <span data-ttu-id="74cf4-130">Чтобы проверить возможности аварийного переключения, рекомендуется протестировать все сценарии аварийного переключения.</span><span class="sxs-lookup"><span data-stu-id="74cf4-130">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a><span data-ttu-id="74cf4-131">Использование зеркального отображения SQL и кластеризации SQL</span><span class="sxs-lookup"><span data-stu-id="74cf4-131">Using SQL Mirroring and SQL Clustering</span></span>

<span data-ttu-id="74cf4-132">Lync Server 2013 поддерживает использование зеркального отображения SQL или кластеризации SQL для каждой базы данных Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74cf4-132">Lync Server 2013 supports the use of either SQL mirroring or SQL clustering for each Lync Server database.</span></span> <span data-ttu-id="74cf4-133">Зеркальное отображение SQL можно легко настроить с помощью средства "Построитель топологий" в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74cf4-133">You can easily set up SQL mirroring with the Topology Builder tool in Lync Server 2013.</span></span> <span data-ttu-id="74cf4-134">Для установки отказоустойчивой кластеризации SQL необходимо использовать SQL Server.</span><span class="sxs-lookup"><span data-stu-id="74cf4-134">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="74cf4-135">Lync Server 2013 поддерживает как зеркальное отображение SQL, так и топологию кластеризации SQL для всех развертываний, включая нуля развертывания и организации, обновленные с предыдущих версий Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74cf4-135">Lync Server 2013 supports both SQL mirroring and SQL clustering topologies for all deployments, including greenfield deployments and organizations that have upgraded from previous versions of Lync Server.</span></span>

<span data-ttu-id="74cf4-136">Поддержка кластеризации SQL для активной и пассивной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="74cf4-136">SQL Clustering support is for an active/passive configuration.</span></span> <span data-ttu-id="74cf4-137">В целях повышения производительности пассивный узел не должен совместно использоваться любым другим экземпляром SQL.</span><span class="sxs-lookup"><span data-stu-id="74cf4-137">For performance reasons, the passive node should not be shared by any other SQL instance.</span></span>

<span data-ttu-id="74cf4-138">Включена следующая поддержка:</span><span class="sxs-lookup"><span data-stu-id="74cf4-138">The following support is included:</span></span>

  - <span data-ttu-id="74cf4-139">Отказоустойчивая кластеризация с двумя узлами для следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="74cf4-139">Two-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="74cf4-140">Microsoft SQL Server 2012 Standard (64-разрядная версия).</span><span class="sxs-lookup"><span data-stu-id="74cf4-140">Microsoft SQL Server 2012 Standard (64-bit edition).</span></span> <span data-ttu-id="74cf4-141">Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="74cf4-141">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="74cf4-142">Microsoft SQL Server 2008 R2 Standard (64-разрядная версия).</span><span class="sxs-lookup"><span data-stu-id="74cf4-142">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="74cf4-143">Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="74cf4-143">Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="74cf4-144">Отказоустойчивая кластеризация на шестнадцать узлов для следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="74cf4-144">Up to sixteen-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="74cf4-145">Microsoft SQL Server 2012 Enterprise (64-разрядная версия).</span><span class="sxs-lookup"><span data-stu-id="74cf4-145">Microsoft SQL Server 2012 Enterprise (64-bit edition).</span></span> <span data-ttu-id="74cf4-146">Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="74cf4-146">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="74cf4-147">Программное обеспечение для баз данных Microsoft SQL Server 2008 R2 Enterprise (64-разрядная версия).</span><span class="sxs-lookup"><span data-stu-id="74cf4-147">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition).</span></span> <span data-ttu-id="74cf4-148">Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="74cf4-148">Additionally running the latest service pack is recommended.</span></span>

<span data-ttu-id="74cf4-149">Для получения дополнительных сведений о зеркальном отображении SQL ознакомьтесь со статьей [Высокая доступность внутреннего сервера в Lync server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="74cf4-149">For more information about SQL mirroring, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span> <span data-ttu-id="74cf4-150">Подробнее о развертывании SQL кластеризации можно узнать в статье [Настройка кластеризации SQL Server для Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="74cf4-150">For details on how to deploy SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<span data-ttu-id="74cf4-151">Дополнительные сведения и рекомендации по обеспечению отказоустойчивости кластеров в SQL Server 2012 приведены в разделе <https://technet.microsoft.com/library/hh231721.aspx> .</span><span class="sxs-lookup"><span data-stu-id="74cf4-151">For more information and best practices for failover clustering in SQL Server 2012, see <https://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="74cf4-152">Сведения об отказоустойчивой кластеризации в SQL Server 2008 см <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> .</span><span class="sxs-lookup"><span data-stu-id="74cf4-152">For failover clustering in SQL Server 2008, see <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

