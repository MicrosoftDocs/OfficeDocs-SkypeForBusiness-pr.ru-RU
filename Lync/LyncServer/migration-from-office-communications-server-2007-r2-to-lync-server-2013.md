---
title: Миграция с Office Communications Server 2007 R2 на Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43064d265bc08cab3721d0f19fd7f89184871f0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a><span data-ttu-id="760b6-102">Миграция с Office Communications Server 2007 R2 на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="760b6-102">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="760b6-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="760b6-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="760b6-104">В этом разделе приведены инструкции по переходу с Office Communications Server 2007 R2 на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="760b6-104">The topics in this section guide you through the process of migrating from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="760b6-105">В этом документе описаны действия, которые обычно требуются для выполнения каждого этапа миграции.</span><span class="sxs-lookup"><span data-stu-id="760b6-105">This document describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="760b6-106">Она не будет обращаться к каждой возможной топологии устаревшего развертывания или к любому из возможных сценариев миграции.</span><span class="sxs-lookup"><span data-stu-id="760b6-106">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="760b6-107">Таким образом, вам может потребоваться выполнить все описанные выше действия или, возможно, потребуется выполнить дополнительные действия в зависимости от развертывания.</span><span class="sxs-lookup"><span data-stu-id="760b6-107">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="760b6-108">В этом документе также приводятся примеры шагов проверки.</span><span class="sxs-lookup"><span data-stu-id="760b6-108">This document also provides examples of verification steps.</span></span> <span data-ttu-id="760b6-109">Эти шаги проверки предназначены для того, чтобы понять, что необходимо для того, чтобы убедиться в том, что каждый этап прошел успешно по ходу миграции.</span><span class="sxs-lookup"><span data-stu-id="760b6-109">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="760b6-110">Настройте эти шаги проверки в соответствии с конкретным процессом миграции.</span><span class="sxs-lookup"><span data-stu-id="760b6-110">Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="760b6-111">Это руководство содержит сведения, относящиеся к обновлению существующих развертываний.</span><span class="sxs-lookup"><span data-stu-id="760b6-111">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="760b6-112">В этой статье объясняется, как изменить существующую топологию.</span><span class="sxs-lookup"><span data-stu-id="760b6-112">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="760b6-113">В этом руководстве не рассматриваются реализации новых функций.</span><span class="sxs-lookup"><span data-stu-id="760b6-113">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="760b6-114">Подробное описание процедуры приведено в соответствующем руководстве документа или документа.</span><span class="sxs-lookup"><span data-stu-id="760b6-114">When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="760b6-115">Этот документ определяет условия, указанные в приведенном ниже списке.</span><span class="sxs-lookup"><span data-stu-id="760b6-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="760b6-116">*Перемещение*</span><span class="sxs-lookup"><span data-stu-id="760b6-116">*migration*</span></span>  
    <span data-ttu-id="760b6-117">Перемещение рабочего развертывания из предыдущей версии Office Communications Server 2007 R2 на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="760b6-117">Moving your production deployment from a previous version of Office Communications Server 2007 R2 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="760b6-118">*Обновление*</span><span class="sxs-lookup"><span data-stu-id="760b6-118">*upgrade*</span></span>  
    <span data-ttu-id="760b6-119">Установка более новой версии программного обеспечения на сервере или клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="760b6-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="760b6-120">*сосуществование*</span><span class="sxs-lookup"><span data-stu-id="760b6-120">*coexistence*</span></span>  
    <span data-ttu-id="760b6-121">Временная среда, существующая во время миграции, если некоторые функции были перенесены на Lync Server 2013, а другие функции по-прежнему остаются на ранней версии Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="760b6-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Office Communications Server 2007 R2.</span></span>

<!-- end list -->

  - <span data-ttu-id="760b6-122">*взаимодействия*</span><span class="sxs-lookup"><span data-stu-id="760b6-122">*interoperability*</span></span>  
    <span data-ttu-id="760b6-123">Развертывание может успешно выполняться в течение периода сосуществования.</span><span class="sxs-lookup"><span data-stu-id="760b6-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="760b6-124">Содержание</span><span class="sxs-lookup"><span data-stu-id="760b6-124">In This Section</span></span>

  - [<span data-ttu-id="760b6-125">Перед началом миграции</span><span class="sxs-lookup"><span data-stu-id="760b6-125">Before you begin the migration</span></span>](before-you-begin-the-migration_1.md)

  - [<span data-ttu-id="760b6-126">Этапы миграции</span><span class="sxs-lookup"><span data-stu-id="760b6-126">Migration phases</span></span>](migration-phases_1.md)

  - [<span data-ttu-id="760b6-127">Этап 1: планирование перехода с Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="760b6-127">Phase 1: Plan your migration from Office Communications Server 2007 R2</span></span>](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [<span data-ttu-id="760b6-128">Этап 2: подготовка к миграции</span><span class="sxs-lookup"><span data-stu-id="760b6-128">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration_1.md)

  - [<span data-ttu-id="760b6-129">Этап 3: развертывание пула Lync Server 2013 Pilot</span><span class="sxs-lookup"><span data-stu-id="760b6-129">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [<span data-ttu-id="760b6-130">Этап 4: объединение топологий</span><span class="sxs-lookup"><span data-stu-id="760b6-130">Phase 4: Merge topologies</span></span>](phase-4-merge-topologies.md)

  - [<span data-ttu-id="760b6-131">Этап 5: Настройка пилотного пула</span><span class="sxs-lookup"><span data-stu-id="760b6-131">Phase 5: Configure the pilot pool</span></span>](phase-5-configure-the-pilot-pool.md)

  - [<span data-ttu-id="760b6-132">Этап 6: перемещение пользователей в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="760b6-132">Phase 6: Move users to the pilot pool</span></span>](phase-6-move-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="760b6-133">Этап 7: Добавление сервера Lync Server 2013 EDGE на пилотный пул</span><span class="sxs-lookup"><span data-stu-id="760b6-133">Phase 7: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="760b6-134">Этап 8: переход с пилотного развертывания на рабочий</span><span class="sxs-lookup"><span data-stu-id="760b6-134">Phase 8: Move from pilot deployment into production</span></span>](phase-8-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="760b6-135">Этап 9: завершение задач после миграции</span><span class="sxs-lookup"><span data-stu-id="760b6-135">Phase 9: Complete post-migration tasks</span></span>](phase-9-complete-post-migration-tasks.md)

  - [<span data-ttu-id="760b6-136">Этап 10: списание устаревшего сайта</span><span class="sxs-lookup"><span data-stu-id="760b6-136">Phase 10: Decommission legacy site</span></span>](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

