---
title: 'Lync Server 2013: поддержка программного обеспечения баз данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bc8daef764ce5b15fd8c8b7e29f7031ebcfbafc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a><span data-ttu-id="a7ced-102">Поддержка программного обеспечения баз данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7ced-102">Database software support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7ced-103">_**Тема последнего изменения:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="a7ced-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="a7ced-104">Lync Server 2013 поддерживает следующие системы управления базами данных:</span><span class="sxs-lookup"><span data-stu-id="a7ced-104">Lync Server 2013 supports the following database management systems:</span></span>

  - <span data-ttu-id="a7ced-105">**Серверная база данных интерфейсного пула, база данных архивации, база данных мониторинга, база данных сохраняемого чата и база данных соответствия сохраняемого чата**</span><span class="sxs-lookup"><span data-stu-id="a7ced-105">**Back-end database of a Front End pool, Archiving database, Monitoring database, persistent chat database, and persistent chat compliance database**</span></span>
    
      - <span data-ttu-id="a7ced-p101">Программное обеспечение для баз данных Microsoft SQL Server 2008 R2 Enterprise (64-разрядная версия). Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="a7ced-p101">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="a7ced-108">Microsoft SQL Server 2008 R2 Standard (64-разрядная версия).</span><span class="sxs-lookup"><span data-stu-id="a7ced-108">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="a7ced-109">Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="a7ced-109">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="a7ced-p103">Microsoft SQL Server 2012 Enterprise (64-разрядная версия). Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="a7ced-p103">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="a7ced-p104">Microsoft SQL Server 2012 Standard (64-разрядная версия). Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="a7ced-p104">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="a7ced-114">**Базы данных сервера Standard Edition и серверного сервера переднего плана**</span><span class="sxs-lookup"><span data-stu-id="a7ced-114">**Standard Edition server database and Front End Server databases**</span></span>
    
      - <span data-ttu-id="a7ced-115">Microsoft SQL Server 2012 Express (64-разрядная версия).</span><span class="sxs-lookup"><span data-stu-id="a7ced-115">Microsoft SQL Server 2012 Express (64-bit edition).</span></span> <span data-ttu-id="a7ced-116">Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="a7ced-116">Additionally running the latest service pack is recommended.</span></span>
        
        <span data-ttu-id="a7ced-117">Мы поддерживаем обновление и обновление Microsoft SQL Server на серверах переднего и стандартном выпуске.</span><span class="sxs-lookup"><span data-stu-id="a7ced-117">We support the patching and upgrade of Microsoft SQL Server on Front End Servers and Standard Edition servers.</span></span> <span data-ttu-id="a7ced-118">Тем не менее, если вы вносите обновления или исправления на серверах переднего плана, необходимо учитывать требования кворума.</span><span class="sxs-lookup"><span data-stu-id="a7ced-118">However, when you make any kind of upgrade or patch on Front End Servers, you must account for quorum requirements.</span></span> <span data-ttu-id="a7ced-119">Подробнее см. разделы [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) и [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="a7ced-119">For more information, see [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) and [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a7ced-120">Microsoft SQL Server 2012 Express (64-bit Edition) автоматически устанавливается на Lync Server 2013 на каждом сервере Standard Edition и на каждом сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a7ced-120">Microsoft SQL Server 2012 Express (64-bit edition) is automatically installed by Lync Server 2013 on each Standard Edition server and each Front End Server server.</span></span>

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="a7ced-121">Lync Server 2013 не поддерживает 32-разрядный выпуск SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a7ced-121">Lync Server 2013 does not support the 32-bit edition of SQL Server.</span></span> <span data-ttu-id="a7ced-122">Вам следует использовать 64-разрядную версию.</span><span class="sxs-lookup"><span data-stu-id="a7ced-122">You must use the 64-bit edition.</span></span></P>
> <LI>
> <P><span data-ttu-id="a7ced-123">SQL Server Web Edition и SQL Server Workgroup Edition не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a7ced-123">SQL Server Web edition and SQL Server Workgroup edition are not supported.</span></span> <span data-ttu-id="a7ced-124">Вы не можете использовать их в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7ced-124">You cannot use them with Lync Server 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="a7ced-125">Lync Server 2013 поддерживает встроенное зеркальное отображение базы данных.</span><span class="sxs-lookup"><span data-stu-id="a7ced-125">Lync Server 2013 does support native database mirroring.</span></span></P>
> <LI>
> <P><span data-ttu-id="a7ced-126">Чтобы использовать роль сервера мониторинга, необходимо установить службы SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="a7ced-126">To use the Monitoring Server role, you should install SQL Server Reporting Services.</span></span></P></LI></UL>



</div>

<span data-ttu-id="a7ced-127">В пуле переднего плана серверная база данных может быть одним компьютером SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a7ced-127">In a Front End pool, the back-end database can be a single SQL Server computer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a7ced-128">При совместном использовании баз данных Lync Server с другими базами данных мы настоятельно рекомендуем оценить все факторы, которые могут повлиять на доступность и производительность, а также гарантируя, что если один из узлов завершается сбоем, оставшийся узел может обрабатывать загрузку.</span><span class="sxs-lookup"><span data-stu-id="a7ced-128">If you collocate Lync Server databases with other databases, we highly recommend assessing all factors that might affect availability and performance, as well as ensuring that, if one node fails, the remaining node can handle the load.</span></span> <span data-ttu-id="a7ced-129">Для проверки возможностей отработки отказа мы рекомендуем провести тестирование для всех сценариев отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="a7ced-129">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a><span data-ttu-id="a7ced-130">Использование зеркального отображения и кластеризации SQL</span><span class="sxs-lookup"><span data-stu-id="a7ced-130">Using SQL Mirroring and SQL Clustering</span></span>

<span data-ttu-id="a7ced-131">Lync Server 2013 поддерживает использование либо SQL Mirroring, либо кластеризации SQL для каждой базы данных сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a7ced-131">Lync Server 2013 supports the use of either SQL mirroring or SQL clustering for each Lync Server database.</span></span> <span data-ttu-id="a7ced-132">Зеркальное отображение SQL можно легко настроить с помощью средства Topology Builder в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7ced-132">You can easily set up SQL mirroring with the Topology Builder tool in Lync Server 2013.</span></span> <span data-ttu-id="a7ced-133">Для настройки отказоустойчивой кластеризации SQL необходимо использовать SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a7ced-133">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="a7ced-134">Lync Server 2013 поддерживает как зеркальное отражение SQL, так и топологии кластеризации SQL для всех развертываний, в том числе гринфиелд развертываний и организаций, обновленных из предыдущих версий Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a7ced-134">Lync Server 2013 supports both SQL mirroring and SQL clustering topologies for all deployments, including greenfield deployments and organizations that have upgraded from previous versions of Lync Server.</span></span>

<span data-ttu-id="a7ced-p111">Поддержка кластеризации SQL предназначена для активных и пассивных конфигураций. По соображениям производительности не следует предоставлять общий доступ к пассивному узлу для любого другого экземпляра SQL.</span><span class="sxs-lookup"><span data-stu-id="a7ced-p111">SQL Clustering support is for an active/passive configuration. For performance reasons, the passive node should not be shared by any other SQL instance.</span></span>

<span data-ttu-id="a7ced-137">Включена поддержка описанных ниже функций.</span><span class="sxs-lookup"><span data-stu-id="a7ced-137">The following support is included:</span></span>

  - <span data-ttu-id="a7ced-138">Отказоустойчивая кластеризация двух узлов для указанных ниже продуктов.</span><span class="sxs-lookup"><span data-stu-id="a7ced-138">Two-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="a7ced-p112">Microsoft SQL Server 2012 Standard (64-разрядная версия). Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="a7ced-p112">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="a7ced-p113">Microsoft SQL Server 2008 R2 Standard (64-разрядная версия). Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="a7ced-p113">Microsoft SQL Server 2008 R2 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="a7ced-143">Отказоустойчивая кластеризации для узлов количеством до шестнадцати для указанных ниже продуктов.</span><span class="sxs-lookup"><span data-stu-id="a7ced-143">Up to sixteen-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="a7ced-p114">Microsoft SQL Server 2012 Enterprise (64-разрядная версия). Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="a7ced-p114">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="a7ced-p115">Программное обеспечение для баз данных Microsoft SQL Server 2008 R2 Enterprise (64-разрядная версия). Рекомендуется установить более новый пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="a7ced-p115">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

<span data-ttu-id="a7ced-148">Дополнительные сведения о зеркальном отображении SQL можно найти в разделе о [высокой доступности сервера в Lync server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="a7ced-148">For more information about SQL mirroring, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span> <span data-ttu-id="a7ced-149">Подробнее о том, как развертывать кластеризацию SQL, можно узнать в разделе [Настройка кластеризации SQL Server для Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="a7ced-149">For details on how to deploy SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<span data-ttu-id="a7ced-150">Дополнительные сведения и рекомендации по работе с отказоустойчивой кластеризацией в SQL Server 2012 можно <http://technet.microsoft.com/en-us/library/hh231721.aspx>найти в разделе.</span><span class="sxs-lookup"><span data-stu-id="a7ced-150">For more information and best practices for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/en-us/library/hh231721.aspx>.</span></span> <span data-ttu-id="a7ced-151">Сведения об отказоустойчивой кластеризации в SQL Server 2008 <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>можно найти в разделе.</span><span class="sxs-lookup"><span data-stu-id="a7ced-151">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

