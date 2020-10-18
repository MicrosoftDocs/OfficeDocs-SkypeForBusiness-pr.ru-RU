---
title: 'Lync Server 2013: технические требования для архивации'
description: 'Lync Server 2013: технические требования для архивации.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6100753ad2c62424eb68c8c258094ba51848170e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577175"
---
# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="8866f-103">Технические требования для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8866f-103">Technical requirements for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8866f-104">_**Последнее изменение темы:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="8866f-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="8866f-105">Lync Server 2013 технические требования включают следующее:</span><span class="sxs-lookup"><span data-stu-id="8866f-105">Lync Server 2013 technical requirements include the following:</span></span>

  - <span data-ttu-id="8866f-106">требования к инфраструктуре;</span><span class="sxs-lookup"><span data-stu-id="8866f-106">Infrastructure requirements.</span></span>

  - <span data-ttu-id="8866f-107">необходимое программное обеспечение, которое должны быть установлены для архивации;</span><span class="sxs-lookup"><span data-stu-id="8866f-107">Prerequisite software that must be installed for Archiving.</span></span>

  - <span data-ttu-id="8866f-108">требования к хранилищу для архивации;</span><span class="sxs-lookup"><span data-stu-id="8866f-108">Data storage requirements for Archiving.</span></span>

  - <span data-ttu-id="8866f-109">требования к масштабированию и рекомендации для развертывания архивации;</span><span class="sxs-lookup"><span data-stu-id="8866f-109">Scaling requirements and considerations for your Archiving deployment.</span></span>

  - <span data-ttu-id="8866f-110">требования к производительности и рекомендации для баз данных архивации.</span><span class="sxs-lookup"><span data-stu-id="8866f-110">Performance requirements and considerations for your Archiving databases.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8866f-111">Сведения о масштабировании и производительности недоступны в этом выпуске Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8866f-111">Scaling and performance information is not available in this Lync Server 2013 release.</span></span>



</div>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="8866f-112">Требования к инфраструктуре</span><span class="sxs-lookup"><span data-stu-id="8866f-112">Infrastructure Requirements</span></span>

<span data-ttu-id="8866f-113">Требования к инфраструктуре архивации Lync Server 2013 такие же, как и для развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8866f-113">Lync Server 2013 Archiving infrastructure requirements are the same as for deployment of Lync Server 2013.</span></span> <span data-ttu-id="8866f-114">Дополнительные сведения приведены в статье [Определение требований к инфраструктуре для Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="8866f-114">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-prerequisites"></a><span data-ttu-id="8866f-115">Необходимые компоненты для архивации</span><span class="sxs-lookup"><span data-stu-id="8866f-115">Archiving Prerequisites</span></span>

<span data-ttu-id="8866f-116">Lync Server 2013 оптимизирует предварительные требования для архивации из-за следующих условий:</span><span class="sxs-lookup"><span data-stu-id="8866f-116">Lync Server 2013 streamlines prerequisites for Archiving because of the following:</span></span>

  - <span data-ttu-id="8866f-p102">Сервер архивации больше не является ролью сервера. Вместо этого агенты единой системы сбора данных выполняются на интерфейсных серверах в пуле и на серверах Standard Edition для захвата данных для архивации, поэтому вам не нужно настраивать отдельные платформы для архивации.</span><span class="sxs-lookup"><span data-stu-id="8866f-p102">Archiving Server is no longer a server role. Instead, Unified Data Collection Agents run on the Front End Servers in a pool and Standard Edition servers to capture data for Archiving, so you do not set up separate system platforms for Archiving.</span></span>

  - <span data-ttu-id="8866f-119">При архивации используется хранилище файлов Lync Server 2013 для временного хранения файлов контента собраний, поэтому не нужно настраивать отдельное хранилище файлов для архивации.</span><span class="sxs-lookup"><span data-stu-id="8866f-119">Archiving uses the Lync Server 2013 file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>

  - <span data-ttu-id="8866f-120">В Lync Server 2013 очередь сообщений не является обязательной.</span><span class="sxs-lookup"><span data-stu-id="8866f-120">In Lync Server 2013, Message Queuing is not required.</span></span>

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a><span data-ttu-id="8866f-121">Требования к хранилищу для архивации</span><span class="sxs-lookup"><span data-stu-id="8866f-121">Data Storage Requirements for Archiving</span></span>

