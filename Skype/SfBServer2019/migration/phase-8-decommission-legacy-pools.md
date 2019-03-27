---
title: Этап 8 Decommission старых пулов
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: httpsfix
description: В следующем разделе приводятся рекомендации по обновление записей DNS, перемещении сервера управления контентом, ликвидации пулов и деактивация и удаление серверов и пулов из устаревшего развертывания. Не все процедуры, приведенные в этом разделе не требуется. Ознакомьтесь с документацией и определить, какие списанию процедуру, чтобы использовать.
ms.openlocfilehash: 2363b90f1bcc71c3c8c1ee42d258101240bcacb7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880263"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="5d5a8-105">Этап 8: ликвидация старых пулов</span><span class="sxs-lookup"><span data-stu-id="5d5a8-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="5d5a8-106">В следующем разделе приводятся рекомендации по обновление записей DNS, перемещении сервера управления контентом, ликвидации пулов и деактивация и удаление серверов и пулов из устаревшего развертывания.</span><span class="sxs-lookup"><span data-stu-id="5d5a8-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="5d5a8-107">Не все процедуры, приведенные в этом разделе не требуется.</span><span class="sxs-lookup"><span data-stu-id="5d5a8-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="5d5a8-108">Ознакомьтесь с документацией и определить, какие списанию процедуру, чтобы использовать.</span><span class="sxs-lookup"><span data-stu-id="5d5a8-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="5d5a8-109">Устаревшей, но исчерпывающий статьи на удаление серверов и ролей сервера и пошаговое руководство по ликвидации в развертывании Загрузите [Удаление Microsoft Lync Server и удаление ролей сервера](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="5d5a8-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5d5a8-110">Сведения о миграции и обновлении приложений Microsoft Unified Communications Managed API (UCMA), перед ликвидацией старой среды в разделе [UCMA приложений: совместная работа, миграции и сценарии обновления](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span><span class="sxs-lookup"><span data-stu-id="5d5a8-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="5d5a8-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="5d5a8-111">In this section</span></span>

> [<span data-ttu-id="5d5a8-112">Обновление записей DNS SRV</span><span class="sxs-lookup"><span data-stu-id="5d5a8-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="5d5a8-113">Перемещение прежних версий install центральный сервер управления Скайп для Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="5d5a8-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="5d5a8-114">Перемещение каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="5d5a8-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="5d5a8-115">Удаление связи с сервером архивирования</span><span class="sxs-lookup"><span data-stu-id="5d5a8-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="5d5a8-116">Удаление связи с сервером мониторинга</span><span class="sxs-lookup"><span data-stu-id="5d5a8-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="5d5a8-117">Удаление сервера переднего плана Enterprise Edition или сервера переднего плана Standard Edition</span><span class="sxs-lookup"><span data-stu-id="5d5a8-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="5d5a8-118">Удаление экземпляров и баз данных SQL Server на внутреннем сервере</span><span class="sxs-lookup"><span data-stu-id="5d5a8-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

