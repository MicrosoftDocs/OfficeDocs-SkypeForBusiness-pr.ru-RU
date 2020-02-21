---
title: Миграция групп ответа
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36b37fc6a67a1935c442edb4e2e8ef0d8812315c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="39ce0-102">Миграция групп ответа</span><span class="sxs-lookup"><span data-stu-id="39ce0-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39ce0-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="39ce0-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="39ce0-104">После перемещения пользователей в пулы Lync Server 2013 вы можете перенести свои группы ответа.</span><span class="sxs-lookup"><span data-stu-id="39ce0-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="39ce0-105">Миграция групп ответа включает копирование групп агентов, очередей, рабочих процессов и звуковых файлов, а также перемещение контактных объектов группы ответа из устаревшего развертывания в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39ce0-105">Migrating response groups includes copying agent groups, queues, workflows, and audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="39ce0-106">После миграции устаревших групп ответа звонки в группы ответа обрабатываются приложением группы ответа в пуле Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39ce0-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="39ce0-107">Вызовы групп ответа больше не будут обрабатываться устаревшим пулом.</span><span class="sxs-lookup"><span data-stu-id="39ce0-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="39ce0-108">Несмотря на то, что вы можете перенести группы ответа, прежде чем переместить всех пользователей в пул Lync Server 2013, рекомендуется сначала переместить всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="39ce0-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="39ce0-109">В частности, у пользователей, которые являются агентами группы ответа, не будут полностью функциональные возможности новых функций, пока они не будут перемещены в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39ce0-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="39ce0-110">Перед миграцией групп ответа необходимо развернуть пул Lync Server 2013, включающий приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="39ce0-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="39ce0-111">Приложение группы ответа устанавливается и активируется по умолчанию при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="39ce0-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="39ce0-112">Вы можете убедиться, что приложение группы ответа установлено, выполнив командлет **Get-CsService – ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="39ce0-112">You can ensure that the Response Group application is installed by running the **Get-CsService–ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="39ce0-113">Вы можете создать новые группы ответа Lync Server 2013 в пуле Lync Server 2013, прежде чем вы перенесете старые группы ответа.</span><span class="sxs-lookup"><span data-stu-id="39ce0-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="39ce0-114">Чтобы перенести группы ответа из устаревшего пула в Lync Server 2013, выполните командлет **Move – CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="39ce0-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="39ce0-115">Прежде чем можно будет выполнить командлет **Move-CsRgsConfiguration**, необходимо установить пакет интерфейсов обратной совместимости инструментария управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="39ce0-115">Before you can run **Move-CsRgsConfiguration**, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package.</span></span> <span data-ttu-id="39ce0-116">Установите это приложение, запустив файл OCSWMIBC.msi.</span><span class="sxs-lookup"><span data-stu-id="39ce0-116">Install this application by running OCSWMIBC.msi.</span></span> <span data-ttu-id="39ce0-117">Файл OCSWMIBC.msi можно найти на установочном носителе в папке Setup.</span><span class="sxs-lookup"><span data-stu-id="39ce0-117">You can find OCSWMIBC.msi on the installation media in the Setup folder.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="39ce0-118">Командлет миграции группы ответа перемещает конфигурацию группы ответа для всего пула.</span><span class="sxs-lookup"><span data-stu-id="39ce0-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="39ce0-119">Нельзя выбрать для миграции конкретные группы, очереди или рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="39ce0-119">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="39ce0-120">После миграции групп ответа необходимо обновить URL-адрес, который используются формальными агентами для входа в группы ответа и выхода из них, а также с помощью командлетов панели управления Lync Server или Командная консоль командной консоли Lync Server для проверки того, что все группы агентов, очереди и рабочие процессы перемещены. удается.</span><span class="sxs-lookup"><span data-stu-id="39ce0-120">After you migrate the response groups, you need to update the URL that formal agents use to sign into and out of their response groups, and use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="39ce0-121">При миграции групп ответа группы ответа Office Communications Server 2007 R2 не удаляются.</span><span class="sxs-lookup"><span data-stu-id="39ce0-121">When you migrate response groups, the Office Communications Server 2007 R2 response groups are not removed.</span></span> <span data-ttu-id="39ce0-122">Не удаляйте группы ответа Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="39ce0-122">Do not remove Office Communications Server 2007 R2 response groups.</span></span> <span data-ttu-id="39ce0-123">При удалении группы ответа Office Communications Server 2007 R2 группы ответа в Lync Server 2013 перестают работать.</span><span class="sxs-lookup"><span data-stu-id="39ce0-123">If you remove an Office Communications Server 2007 R2 response group, the response groups in Lync Server 2013 stop working.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="39ce0-124">Рекомендуется не удалять данные предыдущего развертывания до ликвидации пула.</span><span class="sxs-lookup"><span data-stu-id="39ce0-124">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="39ce0-125">Кроме того, настоятельно рекомендуется экспортировать группы ответов сразу же после миграции.</span><span class="sxs-lookup"><span data-stu-id="39ce0-125">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="39ce0-126">Если вы удаляете группу ответа Office Communications Server 2007 R2, вы можете восстановить группы ответа из резервной копии, чтобы получить группы ответа Lync Server 2013, запущенные повторно.</span><span class="sxs-lookup"><span data-stu-id="39ce0-126">If an Office Communications Server 2007 R2 response group gets removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="39ce0-127">При выполнении командлета **Move-CsRgsConfiguration** группы агентов, очереди, рабочие процессы и звуковые файлы остаются в устаревшем пуле на случай отката.</span><span class="sxs-lookup"><span data-stu-id="39ce0-127">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="39ce0-128">Однако если потребуется откат в устаревший пул, придется выполнить командлет **Move-CsApplicationEndpoint**, чтобы переместить контактные объекты обратно в устаревший пул.</span><span class="sxs-lookup"><span data-stu-id="39ce0-128">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="39ce0-129">Рекомендуется не удалять какие-либо данные групп ответа из устаревшего пула до его ликвидации.</span><span class="sxs-lookup"><span data-stu-id="39ce0-129">We recommend that you don't delete any response group data from the legacy pool until you decommission the pool.</span></span>



