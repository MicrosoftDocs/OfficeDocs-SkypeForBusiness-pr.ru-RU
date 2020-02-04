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
ms.openlocfilehash: a5a380ce6c863c54739e74488bfa3b3979664e78
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a><span data-ttu-id="00f2d-102">Настройка хранилища для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00f2d-102">Setting up storage for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00f2d-103">_**Тема последнего изменения:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="00f2d-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="00f2d-104">Архивирование хранилища для Lync Server 2013 включает в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="00f2d-104">Archiving storage for Lync Server 2013 includes the following:</span></span>

  - <span data-ttu-id="00f2d-105">\*\*\*\*   Хранилище данных хранилища данных необходимо для хранения содержимого для обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="00f2d-105">**Data storage**   Data storage is required to store IM content.</span></span>

  - <span data-ttu-id="00f2d-106">\*\*\*\* Хранение файлов в хранилище файлов требуется для хранения данных и хранения файлов в конференц-заходе (собраниях).   </span><span class="sxs-lookup"><span data-stu-id="00f2d-106">**File storage**   File storage is required to store conferencing (meeting) content data storage and file storage.</span></span>

<div>

## <a name="setting-up-data-storage"></a><span data-ttu-id="00f2d-107">Настройка хранилища данных</span><span class="sxs-lookup"><span data-stu-id="00f2d-107">Setting Up Data Storage</span></span>

<span data-ttu-id="00f2d-108">Требования для настройки хранения данных для архивации в Lync Server 2013 зависят от того, как вы хотите хранить данные для архивации.</span><span class="sxs-lookup"><span data-stu-id="00f2d-108">Requirements for setting up data storage for Archiving in Lync Server 2013 depend on how you want to store archiving data:</span></span>

  - <span data-ttu-id="00f2d-109">Интеграция сервера Lync Server 2013 архивирование и развертывание Exchange для хранения данных архивации с помощью Exchange Storage.</span><span class="sxs-lookup"><span data-stu-id="00f2d-109">Integrate Lync Server 2013 Archiving with your Exchange deployment to store Archiving data using Exchange storage.</span></span>

  - <span data-ttu-id="00f2d-110">Настройте отдельные серверы баз данных SQL Server для хранения данных архивации.</span><span class="sxs-lookup"><span data-stu-id="00f2d-110">Set up separate SQL Server database servers to store Archiving data.</span></span>

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a><span data-ttu-id="00f2d-111">Настройка хранилища Exchange для архивации данных</span><span class="sxs-lookup"><span data-stu-id="00f2d-111">Setting Up Exchange Storage for Archiving Data</span></span>

<span data-ttu-id="00f2d-112">Чтобы настроить Exchange для хранения данных архивации, необходимо, чтобы на сервере Exchange Server было установлено приложение Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="00f2d-112">Setting up Exchange for storage of Archiving data requires that your Exchange deployment is running Exchange 2013.</span></span> <span data-ttu-id="00f2d-113">Кроме того, почтовые ящики пользователей должны располагаться на сервере Exchange 2013, а их почтовые ящики должны быть помещены на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="00f2d-113">Additionally, user mailboxes must be homed on the Exchange 2013 server and their mailboxes must be put on In-Place Hold.</span></span> <span data-ttu-id="00f2d-114">Подробные сведения о настройке Exchange 2013 можно найти в документации по продукту Exchange.</span><span class="sxs-lookup"><span data-stu-id="00f2d-114">For details about configuring Exchange 2013, see the Exchange product documentation.</span></span>

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a><span data-ttu-id="00f2d-115">Настройка серверов базы данных SQL Server для хранения данных архивации</span><span class="sxs-lookup"><span data-stu-id="00f2d-115">Setting Up SQL Server Database Servers for Storage of Archiving Data</span></span>

