---
title: 'Lync Server 2013: определение требований для сервера сохраняемого чата'
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
ms.openlocfilehash: 15beb7728525fa3e4bb6b75dfc46fb46335d1063
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="ab454-102">Определение требований Организации для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab454-102">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab454-103">_**Последнее изменение темы:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="ab454-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="ab454-104">Перед развертыванием сервера сохраняемого чата для Организации важно учесть следующие ключевые вопросы для оптимизации развертывания:</span><span class="sxs-lookup"><span data-stu-id="ab454-104">Before you deploy Persistent Chat Server for your organization, it’s essential to consider the following key questions to optimize your deployment:</span></span>

  - <span data-ttu-id="ab454-105">Кто (профиль пользователя) должен быть включен для сервера сохраняемого чата?</span><span class="sxs-lookup"><span data-stu-id="ab454-105">Who (user profile) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="ab454-106">Сервер сохраняемого чата включен политикой, которая может быть задана на глобальном уровне, на уровне сайта, в пуле или на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="ab454-106">Persistent Chat Server is enabled by a policy that can be set at a Global, Site, Pool or User level.</span></span>

  - <span data-ttu-id="ab454-107">Сколько пользователей (шкалы) следует включить для сервера сохраняемого чата?</span><span class="sxs-lookup"><span data-stu-id="ab454-107">How many users (scale) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="ab454-108">Сервер сохраняемого чата поддерживает 150 000 подготовленных пользователей (включается в соответствии с политикой) и максимальное количество одновременных пользователей 80 000 с помощью сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="ab454-108">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users using Persistent Chat Server.</span></span> <span data-ttu-id="ab454-109">Один сервер сохраняемого чата может поддерживать подключенных пользователей 20 000, а один пул серверов сохраняемого чата может иметь до 4 активных серверов для всего 80 000 одновременно подключенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="ab454-109">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>

  - <span data-ttu-id="ab454-110">Выполняется ли миграция с предыдущей версии сервера группового чата или развертывание сервера сохраняемого чата в первый раз?</span><span class="sxs-lookup"><span data-stu-id="ab454-110">Are you migrating from a previous version of Group Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>

  - <span data-ttu-id="ab454-111">Существуют ли требования для соответствия требованиям?</span><span class="sxs-lookup"><span data-stu-id="ab454-111">Are there compliance requirements?</span></span> <span data-ttu-id="ab454-112">Сервер сохраняемого чата поддерживает соответствие требованиям.</span><span class="sxs-lookup"><span data-stu-id="ab454-112">Persistent Chat Server supports compliance.</span></span> <span data-ttu-id="ab454-113">Служба соответствия работает на сервере переднего плана сервера сохраняемого чата, а не требование к отдельному компьютеру в предыдущих развертываниях сервера группового чата.</span><span class="sxs-lookup"><span data-stu-id="ab454-113">The compliance service runs collocated on the Persistent Chat Server Front End Server, as opposed to the requirement for a separate computer in previous Group Chat Server deployments.</span></span> <span data-ttu-id="ab454-114">Соответствие является необязательным и, если выбрано, требует наличия базы данных соответствия требованиям, которая должна быть настроена для хранения данных и событий соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ab454-114">Compliance is optional, and if chosen, requires a compliance database that must be configured to store compliance data and events.</span></span> <span data-ttu-id="ab454-115">Кроме того, вы можете настроить адаптер для получения данных из базы данных соответствия и преобразования в другой формат (например, XML-файлы или архивы, размещенные на сервере Exchange).</span><span class="sxs-lookup"><span data-stu-id="ab454-115">You may want to also configure an adapter to take the data from the compliance database and convert to another format (such as XML files or Exchange-hosted archives).</span></span>

  - <span data-ttu-id="ab454-p104">Каким образом можно контролировать сферу применения, этические нормы и права доступа? Можно определить **Категории** для разграничения прав и выбора пользователей, которые могут присутствовать в тех или иных комнатах.</span><span class="sxs-lookup"><span data-stu-id="ab454-p104">How do you want to control scopes, ethical boundaries, and access? You can define **Categories** to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>

  - <span data-ttu-id="ab454-p105">Как можно ограничить права на создание комнат? С помощью группы **Авторы** можно дать права пользователям на создание комнат в соответствии с используемыми категориями. Авторы могут назначать других участников в качестве **менеджеров комнат чата** для постоянного управления комнатами (добавление или удаление дополнительных участников) в соответствии с параметром **AllowedMembers/DeniedMembers**, настроенным для той или иной категории.</span><span class="sxs-lookup"><span data-stu-id="ab454-p105">How do you want to control who can create rooms? You can configure **Creators**, appropriate to your categories, who can create rooms. Creators can assign other members as **Chat Room Managers** for ongoing management of the rooms (adding or removing additional members), according to the scope for **AllowedMembers/DeniedMembers** configured by the category.</span></span>

  - <span data-ttu-id="ab454-121">Как вы хотите создавать комнаты?</span><span class="sxs-lookup"><span data-stu-id="ab454-121">How do you want to create rooms?</span></span> <span data-ttu-id="ab454-122">Сервер сохраняемого чата предоставляет веб-функцию для создания и управления комнатами.</span><span class="sxs-lookup"><span data-stu-id="ab454-122">Persistent Chat Server provides a web-based feature for room creation and management.</span></span> <span data-ttu-id="ab454-123">Его можно запустить из клиента Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ab454-123">This can be launched from the Lync 2013 client.</span></span> <span data-ttu-id="ab454-124">Вы можете определить настраиваемое решение (с помощью пакета средств пакет SDK сервера сохраняемого чата (SDK)), которое реализует бизнес-требования и рабочие процессы, и настраивает сервер сохраняемого чата для направления пользователей в ваше пользовательское решение.</span><span class="sxs-lookup"><span data-stu-id="ab454-124">You can choose to define a custom solution (by using the Persistent Chat Server Software Development Kit (SDK)) that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>

  - <span data-ttu-id="ab454-125">Какие типы надстроек следует предоставлять?</span><span class="sxs-lookup"><span data-stu-id="ab454-125">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="ab454-126">**Надстройки расширяют** возможности в помещении, используя область расширяемости в клиенте Lync 2013, чтобы предоставить контекст, относящийся к комнате.</span><span class="sxs-lookup"><span data-stu-id="ab454-126">**Add-ins** enhance the in-room experience by leveraging the extensibility pane in the Lync 2013 client to provide context that is relevant to the room.</span></span> <span data-ttu-id="ab454-127">Можно указать, какие общие надстройки будут наиболее полезными (например, веб-сайт компании, внутренние документы для совместной работы и т. д.).</span><span class="sxs-lookup"><span data-stu-id="ab454-127">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="ab454-128">Менеджеры комнат чата могут выбирать зарегистрированные надстройки и сопоставлять их с комнатами.</span><span class="sxs-lookup"><span data-stu-id="ab454-128">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span>

  - <span data-ttu-id="ab454-129">Каковы требования к высокой доступности и аварийному восстановлению?</span><span class="sxs-lookup"><span data-stu-id="ab454-129">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="ab454-130">Сервер сохраняемого чата поддерживает зеркальное отображение SQL Server и кластеризацию SQL Server для обеспечения высокой доступности и поддерживает до 8 серверов (4 активных и 4 ждущих режимов) в растянутом пуле с доставкой журналов SQL Server для аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="ab454-130">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability and supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping for disaster recovery.</span></span>

  - <span data-ttu-id="ab454-131">Существуют ли нормативные требования?</span><span class="sxs-lookup"><span data-stu-id="ab454-131">Are there regulatory requirements?</span></span> <span data-ttu-id="ab454-132">Если ваша организация находится в стране или регионе, где данные должны храниться в стране, возможно, потребуется развернуть несколько пулов серверов сохраняемого чата, каждый из которых будет использоваться в определенном географическом стандарте.</span><span class="sxs-lookup"><span data-stu-id="ab454-132">If your company is in a country/region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="ab454-133">Комната, категория или надстройка не охватывают пулы — она относится только к одному пулу серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="ab454-133">A room, category, or add-in does not span pools—it belongs to only one Persistent Chat Server pool.</span></span> <span data-ttu-id="ab454-134">Можно управлять набором категорий, надстроек и комнат для каждого пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="ab454-134">You can manage the set of categories, add-ins and rooms for each Persistent Chat Server pool.</span></span> <span data-ttu-id="ab454-135">Пользователи могут настраивать доступ к комнатам в одном или нескольких пулах, используя область категорий AllowedMembers область или членство в комнате, в зависимости от того, как вы разрабатываете категории.</span><span class="sxs-lookup"><span data-stu-id="ab454-135">Users can be configured to have access to rooms in one or more pools using the category AllowedMembers scope or Room’s membership scope, depending on how you design your categories.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ab454-136">Наличие нескольких пулов серверов сохраняемого чата не обеспечивает более масштабный доступ (по-прежнему можно получить только 80 000 пользователей, одновременно подключенных к пулам серверов сохраняемого чата).</span><span class="sxs-lookup"><span data-stu-id="ab454-136">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrently connected users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="ab454-137">Основная причина поддержки нескольких пулов серверов сохраняемого чата заключается в поддержке нормативных требований.</span><span class="sxs-lookup"><span data-stu-id="ab454-137">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

