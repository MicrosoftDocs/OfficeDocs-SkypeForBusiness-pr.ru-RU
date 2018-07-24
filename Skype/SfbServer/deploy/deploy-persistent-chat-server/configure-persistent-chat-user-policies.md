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
ms.openlocfilehash: 186611977a1a9dfa77549e8f0c5df6b863718eee
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21000838"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="74ba6-104">Настройка пользовательских политик сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="74ba6-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="74ba6-105">**Сводка:** Прочтите этот раздел, чтобы узнать, как создание начальной пользовательских политик для сервера сохраняемого чата в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="74ba6-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="74ba6-106">Пользовательские политики persistent Chat определение ли доступны пользователям доступ к комнатам чата.</span><span class="sxs-lookup"><span data-stu-id="74ba6-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="74ba6-107">Можно управлять политиками пользователя сервера сохраняемого чата на следующих уровнях: глобальная, на уровне сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="74ba6-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="74ba6-108">Сначала можно настроить глобальную политику, чтобы включить использование параметров сохраняемого чата для всех пользователей в развертывании, а затем создать дополнительные политики пользователя и сайта с целью управления возможностью включения сохраняемого чата для определенных пользователей и сайтов.</span><span class="sxs-lookup"><span data-stu-id="74ba6-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="74ba6-109">В этой статье содержатся следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="74ba6-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="74ba6-110">Настройка глобальной политики</span><span class="sxs-lookup"><span data-stu-id="74ba6-110">Configure the global policy</span></span>
    
- <span data-ttu-id="74ba6-111">Создание политики сайта</span><span class="sxs-lookup"><span data-stu-id="74ba6-111">Create a site policy</span></span>
    
- <span data-ttu-id="74ba6-112">Создание политики пользователя</span><span class="sxs-lookup"><span data-stu-id="74ba6-112">Create a user policy</span></span>
    
- <span data-ttu-id="74ba6-113">Применение политики к пользователю или группе пользователей</span><span class="sxs-lookup"><span data-stu-id="74ba6-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="74ba6-114">Сохраняемый чат доступна в Скайп для Business Server 2015, но больше не поддерживается в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="74ba6-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="74ba6-115">Те же функциональные возможности доступны в группах.</span><span class="sxs-lookup"><span data-stu-id="74ba6-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="74ba6-116">Для получения дополнительных сведений см [Реализация из Скайп для бизнеса для групп Майкрософт](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="74ba6-116">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="74ba6-117">Если необходимо использовать сохраняемого чата, возможны либо перенос пользователей, которым требуется эта функция групп, или для дальнейшего использования Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="74ba6-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="74ba6-118">Настройка глобальной политики</span><span class="sxs-lookup"><span data-stu-id="74ba6-118">Configure the global policy</span></span>

<span data-ttu-id="74ba6-119">Чтобы настроить глобальную политику, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="74ba6-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="74ba6-120">Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="74ba6-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="74ba6-121">Из меню **Пуск** выберите Скайп для панели управления Business Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="74ba6-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="74ba6-122">В Скайп для панели управления Business Server щелкните **Сохраняемый чат**и выберите **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="74ba6-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="74ba6-123">Нажмите пункт **Глобальная** в списке политик, выберите **Изменить**, затем **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="74ba6-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="74ba6-124">В окне **Изменение политики сохраняемого чата — глобальная политика** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="74ba6-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="74ba6-125">В поле **Имя** укажите новое имя глобальной политики, если не следует использовать значение по умолчанию "Глобальная".</span><span class="sxs-lookup"><span data-stu-id="74ba6-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="74ba6-126">В разделе **Описание**приведены подробные сведения о том, что политики пользователя (например, глобальная политика для _Имя_центрального_сайта_).</span><span class="sxs-lookup"><span data-stu-id="74ba6-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="74ba6-127">Чтобы управлять сохраняемым чатом для всех сайтов и пользователей, которые не управляются на уровне сайта или политика пользователя, установите или снимите флажок **Разрешить сохраняемый чат** .</span><span class="sxs-lookup"><span data-stu-id="74ba6-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="74ba6-128">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="74ba6-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="74ba6-129">Создание политики сайта</span><span class="sxs-lookup"><span data-stu-id="74ba6-129">Create a site policy</span></span>

