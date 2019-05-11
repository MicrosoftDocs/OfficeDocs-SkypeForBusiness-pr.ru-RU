---
title: Страница публикации CMS выбора топологии
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Опубликуйте топологию, которую вы настроили с помощью построителя топологий. Будет предложено выбрать из списка, в котором сервер переднего плана или интерфейсный пул примет на себя роль руку центрального хранилища управления. Только один сервер переднего плана или интерфейсный пул может содержать эта роль в любой момент времени.
ms.openlocfilehash: e649629650bfa1fe168698984e3e8b0aaa5d2df4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888760"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="3d800-105">Страница публикации CMS выбора топологии</span><span class="sxs-lookup"><span data-stu-id="3d800-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="3d800-106">Опубликуйте топологию, которую вы настроили с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="3d800-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="3d800-107">Будет предложено выбрать из списка, в котором сервер переднего плана или интерфейсный пул примет на себя роль руку центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="3d800-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="3d800-108">Только один сервер переднего плана или интерфейсный пул может содержать эта роль в любой момент времени.</span><span class="sxs-lookup"><span data-stu-id="3d800-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="3d800-109">О центрального сервера управления</span><span class="sxs-lookup"><span data-stu-id="3d800-109">About the Central Management Server</span></span>
<span data-ttu-id="3d800-110">Центральный сервер управления — это система единого главных/несколькими реплики, где хранится чтение/запись копии базы данных сервера переднего плана, содержащий центральный сервер управления.</span><span class="sxs-lookup"><span data-stu-id="3d800-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="3d800-111">На каждом компьютере в топологии, в том числе сервера переднего плана, содержащий центральный сервер управления имеется только для чтения копию данных хранилища централизованного управления базы данных SQL Server (с именем RTCLOCAL по умолчанию) установлен на компьютере во время установки и развертывание.</span><span class="sxs-lookup"><span data-stu-id="3d800-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="3d800-112">Локальная база данных получает обновления реплики последовательности действий агента репликации Lync Server реплики, на котором выполняется как служба на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3d800-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="3d800-113">Имя базы данных на центральный сервер управления и локальной реплики — XDS, которая включает в себя файлы xds.mdf и xds.ldf.</span><span class="sxs-lookup"><span data-stu-id="3d800-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="3d800-114">Расположение базы данных master ссылаются точки управления службой (SCP) в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3d800-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="3d800-115">Все средства, которые служат для управления и настройки Lync Server центральный сервер управления используйте точку подключения службы для указания центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="3d800-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3d800-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3d800-116">See also</span></span>

[<span data-ttu-id="3d800-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="3d800-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
