---
title: Перенос групп ответа
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bf7f0fa04f494eb49a0537011d5f9affcc68065
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="9da84-102">Перенос групп ответа</span><span class="sxs-lookup"><span data-stu-id="9da84-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9da84-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="9da84-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="9da84-104">После перемещения пользователей в пулы Lync Server 2013 вы можете выполнять миграцию групп ответа.</span><span class="sxs-lookup"><span data-stu-id="9da84-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="9da84-105">Миграция групп ответов включает копирование групп агента, очередей, рабочих процессов и звуковых файлов, а также перемещение объектов контактных данных группы ответа из устаревшего развертывания в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9da84-105">Migrating response groups includes copying agent groups, queues, workflows, and audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="9da84-106">После миграции устаревших групп ответов звонки в группы ответа обрабатываются приложением группы ответа в пуле Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9da84-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="9da84-107">Вызовы групп ответа больше не обрабатываются пулом устаревших версий.</span><span class="sxs-lookup"><span data-stu-id="9da84-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9da84-108">Несмотря на то, что вы можете перенести группы ответа перед перемещением всех пользователей в пул Lync Server 2013, рекомендуем сначала переместить всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="9da84-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="9da84-109">В частности, пользователи, которые являются агентами группы ответа, не будут иметь полную функциональность новых функций, пока они не будут перемещены в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9da84-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="9da84-110">Прежде чем приступить к миграции групп ответов, необходимо развернуть пул Lync Server 2013, включающий приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="9da84-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="9da84-111">Приложение группы ответа устанавливается и активируется по умолчанию при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9da84-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="9da84-112">Вы можете убедиться, что приложение группы ответа установлено, выполнив командлет **Get-кссервице – аппликатионсервер** .</span><span class="sxs-lookup"><span data-stu-id="9da84-112">You can ensure that the Response Group application is installed by running the **Get-CsService–ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9da84-113">Вы можете создать новые группы ответов Lync Server 2013 в пуле Lync Server 2013 перед переносом устаревших групп ответов.</span><span class="sxs-lookup"><span data-stu-id="9da84-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="9da84-114">Для миграции групп ответов из устаревшего пула на Lync Server 2013 вы запускаете командлет **Remove-ксргсконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="9da84-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="9da84-115">Прежде чем запускать **Move-ксргсконфигуратион**, необходимо сначала установить пакет интерфейсов WMI для обеспечения обратной совместимости с инструментарием управления Windows.</span><span class="sxs-lookup"><span data-stu-id="9da84-115">Before you can run **Move-CsRgsConfiguration**, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package.</span></span> <span data-ttu-id="9da84-116">Установите это приложение, запустив ОКСВМИБК. msi.</span><span class="sxs-lookup"><span data-stu-id="9da84-116">Install this application by running OCSWMIBC.msi.</span></span> <span data-ttu-id="9da84-117">Вы можете найти ОКСВМИБК. msi на установочном носителе в папке Setup.</span><span class="sxs-lookup"><span data-stu-id="9da84-117">You can find OCSWMIBC.msi on the installation media in the Setup folder.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9da84-118">Командлет миграции групп ответа перемещает конфигурацию группы ответа для всего пула.</span><span class="sxs-lookup"><span data-stu-id="9da84-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="9da84-119">Вы не можете выбрать определенные группы, очереди или рабочие процессы для миграции.</span><span class="sxs-lookup"><span data-stu-id="9da84-119">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="9da84-120">После миграции групп ответов необходимо обновить URL-адрес, который используются формальными агентами для входа в группы ответа и выхода из них, а также с помощью командлетов на панели управления Lync Server или командной консоли Lync Server Management Shell для проверки того, что все группы агентов, очереди и рабочие процессы перемещены. успешность.</span><span class="sxs-lookup"><span data-stu-id="9da84-120">After you migrate the response groups, you need to update the URL that formal agents use to sign into and out of their response groups, and use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="9da84-121">При миграции групп ответов группы ответов Office Communications Server 2007 R2 не удаляются.</span><span class="sxs-lookup"><span data-stu-id="9da84-121">When you migrate response groups, the Office Communications Server 2007 R2 response groups are not removed.</span></span> <span data-ttu-id="9da84-122">Не удаляйте группы ответов Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9da84-122">Do not remove Office Communications Server 2007 R2 response groups.</span></span> <span data-ttu-id="9da84-123">Если вы удалите группу ответов Office Communications Server 2007 R2, группы ответа в Lync Server 2013 перестанут работать.</span><span class="sxs-lookup"><span data-stu-id="9da84-123">If you remove an Office Communications Server 2007 R2 response group, the response groups in Lync Server 2013 stop working.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9da84-124">Мы не рекомендуем удалять данные из предыдущего развертывания, пока не будет списано пул.</span><span class="sxs-lookup"><span data-stu-id="9da84-124">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="9da84-125">Кроме того, настоятельно рекомендуется экспортировать группы ответов сразу после миграции.</span><span class="sxs-lookup"><span data-stu-id="9da84-125">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="9da84-126">Если группа ответов Office Communications Server 2007 R2 удаляется, вы можете восстановить группы ответов из резервной копии, чтобы начать работу групп ответов Lync Server 2013 еще раз.</span><span class="sxs-lookup"><span data-stu-id="9da84-126">If an Office Communications Server 2007 R2 response group gets removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="9da84-127">Когда вы запускаете командлет **Move-ксргсконфигуратион** , группы агента, очереди, рабочие процессы и звуковые файлы остаются в пуле старого пула для целей отката.</span><span class="sxs-lookup"><span data-stu-id="9da84-127">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="9da84-128">Тем не менее, если вам нужно вернуться к устаревшему пулу, необходимо запустить командлет **Move-ксаппликатионендпоинт** , чтобы переместить объекты контакта в пул устаревших.</span><span class="sxs-lookup"><span data-stu-id="9da84-128">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9da84-129">Мы не рекомендуем удалять данные группы ответа из устаревшего пула, пока вы не намерены его списать.</span><span class="sxs-lookup"><span data-stu-id="9da84-129">We recommend that you don't delete any response group data from the legacy pool until you decommission the pool.</span></span>



