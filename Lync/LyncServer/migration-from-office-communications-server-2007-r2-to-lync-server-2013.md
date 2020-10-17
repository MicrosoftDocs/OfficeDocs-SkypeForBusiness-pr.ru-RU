---
title: Миграция с Office Communications Server 2007 R2 на Lync Server 2013
description: Миграция из Office Communications Server 2007 R2 на Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0afdc754ae691bc674c200addb9fb97c1eb4199
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569595"
---
# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a><span data-ttu-id="b5339-103">Миграция с Office Communications Server 2007 R2 на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5339-103">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5339-104">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b5339-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b5339-105">В подразделах этого раздела описывается процесс перехода с Office Communications Server 2007 R2 на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5339-105">The topics in this section guide you through the process of migrating from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b5339-p101">В данном документе приведены действия, которые в общем случае требуется выполнить для завершения каждого из этапов миграции, и не рассматриваются все возможные топологии устаревших развертываний или сценарии миграции. Таким образом, возможно, что в зависимости от развертывания вам не потребуется выполнять все перечисленные действия или потребуется выполнить дополнительные действия. В этом документе также содержатся примеры действий по проверке, которые помогут вам понять, на что нужно обратить внимание для успешного выполнения каждого из этапов миграции. Приведите эти действия по проверки в соответствие со своим процессом миграции.</span><span class="sxs-lookup"><span data-stu-id="b5339-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="b5339-p102">В данном руководстве приведена информация об обновлении вашего существующего развертывания. В нем не поясняется, как изменить существующую топологию или внедрить новые возможности. При наличии описания подробной процедуры в данном руководстве указывается ссылка на соответствующий документ или его раздел.</span><span class="sxs-lookup"><span data-stu-id="b5339-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="b5339-116">В этом документе используются термины, указанные в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="b5339-116">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="b5339-117">*следующего*</span><span class="sxs-lookup"><span data-stu-id="b5339-117">*migration*</span></span>  
    <span data-ttu-id="b5339-118">Перемещение рабочего развертывания из предыдущей версии Office Communications Server 2007 R2 на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5339-118">Moving your production deployment from a previous version of Office Communications Server 2007 R2 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="b5339-119">*Обновление*</span><span class="sxs-lookup"><span data-stu-id="b5339-119">*upgrade*</span></span>  
    <span data-ttu-id="b5339-120">Установка более новой версии программного обеспечения на сервере или клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="b5339-120">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="b5339-121">*сосуществования*</span><span class="sxs-lookup"><span data-stu-id="b5339-121">*coexistence*</span></span>  
    <span data-ttu-id="b5339-122">Временная среда, существующая во время миграции, когда некоторые функции были перенесены в Lync Server 2013, и другие функции по-прежнему остаются в предыдущей версии Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b5339-122">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Office Communications Server 2007 R2.</span></span>

<!-- end list -->

  - <span data-ttu-id="b5339-123">*взаимодействие*</span><span class="sxs-lookup"><span data-stu-id="b5339-123">*interoperability*</span></span>  
    <span data-ttu-id="b5339-124">Способность вашего развертывания успешно работать во время периода сосуществования.</span><span class="sxs-lookup"><span data-stu-id="b5339-124">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b5339-125">Содержание</span><span class="sxs-lookup"><span data-stu-id="b5339-125">In This Section</span></span>

  - [<span data-ttu-id="b5339-126">Перед началом миграции</span><span class="sxs-lookup"><span data-stu-id="b5339-126">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="b5339-127">Этапы миграции</span><span class="sxs-lookup"><span data-stu-id="b5339-127">Migration phases</span></span>](migration-phases.md)

  - [<span data-ttu-id="b5339-128">Этап 1: Планирование миграции с Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="b5339-128">Phase 1: Plan your migration from Office Communications Server 2007 R2</span></span>](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [<span data-ttu-id="b5339-129">Этап 2: подготовка к миграции</span><span class="sxs-lookup"><span data-stu-id="b5339-129">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="b5339-130">Этап 3: Развертывание пилотного пула Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5339-130">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="b5339-131">Этап 4: объединение топологий</span><span class="sxs-lookup"><span data-stu-id="b5339-131">Phase 4: Merge topologies</span></span>](phase-4-merge-topologies.md)

  - [<span data-ttu-id="b5339-132">Этап 5: Настройка пилотного пула</span><span class="sxs-lookup"><span data-stu-id="b5339-132">Phase 5: Configure the pilot pool</span></span>](phase-5-configure-the-pilot-pool.md)

  - [<span data-ttu-id="b5339-133">Этап 6: перемещение пользователей в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="b5339-133">Phase 6: Move users to the pilot pool</span></span>](phase-6-move-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="b5339-134">Этап 7: Добавление пограничного сервера Lync Server 2013 в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="b5339-134">Phase 7: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="b5339-135">Этап 8: переход от пилотного развертывания к рабочей среде</span><span class="sxs-lookup"><span data-stu-id="b5339-135">Phase 8: Move from pilot deployment into production</span></span>](phase-8-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="b5339-136">Этап 9: выполнение задач, выполняемых после миграции</span><span class="sxs-lookup"><span data-stu-id="b5339-136">Phase 9: Complete post-migration tasks</span></span>](phase-9-complete-post-migration-tasks.md)

  - [<span data-ttu-id="b5339-137">Этап 10: списание устаревшего сайта</span><span class="sxs-lookup"><span data-stu-id="b5339-137">Phase 10: Decommission legacy site</span></span>](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

