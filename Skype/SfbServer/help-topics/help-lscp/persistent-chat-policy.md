---
title: Политика сохраняемого чата
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: Страницу Политика сохраняемого чата группы Сохраняемый чат можно использовать для управления политиками на глобальном уровне, на уровне пула, сайта или пользователя, в том числе для настройки глобальной политики по умолчанию и создания одной или нескольких дополнительных политик пользователей или сайтов для вашего развертывания. Если сервера сохраняемого чата для пользователя включена политикой, среды сервера сохраняемого чата отображается в своих клиентов.
ms.openlocfilehash: 95020a24cc8f68c33028977cc5e4c3569423b219
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375785"
---
# <a name="persistent-chat-policy"></a><span data-ttu-id="90c4d-104">Политика сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="90c4d-104">Persistent Chat Policy</span></span>
 
<span data-ttu-id="90c4d-105">Страницу **Политика сохраняемого чата** группы **Сохраняемый чат** можно использовать для управления политиками на глобальном уровне, на уровне пула, сайта или пользователя, в том числе для настройки глобальной политики по умолчанию и создания одной или нескольких дополнительных политик пользователей или сайтов для вашего развертывания.</span><span class="sxs-lookup"><span data-stu-id="90c4d-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="90c4d-106">Если сервера сохраняемого чата для пользователя включена политикой, среды сервера сохраняемого чата отображается в своих клиентов.</span><span class="sxs-lookup"><span data-stu-id="90c4d-106">If Persistent Chat Server is enabled for a user by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
<span data-ttu-id="90c4d-107">Глобальную политику создается автоматически при развертывании сервера сохраняемого чата, и он может быть настроен, но не удаляется.</span><span class="sxs-lookup"><span data-stu-id="90c4d-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="90c4d-108">Так как глобальной политики применяется ко всем пользователям, его не должен устанавливаться на одного пользователя.</span><span class="sxs-lookup"><span data-stu-id="90c4d-108">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="90c4d-109">Можно создать и настроить несколько политик пользователей и сайтов, которые совместно с глобальной политики предоставляют пользователям для сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="90c4d-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="90c4d-110">Сайт и пул серверов сохраняемого чата переопределяют глобальной политики сервера сохраняемого чата, но только для пользователей этого сайта.</span><span class="sxs-lookup"><span data-stu-id="90c4d-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="90c4d-111">Политики пользователей переопределяют как глобальную политику, так и политики пулов и сайтов для тех пользователей, кому назначены такие политики пользователей.</span><span class="sxs-lookup"><span data-stu-id="90c4d-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="90c4d-112">Настройка и использование сервера сохраняемого чата, необходимо сначала добавить поддержку сервера сохраняемого чата в топологию с помощью построителя топологии и затем опубликовать эту топологию.</span><span class="sxs-lookup"><span data-stu-id="90c4d-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="90c4d-113">Дополнительные сведения см [Добавление сервера сохраняемого чата для вашей Скайп для топологии Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="90c4d-113">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="90c4d-114">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="90c4d-114">Tasks that you can perform</span></span>

