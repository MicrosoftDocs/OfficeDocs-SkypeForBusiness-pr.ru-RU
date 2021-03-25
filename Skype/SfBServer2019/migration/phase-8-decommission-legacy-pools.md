---
title: Пулы устаревших пулов вывода из эксплуатации фазы 8
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
description: В следующем разделе приводится руководство по обновлению записей DNS, перемещению сервера управления контентом, выводу пулов из эксплуатации, а также отключению и удалянию серверов и пулов из устаревшего развертывания. Не все процедуры, рассматриваемые в этом разделе, являются обязательными. Ознакомьтесь в документацией и определите, какую из процедур списания следует использовать.
ms.openlocfilehash: b1080c68e3b4075ce92aaef497854855135dc47d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113245"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="ac916-105">Этап 8: ликвидация старых пулов</span><span class="sxs-lookup"><span data-stu-id="ac916-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="ac916-106">В следующем разделе приводится руководство по обновлению записей DNS, перемещению сервера управления контентом, выводу пулов из эксплуатации, а также отключению и удалянию серверов и пулов из устаревшего развертывания.</span><span class="sxs-lookup"><span data-stu-id="ac916-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="ac916-107">Не все процедуры, рассматриваемые в этом разделе, являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="ac916-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="ac916-108">Ознакомьтесь в документацией и определите, какую из процедур списания следует использовать.</span><span class="sxs-lookup"><span data-stu-id="ac916-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="ac916-109">Для датной, но исчерпывающей статьи об удалении серверов и ролей сервера и пошаговом руководстве по выводу развертывания из эксплуатации скачайте [uninstalling Microsoft Lync Server](https://go.microsoft.com/fwlink/p/?linkId=246227)и Removing Server Roles .</span><span class="sxs-lookup"><span data-stu-id="ac916-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ac916-110">Сведения о переносе и обновлении приложений microsoft Unified Communications Managed API (UCMA) перед выводом из эксплуатации устаревшей среды см. в приложении [UCMA: сосуществование,](/previous-versions/office/jj728782(v=office.15))миграция и сценарии обновления.</span><span class="sxs-lookup"><span data-stu-id="ac916-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](/previous-versions/office/jj728782(v=office.15)).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="ac916-111">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="ac916-111">In this section</span></span>

> [<span data-ttu-id="ac916-112">Обновление записей DNS SRV</span><span class="sxs-lookup"><span data-stu-id="ac916-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="ac916-113">Перемещение устаревшей установки Центрального сервера управления в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="ac916-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="ac916-114">Перемещение каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="ac916-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="ac916-115">Удаление связи с сервером архивирования</span><span class="sxs-lookup"><span data-stu-id="ac916-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="ac916-116">Удаление связи с сервером мониторинга</span><span class="sxs-lookup"><span data-stu-id="ac916-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="ac916-117">Удаление переднего сервера корпоративного выпуска или переднего сервера стандартного выпуска</span><span class="sxs-lookup"><span data-stu-id="ac916-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="ac916-118">Удаление экземпляров и баз данных SQL Server на внутреннем сервере</span><span class="sxs-lookup"><span data-stu-id="ac916-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
