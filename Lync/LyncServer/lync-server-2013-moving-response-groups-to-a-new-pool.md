---
title: 'Lync Server 2013: перемещение групп ответа в новый пул'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6b0af841385bff8b11d46dd24793de5cdcf81da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507106"
---
# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="3d4b2-102">Перемещение групп ответа в новый пул в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d4b2-102">Moving response groups to a new pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d4b2-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3d4b2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3d4b2-104">Lync Server 2013 представляет новую поддержку командлетов для перемещения групп ответа из одного пула в другой, даже если полное доменное имя (FQDN) отличается.</span><span class="sxs-lookup"><span data-stu-id="3d4b2-104">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="3d4b2-105">Выполните действия, описанные в следующей процедуре, чтобы переместить группы ответа из одного пула переднего плана в другой интерфейсный пул с другим полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="3d4b2-105">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3d4b2-106">В среде сосуществования можно перемещать группы ответа только между &nbsp; интерфейсными пулами Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d4b2-106">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="3d4b2-107">Перемещение группы ответа в пул с другими полным доменным именем</span><span class="sxs-lookup"><span data-stu-id="3d4b2-107">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="3d4b2-108">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3d4b2-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3d4b2-p101">Экспортируйте группу ответа в исходном пуле. В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="3d4b2-p101">Export the response groups in the source pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="3d4b2-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="3d4b2-111">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="3d4b2-p102">Чтобы удалить группы ответа из исходного пула во время экспорта, включите в команду параметр –RemoveExportedConfiguration. Пример:</span><span class="sxs-lookup"><span data-stu-id="3d4b2-p102">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter. For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="3d4b2-p103">Импортируйте группы ответа в конечный пул и назначьте конечный пул новому владельцу. В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="3d4b2-p103">Import the response groups to the destination pool and assign the destination pool as the new owner. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="3d4b2-116">Если вы также хотите скопировать параметры уровня приложения группы ответа из исходного пула в целевой пул, включите параметр – Реплацеексистингргссеттингс.</span><span class="sxs-lookup"><span data-stu-id="3d4b2-116">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="3d4b2-117">Для каждого пула можно указать только один набор параметров уровня приложения.</span><span class="sxs-lookup"><span data-stu-id="3d4b2-117">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="3d4b2-118">Если вы копируете параметры уровня приложения из исходного пула в целевой пул, параметры из исходного пула заменяют параметры целевого пула.</span><span class="sxs-lookup"><span data-stu-id="3d4b2-118">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="3d4b2-119">Если вы не копируете параметры из исходного пула, к импортируемым группам ответа применяются существующие параметры из целевого пула.</span><span class="sxs-lookup"><span data-stu-id="3d4b2-119">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="3d4b2-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="3d4b2-120">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3d4b2-121">Параметры уровня приложения включают используемую по умолчанию конфигурацию музыки для хранения музыки, по умолчанию музыкальный файл по умолчанию, период отсрочки агента удерживаемого абонента и конфигурацию контекста вызовов.</span><span class="sxs-lookup"><span data-stu-id="3d4b2-121">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="3d4b2-122">Чтобы просмотреть эти параметры конфигурации, запустите командлет <STRONG>Get – CsRgsConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="3d4b2-122">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="3d4b2-123">Подробнее об этом командлете можно узнать в статье <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get – CsRgsConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="3d4b2-123">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="3d4b2-124">Убедитесь, что импорт выполнен успешно, просмотрев импортированную конфигурацию группы ответа. Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3d4b2-124">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="3d4b2-p106">Убедитесь, что импортированы все рабочие процессы. В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d4b2-p106">Verify that all the workflows were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="3d4b2-p107">Убедитесь, что импортированы все очереди. В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d4b2-p107">Verify that all the queues were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="3d4b2-p108">Убедитесь, что импортированы все группы агентов. В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d4b2-p108">Verify that all the agent groups were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="3d4b2-p109">Убедитесь, что импортированы все часы работы. В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d4b2-p109">Verify that all the hours of business were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="3d4b2-p110">Убедитесь, что импортированы все наборы выходных. В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d4b2-p110">Verify that all the holiday sets were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="3d4b2-135">Убедитесь, что импорт выполнен успешно, позвонив в одну из групп ответа и убедившись, что вызов обрабатывается правильно.</span><span class="sxs-lookup"><span data-stu-id="3d4b2-135">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="3d4b2-136">Попросите агентов, которые являются участниками формальных групп агентов, войти в свои группы в конечном пуле.</span><span class="sxs-lookup"><span data-stu-id="3d4b2-136">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="3d4b2-p111">Если группы ответа не удалялись из исходного пула в ходе процедуры, удалите их из него. В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="3d4b2-p111">If you did not previously remove response groups from the source pool, remove the response groups from the source pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="3d4b2-139">Пример:</span><span class="sxs-lookup"><span data-stu-id="3d4b2-139">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

