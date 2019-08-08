---
title: Стандартные пулы для фазы 8 списания
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: httpsfix
description: В следующих разделах приведены рекомендации по обновлению DNS-записей, перемещению сервера управления контентом, удалению пулов и отключению серверов и пулов из устаревшего развертывания. Не все процедуры, перечисленные в этом разделе, являются обязательными. Ознакомьтесь с документацией и определите, какую процедуру списания использовать.
ms.openlocfilehash: 5edad470bcd7bcf0340a311a890f73ef01645138
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236998"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="16564-105">Этап 8: ликвидация старых пулов</span><span class="sxs-lookup"><span data-stu-id="16564-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="16564-106">В следующих разделах приведены рекомендации по обновлению DNS-записей, перемещению сервера управления контентом, удалению пулов и отключению серверов и пулов из устаревшего развертывания.</span><span class="sxs-lookup"><span data-stu-id="16564-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="16564-107">Не все процедуры, перечисленные в этом разделе, являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="16564-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="16564-108">Ознакомьтесь с документацией и определите, какую процедуру списания использовать.</span><span class="sxs-lookup"><span data-stu-id="16564-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="16564-109">Для получения устаревшей статьи об удалении серверов и ролей сервера и пошаговом руководстве по списанию развертывания Скачайте [приложение Microsoft Lync Server и удалите роли сервера](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="16564-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="16564-110">Сведения о переносе и обновлении приложений для управляемых API Microsoft Unified Communications (УКМА) перед списанием устаревшей среды можно найти в статье [приложения УКМА: сосуществование, миграция и сценарии обновления](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span><span class="sxs-lookup"><span data-stu-id="16564-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="16564-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="16564-111">In this section</span></span>

> [<span data-ttu-id="16564-112">Обновление записей DNS SRV</span><span class="sxs-lookup"><span data-stu-id="16564-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="16564-113">Перемещение устаревшего сервера централизованного управления установкой в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="16564-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="16564-114">Перемещение каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="16564-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="16564-115">Удаление связи с сервером архивирования</span><span class="sxs-lookup"><span data-stu-id="16564-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="16564-116">Удаление связи с сервером мониторинга</span><span class="sxs-lookup"><span data-stu-id="16564-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="16564-117">Удаление сервера переднего плана Enterprise Edition или стандартного выпуска Standard Edition</span><span class="sxs-lookup"><span data-stu-id="16564-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="16564-118">Удаление экземпляров и баз данных SQL Server на внутреннем сервере</span><span class="sxs-lookup"><span data-stu-id="16564-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

