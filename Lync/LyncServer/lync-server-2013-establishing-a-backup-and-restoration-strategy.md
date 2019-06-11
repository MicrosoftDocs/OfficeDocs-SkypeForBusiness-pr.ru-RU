---
title: 'Lync Server 2013: Установка стратегии резервного копирования и восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d378c66ae820ef0be7b7b3b0492b023863e977ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="48a1c-102">Установка стратегии резервного копирования и восстановления для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48a1c-102">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48a1c-103">_**Тема последнего изменения:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="48a1c-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="48a1c-104">Прежде чем вы сможете разработать план резервного копирования и восстановления для Lync Server, вам нужно разработать стратегию, которая подходит для целей Организации.</span><span class="sxs-lookup"><span data-stu-id="48a1c-104">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="48a1c-105">Чтобы разработать эффективную стратегию резервного копирования и восстановления, вам понадобятся следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="48a1c-105">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="48a1c-106">Определите бизнес-приоритеты.</span><span class="sxs-lookup"><span data-stu-id="48a1c-106">Establish business priorities.</span></span>

  - <span data-ttu-id="48a1c-107">Определите требования к резервному копированию и восстановлению.</span><span class="sxs-lookup"><span data-stu-id="48a1c-107">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="48a1c-108">Установка бизнес-приоритетов</span><span class="sxs-lookup"><span data-stu-id="48a1c-108">Establishing Business Priorities</span></span>

<span data-ttu-id="48a1c-109">Оцените бизнес-приоритеты своей организации.</span><span class="sxs-lookup"><span data-stu-id="48a1c-109">Evaluate the business priorities of your organization.</span></span> <span data-ttu-id="48a1c-110">Обычно основные бизнес-приоритеты, влияющие на стратегию резервного копирования и восстановления, описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="48a1c-110">Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="48a1c-111">Требования к бесперебойной работе компании</span><span class="sxs-lookup"><span data-stu-id="48a1c-111">Business continuity requirements</span></span>

  - <span data-ttu-id="48a1c-112">Полнота данных</span><span class="sxs-lookup"><span data-stu-id="48a1c-112">Data completeness</span></span>

  - <span data-ttu-id="48a1c-113">Критические данные</span><span class="sxs-lookup"><span data-stu-id="48a1c-113">Data criticality</span></span>

  - <span data-ttu-id="48a1c-114">Требования к переносимости</span><span class="sxs-lookup"><span data-stu-id="48a1c-114">Portability requirements</span></span>

  - <span data-ttu-id="48a1c-115">Ограничения затрат</span><span class="sxs-lookup"><span data-stu-id="48a1c-115">Cost constraints</span></span>

