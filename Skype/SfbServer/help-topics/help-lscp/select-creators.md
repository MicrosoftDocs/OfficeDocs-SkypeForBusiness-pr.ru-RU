---
title: Выбор создателей
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.SelectCreators
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8d9ed6f-22ba-470e-b0b4-0da3cea5e961
description: Создавать сохраняемые комнаты чатов и управлять ими намного проще благодаря правильному использованию категорий. Администратор сохраняемого чата может определять Алловедмемберс и создателя для каждой категории, а также задавать параметры и поведения комнаты чата по умолчанию, которые будут применяться ко всем комнатам чата, созданным в этой категории. Сохраняемые администраторы чата создают категории и управляйте ими с помощью панели управления Skype для бизнеса Server или командлетов Windows PowerShell.
ms.openlocfilehash: cfaa7531f4f2a401dd90dc9473409d301a2fbfa6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699644"
---
# <a name="select-creators"></a><span data-ttu-id="0f251-105">Выбор создателей</span><span class="sxs-lookup"><span data-stu-id="0f251-105">Select Creators</span></span>

<span data-ttu-id="0f251-106">Создавать сохраняемые комнаты чатов и управлять ими намного проще благодаря правильному использованию категорий.</span><span class="sxs-lookup"><span data-stu-id="0f251-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="0f251-107">Администратор сохраняемого чата может определять **алловедмемберс** и **создателя** для каждой категории, а также задавать параметры и поведения комнаты чата по умолчанию, которые будут применяться ко всем комнатам чата, созданным в этой категории.</span><span class="sxs-lookup"><span data-stu-id="0f251-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="0f251-108">Сохраняемые администраторы чата создают категории и управляйте ими с помощью панели управления Skype для бизнеса Server или командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f251-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="0f251-109">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="0f251-109">Tasks that you can perform</span></span>

<span data-ttu-id="0f251-110">На странице **Выбор создателей** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="0f251-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="0f251-111">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="0f251-111">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="0f251-112">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="0f251-112">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="0f251-113">Сведения о различных процедурах, которые можно выполнить с помощью панели управления "Skype для бизнеса Server", приведены в статье [Управление Skype для бизнеса server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="0f251-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="0f251-114">Настройка категорий для комнат чата</span><span class="sxs-lookup"><span data-stu-id="0f251-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="0f251-115">В разделе " **участие**" в группе " **Создатели** " добавьте или удалите пользователей и других участников Active Directory, связанных с создателями для этой категории.</span><span class="sxs-lookup"><span data-stu-id="0f251-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="0f251-116">Автор — это пользователь, обладающий разрешениями на создание комнат чата и назначение их диспетчеров и участников.</span><span class="sxs-lookup"><span data-stu-id="0f251-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="0f251-117">Сведения о функциях и возможностях сервера в чате можно найти в разделе [Обзор сохраняемого сервера чата](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="0f251-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="0f251-118">Подробнее о работе с сохраняемыми конфигурациями сервера чата: [Настройка сервера сохраняемого чата](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) в документации по развертыванию и [управление Lync Server 2013, сохраняемый сервер чата](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="0f251-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f251-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0f251-119">See also</span></span>

[<span data-ttu-id="0f251-120">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="0f251-120">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

[<span data-ttu-id="0f251-121">Использование категорий для администрирования сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="0f251-121">Using Categories to Administer Persistent Chat Server</span></span>](https://technet.microsoft.com/library/dfcb3ad1-da90-467e-b08c-f4e68673b7b5.aspx)

[<span data-ttu-id="0f251-122">Перемещение комнаты чата из одной категории в другую</span><span class="sxs-lookup"><span data-stu-id="0f251-122">Moving a Chat Room from One Category to Another</span></span>](https://technet.microsoft.com/library/7e93b8f6-5a18-4476-a432-3918e01bcfa6.aspx)

[<span data-ttu-id="0f251-123">Создание и редактирование новой комнаты</span><span class="sxs-lookup"><span data-stu-id="0f251-123">Creating or Editing a New Room</span></span>](https://technet.microsoft.com/library/aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4.aspx)
