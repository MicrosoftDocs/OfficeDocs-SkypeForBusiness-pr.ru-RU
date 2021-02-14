---
title: Страница публикации CMS выбора топологии
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Топология, настроенная с помощью построитель топологий, публикуется. Вам будет предложено выбрать из списка, какой сервер переднего плана или пул переднего плана будут выполнять роль хранения центрального банка управления. В любой момент времени эту роль может использовать только один сервер переднего плана или пул переднего плана.
ms.openlocfilehash: d4af4756dc42c54790ee1120b418eb5e6a349387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822189"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="9ddae-105">Страница публикации CMS выбора топологии</span><span class="sxs-lookup"><span data-stu-id="9ddae-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="9ddae-106">Вы публикуете топологию, настроенную с помощью построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="9ddae-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="9ddae-107">Вам будет предложено выбрать из списка, какой сервер переднего плана или пул переднего плана будут выполнять роль хранения центрального банка управления.</span><span class="sxs-lookup"><span data-stu-id="9ddae-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="9ddae-108">В любой момент времени эту роль может использовать только один сервер переднего плана или пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="9ddae-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="9ddae-109">О центральном сервере управления</span><span class="sxs-lookup"><span data-stu-id="9ddae-109">About the Central Management Server</span></span>
<span data-ttu-id="9ddae-110">Центральный сервер управления — это единая система с несколькими репликами, где копия базы данных для чтения и записи хранится на сервере переднего сервера, содержаном центральный сервер управления.</span><span class="sxs-lookup"><span data-stu-id="9ddae-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="9ddae-111">Каждый компьютер в топологии, включая сервер переднего сервера, содержащий центральный сервер управления, имеет доступную только для чтения копию данных центрального банка управления в базе данных SQL Server (с именем RTCLOCAL по умолчанию), установленной на компьютере во время установки и развертывания.</span><span class="sxs-lookup"><span data-stu-id="9ddae-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="9ddae-112">Локализованная база данных получает обновления реплики с помощью агента репликатора Lync Server, который выполняется как служба на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="9ddae-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="9ddae-113">Имя фактической базы данных на центральном сервере управления и локальной реплики — XDS, которая состоит из файлов xds.mdf и xds.ldf.</span><span class="sxs-lookup"><span data-stu-id="9ddae-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="9ddae-114">На расположение базы данных эталонной базы данных ссылается точка управления службой (SCP) в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9ddae-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="9ddae-115">Все средства, которые используют центральный сервер управления для управления и настройки Lync Server, используют SCP для поиска центрального хранения управления.</span><span class="sxs-lookup"><span data-stu-id="9ddae-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9ddae-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9ddae-116">See also</span></span>

[<span data-ttu-id="9ddae-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="9ddae-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
