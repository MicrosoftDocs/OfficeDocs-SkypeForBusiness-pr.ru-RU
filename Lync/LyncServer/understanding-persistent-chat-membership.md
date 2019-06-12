---
title: Общие сведения о членстве в сохраняемом чате
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e525d93e58e73304b9d3a26248418c88b5e9ea79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="5276f-102">Общие сведения о членстве в сохраняемом чате</span><span class="sxs-lookup"><span data-stu-id="5276f-102">Understanding Persistent Chat membership</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5276f-103">_**Тема последнего изменения:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="5276f-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="5276f-104">Доступ пользователей к сохраняемым комнатам чата осуществляется с помощью членства; Пользователи должны быть членами комнаты чата, чтобы отправлять и читать сообщения.</span><span class="sxs-lookup"><span data-stu-id="5276f-104">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="5276f-105">В \*\*\*\* **Аудиториум комнатах**можно использовать только выступающие, у которых есть назначенная принадлежность с комнатой чата.</span><span class="sxs-lookup"><span data-stu-id="5276f-105">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="5276f-106">Аудиториум — это тип комнаты чата (второй — **обычный**), где могут быть прочитаны только выступающие, и все могут читать.</span><span class="sxs-lookup"><span data-stu-id="5276f-106">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="5276f-107">Кроме того, сохраняемые комнаты чата работают в соответствии с правилами категории.</span><span class="sxs-lookup"><span data-stu-id="5276f-107">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="5276f-108">Подробнее о категориях читайте в статье [Управление категориями, комнатами и надстройками в Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), а также разделы "как работает область категорий" и "стратегии категорий помещений" в разделе ниже.</span><span class="sxs-lookup"><span data-stu-id="5276f-108">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="5276f-109">Администратор сохраняемого чата может создавать категории комнат чата и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="5276f-109">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="5276f-110">В рамках создания и управления категориями комнаты чата администратор сохраняемого чата может настраивать участников (группы доменных служб Active Directory, контейнеры и пользователей), которые имеют доступ к участникам или создателям чатов в определенной категории.</span><span class="sxs-lookup"><span data-stu-id="5276f-110">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="5276f-111">Доменные службы Active Directory и сохраняемый чат</span><span class="sxs-lookup"><span data-stu-id="5276f-111">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="5276f-112">Сервер сохраняемого чата использует службу каталогов Active Directory для пула внутренних пользователей, использующих сохраняемый чат.</span><span class="sxs-lookup"><span data-stu-id="5276f-112">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="5276f-113">После установки сохраняемого чата (клиента) вы можете добавлять домены пользователей и групп пользователей в категорию Room (комната).</span><span class="sxs-lookup"><span data-stu-id="5276f-113">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="5276f-114">Затем вы можете добавить этих пользователей и группы к членству в категориях комнат.</span><span class="sxs-lookup"><span data-stu-id="5276f-114">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5276f-115">Необходимо убедиться в отсутствии повторяющихся имен для пользователей, которые хотят вносить изменения в записную комнату.</span><span class="sxs-lookup"><span data-stu-id="5276f-115">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="5276f-116">Если существуют повторяющиеся имена пользователей, измените их на разные имена, чтобы разблокировать пользователей от внесения этих изменений.</span><span class="sxs-lookup"><span data-stu-id="5276f-116">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="5276f-117">Если пользователь имеет повторяющиеся имена в Active Directory и пытается внести в них изменения, появится сообщение об ошибке с предложением пользователя связаться с администратором для устранения проблемы.</span><span class="sxs-lookup"><span data-stu-id="5276f-117">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="5276f-118">Как работает область видимости категорий</span><span class="sxs-lookup"><span data-stu-id="5276f-118">How Category Scoping Works</span></span>

