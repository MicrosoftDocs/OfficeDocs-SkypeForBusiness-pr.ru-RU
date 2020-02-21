---
title: Миграция с Lync Server 2010 на Lync Server 2013
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
ms.openlocfilehash: 7ea588abf4018ab06a415d4aa5ef7decf5f93996
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="3f7da-102">Миграция с Lync Server 2010 на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f7da-102">Migration from Lync Server 2010 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f7da-103">_**Последнее изменение темы:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="3f7da-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="3f7da-104">В подразделах этого раздела описывается процесс перехода с Lync Server 2010 на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f7da-104">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3f7da-p101">В данном документе приведены действия, которые в общем случае требуется выполнить для завершения каждого из этапов миграции, и не рассматриваются все возможные топологии устаревших развертываний или сценарии миграции. Таким образом, возможно, что в зависимости от развертывания вам не потребуется выполнять все перечисленные действия или потребуется выполнить дополнительные действия. В этом документе также содержатся примеры действий по проверке, которые помогут вам понять, на что нужно обратить внимание для успешного выполнения каждого из этапов миграции. Приведите эти действия по проверки в соответствие со своим процессом миграции.</span><span class="sxs-lookup"><span data-stu-id="3f7da-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="3f7da-p102">В данном руководстве приведена информация об обновлении вашего существующего развертывания. В нем не поясняется, как изменить существующую топологию или внедрить новые возможности. При наличии описания подробной процедуры в данном руководстве указывается ссылка на соответствующий документ или его раздел.</span><span class="sxs-lookup"><span data-stu-id="3f7da-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="3f7da-115">В этом документе используются термины, указанные в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="3f7da-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="3f7da-116">*следующего*</span><span class="sxs-lookup"><span data-stu-id="3f7da-116">*migration*</span></span>  
    <span data-ttu-id="3f7da-117">Перемещение рабочего развертывания из предыдущей версии Lync Server 2010 на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f7da-117">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="3f7da-118">*Обновление*</span><span class="sxs-lookup"><span data-stu-id="3f7da-118">*upgrade*</span></span>  
    <span data-ttu-id="3f7da-119">Установка более новой версии программного обеспечения на сервере или клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="3f7da-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="3f7da-120">*сосуществования*</span><span class="sxs-lookup"><span data-stu-id="3f7da-120">*coexistence*</span></span>  
    <span data-ttu-id="3f7da-121">Временная среда, существующая во время миграции, когда некоторые функции были перенесены в Lync Server 2013, и другие функции по-прежнему остаются в предыдущей версии Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3f7da-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="3f7da-122">*взаимодействие*</span><span class="sxs-lookup"><span data-stu-id="3f7da-122">*interoperability*</span></span>  
    <span data-ttu-id="3f7da-123">Способность вашего развертывания успешно работать во время периода сосуществования.</span><span class="sxs-lookup"><span data-stu-id="3f7da-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3f7da-124">Содержание</span><span class="sxs-lookup"><span data-stu-id="3f7da-124">In This Section</span></span>

  - [<span data-ttu-id="3f7da-125">Перед началом миграции</span><span class="sxs-lookup"><span data-stu-id="3f7da-125">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="3f7da-126">Этап 1: Планирование миграции с Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3f7da-126">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="3f7da-127">Этап 2: подготовка к миграции</span><span class="sxs-lookup"><span data-stu-id="3f7da-127">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="3f7da-128">Этап 3: Развертывание пилотного пула Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f7da-128">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="3f7da-129">Этап 4: перемещение тестовых пользователей в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="3f7da-129">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="3f7da-130">Этап 5: Добавление пограничного сервера Lync Server 2013 в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="3f7da-130">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="3f7da-131">Этап 6: переход от пилотного развертывания к рабочей среде</span><span class="sxs-lookup"><span data-stu-id="3f7da-131">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="3f7da-132">Этап 7: выполнение задач, выполняемых после миграции</span><span class="sxs-lookup"><span data-stu-id="3f7da-132">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="3f7da-133">Этап 8: списание устаревших пулов</span><span class="sxs-lookup"><span data-stu-id="3f7da-133">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