<span data-ttu-id="48a1c-116">Бизнес-потребности, такие как эти сведения помогут вам определить соглашения об уровне обслуживания, разработанные для клиентов.</span><span class="sxs-lookup"><span data-stu-id="48a1c-116">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="48a1c-117">Соглашение об уровне обслуживания сильно влияет на стратегию резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="48a1c-117">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="48a1c-118">Определение требований к резервному копированию и восстановлению</span><span class="sxs-lookup"><span data-stu-id="48a1c-118">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="48a1c-119">Ваши бизнес-приоритеты и соглашения об уровне обслуживания определяют требования Организации к резервному и восстановлению сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="48a1c-119">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="48a1c-120">Определите и Задокументируйте требования, указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="48a1c-120">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="48a1c-121">**Периодичность**   создания резервных копий дополнительные сведения о том, как [создавать резервные копии и восстановление для Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md), приведены в разделе Советы и рекомендации по их использованию.</span><span class="sxs-lookup"><span data-stu-id="48a1c-121">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="48a1c-122">**Средства резервного копирования и восстановления**   включают пользователей, которые должны использовать инструменты, и компьютеры.</span><span class="sxs-lookup"><span data-stu-id="48a1c-122">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="48a1c-123">Сведения о средствах и разрешениях, описанных в этом разделе, и необходимые разрешения описаны в статье [требования к резервному копированию и восстановлению в Lync Server 2013: инструменты и разрешения](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="48a1c-123">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="48a1c-124">**Расположение резервной копии**   определение того, хранятся ли резервные копии локально или удаленно, с учетом безопасности и специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="48a1c-124">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="48a1c-125">Укажите носитель, который будет использоваться для резервных копий.</span><span class="sxs-lookup"><span data-stu-id="48a1c-125">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="48a1c-126">**Требования к оборудованию и программному обеспечению**   определяют и задокументированы конкретные требования к оборудованию и программному обеспечению, включая оборудование для хранения резервных копий и восстановление конкретных компонентов, а также любые программы и сетевые подключения, необходимые для поддерживает резервное копирование и восстановление.</span><span class="sxs-lookup"><span data-stu-id="48a1c-126">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="48a1c-127">По мере разработки требований к оборудованию и программному обеспечению следует помнить о различных сценариях восстановления, которые следуют за этим.</span><span class="sxs-lookup"><span data-stu-id="48a1c-127">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="48a1c-128">**Сценарии восстановления ниже**   описаны процедуры восстановления для следующих сценариев:</span><span class="sxs-lookup"><span data-stu-id="48a1c-128">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="48a1c-129">Пул Lync Server завершает работу со сбоем.</span><span class="sxs-lookup"><span data-stu-id="48a1c-129">A Lync Server pool fails.</span></span> <span data-ttu-id="48a1c-130">Для этого сценария необходимо перестраивать каждый сервер в пуле.</span><span class="sxs-lookup"><span data-stu-id="48a1c-130">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="48a1c-131">Сервер Standard Edition завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="48a1c-131">A Standard Edition server fails.</span></span> <span data-ttu-id="48a1c-132">Этот сценарий требует перестройки сервера на новом или очистке компьютера и восстановлении баз данных.</span><span class="sxs-lookup"><span data-stu-id="48a1c-132">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="48a1c-133">Потеря хранилища центрального управления.</span><span class="sxs-lookup"><span data-stu-id="48a1c-133">Loss of the Central Management store.</span></span> <span data-ttu-id="48a1c-134">Как минимум, этот сценарий требует восстановления и публикации хранилища центрального управления.</span><span class="sxs-lookup"><span data-stu-id="48a1c-134">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="48a1c-135">Потеря обратного сервера, когда хранилище Центрального управления продолжает работать нормально.</span><span class="sxs-lookup"><span data-stu-id="48a1c-135">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="48a1c-136">Этот сценарий требует перестройки сервера на новом или очистке компьютера и восстановлении баз данных.</span><span class="sxs-lookup"><span data-stu-id="48a1c-136">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="48a1c-137">Сервер, который входит в состав пула Lync Server, завершает работу со сбоем.</span><span class="sxs-lookup"><span data-stu-id="48a1c-137">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="48a1c-138">Для этого сценария требуется перестроение сервера на новом или пустом компьютере.</span><span class="sxs-lookup"><span data-stu-id="48a1c-138">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="48a1c-139">Не удается сохранить файл.</span><span class="sxs-lookup"><span data-stu-id="48a1c-139">A File Store fails.</span></span> <span data-ttu-id="48a1c-140">Для этого сценария требуется восстановление файлового сервера или кластера файлов.</span><span class="sxs-lookup"><span data-stu-id="48a1c-140">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="48a1c-141">Не удается выполнить архивацию, мониторинг или сохраняемость базы данных чата.</span><span class="sxs-lookup"><span data-stu-id="48a1c-141">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="48a1c-142">Этот сценарий требует повторного создания баз данных и, если данные важны для Организации, — для восстановления данных.</span><span class="sxs-lookup"><span data-stu-id="48a1c-142">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="48a1c-143">Архивация, мониторинг и сохраняемые данные чата не требуются для того, чтобы получить доступ к серверу Lync Server и запустить его.</span><span class="sxs-lookup"><span data-stu-id="48a1c-143">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