</div>

<span data-ttu-id="9da84-130">Для миграции конфигураций групп ответов предполагается, что у вас есть связь "один-к-одному" между устаревшими пулами и пулами Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9da84-130">The procedure that follows for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="9da84-131">Если вы планируете консолидировать и разбить пулы во время миграции и развертывания, вам нужно будет планировать, для каких устаревших схем пулов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9da84-131">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="9da84-132">Миграция конфигураций групп ответа</span><span class="sxs-lookup"><span data-stu-id="9da84-132">To Migrate Response Group Configurations</span></span>

1.  <span data-ttu-id="9da84-133">Найдите ОКСВМИБК. msi в папке Setup установочного носителя и установите его.</span><span class="sxs-lookup"><span data-stu-id="9da84-133">Locate OCSWMIBC.msi in the Setup folder of the installation media and install it.</span></span>

2.  <span data-ttu-id="9da84-134">Войдите в систему с помощью учетной записи, входящей в группу Рткуниверсалсерверадминс, или обладающей эквивалентными правами и разрешениями администратора.</span><span class="sxs-lookup"><span data-stu-id="9da84-134">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

3.  <span data-ttu-id="9da84-135">Откройте командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9da84-135">Open the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="9da84-136">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9da84-136">At the command line, type the following:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="9da84-137">Например:</span><span class="sxs-lookup"><span data-stu-id="9da84-137">For example:</span></span>
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  <span data-ttu-id="9da84-138">Если вы развернули вкладку Группа ответа для Microsoft Office Communicator 2007 R2 в среде Office Communications Server 2007 R2, удалите ее из файла вкладок Office Communicator 2007 R2 Tab. XML.</span><span class="sxs-lookup"><span data-stu-id="9da84-138">If you deployed the Response Group tab for Microsoft Office Communicator 2007 R2 in your Office Communications Server 2007 R2 environment, remove the tab from the Office Communicator 2007 R2 tabs.xml file.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9da84-139">Формальные агенты. на вкладке Группа ответа используется для входа в группы ответа, прежде чем они смогут принимать звонки.</span><span class="sxs-lookup"><span data-stu-id="9da84-139">Formal agents used the Response Group tab to sign in to their response groups before they could receive calls.</span></span> <span data-ttu-id="9da84-140">Если вы развернули вкладку группы ответа, вы выбрали расположение для файла закладка Office Communicator 2007 R2 Tab. XML после его развертывания.</span><span class="sxs-lookup"><span data-stu-id="9da84-140">If you deployed the Response Group tab, you chose the location for the Office Communicator 2007 R2 tabs.xml file when you deployed it.</span></span>

    
    </div>

