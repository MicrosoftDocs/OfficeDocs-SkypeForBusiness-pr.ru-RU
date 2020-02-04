---
title: 'Lync Server 2013: использование команды "остановить" для централизованной службы ведения журнала'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 621d7c02530fea62b1601c1db755292c8f819a6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="4ff4a-102">Использование функции "остановить" для централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ff4a-102">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ff4a-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4ff4a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4ff4a-p101">Остановить текущий работающий сеанс ведения журнала можно с помощью командлета Stop-CsClsLogging. Обычно ситуации, когда нужно остановить сеанс ведения журнала, возникают достаточно редко. Например, поиск в журналах и изменение конфигураций можно выполнять без обязательной предварительной остановки ведения журнала. Если выполняются два сценария, например AlwaysOn и UserReplicator, и нужно собирать сведения, связанные с проверкой подлинности (сценарий Authentication), понадобится остановить один из других сценариев (на глобальном уровне, уровне сайта, пула или компьютера), прежде чем можно будет запустить сценарий Authentication. Подробные сведения см. в статье [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span><span class="sxs-lookup"><span data-stu-id="4ff4a-p101">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet. Generally, there aren’t many situations in which you would need to stop a logging session. For example, you can search logs and change configurations without first needing to stop logging. If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario. For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ff4a-109">При определении сценариев, которые можно выполнять для определенного развертывания, пула или компьютера, необходимо помнить, что вы ограничены выполнение двух сценариев <STRONG>на компьютере</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4ff4a-109">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios <STRONG>per computer</STRONG>.</span></span> <span data-ttu-id="4ff4a-110">If you are logging activity on a pool, you should treat a pool as a single entity.</span><span class="sxs-lookup"><span data-stu-id="4ff4a-110">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="4ff4a-111">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span><span class="sxs-lookup"><span data-stu-id="4ff4a-111">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="4ff4a-112">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span><span class="sxs-lookup"><span data-stu-id="4ff4a-112">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="4ff4a-113">Например, если вы просматриваете сценарий Усеррепликатор, то в процессе выполнения Усеррепликатор на пограничном сервере или пуле Edgeов было бы очень мало значений.</span><span class="sxs-lookup"><span data-stu-id="4ff4a-113">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span><BR><span data-ttu-id="4ff4a-p103">Разобравшись в проблеме и оценив масштаб влияния, следует аккуратно выбрать, какие сценарии будут выполняться и на каких компьютерах и пулах. Хотя сценарий AlwaysOn имеет смысл для широкой области применения, так как он собирает данные для широкого множества поставщиков, определенные сценарии целесообразно применять только на конкретных компьютерах и пулах. Кроме того, следует соблюдать осторожность и не запускать сеанс ведения журнала случайным образом, не разобравшись сначала в эффективности данного сценария в конкретном случае. Использование неправильного сценария или сценария, не соответствующего задаче, либо запуск сценария в неправильной области применения (будь это глобальный уровень, уровень площадки, пула или компьютера), может привести к получению сомнительных и не слишком полезных данных — как если бы никакой сценарий вообще не запускался.</span><span class="sxs-lookup"><span data-stu-id="4ff4a-p103">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools. While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools. Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario. If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>



</div>

<span data-ttu-id="4ff4a-118">Для управления централизованными функциями ведения журналов с помощью командной консоли Lync Server вы должны быть членами либо группами безопасности Ксадминистратор или Кссерверадминистратор, либо настраиваемой роли RBAC, которая включает в себя Любая из этих двух групп.</span><span class="sxs-lookup"><span data-stu-id="4ff4a-118">To control the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="4ff4a-119">Чтобы возвратить список всех ролей RBAC, которым был назначен этот командлет (включая любые пользовательские роли RBAC, созданные пользователем), выполните следующую команду из командной консоли Lync Server Management Shell или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ff4a-119">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="4ff4a-120">Например:</span><span class="sxs-lookup"><span data-stu-id="4ff4a-120">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="4ff4a-121">Чтобы остановить запущенный в данный момент централизованный сеанс службы ведения журнала</span><span class="sxs-lookup"><span data-stu-id="4ff4a-121">To stop a currently running Centralized Logging Service session</span></span>

1.  <span data-ttu-id="4ff4a-122">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4ff4a-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4ff4a-123">Запросите службу централизованного ведения журналов, чтобы узнать, какие сценарии в настоящее время выполняются, введя следующее:</span><span class="sxs-lookup"><span data-stu-id="4ff4a-123">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
        Show-CsClsLogging
    
    <span data-ttu-id="4ff4a-124">![Консоль Windows PowerShell после вызова Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Консоль Windows PowerShell после вызова Show-CsCl")</span><span class="sxs-lookup"><span data-stu-id="4ff4a-124">![Windows PowerShell console after calling Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Windows PowerShell console after calling Show-CsCl")</span></span>
    
    <span data-ttu-id="4ff4a-p105">Результатом выполнения Show-CsClsLogging являются сводные данные обо всех выполняемых сценариях и областях их выполнения. Подробные сведения см. в статье [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span><span class="sxs-lookup"><span data-stu-id="4ff4a-p105">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in. For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span></span>

3.  <span data-ttu-id="4ff4a-127">Чтобы остановить выполняемый в данный момент сеанс ведения журнала, введите:</span><span class="sxs-lookup"><span data-stu-id="4ff4a-127">To stop a currently running logging session with a specific scenario, type:</span></span>
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    <span data-ttu-id="4ff4a-128">Например:</span><span class="sxs-lookup"><span data-stu-id="4ff4a-128">For example:</span></span>
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    <span data-ttu-id="4ff4a-129">Эта команда остановит ведение журнала с помощью сценария UserReplicatior для pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="4ff4a-129">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4ff4a-p106">Журналы, созданные в течение останавливаемого сеанса ведения журнала с помощью сценария UserReplicator, не удаляются. Журналы остаются доступными для выполнения поиска с помощью команды Search-CsClsLogging. Подробные сведения см. в статье <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="4ff4a-p106">Logs created during this logging session using the UserReplicator scenario are not deleted. The logging is still available for you to execute searches against using the Search-CsClsLogging command. For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span></span>

    
    </div>

<span data-ttu-id="4ff4a-p107">Действуя в качестве команды-спутника для Start-CsClsLogging, командлет Stop-CsClsLogging завершает сеанс ведения журнала и сохраняет журналы, созданные в течение этого сеанса. Одновременно на данном компьютере может выполняться не более двух сценариев. Способ остановки одного сценария для сбора данных с помощью другого сценария является типовой задачей, часто выполняемой при устранении неполадок рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="4ff4a-p107">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session. You can run two scenarios on a given computer at any time. The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4ff4a-136">См. также</span><span class="sxs-lookup"><span data-stu-id="4ff4a-136">See Also</span></span>


[<span data-ttu-id="4ff4a-137">Использование команды Start для централизованной службы ведения журналов для захвата журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ff4a-137">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[<span data-ttu-id="4ff4a-138">Общие сведения об централизованной службе ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ff4a-138">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="4ff4a-139">Show-Ксклслоггинг</span><span class="sxs-lookup"><span data-stu-id="4ff4a-139">Show-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[<span data-ttu-id="4ff4a-140">Start-Ксклслоггинг</span><span class="sxs-lookup"><span data-stu-id="4ff4a-140">Start-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[<span data-ttu-id="4ff4a-141">Остановить-Ксклслоггинг</span><span class="sxs-lookup"><span data-stu-id="4ff4a-141">Stop-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

