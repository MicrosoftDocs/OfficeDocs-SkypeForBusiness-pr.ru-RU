---
title: Настройка пользовательских политик сохраняемого чата в Skype для бизнеса Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Сводка: Прочтите этот раздел, чтобы узнать, как создание начальной пользовательских политик для сервера сохраняемого чата в Скайп для Business Server 2015. Пользовательские политики persistent Chat определение ли доступны пользователям доступ к комнатам чата.'
ms.openlocfilehash: 01ed6eb048f1949c93260c554eb58d0c76c5259f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="a5c07-104">Настройка пользовательских политик сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="a5c07-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a5c07-105">**Сводка:** Прочтите этот раздел, чтобы узнать, как создание начальной пользовательских политик для сервера сохраняемого чата в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a5c07-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="a5c07-106">Пользовательские политики persistent Chat определение ли доступны пользователям доступ к комнатам чата.</span><span class="sxs-lookup"><span data-stu-id="a5c07-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="a5c07-107">Можно управлять политиками пользователя сервера сохраняемого чата на следующих уровнях: глобальная, на уровне сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="a5c07-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="a5c07-108">Сначала можно настроить глобальную политику, чтобы включить использование параметров сохраняемого чата для всех пользователей в развертывании, а затем создать дополнительные политики пользователя и сайта с целью управления возможностью включения сохраняемого чата для определенных пользователей и сайтов.</span><span class="sxs-lookup"><span data-stu-id="a5c07-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="a5c07-109">В этой статье содержатся следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="a5c07-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="a5c07-110">Настройка глобальной политики</span><span class="sxs-lookup"><span data-stu-id="a5c07-110">Configure the global policy</span></span>
    
- <span data-ttu-id="a5c07-111">Создание политики сайта</span><span class="sxs-lookup"><span data-stu-id="a5c07-111">Create a site policy</span></span>
    
- <span data-ttu-id="a5c07-112">Создание политики пользователя</span><span class="sxs-lookup"><span data-stu-id="a5c07-112">Create a user policy</span></span>
    
- <span data-ttu-id="a5c07-113">Применение политики к пользователю или группе пользователей</span><span class="sxs-lookup"><span data-stu-id="a5c07-113">Apply a policy to a user or user group</span></span>
    
## <a name="configure-the-global-policy"></a><span data-ttu-id="a5c07-114">Настройка глобальной политики</span><span class="sxs-lookup"><span data-stu-id="a5c07-114">Configure the global policy</span></span>

<span data-ttu-id="a5c07-115">Чтобы настроить глобальную политику, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a5c07-115">To configure the global policy:</span></span>
  
1. <span data-ttu-id="a5c07-116">Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a5c07-116">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a5c07-117">Из меню **Пуск** выберите Скайп для панели управления Business Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="a5c07-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="a5c07-118">В Скайп для панели управления Business Server щелкните **Сохраняемый чат**и выберите **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="a5c07-118">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="a5c07-119">Нажмите пункт **Глобальная** в списке политик, выберите **Изменить**, затем **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="a5c07-119">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a5c07-120">В окне **Изменение политики сохраняемого чата — глобальная политика** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a5c07-120">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="a5c07-121">В поле **Имя** укажите новое имя глобальной политики, если не следует использовать значение по умолчанию "Глобальная".</span><span class="sxs-lookup"><span data-stu-id="a5c07-121">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="a5c07-122">В разделе **Описание**приведены подробные сведения о том, что политики пользователя (например, глобальная политика для _Имя_центрального_сайта_).</span><span class="sxs-lookup"><span data-stu-id="a5c07-122">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="a5c07-123">Чтобы управлять сохраняемым чатом для всех сайтов и пользователей, которые не управляются на уровне сайта или политика пользователя, установите или снимите флажок **Разрешить сохраняемый чат** .</span><span class="sxs-lookup"><span data-stu-id="a5c07-123">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="a5c07-124">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a5c07-124">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="a5c07-125">Создание политики сайта</span><span class="sxs-lookup"><span data-stu-id="a5c07-125">Create a site policy</span></span>

