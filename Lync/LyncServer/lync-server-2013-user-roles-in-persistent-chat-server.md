---
title: 'Lync Server 2013: роли пользователей на сервере сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 771eac8e5c8ff1c72bfb2ce64d9b6c04853b30a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="6e61f-102">Роли пользователей в постоянном сервере чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e61f-102">User roles in Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e61f-103">_**Тема последнего изменения:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="6e61f-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="6e61f-104">Сервер сохраняемого чата обеспечивает концепцию разрешенных и запрещенных пользователей, которые применяются к постоянным категориям чата и элементам управления, которые могут получать доступ к комнатам в определенной категории.</span><span class="sxs-lookup"><span data-stu-id="6e61f-104">Persistent Chat Server provides the concept of Allowed/Denied members, which applies to Persistent Chat categories and controls who can access rooms in a particular category.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6e61f-105">Разрешенные и запрещенные пользователи в категории — это не то же, что и роль <STRONG>участника</STRONG> , которая применяется к сохраняемой комнате чата.</span><span class="sxs-lookup"><span data-stu-id="6e61f-105">Allowed/Denied members in a Category is not the same as a <STRONG>Member</STRONG> role, which applies to a Persistent Chat room.</span></span><BR><span data-ttu-id="6e61f-106">В области поиска отображаются все открытые и закрытые комнаты чата, в которых пользователь выполняет поиск, в списке разрешенных и запрещенных участников.</span><span class="sxs-lookup"><span data-stu-id="6e61f-106">Searches display all open and closed chat rooms for which the user performing the search is in the Allowed/Denied member list.</span></span> <span data-ttu-id="6e61f-107">Секретные комнаты не отображаются, если пользователь, выполняющий поиск, не является участником секретной комнаты.</span><span class="sxs-lookup"><span data-stu-id="6e61f-107">Secret rooms are not displayed unless the user who performs the search is a member of the secret room.</span></span> <span data-ttu-id="6e61f-108">Пользователь может выполнять поиск только комнат, участником которых он или она уже является или может запросить участие.</span><span class="sxs-lookup"><span data-stu-id="6e61f-108">The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span>



</div>

<span data-ttu-id="6e61f-109">Основным обоснованием для разрешения разрешенных и отклоненных членов является «безупречная стенка».</span><span class="sxs-lookup"><span data-stu-id="6e61f-109">The primary rationale for the concept of Allowed/Denied Members is ethical walls.</span></span> <span data-ttu-id="6e61f-110">Например, в банковских и финансовых учреждениях обычно существуют этические ограничения, не позволяющие торговцам и аналитикам передавать друг другу информацию при осуществлении политик и соглашений.</span><span class="sxs-lookup"><span data-stu-id="6e61f-110">For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions.</span></span> <span data-ttu-id="6e61f-111">Чтобы учесть это требование, администратор может создать категории таким образом, чтобы одна категория позволяла создавать и использовать комнаты торговцам, а другая — аналитикам.</span><span class="sxs-lookup"><span data-stu-id="6e61f-111">To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts.</span></span> <span data-ttu-id="6e61f-112">Благодаря этому ограничению система не может добавить пользователя в комнату в том случае, если родительская Категория ее не допускает.</span><span class="sxs-lookup"><span data-stu-id="6e61f-112">With this constraint is designed into the system prohibits adding a user as a member of the room if the parent category prevents it.</span></span>