</div>

<span data-ttu-id="39ce0-130">В следующей процедуре для миграции конфигураций групп ответа подразумевается, что между устаревшими пулами и пулами Lync Server 2013 существуют отношения "один к одному".</span><span class="sxs-lookup"><span data-stu-id="39ce0-130">The procedure that follows for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="39ce0-131">Если вы планируете консолидировать или разделить пулы во время миграции и развертывания, вам необходимо спланировать сопоставления устаревших пулов с пулом Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39ce0-131">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="39ce0-132">Миграция конфигураций групп ответа</span><span class="sxs-lookup"><span data-stu-id="39ce0-132">To Migrate Response Group Configurations</span></span>

1.  <span data-ttu-id="39ce0-133">Найдите файл OCSWMIBC.msi в папке Setup установочного носителя и установите его.</span><span class="sxs-lookup"><span data-stu-id="39ce0-133">Locate OCSWMIBC.msi in the Setup folder of the installation media and install it.</span></span>

2.  <span data-ttu-id="39ce0-134">Войдите в компьютер с учетной записью, которая является членом группы RTCUniversalServerAdmins или имеет эквивалентные права и разрешения администратора.</span><span class="sxs-lookup"><span data-stu-id="39ce0-134">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

3.  <span data-ttu-id="39ce0-135">Откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="39ce0-135">Open the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="39ce0-136">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="39ce0-136">At the command line, type the following:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="39ce0-137">Пример:</span><span class="sxs-lookup"><span data-stu-id="39ce0-137">For example:</span></span>
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  <span data-ttu-id="39ce0-138">Если вы развернули вкладку Группа ответа для Microsoft Office Communicator 2007 R2 в среде Office Communications Server 2007 R2, удалите эту вкладку из файла вкладок Office Communicator 2007 R2. XML.</span><span class="sxs-lookup"><span data-stu-id="39ce0-138">If you deployed the Response Group tab for Microsoft Office Communicator 2007 R2 in your Office Communications Server 2007 R2 environment, remove the tab from the Office Communicator 2007 R2 tabs.xml file.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39ce0-139">Формальные агенты использовали вкладку "Группа ответа" для входа в свои группы ответа, чтобы можно было получать вызовы.</span><span class="sxs-lookup"><span data-stu-id="39ce0-139">Formal agents used the Response Group tab to sign in to their response groups before they could receive calls.</span></span> <span data-ttu-id="39ce0-140">Если вы развернули вкладку группы ответа, вы выбрали расположение для файла с вкладками Office Communicator 2007 R2 Tab при его развертывании.</span><span class="sxs-lookup"><span data-stu-id="39ce0-140">If you deployed the Response Group tab, you chose the location for the Office Communicator 2007 R2 tabs.xml file when you deployed it.</span></span>

    
    </div>