<span data-ttu-id="90c4d-115">На странице **Политика сохраняемого чата** можно выполнить следующие задачи: включение сервера сохраняемого чата и управление политикой сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="90c4d-115">You can perform the following tasks on the **Persistent Chat Policy** page: enable Persistent Chat Server policy; manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="90c4d-116">Чтобы настроить глобальную политику для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="90c4d-116">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="90c4d-117">Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="90c4d-117">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="90c4d-118">Из меню **Пуск** выберите Скайп для панели управления Business Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="90c4d-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="90c4d-119">В Скайп для панели управления Business Server щелкните **Сохраняемый чат**и выберите **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="90c4d-119">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="90c4d-120">Нажмите пункт **Глобальная** в списке политик, выберите **Изменить**, затем **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="90c4d-120">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="90c4d-121">В окне **Изменение политики сохраняемого чата — глобальная политика** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="90c4d-121">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="90c4d-122">В поле **Имя** укажите новое имя глобальной политики, если не следует использовать значение по умолчанию "Глобальная".</span><span class="sxs-lookup"><span data-stu-id="90c4d-122">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="90c4d-123">В разделе **Описание**приведены подробные сведения о том, что политики пользователя (например, глобальная политика для _Имя_центрального_сайта_).</span><span class="sxs-lookup"><span data-stu-id="90c4d-123">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="90c4d-124">Чтобы управлять сохраняемым чатом для всех сайтов и пользователей, которые не управляются на уровне сайта или политика пользователя, установите или снимите флажок **Разрешить сохраняемый чат** .</span><span class="sxs-lookup"><span data-stu-id="90c4d-124">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="90c4d-125">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="90c4d-125">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="90c4d-126">Создание политики Persistent Chat для сайта</span><span class="sxs-lookup"><span data-stu-id="90c4d-126">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="90c4d-127">Для каждого развернутого сайта можно создать политику сайта Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="90c4d-127">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="90c4d-128">Конфигурация в политике сайта переопределяет глобальную политику, но только для сайта, к которому применяется эта политика.</span><span class="sxs-lookup"><span data-stu-id="90c4d-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="90c4d-129">Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="90c4d-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="90c4d-130">Из меню **Пуск** выберите Скайп для панели управления Business Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="90c4d-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="90c4d-131">В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="90c4d-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="90c4d-132">Нажмите кнопку **Создать** и выберите **Политика сайта**.</span><span class="sxs-lookup"><span data-stu-id="90c4d-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="90c4d-133">В окне **Выбор сайта** нажмите сайт, к которому нужно применить эту политику.</span><span class="sxs-lookup"><span data-stu-id="90c4d-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="90c4d-134">В окне **Создание политики сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="90c4d-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="90c4d-135">В поле **Имя** укажите имя новой политики сайта (например, Редмонд).</span><span class="sxs-lookup"><span data-stu-id="90c4d-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="90c4d-136">В поле **Описание** укажите сведения о цели политики сайта (например, политика комнаты чата для сайта Редмонд).</span><span class="sxs-lookup"><span data-stu-id="90c4d-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="90c4d-137">Чтобы управлять сохраняемым чатом для всех сайтов, которые не контролируются политикой сайта, установите или снимите флажок **Разрешить сохраняемый чат**.</span><span class="sxs-lookup"><span data-stu-id="90c4d-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="90c4d-138">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="90c4d-138">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="90c4d-139">Для создания пользовательской политики для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="90c4d-139">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="90c4d-140">Скайп для панели управления Business Server вы задаете политики пользователей, которые можно назначить пользователям в разделе **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="90c4d-140">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="90c4d-141">Политика пользователя переопределяет глобальную политику и политики сайта, но только для пользователей, которым она назначена.</span><span class="sxs-lookup"><span data-stu-id="90c4d-141">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="90c4d-142">Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="90c4d-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="90c4d-143">Из меню **Пуск** выберите Скайп для панели управления Business Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="90c4d-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="90c4d-144">В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="90c4d-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="90c4d-145">Нажмите кнопку **Создать** и выберите **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="90c4d-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="90c4d-146">В окне **Создание политики сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="90c4d-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="90c4d-147">В поле **Имя** укажите имя новой политики пользователя.</span><span class="sxs-lookup"><span data-stu-id="90c4d-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="90c4d-148">В разделе **Описание**приведены подробные сведения о том, что политики пользователя (например, политика сохраняемого чата для определенного пользователя).</span><span class="sxs-lookup"><span data-stu-id="90c4d-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="90c4d-149">Чтобы управлять сохраняемым чатом для всех пользователей, которые не контролируются политикой пользователя, установите или снимите флажок **Разрешить сохраняемый чат** .</span><span class="sxs-lookup"><span data-stu-id="90c4d-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="90c4d-150">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="90c4d-150">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="90c4d-151">Для применения политики Persistent Chat пользователя для учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="90c4d-151">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="90c4d-152">Если пользователь включен для Скайп для сервера, можно применить соответствующие политики к определенным пользователям, чтобы разрешить или запретить им для сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="90c4d-152">If a user has been enabled for Skype for Business Server, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="90c4d-153">Используйте описанную в этом разделе для применения ранее созданной политики Persistent Chat пользователя для одного или нескольких учетных записей пользователей или групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="90c4d-153">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="90c4d-154">Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="90c4d-154">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="90c4d-155">Из меню **Пуск** выберите Скайп для панели управления Business Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="90c4d-155">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="90c4d-156">В левой панели навигации нажмите **Пользователи** и выполните поиск учетной записи, которую вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="90c4d-156">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="90c4d-157">В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="90c4d-157">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="90c4d-158">В **Окне Изменение пользователя Lync Server** в разделе **Политика сохраняемого чата**выберите Persistent Chat политику пользователя, который вы хотите применить.</span><span class="sxs-lookup"><span data-stu-id="90c4d-158">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="90c4d-159">\*\* \<Автоматического\> \*\* применение параметров действующей политики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="90c4d-159">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="90c4d-160">Данные параметры автоматически применяются сервером.</span><span class="sxs-lookup"><span data-stu-id="90c4d-160">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="90c4d-161">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="90c4d-161">Click **Commit**.</span></span>
    

