---
title: 'Lync Server 2013: роли пользователей на сервере сохраняемого чата'
description: 'Lync Server 2013: роли пользователей на сервере сохраняемого чата.'
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
ms.openlocfilehash: aed64aaa9129e6667cd138bc4365acfb2a64d52c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550855"
---
# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="4d707-103">Роли пользователей на сервере сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d707-103">User roles in Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d707-104">_**Последнее изменение темы:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="4d707-104">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="4d707-105">Сервер сохраняемого чата предоставляет концепцию разрешенных и запрещенных участников, которые применяются к категориям сохраняемого чата и элементам управления, которые могут получать доступ к комнатам в определенной категории.</span><span class="sxs-lookup"><span data-stu-id="4d707-105">Persistent Chat Server provides the concept of Allowed/Denied members, which applies to Persistent Chat categories and controls who can access rooms in a particular category.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4d707-106">Разрешенные или запрещенные участники в категории — это не то же самое, что и роль <STRONG>участника</STRONG> , которая применяется к сохраняемой комнате чата.</span><span class="sxs-lookup"><span data-stu-id="4d707-106">Allowed/Denied members in a Category is not the same as a <STRONG>Member</STRONG> role, which applies to a Persistent Chat room.</span></span><BR><span data-ttu-id="4d707-p101">Операции поиска возвращают все открытые и закрытые комнаты чата, у которых пользователь, выполняющий поиск, находится в списке разрешенных или запрещенных участников. Секретные комнаты не отображаются, если пользователь, выполняющий поиск, не является участником секретной комнаты. Пользователь может выполнять поиск только комнат, участником которых он или она уже является или может запросить участие.</span><span class="sxs-lookup"><span data-stu-id="4d707-p101">Searches display all open and closed chat rooms for which the user performing the search is in the Allowed/Denied member list. Secret rooms are not displayed unless the user who performs the search is a member of the secret room. The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span>



</div>

<span data-ttu-id="4d707-p102">В основе применения разрешенных и запрещенных участников лежат прежде всего ограничения, налагаемые корпоративными стандартами. Например, в банковских и финансовых учреждениях обычно существуют этические ограничения, не позволяющие торговцам и аналитикам передавать другу другу информацию при осуществлении политик и соглашений. Чтобы учесть это требование, администратор может создать категории таким образом, чтобы одна категория позволяла создавать и использовать комнаты торговцам, а другая — аналитикам. При использовании такого ограничения система запрещает добавление пользователя как участника комнаты, если этому препятствует родительская категория.</span><span class="sxs-lookup"><span data-stu-id="4d707-p102">The primary rationale for the concept of Allowed/Denied Members is ethical walls. For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions. To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts. With this constraint is designed into the system prohibits adding a user as a member of the room if the parent category prevents it.</span></span>

