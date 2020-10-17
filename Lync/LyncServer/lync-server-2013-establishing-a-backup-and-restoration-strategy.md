---
title: 'Lync Server 2013: Установка стратегии резервного копирования и восстановления'
description: 'Lync Server 2013: создание стратегии резервного копирования и восстановления.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4fdefed873d1fd69d82f8ecebceeb92f06f65f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555045"
---
# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="980ab-103">Создание стратегии резервного копирования и восстановления для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="980ab-103">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="980ab-104">_**Последнее изменение темы:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="980ab-104">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="980ab-105">Прежде чем приступить к разработке плана резервного копирования и восстановления для Lync Server, необходимо разработать стратегию, которая соответствует целям Организации.</span><span class="sxs-lookup"><span data-stu-id="980ab-105">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="980ab-106">Чтобы разработать эффективную стратегию резервного копирования и восстановления, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="980ab-106">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="980ab-107">Определение бизнес-приоритетов.</span><span class="sxs-lookup"><span data-stu-id="980ab-107">Establish business priorities.</span></span>

  - <span data-ttu-id="980ab-108">Определите требования к резервному копированию и восстановлению.</span><span class="sxs-lookup"><span data-stu-id="980ab-108">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="980ab-109">Задание приоритетов бизнеса</span><span class="sxs-lookup"><span data-stu-id="980ab-109">Establishing Business Priorities</span></span>

<span data-ttu-id="980ab-110">Оцените бизнес-приоритеты вашей организации.</span><span class="sxs-lookup"><span data-stu-id="980ab-110">Evaluate the business priorities of your organization.</span></span> <span data-ttu-id="980ab-111">Как правило, основные бизнес-приоритеты, влияющие на стратегию резервного копирования и восстановления, приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="980ab-111">Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="980ab-112">Требования к бесперебойной работе бизнеса</span><span class="sxs-lookup"><span data-stu-id="980ab-112">Business continuity requirements</span></span>

  - <span data-ttu-id="980ab-113">Полнота данных</span><span class="sxs-lookup"><span data-stu-id="980ab-113">Data completeness</span></span>

  - <span data-ttu-id="980ab-114">Критические данные</span><span class="sxs-lookup"><span data-stu-id="980ab-114">Data criticality</span></span>

  - <span data-ttu-id="980ab-115">Требования к переносимости</span><span class="sxs-lookup"><span data-stu-id="980ab-115">Portability requirements</span></span>

  - <span data-ttu-id="980ab-116">Ограничения затрат</span><span class="sxs-lookup"><span data-stu-id="980ab-116">Cost constraints</span></span>

<span data-ttu-id="980ab-117">Бизнес-потребности, например, помогут вам определить соглашения об уровне обслуживания, которые вы разрабатываете у ваших клиентов.</span><span class="sxs-lookup"><span data-stu-id="980ab-117">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="980ab-118">Соглашение об уровне обслуживания сильно влияет на стратегию резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="980ab-118">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="980ab-119">Определение требований к резервному копированию и восстановлению</span><span class="sxs-lookup"><span data-stu-id="980ab-119">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="980ab-120">Бизнес-приоритеты и соглашения об уровне обслуживания действуют при определении требований Организации к резервному копированию и восстановлению сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="980ab-120">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="980ab-121">Определите и задокументируйте свои требования для следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="980ab-121">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="980ab-122">**Периодичность резервного копирования**     Рекомендации по [резервному копированию и восстановлению для Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md)приведены в статье рекомендации по их использованию.</span><span class="sxs-lookup"><span data-stu-id="980ab-122">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="980ab-123">Средства резервного **копирования и восстановления**     Укажите, кто должен использовать средства и на каких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="980ab-123">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="980ab-124">Подробные сведения о средствах, обсуждаемых в этой теме и необходимых разрешениях, приведены [в статье требования к резервному копированию и восстановлению в Lync Server 2013: Tools and Permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="980ab-124">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="980ab-125">Расположение резервной **копии**     Определить, хранятся ли резервные копии локально или удаленно, следует учитывать безопасность и специальные возможности.</span><span class="sxs-lookup"><span data-stu-id="980ab-125">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="980ab-126">Укажите носитель, который будет использоваться для резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="980ab-126">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="980ab-127">**Требования к**     оборудованию и программному обеспечению Определите и задокументируйте определенные требования к оборудованию и программному обеспечению, в том числе оборудование для резервного хранения и восстановления определенных компонентов, а также программное обеспечение и сетевое подключение, необходимое для поддержки резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="980ab-127">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="980ab-128">Когда вы разрабатываете требования к оборудованию и программному обеспечению, помните о различных сценариях восстановления, приведенных ниже.</span><span class="sxs-lookup"><span data-stu-id="980ab-128">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="980ab-129">**Сценарии восстановления**     Ниже приведены процессы восстановления для следующих сценариев:</span><span class="sxs-lookup"><span data-stu-id="980ab-129">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="980ab-130">Сбой пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="980ab-130">A Lync Server pool fails.</span></span> <span data-ttu-id="980ab-131">В этом сценарии требуется перестроение каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="980ab-131">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="980ab-132">Сервер Standard Edition завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="980ab-132">A Standard Edition server fails.</span></span> <span data-ttu-id="980ab-133">В этом сценарии требуется повторное создание сервера на новом или чистом компьютере и восстановление баз данных.</span><span class="sxs-lookup"><span data-stu-id="980ab-133">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="980ab-134">Потеря центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="980ab-134">Loss of the Central Management store.</span></span> <span data-ttu-id="980ab-135">Как минимум, этот сценарий требует восстановления и публикации центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="980ab-135">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="980ab-136">Потеря внутреннего сервера, когда центральное хранилище управления все же работает нормально.</span><span class="sxs-lookup"><span data-stu-id="980ab-136">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="980ab-137">В этом сценарии требуется повторное создание сервера на новом или чистом компьютере и восстановление баз данных.</span><span class="sxs-lookup"><span data-stu-id="980ab-137">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="980ab-138">Сервер, который является членом пула Lync Server, завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="980ab-138">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="980ab-139">В этом сценарии требуется повторное создание сервера на новом или чистом компьютере.</span><span class="sxs-lookup"><span data-stu-id="980ab-139">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="980ab-140">Не удается сохранить файл.</span><span class="sxs-lookup"><span data-stu-id="980ab-140">A File Store fails.</span></span> <span data-ttu-id="980ab-141">Этот сценарий требует восстановления файлового сервера или кластера файлов.</span><span class="sxs-lookup"><span data-stu-id="980ab-141">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="980ab-142">Произойдет сбой базы данных архивации, мониторинга или сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="980ab-142">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="980ab-143">Этот сценарий требует повторного создания баз данных и, если данные важны для Организации, восстанавливая данные.</span><span class="sxs-lookup"><span data-stu-id="980ab-143">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="980ab-144">Архивация, мониторинг и данные сохраняемого чата не требуются для резервного копирования и запуска Lync Server.</span><span class="sxs-lookup"><span data-stu-id="980ab-144">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

