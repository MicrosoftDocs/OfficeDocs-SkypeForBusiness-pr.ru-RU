---
title: Перенос групп ответа
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После перемещения пользователей к Скайп для пулов Business Server 2019 можно выполнить миграцию групп ответа. Перенос ответа групп включает копирование группы агентов, очередей, рабочие процессы, звуковые файлы и перемещение контактных объектов группы ответа из устаревшего развертывания Скайп для пула Business Server 2019. После миграции устаревших групп ответа звонки для группы ответа обрабатывается приложения группы ответа в Скайп для пула Business Server 2019. Вызовы в группы ответа больше не обрабатывается устаревшего пула.
ms.openlocfilehash: 17ba19be3b574436f3a175457264654d8c28ebd0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876315"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="e4e98-106">Перенос групп ответа</span><span class="sxs-lookup"><span data-stu-id="e4e98-106">Migrate response groups</span></span>

<span data-ttu-id="e4e98-107">После перемещения пользователей к Скайп для пулов Business Server 2019 можно выполнить миграцию групп ответа.</span><span class="sxs-lookup"><span data-stu-id="e4e98-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="e4e98-108">Перенос ответа групп включает копирование группы агентов, очередей, рабочие процессы, звуковые файлы и перемещение контактных объектов группы ответа из устаревшего развертывания Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4e98-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="e4e98-109">После миграции устаревших групп ответа звонки для группы ответа обрабатывается приложения группы ответа в Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4e98-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="e4e98-110">Вызовы в группы ответа больше не обрабатывается устаревшего пула.</span><span class="sxs-lookup"><span data-stu-id="e4e98-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4e98-111">Несмотря на то, что можно Миграция групп ответа, прежде чем переместить всех пользователей в Скайп для пула Business Server 2019, рекомендуется сначала переместить всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="e4e98-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="e4e98-112">В частности пользователи будут агентов группы ответа не будут иметь полной функциональности новых функций, пока они перемещаются в Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4e98-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="e4e98-113">Перед миграцией групп ответа необходимо развернуть Скайп для пула Business Server 2019, который включает в себя приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="e4e98-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="e4e98-114">Приложение группы ответа устанавливается и активируется по умолчанию при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="e4e98-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e4e98-115">Можно обеспечить установку приложения группы ответа с помощью командлета **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="e4e98-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e4e98-116">Перед миграцией устаревших групп ответа, можно создать новые Скайп для групп ответа Business Server 2019 в Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4e98-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="e4e98-117">Миграция групп ответа из устаревшего пула Скайп для Business Server 2019, выполните командлет **Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="e4e98-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e4e98-118">Командлет миграции групп ответа перемещает конфигурации группы ответа для всего пула.</span><span class="sxs-lookup"><span data-stu-id="e4e98-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="e4e98-119">Нельзя выбрать определенных групп очереди и рабочие процессы для переноса.</span><span class="sxs-lookup"><span data-stu-id="e4e98-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="e4e98-120">После миграции групп ответа, необходимо использовать Скайп для панели управления Business Server или Скайп для командлеты командную консоль Business Server, чтобы убедиться, что все группы агентов, очереди и рабочие процессы были успешно перемещены.</span><span class="sxs-lookup"><span data-stu-id="e4e98-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="e4e98-121">При миграции групп ответа устаревших групп ответа не удаляются.</span><span class="sxs-lookup"><span data-stu-id="e4e98-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="e4e98-122">Если управление группами ответа после миграции с помощью любого из Скайп для панели управления Business Server или Скайп для консоли Business Server, могут видеть устаревших групп ответа и Скайп для групп ответа Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4e98-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="e4e98-123">Обновления должны применяться только к Скайп для групп ответа Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4e98-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="e4e98-124">Устаревших групп ответа, сохраняются только в целях отката.</span><span class="sxs-lookup"><span data-stu-id="e4e98-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="e4e98-125">После завершения переноса и будут созданы новые группы ответа, Скайп для панели управления Business Server и Скайп для консоли Business Server будет отображаться устаревший и Скайп для версий Business Server 2019 каждого ответа в группе.</span><span class="sxs-lookup"><span data-stu-id="e4e98-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="e4e98-126">Не используйте Скайп для панели управления Business Server или Скайп для консоли Business Server для удаления устаревших групп ответа.</span><span class="sxs-lookup"><span data-stu-id="e4e98-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="e4e98-127">Если удалить один, соответствующие группы ответа, который был создан во время миграции перестанет работать.</span><span class="sxs-lookup"><span data-stu-id="e4e98-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="e4e98-128">Устаревших групп ответа будут удалены при его ликвидации прежних версий.</span><span class="sxs-lookup"><span data-stu-id="e4e98-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e4e98-129">Мы рекомендуем не удалить все данные из предыдущего развертывания до его ликвидации.</span><span class="sxs-lookup"><span data-stu-id="e4e98-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="e4e98-130">Кроме того мы настоятельно рекомендуем Экспорт групп ответа сразу же после миграции.</span><span class="sxs-lookup"><span data-stu-id="e4e98-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="e4e98-131">Если необходимо получить удален группу ответа прежних версий, групп ответа можно будет восстановить из резервной копии для получения Скайп для повторного запуска групп ответа Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4e98-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="e4e98-132">Скайп для Business Server 2019 вводится новая функция группы ответа, называется **Тип рабочего процесса**.</span><span class="sxs-lookup"><span data-stu-id="e4e98-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="e4e98-133">**Тип рабочего процесса** может быть **управляемый** или **неуправляемый**.</span><span class="sxs-lookup"><span data-stu-id="e4e98-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="e4e98-134">Установка как **неуправляемый** **Тип рабочего процесса** и с пустым списком диспетчера переносятся все группы ответа.</span><span class="sxs-lookup"><span data-stu-id="e4e98-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="e4e98-135">При запуске командлета **Move-CsRgsConfiguration** группы агентов, очередей, рабочие процессы и звуковые файлы остаются в устаревшем пуле для отката целей.</span><span class="sxs-lookup"><span data-stu-id="e4e98-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="e4e98-136">Если требуется выполнить откат в устаревшем пуле, тем не менее, необходимо запустить командлет **Move-CsApplicationEndpoint** , чтобы возвратить контактные объекты в устаревшем пуле.</span><span class="sxs-lookup"><span data-stu-id="e4e98-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="e4e98-137">Следующую процедуру для миграции групп ответа конфигураций предполагается, что двустороннее отношение между старых пулов и Скайп для пулов Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4e98-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="e4e98-138">Если вы планируете консолидировать или разделить пулы во время миграции и развертывания, необходимо плана, какие устаревшего пула сопоставляет какие Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4e98-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="e4e98-139">Миграция конфигураций групп ответа</span><span class="sxs-lookup"><span data-stu-id="e4e98-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="e4e98-140">Войдите на компьютер с учетной записью, которая является членом группы RTCUniversalServerAdmins или имеет права и разрешения администратора эквивалентный.</span><span class="sxs-lookup"><span data-stu-id="e4e98-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="e4e98-141">Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп Microsoft для Business Server 2019**и нажмите кнопку **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="e4e98-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e4e98-142">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e4e98-142">Run:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="e4e98-143">Например:</span><span class="sxs-lookup"><span data-stu-id="e4e98-143">For example:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="e4e98-144">После миграции групп ответа и агентами в Скайп для пула Business Server 2019 URL-адрес, агенты выполняют вход и выход с Скайп для URL-адреса 2019 Business Server и доступен из меню " **Сервис** ".</span><span class="sxs-lookup"><span data-stu-id="e4e98-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="e4e98-145">Напоминание агенты для обновления всех ссылок, например закладок, новый URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="e4e98-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e4e98-146">Проверка миграции групп ответа с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="e4e98-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e4e98-147">Войдите на компьютер с учетной записью, которая является членом группы RTCUniversalReadOnlyAdmins или как минимум быть членом роли CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e4e98-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="e4e98-148">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="e4e98-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="e4e98-149">Для получения дополнительных сведений о различных способах, которые можно использовать для запуска Скайп для панели управления сервера Business видеть [Open Скайп для средств администрирования Business Server 2019](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span><span class="sxs-lookup"><span data-stu-id="e4e98-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="e4e98-150">На левой панели навигации слева щелкните элемент **Группы ответа**.</span><span class="sxs-lookup"><span data-stu-id="e4e98-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="e4e98-151">Убедитесь, что включены все рабочие процессы из старой среды в списке на вкладке **рабочего процесса** .</span><span class="sxs-lookup"><span data-stu-id="e4e98-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="e4e98-152">Перейдите на вкладку **очередь** и проверьте, все ли очереди из старой среды включены в список.</span><span class="sxs-lookup"><span data-stu-id="e4e98-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="e4e98-153">Перейдите на вкладку **Группа** и проверьте, все ли группы агентов в старой среды включены в список.</span><span class="sxs-lookup"><span data-stu-id="e4e98-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e4e98-154">Проверка миграции групп ответа с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="e4e98-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="e4e98-155">Войдите на компьютер с учетной записью, которая является членом группы RTCUniversalReadOnlyAdmins или как минимум быть членом роли CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e4e98-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="e4e98-156">Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп Microsoft для Business Server 2019**и нажмите кнопку **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="e4e98-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="e4e98-157">Для получения дополнительных сведений о следующих командлетах выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e4e98-157">For details about the following cmdlets, run:</span></span>
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="e4e98-158">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e4e98-158">Run:</span></span>
    
   ```
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="e4e98-159">Проверьте, все ли группы агентов в старой среды включены в список.</span><span class="sxs-lookup"><span data-stu-id="e4e98-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="e4e98-160">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e4e98-160">Run:</span></span>
    
   ```
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="e4e98-161">Проверьте, все ли очереди из старой среды включены в список.</span><span class="sxs-lookup"><span data-stu-id="e4e98-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="e4e98-162">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e4e98-162">Run:</span></span>
    
   ```
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="e4e98-163">Проверьте, все ли рабочие процессы из старой среды включены в список.</span><span class="sxs-lookup"><span data-stu-id="e4e98-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

