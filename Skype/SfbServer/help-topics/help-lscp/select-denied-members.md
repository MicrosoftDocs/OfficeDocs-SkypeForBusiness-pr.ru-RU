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
description: Администратор сохраняемой беседы может создавать категории комнат чата и управлять ими. В рамках создания категорий комнат чата и управления ними администратор сохраняемого чата может настраивать участников (группы, контейнеры и пользователи доменных служб Active Directory), которые могут быть участниками или создателями комнат чата определенной категории. Администратор сохраняемой беседы также может добавить DeniedMembers в категорию, и они станут явными исключениями из списка разрешенных. DeniedMembers переопределяет то, что имеется в AllowedMembers.
ms.openlocfilehash: c5f942723937fe2da28025fba5da1fc7ee121c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814579"
---
# <a name="select-denied-members"></a><span data-ttu-id="4e659-106">Выбор запрещенных участников</span><span class="sxs-lookup"><span data-stu-id="4e659-106">Select Denied Members</span></span>

<span data-ttu-id="4e659-107">Администратор сохраняемой беседы может создавать категории комнат чата и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="4e659-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="4e659-108">В рамках создания категорий комнат чата и управления ними администратор сохраняемого чата может настраивать участников (группы, контейнеры и пользователи доменных служб Active Directory), которые могут быть участниками или создателями комнат чата определенной категории.</span><span class="sxs-lookup"><span data-stu-id="4e659-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="4e659-109">Администратор сохраняемой беседы также может добавить DeniedMembers в категорию, и они станут явными исключениями из списка разрешенных.</span><span class="sxs-lookup"><span data-stu-id="4e659-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="4e659-110">DeniedMembers переопределяет то, что имеется в AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="4e659-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="4e659-111">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="4e659-111">Tasks that you can perform</span></span>

<span data-ttu-id="4e659-112">На странице **Выберите запрещенных участников** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="4e659-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="4e659-113">Настройка категорий</span><span class="sxs-lookup"><span data-stu-id="4e659-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="4e659-114">Новые функции сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="4e659-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="4e659-115">Подробные сведения о различных процедурах, которые можно выполнить с помощью панели управления Skype для бизнеса Server, см. в под управлением Skype для бизнеса [Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="4e659-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="4e659-116">Настройка категорий для комнат чата</span><span class="sxs-lookup"><span data-stu-id="4e659-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="4e659-117">В **разделе**"Отказано **в** членстве" добавьте или удалите пользователей и других участников Active Directory, связанных с участниками, отказано в доступе к комнате.</span><span class="sxs-lookup"><span data-stu-id="4e659-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="4e659-118">Подробные сведения о возможностях и [](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) возможностях сервера сохраняемого чата см. в обзоре сервера сохраняемого чата в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="4e659-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="4e659-119">Подробные сведения о работе с конфигурациями сервера сохраняемой беседы см. в документации по развертыванию и управлении сервером сохраняемой беседы [](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) [Lync Server 2013](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="4e659-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e659-120">См. также</span><span class="sxs-lookup"><span data-stu-id="4e659-120">See also</span></span>

[<span data-ttu-id="4e659-121">Общие сведения о членстве в сохраняемом чате</span><span class="sxs-lookup"><span data-stu-id="4e659-121">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
