---
title: Этапы 8 списания устаревших пулов
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: httpsfix
description: В следующих разделах представлены рекомендации по обновлению записей DNS, перемещению сервера управления контентом, отключению пулов, отключению и удалению серверов и пулов из устаревшего развертывания. Не все процедуры, рассматриваемые в этом разделе, являются обязательными. Ознакомьтесь в документацией и определите, какую из процедур списания следует использовать.
ms.openlocfilehash: 2406b25436bc13cafca8b09c92220a96e0635ae3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753697"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="8bfd3-105">Этап 8: ликвидация старых пулов</span><span class="sxs-lookup"><span data-stu-id="8bfd3-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="8bfd3-106">В следующих разделах представлены рекомендации по обновлению записей DNS, перемещению сервера управления контентом, отключению пулов, отключению и удалению серверов и пулов из устаревшего развертывания.</span><span class="sxs-lookup"><span data-stu-id="8bfd3-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="8bfd3-107">Не все процедуры, рассматриваемые в этом разделе, являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="8bfd3-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="8bfd3-108">Ознакомьтесь в документацией и определите, какую из процедур списания следует использовать.</span><span class="sxs-lookup"><span data-stu-id="8bfd3-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="8bfd3-109">За исключением подробной статьи об удалении серверов и ролей серверов и пошаговом руководстве по списанию развертывания, скачайте раздел Удаление [Microsoft Lync Server и удалите роли сервера](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="8bfd3-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8bfd3-110">Сведения о переносе и обновлении приложений Microsoft Unified Communications Managed API (UCMA) перед списанием устаревшей среды [: UCMA Applications: сосуществование, миграция и сценарии обновления](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span><span class="sxs-lookup"><span data-stu-id="8bfd3-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="8bfd3-111">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="8bfd3-111">In this section</span></span>

> [<span data-ttu-id="8bfd3-112">Обновление записей DNS SRV</span><span class="sxs-lookup"><span data-stu-id="8bfd3-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="8bfd3-113">Перемещение устаревшего сервера централизованного управления установки в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="8bfd3-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="8bfd3-114">Перемещение каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="8bfd3-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="8bfd3-115">Удаление связи с сервером архивирования</span><span class="sxs-lookup"><span data-stu-id="8bfd3-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="8bfd3-116">Удаление связи с сервером мониторинга</span><span class="sxs-lookup"><span data-stu-id="8bfd3-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="8bfd3-117">Удаление сервера переднего плана Enterprise Edition или сервера переднего плана Standard Edition</span><span class="sxs-lookup"><span data-stu-id="8bfd3-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="8bfd3-118">Удаление экземпляров и баз данных SQL Server на внутреннем сервере</span><span class="sxs-lookup"><span data-stu-id="8bfd3-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

