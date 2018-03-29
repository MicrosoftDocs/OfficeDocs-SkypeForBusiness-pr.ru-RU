---
title: Требования к программному обеспечению и оборудованию для архивации в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
description: 'Сводка: Прочтите этот раздел, чтобы узнать о требованиях к оборудованию и программному обеспечению для архивации в Скайп для Business Server 2015.'
ms.openlocfilehash: d8d8039e95a3b578551d0db6ff219fe8f3c1e5c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a><span data-ttu-id="7056a-103">Требования к программному обеспечению и оборудованию для архивации в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="7056a-103">Hardware and software requirements for archiving in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7056a-104">**Сводка:** Прочтите этот раздел, чтобы узнать о требованиях к оборудованию и программному обеспечению для архивации в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7056a-104">**Summary:** Read this topic to learn about hardware and software requirements for archiving in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7056a-105">Скайп для архивации Business Server 2015 теперь является частью роли сервера переднего плана, поэтому необходимо установить на отдельный сервер.</span><span class="sxs-lookup"><span data-stu-id="7056a-105">Skype for Business Server 2015 archiving is now part of the Front End role, so you do not need to install a separate server.</span></span> <span data-ttu-id="7056a-106">Однако необходимо учитывать следующие требования:</span><span class="sxs-lookup"><span data-stu-id="7056a-106">You do, however, need to consider the following requirements:</span></span>
  
- <span data-ttu-id="7056a-107">Требования к инфраструктуре</span><span class="sxs-lookup"><span data-stu-id="7056a-107">Infrastructure requirements</span></span>
    
- <span data-ttu-id="7056a-108">Требования к обязательному программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="7056a-108">Prerequisite software requirements</span></span>
    
- <span data-ttu-id="7056a-109">Требования к хранилищу данных</span><span class="sxs-lookup"><span data-stu-id="7056a-109">Data storage requirements</span></span>
    
## <a name="infrastructure-requirements"></a><span data-ttu-id="7056a-110">Требования к инфраструктуре</span><span class="sxs-lookup"><span data-stu-id="7056a-110">Infrastructure requirements</span></span>