<span data-ttu-id="74ba6-130">Для каждого развернутого сайта можно создать определенную политику сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="74ba6-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="74ba6-131">Конфигурация политики сайта переопределяет глобальную политику, но только для определенного указанного в политике сайта.</span><span class="sxs-lookup"><span data-stu-id="74ba6-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="74ba6-132">Чтобы создать политику сайта, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="74ba6-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="74ba6-133">Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="74ba6-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="74ba6-134">Из меню **Пуск** выберите Скайп для панели управления Business Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="74ba6-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="74ba6-135">В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="74ba6-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="74ba6-136">Нажмите кнопку **Создать** и выберите **Политика сайта**.</span><span class="sxs-lookup"><span data-stu-id="74ba6-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="74ba6-137">В окне **Выбор сайта** нажмите сайт, к которому нужно применить эту политику.</span><span class="sxs-lookup"><span data-stu-id="74ba6-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="74ba6-138">В окне **Создание политики сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="74ba6-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="74ba6-139">В поле **Имя** укажите имя новой политики сайта (например, Редмонд).</span><span class="sxs-lookup"><span data-stu-id="74ba6-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="74ba6-140">В поле **Описание** укажите сведения о цели политики сайта (например, политика комнаты чата для сайта Редмонд).</span><span class="sxs-lookup"><span data-stu-id="74ba6-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="74ba6-141">Чтобы управлять сохраняемым чатом для всех сайтов, которые не контролируются политикой сайта, установите или снимите флажок **Разрешить сохраняемый чат**.</span><span class="sxs-lookup"><span data-stu-id="74ba6-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="74ba6-142">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="74ba6-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="74ba6-143">Создание политики пользователя</span><span class="sxs-lookup"><span data-stu-id="74ba6-143">Create a user policy</span></span>

<span data-ttu-id="74ba6-144">Можно создать определенные политики пользователя, которые переопределяют глобальную политику и любые политики сайта, к которому принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="74ba6-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="74ba6-145">Чтобы создать политику пользователя, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="74ba6-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="74ba6-146">Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="74ba6-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="74ba6-147">Из меню **Пуск** выберите Скайп для панели управления Business Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="74ba6-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="74ba6-148">В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="74ba6-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="74ba6-149">Нажмите кнопку **Создать** и выберите **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="74ba6-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="74ba6-150">В окне **Создание политики сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="74ba6-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="74ba6-151">В поле **Имя** укажите имя новой политики пользователя.</span><span class="sxs-lookup"><span data-stu-id="74ba6-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="74ba6-152">В разделе **Описание**приведены подробные сведения о том, что политики пользователя (например, политика сохраняемого чата для определенного пользователя).</span><span class="sxs-lookup"><span data-stu-id="74ba6-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="74ba6-153">Чтобы управлять сохраняемым чатом для всех пользователей, которые не контролируются политикой пользователя, установите или снимите флажок **Разрешить сохраняемый чат** .</span><span class="sxs-lookup"><span data-stu-id="74ba6-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="74ba6-154">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="74ba6-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="74ba6-155">Применение политики к учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="74ba6-155">Apply a policy to a user account</span></span>

<span data-ttu-id="74ba6-156">После создания политик их можно применить к учетной записи пользователя следующим образом:</span><span class="sxs-lookup"><span data-stu-id="74ba6-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="74ba6-157">Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="74ba6-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="74ba6-158">Из меню **Пуск** выберите Скайп для панели управления Business Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="74ba6-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="74ba6-159">В левой панели навигации нажмите **Пользователи** и выполните поиск учетной записи, которую вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="74ba6-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="74ba6-160">В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="74ba6-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="74ba6-161">В **Скайп изменение для пользователя Business Server** в разделе **Политика сохраняемого чата**выберите Persistent Chat политику пользователя, который вы хотите применить.</span><span class="sxs-lookup"><span data-stu-id="74ba6-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="74ba6-162">** \<Автоматического\> ** применение параметров действующей политики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="74ba6-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="74ba6-163">Данные параметры автоматически применяются сервером.</span><span class="sxs-lookup"><span data-stu-id="74ba6-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="74ba6-164">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="74ba6-164">Click **Commit**.</span></span>
    

