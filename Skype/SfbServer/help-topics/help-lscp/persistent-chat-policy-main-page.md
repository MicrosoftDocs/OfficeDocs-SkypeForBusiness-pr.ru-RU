---
title: Главная страница политики сохраняемого чата
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Страницу Политика сохраняемого чата группы Сохраняемый чат можно использовать для управления политиками на глобальном уровне, на уровне пула, сайта или пользователя, в том числе для настройки глобальной политики по умолчанию и создания одной или нескольких дополнительных политик пользователей или сайтов для вашего развертывания. Если пользователю разрешено ведение постоянного сервера чата с помощью политики, то серверная среда сохраняемого чата появляется на своем клиенте.
ms.openlocfilehash: 053e7fb4f03f7e152a238a3b155eac161433c141
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822522"
---
# <a name="persistent-chat-policy-main-page"></a><span data-ttu-id="b0e8c-104">Главная страница политики сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="b0e8c-104">Persistent Chat Policy Main Page</span></span>
 
<span data-ttu-id="b0e8c-105">Страницу **Политика сохраняемого чата** группы **Сохраняемый чат** можно использовать для управления политиками на глобальном уровне, на уровне пула, сайта или пользователя, в том числе для настройки глобальной политики по умолчанию и создания одной или нескольких дополнительных политик пользователей или сайтов для вашего развертывания.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="b0e8c-106">Если пользователю разрешено ведение постоянного сервера чата с помощью политики, то серверная среда сохраняемого чата появляется на своем клиенте.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-106">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b0e8c-107">В топологии политики сайтов сервера сохраняемого чата применяются глобально, в пул пользователей или на сайт пользователя или на каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-107">In the topology, Persistent Chat Server site policies apply globally, per user's pool, or per user's site, or per user.</span></span> 
  
<span data-ttu-id="b0e8c-108">Глобальная политика создается автоматически при развертывании сервера сохраняемого чата и может быть настроена, но не удалена.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-108">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="b0e8c-109">Так как Глобальная политика применяется ко всем пользователям, ее не нужно настраивать для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-109">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="b0e8c-110">Вы можете создать и настроить несколько политик сайта и пользователей, которые вместе с глобальной политикой позволяют пользователям использовать сохраняемый сервер чата.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-110">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="b0e8c-111">Политики сервера для работы с сохраненными разчатами для пула и сайтов переопределяют глобальную политику сервера сохраняемого чата, но только для пользователей этого сайта.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-111">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="b0e8c-112">Политики пользователей переопределяют как глобальную политику, так и политики пулов и сайтов для тех пользователей, кому назначены такие политики пользователей.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-112">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b0e8c-113">Чтобы настроить и использовать сохраняемый сервер чата, необходимо сначала использовать Topology Builder, чтобы добавить в топологию постоянную поддержку сервера чата, а затем опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-113">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="b0e8c-114">Дополнительные сведения можно найти [в разделе Добавление постоянного сервера чата в топологию 2015 в Skype для бизнеса Server](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="b0e8c-114">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="b0e8c-115">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="b0e8c-115">Tasks that you can perform</span></span>