<span data-ttu-id="4d707-114">Ниже приведены четыре роли пользователей сервера сохраняемого чата:</span><span class="sxs-lookup"><span data-stu-id="4d707-114">Following are the four user roles Persistent Chat Server:</span></span>

  - <span data-ttu-id="4d707-115">**Создатель:** Пользователи, у которых есть разрешения на создание комнат чата.</span><span class="sxs-lookup"><span data-stu-id="4d707-115">**Creator:** Users who have permissions to create chat rooms.</span></span> <span data-ttu-id="4d707-116">Эти пользователи находятся в списке создателей определенных категорий: они могут создавать комнаты чата в этой категории, а также назначать членство в соответствии с категорией, а также назначать руководителей для управления комнатой чата.</span><span class="sxs-lookup"><span data-stu-id="4d707-116">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="4d707-117">Пользователь, который создает комнату чата, автоматически добавляется в качестве руководителя комнаты.</span><span class="sxs-lookup"><span data-stu-id="4d707-117">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4d707-p104">Роль автора просто дает права для создания комнат чата. При этом автор автоматически переходит в диспетчеры, что позволяет ему настраивать участие, назначать диспетчеров и выполнять прочие функции в создаваемых службах чата.</span><span class="sxs-lookup"><span data-stu-id="4d707-p104">Being a Creator simply provides rights for creating chat rooms. It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span>

    
    </div>
    
    <span data-ttu-id="4d707-120">С помощью этой роли вы можете определять, кто будет создавать комнаты чата в вашей организации, в частности для центрального управления созданием комнат чата, которое обеспечит применение политик и соглашений, и последующей передачи управления комнатами другим пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="4d707-120">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>

  - <span data-ttu-id="4d707-121">**Руководитель:** Пользователи, управляющие свойствами комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="4d707-121">**Manager:** Users who manage properties of a chat room.</span></span> <span data-ttu-id="4d707-122">Менеджеры комнаты чата могут изменять список участников (добавлять и удалять участников), а также изменять список руководителей комнаты чата (Добавление и удаление руководителей).</span><span class="sxs-lookup"><span data-stu-id="4d707-122">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="4d707-123">Менеджеры комнаты чата могут добавлять себя в список участников или докладчиков (для комнат аудитория), чтобы они могли участвовать в комнате чата.</span><span class="sxs-lookup"><span data-stu-id="4d707-123">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="4d707-124">Менеджеры комнаты чата также могут отключить комнаты чата (администраторы могут запрашивать отключенные комнаты чата и навсегда удалять их).</span><span class="sxs-lookup"><span data-stu-id="4d707-124">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="4d707-125">Руководители могут изменять все свойства комнаты чата, кроме категории комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="4d707-125">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="4d707-126">Только администратор сохраняемого чата может изменить категорию после создания комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="4d707-126">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4d707-127">Если диспетчер является также автором в другой категории, он или она может изменить категорию на ту, в которой имеет полномочия на создание комнат.</span><span class="sxs-lookup"><span data-stu-id="4d707-127">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span>

    
    </div>

  - <span data-ttu-id="4d707-128">**Член:** Пользователи, являющиеся участниками комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="4d707-128">**Member:** Users who are members of a chat room.</span></span> <span data-ttu-id="4d707-129">Эти пользователи могут просматривать комнаты чата в каталоге (даже если комната чата конфиденциально), а также подписываться на комнату чата (включая такие параметры метаданных, как непрочтенные сообщения, фильтры его и фильтры ключевых слов), а также участвовать в комнате чата (возможен учет, если комната не является помещением аудитория, в котором только докладчики могут отправлять, получать содержимое и выполнять поиск).</span><span class="sxs-lookup"><span data-stu-id="4d707-129">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="4d707-130">Пользователи, не являющиеся участниками комнаты чата, могут выполнять поиск комнаты чата, если они находятся в списке разрешенных участников категории, но вам необходимо запросить доступ к этим комнатам чата для доступа к содержимому.</span><span class="sxs-lookup"><span data-stu-id="4d707-130">Users who aren’t members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="4d707-131">(В системе нет доступа к запросам или утверждений, которые можно сделать внешними по электронной почте, телефону или другим формам контакта.)</span><span class="sxs-lookup"><span data-stu-id="4d707-131">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>

  - <span data-ttu-id="4d707-132">**Выступающий:** Пользователи, которые могут отправлять сообщения в конференцию аудитория.</span><span class="sxs-lookup"><span data-stu-id="4d707-132">**Presenter:** Users who can post to an auditorium room.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d707-133">Сервер сохраняемого чата позволяет пользователям создавать комнаты чата для определенного сайта и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="4d707-133">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="4d707-134">Однако пользователи не могут создавать комнаты чата и управлять ими на других сайтах в одной и той же топологии.</span><span class="sxs-lookup"><span data-stu-id="4d707-134">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="4d707-135">Не забудьте указать создатели и менеджеры комнаты чата для всех сайтов в Организации.</span><span class="sxs-lookup"><span data-stu-id="4d707-135">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<span data-ttu-id="4d707-136">Следующие роли являются ролями администратора для сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="4d707-136">The following roles are administrator roles for Persistent Chat Server:</span></span>

  - <span data-ttu-id="4d707-137">**Администратор сохраняемого чата (CsPersistentChatAdministrator):** Это новая роль управления доступом Role-Based (RBAC) для управления сервером сохраняемого чата и управления им.</span><span class="sxs-lookup"><span data-stu-id="4d707-137">**Persistent Chat Administrator (CsPersistentChatAdministrator):** This is a new Role-Based Access Control (RBAC) role to administer and manage Persistent Chat Server.</span></span> <span data-ttu-id="4d707-138">Пользователи или группы безопасности, назначенные в качестве CsPersistentChatAdministrator, могут администрировать сервер сохраняемого чата с помощью командлетов Windows PowerShell, удаленных с помощью командлетов Windows PowerShell (на компьютере, отличном от сервера сохраняемого чата).</span><span class="sxs-lookup"><span data-stu-id="4d707-138">Users or security groups designated as CsPersistentChatAdministrator are able administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="4d707-139">Сервер сохраняемого чата проверяет, входит ли администратор сохраняемого чата в локальную группу локального администратора RTC на сервере переднего плана сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="4d707-139">Persistent Chat Server checks that the Persistent Chat Administrator is member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
    <span data-ttu-id="4d707-140">Роль CsPersistentChatAdministrator позволяет управлять комнатами чата (изменять любые свойства, включая участие, диспетчеров, категории, пометку комнат как отключенных), а также создавать категории комнат чата (и управлять ими), определяющие, кто может создавать и использовать эти комнаты.</span><span class="sxs-lookup"><span data-stu-id="4d707-140">The CsPersistentChatAdministrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="4d707-141">Администраторы могут помечать комнаты чата как отключенные и очищать комнаты чата, которые больше неактивны.</span><span class="sxs-lookup"><span data-stu-id="4d707-141">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="4d707-142">На администраторов не распространяются ограничения, применяемые к авторам или разрешенным участникам.</span><span class="sxs-lookup"><span data-stu-id="4d707-142">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="4d707-143">Администраторы могут создавать комнаты чата любого типа и добавлять себя в качестве участников в любые комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="4d707-143">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="4d707-144">Администраторы также могут изменять и управлять конфигурацией сохраняемого чата (свойствами пула, глобальными параметрами и конфигурацией соответствия требованиям), а также планировать и внедрять миграцию с устаревшего развертывания сервера группового чата на сервер Lync Server 2013 сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="4d707-144">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Lync Server 2013 Persistent Chat Server.</span></span>

  - <span data-ttu-id="4d707-145">**Администратор Lync:** Общий администратор предприятия для Lync Server 2013, ответственный за развертывание.</span><span class="sxs-lookup"><span data-stu-id="4d707-145">**Lync Administrator:** Overall enterprise administrator for Lync Server 2013 responsible for deployment.</span></span>

  - <span data-ttu-id="4d707-146">**Operations Manager:** Пользователь, ответственный за управление повседневными операциями.</span><span class="sxs-lookup"><span data-stu-id="4d707-146">**Operations Manager:** User responsible for managing day-to-day operations.</span></span>

  - <span data-ttu-id="4d707-147">**Сторонние разработчики и партнеры:** Сторонние разработчики расширяют систему, в частности, предоставляя решение для групповых бесед, поддержки и поддержки соответствия требованиям, а также для веб-клиентов и мобильных клиентов, а также для разработки для программы Bot.</span><span class="sxs-lookup"><span data-stu-id="4d707-147">**Third-party developers and partners:** Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

