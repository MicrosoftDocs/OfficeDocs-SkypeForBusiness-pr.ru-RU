---
title: Выбор разрешенных участников
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Создавать сохраняемые комнаты чатов и управлять ими намного проще благодаря правильному использованию категорий. Администратор сохраняемого чата может определять Алловедмемберс и создателя для каждой категории, а также задавать параметры и поведения комнаты чата по умолчанию, которые будут применяться ко всем комнатам чата, созданным в этой категории. Сохраняемые администраторы чата создают категории и управляйте ими с помощью панели управления или командлетов Windows PowerShell.
ms.openlocfilehash: dedc022853738ad02b4da2ce0ab2cdc7ccbee576
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282254"
---
# <a name="select-allowed-members"></a><span data-ttu-id="93d65-105">Выбор разрешенных участников</span><span class="sxs-lookup"><span data-stu-id="93d65-105">Select Allowed Members</span></span>

<span data-ttu-id="93d65-106">Создавать сохраняемые комнаты чатов и управлять ими намного проще благодаря правильному использованию категорий.</span><span class="sxs-lookup"><span data-stu-id="93d65-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="93d65-107">Администратор сохраняемого чата может определять **алловедмемберс** и **создателя** для каждой категории, а также задавать параметры и поведения комнаты чата по умолчанию, которые будут применяться ко всем комнатам чата, созданным в этой категории.</span><span class="sxs-lookup"><span data-stu-id="93d65-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="93d65-108">Сохраняемые администраторы чата создают категории и управляйте ими с помощью панели управления или командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93d65-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="93d65-109">Создавать комнаты в категории могут только пользователи, подразделения и группы пользователей, которым назначено свойство "Авторы" в данной категории.</span><span class="sxs-lookup"><span data-stu-id="93d65-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="93d65-110">После того как категория создана, она может выбрать пользователей, подразделения и группы пользователей из списка **алловедмемберс** категории в качестве руководителей комнаты и участников для управления ими и участия в комнате.</span><span class="sxs-lookup"><span data-stu-id="93d65-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="93d65-111">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="93d65-111">Tasks that you can perform</span></span>

<span data-ttu-id="93d65-112">На странице **Выберите разрешенных участников** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="93d65-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="93d65-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="93d65-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="93d65-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="93d65-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="93d65-115">Сведения о различных процедурах, которые можно выполнить с помощью панели управления "Skype для бизнеса Server", приведены в статье [Управление Skype для бизнеса server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="93d65-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="93d65-116">Настройка категорий для комнат чата</span><span class="sxs-lookup"><span data-stu-id="93d65-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="93d65-117">В \*\*\*\* разделе "разрешенные \*\*\*\* пользователи" добавьте или удалите пользователей и других участников доменных служб Active Directory (пользователей, группы рассылки, подразделения и т. д.), которые разрешено добавлять в качестве участников комнат чата. принадлежит к категории.</span><span class="sxs-lookup"><span data-stu-id="93d65-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="93d65-118">Разрешенные в категории субъекты могут выполнять поиск комнат в этой категории (если только комната не является скрытой — такую комнату могут искать в каталоге только ее участники).</span><span class="sxs-lookup"><span data-stu-id="93d65-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="93d65-119">Сведения о функциях и возможностях сервера в чате можно найти в разделе [Обзор сохраняемого сервера чата](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="93d65-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="93d65-120">Подробнее о работе с сохраняемыми конфигурациями сервера чата: [Настройка сервера сохраняемого чата](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) в документации по развертыванию и [управление Lync Server 2013, сохраняемый сервер чата](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="93d65-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="93d65-121">См. также</span><span class="sxs-lookup"><span data-stu-id="93d65-121">See also</span></span>

[<span data-ttu-id="93d65-122">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="93d65-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
