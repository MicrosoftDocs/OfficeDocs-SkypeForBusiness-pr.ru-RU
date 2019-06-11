---
title: 'Lync Server 2013: определение и настройка топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8660ac75e325e5737ceb5df59e9463c88ef1c077
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a><span data-ttu-id="bbe1c-102">Определение и настройка топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbe1c-102">Defining and configuring the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbe1c-103">_**Тема последнего изменения:** 2012-09-14_</span><span class="sxs-lookup"><span data-stu-id="bbe1c-103">_**Topic Last Modified:** 2012-09-14_</span></span>

<span data-ttu-id="bbe1c-104">Вы определяете топологию и настраиваете ее с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="bbe1c-104">You define and configure your topology by using Topology Builder.</span></span> <span data-ttu-id="bbe1c-105">Для Topology Builder не требуется входить в локальную группу администраторов или привилегированную группу домена (например, Администраторы домена).</span><span class="sxs-lookup"><span data-stu-id="bbe1c-105">Topology Builder does not require you to be a member of the local Administrators group or a privileged domain group (such as Domain Admins).</span></span> <span data-ttu-id="bbe1c-106">Вы можете определить свою топологию как обычный пользователь.</span><span class="sxs-lookup"><span data-stu-id="bbe1c-106">You can define your topology as a standard user.</span></span> <span data-ttu-id="bbe1c-107">Когда вы запускаете построитель топологии при первом использовании и последующих сеансах редактирования, вам будет предложено указать расположение, в которое построитель топологии должен загрузить текущий документ конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bbe1c-107">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="bbe1c-108">Доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="bbe1c-108">The choices are the following:</span></span>

  - <span data-ttu-id="bbe1c-109">загрузка топологии из существующего развертывания;</span><span class="sxs-lookup"><span data-stu-id="bbe1c-109">Download topology from existing deployment</span></span>

  - <span data-ttu-id="bbe1c-110">Открытие топологии из локального файла</span><span class="sxs-lookup"><span data-stu-id="bbe1c-110">Open topology from a local file</span></span>

  - <span data-ttu-id="bbe1c-111">Новая топология</span><span class="sxs-lookup"><span data-stu-id="bbe1c-111">New topology</span></span>

<span data-ttu-id="bbe1c-112">Если вы уже определили топологию и установили хранилище Центрального управления, необходимо выбрать загрузку топологии из существующего развертывания.</span><span class="sxs-lookup"><span data-stu-id="bbe1c-112">If you have already defined a topology and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="bbe1c-113">Построитель топологии будет считывать базу данных и получать текущее определение.</span><span class="sxs-lookup"><span data-stu-id="bbe1c-113">Topology Builder will read the database and retrieve the current definition.</span></span> <span data-ttu-id="bbe1c-114">Если у вас есть хранилище Центрального управления, всегда выбирайте этот параметр.</span><span class="sxs-lookup"><span data-stu-id="bbe1c-114">If you have an existing Central Management store, you should always choose this option.</span></span>

<span data-ttu-id="bbe1c-115">Если вы не установили центральное хранилище для управления и хотите изменить ранее сохраненную конфигурацию, необходимо открыть топологию из локального файла.</span><span class="sxs-lookup"><span data-stu-id="bbe1c-115">If you have not established a Central Management store and want to edit a previously saved configuration, you should choose to open the topology from a local file.</span></span> <span data-ttu-id="bbe1c-116">Откроется файл конфигурации, сохраненный в предыдущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="bbe1c-116">The file that you will open would be the configuration file that was saved in a previous session.</span></span> <span data-ttu-id="bbe1c-117">Вы можете использовать этот параметр, чтобы изменить ранее сохраненную топологию.</span><span class="sxs-lookup"><span data-stu-id="bbe1c-117">You can use this option to edit the previously saved topology.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="bbe1c-118">Если у вас уже есть опубликованная топология, не загружайте локальный файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bbe1c-118">If you already have a published topology, you should not load a local configuration file.</span></span> <span data-ttu-id="bbe1c-119">Необходимо выбрать загрузку топологии из существующего развертывания.</span><span class="sxs-lookup"><span data-stu-id="bbe1c-119">You should choose to download the topology from an existing deployment.</span></span>



</div>

<span data-ttu-id="bbe1c-120">Выберите, чтобы создать новую топологию, если вы хотите создать новую конфигурацию построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="bbe1c-120">Choose to create a new topology, if you want to create a new Topology Builder configuration.</span></span> <span data-ttu-id="bbe1c-121">Ранее сохраненный макет не перезаписывается, пока вы не решите сохранить его в том же файле, который вы создали в более раннем сеансе конструирования.</span><span class="sxs-lookup"><span data-stu-id="bbe1c-121">A previously saved design is not overwritten unless you choose to save it as the same file that you created in an earlier design session.</span></span>

<span data-ttu-id="bbe1c-122">В каждом из этих параметров вам будет предложено указать расположение для хранения файла конфигурации построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="bbe1c-122">In each of these options, you will be prompted for a location to store the Topology Builder configuration file.</span></span> <span data-ttu-id="bbe1c-123">Для файла может быть задано локальное расположение, общее расположение в установленном файловом ресурсе или съемном носителе.</span><span class="sxs-lookup"><span data-stu-id="bbe1c-123">The location for the file could be a local location, a shared location on an established file share, or removable media.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bbe1c-124">Содержание</span><span class="sxs-lookup"><span data-stu-id="bbe1c-124">In This Section</span></span>

  - [<span data-ttu-id="bbe1c-125">Определение и настройка топологии в средстве построения топологии для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbe1c-125">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [<span data-ttu-id="bbe1c-126">Определение и настройка пула переднего плана или сервера Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbe1c-126">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="bbe1c-127">Развертывание сопоставленных пулов переднего плана для аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbe1c-127">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [<span data-ttu-id="bbe1c-128">Развертывание зеркального отображения SQL Server для обеспечения высокой доступности внутреннего сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbe1c-128">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [<span data-ttu-id="bbe1c-129">Изменить или настроить простые URL-адреса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbe1c-129">Edit or configure simple URLs in Lync Server 2013</span></span>](lync-server-2013-edit-or-configure-simple-urls.md)

  - [<span data-ttu-id="bbe1c-130">Выбор центрального сервера управления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbe1c-130">Select the Central Management Server in Lync Server 2013</span></span>](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

