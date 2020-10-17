---
title: Использование категорий для администрирования сервера сохраняемого чата
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d008e77df49dcfb2875923575c5d0c2acb1d1dd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526416"
---
# <a name="using-categories-to-administer-persistent-chat-server"></a><span data-ttu-id="d2adc-102">Использование категорий для администрирования сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="d2adc-102">Using categories to administer Persistent Chat Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2adc-103">_**Последнее изменение темы:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="d2adc-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="d2adc-104">В развертывании сервера сохраняемого чата могут размещаться множество одновременных комнат сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="d2adc-104">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="d2adc-105">Комнаты чата можно организовать как набор категорий на сервере.</span><span class="sxs-lookup"><span data-stu-id="d2adc-105">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="d2adc-106">Каждая комната чата принадлежит одной категории и наследует некоторые параметры из этой категории.</span><span class="sxs-lookup"><span data-stu-id="d2adc-106">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="d2adc-107">Такая организация создает полезную структуру для определения бесед на основе их бизнес-цели и обеспечивает делегированное администрирование и упрощает управление.</span><span class="sxs-lookup"><span data-stu-id="d2adc-107">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d2adc-108">Несмотря на то, что многие функции управления комнат чата доступны на компьютерах, на которых выполняется функция сохраняемого чата (клиент Lync) для пользователя, администраторы сохраняемого чата (в роли <STRONG>cspersistentchatadministrator</STRONG> ) должны использовать для создания категорий и управления ими командлеты Windows PowerShell: панель управления Lync Server или командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2adc-108">Although many of the management features of chat rooms are available in computers running Persistent Chat (Lync client) for the user, Persistent Chat Administrators (in the <STRONG>cspersistentchatadministrator</STRONG> role) must use the Lync Server Control Panel or Windows PowerShell cmdlets to create or manage categories.</span></span>



</div>

<span data-ttu-id="d2adc-109">Администраторы сохраняемого чата используют панель управления Lync Server или командлеты Windows PowerShell для создания категорий и управления ими, а также для разрабатывать доступ к комнатам чата для пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="d2adc-109">Persistent Chat administrators use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>

<span data-ttu-id="d2adc-110">Менеджеры комнаты сохраняемого чата, которые имеют возможность управлять одной или несколькими комнатами чата, могут использовать клиент Lync для запуска веб-приложения управления комнатами для создания комнат и управления ими (или клиенты могут создавать настраиваемые решения и рабочие процессы для вызова).</span><span class="sxs-lookup"><span data-stu-id="d2adc-110">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the Lync client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="d2adc-111">Администраторы сохраняемого чата также могут использовать панель управления Lync Server или командлеты Windows PowerShell для создания комнат и управления ими.</span><span class="sxs-lookup"><span data-stu-id="d2adc-111">Persistent Chat administrators can also use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d2adc-112">Комната сохраняемого чата не может иметь такое же имя, как и Категория сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="d2adc-112">A Persistent Chat room cannot have the same name as a Persistent Chat category.</span></span>



</div>

<span data-ttu-id="d2adc-p103">Руководители комнат чата могут изменять все свойства комнат чата, кроме категории комнаты. Им нельзя запретить выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d2adc-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>

  - <span data-ttu-id="d2adc-115">отключать комнату чата;</span><span class="sxs-lookup"><span data-stu-id="d2adc-115">Disabling a chat room</span></span>

  - <span data-ttu-id="d2adc-116">изменять имя комнаты чата;</span><span class="sxs-lookup"><span data-stu-id="d2adc-116">Changing a chat room name</span></span>

  - <span data-ttu-id="d2adc-117">изменять описание комнаты чата;</span><span class="sxs-lookup"><span data-stu-id="d2adc-117">Changing a chat room description</span></span>

  - <span data-ttu-id="d2adc-118">изменять тип комнаты чата (с Auditorium на Normal и наоборот);</span><span class="sxs-lookup"><span data-stu-id="d2adc-118">Changing a chat room type (Auditorium versus Normal)</span></span>

  - <span data-ttu-id="d2adc-119">изменять свойство конфиденциальности комнаты (открытая, закрытая или секретная);</span><span class="sxs-lookup"><span data-stu-id="d2adc-119">Changing the privacy of a room (open versus closed versus secret)</span></span>

  - <span data-ttu-id="d2adc-120">добавлять и удалять участников;</span><span class="sxs-lookup"><span data-stu-id="d2adc-120">Adding or removing members</span></span>

  - <span data-ttu-id="d2adc-121">добавлять и удалять руководителей комнат чата;</span><span class="sxs-lookup"><span data-stu-id="d2adc-121">Adding or removing chat room managers</span></span>

  - <span data-ttu-id="d2adc-122">добавлять и удалять надстройки;</span><span class="sxs-lookup"><span data-stu-id="d2adc-122">Adding or removing an add-in</span></span>

  - <span data-ttu-id="d2adc-123">Изменение различных настроек, например приглашений (в пределах, допускаемых категорией)</span><span class="sxs-lookup"><span data-stu-id="d2adc-123">Changing settings such as invitations (according to what’s permitted by the category)</span></span>

<div>

## <a name="delegated-administration"></a><span data-ttu-id="d2adc-124">Делегированное администрирование</span><span class="sxs-lookup"><span data-stu-id="d2adc-124">Delegated Administration</span></span>

<span data-ttu-id="d2adc-125">Создание и управление комнатами сохраняемого чата значительно упрощается благодаря правильному использованию категорий.</span><span class="sxs-lookup"><span data-stu-id="d2adc-125">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="d2adc-126">Администратор сохраняемого чата может определять **AllowedMembers** и **Creators** для каждой категории, а также задавать параметры и поведения комнаты чата по умолчанию, которые будут применяться ко всем комнатам чата, созданным в категории.</span><span class="sxs-lookup"><span data-stu-id="d2adc-126">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="d2adc-127">Администраторам сохраняемого чата создавать категории и управлять ими с помощью панели управления Lync Server или командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2adc-127">Persistent Chat administrators create and manage categories by using Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="d2adc-p105">Создавать комнаты в категории могут только пользователи, подразделения и группы пользователей, которым назначено свойство Creators в данной категории. После создания категории они могут выбрать пользователей, подразделения или группы пользователей из списка **AllowedMembers** данной категории в качестве руководителей и участников комнат чата.</span><span class="sxs-lookup"><span data-stu-id="d2adc-p105">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category. After the category is created, they can choose users, OUs, and user groups from the category’s **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

<span data-ttu-id="d2adc-130">На комнаты чата, созданные в категории, распространяются действующие в ней политики и параметры (например, кто может быть участником комнаты, кто может управлять комнатой, разрешена ли отправка файлов, отправляются ли приглашения и т. п.).</span><span class="sxs-lookup"><span data-stu-id="d2adc-130">Chat rooms that are created in a category adhere to the policies and settings enforced by the category (such as who can be in the room’s membership, who can manage the room, whether file uploads are allowed, whether invitations are sent, and so on).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

