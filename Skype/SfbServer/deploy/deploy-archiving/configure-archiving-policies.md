---
title: Настройка политик архива для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: Сводка. В этом разделе вы узнаете, как настроить первоначальные политики архива для пользователей Skype для бизнеса Server.
ms.openlocfilehash: ab737305561aa20c873bbce6e0f075d17fedd0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820859"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="1675f-103">Настройка политик архива для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1675f-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="1675f-104">**Сводка:** В этом разделе вы узнаете, как настроить первоначальные политики архива для пользователей Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1675f-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="1675f-105">В Skype для бизнеса Server политики используются для того, чтобы включить и отключить архивировать внутренние и внешние коммуникации для пользователей, которые находятся в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1675f-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="1675f-106">Эта кнопка предоставляет доступ ко следующим командам:</span><span class="sxs-lookup"><span data-stu-id="1675f-106">This includes the following:</span></span>
  
- <span data-ttu-id="1675f-107">Глобальная политика, которая создается по умолчанию при развертывании Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1675f-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="1675f-108">Необязательные политики уровня сайта, определяющие реализации архива для определенного сайта</span><span class="sxs-lookup"><span data-stu-id="1675f-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="1675f-109">Необязательные политики на уровне пользователя, определяющие реализации архива для определенных пользователей</span><span class="sxs-lookup"><span data-stu-id="1675f-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="1675f-110">Политики архивации изначально устанавливаются при развертывании архивации, но после развертывания можно изменять, добавлять и удалять политики.</span><span class="sxs-lookup"><span data-stu-id="1675f-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="1675f-111">На панели управления Skype для бизнеса  Server для управления политиками на глобальном уровне, уровне сайта и пользователя можно использовать страницу политики архива в группе архива и мониторинга. </span><span class="sxs-lookup"><span data-stu-id="1675f-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1675f-112">Для управления реализацией архивации необходимо указать параметры, такие как архивировать мгновенные или видеоконференции, использование критического режима и параметры восстановления.</span><span class="sxs-lookup"><span data-stu-id="1675f-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="1675f-113">По умолчанию в глобальной конфигурации архивации или конфигурации архивации сайта или пула не включены никакие параметры.</span><span class="sxs-lookup"><span data-stu-id="1675f-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="1675f-114">Перед включением архива для внутренней или внешней связи необходимо указать все соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="1675f-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="1675f-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span><span class="sxs-lookup"><span data-stu-id="1675f-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1675f-116">Если для развертывания включена интеграция с Microsoft Exchange, политики удержания Exchange In-Place контролируют, включена ли архивация для пользователей, которые размещены в Exchange и наложены ли их почтовые ящики на In-Place удержание.</span><span class="sxs-lookup"><span data-stu-id="1675f-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="1675f-117">Подробные сведения о том, как работают политики архива, включая иерархию глобальных политик, политик сайтов и пользователей, см. в плане архива в [Skype для бизнеса Server.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="1675f-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="1675f-118">Подробные сведения об управлении политиками после развертывания см. в сведениях об управлении политиками [архивации в Skype для бизнеса Server.](../../manage/archiving/policies.md)</span><span class="sxs-lookup"><span data-stu-id="1675f-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="1675f-119">Глобальная политика</span><span class="sxs-lookup"><span data-stu-id="1675f-119">Global policy</span></span>

<span data-ttu-id="1675f-120">При развертывании серверов переднего сервера Skype для бизнеса Server создает глобальную политику для архива.</span><span class="sxs-lookup"><span data-stu-id="1675f-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="1675f-121">По умолчанию архивная архива в глобальной политике отключена.</span><span class="sxs-lookup"><span data-stu-id="1675f-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="1675f-122">Глобальная политика контролирует, включена ли архивация для внутренней и внешней связи для всего развертывания, если не настроены политики сайта или пользователя, переопределяющие глобальную политику, или если интеграция Microsoft Exchange используется для некоторых или всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="1675f-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="1675f-123">При использовании интеграции Microsoft Exchange глобальная политика не применяется к пользователям, которые находятся в Exchange и имеют почтовые ящики, In-Place удержание.</span><span class="sxs-lookup"><span data-stu-id="1675f-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="1675f-124">Настройка глобальной политики для архивных баз данных Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1675f-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="1675f-125">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1675f-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1675f-126">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1675f-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="1675f-127">В левой панели навигации щелкните **"Мониторинг и** архивации" и выберите "Политика **архивации".**</span><span class="sxs-lookup"><span data-stu-id="1675f-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="1675f-128">На странице **Archiving Policy** (Политика архивации) последовательно щелкните **Global** (Глобальная), **Edit** (Изменить) и **Show details** (Показать сведения).</span><span class="sxs-lookup"><span data-stu-id="1675f-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="1675f-129">На странице **Edit Archiving Policy - Global** (Изменение политики архивации — глобальный уровень) выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1675f-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="1675f-130">Если вы не хотите использовать имя Global по умолчанию, укажите в поле **Имя** новое имя глобальной политики.</span><span class="sxs-lookup"><span data-stu-id="1675f-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="1675f-131">В **описании** уделяем сведения о том, что такое политика (например, глобальная политика *для divisionName.*</span><span class="sxs-lookup"><span data-stu-id="1675f-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="1675f-132">Для управления архивацией внутренних коммуникаций для всех сайтов и пользователей, которые не управляются отдельными политиками на уровне сайта или пользователя, снимите или установите флажок **Archive internal communications** (Архивировать внутренние коммуникации).</span><span class="sxs-lookup"><span data-stu-id="1675f-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="1675f-133">Для управления архивацией внешних коммуникаций для всех сайтов и пользователей, которые не управляются отдельными политиками на уровне сайта или пользователя, снимите или установите флажок **Archive external communications** (Архивировать внешние коммуникации).</span><span class="sxs-lookup"><span data-stu-id="1675f-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="1675f-134">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="1675f-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="1675f-135">Политики сайта</span><span class="sxs-lookup"><span data-stu-id="1675f-135">Site policies</span></span>

<span data-ttu-id="1675f-136">Вы можете включить или отключить архивировать для определенных сайтов, создав политику архива для каждого из этих сайтов.</span><span class="sxs-lookup"><span data-stu-id="1675f-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="1675f-137">Политика сайта переопределяет глобальную политику, а политики пользователей — политики сайта.</span><span class="sxs-lookup"><span data-stu-id="1675f-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="1675f-138">Политики архивации применяются только в том случае, если вы не используете интеграцию с Microsoft Exchange или используете интеграцию с Microsoft Exchange, но некоторые пользователи, которые не находятся в Exchange и их почтовые ящики находятся на In-Place удержании.</span><span class="sxs-lookup"><span data-stu-id="1675f-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="1675f-139">Создание политики архива для сайта</span><span class="sxs-lookup"><span data-stu-id="1675f-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="1675f-140">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1675f-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1675f-141">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1675f-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1675f-142">В левой панели навигации щелкните **"Мониторинг и** архивации" и выберите "Политика **архивации".**</span><span class="sxs-lookup"><span data-stu-id="1675f-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="1675f-143">Подробные сведения о том, как работают политики архива, включая иерархию глобальных политик, политик сайтов и пользователей, см. в плане архива в [Skype для бизнеса Server.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="1675f-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="1675f-144">Нажмите кнопку **Создать** и выберите **Политика сайта**.</span><span class="sxs-lookup"><span data-stu-id="1675f-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="1675f-145">В поле **Выбор сайта** щелкните сайт, к которому требуется применить политику.</span><span class="sxs-lookup"><span data-stu-id="1675f-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="1675f-146">В области **Создать политику архивации** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1675f-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="1675f-147">В поле **Имя** укажите имя для политики сайта.</span><span class="sxs-lookup"><span data-stu-id="1675f-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="1675f-148">В поле **Описание** укажите сведения о назначении политики сайта (например, "политика сайта для Москвы").</span><span class="sxs-lookup"><span data-stu-id="1675f-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="1675f-149">Чтобы выбрать управление архивацией внутренних коммуникаций для указанного сайта, установите или снимите флажок **Архивация внутренних коммуникаций**.</span><span class="sxs-lookup"><span data-stu-id="1675f-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="1675f-150">Чтобы выбрать управление архивацией внешних коммуникаций для указанного сайта, установите или снимите флажок **Архивация внешних коммуникаций**.</span><span class="sxs-lookup"><span data-stu-id="1675f-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="1675f-151">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="1675f-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="1675f-152">Политики пользователей</span><span class="sxs-lookup"><span data-stu-id="1675f-152">User policies</span></span>

<span data-ttu-id="1675f-153">Вы можете включить или отключить архивировать для определенных пользователей, создав и настроив политику архива для пользователей, а затем применив политику к определенным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="1675f-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="1675f-154">Политики пользователей переопределяют любую глобальную политику и политики сайтов.</span><span class="sxs-lookup"><span data-stu-id="1675f-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="1675f-155">Политики архивации применяются только в том случае, если вы не используете интеграцию с Microsoft Exchange или используете интеграцию с Microsoft Exchange, но некоторые пользователи, которые не находятся в Exchange и их почтовые ящики находятся на In-Place удержании.</span><span class="sxs-lookup"><span data-stu-id="1675f-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="1675f-156">Настройка политики архива для пользователей, которые были в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1675f-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="1675f-157">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1675f-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1675f-158">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1675f-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="1675f-159">В левой панели навигации щелкните **"Мониторинг и** архивации" и выберите "Политика **архивации".**</span><span class="sxs-lookup"><span data-stu-id="1675f-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="1675f-160">Щелкните элемент **New** (Создать) и **User policy** (Политика пользователей).</span><span class="sxs-lookup"><span data-stu-id="1675f-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="1675f-161">В окне **New Archiving Policy** (Новая политика архивации) выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1675f-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="1675f-162">В поле **Name** (Имя) укажите имя политики пользователей.</span><span class="sxs-lookup"><span data-stu-id="1675f-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="1675f-163">В поле **Description** (Описание) укажите сведения о том, что из себя представляет данная политика пользователей (например, политика пользователей для юридического отдела).</span><span class="sxs-lookup"><span data-stu-id="1675f-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="1675f-164">Чтобы контролировать архивацию внутренних коммуникаций в рамках политики пользователей, установите или снимите флажок **Archive internal communications** (Архивировать внутренние коммуникации).</span><span class="sxs-lookup"><span data-stu-id="1675f-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="1675f-165">Чтобы контролировать архивацию внешних коммуникаций в рамках политики пользователей, установите или снимите флажок **Archive external communications** (Архивировать внешние коммуникации).</span><span class="sxs-lookup"><span data-stu-id="1675f-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="1675f-166">Щелкните элемент **Commit** (Исполнить).</span><span class="sxs-lookup"><span data-stu-id="1675f-166">Click **Commit**.</span></span>
    
<span data-ttu-id="1675f-167">Политика пользователей применяется только к тем пользователям, которым вы ее назначили.</span><span class="sxs-lookup"><span data-stu-id="1675f-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="1675f-168">Применение политики архива Skype для бизнеса Server к пользователю</span><span class="sxs-lookup"><span data-stu-id="1675f-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="1675f-169">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1675f-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1675f-170">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1675f-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="1675f-171">В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить.</span><span class="sxs-lookup"><span data-stu-id="1675f-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="1675f-172">В таблице со списком результатов поиска щелкните учетную запись пользователя, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="1675f-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="1675f-173">In **Edit Skype for Business Server user** under **Archiving policy,** select the archiving user policy that you want to apply.</span><span class="sxs-lookup"><span data-stu-id="1675f-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1675f-174">Параметры **\<Automatic\>** применяют параметры установки сервера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1675f-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="1675f-175">Данный параметр автоматически применяется сервером.</span><span class="sxs-lookup"><span data-stu-id="1675f-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="1675f-176">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1675f-176">Click **Commit**.</span></span>
    