6.  <span data-ttu-id="9da84-141">Предоставьте пользователям обновленный URL-адрес, который агенты должны входить в группы ответа и выйти из них.</span><span class="sxs-lookup"><span data-stu-id="9da84-141">Provide users with the updated URL that agents need to sign into and out of their response groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9da84-142">URL-адрес обычно https://webpoolFQDN/RgsClients/Tab.aspx— это полное доменное имя (FQDN) веб-пула, связанного с пулом, который вы только что перешли в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9da84-142">The URL is typically https://webpoolFQDN/RgsClients/Tab.aspx, where webpoolFQDN is the fully qualified domain name (FQDN) of the web pool that is associated with the pool that you just migrated to Lync Server 2013.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9da84-143">Это действие не требуется после перехода пользователей на Lync 2013, так как URL-адрес доступен в меню " <STRONG>Сервис</STRONG> " в Lync.</span><span class="sxs-lookup"><span data-stu-id="9da84-143">This step is not required after users upgrade to Lync 2013 because the URL is available from the <STRONG>Tools</STRONG> menu in Lync.</span></span>

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="9da84-144">Проверка миграции групп ответов с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="9da84-144">To Verify Response Group Migration by Using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9da84-145">Откройте панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9da84-145">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="9da84-146">В области навигации слева выберите пункт **группы ответа**.</span><span class="sxs-lookup"><span data-stu-id="9da84-146">In the left navigation pane, click **Response Groups**.</span></span>

3.  <span data-ttu-id="9da84-147">На вкладке **Рабочий процесс** убедитесь, что все рабочие процессы в среде Office Communications Server 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="9da84-147">On the **Workflow** tab, verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="9da84-148">Откройте вкладку **очередь** и убедитесь в том, что все очереди в среде Office Communications Server 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="9da84-148">Click the **Queue** tab, and verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

5.  <span data-ttu-id="9da84-149">Откройте вкладку **Группа** и убедитесь, что все группы агентов в среде Office Communications Server 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="9da84-149">Click the **Group** tab, and verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a><span data-ttu-id="9da84-150">Проверка миграции групп ответа с помощью командлетов</span><span class="sxs-lookup"><span data-stu-id="9da84-150">To Verify Response Group Migration by Using Cmdlets</span></span>

1.  <span data-ttu-id="9da84-151">Откройте командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9da84-151">Open the Lync Server Management Shell.</span></span>
    
    <span data-ttu-id="9da84-152">Чтобы получить подробные сведения о следующих командлетах, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9da84-152">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

2.  <span data-ttu-id="9da84-153">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9da84-153">At the command line, type the following:</span></span>
    
        Get-CsRgsAgentGroup

3.  <span data-ttu-id="9da84-154">Убедитесь в том, что все группы агентов в среде Office Communications Server 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="9da84-154">Verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="9da84-155">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9da84-155">At the command line, type the following:</span></span>
    
        Get-CsRgsQueue

5.  <span data-ttu-id="9da84-156">Убедитесь в том, что все очереди в среде Office Communications Server 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="9da84-156">Verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

6.  <span data-ttu-id="9da84-157">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9da84-157">At the command line, type the following:</span></span>
    
        Get-CsRgsWorkflow

7.  <span data-ttu-id="9da84-158">Убедитесь в том, что все рабочие процессы в среде Office Communications Server 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="9da84-158">Verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

