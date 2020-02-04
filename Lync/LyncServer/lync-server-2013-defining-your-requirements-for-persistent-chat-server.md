---
title: 'Lync Server 2013: определение своих требований для сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0e7482ab85b72168e990eaa97b2f79cb3665532
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="45b05-102">Определение требований организации для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45b05-102">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45b05-103">_**Тема последнего изменения:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="45b05-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="45b05-104">Прежде чем развертывать сохраняемый сервер чата для своей организации, необходимо выполнить указанные ниже ключевые вопросы, чтобы оптимизировать развертывание.</span><span class="sxs-lookup"><span data-stu-id="45b05-104">Before you deploy Persistent Chat Server for your organization, it’s essential to consider the following key questions to optimize your deployment:</span></span>

  - <span data-ttu-id="45b05-105">Кто (профиль пользователя) должен быть включен для постоянного сервера чата?</span><span class="sxs-lookup"><span data-stu-id="45b05-105">Who (user profile) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="45b05-106">Сервер сохраняемого чата поддерживается политикой, которая может быть задана на глобальном уровне, сайте, пуле или пользователе.</span><span class="sxs-lookup"><span data-stu-id="45b05-106">Persistent Chat Server is enabled by a policy that can be set at a Global, Site, Pool or User level.</span></span>

  - <span data-ttu-id="45b05-107">Количество пользователей (шкалы), которые должны быть включены для постоянного сервера чата?</span><span class="sxs-lookup"><span data-stu-id="45b05-107">How many users (scale) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="45b05-108">Сервер сохраняемого чата поддерживает пользователей, предоставилых 150 000 (включенных в политику), и максимальное 80 000 количество одновременных пользователей, использующих сохраняемый сервер чата.</span><span class="sxs-lookup"><span data-stu-id="45b05-108">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users using Persistent Chat Server.</span></span> <span data-ttu-id="45b05-109">Отдельный сервер сохраняемого чата может поддерживать до 20 000 подключенных пользователей, а отдельный пул серверов сохраняемого чата может иметь до 4 активных серверов, что в совокупности составляет 80 000 одновременно подключенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="45b05-109">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>

  - <span data-ttu-id="45b05-110">Выполняется ли переход с предыдущей версии сервера группового чата или вы развертываете сохраняемый сервер чата в первый раз?</span><span class="sxs-lookup"><span data-stu-id="45b05-110">Are you migrating from a previous version of Group Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>

  - <span data-ttu-id="45b05-111">Соблюдены ли требования для соответствия требованиям?</span><span class="sxs-lookup"><span data-stu-id="45b05-111">Are there compliance requirements?</span></span> <span data-ttu-id="45b05-112">Сервер сохраняемого чата поддерживает соответствие требованиям.</span><span class="sxs-lookup"><span data-stu-id="45b05-112">Persistent Chat Server supports compliance.</span></span> <span data-ttu-id="45b05-113">Служба соответствия будет размещена на сервере клиентского доступа на постоянной версии, а не на отдельном компьютере в предыдущих развертываниях сервера группового чата.</span><span class="sxs-lookup"><span data-stu-id="45b05-113">The compliance service runs collocated on the Persistent Chat Server Front End Server, as opposed to the requirement for a separate computer in previous Group Chat Server deployments.</span></span> <span data-ttu-id="45b05-114">Соответствие обязательным, и, если оно выбрано, требуется база данных соответствия требованиям, которая должна быть настроена для хранения данных о соответствии требованиям и событий.</span><span class="sxs-lookup"><span data-stu-id="45b05-114">Compliance is optional, and if chosen, requires a compliance database that must be configured to store compliance data and events.</span></span> <span data-ttu-id="45b05-115">Вы также можете настроить адаптер таким образом, чтобы он мог принимать данные из базы данных соответствия требованиям и преобразовывать их в другой формат (например, XML-файлы или архивы Exchange).</span><span class="sxs-lookup"><span data-stu-id="45b05-115">You may want to also configure an adapter to take the data from the compliance database and convert to another format (such as XML files or Exchange-hosted archives).</span></span>

  - <span data-ttu-id="45b05-116">Каким образом можно контролировать сферу применения, этические нормы и права доступа?</span><span class="sxs-lookup"><span data-stu-id="45b05-116">How do you want to control scopes, ethical boundaries, and access?</span></span> <span data-ttu-id="45b05-117">Вы можете определить **категории** , чтобы выделять эти границы, и выбрать, кто может находиться в каждой из этих категорий.</span><span class="sxs-lookup"><span data-stu-id="45b05-117">You can define **Categories** to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>

  - <span data-ttu-id="45b05-118">Как можно управлять правами на создание комнат?</span><span class="sxs-lookup"><span data-stu-id="45b05-118">How do you want to control who can create rooms?</span></span> <span data-ttu-id="45b05-119">Вы можете настроить **Создатели**, соответствующие категориям, которые могут создавать комнаты.</span><span class="sxs-lookup"><span data-stu-id="45b05-119">You can configure **Creators**, appropriate to your categories, who can create rooms.</span></span> <span data-ttu-id="45b05-120">Создатели могут назначать других участников в качестве **руководителей комнаты чата** для постоянного управления комнатами (добавления или удаления дополнительных участников) в соответствии с областью для **алловедмемберс/дениедмемберс** , настроенной категорией.</span><span class="sxs-lookup"><span data-stu-id="45b05-120">Creators can assign other members as **Chat Room Managers** for ongoing management of the rooms (adding or removing additional members), according to the scope for **AllowedMembers/DeniedMembers** configured by the category.</span></span>

  - <span data-ttu-id="45b05-121">Как вы хотите создавать помещения?</span><span class="sxs-lookup"><span data-stu-id="45b05-121">How do you want to create rooms?</span></span> <span data-ttu-id="45b05-122">Сервер сохраняемого чата предоставляет веб-функцию для создания и управления комнатой.</span><span class="sxs-lookup"><span data-stu-id="45b05-122">Persistent Chat Server provides a web-based feature for room creation and management.</span></span> <span data-ttu-id="45b05-123">Это можно запустить в клиенте Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="45b05-123">This can be launched from the Lync 2013 client.</span></span> <span data-ttu-id="45b05-124">Вы можете определить настраиваемое решение (с помощью пакета средств разработки программного обеспечения (SDK) сервера для бизнеса, в котором реализованы бизнес-требования и рабочие процессы, и настроить сохраняемый сервер чата для направления пользователей в свое собственное решение.</span><span class="sxs-lookup"><span data-stu-id="45b05-124">You can choose to define a custom solution (by using the Persistent Chat Server Software Development Kit (SDK)) that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>

  - <span data-ttu-id="45b05-125">Какие типы надстроек вы хотите подготовить?</span><span class="sxs-lookup"><span data-stu-id="45b05-125">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="45b05-126">**Надстройки** расширяют возможности в комнате, используя область расширяемости в клиенте Lync 2013 для обеспечения контекста, связанного с комнатой.</span><span class="sxs-lookup"><span data-stu-id="45b05-126">**Add-ins** enhance the in-room experience by leveraging the extensibility pane in the Lync 2013 client to provide context that is relevant to the room.</span></span> <span data-ttu-id="45b05-127">Можно указать, какие общие надстройки будут наиболее полезными (например, веб-сайт компании, внутренние документы для совместной работы и т. д.).</span><span class="sxs-lookup"><span data-stu-id="45b05-127">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="45b05-128">Диспетчеры комнат чата могут выбирать зарегистрированные надстройки и сопоставлять их с комнатами, если требуется.</span><span class="sxs-lookup"><span data-stu-id="45b05-128">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span>

  - <span data-ttu-id="45b05-129">Какие предъявляются требования к высокой доступности и аварийному восстановлению?</span><span class="sxs-lookup"><span data-stu-id="45b05-129">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="45b05-130">Сервер сохраняемого чата поддерживает зеркальное отображение SQL Server и кластеризацию SQL Server для обеспечения высокой доступности и поддерживает до 8 серверов (4 активных и 4 режимов) в растянутом пуле с доставкой журналов SQL Server для аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="45b05-130">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability and supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping for disaster recovery.</span></span>

  - <span data-ttu-id="45b05-131">Существуют ли нормативные требования?</span><span class="sxs-lookup"><span data-stu-id="45b05-131">Are there regulatory requirements?</span></span> <span data-ttu-id="45b05-132">Если ваша компания находится в стране или регионе, где данные должны храниться в стране, вам может потребоваться развернуть несколько пулов серверов сохраняемого чата, каждый из которых должен быть указан в определенном географическом элементе.</span><span class="sxs-lookup"><span data-stu-id="45b05-132">If your company is in a country/region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="45b05-133">Комната, категория или надстройка не охватывает группы, и она принадлежит только одному пулу серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="45b05-133">A room, category, or add-in does not span pools—it belongs to only one Persistent Chat Server pool.</span></span> <span data-ttu-id="45b05-134">Вы можете управлять набором категорий, надстроек и комнат для каждого пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="45b05-134">You can manage the set of categories, add-ins and rooms for each Persistent Chat Server pool.</span></span> <span data-ttu-id="45b05-135">Пользователи могут быть настроены таким образом, чтобы иметь доступ к комнатам в одном или нескольких пулах, используя область категорий Алловедмемберс область или участие в комнате, в зависимости от того, как вы разрешаете создание категорий.</span><span class="sxs-lookup"><span data-stu-id="45b05-135">Users can be configured to have access to rooms in one or more pools using the category AllowedMembers scope or Room’s membership scope, depending on how you design your categories.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="45b05-136">Если несколько пулов серверов для работы с несколькими пользователями не дают вам больше масштаба (вы можете по-прежнему иметь только 80 000 пользователей, одновременно подключенных к вашим пулам серверов для вашего постоянного чата).</span><span class="sxs-lookup"><span data-stu-id="45b05-136">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrently connected users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="45b05-137">Основная причина поддержки множества пулов серверов для чатов — обеспечение соответствия нормативным требованиям.</span><span class="sxs-lookup"><span data-stu-id="45b05-137">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

