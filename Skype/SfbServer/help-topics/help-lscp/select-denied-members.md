---
title: Выбор запрещенных участников
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: Администратор сохраняемого чата может создавать категории комнат чата и управлять ими. В рамках создания и управления категориями комнаты чата администратор сохраняемого чата может настраивать участников (для групп доменных служб Active Directory, контейнеров и пользователей), которые имеют доступ к участникам или создателям чатов в определенной категории. Администратор сохраняемого чата также может добавить Дениедмемберс в категорию, и они станут явными исключениями для списка разрешенных. Дениедмемберс переопределить содержимое в Алловедмемберс.
ms.openlocfilehash: c8b357abe49d794283b7165d9c5decdffaece275
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685889"
---
# <a name="select-denied-members"></a><span data-ttu-id="e08eb-106">Выбор запрещенных участников</span><span class="sxs-lookup"><span data-stu-id="e08eb-106">Select Denied Members</span></span>

<span data-ttu-id="e08eb-107">Администратор сохраняемого чата может создавать категории комнат чата и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="e08eb-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="e08eb-108">В рамках создания и управления категориями комнаты чата администратор сохраняемого чата может настраивать участников (для групп доменных служб Active Directory, контейнеров и пользователей), которые имеют доступ к участникам или создателям чатов в определенной категории.</span><span class="sxs-lookup"><span data-stu-id="e08eb-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="e08eb-109">Администратор сохраняемого чата также может добавить Дениедмемберс в категорию, и они станут явными исключениями для списка разрешенных.</span><span class="sxs-lookup"><span data-stu-id="e08eb-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="e08eb-110">Дениедмемберс переопределить содержимое в Алловедмемберс.</span><span class="sxs-lookup"><span data-stu-id="e08eb-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="e08eb-111">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="e08eb-111">Tasks that you can perform</span></span>

<span data-ttu-id="e08eb-112">На странице **Выберите запрещенных участников** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="e08eb-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="e08eb-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="e08eb-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="e08eb-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="e08eb-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="e08eb-115">Сведения о различных процедурах, которые можно выполнить с помощью панели управления "Skype для бизнеса Server", приведены в статье [Управление Skype для бизнеса server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="e08eb-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="e08eb-116">Настройка категорий для комнат чата</span><span class="sxs-lookup"><span data-stu-id="e08eb-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="e08eb-117">В разделе "участие в группе" **члены** **группы**"участники" добавляют и удаляют пользователей и других участников Active Directory, связанных с участниками, которые отклоняются из комнаты.</span><span class="sxs-lookup"><span data-stu-id="e08eb-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="e08eb-118">Сведения о функциях и возможностях сервера в чате можно найти в разделе [Обзор сохраняемого сервера чата](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e08eb-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="e08eb-119">Подробнее о работе с сохраняемыми конфигурациями сервера чата: [Настройка сервера сохраняемого чата](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) в документации по развертыванию и [управление Lync Server 2013, сохраняемый сервер чата](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="e08eb-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="e08eb-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e08eb-120">See also</span></span>

[<span data-ttu-id="e08eb-121">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="e08eb-121">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
