---
title: Перенос групп ответа
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: После переноса пользователей в пулы Skype для бизнеса Server 2019 можно перенести группы ответа. Миграция групп ответа включает копирование групп агентов, очередей, бизнес-процессов, звуковых файлов и перемещение контактных объектов группы ответа из устаревшего развертывания в пул Skype для бизнеса Server 2019. После переноса устаревших групп ответа звонки в группы ответа обрабатываются приложением группы ответа в пуле Skype для бизнеса Server 2019. Вызовы групп ответа больше не будут обрабатываться устаревшим пулом.
ms.openlocfilehash: 03b0ffd900b5d7c23dd6ff680d56c0c4db53d8dc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752681"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="e783a-106">Перенос групп ответа</span><span class="sxs-lookup"><span data-stu-id="e783a-106">Migrate response groups</span></span>

<span data-ttu-id="e783a-107">После переноса пользователей в пулы Skype для бизнеса Server 2019 можно перенести группы ответа.</span><span class="sxs-lookup"><span data-stu-id="e783a-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="e783a-108">Миграция групп ответа включает копирование групп агентов, очередей, бизнес-процессов, звуковых файлов и перемещение контактных объектов группы ответа из устаревшего развертывания в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e783a-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="e783a-109">После переноса устаревших групп ответа вызовы в группы ответа обрабатываются приложением группы ответа в пуле Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e783a-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="e783a-110">Вызовы групп ответа больше не будут обрабатываться устаревшим пулом.</span><span class="sxs-lookup"><span data-stu-id="e783a-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e783a-111">Хотя вы можете перенести группы ответа перед перемещением всех пользователей в пул Skype для бизнеса Server 2019, рекомендуется сначала переместить всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="e783a-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="e783a-112">В частности, пользователи, которые являются агентами группы ответа, не будут иметь полной функциональности новых функций, пока они не будут перемещены в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e783a-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="e783a-113">Перед миграцией групп ответа необходимо развернуть пул Skype для бизнеса Server 2019, который включает приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="e783a-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="e783a-114">Приложение группы ответа устанавливается и активируется по умолчанию при развертывании Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="e783a-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e783a-115">Чтобы убедиться в том, что приложение группы ответа установлено, вы можете с помощью **get-CsService -ApplicationServer.**</span><span class="sxs-lookup"><span data-stu-id="e783a-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e783a-116">Вы можете создать новые группы ответа Skype для бизнеса Server 2019 в пуле Skype для бизнеса Server 2019 перед переносом устаревших групп ответа.</span><span class="sxs-lookup"><span data-stu-id="e783a-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="e783a-117">Чтобы перенести группы ответа из устаревшего пула в Skype для бизнеса Server 2019, запустите **cmdlet Move-CsRgsConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="e783a-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e783a-118">При миграции группы ответа конфигурация группы ответа перемещается для всего пула.</span><span class="sxs-lookup"><span data-stu-id="e783a-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="e783a-119">Нельзя выбрать для миграции конкретные группы, очереди или рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="e783a-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="e783a-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span><span class="sxs-lookup"><span data-stu-id="e783a-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="e783a-121">При переносе групп ответа устаревшие группы ответа не удаляются.</span><span class="sxs-lookup"><span data-stu-id="e783a-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="e783a-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span><span class="sxs-lookup"><span data-stu-id="e783a-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="e783a-123">Обновления следует применять только к группам ответа Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e783a-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="e783a-124">Устаревшие группы ответа сохраняются только для отката.</span><span class="sxs-lookup"><span data-stu-id="e783a-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="e783a-125">После завершения миграции и создания новых групп ответа на панели управления Skype для бизнеса Server и в оболочке управления Skype для бизнеса Server будут отображаться устаревшие версии и версии каждой группы ответа в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e783a-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="e783a-126">Не используйте панель управления Skype для бизнеса Server или skype для бизнеса Server Management Shell для удаления устаревших групп ответа.</span><span class="sxs-lookup"><span data-stu-id="e783a-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="e783a-127">Если удалить его, соответствующая группа ответа, созданная во время миграции, перестанет работать.</span><span class="sxs-lookup"><span data-stu-id="e783a-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="e783a-128">Устаревшие группы ответа будут удалены при выводе устаревшего пула из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="e783a-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e783a-129">Рекомендуется не удалять данные предыдущего развертывания до ликвидации пула.</span><span class="sxs-lookup"><span data-stu-id="e783a-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="e783a-130">Кроме того, настоятельно рекомендуется экспортировать группы ответов сразу же после миграции.</span><span class="sxs-lookup"><span data-stu-id="e783a-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="e783a-131">Если устаревшая группа ответа должна быть удалена, вы можете восстановить группы ответа из резервной копии, чтобы снова запускать группы ответа Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e783a-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="e783a-132">Skype для бизнеса Server 2019 представляет новую функцию группы ответа под названием **"Тип рабочего процесса".**</span><span class="sxs-lookup"><span data-stu-id="e783a-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="e783a-133">**Тип рабочего процесса** может быть **управляемым** или **неуправляемым**.</span><span class="sxs-lookup"><span data-stu-id="e783a-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="e783a-134">Все группы ответа переносятся с помощью **неуправляемого\*\*\*\*типа рабочего процесса** и с пустым списком управляющих.</span><span class="sxs-lookup"><span data-stu-id="e783a-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="e783a-135">При выполнении командлета **Move-CsRgsConfiguration** группы агентов, очереди, рабочие процессы и звуковые файлы остаются в устаревшем пуле на случай отката.</span><span class="sxs-lookup"><span data-stu-id="e783a-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="e783a-136">Однако если потребуется откат в устаревший пул, придется выполнить командлет **Move-CsApplicationEndpoint**, чтобы переместить контактные объекты обратно в устаревший пул.</span><span class="sxs-lookup"><span data-stu-id="e783a-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="e783a-137">Следующая процедура переноса конфигураций группы ответа предполагает, что между устаревшими пулами и пулами Skype для бизнеса Server 2019 имеется отношение "один к одному".</span><span class="sxs-lookup"><span data-stu-id="e783a-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="e783a-138">Если вы планируете консолидировать или разделить пулы во время миграции и развертывания, необходимо спланировать, какой устаревший пул сопобится с пулом Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e783a-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="e783a-139">Перенос конфигураций группы ответа</span><span class="sxs-lookup"><span data-stu-id="e783a-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="e783a-140">Войдите в компьютер с учетной записью, которая является членом группы RTCUniversalServerAdmins или имеет эквивалентные права и разрешения администратора.</span><span class="sxs-lookup"><span data-stu-id="e783a-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="e783a-141">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Microsoft Skype для бизнеса Server **2019"** и щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="e783a-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e783a-142">Запустите:</span><span class="sxs-lookup"><span data-stu-id="e783a-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="e783a-143">Пример:</span><span class="sxs-lookup"><span data-stu-id="e783a-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="e783a-144">После переноса групп ответа и агентов в пул Skype для бизнеса Server 2019 url-адрес, который агенты используют для входов  и выходов, является URL-адресом Skype для бизнеса Server 2019 и доступен в меню "Сервис".</span><span class="sxs-lookup"><span data-stu-id="e783a-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="e783a-145">Напомните агентам обновить все ссылки, например закладки, с учетом этого нового URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="e783a-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e783a-146">Проверка миграции группы ответа с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e783a-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e783a-147">Войдите в компьютер с учетной записью, которая является членом группы RTCUniversalReadOnlyAdmins или как минимум членом роли CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e783a-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="e783a-148">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e783a-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="e783a-149">Подробные сведения о различных методах запуска панели управления Skype для бизнеса Server см. в средствах администрирования Open Skype для бизнеса [Server 2019.](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx)</span><span class="sxs-lookup"><span data-stu-id="e783a-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="e783a-150">В левой панели навигации выберите пункт **Группы ответа**.</span><span class="sxs-lookup"><span data-stu-id="e783a-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="e783a-151">На **вкладке "Рабочий** процесс" убедитесь, что все процессы в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="e783a-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="e783a-152">Перейдите **на вкладку** "Очередь" и убедитесь, что все очереди в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="e783a-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="e783a-153">Перейдите **на вкладку "Группа"** и убедитесь, что все группы агентов в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="e783a-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e783a-154">Проверка миграции группы ответа с помощью оболочки управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e783a-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="e783a-155">Войдите в компьютер с учетной записью, которая является членом группы RTCUniversalReadOnlyAdmins или как минимум членом роли CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e783a-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="e783a-156">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Microsoft Skype для бизнеса Server **2019"** и щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="e783a-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="e783a-157">Чтобы получить сведения о следующих командлетах, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e783a-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="e783a-158">Запустите:</span><span class="sxs-lookup"><span data-stu-id="e783a-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="e783a-159">Убедитесь, что все группы агентов в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="e783a-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="e783a-160">Запустите:</span><span class="sxs-lookup"><span data-stu-id="e783a-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="e783a-161">Убедитесь, что все очереди в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="e783a-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="e783a-162">Запустите:</span><span class="sxs-lookup"><span data-stu-id="e783a-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="e783a-163">Убедитесь, что все процессы в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="e783a-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

