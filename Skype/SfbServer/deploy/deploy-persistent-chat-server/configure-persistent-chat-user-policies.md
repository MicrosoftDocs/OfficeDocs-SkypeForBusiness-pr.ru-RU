---
title: Настройка политик пользователей сохраняемой беседы в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: Сводка. В этом разделе вы узнаете, как создать начальные политики пользователей для сервера сохраняемой беседы в Skype для бизнеса Server 2015. Политики пользователей сохраняемой беседы определяют, разрешен ли пользователям доступ к комнатам чата.
ms.openlocfilehash: 531146a55b0282db191f503ef39e9be9e4d5f879
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802119"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="d01aa-104">Настройка политик пользователей сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="d01aa-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d01aa-105">**Сводка:** В этом разделе вы узнаете, как создать начальные политики пользователей для сервера сохраняемой беседы в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d01aa-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="d01aa-106">Политики пользователей сохраняемой беседы определяют, разрешен ли пользователям доступ к комнатам чата.</span><span class="sxs-lookup"><span data-stu-id="d01aa-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="d01aa-107">Вы можете управлять политиками пользователей сервера сохраняемой беседы на следующих уровнях: на глобальном уровне, на уровне сайта или на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="d01aa-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="d01aa-108">Сначала необходимо настроить глобальную политику, чтобы включить параметры сохраняемого чата для всех пользователей в развертывании, а затем создать дополнительные политики пользователей и сайтов, чтобы контролировать, включен ли сохраняемый чат для определенных пользователей и сайтов.</span><span class="sxs-lookup"><span data-stu-id="d01aa-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="d01aa-109">В этом разделе содержатся следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="d01aa-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="d01aa-110">Настройка глобальной политики</span><span class="sxs-lookup"><span data-stu-id="d01aa-110">Configure the global policy</span></span>
    
- <span data-ttu-id="d01aa-111">Создание политики сайта</span><span class="sxs-lookup"><span data-stu-id="d01aa-111">Create a site policy</span></span>
    
- <span data-ttu-id="d01aa-112">Создание политики пользователя</span><span class="sxs-lookup"><span data-stu-id="d01aa-112">Create a user policy</span></span>
    
- <span data-ttu-id="d01aa-113">Применение политики к пользователю или группе пользователей</span><span class="sxs-lookup"><span data-stu-id="d01aa-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="d01aa-114">Сохраняемая беседа доступна в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d01aa-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="d01aa-115">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="d01aa-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="d01aa-116">Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d01aa-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="d01aa-117">Если необходимо использовать сохраняемого чата, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить использование Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d01aa-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="d01aa-118">Настройка глобальной политики</span><span class="sxs-lookup"><span data-stu-id="d01aa-118">Configure the global policy</span></span>

<span data-ttu-id="d01aa-119">Чтобы настроить глобальную политику:</span><span class="sxs-lookup"><span data-stu-id="d01aa-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="d01aa-120">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d01aa-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d01aa-121">В меню **"Пуск"** выберите панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="d01aa-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d01aa-122">В панели управления Skype для бизнеса Server щелкните **"Сохраняемого** чата" и выберите "Политика сохраняемого **чата".**</span><span class="sxs-lookup"><span data-stu-id="d01aa-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="d01aa-123">Выберите **Глобальная** в списке политик, нажмите кнопку **Изменить**, а затем нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="d01aa-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d01aa-124">В окне **Изменение политики сохраняемого чата — глобальная политика** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d01aa-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="d01aa-125">В поле **Имя** введите новое имя глобальной политики, если вы не хотите использовать политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d01aa-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="d01aa-126">В **описании** укавите сведения о политике пользователя (например, "Глобальная политика _для centralSiteName")._</span><span class="sxs-lookup"><span data-stu-id="d01aa-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="d01aa-127">Чтобы управлять сохраняемого чата для всех сайтов и пользователей, которые  не контролируются политикой сайта или политикой пользователя, выберите или сохраняйте его.</span><span class="sxs-lookup"><span data-stu-id="d01aa-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="d01aa-128">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="d01aa-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="d01aa-129">Создание политики сайта</span><span class="sxs-lookup"><span data-stu-id="d01aa-129">Create a site policy</span></span>

