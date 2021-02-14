---
title: Главная страница политики сохраняемого чата
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
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: Вы можете использовать страницу политики сохраняемого чата группы сохраняемого чата для управления политиками на глобальном уровне, на уровне пула, сайта или пользователя, включая настройку глобальной политики по умолчанию и создание одной или более дополнительных политик пользователей и сайтов для развертывания. Если пользователь включен для сервера сохраняемого чата с помощью политики, в клиенте появится среда сервера сохраняемого чата.
ms.openlocfilehash: 9664cbf182fe388fbffd2b270e306a4c17b36e95
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819309"
---
# <a name="persistent-chat-policy-main-page"></a><span data-ttu-id="d5101-104">Главная страница политики сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="d5101-104">Persistent Chat Policy Main Page</span></span>
 
<span data-ttu-id="d5101-105">Вы можете  использовать страницу политики сохраняемого чата группы сохраняемого чата для управления политиками на глобальном уровне, на уровне пула, сайта или пользователя, включая настройку глобальной политики по умолчанию и создание одной или более дополнительных политик пользователей и сайтов для развертывания. </span><span class="sxs-lookup"><span data-stu-id="d5101-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="d5101-106">Если пользователь включен для сервера сохраняемого чата с помощью политики, в клиенте появится среда сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="d5101-106">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d5101-107">В топологии политики сайта сервера сохраняемой беседы применяются глобально, для каждого пула пользователей, сайта пользователя или для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="d5101-107">In the topology, Persistent Chat Server site policies apply globally, per user's pool, or per user's site, or per user.</span></span> 
  
