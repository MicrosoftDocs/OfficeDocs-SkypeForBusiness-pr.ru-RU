---
title: Перенос групп ответа
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
ms.openlocfilehash: 23ef26b86b1de3fa7f9656cdb2ea82bb7a220948
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="8058c-102">Перенос групп ответа</span><span class="sxs-lookup"><span data-stu-id="8058c-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8058c-103">_**Тема последнего изменения:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="8058c-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="8058c-104">После перемещения пользователей в пулы Lync Server 2013 вы можете выполнять миграцию групп ответа.</span><span class="sxs-lookup"><span data-stu-id="8058c-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="8058c-105">Миграция групп ответа включает в себя копирование групп агента, очередей, рабочих процессов, звуковых файлов и перемещение контактных объектов группы ответа из устаревшего развертывания в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8058c-105">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="8058c-106">После миграции устаревших групп ответов звонки в группы ответа обрабатываются приложением группы ответа в пуле Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8058c-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="8058c-107">Вызовы групп ответа больше не обрабатываются пулом устаревших версий.</span><span class="sxs-lookup"><span data-stu-id="8058c-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8058c-108">Несмотря на то, что вы можете перенести группы ответа перед перемещением всех пользователей в пул Lync Server 2013, рекомендуем сначала переместить всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="8058c-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="8058c-109">В частности, пользователи, которые являются агентами группы ответа, не будут иметь полную функциональность новых функций, пока они не будут перемещены в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8058c-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="8058c-110">Прежде чем приступить к миграции групп ответов, необходимо развернуть пул Lync Server 2013, включающий приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="8058c-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="8058c-111">Приложение группы ответа устанавливается и активируется по умолчанию при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="8058c-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="8058c-112">Вы можете убедиться, что приложение группы ответа установлено, выполнив командлет **Get-кссервице – аппликатионсервер** .</span><span class="sxs-lookup"><span data-stu-id="8058c-112">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8058c-113">Вы можете создать новые группы ответов Lync Server 2013 в пуле Lync Server 2013 перед переносом устаревших групп ответов.</span><span class="sxs-lookup"><span data-stu-id="8058c-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="8058c-114">Для миграции групп ответов из устаревшего пула на Lync Server 2013 вы запускаете командлет **Remove-ксргсконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="8058c-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8058c-115">Командлет миграции групп ответа перемещает конфигурацию группы ответа для всего пула.</span><span class="sxs-lookup"><span data-stu-id="8058c-115">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="8058c-116">Вы не можете выбрать определенные группы, очереди или рабочие процессы для миграции.</span><span class="sxs-lookup"><span data-stu-id="8058c-116">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="8058c-117">После миграции групп ответов на панели управления Lync Server или командлетов командной консоли Lync Server вы должны убедиться, что все группы агентов, очереди и рабочие процессы перемещены успешно.</span><span class="sxs-lookup"><span data-stu-id="8058c-117">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="8058c-118">При миграции групп ответов группы ответа Lync Server 2010 не удаляются.</span><span class="sxs-lookup"><span data-stu-id="8058c-118">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="8058c-119">Когда вы управляете группами ответа после миграции с помощью панели управления Lync Server или консоли управления Lync Server, вы можете видеть как группы ответов Lync Server 2010, так и группы ответа Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8058c-119">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="8058c-120">Следует применять обновления только к группам ответов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8058c-120">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="8058c-121">Группы ответов Lync Server 2010 сохраняются только для целей отката.</span><span class="sxs-lookup"><span data-stu-id="8058c-121">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="8058c-122">После завершения миграции и создания новых групп ответов на панели управления Lync Server и в командной консоли Lync Server выводятся версии сервера Lync Server 2010 и Lync Server 2013 для каждой группы ответа.</span><span class="sxs-lookup"><span data-stu-id="8058c-122">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="8058c-123">Не используйте панель управления Lync Server или консоль управления Lync Server для удаления групп ответа Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8058c-123">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="8058c-124">Если удалить одну из них, соответствующая группа ответа, созданная в ходе миграции, перестанет работать.</span><span class="sxs-lookup"><span data-stu-id="8058c-124">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="8058c-125">Группы ответа Lync Server 2010 удаляются при списании пула Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8058c-125">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8058c-126">Мы не рекомендуем удалять данные из предыдущего развертывания, пока не будет списано пул.</span><span class="sxs-lookup"><span data-stu-id="8058c-126">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="8058c-127">Кроме того, настоятельно рекомендуется экспортировать группы ответов сразу после миграции.</span><span class="sxs-lookup"><span data-stu-id="8058c-127">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="8058c-128">Если группа ответа Lync Server 2010 должна быть удалена, вы можете восстановить группы ответов из резервной копии, чтобы начать работу групп ответов Lync Server 2013 еще раз.</span><span class="sxs-lookup"><span data-stu-id="8058c-128">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="8058c-129">Lync Server 2013 представляет новую функцию группы ответа, называемую **типом рабочего процесса**.</span><span class="sxs-lookup"><span data-stu-id="8058c-129">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="8058c-130">**Тип рабочего процесса** может быть **управляемым** или **неуправляемым**.</span><span class="sxs-lookup"><span data-stu-id="8058c-130">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="8058c-131">Все группы ответа переносятся с **типом рабочего процесса** в **неуправляемый** и с пустым списком руководителей.</span><span class="sxs-lookup"><span data-stu-id="8058c-131">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="8058c-132">Когда вы запускаете командлет **Move-ксргсконфигуратион** , группы агента, очереди, рабочие процессы и звуковые файлы остаются в пуле старого пула для целей отката.</span><span class="sxs-lookup"><span data-stu-id="8058c-132">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="8058c-133">Тем не менее, если вам нужно вернуться к устаревшему пулу, необходимо запустить командлет **Move-ксаппликатионендпоинт** , чтобы переместить объекты контакта в пул устаревших.</span><span class="sxs-lookup"><span data-stu-id="8058c-133">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="8058c-134">Для миграции конфигураций групп ответов предполагается, что у вас есть связь "один-к-одному" между устаревшими пулами и пулами Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8058c-134">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="8058c-135">Если вы планируете консолидировать и разбить пулы во время миграции и развертывания, вам нужно будет планировать, для каких устаревших схем пулов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8058c-135">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="8058c-136">Миграция конфигураций групп ответа</span><span class="sxs-lookup"><span data-stu-id="8058c-136">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="8058c-137">Войдите в систему с помощью учетной записи, входящей в группу Рткуниверсалсерверадминс, или обладающей эквивалентными правами и разрешениями администратора.</span><span class="sxs-lookup"><span data-stu-id="8058c-137">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="8058c-138">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8058c-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8058c-139">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8058c-139">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="8058c-140">Например:</span><span class="sxs-lookup"><span data-stu-id="8058c-140">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="8058c-141">После миграции групп ответов и агентов в пул Lync Server 2013 URL-адрес, используемый агентами для входа и выхода, является URL-адресом Lync Server 2013 и доступен в меню " **Сервис** ".</span><span class="sxs-lookup"><span data-stu-id="8058c-141">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="8058c-142">Напомни агенту обновить все ссылки, например закладки, на новый URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="8058c-142">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="8058c-143">Проверка миграции групп ответов с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="8058c-143">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8058c-144">Войдите в систему с помощью учетной записи, которая является членом группы Рткуниверсалреадонлядминс или является минимум членом роли Ксвиевонлядминистратор.</span><span class="sxs-lookup"><span data-stu-id="8058c-144">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="8058c-145">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8058c-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8058c-146">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8058c-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8058c-147">В области навигации слева выберите пункт **группы ответа**.</span><span class="sxs-lookup"><span data-stu-id="8058c-147">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="8058c-148">На вкладке **Рабочий процесс** убедитесь, что все рабочие процессы в среде Lync Server 2010 включены в список.</span><span class="sxs-lookup"><span data-stu-id="8058c-148">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="8058c-149">Откройте вкладку **очередь** и убедитесь в том, что все очереди в среде Lync Server 2010 включены в список.</span><span class="sxs-lookup"><span data-stu-id="8058c-149">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="8058c-150">Откройте вкладку **Группа** и убедитесь, что все группы агентов в среде Lync Server 2010 включены в список.</span><span class="sxs-lookup"><span data-stu-id="8058c-150">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="8058c-151">Проверка миграции групп ответов с помощью командной консоли Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8058c-151">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="8058c-152">Войдите в систему с помощью учетной записи, которая является членом группы Рткуниверсалреадонлядминс или является минимум членом роли Ксвиевонлядминистратор.</span><span class="sxs-lookup"><span data-stu-id="8058c-152">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="8058c-153">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8058c-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="8058c-154">Чтобы получить подробные сведения о следующих командлетах, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8058c-154">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="8058c-155">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8058c-155">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="8058c-156">Убедитесь в том, что все группы агентов в среде Lync Server 2010 включены в список.</span><span class="sxs-lookup"><span data-stu-id="8058c-156">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="8058c-157">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8058c-157">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="8058c-158">Убедитесь в том, что все очереди в среде Lync Server 2010 включены в список.</span><span class="sxs-lookup"><span data-stu-id="8058c-158">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="8058c-159">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8058c-159">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="8058c-160">Убедитесь в том, что все рабочие процессы в среде Lync Server 2010 включены в список.</span><span class="sxs-lookup"><span data-stu-id="8058c-160">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

