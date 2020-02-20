---
title: Общие сведения о членстве в сохраняемом чате
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f2422e1b7191680b6ff81ecec7fb60d82a9ef10
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="d61ce-102">Общие сведения о членстве в сохраняемом чате</span><span class="sxs-lookup"><span data-stu-id="d61ce-102">Understanding Persistent Chat membership</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d61ce-103">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="d61ce-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="d61ce-104">Доступ пользователей к комнатам сохраняемого чата управляется членством; чтобы отправлять и читать сообщения, пользователи должны быть участниками комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="d61ce-104">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="d61ce-105">Использовать функцию **отправки в комнаты-аудитории** могут только **выступающие**, которым назначено членство в комнатах чата.</span><span class="sxs-lookup"><span data-stu-id="d61ce-105">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="d61ce-106">Аудитория — это тип комнаты чата (другим типом является **обычная комната**), в которую могут отправлять сообщения только выступающие, а остальные пользователи могут их читать.</span><span class="sxs-lookup"><span data-stu-id="d61ce-106">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="d61ce-107">Кроме того, комнаты сохраняемого чата действуют в соответствии с правилами категории.</span><span class="sxs-lookup"><span data-stu-id="d61ce-107">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="d61ce-108">Подробнее о категориях можно узнать [в статье Управление категориями, комнатами и надстройками в Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), а также в разделах "как работает определение категорий" и "стратегии категорий помещений" Далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d61ce-108">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="d61ce-109">Администратор сохраняемого чата может создавать категории комнат чата и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="d61ce-109">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="d61ce-110">В процессе создания и управления категориями комнат чата администратор сохраняемого чата может настраивать субъекты (группы доменных служб Active Directory, контейнеры и пользователей), у которых есть доступ к участникам или создателям чатов для конкретной категории.</span><span class="sxs-lookup"><span data-stu-id="d61ce-110">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="d61ce-111">Доменные службы Active Directory и сохраняемый чат</span><span class="sxs-lookup"><span data-stu-id="d61ce-111">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="d61ce-112">Сервер сохраняемого чата использует Active Directory для пула внутренних пользователей сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="d61ce-112">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="d61ce-113">После установки сохраняемого чата (клиента) можно добавить домены пользователей и групп пользователей в категорию комнаты.</span><span class="sxs-lookup"><span data-stu-id="d61ce-113">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="d61ce-114">Затем можно добавить этих пользователей и группы в членство категорий комнат.</span><span class="sxs-lookup"><span data-stu-id="d61ce-114">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d61ce-115">Необходимо убедиться в отсутствии повторяющихся имен для пользователей, которые хотят вносить изменения в комнаты сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="d61ce-115">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="d61ce-116">Если существуют дублирующиеся имена, измените их на другие, чтобы позволить пользователям делать подобные изменения.</span><span class="sxs-lookup"><span data-stu-id="d61ce-116">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="d61ce-117">Если пользователь имеет дублирующиеся имена в Active Directory и пытается внести изменения в свои комнаты, появится сообщение об ошибке, предлагающее пользователю связаться с администратором для устранения проблемы.</span><span class="sxs-lookup"><span data-stu-id="d61ce-117">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="d61ce-118">Принципы работы определения границ категорий</span><span class="sxs-lookup"><span data-stu-id="d61ce-118">How Category Scoping Works</span></span>

