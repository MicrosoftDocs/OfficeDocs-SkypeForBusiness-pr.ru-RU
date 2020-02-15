---
title: Миграция групп ответа
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02d69bcdffdb420d0c79d049f83ab5fa23ddc968
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="36503-102">Миграция групп ответа</span><span class="sxs-lookup"><span data-stu-id="36503-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36503-103">_**Последнее изменение темы:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="36503-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="36503-104">После перемещения пользователей в пулы Lync Server 2013 вы можете перенести свои группы ответа.</span><span class="sxs-lookup"><span data-stu-id="36503-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="36503-105">Миграция групп ответа включает копирование групп агентов, очередей, рабочих процессов, звуковых файлов и перемещение контактных объектов группы ответа из устаревшего развертывания в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36503-105">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="36503-106">После миграции устаревших групп ответа звонки в группы ответа обрабатываются приложением группы ответа в пуле Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36503-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="36503-107">Вызовы групп ответа больше не будут обрабатываться устаревшим пулом.</span><span class="sxs-lookup"><span data-stu-id="36503-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36503-108">Несмотря на то, что вы можете перенести группы ответа, прежде чем переместить всех пользователей в пул Lync Server 2013, рекомендуется сначала переместить всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="36503-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="36503-109">В частности, у пользователей, которые являются агентами группы ответа, не будут полностью функциональные возможности новых функций, пока они не будут перемещены в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36503-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="36503-110">Перед миграцией групп ответа необходимо развернуть пул Lync Server 2013, включающий приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="36503-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="36503-111">Приложение группы ответа устанавливается и активируется по умолчанию при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="36503-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="36503-112">Вы можете убедиться, что приложение группы ответа установлено, выполнив командлет **Get-CsService – ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="36503-112">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36503-113">Вы можете создать новые группы ответа Lync Server 2013 в пуле Lync Server 2013, прежде чем вы перенесете старые группы ответа.</span><span class="sxs-lookup"><span data-stu-id="36503-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="36503-114">Чтобы перенести группы ответа из устаревшего пула в Lync Server 2013, выполните командлет **Move – CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="36503-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="36503-115">Командлет миграции группы ответа перемещает конфигурацию группы ответа для всего пула.</span><span class="sxs-lookup"><span data-stu-id="36503-115">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="36503-116">Нельзя выбрать для миграции конкретные группы, очереди или рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="36503-116">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="36503-117">После миграции групп ответа необходимо использовать командлеты Lync Server Control Panel или командную консоль командной консоли Lync Server, чтобы убедиться, что все группы агентов, очереди и рабочие процессы перемещены успешно.</span><span class="sxs-lookup"><span data-stu-id="36503-117">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="36503-118">При миграции групп ответа группы ответа Lync Server 2010 не удаляются.</span><span class="sxs-lookup"><span data-stu-id="36503-118">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="36503-119">При управлении группами ответа после миграции с помощью панели управления Lync Server или командной консоли Lync Server можно просматривать как группы ответа Lync Server 2010, так и группы ответа Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36503-119">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="36503-120">Обновление следует применять только к группам ответа Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36503-120">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="36503-121">Группы ответа Lync Server 2010 хранятся только в целях отката.</span><span class="sxs-lookup"><span data-stu-id="36503-121">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="36503-122">После завершения миграции и создания новых групп ответа панель управления Lync Server и Командная консоль Lync Server отобразят версии Lync Server 2010 и Lync Server 2013 для каждой группы ответа.</span><span class="sxs-lookup"><span data-stu-id="36503-122">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="36503-123">Не используйте панель управления Lync Server или командную консоль Lync Server, чтобы удалить группы ответа Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="36503-123">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="36503-124">Если удалить один из них, соответствующая ему группа ответа, созданная во время миграции, перестанет работать.</span><span class="sxs-lookup"><span data-stu-id="36503-124">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="36503-125">Группы ответа Lync Server 2010 будут удалены при списании пула Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="36503-125">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="36503-126">Рекомендуется не удалять данные предыдущего развертывания до ликвидации пула.</span><span class="sxs-lookup"><span data-stu-id="36503-126">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="36503-127">Кроме того, настоятельно рекомендуется экспортировать группы ответов сразу же после миграции.</span><span class="sxs-lookup"><span data-stu-id="36503-127">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="36503-128">Если группа ответа Lync Server 2010 должна быть удалена, вы можете восстановить группы ответа из резервной копии, чтобы получить группы ответа Lync Server 2013, запущенные повторно.</span><span class="sxs-lookup"><span data-stu-id="36503-128">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="36503-129">Lync Server 2013 новая функция группы ответа называется **тип рабочего процесса**.</span><span class="sxs-lookup"><span data-stu-id="36503-129">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="36503-130">**Тип рабочего процесса** может быть **управляемым** или **неуправляемым**.</span><span class="sxs-lookup"><span data-stu-id="36503-130">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="36503-131">Все группы ответа переносятся с помощью **неуправляемого\*\*\*\*типа рабочего процесса** и с пустым списком управляющих.</span><span class="sxs-lookup"><span data-stu-id="36503-131">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="36503-132">При выполнении командлета **Move-CsRgsConfiguration** группы агентов, очереди, рабочие процессы и звуковые файлы остаются в устаревшем пуле на случай отката.</span><span class="sxs-lookup"><span data-stu-id="36503-132">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="36503-133">Однако если потребуется откат в устаревший пул, придется выполнить командлет **Move-CsApplicationEndpoint**, чтобы переместить контактные объекты обратно в устаревший пул.</span><span class="sxs-lookup"><span data-stu-id="36503-133">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="36503-134">Для миграции конфигураций группы ответа необходимо, чтобы между устаревшими пулами и пулами Lync Server 2013 были установлены связи "один к одному".</span><span class="sxs-lookup"><span data-stu-id="36503-134">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="36503-135">Если вы планируете консолидировать или разделить пулы во время миграции и развертывания, вам необходимо спланировать сопоставления устаревших пулов с пулом Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36503-135">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="36503-136">Миграция конфигураций групп ответа</span><span class="sxs-lookup"><span data-stu-id="36503-136">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="36503-137">Войдите в компьютер с учетной записью, которая является членом группы RTCUniversalServerAdmins или имеет эквивалентные права и разрешения администратора.</span><span class="sxs-lookup"><span data-stu-id="36503-137">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="36503-138">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="36503-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="36503-139">Выполняем</span><span class="sxs-lookup"><span data-stu-id="36503-139">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="36503-140">Пример:</span><span class="sxs-lookup"><span data-stu-id="36503-140">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="36503-141">После миграции групп ответа и агентов в пул Lync Server 2013 URL-адрес, используемый агентами для входа и выхода, является URL-адресом Lync Server 2013 и доступен в меню " **Сервис** ".</span><span class="sxs-lookup"><span data-stu-id="36503-141">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="36503-142">Напомните агентам обновить все ссылки, например закладки, с учетом этого нового URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="36503-142">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="36503-143">Проверка миграции групп ответа с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="36503-143">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="36503-144">Войдите в компьютер с учетной записью, которая является членом группы RTCUniversalReadOnlyAdmins или как минимум членом роли CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="36503-144">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="36503-145">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="36503-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="36503-146">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="36503-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="36503-147">В левой панели навигации выберите пункт **Группы ответа**.</span><span class="sxs-lookup"><span data-stu-id="36503-147">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="36503-148">На вкладке **Рабочий процесс** убедитесь, что все рабочие процессы в среде Lync Server 2010 включены в список.</span><span class="sxs-lookup"><span data-stu-id="36503-148">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="36503-149">Перейдите на вкладку **очередь** и убедитесь, что все очереди в среде Lync Server 2010 включены в список.</span><span class="sxs-lookup"><span data-stu-id="36503-149">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="36503-150">Перейдите на вкладку **Группа** и убедитесь, что все группы агентов в среде Lync Server 2010 включены в список.</span><span class="sxs-lookup"><span data-stu-id="36503-150">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="36503-151">Проверка миграции групп ответа с помощью командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="36503-151">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="36503-152">Войдите в компьютер с учетной записью, которая является членом группы RTCUniversalReadOnlyAdmins или как минимум членом роли CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="36503-152">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="36503-153">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="36503-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="36503-154">Чтобы получить сведения о следующих командлетах, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="36503-154">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="36503-155">Выполняем</span><span class="sxs-lookup"><span data-stu-id="36503-155">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="36503-156">Убедитесь, что все группы агентов в среде Lync Server 2010 включены в список.</span><span class="sxs-lookup"><span data-stu-id="36503-156">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="36503-157">Выполняем</span><span class="sxs-lookup"><span data-stu-id="36503-157">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="36503-158">Убедитесь, что все очереди в среде Lync Server 2010 включены в список.</span><span class="sxs-lookup"><span data-stu-id="36503-158">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="36503-159">Выполняем</span><span class="sxs-lookup"><span data-stu-id="36503-159">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="36503-160">Убедитесь, что все рабочие процессы в среде Lync Server 2010 включены в список.</span><span class="sxs-lookup"><span data-stu-id="36503-160">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

