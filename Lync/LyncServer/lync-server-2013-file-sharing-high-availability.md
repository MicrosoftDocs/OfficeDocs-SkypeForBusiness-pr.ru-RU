---
title: 'Lync Server 2013: высокая доступность общего доступа к файлам'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf27a7316494d24127f65309bdef347b558fade5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a><span data-ttu-id="a75c8-102">Высокая доступность общего доступа к файлам в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a75c8-102">File sharing high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a75c8-103">_**Последнее изменение темы:** 2012-03-30_</span><span class="sxs-lookup"><span data-stu-id="a75c8-103">_**Topic Last Modified:** 2012-03-30_</span></span>

<span data-ttu-id="a75c8-104">Для обеспечения высокой доступности общего доступа к файлам Lync Server в одном центре обработки данных можно использовать распределенную файловую систему (DFS).</span><span class="sxs-lookup"><span data-stu-id="a75c8-104">To ensure high availability for Lync Server file sharing within a single data center, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="a75c8-105">Распределенная файловая система поддерживает отработку отказа в пределах одного центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="a75c8-105">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="a75c8-106">Для крупных развертываний рекомендуется использовать выделенные файловые серверы, связанные между собой с помощью распределенной файловой системы.</span><span class="sxs-lookup"><span data-stu-id="a75c8-106">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span>

<span data-ttu-id="a75c8-107">В зависимости от размера сети и требуемой устойчивости вы можете использовать одну пару серверов для всех файловых ресурсов общего доступа на сайте или использовать одну пару серверов для каждого интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="a75c8-107">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>

<span data-ttu-id="a75c8-p102">Распределенная файловая система предоставляет наилучший механизм репликации файлов, который не имеет заявленных обязательств по директивному времени восстановления (RTO) или целевой точке восстановления (RPO). Отработка отказа между серверами распределенной файловой системы должна выполняться быстро, однако задержки репликации данных могут привести к тому, что пользователи не смогут продолжить работу при отработке отказа.</span><span class="sxs-lookup"><span data-stu-id="a75c8-p102">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment. The failover between the DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>

<span data-ttu-id="a75c8-p103">Если вы используете распределенную файловую систему и храните на файловом ресурсе общего доступа критически важные данные, то вам потребуется достаточно часто создавать резервные копии файлов, например каждые 4-8 часов. При сбое одного файлового ресурса общего доступа и неактуальной репликации вы можете воспользоваться резервной копией для восстановления содержимого серверов на других серверах, которые связаны с временно недоступным сервером.</span><span class="sxs-lookup"><span data-stu-id="a75c8-p103">If you use DFS and data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours. When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

