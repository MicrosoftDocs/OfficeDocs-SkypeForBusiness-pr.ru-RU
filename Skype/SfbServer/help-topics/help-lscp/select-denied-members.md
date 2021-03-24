---
title: Выбор запрещенных участников
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
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: Постоянный администратор чата может создавать и управлять категориями комнат чата. В рамках создания и управления категориями комнат чата администратор сохраняемого чата может настраивать директоров (группы/контейнеры/пользователи active Directory Domain Services), которые имеют доступ к членам или создателям комнат чатов определенной категории. Администратор сохраняемой беседы также может добавлять DeniedMembers в категорию, и они становятся явными исключениями в разрешенный список. DeniedMembers переопределяют то, что есть в AllowedMembers.
ms.openlocfilehash: 5a31716c2fae15c6216ed050b543673479415a76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107965"
---
# <a name="select-denied-members"></a><span data-ttu-id="7acf3-106">Выбор запрещенных участников</span><span class="sxs-lookup"><span data-stu-id="7acf3-106">Select Denied Members</span></span>

<span data-ttu-id="7acf3-107">Постоянный администратор чата может создавать и управлять категориями комнат чата.</span><span class="sxs-lookup"><span data-stu-id="7acf3-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="7acf3-108">В рамках создания и управления категориями комнат чата администратор сохраняемого чата может настраивать директоров (группы/контейнеры/пользователи active Directory Domain Services), которые имеют доступ к членам или создателям комнат чатов определенной категории.</span><span class="sxs-lookup"><span data-stu-id="7acf3-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="7acf3-109">Администратор сохраняемой беседы также может добавлять DeniedMembers в категорию, и они становятся явными исключениями в разрешенный список.</span><span class="sxs-lookup"><span data-stu-id="7acf3-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="7acf3-110">DeniedMembers переопределяют то, что есть в AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="7acf3-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="7acf3-111">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="7acf3-111">Tasks that you can perform</span></span>

<span data-ttu-id="7acf3-112">На странице **Выберите запрещенных участников** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="7acf3-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="7acf3-113">Настройка категорий</span><span class="sxs-lookup"><span data-stu-id="7acf3-113">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="7acf3-114">Новые функции сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="7acf3-114">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="7acf3-115">Сведения о различных процедурах, которые можно выполнить с помощью панели управления Skype для бизнес-серверов, см. в материале Управление Skype для бизнеса [Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="7acf3-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="7acf3-116">Настройка категорий для комнат чата</span><span class="sxs-lookup"><span data-stu-id="7acf3-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="7acf3-117">В **разделе Членство**, в разделе **Отказано в членстве** добавьте или удалите пользователей и других директоров Active Directory, связанных с тем, что участникам отказано в доступе из комнаты.</span><span class="sxs-lookup"><span data-stu-id="7acf3-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="7acf3-118">Подробные сведения о возможностях и возможностях сохраняемого сервера чата см. в обзоре сохраняемого сервера [чата](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="7acf3-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="7acf3-119">Подробные сведения о работе с настойчивыми конфигурациями сервера чата см. в материале Настройка стойких серверов чата в документации по развертыванию и управление [Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) в документации по операциям. [](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server)</span><span class="sxs-lookup"><span data-stu-id="7acf3-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="7acf3-120">См. также</span><span class="sxs-lookup"><span data-stu-id="7acf3-120">See also</span></span>

[<span data-ttu-id="7acf3-121">Общие сведения о членстве в сохраняемом чате</span><span class="sxs-lookup"><span data-stu-id="7acf3-121">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)