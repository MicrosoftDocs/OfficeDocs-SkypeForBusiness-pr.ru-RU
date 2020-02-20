---
title: 'Lync Server 2013: необходимые ресурсы для сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f59c2d368a9ea94fdd79a6aa0466313ddc43993
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="cfeec-102">Необходимые ресурсы для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfeec-102">Required resources for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfeec-103">_**Последнее изменение темы:** 2016-02-05_</span><span class="sxs-lookup"><span data-stu-id="cfeec-103">_**Topic Last Modified:** 2016-02-05_</span></span>

<span data-ttu-id="cfeec-104">Высокая доступность и аварийное восстановление для сервера сохраняемого чата требует дополнительных ресурсов помимо тех, которые обычно необходимы для выполнения полной операции.</span><span class="sxs-lookup"><span data-stu-id="cfeec-104">High availability and disaster recovery for Persistent Chat Server requires additional resources beyond what is typically needed for full operation.</span></span> <span data-ttu-id="cfeec-105">Перед настройкой сервера сохраняемого чата для обеспечения высокой доступности и аварийного восстановления убедитесь, что у вас есть следующие ресурсы в дополнение к тому, что требуется для стандартной операции сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cfeec-105">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following resources in addition to what is required for standard Persistent Chat Server operation.</span></span> <span data-ttu-id="cfeec-106">Дополнительные сведения о конфигурации приведены [в разделе Настройка сервера сохраняемого чата в Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="cfeec-106">For additional configuration information, see [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span></span>

  - <span data-ttu-id="cfeec-107">Один выделенный экземпляр базы данных, расположенный в том же физическом центре обработки данных, в котором размещается домашний интерфейс службы сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cfeec-107">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="cfeec-108">Эта база данных будет служить зеркалом SQL Server для основной базы данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cfeec-108">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="cfeec-109">При необходимости назначьте дополнительный SQL Server для использования в качестве следящего сервера, если требуется автоматическая отработка отказа для зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="cfeec-109">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>

  - <span data-ttu-id="cfeec-110">Один выделенный экземпляр базы данных, расположенный в другом физическом центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="cfeec-110">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="cfeec-111">Эта база данных будет выступать в качестве дополнительной базы данных доставки журналов SQL Server для базы данных в основном центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="cfeec-111">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>

  - <span data-ttu-id="cfeec-112">Один выделенный экземпляр базы данных для использования в качестве зеркала SQL Server для базы данных получателя.</span><span class="sxs-lookup"><span data-stu-id="cfeec-112">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="cfeec-113">При необходимости назначьте дополнительный сервер SQL Server в качестве следящего сервера зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="cfeec-113">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="cfeec-114">Обе базы данных должны быть расположены в одном физическом центре обработки данных в качестве базы данных-получателя.</span><span class="sxs-lookup"><span data-stu-id="cfeec-114">Both of these must be located in the same physical data center as the secondary database.</span></span>

  - <span data-ttu-id="cfeec-115">Если включено соответствие сервера сохраняемого чата, требуются дополнительные три выделенных экземпляра базы данных.</span><span class="sxs-lookup"><span data-stu-id="cfeec-115">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="cfeec-116">Их распространение выполняется так же, как и для базы данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cfeec-116">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="cfeec-117">Несмотря на то, что база данных соответствия может совместно использовать тот же экземпляр SQL Server, что и база данных сохраняемого чата, рекомендуется использовать отдельные экземпляры для обеспечения высокой доступности и аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="cfeec-117">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, we recommend standalone instances for high availability and disaster recovery.</span></span>

  - <span data-ttu-id="cfeec-118">Необходимо создать общий файловый ресурс для журналов транзакций доставки журналов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cfeec-118">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="cfeec-119">Все серверы SQL в обоих центрах обработки данных, которые запускают базы данных сохраняемого чата, должны иметь доступ на чтение и запись к этому общему файловому ресурсу.</span><span class="sxs-lookup"><span data-stu-id="cfeec-119">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="cfeec-120">Этот файловый ресурс не задается как часть роли хранилища файлов.</span><span class="sxs-lookup"><span data-stu-id="cfeec-120">This share is not defined as part of a FileStore role.</span></span>

  - <span data-ttu-id="cfeec-121">Файловый ресурс на дополнительном сервере баз данных, который будет служить папкой назначения для журналов транзакций SQL Server, которые копируются из общего файлового ресурса основного сервера.</span><span class="sxs-lookup"><span data-stu-id="cfeec-121">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cfeec-122">Активные серверы сохраняемого чата в пуле серверов сохраняемого чата должны находиться в том же часовом поясе, что и пул Lync следующего прыжка, определенный в топологии.</span><span class="sxs-lookup"><span data-stu-id="cfeec-122">Active Persistent Chat servers in a Persistent Chat Server pool MUST reside in the same time zone as the next hop Lync Pool defined in the topology.</span></span>



</div>

<span data-ttu-id="cfeec-123">На следующих рисунках представлены примеры того, как можно настроить весь пул серверов сохраняемого чата в двух разных топологиях растянутого пула:</span><span class="sxs-lookup"><span data-stu-id="cfeec-123">The following figures provide examples about how the entire Persistent Chat Server pool can be configured in the two different stretched pool topologies:</span></span>

  - <span data-ttu-id="cfeec-124">Растянутый пул серверов сохраняемого чата для территориально-распределенных центров обработки данных с высокой пропускной способностью и небольшой задержкой</span><span class="sxs-lookup"><span data-stu-id="cfeec-124">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>

  - <span data-ttu-id="cfeec-125">Растянутый пул серверов сохраняемого чата для территориально-распределенных центров обработки данных с низкой пропускной способностью и большой задержкой</span><span class="sxs-lookup"><span data-stu-id="cfeec-125">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="cfeec-126">На следующем рисунке показана топология с растянутым пулом серверов сохраняемого чата, в которой центры обработки данных географически расположены с высокой пропускной способностью и небольшой задержкой.</span><span class="sxs-lookup"><span data-stu-id="cfeec-126">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span>

<span data-ttu-id="cfeec-127">**Растянутый пул серверов сохраняемого чата для территориально-распределенных центров обработки данных с высокой пропускной способностью и небольшой задержкой**</span><span class="sxs-lookup"><span data-stu-id="cfeec-127">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.**</span></span>

<span data-ttu-id="cfeec-128">![Экзамен по настройке пула серверов сохраняемого чата ХБВ](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Экзамен по настройке пула серверов сохраняемого чата ХБВ")</span><span class="sxs-lookup"><span data-stu-id="cfeec-128">![Persistent Chat Server pool HBW configuration exam](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server pool HBW configuration exam")</span></span>

<span data-ttu-id="cfeec-129">На следующем рисунке показана топология с растянутым пулом серверов сохраняемого чата, где центры обработки данных расположены географически с низкой пропускной способностью и высокой задержкой.</span><span class="sxs-lookup"><span data-stu-id="cfeec-129">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="cfeec-130">**Растянутый пул серверов сохраняемого чата для территориально-распределенных центров обработки данных с низкой пропускной способностью и большой задержкой**</span><span class="sxs-lookup"><span data-stu-id="cfeec-130">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.**</span></span>

<span data-ttu-id="cfeec-131">![Экзамен по настройке пула серверов сохраняемого чата ЛБВ](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Экзамен по настройке пула серверов сохраняемого чата ЛБВ")</span><span class="sxs-lookup"><span data-stu-id="cfeec-131">![Persistent Chat Server pool LBW configuration exam](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server pool LBW configuration exam")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

