---
title: Высокая доступность общего доступа к файлам в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Узнайте о том, как обеспечить высокую доступность файлового доступа в Skype для бизнеса Server с помощью DFS.
ms.openlocfilehash: 4d443425f453d63694511d13c6d3a84893058daa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802899"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="fa7e0-103">Высокая доступность общего доступа к файлам в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="fa7e0-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="fa7e0-104">Узнайте о том, как обеспечить высокую доступность файлового доступа в Skype для бизнеса Server с помощью DFS.</span><span class="sxs-lookup"><span data-stu-id="fa7e0-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="fa7e0-105">Чтобы обеспечить высокую доступность общего доступа к файлам в развертывании Skype для бизнеса Server, можно использовать распределенную файловую систему (DFS).</span><span class="sxs-lookup"><span data-stu-id="fa7e0-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="fa7e0-106">Распределенная файловая система поддерживает отработку отказа в пределах одного центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="fa7e0-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="fa7e0-107">Для крупных развертываний рекомендуется использовать выделенные файловые серверы, связанные между собой с помощью распределенной файловой системы.</span><span class="sxs-lookup"><span data-stu-id="fa7e0-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="fa7e0-108">Дополнительные сведения о DFS в Windows Server 2012 см. в [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384) .</span><span class="sxs-lookup"><span data-stu-id="fa7e0-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="fa7e0-109">Сведения о DFS в Windows Server 2008 см. в [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385) .</span><span class="sxs-lookup"><span data-stu-id="fa7e0-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="fa7e0-110">В зависимости от размера сети и требуемой устойчивости вы можете использовать одну пару серверов для всех файловых ресурсов общего доступа на сайте или использовать одну пару серверов для каждого интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="fa7e0-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="fa7e0-111">Распределенная файловая система предоставляет наилучший механизм репликации файлов, который не имеет заявленных обязательств по директивному времени восстановления (RTO) или целевой точке восстановления (RPO).</span><span class="sxs-lookup"><span data-stu-id="fa7e0-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="fa7e0-112">Отбой между серверами DFS должен быть выполнен быстро, но задержка репликации данных может препятствовать тому, что пользователи смогут продолжить работу в процессе отложенного выполнения.</span><span class="sxs-lookup"><span data-stu-id="fa7e0-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="fa7e0-113">Если вы используете DFS и хранилище данных в файловой папке имеет критическое значение, следует часто архивировать файловый файл, например каждые 4–8 часов.</span><span class="sxs-lookup"><span data-stu-id="fa7e0-113">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="fa7e0-114">При сбое одного файлового ресурса общего доступа и неактуальной репликации вы можете воспользоваться резервной копией для восстановления содержимого серверов на других серверах, которые связаны с временно недоступным сервером.</span><span class="sxs-lookup"><span data-stu-id="fa7e0-114">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

