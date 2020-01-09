---
title: Перенос групп ответа
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После перемещения пользователей в пулы Skype для бизнеса Server 2019 вы можете выполнять миграцию групп ответа. Миграция групп ответа включает в себя копирование групп агента, очередей, рабочих процессов, звуковых файлов и перемещение контактных данных группы ответа из устаревшего развертывания в пул Skype для бизнеса Server 2019. После миграции устаревших групп ответов звонки в группы ответа обрабатываются приложением группы ответа в пуле 2019 в Skype для бизнеса Server. Вызовы групп ответа больше не обрабатываются пулом устаревших версий.
ms.openlocfilehash: 148fbe2ca547c3bd7e3d240e687b37c94d10270b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991114"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="70df1-106">Перенос групп ответа</span><span class="sxs-lookup"><span data-stu-id="70df1-106">Migrate response groups</span></span>

<span data-ttu-id="70df1-107">После перемещения пользователей в пулы Skype для бизнеса Server 2019 вы можете выполнять миграцию групп ответа.</span><span class="sxs-lookup"><span data-stu-id="70df1-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="70df1-108">Миграция групп ответа включает в себя копирование групп агента, очередей, рабочих процессов, звуковых файлов и перемещение контактных данных группы ответа из устаревшего развертывания в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="70df1-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="70df1-109">После миграции устаревших групп ответов звонки в группы ответа обрабатываются приложением группы ответа в пуле 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="70df1-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="70df1-110">Вызовы групп ответа больше не обрабатываются пулом устаревших версий.</span><span class="sxs-lookup"><span data-stu-id="70df1-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="70df1-111">Несмотря на то, что вы можете перенести группы ответов, прежде чем переносить пользователей в пул Skype для бизнеса Server 2019, рекомендуем сначала переместить всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="70df1-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="70df1-112">В частности, пользователи, которые являются агентами группы ответа, не будут иметь никаких функциональных возможностей новых функций, пока они не будут перемещены в пул 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="70df1-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="70df1-113">Прежде чем приступить к миграции групп ответов, необходимо развернуть пул 2019 в Skype для бизнеса Server, включающий приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="70df1-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="70df1-114">Приложение группы ответа устанавливается и активируется по умолчанию при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="70df1-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="70df1-115">Вы можете убедиться, что приложение группы ответа установлено, запустив командлет **Get-кссервице-аппликатионсервер** .</span><span class="sxs-lookup"><span data-stu-id="70df1-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="70df1-116">Вы можете создать новые группы ответов Skype для бизнеса Server 2019 в пуле Skype для бизнеса Server 2019 перед переносом устаревших групп ответов.</span><span class="sxs-lookup"><span data-stu-id="70df1-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="70df1-117">Для миграции групп ответов из устаревшего пула в Skype для бизнеса Server 2019 вы запускаете командлет **Remove-ксргсконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="70df1-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="70df1-118">Командлет миграции групп ответа перемещает конфигурацию группы ответа для всего пула.</span><span class="sxs-lookup"><span data-stu-id="70df1-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="70df1-119">Вы не можете выбрать определенные группы, очереди или рабочие процессы для миграции.</span><span class="sxs-lookup"><span data-stu-id="70df1-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="70df1-120">После миграции групп ответов на панели управления сервера Skype для бизнеса или с помощью командлетов командной консоли Skype для бизнеса Server вы должны убедиться, что все группы агентов, очереди и рабочие процессы перемещены успешно.</span><span class="sxs-lookup"><span data-stu-id="70df1-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="70df1-121">При миграции групп ответов старые группы ответов не удаляются.</span><span class="sxs-lookup"><span data-stu-id="70df1-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="70df1-122">Когда вы управляете группами ответа после миграции с помощью панели управления Skype для бизнеса Server или консоли управления в Skype для бизнеса Server, вы можете просмотреть как устаревшие группы ответов, так и группы ответов Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="70df1-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="70df1-123">Следует применять обновления только к группам ответов Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="70df1-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="70df1-124">Устаревшие группы ответа сохраняются только для целей отката.</span><span class="sxs-lookup"><span data-stu-id="70df1-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="70df1-125">После завершения миграции и создания новых групп ответов на панели управления сервера Skype для бизнеса и в командной консоли Skype для бизнеса Server будут отображаться устаревшие и версии Skype для бизнеса Server 2019 для каждого ответа. сгруппирован.</span><span class="sxs-lookup"><span data-stu-id="70df1-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="70df1-126">Не используйте панель управления Skype для бизнеса Server или консоль управления Skype для бизнеса Server для удаления устаревших групп ответа.</span><span class="sxs-lookup"><span data-stu-id="70df1-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="70df1-127">Если удалить одну из них, соответствующая группа ответа, созданная в ходе миграции, перестанет работать.</span><span class="sxs-lookup"><span data-stu-id="70df1-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="70df1-128">Устаревшие группы ответов будут удалены при удалении пула старых версий.</span><span class="sxs-lookup"><span data-stu-id="70df1-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="70df1-129">Мы не рекомендуем удалять данные из предыдущего развертывания, пока не будет списано пул.</span><span class="sxs-lookup"><span data-stu-id="70df1-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="70df1-130">Кроме того, настоятельно рекомендуется экспортировать группы ответов сразу после миграции.</span><span class="sxs-lookup"><span data-stu-id="70df1-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="70df1-131">Если вы хотите удалить устаревшую группу ответа, вы можете восстановить группы ответа из резервной копии, чтобы получить группы ответов Skype для бизнеса Server 2019, запущенные на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="70df1-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="70df1-132">В Skype для бизнеса Server 2019 введена новая функция группы ответа с именем " **тип рабочего процесса**".</span><span class="sxs-lookup"><span data-stu-id="70df1-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="70df1-133">**Тип рабочего процесса** может быть **управляемым** или **неуправляемым**.</span><span class="sxs-lookup"><span data-stu-id="70df1-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="70df1-134">Все группы ответа переносятся с **типом рабочего процесса** в **неуправляемый** и с пустым списком руководителей.</span><span class="sxs-lookup"><span data-stu-id="70df1-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="70df1-135">Когда вы запускаете командлет **Move-ксргсконфигуратион** , группы агента, очереди, рабочие процессы и звуковые файлы остаются в пуле старого пула для целей отката.</span><span class="sxs-lookup"><span data-stu-id="70df1-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="70df1-136">Тем не менее, если вам нужно вернуться к устаревшему пулу, необходимо запустить командлет **Move-ксаппликатионендпоинт** , чтобы переместить объекты контакта в пул устаревших.</span><span class="sxs-lookup"><span data-stu-id="70df1-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="70df1-137">Для миграции конфигураций групп ответов предполагается, что у вас есть связь "один-к-одному" между устаревшими пулами и пулами Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="70df1-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="70df1-138">Если вы планируете консолидировать и разбить пулы во время миграции и развертывания, вам нужно будет планировать, какие карты устаревших пулов, в которых вы собираетесь создать: Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="70df1-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="70df1-139">Миграция конфигураций групп ответа</span><span class="sxs-lookup"><span data-stu-id="70df1-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="70df1-140">Войдите в систему с помощью учетной записи, входящей в группу Рткуниверсалсерверадминс, или обладающей эквивалентными правами и разрешениями администратора.</span><span class="sxs-lookup"><span data-stu-id="70df1-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="70df1-141">Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Skype для бизнеса Server 2019**, а затем — **Командная консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="70df1-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="70df1-142">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="70df1-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="70df1-143">Например:</span><span class="sxs-lookup"><span data-stu-id="70df1-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="70df1-144">После того как вы перенесете группы ответов и агенты в пул Skype для бизнеса Server 2019, URL-адрес, используемый агентом для входа и выхода, — это URL Skype для бизнеса Server 2019 и доступен в меню " **Сервис** ".</span><span class="sxs-lookup"><span data-stu-id="70df1-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="70df1-145">Напомни агенту обновить все ссылки, например закладки, на новый URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="70df1-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="70df1-146">Проверка миграции групп ответов с помощью панели управления "Skype для бизнеса Server"</span><span class="sxs-lookup"><span data-stu-id="70df1-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="70df1-147">Войдите в систему с помощью учетной записи, которая является членом группы Рткуниверсалреадонлядминс или является минимум членом роли Ксвиевонлядминистратор.</span><span class="sxs-lookup"><span data-stu-id="70df1-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="70df1-148">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="70df1-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="70df1-149">Дополнительные сведения о различных способах использования панели управления "Skype для бизнеса Server" можно найти в разделе [Открытие средства администрирования Skype для бизнеса server 2019](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span><span class="sxs-lookup"><span data-stu-id="70df1-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="70df1-150">В области навигации слева выберите пункт **группы ответа**.</span><span class="sxs-lookup"><span data-stu-id="70df1-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="70df1-151">На вкладке **Рабочий процесс** убедитесь, что все рабочие процессы в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="70df1-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="70df1-152">Откройте вкладку **очередь** и убедитесь, что все очереди в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="70df1-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="70df1-153">Откройте вкладку **Группа** и убедитесь, что все группы агента в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="70df1-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="70df1-154">Проверка миграции групп ответов с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="70df1-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="70df1-155">Войдите в систему с помощью учетной записи, которая является членом группы Рткуниверсалреадонлядминс или является минимум членом роли Ксвиевонлядминистратор.</span><span class="sxs-lookup"><span data-stu-id="70df1-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="70df1-156">Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Skype для бизнеса Server 2019**, а затем — **Командная консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="70df1-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="70df1-157">Чтобы получить подробные сведения о следующих командлетах, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="70df1-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="70df1-158">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="70df1-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="70df1-159">Убедитесь в том, что все группы агентов в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="70df1-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="70df1-160">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="70df1-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="70df1-161">Убедитесь в том, что все очереди в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="70df1-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="70df1-162">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="70df1-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="70df1-163">Убедитесь в том, что все рабочие процессы в устаревшей среде включены в список.</span><span class="sxs-lookup"><span data-stu-id="70df1-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

