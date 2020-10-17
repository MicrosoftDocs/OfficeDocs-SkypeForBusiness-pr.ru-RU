---
title: 'Lync Server 2013: определение и Настройка топологии'
description: 'Lync Server 2013: определение и Настройка топологии.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec444a1ddf434c5a80fdc2d56bdba27573da14ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542085"
---
# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a><span data-ttu-id="0e7f1-103">Определение и Настройка топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e7f1-103">Defining and configuring the topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e7f1-104">_**Последнее изменение темы:** 2012-09-14_</span><span class="sxs-lookup"><span data-stu-id="0e7f1-104">_**Topic Last Modified:** 2012-09-14_</span></span>

<span data-ttu-id="0e7f1-105">Вы определяете и настраиваете топологию с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="0e7f1-105">You define and configure your topology by using Topology Builder.</span></span> <span data-ttu-id="0e7f1-106">В построителе топологий не требуется входить в группу "Локальные администраторы" или "Привилегированный домен" (например, "Администраторы домена").</span><span class="sxs-lookup"><span data-stu-id="0e7f1-106">Topology Builder does not require you to be a member of the local Administrators group or a privileged domain group (such as Domain Admins).</span></span> <span data-ttu-id="0e7f1-107">Топологию может задавать стандартный пользователь.</span><span class="sxs-lookup"><span data-stu-id="0e7f1-107">You can define your topology as a standard user.</span></span> <span data-ttu-id="0e7f1-108">При запуске построителя топологий при первом использовании и в последующих сеансах редактирования, отображается запрос на ввод расположения, из которого построитель топологий должен загрузить текущий документ конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0e7f1-108">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="0e7f1-109">Могут быть следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="0e7f1-109">The choices are the following:</span></span>

  - <span data-ttu-id="0e7f1-110">загрузка топологии из существующего развертывания;</span><span class="sxs-lookup"><span data-stu-id="0e7f1-110">Download topology from existing deployment</span></span>

  - <span data-ttu-id="0e7f1-111">открытие топологии из локального файла;</span><span class="sxs-lookup"><span data-stu-id="0e7f1-111">Open topology from a local file</span></span>

  - <span data-ttu-id="0e7f1-112">новая топология.</span><span class="sxs-lookup"><span data-stu-id="0e7f1-112">New topology</span></span>

<span data-ttu-id="0e7f1-113">Если вы уже определили топологию и установили центральное хранилище управления, необходимо выбрать загрузку топологии из существующего развертывания.</span><span class="sxs-lookup"><span data-stu-id="0e7f1-113">If you have already defined a topology and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="0e7f1-114">Построитель топологии прочитает базу данных и извлечет текущее определение.</span><span class="sxs-lookup"><span data-stu-id="0e7f1-114">Topology Builder will read the database and retrieve the current definition.</span></span> <span data-ttu-id="0e7f1-115">При наличии существующего центрального хранилища управления всегда следует выбирать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="0e7f1-115">If you have an existing Central Management store, you should always choose this option.</span></span>

<span data-ttu-id="0e7f1-116">Если вы не настроили центральное хранилище управления и хотите изменить ранее сохраненную конфигурацию, необходимо выбрать вариант Открыть топологию из локального файла.</span><span class="sxs-lookup"><span data-stu-id="0e7f1-116">If you have not established a Central Management store and want to edit a previously saved configuration, you should choose to open the topology from a local file.</span></span> <span data-ttu-id="0e7f1-117">Открываться будет файл конфигурации, сохраненный в предыдущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="0e7f1-117">The file that you will open would be the configuration file that was saved in a previous session.</span></span> <span data-ttu-id="0e7f1-118">Этот вариант можно использовать для изменения ранее сохраненной топологии.</span><span class="sxs-lookup"><span data-stu-id="0e7f1-118">You can use this option to edit the previously saved topology.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0e7f1-p104">Если имеется уже опубликованная топология, то не следует загружать локальный файл конфигурации. Необходимо выбрать загрузку топологии из существующего развертывания.</span><span class="sxs-lookup"><span data-stu-id="0e7f1-p104">If you already have a published topology, you should not load a local configuration file. You should choose to download the topology from an existing deployment.</span></span>



</div>

<span data-ttu-id="0e7f1-121">Выберите, чтобы создать новую топологию, если вы хотите создать новую конфигурацию построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="0e7f1-121">Choose to create a new topology, if you want to create a new Topology Builder configuration.</span></span> <span data-ttu-id="0e7f1-122">Ранее сохраненная конструкция не переопределяется, пока не будет указано сохранить новую топологию в файл, созданный в предыдущем сеансе разработки.</span><span class="sxs-lookup"><span data-stu-id="0e7f1-122">A previously saved design is not overwritten unless you choose to save it as the same file that you created in an earlier design session.</span></span>

<span data-ttu-id="0e7f1-123">В каждом из этих параметров будет предложено указать расположение для хранения файла конфигурации построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="0e7f1-123">In each of these options, you will be prompted for a location to store the Topology Builder configuration file.</span></span> <span data-ttu-id="0e7f1-124">Это может быть локальное расположение, общедоступное расположение в установленной общей папке или съемный носитель.</span><span class="sxs-lookup"><span data-stu-id="0e7f1-124">The location for the file could be a local location, a shared location on an established file share, or removable media.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0e7f1-125">Содержание</span><span class="sxs-lookup"><span data-stu-id="0e7f1-125">In This Section</span></span>

  - [<span data-ttu-id="0e7f1-126">Определение и Настройка топологии в построителе топологий для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e7f1-126">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [<span data-ttu-id="0e7f1-127">Определение и Настройка пула переднего плана или сервера Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e7f1-127">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="0e7f1-128">Развертывание подключенных пулов переднего плана для аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e7f1-128">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [<span data-ttu-id="0e7f1-129">Развертывание зеркального отображения SQL для обеспечения высокой доступности внутреннего сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e7f1-129">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [<span data-ttu-id="0e7f1-130">Изменение или Настройка простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e7f1-130">Edit or configure simple URLs in Lync Server 2013</span></span>](lync-server-2013-edit-or-configure-simple-urls.md)

  - [<span data-ttu-id="0e7f1-131">Выбор центрального сервера управления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e7f1-131">Select the Central Management Server in Lync Server 2013</span></span>](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

