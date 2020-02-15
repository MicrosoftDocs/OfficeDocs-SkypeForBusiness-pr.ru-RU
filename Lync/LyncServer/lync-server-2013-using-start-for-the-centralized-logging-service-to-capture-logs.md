---
title: Использование команды Start для централизованной службы ведения журналов для записи журналов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b32a746f6614ea72e9f0f085a3d3731969cf5f70
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a><span data-ttu-id="b3dbc-102">Использование Start для централизованной службы ведения журналов для захвата журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3dbc-102">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3dbc-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b3dbc-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b3dbc-104">Для записи журналов трассировки с помощью централизованной службы ведения журналов вы можете выполнить команду для начала ведения журнала на одном или нескольких компьютерах и в пулах.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-104">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="b3dbc-105">Кроме того, вы можете указать, какие компьютеры или пулы, какие сценарии следует запустить (например, AlwaysOn, другой предварительно определенный сценарий или созданный сценарий), какие компоненты Lync Server (например, S4, SipStack) будут трассироваться.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-105">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Lync Server components (for example, S4, SipStack) to trace.</span></span>

<span data-ttu-id="b3dbc-106">Для получения правильных сведений нужно гарантировать использование правильного сценария сбора данных, связанного с проблемой.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-106">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="b3dbc-107">В централизованной службе ведения журналов сценарий состоит в том, чтобы включать и отключать ведение журнала на основе коллекции серверных компонентов, уровней ведения журнала и флагов, что является гораздо более эффективным и эффективным, чем определять эти элементы на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-107">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="b3dbc-108">Нужный сценарий определяется для всех серверов и пулов используемой области инфраструктуры и согласованно выполняется на них.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-108">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>

<span data-ttu-id="b3dbc-p103">Сценарий по умолчанию называется **AlwaysOn**. Сценарий AlwaysOn, в соответствии со своим названием, предназначен для постоянного выполнения. Сценарий AlwaysOn собирает данные на уровне Info (обратите внимание, что помимо информационных сообщений при ведении журнала на уровне Info также регистрируются сообщения Fatal (неустранимо), Error (ошибка) и Warning (предупреждение)) для многих из наиболее типичных серверных компонентов. AlwaysOn собирает сведения до, во время и после возникновения проблемы. Это резко отличается от поведения предыдущих средств ведения журнала, таких как OCSLogger. OCSLogger запускается уже после появления проблемы, что затрудняет поиск и устранение неисправностей, так как данные собираются как реакция на событие, а не упреждающе. Если AlwaysOn не содержит данных, нужных для определения проблемного компонента, и не указывает направление действий для исправления проблемы (что, скорее всего, связано с недостаточной шириной и глубиной поставщиков в AlwaysOn), будет указан разумный уровень данных для определения дальнейших действий, таких как создание нового сценария, сбор других данных, выполнение другого поиска для сбора более подробных сведений и т. д.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-p103">The default scenario is called **AlwaysOn**. The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies. The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components. AlwaysOn collects information before, during, and after a problem occurs. This differs dramatically from the typical behavior of previous logging tools such as OCSLogger. You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive. If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>

<span data-ttu-id="b3dbc-116">Централизованная служба ведения журналов предоставляет два способа выполнения команд.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-116">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="b3dbc-117">Несколько разделов посвящены использованию Windows PowerShell с помощью командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-117">A number of topics have been focused squarely on using Windows PowerShell through the Lync Server Management Shell.</span></span> <span data-ttu-id="b3dbc-118">Возможность использования ряда сложных конфигураций и команд обеспечивает Windows PowerShell для централизованного использования службы ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-118">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="b3dbc-119">Так как Windows PowerShell с помощью командной консоли Lync Server является почти общедоступной для всех функций в Lync Server, обсуждаются только команды Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-119">Because Windows PowerShell through the Lync Server Management Shell is nearly ubiquitous for all functions in Lync Server, only the Windows PowerShell commands are discussed.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b3dbc-120">Если вы решили использовать ограниченный набор команд, доступный в командной строке, можно получить справку по CLSController. exe, введя <CODE>ClsController.exe</CODE>команду.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-120">If you decide to use the limited command set available from the command line, you can get help with CLSController.exe by typing <CODE>ClsController.exe</CODE>.</span></span> <span data-ttu-id="b3dbc-121">По умолчанию <STRONG>ClsController. exe</STRONG> устанавливается в каталог C:\Program Files\Microsoft Lync Server 2013 \ ClsAgent.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-121">By default, <STRONG>ClsController.exe</STRONG> is installed in the directory C:\Program Files\Microsoft Lync Server 2013\ClsAgent.</span></span>



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="b3dbc-122">Запуск командлета Start – CsClsLogging с помощью Windows PowerShell с помощью основных команд</span><span class="sxs-lookup"><span data-stu-id="b3dbc-122">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1.  <span data-ttu-id="b3dbc-123">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b3dbc-124">Запустите сценарий ведения журнала с помощью службы централизованного ведения журналов, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b3dbc-124">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    <span data-ttu-id="b3dbc-125">Например, для запуска сценария **AlwaysOn** введите:</span><span class="sxs-lookup"><span data-stu-id="b3dbc-125">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b3dbc-126">У сценария AlwaysOn нет длительности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-126">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="b3dbc-127">Этот сценарий будет выполняться, пока он не будет явно остановлен с помощью командлета <STRONG>Stop-CsClsLogging</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-127">This scenario will run until you explicitly stop it with the <STRONG>Stop-CsClsLogging</STRONG> cmdlet.</span></span> <span data-ttu-id="b3dbc-128">Подробные сведения см. в статье <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-128">For details, see <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span> <span data-ttu-id="b3dbc-129">Для всех остальных сценариев длительность по умолчанию составляет 4 часа.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-129">For all other scenarios, the default duration is 4 hours.</span></span>

    
    </div>

