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
description: Создавать комнаты сохраняемого чата и управлять им намного проще при правильном использовании категорий. Администратор сохраняемого чата может определить AllowedMembers и Creators для каждой категории, а также определить параметры и поведение комнат чата по умолчанию, которые будут применяться для всех комнат чата, созданных в этой категории. Администраторы сохраняемой беседы создают категории и управляют ими с помощью панели управления или Windows PowerShell управления.
ms.openlocfilehash: 8c45a16f88bf20ab973927e17807b3241f20e942
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829139"
---
# <a name="select-allowed-members"></a><span data-ttu-id="d982a-105">Выбор разрешенных участников</span><span class="sxs-lookup"><span data-stu-id="d982a-105">Select Allowed Members</span></span>

<span data-ttu-id="d982a-106">Создавать комнаты сохраняемого чата и управлять им намного проще при правильном использовании категорий.</span><span class="sxs-lookup"><span data-stu-id="d982a-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="d982a-107">Администратор сохраняемого чата может определить **AllowedMembers** и **Creators** для каждой категории, а также определить параметры и поведение комнат чата по умолчанию, которые будут применяться для всех комнат чата, созданных в этой категории.</span><span class="sxs-lookup"><span data-stu-id="d982a-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="d982a-108">Администраторы сохраняемой беседы создают категории и управляют ими с помощью панели управления или Windows PowerShell управления.</span><span class="sxs-lookup"><span data-stu-id="d982a-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="d982a-109">Создавать комнаты в категории могут только пользователи, подразделения и группы пользователей, определенные как авторы этой категории.</span><span class="sxs-lookup"><span data-stu-id="d982a-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="d982a-110">После создания категории они могут выбирать пользователей, организации и группы пользователей из списка **AllowedMembers** категории в качестве руководителей и участников комнат чата для управления комнатой чата и участия в ней.</span><span class="sxs-lookup"><span data-stu-id="d982a-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="d982a-111">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="d982a-111">Tasks that you can perform</span></span>

<span data-ttu-id="d982a-112">На странице **Выберите разрешенных участников** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d982a-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="d982a-113">Настройка категорий</span><span class="sxs-lookup"><span data-stu-id="d982a-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="d982a-114">Новые функции сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="d982a-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="d982a-115">Подробные сведения о различных процедурах, которые можно выполнить с помощью панели управления Skype для бизнеса Server, см. в под управлением Skype для бизнеса [Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="d982a-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="d982a-116">Настройка категорий для комнат чата</span><span class="sxs-lookup"><span data-stu-id="d982a-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="d982a-117">В разделе "Членство" **в** разделе "Разрешенные участники" добавьте или удалите пользователей и других участников доменных служб Active Directory (пользователей, групп рассылки, подразделений и так далее), которые могут быть добавлены в качестве членов комнат чата, принадлежащих этой категории. </span><span class="sxs-lookup"><span data-stu-id="d982a-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="d982a-118">Разрешенные в категории субъекты могут выполнять поиск комнат в этой категории (если только комната не является скрытой — такую комнату могут искать в каталоге только ее участники).</span><span class="sxs-lookup"><span data-stu-id="d982a-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="d982a-119">Подробные сведения о возможностях и возможностях сервера сохраняемого чата см. в обзоре сервера сохраняемого [чата](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="d982a-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="d982a-120">Подробные сведения о работе с конфигурациями сервера сохраняемой беседы см. в документации по развертыванию и управлении сервером сохраняемой беседы [](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) [Lync Server 2013](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="d982a-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="d982a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="d982a-121">See also</span></span>

[<span data-ttu-id="d982a-122">Общие сведения о членстве в сохраняемом чате</span><span class="sxs-lookup"><span data-stu-id="d982a-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
