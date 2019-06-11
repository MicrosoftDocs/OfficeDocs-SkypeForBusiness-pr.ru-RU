---
title: 'Lync Server 2013: перемещение групп ответов в новый пул'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e682ce99826cd5b9f2812c358e1028bfb491ddef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="0d8f0-102">Перемещение групп ответа в новый пул в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d8f0-102">Moving response groups to a new pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d8f0-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0d8f0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0d8f0-104">Lync Server 2013 предлагает новую поддержку командлетов для перемещения групп ответов из одного пула в другой, даже если полное доменное имя (FQDN) отличается.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-104">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="0d8f0-105">Выполните действия, описанные в приведенной ниже процедуре, для перемещения групп ответов из пула переднего плана в другой пул переднего плана с другим полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-105">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0d8f0-106">В среде сосуществования вы можете перемещать группы ответов только между пулами интерфейсов внешних&nbsp;интерфейсов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-106">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="0d8f0-107">Перемещение групп ответа в пул с другим полным доменным именем</span><span class="sxs-lookup"><span data-stu-id="0d8f0-107">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="0d8f0-108">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0d8f0-109">Экспортируйте группы ответов в исходном пуле.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-109">Export the response groups in the source pool.</span></span> <span data-ttu-id="0d8f0-110">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0d8f0-110">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="0d8f0-111">Например:</span><span class="sxs-lookup"><span data-stu-id="0d8f0-111">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="0d8f0-112">Чтобы удалить группы ответов из исходного пула во время экспорта, включите параметр – Ремовикспортедконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-112">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter.</span></span> <span data-ttu-id="0d8f0-113">Например:</span><span class="sxs-lookup"><span data-stu-id="0d8f0-113">For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="0d8f0-114">Импортируйте группы ответа в целевой пул и назначьте пул назначения в качестве нового владельца.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-114">Import the response groups to the destination pool and assign the destination pool as the new owner.</span></span> <span data-ttu-id="0d8f0-115">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0d8f0-115">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="0d8f0-116">Если вы также хотите скопировать параметры уровня приложения группы ответа из исходного пула в конечный пул, добавьте параметр – Реплацеексистингргссеттингс.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-116">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="0d8f0-117">Для каждого пула можно задать на уровне приложения только один набор параметров.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-117">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="0d8f0-118">При копировании параметров уровня приложения из исходного пула в конечный пул параметры из исходного пула заменяют параметры для целевого пула.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-118">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="0d8f0-119">Если вы не копируете параметры уровня приложения из исходного пула, в импортированных группах ответа применяются существующие параметры из целевого пула.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-119">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="0d8f0-120">Например:</span><span class="sxs-lookup"><span data-stu-id="0d8f0-120">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0d8f0-121">Параметры уровня приложения включают стандартную конфигурацию хранения музыки, используемую по умолчанию в качестве звукового файла для хранения музыки, агент рингбакк льготный период и контекстную конфигурацию вызова.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-121">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="0d8f0-122">Чтобы просмотреть эти параметры конфигурации, запустите командлет <STRONG>Get-ксргсконфигуратион</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="0d8f0-122">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="0d8f0-123">Подробнее об этом командлете можно узнать в <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">статьях Get-ксргсконфигуратион</A>.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-123">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="0d8f0-124">Убедитесь, что импорт прошел успешно, отображая импортированную конфигурацию группы ответа следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-124">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="0d8f0-125">Убедитесь, что все рабочие процессы импортированы.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-125">Verify that all the workflows were imported.</span></span> <span data-ttu-id="0d8f0-126">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0d8f0-126">At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="0d8f0-127">Убедитесь, что все очереди импортированы.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-127">Verify that all the queues were imported.</span></span> <span data-ttu-id="0d8f0-128">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0d8f0-128">At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="0d8f0-129">Убедитесь, что все группы агента импортированы.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-129">Verify that all the agent groups were imported.</span></span> <span data-ttu-id="0d8f0-130">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0d8f0-130">At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="0d8f0-131">Убедитесь, что все деловые часы были импортированы.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-131">Verify that all the hours of business were imported.</span></span> <span data-ttu-id="0d8f0-132">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0d8f0-132">At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="0d8f0-133">Убедитесь, что все наборы праздников импортированы.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-133">Verify that all the holiday sets were imported.</span></span> <span data-ttu-id="0d8f0-134">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0d8f0-134">At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="0d8f0-135">Убедитесь, что импорт выполнен успешно, поместив вызов в одну из групп ответа и подтверждаю, что вызов обрабатывается правильно.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-135">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="0d8f0-136">Агенты запросов, являющиеся членами формальных групп агента, для входа в группы агента в целевом пуле.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-136">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="0d8f0-137">Если вы ранее не удалили группы ответов из исходного пула, удалите группы ответов из исходного пула.</span><span class="sxs-lookup"><span data-stu-id="0d8f0-137">If you did not previously remove response groups from the source pool, remove the response groups from the source pool.</span></span> <span data-ttu-id="0d8f0-138">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0d8f0-138">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="0d8f0-139">Например:</span><span class="sxs-lookup"><span data-stu-id="0d8f0-139">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

