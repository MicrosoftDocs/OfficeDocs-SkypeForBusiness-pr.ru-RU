---
title: Страница публикации CMS выбора топологии
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Вы публикуете топологию, настроенную с помощью построителя топологии. Вам будет предложено выбрать из списка сервер переднего плана или пул переднего плана, роль которого заключается в том, что вы владеете централизованным хранилищем управления. Только один сервер переднего плана или интерфейс переднего плана может включать эту роль в любое время.
ms.openlocfilehash: e56597a1380f908c7abdb49b9b88edd7ad249870
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277883"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="7522b-105">Страница публикации CMS выбора топологии</span><span class="sxs-lookup"><span data-stu-id="7522b-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="7522b-106">Вы публикуете топологию, настроенную с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="7522b-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="7522b-107">Вам будет предложено выбрать из списка сервер переднего плана или пул переднего плана, роль которого заключается в том, что вы владеете централизованным хранилищем управления.</span><span class="sxs-lookup"><span data-stu-id="7522b-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="7522b-108">Только один сервер переднего плана или интерфейс переднего плана может включать эту роль в любое время.</span><span class="sxs-lookup"><span data-stu-id="7522b-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="7522b-109">Общие сведения об центральном сервере управления</span><span class="sxs-lookup"><span data-stu-id="7522b-109">About the Central Management Server</span></span>
<span data-ttu-id="7522b-110">Центральный сервер управления — это единая Главная или несколько реплик, где сервер переднего плана, на котором находится база данных для чтения и записи, находится на сервере, который содержит центральный сервер управления.</span><span class="sxs-lookup"><span data-stu-id="7522b-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="7522b-111">На каждом компьютере в топологии, включая сервер переднего плана, на котором находится центральный сервер управления, доступна только для чтения копия данных центрального хранилища в базе данных SQL Server (с именем РТКЛОКАЛ по умолчанию), установленной на компьютере во время установки и среде.</span><span class="sxs-lookup"><span data-stu-id="7522b-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="7522b-112">Локальная база данных получает обновления реплики с помощью агента репликатора реплики Lync Server, который запускается как служба на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="7522b-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="7522b-113">Имя реальной базы данных на центральном сервере управления и в локальной реплике — XDS, которая состоит из файлов XDS. mdf и XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="7522b-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="7522b-114">На расположение базы данных Master ссылается точка управления службой (SCP) доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7522b-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="7522b-115">Все средства, использующие центральный сервер управления для управления и настройки Lync Server, используют SCP для поиска хранилища центрального управления.</span><span class="sxs-lookup"><span data-stu-id="7522b-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7522b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7522b-116">See also</span></span>

[<span data-ttu-id="7522b-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="7522b-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