<span data-ttu-id="b0e8c-116">На странице **Политика сохраняемого чата** можно выполнить следующие задачи: включение и управление политикой сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-116">You can perform the following tasks on the **Persistent Chat Policy** page: enable and manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="b0e8c-117">Настройка глобальной политики для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="b0e8c-117">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="b0e8c-118">Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-118">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b0e8c-119">В меню **Пуск** выберите Панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-119">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="b0e8c-120">На панели управления Skype для бизнеса Server нажмите кнопку **сохраняемый чат**и выберите пункт **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-120">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="b0e8c-121">Нажмите пункт **Глобальная** в списке политик, выберите **Изменить**, затем **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-121">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b0e8c-122">В окне **Изменение политики сохраняемого чата — глобальная политика** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-122">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="b0e8c-123">В поле **Имя** укажите новое имя глобальной политики, если не следует использовать значение по умолчанию "Глобальная".</span><span class="sxs-lookup"><span data-stu-id="b0e8c-123">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="b0e8c-124">В разделе **Описание**укажите сведения о политике пользователя (например, "Глобальная политика для _централситенаме_").</span><span class="sxs-lookup"><span data-stu-id="b0e8c-124">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="b0e8c-125">Чтобы управлять сохраняемым чат для всех сайтов и пользователей, не контролируемых с помощью политики сайта или политики пользователя, установите или снимите флажок **включить сохраняемый чат** .</span><span class="sxs-lookup"><span data-stu-id="b0e8c-125">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="b0e8c-126">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-126">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="b0e8c-127">Создание политики сохраняемого чата для сайта</span><span class="sxs-lookup"><span data-stu-id="b0e8c-127">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="b0e8c-128">Для каждого сайта, который вы развернули, вы можете создать политику постоянной беседы для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-128">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="b0e8c-129">Конфигурация в политике сайта переопределяет глобальную политику, но только для сайта, к которому применяется эта политика.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-129">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="b0e8c-130">Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-130">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b0e8c-131">В меню **Пуск** выберите Панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="b0e8c-132">В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="b0e8c-133">Нажмите кнопку **Создать** и выберите **Политика сайта**.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-133">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="b0e8c-134">В окне **Выбор сайта** нажмите сайт, к которому нужно применить эту политику.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-134">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="b0e8c-135">В окне **Создание политики сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-135">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="b0e8c-136">В поле **Имя** укажите имя новой политики сайта (например, Редмонд).</span><span class="sxs-lookup"><span data-stu-id="b0e8c-136">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="b0e8c-137">В поле **Описание** укажите сведения о цели политики сайта (например, политика комнаты чата для сайта Редмонд).</span><span class="sxs-lookup"><span data-stu-id="b0e8c-137">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="b0e8c-138">Чтобы управлять сохраняемым чатом для всех сайтов, которые не контролируются политикой сайта, установите или снимите флажок **Разрешить сохраняемый чат**.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-138">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="b0e8c-139">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-139">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="b0e8c-140">Создание политики пользователей для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="b0e8c-140">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="b0e8c-141">На панели управления Skype для бизнеса Server вы можете определить **политики пользователей,** которые можно назначать пользователям.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-141">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="b0e8c-142">Политика пользователя переопределяет глобальную политику и политики сайта, но только для пользователей, которым она назначена.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-142">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="b0e8c-143">Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-143">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b0e8c-144">В меню **Пуск** выберите Панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-144">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="b0e8c-145">В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-145">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="b0e8c-146">Нажмите кнопку **Создать** и выберите **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-146">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="b0e8c-147">В окне **Создание политики сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-147">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="b0e8c-148">В поле **Имя** укажите имя новой политики пользователя.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-148">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="b0e8c-149">В разделе **Описание**укажите сведения о политике пользователя (например, политика постоянного чата для определенного пользователя).</span><span class="sxs-lookup"><span data-stu-id="b0e8c-149">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="b0e8c-150">Чтобы настроить сохраняемый чат для всех пользователей, которые не управляются с помощью политики пользователя, установите или снимите флажок **включить сохраняемый чат** .</span><span class="sxs-lookup"><span data-stu-id="b0e8c-150">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="b0e8c-151">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-151">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="b0e8c-152">Применение политики пользователя сохраняемого чата к учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="b0e8c-152">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="b0e8c-153">Если для пользователя включена поддержка Skype для бизнеса, вы можете применить соответствующие политики к определенным пользователям, чтобы включить или отключить их для постоянного сервера чата.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-153">If a user has been enabled for Skype for Business, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="b0e8c-154">С помощью описанной в этом разделе процедуры примените ранее созданную политику постоянного чата к одной или нескольким учетным записям пользователей или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-154">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="b0e8c-155">Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-155">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b0e8c-156">В меню **Пуск** выберите Панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-156">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="b0e8c-157">В левой панели навигации нажмите **Пользователи** и выполните поиск учетной записи, которую вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-157">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="b0e8c-158">В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-158">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b0e8c-159">В диалоговом окне **изменение пользователя Lync Server** в разделе **Политика сохраняемого чата**выберите политику пользователей сохраняемого чата, которую вы хотите применить.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-159">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b0e8c-160">Автоматические параметры применяются к действующей политике по умолчанию. \*\* \<\> \*\*</span><span class="sxs-lookup"><span data-stu-id="b0e8c-160">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="b0e8c-161">Данные параметры автоматически применяются сервером.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-161">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="b0e8c-162">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="b0e8c-162">Click **Commit**.</span></span>
    

