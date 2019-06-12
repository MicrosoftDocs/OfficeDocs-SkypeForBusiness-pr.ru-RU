---
title: Использование категорий для администрирования сервера сохраняемого чата
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fed28ecc7c2698f4b320729c68de9c5d56b435b2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a><span data-ttu-id="f6605-102">Использование категорий для администрирования сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f6605-102">Using categories to administer Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6605-103">_**Тема последнего изменения:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="f6605-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="f6605-104">В развертывании сервера сохраняемого чата могут размещаться большое количество одновременных комнат чатов.</span><span class="sxs-lookup"><span data-stu-id="f6605-104">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="f6605-105">На сервере комнаты чата можно упорядочить по целому набору категорий.</span><span class="sxs-lookup"><span data-stu-id="f6605-105">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="f6605-106">Каждая комната чата относится к одной категории и наследует от нее некоторые параметры.</span><span class="sxs-lookup"><span data-stu-id="f6605-106">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="f6605-107">Такая организация позволяет получить структуру, которая удобна для идентификации бесед по их назначению, облегчает делегированное администрирование и упрощает управление.</span><span class="sxs-lookup"><span data-stu-id="f6605-107">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f6605-108">Несмотря на то, что многие возможности управления комнат чатов доступны на компьютерах, на которых запущен постоянный чат (клиент Lync) для пользователя, пользователи постоянного чата (в роли <STRONG>ксперсистентчатадминистратор</STRONG> ) должны использовать панель управления Lync Server или Командлеты Windows PowerShell для создания категорий и управления ими.</span><span class="sxs-lookup"><span data-stu-id="f6605-108">Although many of the management features of chat rooms are available in computers running Persistent Chat (Lync client) for the user, Persistent Chat Administrators (in the <STRONG>cspersistentchatadministrator</STRONG> role) must use the Lync Server Control Panel or Windows PowerShell cmdlets to create or manage categories.</span></span>



</div>

<span data-ttu-id="f6605-109">Для создания категорий и управления ими, а также для настройки доступа к комнатам чата для пользователей в своей организации, администраторы сохраняемого чата используют панель управления Lync Server или командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6605-109">Persistent Chat administrators use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>

<span data-ttu-id="f6605-110">С помощью клиента Lync можно запускать веб-приложение управления комнатой для создания комнат и управления ими, а также пользователи, которые могут создавать собственные решения и рабочие процессы, которые можно использовать для создания собственных решений и рабочих процессов, в диспетчере комнат чатов.</span><span class="sxs-lookup"><span data-stu-id="f6605-110">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the Lync client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="f6605-111">Кроме того, для создания комнат и управления ими можно использовать панель управления Lync Server или командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6605-111">Persistent Chat administrators can also use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f6605-112">Имя сохраняемой комнаты чата не может совпадать с именем категории сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="f6605-112">A Persistent Chat room cannot have the same name as a Persistent Chat category.</span></span>



</div>

<span data-ttu-id="f6605-p103">Руководители комнат чата могут вносить изменения во все свойства комнаты чата, кроме непосредственно категории комнаты. Они могут без каких-либо ограничений выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f6605-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>

  - <span data-ttu-id="f6605-115">Отключение комнаты чата</span><span class="sxs-lookup"><span data-stu-id="f6605-115">Disabling a chat room</span></span>

  - <span data-ttu-id="f6605-116">Изменение имени комнаты чата</span><span class="sxs-lookup"><span data-stu-id="f6605-116">Changing a chat room name</span></span>

  - <span data-ttu-id="f6605-117">Изменение описания комнаты чата</span><span class="sxs-lookup"><span data-stu-id="f6605-117">Changing a chat room description</span></span>

  - <span data-ttu-id="f6605-118">Изменение типа комнаты чата (аудитория или обычная)</span><span class="sxs-lookup"><span data-stu-id="f6605-118">Changing a chat room type (Auditorium versus Normal)</span></span>

  - <span data-ttu-id="f6605-119">Изменение уровня конфиденциальности комнаты (открытая, закрытая или секретная)</span><span class="sxs-lookup"><span data-stu-id="f6605-119">Changing the privacy of a room (open versus closed versus secret)</span></span>

  - <span data-ttu-id="f6605-120">Добавление или удаление членов</span><span class="sxs-lookup"><span data-stu-id="f6605-120">Adding or removing members</span></span>

  - <span data-ttu-id="f6605-121">Добавление или удаление руководителей комнат чата</span><span class="sxs-lookup"><span data-stu-id="f6605-121">Adding or removing chat room managers</span></span>

  - <span data-ttu-id="f6605-122">Добавление или удаление надстройки</span><span class="sxs-lookup"><span data-stu-id="f6605-122">Adding or removing an add-in</span></span>

  - <span data-ttu-id="f6605-123">Изменение различных настроек, например приглашений (в пределах, допускаемых категорией)</span><span class="sxs-lookup"><span data-stu-id="f6605-123">Changing settings such as invitations (according to what’s permitted by the category)</span></span>

<div>

## <a name="delegated-administration"></a><span data-ttu-id="f6605-124">Делегированное администрирование</span><span class="sxs-lookup"><span data-stu-id="f6605-124">Delegated Administration</span></span>

<span data-ttu-id="f6605-125">Создавать сохраняемые комнаты чатов и управлять ими намного проще благодаря правильному использованию категорий.</span><span class="sxs-lookup"><span data-stu-id="f6605-125">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="f6605-126">Администратор сохраняемого чата может определять **алловедмемберс** и **создателя** для каждой категории, а также задавать параметры и поведения комнаты чата по умолчанию, которые будут применяться ко всем комнатам чата, созданным в этой категории.</span><span class="sxs-lookup"><span data-stu-id="f6605-126">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="f6605-127">Сохраняемые администраторы чата создают категории и управляйте ими с помощью панели управления Lync Server или командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6605-127">Persistent Chat administrators create and manage categories by using Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="f6605-p105">Создавать комнаты в категории могут только пользователи, подразделения и группы пользователей, которым назначено свойство "Авторы" в данной категории. После создания категории они могут выбрать пользователей, подразделения или группы пользователей из списка **Допустимые участники** данной категории в качестве руководителей и участников комнат чата.</span><span class="sxs-lookup"><span data-stu-id="f6605-p105">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category. After the category is created, they can choose users, OUs, and user groups from the category’s **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

<span data-ttu-id="f6605-130">Комнаты чата, созданные в категории, соответствуют политикам и параметрам, принудительно применяемым категорией (например, кто может находиться в членстве в комнате, кто может управлять комнатой, какие пользователи могут работать с ней, как это разрешено, будь то отправка приглашений и т. д.).</span><span class="sxs-lookup"><span data-stu-id="f6605-130">Chat rooms that are created in a category adhere to the policies and settings enforced by the category (such as who can be in the room’s membership, who can manage the room, whether file uploads are allowed, whether invitations are sent, and so on).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