<span data-ttu-id="5276f-119">Категория задает всех пользователей и групп, которые могут быть членами списка участников сохраняемой комнаты чата в этой категории, на основе ее свойства **алловедмемберс** .</span><span class="sxs-lookup"><span data-stu-id="5276f-119">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="5276f-120">Например, если задать для категории **алловедмемберс** значение contoso.com, вы можете добавить в нее любую группу или пользователя из *contoso* в качестве участника для общения с комнатами в этой категории.</span><span class="sxs-lookup"><span data-stu-id="5276f-120">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="5276f-121">Если вы установили для категории **алловедмемберс** значение " *продажи*", только группы и пользователи из этого списка рассылки можно будет добавить как участники в записную книжку в этой категории.</span><span class="sxs-lookup"><span data-stu-id="5276f-121">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="5276f-122">Аналогичным образом \*\*\*\* свойство Creators позволяет управлять тем, кто может создавать комнаты чата в этой категории.</span><span class="sxs-lookup"><span data-stu-id="5276f-122">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="5276f-123">После создания комнаты чата любой пользователь из группы **алловедмемберс** может быть назначен руководителем для выполнения операций \*\*\*\* управления в помещениях (например, изменения и утверждения участников).</span><span class="sxs-lookup"><span data-stu-id="5276f-123">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="5276f-124">Определение **алловедмемберс** и **создателя** для категории имеет следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="5276f-124">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="5276f-125">Все комнаты чата в этой категории будут подчиняться ограничениям, установленным на уровне категории.</span><span class="sxs-lookup"><span data-stu-id="5276f-125">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="5276f-126">Это можно использовать для разделения комнат чата на основе бизнес-требований и политик доступа.</span><span class="sxs-lookup"><span data-stu-id="5276f-126">You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="5276f-127">Пользователь, который входит в список **создателей** , может создать в этой категории новые комнаты чатов.</span><span class="sxs-lookup"><span data-stu-id="5276f-127">A user who is in the **Creators** list can create new chat rooms in that category.</span></span> <span data-ttu-id="5276f-128">Если вы хотите реализовать систему, в которой ограниченное количество сотрудников в Организации может создавать комнаты чата, этот элемент управления можно использовать для выполнения этого требования.</span><span class="sxs-lookup"><span data-stu-id="5276f-128">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="5276f-129">Стратегии категорий помещений</span><span class="sxs-lookup"><span data-stu-id="5276f-129">Room Category Strategies</span></span>

<span data-ttu-id="5276f-130">**Алловедмемберс** категории должны включать всех пользователей, которые будут использовать в этой категории все пользователи с постоянной комнатой чата.</span><span class="sxs-lookup"><span data-stu-id="5276f-130">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="5276f-131">В зависимости от требований для защиты бизнес-данных и обеспечения соответствующего уровня доступа может потребоваться определить одну или несколько категорий, чтобы указать, кто может выполнять поиск и участвовать в помещениях.</span><span class="sxs-lookup"><span data-stu-id="5276f-131">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="5276f-132">Если вы хотите предоставить доступ только определенному набору пользователей (централизованной службы технической поддержки или только сотрудникам с полной занятостью) для создания комнат, вы \*\*\*\* можете задать для них область, чтобы удовлетворить этим требованиям.</span><span class="sxs-lookup"><span data-stu-id="5276f-132">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="5276f-133">Категории также можно использовать для создания безупречных стен.</span><span class="sxs-lookup"><span data-stu-id="5276f-133">Categories can also be used to create ethical walls.</span></span> <span data-ttu-id="5276f-134">Бесплатные стены не позволяют устранить конфликты, которые интересуются Организацией.</span><span class="sxs-lookup"><span data-stu-id="5276f-134">Ethical walls prevent any conflict of interest in an organization.</span></span> <span data-ttu-id="5276f-135">Например, администратор может создать комнаты чатов только в категории для компании Traders, в то время как комнаты чата в другой категории могут использоваться только аналитиками.</span><span class="sxs-lookup"><span data-stu-id="5276f-135">For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5276f-136">В Lync Server 2013 (сохраняемый сервер чата) не поддерживается доступ к федеративным пользователям.</span><span class="sxs-lookup"><span data-stu-id="5276f-136">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="5276f-137">Если в предыдущих версиях сохраняемого сервера чата есть разговоры от федеративных пользователей, они будут перенесены.</span><span class="sxs-lookup"><span data-stu-id="5276f-137">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="5276f-138">Федеративные пользователи будут добавлены как отключенные участники.</span><span class="sxs-lookup"><span data-stu-id="5276f-138">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="5276f-139">Сокращение пользователей для групп</span><span class="sxs-lookup"><span data-stu-id="5276f-139">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="5276f-140">При добавлении домена в категорию пользователи будут иметь доступ к группам, объекты групп которых содержатся в этом домене, и вы можете указать их в качестве членов комнат в этой категории.</span><span class="sxs-lookup"><span data-stu-id="5276f-140">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="5276f-141">В качестве общего правила мы рекомендуем использовать контейнеры Active Directory, например домены и подразделения, для определения **алловедмемберс** и **создателя**категории.</span><span class="sxs-lookup"><span data-stu-id="5276f-141">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="5276f-142">Вы можете добавлять объекты из любого домена в список **алловедмемберс** или **Creators** .</span><span class="sxs-lookup"><span data-stu-id="5276f-142">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="5276f-143">В помещениях под этой категорией можно добавлять только объекты в списке **алловедмемберс** или **Creators** .</span><span class="sxs-lookup"><span data-stu-id="5276f-143">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

