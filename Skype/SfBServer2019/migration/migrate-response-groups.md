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
description: После переноса пользователей в пулы Skype для бизнеса Server 2019 можно перенести группы ответов. Миграция групп реагирования включает копирование групп агентов, очередей, рабочий процесс, аудиофайлы и перемещение контактных объектов Группы реагирования из устаревшего развертывания в пул Skype для бизнеса Server 2019. После переноса устаревших групп ответов вызовы в группы ответов обрабатываются приложением Группы ответов в пуле Skype для бизнеса Server 2019. Вызовы групп ответа больше не будут обрабатываться устаревшим пулом.
ms.openlocfilehash: bf4087440fb112cb1af906e1a0915531eea08456
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113275"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="65284-106">Перенос групп ответа</span><span class="sxs-lookup"><span data-stu-id="65284-106">Migrate response groups</span></span>

<span data-ttu-id="65284-107">После переноса пользователей в пулы Skype для бизнеса Server 2019 можно перенести группы ответов.</span><span class="sxs-lookup"><span data-stu-id="65284-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="65284-108">Миграция групп реагирования включает копирование групп агентов, очередей, рабочий процесс, аудиофайлы и перемещение контактных объектов Группы реагирования из устаревшего развертывания в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="65284-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="65284-109">После переноса устаревших групп ответов вызовы в группы ответов обрабатываются приложением Группы ответов в пуле Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="65284-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="65284-110">Вызовы групп ответа больше не будут обрабатываться устаревшим пулом.</span><span class="sxs-lookup"><span data-stu-id="65284-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="65284-111">Несмотря на то, что перед перемещением всех пользователей в пул Skype для бизнеса Server 2019 можно перенести группы откликов, рекомендуется сначала переместить всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="65284-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="65284-112">В частности, пользователи, которые являются агентами группы реагирования, не будут иметь полную функциональность новых функций до тех пор, пока они не будут перемещены в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="65284-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="65284-113">Перед переносом групп реагирования необходимо развернуть пул Skype для бизнеса Server 2019, который включает приложение Группы отклика.</span><span class="sxs-lookup"><span data-stu-id="65284-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="65284-114">Приложение Группы реагирования устанавливается и активируется по умолчанию при развертывании Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="65284-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="65284-115">Вы можете убедиться, что приложение Группы реагирования установлено с помощью комлета **Get-CsService-ApplicationServer.**</span><span class="sxs-lookup"><span data-stu-id="65284-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="65284-116">Вы можете создать новые группы реагирования Skype для бизнеса Server 2019 в пуле Skype для бизнеса Server 2019 перед переносом устаревших групп ответа.</span><span class="sxs-lookup"><span data-stu-id="65284-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="65284-117">Чтобы перенести группы ответов из устаревшего пула в Skype для бизнеса Server 2019, вы запустите группу **Move-CsRgsConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="65284-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="65284-118">Комлет группы реагирования перемещает конфигурацию группы реагирования для всего пула.</span><span class="sxs-lookup"><span data-stu-id="65284-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="65284-119">Нельзя выбрать для миграции конкретные группы, очереди или рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="65284-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="65284-120">После переноса групп реагирования необходимо использовать панели управления Skype для бизнес-серверов или команды Skype для управления бизнес-серверами, чтобы убедиться в успешном перемещении всех групп агентов, очередей и рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="65284-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="65284-121">При переносе групп ответов устаревшие группы ответов не удаляются.</span><span class="sxs-lookup"><span data-stu-id="65284-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="65284-122">При управлении группами реагирования после миграции с помощью панели управления Skype для бизнес-серверов или панели управления Skype для бизнес-серверов можно увидеть как устаревшие группы откликов, так и группы реагирования Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="65284-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="65284-123">Обновления следует применять только к группам реагирования Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="65284-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="65284-124">Устаревшие группы ответов сохраняются только для целей отката.</span><span class="sxs-lookup"><span data-stu-id="65284-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="65284-125">После завершения миграции и создания новых групп реагирования панель управления Skype для бизнес-серверов и оболочка управления Skype для бизнес-серверов будут отображать устаревшие версии и версии Skype для бизнеса Server 2019 каждой группы откликов.</span><span class="sxs-lookup"><span data-stu-id="65284-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="65284-126">Не используйте панель управления Skype для бизнес-серверов или оболочку управления бизнес-серверами для удаления устаревших групп реагирования.</span><span class="sxs-lookup"><span data-stu-id="65284-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="65284-127">Если удалить один из них, соответствующая группа откликов, созданная во время миграции, прекратит работу.</span><span class="sxs-lookup"><span data-stu-id="65284-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="65284-128">Устаревшие группы ответов будут удалены при выводе из эксплуатации устаревшего пула.</span><span class="sxs-lookup"><span data-stu-id="65284-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="65284-129">Рекомендуется не удалять данные предыдущего развертывания до ликвидации пула.</span><span class="sxs-lookup"><span data-stu-id="65284-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="65284-130">Кроме того, настоятельно рекомендуется экспортировать группы ответов сразу же после миграции.</span><span class="sxs-lookup"><span data-stu-id="65284-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="65284-131">Если устаревшую группу ответов следует удалить, вы можете восстановить группы ответов из резервного копирования, чтобы группы реагирования Skype для бизнеса Server 2019 снова были запущены.</span><span class="sxs-lookup"><span data-stu-id="65284-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="65284-132">Skype для бизнеса Server 2019 представляет новую функцию Группы ответов под названием **Тип рабочего процесса.**</span><span class="sxs-lookup"><span data-stu-id="65284-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="65284-133">**Тип рабочего процесса** может быть **управляемым** или **неуправляемым**.</span><span class="sxs-lookup"><span data-stu-id="65284-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="65284-134">Все группы ответа переносятся с помощью **неуправляемого\*\*\*\*типа рабочего процесса** и с пустым списком управляющих.</span><span class="sxs-lookup"><span data-stu-id="65284-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="65284-135">При выполнении командлета **Move-CsRgsConfiguration** группы агентов, очереди, рабочие процессы и звуковые файлы остаются в устаревшем пуле на случай отката.</span><span class="sxs-lookup"><span data-stu-id="65284-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="65284-136">Однако если потребуется откат в устаревший пул, придется выполнить командлет **Move-CsApplicationEndpoint**, чтобы переместить контактные объекты обратно в устаревший пул.</span><span class="sxs-lookup"><span data-stu-id="65284-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="65284-137">Следующая процедура переноса конфигураций группы реагирования предполагает, что между устаревшими пулами и пулами Skype для бизнеса Server 2019 имеется отношение один к одному.</span><span class="sxs-lookup"><span data-stu-id="65284-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="65284-138">Если вы планируете консолидировать или разделить пулы во время миграции и развертывания, необходимо спланировать, какие устаревшие карты пула, к которым пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="65284-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="65284-139">Перенос конфигураций группы реагирования</span><span class="sxs-lookup"><span data-stu-id="65284-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="65284-140">Войдите в компьютер с учетной записью, которая является членом группы RTCUniversalServerAdmins или имеет эквивалентные права и разрешения администратора.</span><span class="sxs-lookup"><span data-stu-id="65284-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="65284-141">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Microsoft Skype для бизнеса **Server 2019,** а затем нажмите кнопку Skype для управления бизнес-сервером. </span><span class="sxs-lookup"><span data-stu-id="65284-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="65284-142">Выполните команду: </span><span class="sxs-lookup"><span data-stu-id="65284-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="65284-143">Пример:</span><span class="sxs-lookup"><span data-stu-id="65284-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="65284-144">После переноса групп отклика и агентов в пул Skype для бизнеса Server 2019 URL-адрес, который агенты используют для регистрации и регистрации, является URL-адресом Skype для бизнеса Server 2019 и доступен в меню **Tools.**</span><span class="sxs-lookup"><span data-stu-id="65284-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="65284-145">Напомните агентам обновить все ссылки, например закладки, с учетом этого нового URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="65284-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="65284-146">Проверка миграции группы реагирования с помощью панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="65284-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="65284-147">Войдите в компьютер с учетной записью, которая является членом группы RTCUniversalReadOnlyAdmins или как минимум членом роли CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="65284-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="65284-148">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="65284-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="65284-149">Сведения о различных методах, которые можно использовать для запуска панели управления Skype для бизнес-серверов, см. в материале [Open Skype for Business Server 2019 administrative tools.](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools)</span><span class="sxs-lookup"><span data-stu-id="65284-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="65284-150">В левой панели навигации выберите пункт **Группы ответа**.</span><span class="sxs-lookup"><span data-stu-id="65284-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="65284-151">На **вкладке Workflow** убедитесь, что все процессы в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="65284-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="65284-152">Щелкните **вкладку Queue** и убедитесь, что все очереди в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="65284-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="65284-153">Щелкните **вкладку Group** и убедитесь, что все группы агентов в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="65284-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="65284-154">Проверка миграции группы реагирования с помощью оболочки управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="65284-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="65284-155">Войдите в компьютер с учетной записью, которая является членом группы RTCUniversalReadOnlyAdmins или как минимум членом роли CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="65284-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="65284-156">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Microsoft Skype для бизнеса **Server 2019,** а затем нажмите кнопку Skype для управления бизнес-сервером. </span><span class="sxs-lookup"><span data-stu-id="65284-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="65284-157">Чтобы получить сведения о следующих командлетах, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="65284-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="65284-158">Выполните команду: </span><span class="sxs-lookup"><span data-stu-id="65284-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="65284-159">Убедитесь, что все группы агентов в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="65284-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="65284-160">Выполните команду: </span><span class="sxs-lookup"><span data-stu-id="65284-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="65284-161">Убедитесь, что все очереди в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="65284-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="65284-162">Выполните команду: </span><span class="sxs-lookup"><span data-stu-id="65284-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="65284-163">Убедитесь, что все процессы в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="65284-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
