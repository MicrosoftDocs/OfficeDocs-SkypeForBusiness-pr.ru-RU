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
description: Вы публикуете топологию, настроенную с помощью Topology Builder. Вам будет предложено выбрать из списка, который front End Server или пул переднего плана будет выполнять роль хранения центра управления. Только один пул переднего плана или переднего плана может удерживать эту роль в любой момент времени.
ms.openlocfilehash: fe3e7ed8c0a58b0547ede0eb02f0ea476bce94bc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096885"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="08824-105">Страница публикации CMS выбора топологии</span><span class="sxs-lookup"><span data-stu-id="08824-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="08824-106">Вы публикуете топологию, настроенную с помощью Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="08824-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="08824-107">Вам будет предложено выбрать из списка, который front End Server или пул переднего плана будет выполнять роль хранения центра управления.</span><span class="sxs-lookup"><span data-stu-id="08824-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="08824-108">Только один пул переднего плана или переднего плана может удерживать эту роль в любой момент времени.</span><span class="sxs-lookup"><span data-stu-id="08824-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="08824-109">О центральном сервере управления</span><span class="sxs-lookup"><span data-stu-id="08824-109">About the Central Management Server</span></span>
<span data-ttu-id="08824-110">Центральный сервер управления — это единая система репликации, в которой копия базы данных для чтения и записи хранится на переднем конечном сервере, который содержит центральный сервер управления.</span><span class="sxs-lookup"><span data-stu-id="08824-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="08824-111">Каждый компьютер в топологии, включая сервер переднего конечного сервера, содержащий центральный сервер управления, имеет только для чтения копию данных центра управления в базе данных SQL Server (по умолчанию именуемой RTCLOCAL), установленной на компьютере во время установки и развертывания.</span><span class="sxs-lookup"><span data-stu-id="08824-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="08824-112">Локализованная база данных получает обновления реплики с помощью агента репликатора репликатора Lync Server, который выполняется в качестве службы на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="08824-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="08824-113">Имя фактической базы данных на центральном сервере управления и локальной реплики — XDS, которая состоит из файлов xds.mdf и xds.ldf.</span><span class="sxs-lookup"><span data-stu-id="08824-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="08824-114">Расположение базы данных ссылается на пункт управления службами (SCP) в службах домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="08824-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="08824-115">Все средства, которые используют Центральный сервер управления для управления и настройки Lync Server, используют SCP для обнаружения центра управления.</span><span class="sxs-lookup"><span data-stu-id="08824-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="08824-116">См. также</span><span class="sxs-lookup"><span data-stu-id="08824-116">See also</span></span>

[<span data-ttu-id="08824-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="08824-117">Move-CsManagementServer</span></span>](/powershell/module/skype/move-csmanagementserver?view=skype-ps)