<span data-ttu-id="d61ce-119">В категории указаны все пользователи и группы, которые могут быть членами списка членства в комнате сохраняемого чата в этой категории на основе его свойства **AllowedMembers** .</span><span class="sxs-lookup"><span data-stu-id="d61ce-119">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="d61ce-120">Например, если для категории **AllowedMembers** задано значение contoso.com, вы можете добавить любую группу или пользователя в *contoso* в качестве члена для чатов в этой категории.</span><span class="sxs-lookup"><span data-stu-id="d61ce-120">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="d61ce-121">Если параметр **AllowedMembers** в категории имеет значение *Sales*, то в качестве членов комнат чата в этой категории могут быть добавлены только группы и пользователи из этого списка рассылки.</span><span class="sxs-lookup"><span data-stu-id="d61ce-121">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="d61ce-122">Аналогично, свойство **Creators** позволяет контролировать, кто может создавать комнаты чата в этой категории.</span><span class="sxs-lookup"><span data-stu-id="d61ce-122">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="d61ce-123">После создания комнаты чата любой член группы **AllowedMembers** может быть назначен в качестве **менеджера** для выполнения в комнатах текущих операций управления (таких как изменения и утверждения членства).</span><span class="sxs-lookup"><span data-stu-id="d61ce-123">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="d61ce-124">Указание параметров **AllowedMembers** и **Creators** для категории имеет следующие преимущества.</span><span class="sxs-lookup"><span data-stu-id="d61ce-124">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="d61ce-p107">Все комнаты чата в этой категории будут подчиняться ограничениям, установленным на уровне категории. Это можно использовать для разделения комнат чата на основе бизнес-требований и политик доступа.</span><span class="sxs-lookup"><span data-stu-id="d61ce-p107">All chat rooms in this category are bound by the restrictions set at the category level. You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="d61ce-p108">Пользователь, входящий в список **создателей** (Creators), может создавать новые комнаты чата в этой категории. Если требуется реализовать систему, в которой создавать комнаты чата может только ограниченное количество сотрудников, то с помощью этого элемента управления можно выполнить данные требования.</span><span class="sxs-lookup"><span data-stu-id="d61ce-p108">A user who is in the **Creators** list can create new chat rooms in that category. If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="d61ce-129">Стратегии категорий комнат</span><span class="sxs-lookup"><span data-stu-id="d61ce-129">Room Category Strategies</span></span>

<span data-ttu-id="d61ce-130">В **AllowedMembers** категории должны содержаться все пользователи, которые будут использовать любую комнату сохраняемого чата в этой категории.</span><span class="sxs-lookup"><span data-stu-id="d61ce-130">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="d61ce-131">В зависимости от текущих требований к защите коммерческих данных и для обеспечения правильного уровня доступа может потребоваться задать одну или несколько категорий, чтобы указать, кто может выполнять поиск в комнатах и участвовать в них.</span><span class="sxs-lookup"><span data-stu-id="d61ce-131">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="d61ce-132">Если планируется разрешить создание комнат только определенным пользователям (например, только центральной службе поддержки или только штатным сотрудникам), то для удовлетворения этих требований можно назначить **создателей** категории.</span><span class="sxs-lookup"><span data-stu-id="d61ce-132">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="d61ce-p110">Категории также можно использовать для создания этических границ. Этические границы предотвращают конфликты интересов в организации. Например, администратор может создать в одной категории комнаты чата, предназначенные только для торговцев, а в другой категории — комнаты, которые могут использовать только аналитики.</span><span class="sxs-lookup"><span data-stu-id="d61ce-p110">Categories can also be used to create ethical walls. Ethical walls prevent any conflict of interest in an organization. For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d61ce-136">В Lync Server 2013, сервер сохраняемого чата не поддерживает доступ к федеративным пользователям.</span><span class="sxs-lookup"><span data-stu-id="d61ce-136">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="d61ce-137">При наличии сеансов федеративных пользователей в предыдущих версиях сервера сохраняемого чата они будут перенесены.</span><span class="sxs-lookup"><span data-stu-id="d61ce-137">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="d61ce-138">Федеративные пользователи добавляются как отключенные субъекты.</span><span class="sxs-lookup"><span data-stu-id="d61ce-138">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="d61ce-139">Ограничение членов группами пользователей</span><span class="sxs-lookup"><span data-stu-id="d61ce-139">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="d61ce-140">При добавлении домена в категорию можно указать группы пользователей, чьи объекты группы содержатся в этом домене, в качестве членов комнат в этой категории.</span><span class="sxs-lookup"><span data-stu-id="d61ce-140">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="d61ce-141">В качестве общего правила рекомендуется использовать контейнеры Active Directory, такие как домены и подразделения, для определения **AllowedMembers** и **создателей**категории.</span><span class="sxs-lookup"><span data-stu-id="d61ce-141">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="d61ce-142">Вы можете добавлять объекты из любого домена в список **AllowedMembers** или **Creators** .</span><span class="sxs-lookup"><span data-stu-id="d61ce-142">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="d61ce-143">В комнаты в этой категории можно добавлять только объекты из списка **AllowedMembers** или **Creators** .</span><span class="sxs-lookup"><span data-stu-id="d61ce-143">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

