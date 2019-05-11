---
title: Общий доступ к файлам высокой доступности в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Сведения об обеспечении высокой доступности на файловых Скайп для Business Server, с помощью DFS.
ms.openlocfilehash: 90d67622c1c1fbd9567df69187519be63e812ac8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910216"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="c06ec-103">Общий доступ к файлам высокой доступности в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="c06ec-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="c06ec-104">Сведения об обеспечении высокой доступности на файловых Скайп для Business Server, с помощью DFS.</span><span class="sxs-lookup"><span data-stu-id="c06ec-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="c06ec-105">Чтобы обеспечить высокий уровень доступности общий доступ к файлам в вашей Скайп для развертывания Business Server, можно использовать распределенной файловой системы (DFS).</span><span class="sxs-lookup"><span data-stu-id="c06ec-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="c06ec-106">DFS поддерживает отработку отказов с переключением на другой файловый сервер в пределах того же центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="c06ec-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="c06ec-107">В случае крупномасштабного развертывания рекомендуется пользоваться выделенными файловыми серверами, объединенными в пары с помощью DFS.</span><span class="sxs-lookup"><span data-stu-id="c06ec-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="c06ec-108">Дополнительные сведения о DFS в Windows Server 2012 можно [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span><span class="sxs-lookup"><span data-stu-id="c06ec-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="c06ec-109">Сведения о DFS в Windows Server 2008 можно [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span><span class="sxs-lookup"><span data-stu-id="c06ec-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="c06ec-110">В зависимости от размера вашей сети и объем устойчивость, который будет использовать один из пары серверов для размещения всех общих папках на сайте или используйте один из пары каждого пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c06ec-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="c06ec-111">DFS предоставляет собой наилучший механизм репликации файлов без опубликованных обязательств по целевому времени восстановления (RTO) и целевой точке восстановления (RPO).</span><span class="sxs-lookup"><span data-stu-id="c06ec-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="c06ec-112">Отработка отказа между серверами DFS необходимо выполнить быстро, но задержка репликации данных может запретить пользователям для продолжения выполнения работы в случае отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="c06ec-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="c06ec-p103">Если при работе с DFS на общем файловом ресурсе хранятся критически важные данные, следует создавать резервные копии общего файлового ресурса с высокой периодичностью, например каждые 4–8 часов. Если на момент отказа одного общего файлового ресурса данные репликации устарели, можно восстановить содержимое сбойного сервера на другом сервере, объединенном с ним в пару.</span><span class="sxs-lookup"><span data-stu-id="c06ec-p103">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours. When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