6.  <span data-ttu-id="39ce0-141">Предоставьте пользователям обновленный URL-адрес, который нужен агентам для входа в свои группы ответа и выхода из них.</span><span class="sxs-lookup"><span data-stu-id="39ce0-141">Provide users with the updated URL that agents need to sign into and out of their response groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39ce0-142">Обычно https://webpoolFQDN/RgsClients/Tab.aspxэто URL-адрес, где вебпулфкдн — полное доменное имя веб-пула, связанного с пулом, который вы только что перешли в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39ce0-142">The URL is typically https://webpoolFQDN/RgsClients/Tab.aspx, where webpoolFQDN is the fully qualified domain name (FQDN) of the web pool that is associated with the pool that you just migrated to Lync Server 2013.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39ce0-143">Этот шаг не требуется после обновления пользователями до Lync 2013, так как URL-адрес доступен в меню " <STRONG>Сервис</STRONG> " в Lync.</span><span class="sxs-lookup"><span data-stu-id="39ce0-143">This step is not required after users upgrade to Lync 2013 because the URL is available from the <STRONG>Tools</STRONG> menu in Lync.</span></span>

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="39ce0-144">Проверка миграции групп ответа с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="39ce0-144">To Verify Response Group Migration by Using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="39ce0-145">Откройте панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="39ce0-145">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="39ce0-146">В левой панели навигации выберите пункт **Группы ответа**.</span><span class="sxs-lookup"><span data-stu-id="39ce0-146">In the left navigation pane, click **Response Groups**.</span></span>

3.  <span data-ttu-id="39ce0-147">На вкладке **Рабочий процесс** убедитесь, что все рабочие процессы в среде Office Communications Server 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="39ce0-147">On the **Workflow** tab, verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="39ce0-148">Перейдите на вкладку **очередь** и убедитесь, что все очереди в среде Office Communications Server 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="39ce0-148">Click the **Queue** tab, and verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

5.  <span data-ttu-id="39ce0-149">Перейдите на вкладку **Группа** и убедитесь, что все группы агентов в среде Office Communications Server 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="39ce0-149">Click the **Group** tab, and verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a><span data-ttu-id="39ce0-150">Чтобы проверить миграцию групп ответа с помощью командлетов</span><span class="sxs-lookup"><span data-stu-id="39ce0-150">To Verify Response Group Migration by Using Cmdlets</span></span>

1.  <span data-ttu-id="39ce0-151">Откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="39ce0-151">Open the Lync Server Management Shell.</span></span>
    
    <span data-ttu-id="39ce0-152">Чтобы получить сведения о следующих командлетах, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="39ce0-152">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

2.  <span data-ttu-id="39ce0-153">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="39ce0-153">At the command line, type the following:</span></span>
    
        Get-CsRgsAgentGroup

3.  <span data-ttu-id="39ce0-154">Убедитесь, что все группы агентов в среде Office Communications Server 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="39ce0-154">Verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="39ce0-155">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="39ce0-155">At the command line, type the following:</span></span>
    
        Get-CsRgsQueue

5.  <span data-ttu-id="39ce0-156">Убедитесь, что все очереди в среде Office Communications Server 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="39ce0-156">Verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

6.  <span data-ttu-id="39ce0-157">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="39ce0-157">At the command line, type the following:</span></span>
    
        Get-CsRgsWorkflow

7.  <span data-ttu-id="39ce0-158">Убедитесь, что все рабочие процессы в среде Office Communications Server 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="39ce0-158">Verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

