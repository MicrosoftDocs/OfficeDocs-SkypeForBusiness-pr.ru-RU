---
title: Главная страница надстройки сохраняемого чата
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
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: Вы можете использовать раздел надстройки на странице сохраняемого чата, чтобы связать URL-адреса с комнатами сохраняемого чата. Эти URL-адреса отображаются в клиенте в комнате чата в области возможностей беседы. Администратор должен добавить надстройки в список зарегистрированных надстройок, а руководители и создатели комнат чата должны связать комнаты с одной из зарегистрированных надстройок, прежде чем пользователи смогут увидеть это обновление в клиенте.
ms.openlocfilehash: ee747e12b4a6209d831588e68533531b0a7d95ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803799"
---
# <a name="persistent-chat-add-in-main-page"></a><span data-ttu-id="978d0-105">Главная страница надстройки сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="978d0-105">Persistent Chat Add-in Main Page</span></span>

<span data-ttu-id="978d0-106">Вы можете использовать раздел надстройки на странице **сохраняемого** чата, чтобы связать **URL-адреса** с комнатами сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="978d0-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="978d0-107">Эти URL-адреса отображаются в клиенте в комнате чата в области возможностей беседы.</span><span class="sxs-lookup"><span data-stu-id="978d0-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="978d0-108">Администратор должен добавить надстройки в список зарегистрированных надстройок, а руководители и создатели комнат чата должны связать комнаты с одной из зарегистрированных надстройок, прежде чем пользователи смогут увидеть это обновление в клиенте.</span><span class="sxs-lookup"><span data-stu-id="978d0-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>

<span data-ttu-id="978d0-109">Надстройки используются для расширения функций комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="978d0-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="978d0-110">Типичная надстройка может включать URL-адрес, указывав на приложение Silverlight, которое перехватывает публикацию биржевого деления в комнате чата и отображает историю акций в области возможностей.</span><span class="sxs-lookup"><span data-stu-id="978d0-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="978d0-111">К другим примерам относится внедрение URL-адреса OneNote 2013 в комнату чата в виде надстройки для предоставления общего контекста, например темы дня.</span><span class="sxs-lookup"><span data-stu-id="978d0-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<span data-ttu-id="978d0-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="978d0-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="978d0-113">Если вы администратор сохраняемого чата, вы можете создавать надстройки с помощью панели управления или Windows PowerShell управления.</span><span class="sxs-lookup"><span data-stu-id="978d0-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="978d0-114">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="978d0-114">Tasks you can perform</span></span>

<span data-ttu-id="978d0-115">На странице **Надстройка** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="978d0-115">You can perform the following tasks on the **Add-in** page:</span></span>

- [<span data-ttu-id="978d0-116">Настройка надстройки для комнат сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="978d0-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="978d0-117">Настройка надстроек для комнат чата</span><span class="sxs-lookup"><span data-stu-id="978d0-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="978d0-118">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="978d0-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>

1. <span data-ttu-id="978d0-119">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="978d0-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="978d0-120">В меню **"Пуск"** выберите панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="978d0-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="978d0-121">Подробные сведения о различных методах, которые можно использовать для запуска панели управления, см. в средстве [администрирования Open Lync Server.](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx)</span><span class="sxs-lookup"><span data-stu-id="978d0-121">For details about the different methods that you can use to start control panel, see [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span></span>

3. <span data-ttu-id="978d0-122">В левой панели навигации щелкните **Сохраняемый чат** и выберите пункт **Надстройка**.</span><span class="sxs-lookup"><span data-stu-id="978d0-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>

    <span data-ttu-id="978d0-123">Для нескольких развертываний пула серверов сохраняемого чата выберите соответствующий пул в выпадаемом списке.</span><span class="sxs-lookup"><span data-stu-id="978d0-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4. <span data-ttu-id="978d0-124">На странице **Надстройка** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="978d0-124">On the **Add-in** page, click **New**.</span></span>

5. <span data-ttu-id="978d0-125">В **области "Выбор службы"** выберите службу, соответствующую пулу серверов сохраняемого чата, в котором необходимо создать надстройки.</span><span class="sxs-lookup"><span data-stu-id="978d0-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="978d0-126">Надстройки нельзя переместить из одного пула в другой и нельзя сделать их общими для разных пулов.</span><span class="sxs-lookup"><span data-stu-id="978d0-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6. <span data-ttu-id="978d0-127">В окне **Создание надстройки** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="978d0-127">In **New Add-in**, do the following:</span></span>

   - <span data-ttu-id="978d0-128">В поле **Имя** введите имя новой надстройки.</span><span class="sxs-lookup"><span data-stu-id="978d0-128">In **Name**, specify a name for the new add-in.</span></span>

   - <span data-ttu-id="978d0-p107">В поле **URL-адрес** укажите URL-адрес, который необходимо связать с надстройкой. URL-адреса ограничены до протоколов HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="978d0-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7. <span data-ttu-id="978d0-131">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="978d0-131">Click **Commit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="978d0-132">См. также</span><span class="sxs-lookup"><span data-stu-id="978d0-132">See also</span></span>

<span data-ttu-id="978d0-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="978d0-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>