<span data-ttu-id="d01aa-130">Для каждого развернутого сайта можно создать политику сохраняемого чата для конкретного сайта.</span><span class="sxs-lookup"><span data-stu-id="d01aa-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="d01aa-131">Конфигурация в политике сайта переопределяет глобальную политику, но только для того сайта, которому назначена эта политика.</span><span class="sxs-lookup"><span data-stu-id="d01aa-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="d01aa-132">Чтобы создать политику сайта:</span><span class="sxs-lookup"><span data-stu-id="d01aa-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="d01aa-133">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d01aa-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d01aa-134">В меню **"Пуск"** выберите панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="d01aa-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d01aa-135">В левой панели навигации щелкните **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="d01aa-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="d01aa-136">Нажмите кнопку **Создать** и щелкните **Политика сайта**.</span><span class="sxs-lookup"><span data-stu-id="d01aa-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="d01aa-137">В окне **Выбор сайта** щелкните сайт, к которому будет применена политика.</span><span class="sxs-lookup"><span data-stu-id="d01aa-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="d01aa-138">В окне **Создание политики сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d01aa-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="d01aa-139">В поле **Имя** введите имя новой политики сайта (например, Redmond).</span><span class="sxs-lookup"><span data-stu-id="d01aa-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="d01aa-140">В поле **Описание** введите сведения о политике сайта (например, политика комнаты чата для Redmond).</span><span class="sxs-lookup"><span data-stu-id="d01aa-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="d01aa-141">Чтобы управлять сохраняемым чатом для всех сайтов, которые не контролируются политикой сайта, установите или снимите флажок **Разрешить сохраняемый чат**.</span><span class="sxs-lookup"><span data-stu-id="d01aa-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="d01aa-142">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d01aa-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="d01aa-143">Создание политики пользователя</span><span class="sxs-lookup"><span data-stu-id="d01aa-143">Create a user policy</span></span>

<span data-ttu-id="d01aa-144">Можно создать политики для конкретных пользователей, переопределяют глобальную политику и любые политики сайта, к которым принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="d01aa-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="d01aa-145">Чтобы создать политику пользователя:</span><span class="sxs-lookup"><span data-stu-id="d01aa-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="d01aa-146">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d01aa-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d01aa-147">В меню **"Пуск"** выберите панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="d01aa-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d01aa-148">В левой панели навигации щелкните **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="d01aa-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="d01aa-149">Нажмите кнопку **Создать** и щелкните **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="d01aa-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="d01aa-150">В окне **Создание политики сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d01aa-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="d01aa-151">В поле **Имя** введите имя новой пользовательской политики.</span><span class="sxs-lookup"><span data-stu-id="d01aa-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="d01aa-152">В **описании** укачиваем сведения о политике пользователя (например, политика сохраняемого чата для определенного пользователя).</span><span class="sxs-lookup"><span data-stu-id="d01aa-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="d01aa-153">Чтобы управлять сохраняемого чата для всех пользователей, которые не  контролируются политикой пользователя, выберите или сохраняйте его.</span><span class="sxs-lookup"><span data-stu-id="d01aa-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="d01aa-154">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="d01aa-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="d01aa-155">Применение политики к учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="d01aa-155">Apply a policy to a user account</span></span>

<span data-ttu-id="d01aa-156">После создания политик их можно применить к учетной записи пользователя следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d01aa-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="d01aa-157">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d01aa-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d01aa-158">В меню **"Пуск"** выберите панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="d01aa-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d01aa-159">В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить.</span><span class="sxs-lookup"><span data-stu-id="d01aa-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="d01aa-160">В таблице со списком результатов поиска щелкните учетную запись пользователя, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="d01aa-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d01aa-161">In **Edit Skype for Business Server User** under Persistent Chat **policy**, select the Persistent Chat user policy that you want to apply.</span><span class="sxs-lookup"><span data-stu-id="d01aa-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d01aa-162">Параметры **\<Automatic\>** применяют эффективную политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d01aa-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="d01aa-163">Данный параметр автоматически применяется сервером.</span><span class="sxs-lookup"><span data-stu-id="d01aa-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="d01aa-164">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d01aa-164">Click **Commit**.</span></span>
    

