---
title: Надстройка сохраняемого чата
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: Вы можете использовать раздел надстройки страницы "Постоянный чат", чтобы связать URL-адреса со стойкими комнатами чата. Эти URL-адреса отображаются в клиенте в комнате чата в области разностойности беседы. Администратор должен добавить надстройки в список зарегистрированных надстройок, а администраторы и создатели чата должны связать комнаты с одной из зарегистрированных надстройок, прежде чем пользователи смогут увидеть это обновление в своем клиенте.
ms.openlocfilehash: c90383a26c658e8da73df09368a5d8fe04cfe69b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099505"
---
# <a name="persistent-chat-add-in"></a><span data-ttu-id="dc0c7-105">Надстройка сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="dc0c7-105">Persistent Chat Add-in</span></span>

<span data-ttu-id="dc0c7-106">Вы можете использовать раздел **надстройки** страницы **"Постоянный** чат", чтобы связать URL-адреса со стойкими комнатами чата.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="dc0c7-107">Эти URL-адреса отображаются в клиенте в комнате чата в области разностойности беседы.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="dc0c7-108">Администратор должен добавить надстройки в список зарегистрированных надстройок, а администраторы и создатели чата должны связать комнаты с одной из зарегистрированных надстройок, прежде чем пользователи смогут увидеть это обновление в своем клиенте.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>

<span data-ttu-id="dc0c7-109">Надстройки используются для расширения функций комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="dc0c7-110">Типичная надстройка может включать URL-адрес приложения Silverlight, который перехватывает при размещении тикера акций в комнате чата и отображает историю запасов в области простота.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="dc0c7-111">К другим примерам относится внедрение URL-адреса OneNote 2013 в комнату чата в виде надстройки для предоставления общего контекста, например темы дня.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<span data-ttu-id="dc0c7-112">Чтобы создать надстройки для постоянных чатов, см. в рубке Настройка надстройок для постоянных чатов [в Skype для бизнеса Server 2015.](../../manage/persistent-chat/configure-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="dc0c7-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="dc0c7-113">Если вы постоянный администратор чата, вы можете создавать надстройки с помощью панели управления или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="dc0c7-114">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="dc0c7-114">Tasks that you can perform</span></span>

<span data-ttu-id="dc0c7-115">На странице **Надстройка** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="dc0c7-115">You can perform the following tasks on the **Add-in** page:</span></span>

- [<span data-ttu-id="dc0c7-116">Настройка надстройок для постоянных чатов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="dc0c7-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="dc0c7-117">Настройка надстроек для комнат чата</span><span class="sxs-lookup"><span data-stu-id="dc0c7-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="dc0c7-118">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>

1. <span data-ttu-id="dc0c7-119">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="dc0c7-120">В меню **"Пуск"** выберите панель управления Skype для бизнес-серверов или откройте окно браузера, а затем введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="dc0c7-121">Сведения о различных методах, которые можно использовать для запуска панели управления, см. в материале [Open Lync Server Administrative Tools.](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools)</span><span class="sxs-lookup"><span data-stu-id="dc0c7-121">For details about the different methods that you can use to start the control panel, see [Open Lync Server Administrative Tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools).</span></span>

3. <span data-ttu-id="dc0c7-122">В левой панели навигации щелкните **Сохраняемый чат** и выберите пункт **Надстройка**.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>

    <span data-ttu-id="dc0c7-123">Для нескольких развертываний пула сохраняемого сервера чата выберите соответствующий пул из выпадаемого списка.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4. <span data-ttu-id="dc0c7-124">На странице **Надстройка** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-124">On the **Add-in** page, click **New**.</span></span>

5. <span data-ttu-id="dc0c7-125">В **Выберите службу** выберите службу, соответствующую пулу серверов сохраняемого чата, где необходимо создать надстройки.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="dc0c7-126">Надстройки нельзя переместить из одного пула в другой и нельзя сделать их общими для разных пулов.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6. <span data-ttu-id="dc0c7-127">В окне **Создание надстройки** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-127">In **New Add-in**, do the following:</span></span>

   - <span data-ttu-id="dc0c7-128">В поле **Имя** введите имя новой надстройки.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-128">In **Name**, specify a name for the new add-in.</span></span>

   - <span data-ttu-id="dc0c7-p107">В поле **URL-адрес** укажите URL-адрес, который необходимо связать с надстройкой. URL-адреса ограничены до протоколов HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7. <span data-ttu-id="dc0c7-131">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-131">Click **Commit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc0c7-132">См. также</span><span class="sxs-lookup"><span data-stu-id="dc0c7-132">See also</span></span>

<span data-ttu-id="dc0c7-133">Дополнительные сведения о настойчивых возможностях и возможностях чат-сервера см. в материале Plan [for Persistent Chat Server in Skype for Business Server 2015,](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)Deploy Persistent Chat Server in Skype for Business Server 2015 и [Manage Persistent Chat Server in Skype for Business Server 2015.](../../manage/persistent-chat/persistent-chat.md) [](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="dc0c7-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>