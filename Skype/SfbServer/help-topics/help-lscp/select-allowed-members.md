---
title: Выбор разрешенных участников
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Создание и управление стойкими комнатами чата намного проще при правильном использовании категорий. Администратор сохраняемого чата может определять allowedMembers и Creators для каждой категории, а также определять параметры и поведение комнаты чата по умолчанию, которые будут применяться во всех комнатах чата, созданных в этой категории. Постоянные администраторы чата создают и управляют категориями с помощью панели управления или Windows PowerShell.
ms.openlocfilehash: 47abbec64f6799a85f3f6123a898eeae00becbdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107995"
---
# <a name="select-allowed-members"></a><span data-ttu-id="66809-105">Выбор разрешенных участников</span><span class="sxs-lookup"><span data-stu-id="66809-105">Select Allowed Members</span></span>

<span data-ttu-id="66809-106">Создание и управление стойкими комнатами чата намного проще при правильном использовании категорий.</span><span class="sxs-lookup"><span data-stu-id="66809-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="66809-107">Администратор сохраняемого чата может определять **allowedMembers** и **Creators** для каждой категории, а также определять параметры и поведение комнаты чата по умолчанию, которые будут применяться во всех комнатах чата, созданных в этой категории.</span><span class="sxs-lookup"><span data-stu-id="66809-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="66809-108">Постоянные администраторы чата создают и управляют категориями с помощью панели управления или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66809-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="66809-109">Создавать комнаты в категории могут только пользователи, подразделения и группы пользователей, определенные как авторы этой категории.</span><span class="sxs-lookup"><span data-stu-id="66809-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="66809-110">После создания категории они могут выбирать пользователей, OUs и группы пользователей из списка **AllowedMembers** категории в качестве менеджеров и членов чата для управления и участия в комнате.</span><span class="sxs-lookup"><span data-stu-id="66809-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="66809-111">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="66809-111">Tasks that you can perform</span></span>

<span data-ttu-id="66809-112">На странице **Выберите разрешенных участников** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="66809-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="66809-113">Настройка категорий</span><span class="sxs-lookup"><span data-stu-id="66809-113">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="66809-114">Новые функции сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="66809-114">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="66809-115">Сведения о различных процедурах, которые можно выполнить с помощью панели управления Skype для бизнес-серверов, см. в материале Управление Skype для бизнеса [Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="66809-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="66809-116">Настройка категорий для комнат чата</span><span class="sxs-lookup"><span data-stu-id="66809-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="66809-117">В **разделе** Членство, в разделе Разрешенные участники добавьте или удалите пользователей и других руководителей служб домена Active Directory (пользователи, группы рассылки, организационные подразделения и так далее), которые разрешены добавлять в качестве членов комнат чатов, принадлежащих к этой категории. </span><span class="sxs-lookup"><span data-stu-id="66809-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="66809-118">Разрешенные в категории субъекты могут выполнять поиск комнат в этой категории (если только комната не является скрытой — такую комнату могут искать в каталоге только ее участники).</span><span class="sxs-lookup"><span data-stu-id="66809-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="66809-119">Подробные сведения о возможностях и возможностях сохраняемого сервера чата см. в обзоре сохраняемого сервера [чата](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="66809-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="66809-120">Подробные сведения о работе с настойчивыми конфигурациями сервера чата см. в материале Настройка стойких серверов чата в документации по развертыванию и управление [Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) в документации по операциям. [](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server)</span><span class="sxs-lookup"><span data-stu-id="66809-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="66809-121">См. также</span><span class="sxs-lookup"><span data-stu-id="66809-121">See also</span></span>

[<span data-ttu-id="66809-122">Общие сведения о членстве в сохраняемом чате</span><span class="sxs-lookup"><span data-stu-id="66809-122">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)