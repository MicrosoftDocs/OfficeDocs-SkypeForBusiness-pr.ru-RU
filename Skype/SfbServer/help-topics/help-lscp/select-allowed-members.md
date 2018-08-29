---
title: Выбор разрешенных участников
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Создание и управление Persistent Chat комнат намного проще с правильное использование категорий. Администратор сохраняемого чата можно назначить Указание параметров AllowedMembers и Creators для каждой категории и можно также определить параметры комнаты чата по умолчанию и поведения, которые будут применяться для всех комнатах чата, созданные в категории. Администраторы сохраняемого чата создания категорий или управления ими с помощью панели управления или командлетов Windows PowerShell.
ms.openlocfilehash: 5d1cf35524ae510655cb474c23b09a73b830802f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250761"
---
# <a name="select-allowed-members"></a><span data-ttu-id="53661-105">Выбор разрешенных участников</span><span class="sxs-lookup"><span data-stu-id="53661-105">Select Allowed Members</span></span>

<span data-ttu-id="53661-106">Создание и управление Persistent Chat комнат намного проще с правильное использование категорий.</span><span class="sxs-lookup"><span data-stu-id="53661-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="53661-107">Администратор сохраняемого чата можно назначить **Указание параметров AllowedMembers** и **Creators** для каждой категории и можно также определить параметры комнаты чата по умолчанию и поведения, которые будут применяться для всех комнатах чата, созданные в категории.</span><span class="sxs-lookup"><span data-stu-id="53661-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="53661-108">Администраторы сохраняемого чата создания категорий или управления ими с помощью панели управления или командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53661-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="53661-109">Создавать комнаты в категории могут только пользователи, подразделения и группы пользователей, которым назначено свойство "Авторы" в данной категории.</span><span class="sxs-lookup"><span data-stu-id="53661-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="53661-110">После создания категории можно пользователей, подразделения и группы пользователей из списка категорий **Указание параметров AllowedMembers** как менеджеры чатов аудитории и члены для управления и участвовать в помещении.</span><span class="sxs-lookup"><span data-stu-id="53661-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="53661-111">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="53661-111">Tasks that you can perform</span></span>

<span data-ttu-id="53661-112">На странице **Выберите разрешенных участников** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="53661-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="53661-113">Настройка категорий</span><span class="sxs-lookup"><span data-stu-id="53661-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="53661-114">Новые возможности сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="53661-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="53661-115">Для получения дополнительных сведений о различных процедурах, которые можно выполнять с помощью Скайп для панели управления сервера Business видеть [Управление Скайп для Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="53661-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="53661-116">Настройка категорий для комнат чата</span><span class="sxs-lookup"><span data-stu-id="53661-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="53661-117">В **членства**, в разделе **Участники разрешено** Добавление или удаление пользователей и доменных служб Active Directory других участников (пользователей, группы рассылки, подразделений и т. п.), которые могут быть добавлен в качестве членов комнаты чата принадлежащих категории.</span><span class="sxs-lookup"><span data-stu-id="53661-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="53661-118">Разрешенные в категории субъекты могут выполнять поиск комнат в этой категории (если только комната не является скрытой — такую комнату могут искать в каталоге только ее участники).</span><span class="sxs-lookup"><span data-stu-id="53661-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="53661-119">Для получения дополнительных сведений о сервера сохраняемого чата функциях и возможностях видеть [Overview of сервера сохраняемого чата](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="53661-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="53661-120">Дополнительные сведения о работе с конфигурациями сервера сохраняемого чата содержатся [Настройка сервера сохраняемого чата](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) в документации по развертыванию и [управлению Lync Server 2013, серверов сохраняемого чата](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="53661-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="53661-121">См. также</span><span class="sxs-lookup"><span data-stu-id="53661-121">See also</span></span>

[<span data-ttu-id="53661-122">Общие сведения о членстве в сохраняемом чате</span><span class="sxs-lookup"><span data-stu-id="53661-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)