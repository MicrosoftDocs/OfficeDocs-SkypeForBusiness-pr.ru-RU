---
title: Выбор создателей
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
- ms.lync.lscp.SelectCreators
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8d9ed6f-22ba-470e-b0b4-0da3cea5e961
description: Создание и управление стойкими комнатами чата намного проще при правильном использовании категорий. Администратор сохраняемого чата может определять allowedMembers и Creators для каждой категории, а также определять параметры и поведение комнаты чата по умолчанию, которые будут применяться во всех комнатах чата, созданных в этой категории. Постоянные администраторы чата создают и управляют категориями с помощью панели управления Skype для бизнес-сервера или Windows PowerShell.
ms.openlocfilehash: 7d98ff058251b8bd14eb37a0ae5ba633f5a99c48
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107955"
---
# <a name="select-creators"></a><span data-ttu-id="16b00-105">Выбор создателей</span><span class="sxs-lookup"><span data-stu-id="16b00-105">Select Creators</span></span>

<span data-ttu-id="16b00-106">Создание и управление стойкими комнатами чата намного проще при правильном использовании категорий.</span><span class="sxs-lookup"><span data-stu-id="16b00-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="16b00-107">Администратор сохраняемого чата может определять **allowedMembers** и **Creators** для каждой категории, а также определять параметры и поведение комнаты чата по умолчанию, которые будут применяться во всех комнатах чата, созданных в этой категории.</span><span class="sxs-lookup"><span data-stu-id="16b00-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="16b00-108">Постоянные администраторы чата создают и управляют категориями с помощью панели управления Skype для бизнес-сервера или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16b00-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="16b00-109">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="16b00-109">Tasks that you can perform</span></span>

<span data-ttu-id="16b00-110">На странице **Выберите создателей** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="16b00-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="16b00-111">Настройка категорий</span><span class="sxs-lookup"><span data-stu-id="16b00-111">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="16b00-112">Новые функции сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="16b00-112">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="16b00-113">Сведения о различных процедурах, которые можно выполнить с помощью панели управления Skype для бизнес-серверов, см. в материале Управление Skype для бизнеса [Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="16b00-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="16b00-114">Настройка категорий для комнат чата</span><span class="sxs-lookup"><span data-stu-id="16b00-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="16b00-115">В **разделе Членство,** в разделе **Creators** добавьте или удалите пользователей и других директоров Active Directory, связанных с создателями для этой категории.</span><span class="sxs-lookup"><span data-stu-id="16b00-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="16b00-116">Автор — это пользователь, обладающий разрешениями на создание комнат чата и назначение их диспетчеров и участников.</span><span class="sxs-lookup"><span data-stu-id="16b00-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="16b00-117">Подробные сведения о возможностях и возможностях сохраняемого сервера чата см. в обзоре сохраняемого сервера [чата](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="16b00-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="16b00-118">Подробные сведения о работе с настойчивыми конфигурациями сервера чата см. в материале Настройка стойких серверов чата в документации по развертыванию и управление [Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) в документации по операциям. [](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server)</span><span class="sxs-lookup"><span data-stu-id="16b00-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="16b00-119">См. также</span><span class="sxs-lookup"><span data-stu-id="16b00-119">See also</span></span>

[<span data-ttu-id="16b00-120">Общие сведения о членстве в сохраняемом чате</span><span class="sxs-lookup"><span data-stu-id="16b00-120">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)

[<span data-ttu-id="16b00-121">Использование категорий для администрирования сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="16b00-121">Using Categories to Administer Persistent Chat Server</span></span>](/previous-versions/office/lync-server-2013/using-categories-to-administer-persistent-chat-server)

[<span data-ttu-id="16b00-122">Перемещение комнаты чата из одной категории в другую</span><span class="sxs-lookup"><span data-stu-id="16b00-122">Moving a Chat Room from One Category to Another</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-moving-a-chat-room-from-one-category-to-another)

[<span data-ttu-id="16b00-123">Создание или редактирование нового чата</span><span class="sxs-lookup"><span data-stu-id="16b00-123">Creating or Editing a New Room</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-editing-a-new-room)