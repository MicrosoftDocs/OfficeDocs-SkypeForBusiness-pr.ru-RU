---
title: 'Lync Server 2013: Настройка хранилища для архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6f299b01b95cddd461893b35518e3c2fe40c694
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a><span data-ttu-id="46a54-102">Настройка хранилища для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46a54-102">Setting up storage for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46a54-103">_**Последнее изменение темы:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="46a54-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="46a54-104">Хранилище архивации для Lync Server 2013 включает следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="46a54-104">Archiving storage for Lync Server 2013 includes the following:</span></span>

  - <span data-ttu-id="46a54-105">\*\*\*\*   Хранилище данных хранилища данных требуется для хранения содержимого для обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="46a54-105">**Data storage**   Data storage is required to store IM content.</span></span>

  - <span data-ttu-id="46a54-106">\*\*\*\* Для хранения данных и хранилища файлов контента для конференц-связи (собраний) требуется хранилище файлов хранилища.   </span><span class="sxs-lookup"><span data-stu-id="46a54-106">**File storage**   File storage is required to store conferencing (meeting) content data storage and file storage.</span></span>

<div>

## <a name="setting-up-data-storage"></a><span data-ttu-id="46a54-107">Настройка хранилища данных</span><span class="sxs-lookup"><span data-stu-id="46a54-107">Setting Up Data Storage</span></span>

<span data-ttu-id="46a54-108">Требования для настройки хранения данных для архивации в Lync Server 2013 зависят от того, как будут храниться данные архивации.</span><span class="sxs-lookup"><span data-stu-id="46a54-108">Requirements for setting up data storage for Archiving in Lync Server 2013 depend on how you want to store archiving data:</span></span>

  - <span data-ttu-id="46a54-109">Интеграция сервера Lync Server 2013 Архивация с развертыванием Exchange для хранения архивных данных с помощью хранилища Exchange.</span><span class="sxs-lookup"><span data-stu-id="46a54-109">Integrate Lync Server 2013 Archiving with your Exchange deployment to store Archiving data using Exchange storage.</span></span>

  - <span data-ttu-id="46a54-110">Настройте отдельные серверы баз данных SQL Server для хранения архивных данных.</span><span class="sxs-lookup"><span data-stu-id="46a54-110">Set up separate SQL Server database servers to store Archiving data.</span></span>

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a><span data-ttu-id="46a54-111">Настройка хранилищ Exchange для архивации данных</span><span class="sxs-lookup"><span data-stu-id="46a54-111">Setting Up Exchange Storage for Archiving Data</span></span>

<span data-ttu-id="46a54-112">Для настройки Exchange для хранения архивных данных необходимо, чтобы в развертывании Exchange выполнялся Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="46a54-112">Setting up Exchange for storage of Archiving data requires that your Exchange deployment is running Exchange 2013.</span></span> <span data-ttu-id="46a54-113">Кроме того, почтовые ящики пользователей должны быть размещены на сервере Exchange 2013 и их почтовые ящики должны быть размещены на удержании на месте.</span><span class="sxs-lookup"><span data-stu-id="46a54-113">Additionally, user mailboxes must be homed on the Exchange 2013 server and their mailboxes must be put on In-Place Hold.</span></span> <span data-ttu-id="46a54-114">Более подробную информацию о настройке Exchange 2013 вы найдете в документации по продукту Exchange.</span><span class="sxs-lookup"><span data-stu-id="46a54-114">For details about configuring Exchange 2013, see the Exchange product documentation.</span></span>

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a><span data-ttu-id="46a54-115">Настройка серверов баз данных SQL Server для хранения данных архивации</span><span class="sxs-lookup"><span data-stu-id="46a54-115">Setting Up SQL Server Database Servers for Storage of Archiving Data</span></span>

<span data-ttu-id="46a54-116">Для архивации в Lync Server 2013 необходимо, чтобы программное обеспечение баз данных SQL Server сохранит архивные данные, если вы не интегрируете развертывание с Exchange.</span><span class="sxs-lookup"><span data-stu-id="46a54-116">Archiving in Lync Server 2013 requires the SQL Server database software to store the archived data, unless you integrate your deployment with Exchange.</span></span>

<span data-ttu-id="46a54-117">Для баз данных архивации SQL Server необходимо установить SQL Server на компьютере, на котором будет размещаться база данных архивации.</span><span class="sxs-lookup"><span data-stu-id="46a54-117">For SQL Server archiving databases, you must install SQL Server on the computer that will host the Archiving database.</span></span> <span data-ttu-id="46a54-118">Можно использовать тот же экземпляр SQL, который используется для серверной базы данных пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="46a54-118">You can use the same SQL instance that you use for the back-end database of a Front End pool.</span></span> <span data-ttu-id="46a54-119">Для повышения производительности необходимо развернуть базу данных архивации на компьютере, который отделен от центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="46a54-119">For best performance, you should deploy the Archiving database on a computer that is separate from the Central Management store.</span></span> <span data-ttu-id="46a54-120">Подробнее о совместном размещении компонентов Lync Server 2013 можно узнать в статье Supported [выровненный сервер в Lync server 2013](lync-server-2013-supported-server-collocation.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="46a54-120">For details about collocating Lync Server 2013 components, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="46a54-121">На каждом сервере баз данных должна работать поддерживаемая версия SQL Server.</span><span class="sxs-lookup"><span data-stu-id="46a54-121">Each database server must be running a supported version of SQL Server.</span></span> <span data-ttu-id="46a54-122">Дополнительные сведения о поддерживаемых версиях приведены в статье [технические требования для архивации в Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="46a54-122">For details about the supported versions, see [Technical requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="46a54-123">Перед развертыванием и включением архивации необходимо настроить платформы SQL Server.</span><span class="sxs-lookup"><span data-stu-id="46a54-123">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="46a54-124">Если у учетной записи, которая будет использоваться для публикации топологии, есть необходимые права и разрешения администратора, вы можете создать базу данных архивации (LcsLog) при публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="46a54-124">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="46a54-125">Вы также можете создать базу данных потом, например во время установки.</span><span class="sxs-lookup"><span data-stu-id="46a54-125">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="46a54-126">Подробные сведения о SQL Server можно найти в техническом центре SQL Server [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045)по адресу.</span><span class="sxs-lookup"><span data-stu-id="46a54-126">For details about SQL Server, see the SQL Server TechCenter at [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46a54-127">Убедитесь, что тип запуска службы агента SQL Server является автоматическим, а служба агента SQL Server запущена для экземпляра SQL, на котором хранится база данных архивации, чтобы можно было выполнять задание по умолчанию для архивации SQL Server по умолчанию на уровне Управление службой агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="46a54-127">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Archiving database, so that the Default Archiving SQL Server Maintenance Job can run on its scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a><span data-ttu-id="46a54-128">Настройка хранилища файлов</span><span class="sxs-lookup"><span data-stu-id="46a54-128">Setting Up File Storage</span></span>

<span data-ttu-id="46a54-129">При архивации используется общий файловый ресурс Lync Server 2013, который вы указали при настройке пула переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="46a54-129">Archiving uses the Lync Server 2013 file share that you specified when you set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="46a54-130">Общую папку, используемую для архивации, нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="46a54-130">You cannot change the file share used for Archiving.</span></span> <span data-ttu-id="46a54-131">Подробнее о поддерживаемых системах хранения файлов можно узнать [в статье поддержка хранения файлов в Lync Server 2013](lync-server-2013-file-storage-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="46a54-131">For details about supported file storage systems, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