<span data-ttu-id="8866f-p103">Кроме того, необходимо настроить инфраструктуру для хранилища архивации. Для этого необходимо выполнить одно или оба следующих действия:</span><span class="sxs-lookup"><span data-stu-id="8866f-p103">Additionally, you need to set up the infrastructure for Archiving storage. This includes one or both of the following:</span></span>

  - <span data-ttu-id="8866f-124">**Хранилище Microsoft Exchange**.</span><span class="sxs-lookup"><span data-stu-id="8866f-124">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="8866f-125">Файлы содержимого собраний, например презентации PowerPoint, архивируются как вложения.</span><span class="sxs-lookup"><span data-stu-id="8866f-125">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="8866f-126">Если вы хотите использовать интеграцию Microsoft Exchange для хранения архивных данных Lync с помощью данных соответствия требованиям Exchange, необходимо использовать Exchange 2013 для развертывания Exchange и гарантировать, что максимальный размер хранилища для файлов контента собраний поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8866f-126">If you want to use Microsoft Exchange integration so that Lync archive data is stored with Exchange compliance data, you must use Exchange 2013 for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="8866f-127">Если вы развертываете архивацию с помощью параметра интеграции с Microsoft Exchange, архивные данные Lync хранятся только с данными соответствия требованиям Exchange 2013 для пользователей, размещенных на серверах Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="8866f-127">If you deploy Archiving using the Microsoft Exchange integration option, Lync archive data is stored with Exchange 2013 compliance data only for the users who are homed on your Exchange 2013 servers.</span></span> <span data-ttu-id="8866f-128">Перед развертыванием и включением архивации с помощью функции интеграции с Microsoft Exchange необходимо развернуть Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="8866f-128">You must deploy Exchange 2013 prior to deploying and enabling Archiving using the Microsoft Exchange integration option.</span></span> <span data-ttu-id="8866f-129">Если вы решили использовать хранилище Exchange 2013, то нет необходимости развертывать отдельные базы данных SQL Server для архивации, если пользователи Lync не размещены на серверах Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="8866f-129">If you choose to use Exchange 2013 storage, you do not need to deploy separate SQL Server databases for Archiving, unless you have Lync users who are not homed on your Exchange 2013 servers.</span></span>

  - <span data-ttu-id="8866f-130">**Хранилище базы данных SQL Server для архивации**.</span><span class="sxs-lookup"><span data-stu-id="8866f-130">**SQL Server database storage for Archiving**.</span></span> <span data-ttu-id="8866f-131">Для поддержки пользователей, которые не размещены на серверах Exchange 2013, или если вы не хотите использовать интеграцию Microsoft Exchange, необходимо развернуть хранилище архивации с помощью базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8866f-131">To support users who are not homed on Exchange 2013 servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy Archiving storage using a SQL Server database.</span></span> <span data-ttu-id="8866f-132">Lync Server 2013 поддерживает следующие 64 — поразрядные версии SQL Server:</span><span class="sxs-lookup"><span data-stu-id="8866f-132">Lync Server 2013 supports the following 64-bit versions of SQL Server:</span></span>
    
      - <span data-ttu-id="8866f-133">Microsoft SQL Server 2008 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8866f-133">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
      - <span data-ttu-id="8866f-134">Microsoft SQL Server 2008 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="8866f-134">Microsoft SQL Server 2008 R2 Standard</span></span>
    
      - <span data-ttu-id="8866f-135">Microsoft SQL Server 2012 корпоративный</span><span class="sxs-lookup"><span data-stu-id="8866f-135">Microsoft SQL Server 2012 Enterprise</span></span>
    
      - <span data-ttu-id="8866f-136">Microsoft SQL Server 2012 Стандартный</span><span class="sxs-lookup"><span data-stu-id="8866f-136">Microsoft SQL Server 2012 Standard</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8866f-137">Microsoft SQL Server 2008 R2 Express и Microsoft SQL Server 2012 Express не поддерживаются для архивации.</span><span class="sxs-lookup"><span data-stu-id="8866f-137">Microsoft SQL Server 2008 R2 Express and Microsoft SQL Server 2012 Express are not supported for Archiving.</span></span> <span data-ttu-id="8866f-138">32 – разрядные версии SQL Server не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="8866f-138">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="8866f-139">Дополнительные требования и ограничения SQL Server представлены в разделе <A href="lync-server-2013-database-software-support.md">Поддержка программного обеспечения баз данных в Lync Server 2013</A> в документации по планированию или в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="8866f-139">For additional SQL Server requirements and restrictions, see <A href="lync-server-2013-database-software-support.md">Database software support in Lync Server 2013</A> in the Planning documentation or in the Supportability documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="8866f-140">Перед развертыванием и включением архивации необходимо настроить платформы SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8866f-140">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="8866f-141">Если у учетной записи, которая будет использоваться для публикации топологии, есть необходимые права и разрешения администратора, вы можете создать базу данных архивации (LcsLog) при публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="8866f-141">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="8866f-142">Вы также можете создать базу данных потом, например во время установки.</span><span class="sxs-lookup"><span data-stu-id="8866f-142">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="8866f-143">Подробные сведения о SQL Server можно найти в техническом центре SQL Server по адресу [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) .</span><span class="sxs-lookup"><span data-stu-id="8866f-143">For details about SQL Server, see the SQL Server TechCenter at [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

