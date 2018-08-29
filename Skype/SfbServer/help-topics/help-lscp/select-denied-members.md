---
title: Выбор запрещенных участников
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: Администратор сохраняемого чата можно создавать и управлять категорий комнат чата. В процессе создания и управления ими категорий комнат чата администратор сохраняемого чата можно настроить участников (доменных служб Active Directory группы и контейнеры/пользователи), которые имеют доступ к быть члены/создателей каналы, в конкретной категории. Persistent Chat Administrator также можно добавить DeniedMembers к категории, и они станут явные исключения в список разрешенных. DeniedMembers переопределить возможности Указание параметров AllowedMembers.
ms.openlocfilehash: 768ff250da93d1a134cac942ed28408646dc4be2
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258307"
---
# <a name="select-denied-members"></a><span data-ttu-id="57180-106">Выбор запрещенных участников</span><span class="sxs-lookup"><span data-stu-id="57180-106">Select Denied Members</span></span>

<span data-ttu-id="57180-107">Администратор сохраняемого чата можно создавать и управлять категорий комнат чата.</span><span class="sxs-lookup"><span data-stu-id="57180-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="57180-108">В процессе создания и управления ими категорий комнат чата администратор сохраняемого чата можно настроить участников (доменных служб Active Directory группы и контейнеры/пользователи), которые имеют доступ к быть члены/создателей каналы, в конкретной категории.</span><span class="sxs-lookup"><span data-stu-id="57180-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="57180-109">Persistent Chat Administrator также можно добавить DeniedMembers к категории, и они станут явные исключения в список разрешенных.</span><span class="sxs-lookup"><span data-stu-id="57180-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="57180-110">DeniedMembers переопределить возможности Указание параметров AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="57180-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="57180-111">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="57180-111">Tasks that you can perform</span></span>

<span data-ttu-id="57180-112">На странице **Выберите запрещенных участников** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="57180-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="57180-113">Настройка категорий</span><span class="sxs-lookup"><span data-stu-id="57180-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="57180-114">Новые возможности сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="57180-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="57180-115">Для получения дополнительных сведений о различных процедурах, которые можно выполнять с помощью Скайп для панели управления сервера Business видеть [Управление Скайп для Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="57180-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="57180-116">Настройка категорий для комнат чата</span><span class="sxs-lookup"><span data-stu-id="57180-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="57180-117">В области **членство в**разделе **Запрещенные участники** Добавление или удаление пользователей и другие субъекты Active Directory, связанных с участниками, удаляемыми из комнаты.</span><span class="sxs-lookup"><span data-stu-id="57180-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="57180-118">Для получения дополнительных сведений о сервера сохраняемого чата функциях и возможностях видеть [Overview of сервера сохраняемого чата](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="57180-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="57180-119">Дополнительные сведения о работе с конфигурациями сервера сохраняемого чата содержатся [Настройка сервера сохраняемого чата](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) в документации по развертыванию и [управлению Lync Server 2013, серверов сохраняемого чата](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="57180-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="57180-120">См. также</span><span class="sxs-lookup"><span data-stu-id="57180-120">See also</span></span>

[<span data-ttu-id="57180-121">Общие сведения о членстве в сохраняемом чате</span><span class="sxs-lookup"><span data-stu-id="57180-121">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)