<span data-ttu-id="a5c07-126">Для каждого развернутого сайта можно создать определенную политику сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="a5c07-126">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="a5c07-127">Конфигурация политики сайта переопределяет глобальную политику, но только для определенного указанного в политике сайта.</span><span class="sxs-lookup"><span data-stu-id="a5c07-127">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="a5c07-128">Чтобы создать политику сайта, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a5c07-128">To create a site policy:</span></span>
  
1. <span data-ttu-id="a5c07-129">Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a5c07-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a5c07-130">Из меню **Пуск** выберите Скайп для панели управления Business Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="a5c07-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="a5c07-131">В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="a5c07-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="a5c07-132">Нажмите кнопку **Создать** и выберите **Политика сайта**.</span><span class="sxs-lookup"><span data-stu-id="a5c07-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="a5c07-133">В окне **Выбор сайта** нажмите сайт, к которому нужно применить эту политику.</span><span class="sxs-lookup"><span data-stu-id="a5c07-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="a5c07-134">В окне **Создание политики сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a5c07-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="a5c07-135">В поле **Имя** укажите имя новой политики сайта (например, Редмонд).</span><span class="sxs-lookup"><span data-stu-id="a5c07-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="a5c07-136">В поле **Описание** укажите сведения о цели политики сайта (например, политика комнаты чата для сайта Редмонд).</span><span class="sxs-lookup"><span data-stu-id="a5c07-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="a5c07-137">Чтобы управлять сохраняемым чатом для всех сайтов, которые не контролируются политикой сайта, установите или снимите флажок **Разрешить сохраняемый чат**.</span><span class="sxs-lookup"><span data-stu-id="a5c07-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="a5c07-138">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a5c07-138">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="a5c07-139">Создание политики пользователя</span><span class="sxs-lookup"><span data-stu-id="a5c07-139">Create a user policy</span></span>

<span data-ttu-id="a5c07-140">Можно создать определенные политики пользователя, которые переопределяют глобальную политику и любые политики сайта, к которому принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="a5c07-140">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="a5c07-141">Чтобы создать политику пользователя, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a5c07-141">To create a user policy:</span></span>
  
1. <span data-ttu-id="a5c07-142">Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a5c07-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a5c07-143">Из меню **Пуск** выберите Скайп для панели управления Business Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="a5c07-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="a5c07-144">В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="a5c07-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="a5c07-145">Нажмите кнопку **Создать** и выберите **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="a5c07-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="a5c07-146">В окне **Создание политики сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a5c07-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="a5c07-147">В поле **Имя** укажите имя новой политики пользователя.</span><span class="sxs-lookup"><span data-stu-id="a5c07-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="a5c07-148">В разделе **Описание**приведены подробные сведения о том, что политики пользователя (например, политика сохраняемого чата для определенного пользователя).</span><span class="sxs-lookup"><span data-stu-id="a5c07-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="a5c07-149">Чтобы управлять сохраняемым чатом для всех пользователей, которые не контролируются политикой пользователя, установите или снимите флажок **Разрешить сохраняемый чат** .</span><span class="sxs-lookup"><span data-stu-id="a5c07-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="a5c07-150">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a5c07-150">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="a5c07-151">Применение политики к учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="a5c07-151">Apply a policy to a user account</span></span>

<span data-ttu-id="a5c07-152">После создания политик их можно применить к учетной записи пользователя следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a5c07-152">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="a5c07-153">Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a5c07-153">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a5c07-154">Из меню **Пуск** выберите Скайп для панели управления Business Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="a5c07-154">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="a5c07-155">В левой панели навигации нажмите **Пользователи** и выполните поиск учетной записи, которую вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="a5c07-155">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="a5c07-156">В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="a5c07-156">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a5c07-157">В **Скайп изменение для пользователя Business Server** в разделе **Политика сохраняемого чата**выберите Persistent Chat политику пользователя, который вы хотите применить.</span><span class="sxs-lookup"><span data-stu-id="a5c07-157">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a5c07-158">** \<Автоматического\> ** применение параметров действующей политики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a5c07-158">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="a5c07-159">Данные параметры автоматически применяются сервером.</span><span class="sxs-lookup"><span data-stu-id="a5c07-159">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="a5c07-160">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a5c07-160">Click **Commit**.</span></span>
    

