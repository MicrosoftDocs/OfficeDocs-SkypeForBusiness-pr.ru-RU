---
title: 'Lync Server 2013: Установка стратегии резервного копирования и восстановления'
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
ms.openlocfilehash: 8a65dd081cacd9952ce1b9a7f0917209532a28cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="864bf-102">Создание стратегии резервного копирования и восстановления для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="864bf-102">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="864bf-103">_**Последнее изменение темы:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="864bf-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="864bf-104">Прежде чем приступить к разработке плана резервного копирования и восстановления для Lync Server, необходимо разработать стратегию, которая соответствует целям Организации.</span><span class="sxs-lookup"><span data-stu-id="864bf-104">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="864bf-105">Чтобы разработать эффективную стратегию резервного копирования и восстановления, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="864bf-105">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="864bf-106">Определение бизнес-приоритетов.</span><span class="sxs-lookup"><span data-stu-id="864bf-106">Establish business priorities.</span></span>

  - <span data-ttu-id="864bf-107">Определите требования к резервному копированию и восстановлению.</span><span class="sxs-lookup"><span data-stu-id="864bf-107">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="864bf-108">Задание приоритетов бизнеса</span><span class="sxs-lookup"><span data-stu-id="864bf-108">Establishing Business Priorities</span></span>

<span data-ttu-id="864bf-109">Оцените бизнес-приоритеты вашей организации.</span><span class="sxs-lookup"><span data-stu-id="864bf-109">Evaluate the business priorities of your organization.</span></span> <span data-ttu-id="864bf-110">Как правило, основные бизнес-приоритеты, влияющие на стратегию резервного копирования и восстановления, приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="864bf-110">Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="864bf-111">Требования к бесперебойной работе бизнеса</span><span class="sxs-lookup"><span data-stu-id="864bf-111">Business continuity requirements</span></span>

  - <span data-ttu-id="864bf-112">Полнота данных</span><span class="sxs-lookup"><span data-stu-id="864bf-112">Data completeness</span></span>

  - <span data-ttu-id="864bf-113">Критические данные</span><span class="sxs-lookup"><span data-stu-id="864bf-113">Data criticality</span></span>

  - <span data-ttu-id="864bf-114">Требования к переносимости</span><span class="sxs-lookup"><span data-stu-id="864bf-114">Portability requirements</span></span>

  - <span data-ttu-id="864bf-115">Ограничения затрат</span><span class="sxs-lookup"><span data-stu-id="864bf-115">Cost constraints</span></span>

<span data-ttu-id="864bf-116">Бизнес-потребности, например, помогут вам определить соглашения об уровне обслуживания, которые вы разрабатываете у ваших клиентов.</span><span class="sxs-lookup"><span data-stu-id="864bf-116">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="864bf-117">Соглашение об уровне обслуживания сильно влияет на стратегию резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="864bf-117">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="864bf-118">Определение требований к резервному копированию и восстановлению</span><span class="sxs-lookup"><span data-stu-id="864bf-118">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="864bf-119">Бизнес-приоритеты и соглашения об уровне обслуживания действуют при определении требований Организации к резервному копированию и восстановлению сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="864bf-119">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="864bf-120">Определите и задокументируйте свои требования для следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="864bf-120">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="864bf-121">**Периодичность резервного**   копирования для получения подробных сведений о рекомендациях по резервному копированию, ознакомьтесь с рекомендациями [по резервному копированию и восстановлению для Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span><span class="sxs-lookup"><span data-stu-id="864bf-121">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="864bf-122">**Средства резервного копирования и восстановления**   включают пользователей, которые используют средства и на каких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="864bf-122">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="864bf-123">Подробные сведения о средствах, обсуждаемых в этой теме и необходимых разрешениях, приведены [в статье требования к резервному копированию и восстановлению в Lync Server 2013: Tools and Permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="864bf-123">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="864bf-124">**Расположение резервной копии**   определите, будут ли резервные копии храниться локально или удаленно, учитывая безопасность и специальные возможности.</span><span class="sxs-lookup"><span data-stu-id="864bf-124">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="864bf-125">Укажите носитель, который будет использоваться для резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="864bf-125">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="864bf-126">**Требования к**   оборудованию и программному обеспечению определяют и задокументированы определенные требования к оборудованию и программному обеспечению, включая оборудование для хранения и восстановления отдельных компонентов, а также программное обеспечение и сетевое подключение, необходимое для поддержки резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="864bf-126">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="864bf-127">Когда вы разрабатываете требования к оборудованию и программному обеспечению, помните о различных сценариях восстановления, приведенных ниже.</span><span class="sxs-lookup"><span data-stu-id="864bf-127">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="864bf-128">**Сценарии восстановления вот**   процессы восстановления для следующих сценариев:</span><span class="sxs-lookup"><span data-stu-id="864bf-128">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="864bf-129">Сбой пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="864bf-129">A Lync Server pool fails.</span></span> <span data-ttu-id="864bf-130">В этом сценарии требуется перестроение каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="864bf-130">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="864bf-131">Сервер Standard Edition завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="864bf-131">A Standard Edition server fails.</span></span> <span data-ttu-id="864bf-132">В этом сценарии требуется повторное создание сервера на новом или чистом компьютере и восстановление баз данных.</span><span class="sxs-lookup"><span data-stu-id="864bf-132">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="864bf-133">Потеря центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="864bf-133">Loss of the Central Management store.</span></span> <span data-ttu-id="864bf-134">Как минимум, этот сценарий требует восстановления и публикации центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="864bf-134">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="864bf-135">Потеря внутреннего сервера, когда центральное хранилище управления все же работает нормально.</span><span class="sxs-lookup"><span data-stu-id="864bf-135">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="864bf-136">В этом сценарии требуется повторное создание сервера на новом или чистом компьютере и восстановление баз данных.</span><span class="sxs-lookup"><span data-stu-id="864bf-136">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="864bf-137">Сервер, который является членом пула Lync Server, завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="864bf-137">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="864bf-138">В этом сценарии требуется повторное создание сервера на новом или чистом компьютере.</span><span class="sxs-lookup"><span data-stu-id="864bf-138">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="864bf-139">Не удается сохранить файл.</span><span class="sxs-lookup"><span data-stu-id="864bf-139">A File Store fails.</span></span> <span data-ttu-id="864bf-140">Этот сценарий требует восстановления файлового сервера или кластера файлов.</span><span class="sxs-lookup"><span data-stu-id="864bf-140">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="864bf-141">Произойдет сбой базы данных архивации, мониторинга или сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="864bf-141">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="864bf-142">Этот сценарий требует повторного создания баз данных и, если данные важны для Организации, восстанавливая данные.</span><span class="sxs-lookup"><span data-stu-id="864bf-142">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="864bf-143">Архивация, мониторинг и данные сохраняемого чата не требуются для резервного копирования и запуска Lync Server.</span><span class="sxs-lookup"><span data-stu-id="864bf-143">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

