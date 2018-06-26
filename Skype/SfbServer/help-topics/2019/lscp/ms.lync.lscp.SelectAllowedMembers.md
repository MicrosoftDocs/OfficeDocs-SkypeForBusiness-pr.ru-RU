---
title: Выбор разрешенных участников
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Создание и управление Persistent Chat комнат намного проще с правильное использование категорий. Администратор сохраняемого чата можно назначить Указание параметров AllowedMembers и Creators для каждой категории и можно также определить параметры комнаты чата по умолчанию и поведения, которые будут применяться для всех комнатах чата, созданные в категории. Администраторы сохраняемого чата создания категорий или управления ими с помощью панели управления или командлетов Windows PowerShell.
ms.openlocfilehash: c29163a88394fd9c3653e9bbbdae8c9f744f610e
ms.sourcegitcommit: b42a6a56a0e1e4be1239174c1c3b4ab86517d043
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "20045612"
---
# <a name="select-allowed-members"></a><span data-ttu-id="dbd89-105">Выбор разрешенных участников</span><span class="sxs-lookup"><span data-stu-id="dbd89-105">Select Allowed Members</span></span>
 
<span data-ttu-id="dbd89-106">Создание и управление Persistent Chat комнат намного проще с правильное использование категорий.</span><span class="sxs-lookup"><span data-stu-id="dbd89-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="dbd89-107">Администратор сохраняемого чата можно назначить **Указание параметров AllowedMembers** и **Creators** для каждой категории и можно также определить параметры комнаты чата по умолчанию и поведения, которые будут применяться для всех комнатах чата, созданные в категории.</span><span class="sxs-lookup"><span data-stu-id="dbd89-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="dbd89-108">Администраторы сохраняемого чата создания категорий или управления ими с помощью панели управления или командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dbd89-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>
  
<span data-ttu-id="dbd89-109">Создавать комнаты в категории могут только пользователи, подразделения и группы пользователей, которым назначено свойство "Авторы" в данной категории.</span><span class="sxs-lookup"><span data-stu-id="dbd89-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="dbd89-110">После создания категории можно пользователей, подразделения и группы пользователей из списка категорий **Указание параметров AllowedMembers** как менеджеры чатов аудитории и члены для управления и участвовать в помещении.</span><span class="sxs-lookup"><span data-stu-id="dbd89-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="dbd89-111">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="dbd89-111">Tasks that you can perform</span></span>

<span data-ttu-id="dbd89-112">На странице **Выберите разрешенных участников** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="dbd89-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>
  
- [<span data-ttu-id="dbd89-113">Настройка категорий</span><span class="sxs-lookup"><span data-stu-id="dbd89-113">Configure Categories</span></span>](http://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)
    
- [<span data-ttu-id="dbd89-114">Новые возможности сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="dbd89-114">New Persistent Chat Server Features</span></span>](http://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)
    
 
  
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="dbd89-115">Настройка категорий для комнат чата</span><span class="sxs-lookup"><span data-stu-id="dbd89-115">To configure categories for chat rooms</span></span>

<span data-ttu-id="dbd89-116">В **членства**, в разделе **Участники разрешено** Добавление или удаление пользователей и доменных служб Active Directory других участников (пользователей, группы рассылки, подразделений и т. п.), которые могут быть добавлен в качестве членов комнаты чата принадлежащих категории.</span><span class="sxs-lookup"><span data-stu-id="dbd89-116">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="dbd89-117">Разрешенные в категории субъекты могут выполнять поиск комнат в этой категории (если только комната не является скрытой — такую комнату могут искать в каталоге только ее участники).</span><span class="sxs-lookup"><span data-stu-id="dbd89-117">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
  
### 

<span data-ttu-id="dbd89-118">Для получения дополнительных сведений о сервера сохраняемого чата функциях и возможностях видеть [Overview of сервера сохраняемого чата](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="dbd89-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="dbd89-119">Дополнительные сведения о работе с конфигурациями сервера сохраняемого чата содержатся [Настройка сервера сохраняемого чата](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) в документации по развертыванию и [управлению Lync Server 2013, серверов сохраняемого чата](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="dbd89-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dbd89-120">См. также</span><span class="sxs-lookup"><span data-stu-id="dbd89-120">See also</span></span>

[<span data-ttu-id="dbd89-121">Общие сведения о членстве в сохраняемом чате</span><span class="sxs-lookup"><span data-stu-id="dbd89-121">Understanding Persistent Chat Membership</span></span>](http://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)