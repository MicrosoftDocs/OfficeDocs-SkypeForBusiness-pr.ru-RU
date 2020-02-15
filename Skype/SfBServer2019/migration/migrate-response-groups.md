---
title: Миграция групп ответа
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: После перемещения пользователей в пулы Skype для бизнеса Server 2019 вы можете перенести свои группы ответа. Миграция групп ответа включает копирование групп агентов, очередей, рабочих процессов, звуковых файлов и перемещение контактных объектов группы ответа из устаревшего развертывания в пул Skype для бизнеса Server 2019. После миграции устаревших групп ответа звонки в группы ответа обрабатываются приложением группы ответа в пуле Skype для бизнеса Server 2019. Вызовы групп ответа больше не будут обрабатываться устаревшим пулом.
ms.openlocfilehash: 2d439462fa103cc16fd7ae70b79364be7d79803a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42016110"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="48326-106">Миграция групп ответа</span><span class="sxs-lookup"><span data-stu-id="48326-106">Migrate response groups</span></span>

<span data-ttu-id="48326-107">После перемещения пользователей в пулы Skype для бизнеса Server 2019 вы можете перенести свои группы ответа.</span><span class="sxs-lookup"><span data-stu-id="48326-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="48326-108">Миграция групп ответа включает копирование групп агентов, очередей, рабочих процессов, звуковых файлов и перемещение контактных объектов группы ответа из устаревшего развертывания в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="48326-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="48326-109">После миграции устаревших групп ответа звонки в группы ответа обрабатываются приложением группы ответа в пуле Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="48326-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="48326-110">Вызовы групп ответа больше не будут обрабатываться устаревшим пулом.</span><span class="sxs-lookup"><span data-stu-id="48326-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="48326-111">Несмотря на то, что вы можете перенести группы ответа, прежде чем переместить всех пользователей в пул Skype для бизнеса Server 2019, рекомендуется сначала переместить всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="48326-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="48326-112">В частности, у пользователей, которые являются агентами группы ответа, не будут полностью функциональные возможности новых функций, пока они не будут перемещены в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="48326-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="48326-113">Перед миграцией групп ответа необходимо развернуть пул Skype для бизнеса Server 2019, включающий приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="48326-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="48326-114">Приложение группы ответа устанавливается и активируется по умолчанию при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="48326-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="48326-115">Чтобы убедиться, что приложение группы ответа установлено, запустите командлет **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="48326-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="48326-116">Вы можете создать новые группы ответа Skype для бизнеса Server 2019 в пуле Skype для бизнеса Server 2019, прежде чем вы перенесете старые группы ответа.</span><span class="sxs-lookup"><span data-stu-id="48326-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="48326-117">Чтобы перенести группы ответа из устаревшего пула в Skype для бизнеса Server 2019, выполните командлет **Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="48326-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="48326-118">Командлет миграции группы ответа перемещает конфигурацию группы ответа для всего пула.</span><span class="sxs-lookup"><span data-stu-id="48326-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="48326-119">Нельзя выбрать для миграции конкретные группы, очереди или рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="48326-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="48326-120">После миграции групп ответа необходимо использовать командлеты панели управления Skype для бизнеса Server или консоли управления Skype для бизнеса Server, чтобы убедиться, что все группы агентов, очереди и рабочие процессы перемещены успешно.</span><span class="sxs-lookup"><span data-stu-id="48326-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="48326-121">При миграции групп ответа устаревшие группы ответа не удаляются.</span><span class="sxs-lookup"><span data-stu-id="48326-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="48326-122">При управлении группами ответа после миграции с помощью панели управления Skype для бизнеса Server или консоли управления Skype для бизнеса Server вы можете видеть как устаревшие группы ответа, так и группы ответа Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="48326-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="48326-123">Обновление следует применять только к группам ответа Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="48326-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="48326-124">Устаревшие группы ответа хранятся только в целях отката.</span><span class="sxs-lookup"><span data-stu-id="48326-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="48326-125">После завершения миграции и создания новых групп ответа на панели управления Skype для бизнеса Server и в командной консоли Skype для бизнеса Server будут отображаться устаревшие и Skype для бизнеса Server 2019 версии каждого ответа. группы.</span><span class="sxs-lookup"><span data-stu-id="48326-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="48326-126">Не используйте панель управления Skype для бизнеса Server или консоль управления Skype для бизнеса Server, чтобы удалить устаревшие группы ответа.</span><span class="sxs-lookup"><span data-stu-id="48326-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="48326-127">Если удалить один из них, соответствующая ему группа ответа, созданная во время миграции, перестанет работать.</span><span class="sxs-lookup"><span data-stu-id="48326-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="48326-128">Устаревшие группы ответа будут удалены при списании устаревшего пула.</span><span class="sxs-lookup"><span data-stu-id="48326-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="48326-129">Рекомендуется не удалять данные предыдущего развертывания до ликвидации пула.</span><span class="sxs-lookup"><span data-stu-id="48326-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="48326-130">Кроме того, настоятельно рекомендуется экспортировать группы ответов сразу же после миграции.</span><span class="sxs-lookup"><span data-stu-id="48326-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="48326-131">Если старая группа ответа должна быть удалена, можно восстановить группы ответа из резервной копии, чтобы получить группы ответа Skype для бизнеса Server 2019, запущенные повторно.</span><span class="sxs-lookup"><span data-stu-id="48326-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="48326-132">В Skype для бизнеса Server 2019 новая функция группы ответа называется **тип рабочего процесса**.</span><span class="sxs-lookup"><span data-stu-id="48326-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="48326-133">**Тип рабочего процесса** может быть **управляемым** или **неуправляемым**.</span><span class="sxs-lookup"><span data-stu-id="48326-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="48326-134">Все группы ответа переносятся с помощью **неуправляемого\*\*\*\*типа рабочего процесса** и с пустым списком управляющих.</span><span class="sxs-lookup"><span data-stu-id="48326-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="48326-135">При выполнении командлета **Move-CsRgsConfiguration** группы агентов, очереди, рабочие процессы и звуковые файлы остаются в устаревшем пуле на случай отката.</span><span class="sxs-lookup"><span data-stu-id="48326-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="48326-136">Однако если потребуется откат в устаревший пул, придется выполнить командлет **Move-CsApplicationEndpoint**, чтобы переместить контактные объекты обратно в устаревший пул.</span><span class="sxs-lookup"><span data-stu-id="48326-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="48326-137">Для миграции конфигураций группы ответа необходимо, чтобы между устаревшими пулами и пулами Skype для бизнеса Server 2019 были установлены связи "один к одному".</span><span class="sxs-lookup"><span data-stu-id="48326-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="48326-138">Если вы планируете консолидировать или разделить пулы во время миграции и развертывания, вам необходимо спланировать, какие карты устаревших пулов будут использовать пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="48326-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="48326-139">Миграция конфигураций групп ответа</span><span class="sxs-lookup"><span data-stu-id="48326-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="48326-140">Войдите в компьютер с учетной записью, которая является членом группы RTCUniversalServerAdmins или имеет эквивалентные права и разрешения администратора.</span><span class="sxs-lookup"><span data-stu-id="48326-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="48326-141">Запустите командную консоль Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, затем **Microsoft Skype для бизнеса Server 2019**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="48326-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="48326-142">Выполняем</span><span class="sxs-lookup"><span data-stu-id="48326-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="48326-143">Пример:</span><span class="sxs-lookup"><span data-stu-id="48326-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="48326-144">После миграции групп ответа и агентов в пул Skype для бизнеса Server 2019 URL-адрес, используемый агентами для входа и выхода, является URL-адресом Skype для бизнеса Server 2019 и доступен в меню " **Сервис** ".</span><span class="sxs-lookup"><span data-stu-id="48326-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="48326-145">Напомните агентам обновить все ссылки, например закладки, с учетом этого нового URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="48326-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="48326-146">Проверка миграции групп ответа с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="48326-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="48326-147">Войдите в компьютер с учетной записью, которая является членом группы RTCUniversalReadOnlyAdmins или как минимум членом роли CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="48326-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="48326-148">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="48326-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="48326-149">Для получения дополнительных сведений о различных способах, которые можно использовать для запуска панели управления Skype для бизнеса Server, обратитесь к разделу [Открытие средства администрирования Skype для бизнеса server 2019](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx).</span><span class="sxs-lookup"><span data-stu-id="48326-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="48326-150">В левой панели навигации выберите пункт **Группы ответа**.</span><span class="sxs-lookup"><span data-stu-id="48326-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="48326-151">На вкладке **Рабочий процесс** убедитесь, что все рабочие процессы из устаревшей среды включены в список.</span><span class="sxs-lookup"><span data-stu-id="48326-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="48326-152">Перейдите на вкладку **очередь** и убедитесь, что все очереди в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="48326-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="48326-153">Перейдите на вкладку **Группа** и убедитесь, что все группы агентов в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="48326-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="48326-154">Проверка миграции групп ответа с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="48326-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="48326-155">Войдите в компьютер с учетной записью, которая является членом группы RTCUniversalReadOnlyAdmins или как минимум членом роли CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="48326-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="48326-156">Запустите командную консоль Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, затем **Microsoft Skype для бизнеса Server 2019**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="48326-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="48326-157">Чтобы получить сведения о следующих командлетах, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="48326-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="48326-158">Выполняем</span><span class="sxs-lookup"><span data-stu-id="48326-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="48326-159">Убедитесь, что все группы агентов в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="48326-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="48326-160">Выполняем</span><span class="sxs-lookup"><span data-stu-id="48326-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="48326-161">Убедитесь, что все очереди в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="48326-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="48326-162">Выполняем</span><span class="sxs-lookup"><span data-stu-id="48326-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="48326-163">Убедитесь, что все рабочие процессы из устаревшей среды включены в список.</span><span class="sxs-lookup"><span data-stu-id="48326-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

