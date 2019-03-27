---
title: Настройка политик архивации для Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Сводка: Сведения о сведения о настройке начальной политик архивации для Скайп для пользователей Business Server.'
ms.openlocfilehash: 88840d10cbd7a71b32b5079a8600018b97e8b0c3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876452"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="6838e-103">Настройка политик архивации для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="6838e-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="6838e-104">**Сводка:** Прочтите этот раздел, чтобы узнать, как Настройка начальной политик архивации для Скайп для пользователей Business Server.</span><span class="sxs-lookup"><span data-stu-id="6838e-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="6838e-105">В Скайп для Business Server использовать политики для включения и отключения архивации внутренних коммуникаций и внешних коммуникаций для пользователей, которые размещаются на Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="6838e-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="6838e-106">Доступны следующие политики:</span><span class="sxs-lookup"><span data-stu-id="6838e-106">This includes the following:</span></span>
  
- <span data-ttu-id="6838e-107">Глобальная политика, которая создается по умолчанию при развертывании Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="6838e-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="6838e-108">Дополнительная политика уровня сайта, в которой указан способ реализации архивации для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="6838e-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="6838e-109">Дополнительные политики на уровне пользователя, которые определяют, как архивация реализуется для определенных пользователей</span><span class="sxs-lookup"><span data-stu-id="6838e-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="6838e-110">Первичная настройка политик архивации выполняется при развертывании архивации, однако после развертывания можно выполнить изменение, добавление и удаление политик.</span><span class="sxs-lookup"><span data-stu-id="6838e-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="6838e-111">В Скайп для панели управления сервера Business страницу **Политика архивирования** **архивации и мониторинга** группы можно использовать для управления политиками на глобальном, веб-узла или пользователя.</span><span class="sxs-lookup"><span data-stu-id="6838e-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6838e-112">Для управления архивацией необходимо задать параметры, например включение или отключение архивации сеансов обмена мгновенными сообщениями и конференций, использование критического режима и параметры очистки.</span><span class="sxs-lookup"><span data-stu-id="6838e-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="6838e-113">По умолчанию все параметры глобальной конфигурации архивации или конфигурации архивации на уровне сайта или пула отключены.</span><span class="sxs-lookup"><span data-stu-id="6838e-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="6838e-114">Перед включением архивации внутренних и внешних коммуникаций необходимо задать все требуемые параметры.</span><span class="sxs-lookup"><span data-stu-id="6838e-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="6838e-115">Дополнительные сведения см [настроить параметры для Скайп для сервера архивации](configure-archiving-options.md).</span><span class="sxs-lookup"><span data-stu-id="6838e-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6838e-116">Если включить интеграцию с Microsoft Exchange для вашего развертывания, управления политики хранения на месте Exchange ли архивации для пользователей, которые размещаются на сервере Exchange и установить их почтовые ящики на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="6838e-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="6838e-117">Для получения дополнительных сведений о том, как архивации политики работы, включая иерархии для глобальной, сайта и политики пользователей, см. [Планирование архивации в Скайп для Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="6838e-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="6838e-118">Для получения дополнительных сведений об управлении политики после развертывания, см. [Управление политик архивации в Скайп для Business Server](../../manage/archiving/policies.md).</span><span class="sxs-lookup"><span data-stu-id="6838e-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="6838e-119">Глобальная политика</span><span class="sxs-lookup"><span data-stu-id="6838e-119">Global policy</span></span>

<span data-ttu-id="6838e-120">При развертывании вашего сервера переднего плана, Скайп для Business Server создает глобальной политики для архивации.</span><span class="sxs-lookup"><span data-stu-id="6838e-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="6838e-121">By default, archiving is disabled in the global policy.</span><span class="sxs-lookup"><span data-stu-id="6838e-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="6838e-122">Включение архивации для внутренних и внешних коммуникаций для всего развертывания, если вы не настроили политики сайта или пользователя, которые переопределить глобальную политику, или если интеграция с Microsoft Exchange для некоторых или всех управляет глобальной политики пользователи.</span><span class="sxs-lookup"><span data-stu-id="6838e-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="6838e-123">При использовании интеграции с Microsoft Exchange, глобальной политики не применяется для всех пользователей, которые размещаются на сервере Exchange, и у почтовых ящиков, поставленных на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="6838e-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="6838e-124">Настройка глобальной политики для архивации для Скайп для архивации баз данных Business Server</span><span class="sxs-lookup"><span data-stu-id="6838e-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="6838e-125">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6838e-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6838e-126">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="6838e-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="6838e-127">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Политика архивации**.</span><span class="sxs-lookup"><span data-stu-id="6838e-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="6838e-128">На странице **Политика архивации** последовательно нажмите **Глобальная**, **Изменить** и **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="6838e-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="6838e-129">На странице **Изменить политику архивации — глобальная** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6838e-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="6838e-130">Если вы не хотите использовать имя "Глобальная" по умолчанию, укажите в поле **Имя** новое имя глобальной политики.</span><span class="sxs-lookup"><span data-stu-id="6838e-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="6838e-131">В разделе **Описание**приведены сведения о том, что политики (например, глобальная политика для *имя_подразделения* .</span><span class="sxs-lookup"><span data-stu-id="6838e-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="6838e-132">Для управления архивацией внутренних коммуникаций для всех сайтов и пользователей, которые не управляются отдельными политиками на уровне сайта или пользователя, снимите или установите флажок **Архивация внутренних взаимодействий**.</span><span class="sxs-lookup"><span data-stu-id="6838e-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="6838e-133">Для управления архивацией внешних коммуникаций для всех сайтов и пользователей, которые не управляются отдельными политиками на уровне сайта или пользователя, снимите или установите флажок **Архивация внешних взаимодействий**.</span><span class="sxs-lookup"><span data-stu-id="6838e-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="6838e-134">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="6838e-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="6838e-135">Политики сайта</span><span class="sxs-lookup"><span data-stu-id="6838e-135">Site policies</span></span>

<span data-ttu-id="6838e-136">Архивацию можно включить или отключить для определенных сайтов, создав политику архивации для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="6838e-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="6838e-137">Политика сайта переопределяет глобальную политику, а политики пользователей — политики сайта.</span><span class="sxs-lookup"><span data-stu-id="6838e-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="6838e-138">Политики архивации применяются только в том случае, если вы не используете интеграции с Microsoft Exchange или при использовании интеграции с Microsoft Exchange, но установить некоторые пользователи, которые не размещаются на Exchange и иметь их почтовые ящики на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="6838e-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="6838e-139">Создание политики архивации для сайта</span><span class="sxs-lookup"><span data-stu-id="6838e-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="6838e-140">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6838e-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6838e-141">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="6838e-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="6838e-142">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Политика архивации**.</span><span class="sxs-lookup"><span data-stu-id="6838e-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="6838e-143">Для получения дополнительных сведений о том, как архивации политики работы, включая иерархии для глобальной, сайта и политики пользователей, см. [Планирование архивации в Скайп для Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="6838e-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="6838e-144">Нажмите кнопку **Создать** и выберите **Политика сайта**.</span><span class="sxs-lookup"><span data-stu-id="6838e-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="6838e-145">В окне **Выбор сайта** выберите сайт, к которому нужно применить эту политику.</span><span class="sxs-lookup"><span data-stu-id="6838e-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="6838e-146">В области **Создание новой политики архивации** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6838e-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="6838e-147">В поле **Имя** укажите имя для политики сайта.</span><span class="sxs-lookup"><span data-stu-id="6838e-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="6838e-148">В поле **Описание** укажите сведения о назначении политики сайта (например, "политика сайта для Redmond").</span><span class="sxs-lookup"><span data-stu-id="6838e-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="6838e-149">Чтобы выбрать управление архивацией внутренних коммуникаций для указанного сайта, установите или снимите флажок **Архивация внутренних взаимодействий**.</span><span class="sxs-lookup"><span data-stu-id="6838e-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="6838e-150">Чтобы выбрать управление архивацией внешних коммуникаций для указанного сайта, установите или снимите флажок **Архивация внешних взаимодействий**.</span><span class="sxs-lookup"><span data-stu-id="6838e-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="6838e-151">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="6838e-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="6838e-152">Политики пользователя</span><span class="sxs-lookup"><span data-stu-id="6838e-152">User policies</span></span>

<span data-ttu-id="6838e-153">Вы можете включить или отключить архивацию для отдельных пользователей, создав и настроив для пользователей политику архивации, а затем применив ее к отдельным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="6838e-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="6838e-154">Политики пользователей переопределяют любую глобальную политику и политики сайтов.</span><span class="sxs-lookup"><span data-stu-id="6838e-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="6838e-155">Политики архивации применяются только в том случае, если вы не используете интеграции с Microsoft Exchange или при использовании интеграции с Microsoft Exchange, но установить некоторые пользователи, которые не размещаются на Exchange и иметь их почтовые ящики на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="6838e-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="6838e-156">Настройка политики архивации для пользователей, размещенных на Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="6838e-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="6838e-157">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6838e-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6838e-158">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="6838e-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="6838e-159">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Политика архивации**.</span><span class="sxs-lookup"><span data-stu-id="6838e-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="6838e-160">Нажмите **Создать** и выберите **Политика пользователя**</span><span class="sxs-lookup"><span data-stu-id="6838e-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="6838e-161">В области **Создание новой политики архивации** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6838e-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="6838e-162">В поле **Имя** укажите имя политики пользователей.</span><span class="sxs-lookup"><span data-stu-id="6838e-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="6838e-163">В поле **Описание** укажите сведения о том, что из себя представляет данная политика пользователей (например, политика пользователей для юридического отдела).</span><span class="sxs-lookup"><span data-stu-id="6838e-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="6838e-164">Чтобы контролировать архивацию внутренних коммуникаций в рамках политики пользователей, установите или снимите флажок **Архивация внутренних взаимодействий**.</span><span class="sxs-lookup"><span data-stu-id="6838e-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="6838e-165">Чтобы контролировать архивацию внешних коммуникаций в рамках политики пользователей, установите или снимите флажок **Архивация внешних взаимодействий**.</span><span class="sxs-lookup"><span data-stu-id="6838e-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="6838e-166">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="6838e-166">Click **Commit**.</span></span>
    
<span data-ttu-id="6838e-167">Политика пользователей применяется только к тем пользователям, которым вы ее назначили.</span><span class="sxs-lookup"><span data-stu-id="6838e-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="6838e-168">Применение Скайп для сервера архивирование политику для пользователя</span><span class="sxs-lookup"><span data-stu-id="6838e-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="6838e-169">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6838e-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6838e-170">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="6838e-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="6838e-171">На панели навигации слева нажмите **Пользователи** и затем найдите учетную запись пользователя, которую необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="6838e-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="6838e-172">В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="6838e-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="6838e-173">В **Скайп изменение для пользователя Business Server** в поле **Политика архивация**выберите политику, которую нужно применить.</span><span class="sxs-lookup"><span data-stu-id="6838e-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6838e-174">\*\* \<Автоматического\> \*\* параметры применяются параметры установки сервера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6838e-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="6838e-175">Данные параметры автоматически применяются сервером.</span><span class="sxs-lookup"><span data-stu-id="6838e-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="6838e-176">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="6838e-176">Click **Commit**.</span></span>
    