<span data-ttu-id="6e61f-113">Ниже указаны четыре роли пользователей, которые представляют собой сохраняемый сервер чата.</span><span class="sxs-lookup"><span data-stu-id="6e61f-113">Following are the four user roles Persistent Chat Server:</span></span>

  - <span data-ttu-id="6e61f-114">**Создатель:** Пользователи, у которых есть разрешения на создание комнат чата.</span><span class="sxs-lookup"><span data-stu-id="6e61f-114">**Creator:** Users who have permissions to create chat rooms.</span></span> <span data-ttu-id="6e61f-115">Эти пользователи находятся в списке создателей некоторых категорий: они могут создавать комнаты чата в этой категории, а также назначать членство в соответствии с категорией и назначать руководителей для управления комнатой чата.</span><span class="sxs-lookup"><span data-stu-id="6e61f-115">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="6e61f-116">Пользователь, который создает комнату чата, автоматически добавляется в качестве руководителя комнаты.</span><span class="sxs-lookup"><span data-stu-id="6e61f-116">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6e61f-p104">Роль автора просто дает права для создания комнат чата. При этом автор автоматически переходит в диспетчеры, что позволяет ему настраивать участие, назначать диспетчеров и выполнять прочие функции в создаваемых службах чата.</span><span class="sxs-lookup"><span data-stu-id="6e61f-p104">Being a Creator simply provides rights for creating chat rooms. It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span>

    
    </div>
    
    <span data-ttu-id="6e61f-119">С помощью этой роли вы можете определять, кто будет создавать комнаты чата в вашей организации, в частности для центрального управления созданием комнат чата, которое обеспечит применение политик и соглашений, и последующей передачи управления комнатами другим пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="6e61f-119">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>

  - <span data-ttu-id="6e61f-120">**Руководитель:** Пользователи, которые управляют свойствами комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="6e61f-120">**Manager:** Users who manage properties of a chat room.</span></span> <span data-ttu-id="6e61f-121">Менеджер комнаты чата может изменить список участников (Добавить и удалить участников), а также изменить список руководителей комнаты чата (Добавление и удаление руководителей).</span><span class="sxs-lookup"><span data-stu-id="6e61f-121">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="6e61f-122">Менеджер комнаты чата может добавить себя в список участников или выступающих (для Аудиториум комнат), чтобы они могли участвовать в комнате чата.</span><span class="sxs-lookup"><span data-stu-id="6e61f-122">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="6e61f-123">Руководители комнаты чата также могут отключить комнаты чата (администраторы могут запрашивать отключенные комнаты чата, а также удалять их окончательно).</span><span class="sxs-lookup"><span data-stu-id="6e61f-123">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="6e61f-124">Руководители могут изменять все свойства комнаты чата, за исключением категории комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="6e61f-124">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="6e61f-125">После создания комнаты чата только администратор постоянного чата может изменить категорию.</span><span class="sxs-lookup"><span data-stu-id="6e61f-125">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6e61f-126">Если диспетчер является также автором в другой категории, он или она может изменить категорию на ту, в которой имеет полномочия на создание комнат.</span><span class="sxs-lookup"><span data-stu-id="6e61f-126">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span>

    
    </div>

  - <span data-ttu-id="6e61f-127">**Элемент:** Пользователи, являющиеся участниками комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="6e61f-127">**Member:** Users who are members of a chat room.</span></span> <span data-ttu-id="6e61f-128">Эти пользователи могут просматривать помещения чата в каталог (даже если комната чата конфиденциально), а также подписаться на комнату чата (в том числе параметры метаданных, такие как непрочитанные сообщения, фильтры "эго" и фильтры ключевых слов) и участвовать в комнате чата (может быть опубликована, если только комната не — Это Аудиториум комната, в которой только выступающие могут публиковать, получать содержимое и выполнять поиск.</span><span class="sxs-lookup"><span data-stu-id="6e61f-128">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="6e61f-129">Пользователи, которые не входят в комнату чата, могут найти комнату чата, если они находятся в списке разрешенных пользователей, но вам нужно запросить доступ к этим комнатам для доступа к содержимому.</span><span class="sxs-lookup"><span data-stu-id="6e61f-129">Users who aren’t members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="6e61f-130">(Нет запросов или утверждений, встроенных в систему; они выполняются извне по электронной почте, телефоне или другим формам контакта.)</span><span class="sxs-lookup"><span data-stu-id="6e61f-130">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>

  - <span data-ttu-id="6e61f-131">**Выступающий:** Пользователи, которые могут публиковать в Аудиториум комнате.</span><span class="sxs-lookup"><span data-stu-id="6e61f-131">**Presenter:** Users who can post to an auditorium room.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e61f-132">Сервер сохраняемого чата позволяет пользователям создавать и управлять комнатой чата для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="6e61f-132">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="6e61f-133">Тем не менее, пользователи не могут создавать комнаты чата и управлять ими на других сайтах в пределах одной и той же топологии.</span><span class="sxs-lookup"><span data-stu-id="6e61f-133">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="6e61f-134">Не забудьте указать создатели и руководителей комнаты чата для всех сайтов в Организации.</span><span class="sxs-lookup"><span data-stu-id="6e61f-134">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<span data-ttu-id="6e61f-135">Ниже указаны роли администратора для сохраняемого сервера чата.</span><span class="sxs-lookup"><span data-stu-id="6e61f-135">The following roles are administrator roles for Persistent Chat Server:</span></span>

  - <span data-ttu-id="6e61f-136">**Администратор сохраняемого чата (ксперсистентчатадминистратор):** Это новая роль управления доступом на основе ролей (RBAC) для администрирования и управления сохраняемым сервером чата.</span><span class="sxs-lookup"><span data-stu-id="6e61f-136">**Persistent Chat Administrator (CsPersistentChatAdministrator):** This is a new Role-Based Access Control (RBAC) role to administer and manage Persistent Chat Server.</span></span> <span data-ttu-id="6e61f-137">Пользователи и группы безопасности, назначенные как Ксперсистентчатадминистратор, смогут администрировать сервер сохраняемого чата с помощью командлетов Windows PowerShell (на компьютере, отличном от сервера сохраняемого чата).</span><span class="sxs-lookup"><span data-stu-id="6e61f-137">Users or security groups designated as CsPersistentChatAdministrator are able administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="6e61f-138">Сервер сохраняемого чата проверяет, входит ли администратор сохраняемого чата в локальную группу локального администратора RTC на серверном интерфейсе сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="6e61f-138">Persistent Chat Server checks that the Persistent Chat Administrator is member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
    <span data-ttu-id="6e61f-139">Роль Ксперсистентчатадминистратор может управлять комнатами чата (изменить все свойства, включая членство, руководителей, категории, помечать помещения в состояние "отключено"), а также создавать и управлять категориями комнат чата, которые определяют, кто может создавать комнаты чатов и получать к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="6e61f-139">The CsPersistentChatAdministrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="6e61f-140">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span><span class="sxs-lookup"><span data-stu-id="6e61f-140">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="6e61f-141">Administrators are not subject to the Creators or Allowed Members restrictions.</span><span class="sxs-lookup"><span data-stu-id="6e61f-141">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="6e61f-142">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span><span class="sxs-lookup"><span data-stu-id="6e61f-142">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="6e61f-143">Администраторы могут также изменять и управлять конфигурацией сохраняемого чата (свойствам пула, глобальными параметрами и конфигурацией соответствия требованиям), а также планировать и реализовывать миграцию с более старого сервера группового чата развертывания на Lync Server 2013 сохраняемый чат Server.</span><span class="sxs-lookup"><span data-stu-id="6e61f-143">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Lync Server 2013 Persistent Chat Server.</span></span>

  - <span data-ttu-id="6e61f-144">**Администратор Lync:** Общий администратор предприятия для Lync Server 2013, ответственный за развертывание.</span><span class="sxs-lookup"><span data-stu-id="6e61f-144">**Lync Administrator:** Overall enterprise administrator for Lync Server 2013 responsible for deployment.</span></span>

  - <span data-ttu-id="6e61f-145">**Operations Manager:** Пользователь, ответственный за управление повседневными операциями.</span><span class="sxs-lookup"><span data-stu-id="6e61f-145">**Operations Manager:** User responsible for managing day-to-day operations.</span></span>

  - <span data-ttu-id="6e61f-146">**Сторонние разработчики и партнеры:** Сторонние разработчики расширяют систему, в частности, обеспечивая решение для групповых разговоров, поддержку соответствия требованиям и инструменты, веб-и мобильные клиенты, а также платформу для Bot-разработки.</span><span class="sxs-lookup"><span data-stu-id="6e61f-146">**Third-party developers and partners:** Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

