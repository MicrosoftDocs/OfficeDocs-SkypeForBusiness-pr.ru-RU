---
title: Надстройка сохраняемого чата
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: В разделе Add-in страницы Persistent Chat можно использовать для сопоставления URL-адреса с комнатами Persistent Chat. Эти URL-адреса отображаются в клиенте в комнате чата в области расширения беседы. Администратор должен добавить надстройки в список зарегистрированных надстроек, а руководители или создатели комнат чата должны связать комнаты с одной из зарегистрированных надстроек, чтобы пользователи могли увидеть это обновление в клиенте.
ms.openlocfilehash: 8cac9a89bcccc66459d0663f9211d22c173f94a8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200683"
---
# <a name="persistent-chat-add-in"></a><span data-ttu-id="8ad7f-105">Надстройка сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="8ad7f-105">Persistent Chat Add-in</span></span>

<span data-ttu-id="8ad7f-106">В разделе **Add-in** страницы **Persistent Chat** можно использовать для сопоставления URL-адреса с комнатами Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="8ad7f-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="8ad7f-107">Эти URL-адреса отображаются в клиенте в комнате чата в области расширения беседы.</span><span class="sxs-lookup"><span data-stu-id="8ad7f-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="8ad7f-108">Администратор должен добавить надстройки в список зарегистрированных надстроек, а руководители или создатели комнат чата должны связать комнаты с одной из зарегистрированных надстроек, чтобы пользователи могли увидеть это обновление в клиенте.</span><span class="sxs-lookup"><span data-stu-id="8ad7f-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>

<span data-ttu-id="8ad7f-109">Надстройки используются для расширения доступных в комнате возможностей.</span><span class="sxs-lookup"><span data-stu-id="8ad7f-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="8ad7f-110">Типичная надстройки могут содержать URL-адрес приложение Silverlight, перехватывает при Финансовый символ представляется чата и отображает журнал запасов в области расширяемости.</span><span class="sxs-lookup"><span data-stu-id="8ad7f-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="8ad7f-111">К другим примерам относится внедрение URL-адреса OneNote в комнату чата в качестве надстройки, чтобы включить некоторый общий контекст — "Важные размышления" или "Тема дня".</span><span class="sxs-lookup"><span data-stu-id="8ad7f-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<span data-ttu-id="8ad7f-112">Создание надстроек для комнат сохраняемого чата, видеть [Настройка надстроек для комнат сохраняемого сеанса беседы в Скайп для Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="8ad7f-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="8ad7f-113">Если вы являетесь администратором Persistent Chat, можно создать надстроек с помощью панели управления или командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8ad7f-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="8ad7f-114">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="8ad7f-114">Tasks that you can perform</span></span>

<span data-ttu-id="8ad7f-115">На странице **Надстройка** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="8ad7f-115">You can perform the following tasks on the **Add-in** page:</span></span>

- [<span data-ttu-id="8ad7f-116">Настройка надстроек для комнат сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="8ad7f-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="8ad7f-117">Настройка надстроек для комнат чата</span><span class="sxs-lookup"><span data-stu-id="8ad7f-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="8ad7f-118">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="8ad7f-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>

1. <span data-ttu-id="8ad7f-119">Из учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator, выполните вход на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="8ad7f-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="8ad7f-120">Из меню **Пуск** выберите Скайп для панели управления Business Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="8ad7f-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="8ad7f-121">Дополнительные сведения о различных способах запуска панели управления см. в разделе [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span><span class="sxs-lookup"><span data-stu-id="8ad7f-121">For details about the different methods that you can use to start the control panel, see [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span></span>

3. <span data-ttu-id="8ad7f-122">В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Надстройка**.</span><span class="sxs-lookup"><span data-stu-id="8ad7f-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>

    <span data-ttu-id="8ad7f-123">Для нескольких развертываний пул серверов сохраняемого чата выберите соответствующий пул из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="8ad7f-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4. <span data-ttu-id="8ad7f-124">На странице **Надстройка** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="8ad7f-124">On the **Add-in** page, click **New**.</span></span>

5. <span data-ttu-id="8ad7f-125">В списке **поле выбора службы**выберите службы, соответствующий пул серверов сохраняемого чата, где необходимо создать надстройку.</span><span class="sxs-lookup"><span data-stu-id="8ad7f-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="8ad7f-126">Надстройки нельзя перемещать из одного пула в другой или совместно использовать разными пулами.</span><span class="sxs-lookup"><span data-stu-id="8ad7f-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6. <span data-ttu-id="8ad7f-127">В окне **Новая надстройка** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8ad7f-127">In **New Add-in**, do the following:</span></span>

   - <span data-ttu-id="8ad7f-128">В поле **Имя** укажите имя новой надстройки.</span><span class="sxs-lookup"><span data-stu-id="8ad7f-128">In **Name**, specify a name for the new add-in.</span></span>

   - <span data-ttu-id="8ad7f-p107">В поле **URL-адрес** укажите URL-адрес, который должен быть сопоставлен с данной надстройкой. Эти URL-адреса ограничены протоколами HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8ad7f-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7. <span data-ttu-id="8ad7f-131">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="8ad7f-131">Click **Commit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ad7f-132">См. также</span><span class="sxs-lookup"><span data-stu-id="8ad7f-132">See also</span></span>

<span data-ttu-id="8ad7f-133">Подробные сведения о сервера сохраняемого чата функций и возможностей, посвященной [планированию сервера сохраняемого чата в Скайп для Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Развернуть Persistent Chat Server в Скайп для Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)и [Управление сервера сохраняемого чата в Скайп для Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="8ad7f-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>