3.  <span data-ttu-id="b3dbc-130">Для выполнения команды нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-130">Press Enter to run the command.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b3dbc-131">Для выполнения команд и возвращения состояния от компьютеров среды может потребоваться некоторое небольшое время (от 30 до 60 секунд).</span><span class="sxs-lookup"><span data-stu-id="b3dbc-131">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span>

    
    </div>
    
    <span data-ttu-id="b3dbc-132">![Запуск команды Start — CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Запуск команды Start — CsClsLogging.")</span><span class="sxs-lookup"><span data-stu-id="b3dbc-132">![Running Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>

4.  <span data-ttu-id="b3dbc-133">Чтобы выполнить другой сценарий, используйте командлет **Start-CsClsLogging** с именем выполняемого дополнительного сценария (например, сценария **Authentication**):</span><span class="sxs-lookup"><span data-stu-id="b3dbc-133">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="b3dbc-134">В любой момент времени на любом конкретном компьютере может работать не более двух сценариев.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-134">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="b3dbc-135">Если область применения команды является глобальной, этот сценарий или сценарии будут выполняться на всех компьютерах среды.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-135">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="b3dbc-136">Для запуска третьего сценария необходимо остановить ведение журнала для области применения (компьютер, пул, сайт, глобальная), в которой нужно запустить новый сценарий.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-136">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="b3dbc-137">Если сценарии запущены в глобальной области применения, можно остановить ведение журнала в одном или обоих сценариях для одного или нескольких компьютеров и пулов.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-137">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> <span data-ttu-id="b3dbc-138">Для получения дополнительных сведений об управлении выполняемыми сценариями обратитесь к разделу <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Использование команды Stop для службы централизованного ведения журналов в Lync Server 2013</A> и <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop – CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-138">For details about managing which scenarios are running, see <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A> and <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="b3dbc-139">Выполнение командлета Start – CsClsLogging с помощью Windows PowerShell с помощью расширенных команд</span><span class="sxs-lookup"><span data-stu-id="b3dbc-139">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1.  <span data-ttu-id="b3dbc-140">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b3dbc-141">Для управления командами ведения журнала доступны дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-141">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="b3dbc-142">Можно использовать параметр –Duration, чтобы задать длительность времени выполнения сценария.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-142">You can use –Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="b3dbc-143">Также можно с помощью параметра –Computers определить разделяемый запятыми список полных доменных имен компьютеров, а с помощью параметра –Pools определить разделяемый запятыми список полных доменных имен пулов, на которых нужно вести журнал.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-143">You also can define –Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or –Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="b3dbc-144">Вы запускаете сеанс ведения журнала для сценария *UserReplicator* в пуле "pool01.contoso.NET".</span><span class="sxs-lookup"><span data-stu-id="b3dbc-144">You start a logging session for the *UserReplicator* scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="b3dbc-145">При этом длительность сеанса ведения журнала определяется равной 8 часам.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-145">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="b3dbc-146">Для этого введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b3dbc-146">To do this, type:</span></span>
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    <span data-ttu-id="b3dbc-147">При успешном выполнении этого сценария возвращается результат, подобный следующему:</span><span class="sxs-lookup"><span data-stu-id="b3dbc-147">The successful execution of this scenario returns a result like the following:</span></span>
    
    <span data-ttu-id="b3dbc-148">![Запуск команды Start — CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Запуск команды Start — CsClsLogging.")</span><span class="sxs-lookup"><span data-stu-id="b3dbc-148">![Running Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>
    
    <span data-ttu-id="b3dbc-149">Обратите внимание, что в этом примере выполняются сценарий AlwaysOn и сценарий UserReplicator.</span><span class="sxs-lookup"><span data-stu-id="b3dbc-149">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b3dbc-150">См. также</span><span class="sxs-lookup"><span data-stu-id="b3dbc-150">See Also</span></span>


[<span data-ttu-id="b3dbc-151">Обзор централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3dbc-151">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

