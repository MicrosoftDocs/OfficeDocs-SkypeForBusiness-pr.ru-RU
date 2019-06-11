---
title: 'Lync Server 2013: общий доступ к файлам с высокой доступностью'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b61a4980c854b6cb79bedbe482bec204a541879f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a><span data-ttu-id="e3889-102">Общий доступ к файлам в Lync Server 2013 с высокой доступностью</span><span class="sxs-lookup"><span data-stu-id="e3889-102">File sharing high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3889-103">_**Тема последнего изменения:** 2012-03-30_</span><span class="sxs-lookup"><span data-stu-id="e3889-103">_**Topic Last Modified:** 2012-03-30_</span></span>

<span data-ttu-id="e3889-104">Для обеспечения высокой доступности общего доступа к файлам Lync Server в одном центре обработки данных вы можете использовать распределенную файловую систему (DFS).</span><span class="sxs-lookup"><span data-stu-id="e3889-104">To ensure high availability for Lync Server file sharing within a single data center, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="e3889-105">DFS поддерживает отработку отказов с переключением на другой файловый сервер в пределах того же центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="e3889-105">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="e3889-106">В случае крупномасштабного развертывания рекомендуется пользоваться выделенными файловыми серверами, объединенными в пары с помощью DFS.</span><span class="sxs-lookup"><span data-stu-id="e3889-106">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span>

<span data-ttu-id="e3889-107">В зависимости от размера сети и объема устойчивости вы можете использовать одну пару серверов для размещения всех общих файловых ресурсов на сайте или использовать одну пару для каждого из них на передней стороне пула.</span><span class="sxs-lookup"><span data-stu-id="e3889-107">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>

<span data-ttu-id="e3889-108">DFS предоставляет собой наилучший механизм репликации файлов без опубликованных обязательств по целевому времени восстановления (RTO) и целевой точке восстановления (RPO).</span><span class="sxs-lookup"><span data-stu-id="e3889-108">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="e3889-109">Отработка отказа между серверами распределенной файловой системы (DFS) должна быть быстро завершена, но задержка репликации данных может препятствовать тому, что пользователи смогут продолжить работу, когда происходит переход на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="e3889-109">The failover between the DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>

<span data-ttu-id="e3889-110">Если вы используете DFS и хранилище данных в общей папке, вы должны часто создавать резервные копии общих файловых ресурсов, например каждые 4 – 8 часов.</span><span class="sxs-lookup"><span data-stu-id="e3889-110">If you use DFS and data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="e3889-111">Если на момент отказа одного общего файлового ресурса данные репликации устарели, можно восстановить содержимое сбойного сервера на другом сервере, объединенном с ним в пару.</span><span class="sxs-lookup"><span data-stu-id="e3889-111">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