<span data-ttu-id="7056a-111">Скайп для архивации сервера Business требования к инфраструктуре совпадают с требованиями для развертывания Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="7056a-111">Skype for Business Server Archiving infrastructure requirements are the same as for deployment of Skype for Business Server.</span></span> <span data-ttu-id="7056a-112">Дополнительные сведения см [требования к вашей Скайп для бизнес-среде](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7056a-112">For details, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span></span> 
  
## <a name="prerequisite-software-requirements"></a><span data-ttu-id="7056a-113">Требования к обязательному программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="7056a-113">Prerequisite software requirements</span></span>

<span data-ttu-id="7056a-114">Архивации необходимые условия для Скайп для Business Server проще, чем в предыдущих версиях Lync Server по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="7056a-114">Archiving prerequisites for Skype for Business Server are simpler than earlier versions of Lync Server because of the following:</span></span> 
  
- <span data-ttu-id="7056a-115">Так как архивации больше не роль сервера, не нужно установить на отдельный сервер для архивации.</span><span class="sxs-lookup"><span data-stu-id="7056a-115">Because archiving is no longer a server role, you do not need to install a separate server for archiving.</span></span> <span data-ttu-id="7056a-116">Вместо этого агенты единой системы сбора данных устанавливаются и активируются автоматически на серверах переднего плана Enterprise Edition в пуле и на серверах Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7056a-116">Instead, Unified Data Collection Agents are installed and activated automatically on every Enterprise Edition Front End pool and every Standard Edition Server.</span></span> <span data-ttu-id="7056a-117">Вам потребуется активировать и опубликовать вашу топологию архивации с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="7056a-117">You will need to enable and publish your archiving topology by using Topology Builder.</span></span>
    
- <span data-ttu-id="7056a-118">Архивация использует Скайп для хранения файлов Business Server для временного хранения файлы содержимого собраний, поэтому вам не нужно настраивать отдельное файловое хранилище для архивации.</span><span class="sxs-lookup"><span data-stu-id="7056a-118">Archiving uses the Skype for Business Server file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>
    
- <span data-ttu-id="7056a-119">В Скайп для Business Server очереди сообщений не требуется.</span><span class="sxs-lookup"><span data-stu-id="7056a-119">In Skype for Business Server, Microsoft Message Queuing is not required.</span></span>
    
## <a name="data-storage-requirements"></a><span data-ttu-id="7056a-120">Требования к хранилищу данных</span><span class="sxs-lookup"><span data-stu-id="7056a-120">Data Storage requirements</span></span>

<span data-ttu-id="7056a-p104">Необходимо настроить инфраструктуру для хранилища архивации. Для этого следует выбрать один или оба следующих параметра:</span><span class="sxs-lookup"><span data-stu-id="7056a-p104">You will need to set up the infrastructure for archiving storage. This includes choosing one or both of the following options:</span></span>
  
- <span data-ttu-id="7056a-123">**Хранилище Microsoft Exchange**.</span><span class="sxs-lookup"><span data-stu-id="7056a-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="7056a-124">Файлы содержимого собраний, например презентаций PowerPoint, архивируются как вложения.</span><span class="sxs-lookup"><span data-stu-id="7056a-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="7056a-125">Если вы хотите сохранить Скайп для бизнес-данных архива с данные соответствия Exchange, необходимо использовать Exchange для развертывания Exchange и убедитесь, что максимальный размер хранилища поддерживает хранение файлов контента собрания.</span><span class="sxs-lookup"><span data-stu-id="7056a-125">If you want to store Skype for Business archive data with Exchange compliance data, you must use Exchange for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="7056a-126">Необходимо развернуть Exchange перед развертыванием и Включение архивации с помощью параметра интеграции с Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="7056a-126">You must deploy Exchange prior to deploying and enabling archiving using the Microsoft Exchange integration option.</span></span> 
    
    <span data-ttu-id="7056a-127">Если вы решите использовать хранилища Exchange, не нужно развертывать отдельные базы данных SQL Server для архивации, при отсутствии Скайп для бизнес-пользователей, которые не размещаются на серверах Exchange.</span><span class="sxs-lookup"><span data-stu-id="7056a-127">If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers.</span></span> <span data-ttu-id="7056a-128">При развертывании архивации с помощью параметра интеграции с Microsoft Exchange, Скайп для бизнес-данных архива хранится с Exchange данные соответствия только для пользователей, которые размещаются на серверах Exchange.</span><span class="sxs-lookup"><span data-stu-id="7056a-128">If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers.</span></span> 
    
- <span data-ttu-id="7056a-129">**Скайп для архивации хранилища, используемого Business Server**.</span><span class="sxs-lookup"><span data-stu-id="7056a-129">**Skype for Business Server archiving storage**.</span></span> <span data-ttu-id="7056a-130">Для поддержки пользователей, которые не размещаются на серверах Exchange, или если вы не хотите использовать параметра интеграции с Microsoft Exchange, необходимо развернуть архивации хранилища, используемого с помощью базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7056a-130">To support users who are not homed on Exchange servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy archiving storage using a SQL Server database.</span></span> <span data-ttu-id="7056a-131">Скайп для Business Server поддерживает следующие 64-разрядных версиях SQL Server:</span><span class="sxs-lookup"><span data-stu-id="7056a-131">Skype for Business Server supports the following 64-bit versions of SQL Server:</span></span>
    
  - <span data-ttu-id="7056a-132">Microsoft SQL Server 2008 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7056a-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
  - <span data-ttu-id="7056a-133">Microsoft SQL Server 2008 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="7056a-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
  - <span data-ttu-id="7056a-134">Microsoft SQL Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7056a-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
  - <span data-ttu-id="7056a-135">Microsoft SQL Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="7056a-135">Microsoft SQL Server 2012 Standard</span></span>
    
  - <span data-ttu-id="7056a-136">Enterprise Microsoft SQL Server 2014 г.</span><span class="sxs-lookup"><span data-stu-id="7056a-136">Microsoft SQL Server 2014 Enterprise</span></span>
    
  - <span data-ttu-id="7056a-137">Стандартный Microsoft SQL Server 2014 г.</span><span class="sxs-lookup"><span data-stu-id="7056a-137">Microsoft SQL Server 2014 Standard</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7056a-138">Microsoft SQL Server Express версии не поддерживаются для архивации.</span><span class="sxs-lookup"><span data-stu-id="7056a-138">Microsoft SQL Server Express versions are not supported for archiving.</span></span> <span data-ttu-id="7056a-139">32-разрядные версии SQL Server не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="7056a-139">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="7056a-140">Дополнительные требования к SQL Server и ограничения приведены [требования для вашей Скайп для бизнес-среде](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7056a-140">For additional SQL Server requirements and restrictions, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span></span> 
  
    <span data-ttu-id="7056a-141">Необходимо настроить платформах SQL Server перед развертыванием и включение архивирования.</span><span class="sxs-lookup"><span data-stu-id="7056a-141">You must set up the SQL Server platforms prior to deploying and enabling archiving.</span></span> <span data-ttu-id="7056a-142">Если учетная запись, которую планируется использовать для публикации топологии, имеет соответствующие права и разрешения администратора, базу данных архивации (LcsLog) можно создать при публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="7056a-142">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="7056a-143">Базу данных можно создать и позднее в ходе процедуры установки.</span><span class="sxs-lookup"><span data-stu-id="7056a-143">You can also create the database later, included as part of the installation procedure.</span></span> <span data-ttu-id="7056a-144">Дополнительные сведения о SQL Server см [Технический центр по SQL Server](https://go.microsoft.com/fwlink/p/?linkID=129045).</span><span class="sxs-lookup"><span data-stu-id="7056a-144">For details about SQL Server, see the [SQL Server TechCenter](https://go.microsoft.com/fwlink/p/?linkID=129045).</span></span>
    
    <span data-ttu-id="7056a-145">Нагрузка компонента архивации может оказаться значительной.</span><span class="sxs-lookup"><span data-stu-id="7056a-145">The load increase for archiving can be significant.</span></span> <span data-ttu-id="7056a-146">Таким образом необходимо убедиться, что места на диске подходит для серверов переднего плана, на которых включен архивации.</span><span class="sxs-lookup"><span data-stu-id="7056a-146">Therefore, you should ensure that disk space is adequate for Front End Servers on which archiving is enabled.</span></span>
    