<span data-ttu-id="d5101-108">Глобальная политика создается автоматически при развертывании сервера сохраняемого чата и может быть настроена, но не удалена.</span><span class="sxs-lookup"><span data-stu-id="d5101-108">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="d5101-109">Поскольку глобальная политика применяется ко всем пользователям, ее не нужно устанавливать для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="d5101-109">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="d5101-110">Можно создать и настроить несколько политик сайтов и пользователей, которые вместе с глобальной политикой позволяют пользователям использовать сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="d5101-110">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="d5101-111">Политики сервера сохраняемого чата пула и сайта переопределяют глобальную политику сервера сохраняемого чата, но только для пользователей этого сайта.</span><span class="sxs-lookup"><span data-stu-id="d5101-111">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="d5101-112">Политики пользователей переопределяют как глобальную политику, так и политики пулов и сайтов для тех пользователей, кому назначены такие политики пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5101-112">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d5101-113">Чтобы настроить и использовать сервер сохраняемой беседы, необходимо сначала использовать построитель топологий, чтобы добавить поддержку сервера сохраняемой беседы в топологию, а затем опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="d5101-113">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="d5101-114">Дополнительные сведения см. в дополнительных сведениях о добавлении сервера сохраняемой беседы в топологию [Skype для бизнеса Server 2015.](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="d5101-114">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="d5101-115">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="d5101-115">Tasks that you can perform</span></span>

<span data-ttu-id="d5101-116">На странице "Политика сохраняемого чата" можно выполнить следующие задачи: включить политику сервера сохраняемого чата и управлять ей. </span><span class="sxs-lookup"><span data-stu-id="d5101-116">You can perform the following tasks on the **Persistent Chat Policy** page: enable and manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="d5101-117">Настройка глобальной политики для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="d5101-117">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="d5101-118">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d5101-118">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d5101-119">В меню **"Пуск"** выберите панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="d5101-119">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d5101-120">В панели управления Skype для бизнеса Server щелкните **"Сохраняемого** чата" и выберите "Политика сохраняемого **чата".**</span><span class="sxs-lookup"><span data-stu-id="d5101-120">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="d5101-121">Выберите **Глобальная** в списке политик, нажмите кнопку **Изменить**, а затем нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="d5101-121">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d5101-122">В окне **Изменение политики сохраняемого чата — глобальная политика** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d5101-122">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="d5101-123">В поле **Имя** введите новое имя глобальной политики, если вы не хотите использовать политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d5101-123">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="d5101-124">В **описании** укавите сведения о политике пользователя (например, "Глобальная политика _для centralSiteName")._</span><span class="sxs-lookup"><span data-stu-id="d5101-124">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="d5101-125">Чтобы управлять сохраняемого чата для всех сайтов и пользователей, которые  не контролируются политикой сайта или политикой пользователя, выберите или сохраняйте его.</span><span class="sxs-lookup"><span data-stu-id="d5101-125">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="d5101-126">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="d5101-126">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="d5101-127">Создание политики сохраняемого чата для сайта</span><span class="sxs-lookup"><span data-stu-id="d5101-127">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="d5101-128">Для каждого развернутого сайта можно создать политику сохраняемого чата для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="d5101-128">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="d5101-129">Конфигурация в политике сайта переопределяет глобальную политику, но только для того сайта, которому назначена эта политика.</span><span class="sxs-lookup"><span data-stu-id="d5101-129">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="d5101-130">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d5101-130">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d5101-131">В меню **"Пуск"** выберите панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="d5101-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d5101-132">В левой панели навигации щелкните **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="d5101-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="d5101-133">Нажмите кнопку **Создать** и щелкните **Политика сайта**.</span><span class="sxs-lookup"><span data-stu-id="d5101-133">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="d5101-134">В окне **Выбор сайта** щелкните сайт, к которому будет применена политика.</span><span class="sxs-lookup"><span data-stu-id="d5101-134">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="d5101-135">В окне **Создание политики сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d5101-135">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="d5101-136">В поле **Имя** введите имя новой политики сайта (например, Redmond).</span><span class="sxs-lookup"><span data-stu-id="d5101-136">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="d5101-137">В поле **Описание** введите сведения о политике сайта (например, политика комнаты чата для Redmond).</span><span class="sxs-lookup"><span data-stu-id="d5101-137">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="d5101-138">Чтобы управлять сохраняемым чатом для всех сайтов, которые не контролируются политикой сайта, установите или снимите флажок **Разрешить сохраняемый чат**.</span><span class="sxs-lookup"><span data-stu-id="d5101-138">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="d5101-139">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d5101-139">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="d5101-140">Создание политики пользователя для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="d5101-140">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="d5101-141">На панели управления Skype для бизнеса Server вы определяете политики пользователей, которые можно на назначены пользователям в **оснанатях "Пользователи".**</span><span class="sxs-lookup"><span data-stu-id="d5101-141">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="d5101-142">Пользовательская политики переопределяет глобальную политику и политики сайта, но только для пользователей, которым назначена эта политика.</span><span class="sxs-lookup"><span data-stu-id="d5101-142">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="d5101-143">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d5101-143">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d5101-144">В меню **"Пуск"** выберите панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="d5101-144">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d5101-145">В левой панели навигации щелкните **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="d5101-145">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="d5101-146">Нажмите кнопку **Создать** и щелкните **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="d5101-146">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="d5101-147">В окне **Создание политики сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d5101-147">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="d5101-148">В поле **Имя** введите имя новой пользовательской политики.</span><span class="sxs-lookup"><span data-stu-id="d5101-148">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="d5101-149">В **описании** укачиваем сведения о политике пользователя (например, политика сохраняемого чата для определенного пользователя).</span><span class="sxs-lookup"><span data-stu-id="d5101-149">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="d5101-150">Чтобы управлять сохраняемого чата для всех пользователей, которые не  контролируются политикой пользователя, выберите или сохраняйте его.</span><span class="sxs-lookup"><span data-stu-id="d5101-150">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="d5101-151">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="d5101-151">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="d5101-152">Применение политики пользователя сохраняемого чата к учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="d5101-152">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="d5101-153">Если для пользователя включена skype для бизнеса, вы можете применить соответствующие политики к определенным пользователям, чтобы включить или отключить их для сервера сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="d5101-153">If a user has been enabled for Skype for Business, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="d5101-154">Используйте процедуру, используемую в этом разделе, чтобы применить ранее созданную политику пользователей сохраняемого чата к одной или более учетным записям пользователей или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5101-154">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="d5101-155">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d5101-155">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d5101-156">В меню **"Пуск"** выберите панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="d5101-156">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d5101-157">В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить.</span><span class="sxs-lookup"><span data-stu-id="d5101-157">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="d5101-158">В таблице со списком результатов поиска щелкните учетную запись пользователя, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="d5101-158">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d5101-159">В **области "Изменение пользователя Lync Server"** в политике сохраняемого **чата** выберите политику пользователя сохраняемого чата, которую необходимо применить.</span><span class="sxs-lookup"><span data-stu-id="d5101-159">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d5101-160">Параметры **\<Automatic\>** применяют эффективную политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d5101-160">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="d5101-161">Данный параметр автоматически применяется сервером.</span><span class="sxs-lookup"><span data-stu-id="d5101-161">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="d5101-162">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d5101-162">Click **Commit**.</span></span>
    