<span data-ttu-id="00f2d-116">Для архивации в Lync Server 2013 необходимо, чтобы программа базы данных SQL Server сохранит архивированные данные, если вы не интегрируете развертывание с Exchange.</span><span class="sxs-lookup"><span data-stu-id="00f2d-116">Archiving in Lync Server 2013 requires the SQL Server database software to store the archived data, unless you integrate your deployment with Exchange.</span></span>

<span data-ttu-id="00f2d-117">Для баз данных архивации SQL Server необходимо установить SQL Server на компьютере, на котором будет размещена база данных архивации.</span><span class="sxs-lookup"><span data-stu-id="00f2d-117">For SQL Server archiving databases, you must install SQL Server on the computer that will host the Archiving database.</span></span> <span data-ttu-id="00f2d-118">Вы можете использовать тот же экземпляр SQL, который вы используете для серверной базы данных в пуле переднего плана.</span><span class="sxs-lookup"><span data-stu-id="00f2d-118">You can use the same SQL instance that you use for the back-end database of a Front End pool.</span></span> <span data-ttu-id="00f2d-119">Для оптимальной производительности следует развернуть базу данных архивации на компьютере, отдельном от хранилища центрального управления.</span><span class="sxs-lookup"><span data-stu-id="00f2d-119">For best performance, you should deploy the Archiving database on a computer that is separate from the Central Management store.</span></span> <span data-ttu-id="00f2d-120">Подробные сведения о размещении компонентов Lync Server 2013 можно найти в разделе Поддерживаемые параметры совместного отображения [серверов в Lync server 2013](lync-server-2013-supported-server-collocation.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="00f2d-120">For details about collocating Lync Server 2013 components, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="00f2d-121">На каждом сервере базы данных должна быть установлена поддерживаемая версия SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00f2d-121">Each database server must be running a supported version of SQL Server.</span></span> <span data-ttu-id="00f2d-122">Подробные сведения о поддерживаемых версиях можно найти в статьях [технические требования для архивации в Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="00f2d-122">For details about the supported versions, see [Technical requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="00f2d-123">Перед развертыванием и включением архивации необходимо настроить платформы SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00f2d-123">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="00f2d-124">Если учетная запись, которую планируется использовать для публикации топологии, имеет соответствующие права и разрешения администратора, базу данных архивации (LcsLog) можно создать при публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="00f2d-124">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="00f2d-125">Кроме того, вы можете создать базу данных позже, в том числе в ходе процедуры установки.</span><span class="sxs-lookup"><span data-stu-id="00f2d-125">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="00f2d-126">Подробные сведения о SQL Server можно найти в центре SQL Server TechCenter [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)по адресу.</span><span class="sxs-lookup"><span data-stu-id="00f2d-126">For details about SQL Server, see the SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="00f2d-127">Убедитесь, что тип запуска службы агента SQL Server является автоматическим, и служба агента SQL Server запущена для экземпляра SQL, который удерживает базу данных архивации, чтобы его можно было использовать по умолчанию для задания обслуживания SQL Server для архивации на основе Управление службой агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00f2d-127">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Archiving database, so that the Default Archiving SQL Server Maintenance Job can run on its scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a><span data-ttu-id="00f2d-128">Настройка хранилища файлов</span><span class="sxs-lookup"><span data-stu-id="00f2d-128">Setting Up File Storage</span></span>

<span data-ttu-id="00f2d-129">При архивации используется общий файловый сервер Lync Server 2013, который вы указали при настройке пула переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="00f2d-129">Archiving uses the Lync Server 2013 file share that you specified when you set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="00f2d-130">Вы не можете изменить общую файловую панель, используемую для архивации.</span><span class="sxs-lookup"><span data-stu-id="00f2d-130">You cannot change the file share used for Archiving.</span></span> <span data-ttu-id="00f2d-131">Подробные сведения о поддерживаемых системах хранения файлов можно найти [в разделе Поддержка хранения файлов в Lync Server 2013](lync-server-2013-file-storage-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="00f2d-131">For details about supported file storage systems, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

