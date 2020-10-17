---
title: Миграция с Lync Server 2010 на Lync Server 2013
description: Миграция с Lync Server 2010 на Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbe1bc1b7745c5ddc89a7f8fb64295a82f52c9bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543205"
---
# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="71505-103">Миграция с Lync Server 2010 на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71505-103">Migration from Lync Server 2010 to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71505-104">_**Последнее изменение темы:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="71505-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="71505-105">В подразделах этого раздела описывается процесс перехода с Lync Server 2010 на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71505-105">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="71505-p101">В данном документе приведены действия, которые в общем случае требуется выполнить для завершения каждого из этапов миграции, и не рассматриваются все возможные топологии устаревших развертываний или сценарии миграции. Таким образом, возможно, что в зависимости от развертывания вам не потребуется выполнять все перечисленные действия или потребуется выполнить дополнительные действия. В этом документе также содержатся примеры действий по проверке, которые помогут вам понять, на что нужно обратить внимание для успешного выполнения каждого из этапов миграции. Приведите эти действия по проверки в соответствие со своим процессом миграции.</span><span class="sxs-lookup"><span data-stu-id="71505-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="71505-p102">В данном руководстве приведена информация об обновлении вашего существующего развертывания. В нем не поясняется, как изменить существующую топологию или внедрить новые возможности. При наличии описания подробной процедуры в данном руководстве указывается ссылка на соответствующий документ или его раздел.</span><span class="sxs-lookup"><span data-stu-id="71505-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="71505-116">В этом документе используются термины, указанные в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="71505-116">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="71505-117">*следующего*</span><span class="sxs-lookup"><span data-stu-id="71505-117">*migration*</span></span>  
    <span data-ttu-id="71505-118">Перемещение рабочего развертывания из предыдущей версии Lync Server 2010 на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71505-118">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="71505-119">*Обновление*</span><span class="sxs-lookup"><span data-stu-id="71505-119">*upgrade*</span></span>  
    <span data-ttu-id="71505-120">Установка более новой версии программного обеспечения на сервере или клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="71505-120">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="71505-121">*сосуществования*</span><span class="sxs-lookup"><span data-stu-id="71505-121">*coexistence*</span></span>  
    <span data-ttu-id="71505-122">Временная среда, существующая во время миграции, когда некоторые функции были перенесены в Lync Server 2013, и другие функции по-прежнему остаются в предыдущей версии Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="71505-122">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="71505-123">*взаимодействие*</span><span class="sxs-lookup"><span data-stu-id="71505-123">*interoperability*</span></span>  
    <span data-ttu-id="71505-124">Способность вашего развертывания успешно работать во время периода сосуществования.</span><span class="sxs-lookup"><span data-stu-id="71505-124">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="71505-125">Содержание</span><span class="sxs-lookup"><span data-stu-id="71505-125">In This Section</span></span>

  - [<span data-ttu-id="71505-126">Перед началом миграции</span><span class="sxs-lookup"><span data-stu-id="71505-126">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="71505-127">Этап 1: Планирование миграции с Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="71505-127">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="71505-128">Этап 2: подготовка к миграции</span><span class="sxs-lookup"><span data-stu-id="71505-128">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="71505-129">Этап 3: Развертывание пилотного пула Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71505-129">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="71505-130">Этап 4: перемещение тестовых пользователей в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="71505-130">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="71505-131">Этап 5: Добавление пограничного сервера Lync Server 2013 в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="71505-131">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="71505-132">Этап 6: переход от пилотного развертывания к рабочей версии</span><span class="sxs-lookup"><span data-stu-id="71505-132">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="71505-133">Этап 7: необходимые действия после миграции</span><span class="sxs-lookup"><span data-stu-id="71505-133">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="71505-134">Этап 8: ликвидация старых пулов</span><span class="sxs-lookup"><span data-stu-id="71505-134">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

