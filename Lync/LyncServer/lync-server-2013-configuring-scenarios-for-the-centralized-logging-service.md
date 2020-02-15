---
title: 'Lync Server 2013: Настройка сценариев для централизованной службы ведения журналов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a39bcd23516970edf1c4694a8eff1ecb682eda1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="89a2a-102">Настройка сценариев для централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89a2a-102">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89a2a-103">_**Последнее изменение темы:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="89a2a-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="89a2a-104">В сценариях определяется область (Глобальная, на уровне сайта, в пуле или на компьютере) и какие поставщики используются в централизованной службе ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="89a2a-104">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="89a2a-105">С помощью сценариев вы включаете и отключаете трассировку поставщиков (например, S4, SIPStack, мгновенных сообщений и сведений о присутствии).</span><span class="sxs-lookup"><span data-stu-id="89a2a-105">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="89a2a-106">Настроив сценарий вы можете сгруппировать все поставщики заданной логической коллекции, которые решают определенную проблему.</span><span class="sxs-lookup"><span data-stu-id="89a2a-106">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="89a2a-107">Если вы обнаружите, что сценарий необходимо изменить в соответствии с требованиями к устранению неполадок и ведению журналов, средства отладки Lync Server 2013 предоставляют модуль Windows PowerShell с именем *ClsController. PSM1* , который содержит функцию с именем *Edit — CsClsScenario*.</span><span class="sxs-lookup"><span data-stu-id="89a2a-107">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Lync Server 2013 Debug Tools provides you a Windows PowerShell module named *ClsController.psm1* that contains a function named *Edit-CsClsScenario*.</span></span> <span data-ttu-id="89a2a-108">Предназначение этого модуля — изменение свойств именованного сценария.</span><span class="sxs-lookup"><span data-stu-id="89a2a-108">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="89a2a-109">Примеры работы этого модуля представлены в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="89a2a-109">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="89a2a-110">Средства отладки Lync Server 2013 загружаются по следующей ссылке:[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)</span><span class="sxs-lookup"><span data-stu-id="89a2a-110">The Lync Server 2013 Debug Tools are downloaded from the following link: [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="89a2a-111">Для любой области действия (глобальной, области узла, пула и компьютера) одновременно можно использовать не больше двух сценариев.</span><span class="sxs-lookup"><span data-stu-id="89a2a-111">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="89a2a-112">Чтобы определить, какие сценарии выполняются в данный момент, используйте Windows PowerShell и <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get – CsClsScenario</A>.</span><span class="sxs-lookup"><span data-stu-id="89a2a-112">To determine which scenarios are currently running, use Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>.</span></span> <span data-ttu-id="89a2a-113">С помощью Windows PowerShell и командлета <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set — CsClsScenario</A>можно динамически изменить выполняемые сценарии.</span><span class="sxs-lookup"><span data-stu-id="89a2a-113">By using Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A>, you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="89a2a-114">Это можно сделать во время сеанса ведения журнала, чтобы скорректировать собираемые данные и поставщиков, от которых они собираются.</span><span class="sxs-lookup"><span data-stu-id="89a2a-114">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span>



</div>

<span data-ttu-id="89a2a-115">Для запуска функций централизованной службы ведения журналов с помощью командной консоли Lync Server необходимо быть членом группы безопасности CsAdministrator или CsServerAdministrator с управлением доступом на основе ролей (RBAC) или настраиваемой роли RBAC, содержащей либо из этих двух групп.</span><span class="sxs-lookup"><span data-stu-id="89a2a-115">To run the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="89a2a-116">Чтобы получить список всех ролей RBAC, которым назначен этот командлет, включая любые созданные пользователем роли RBAC, выполните следующую команду в командной консоли Lync Server или в командной строке Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="89a2a-116">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="89a2a-117">Например:</span><span class="sxs-lookup"><span data-stu-id="89a2a-117">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="89a2a-118">Остальная часть этого раздела посвящена определению сценария, изменению сценария, получению сведений о выполняемых сценариях, удалению сценария указанию содержимого сценария для оптимизации устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="89a2a-118">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="89a2a-119">Существует два способа выдача команд службы централизованного ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="89a2a-119">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="89a2a-120">Вы можете\\использовать файл CLSController. exe, расположенный по умолчанию, в папке C: Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="89a2a-120">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="89a2a-121">Вы также можете использовать командную консоль Lync Server для выполнения команд Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89a2a-121">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="89a2a-122">Важное отличие состоит в том, что при использовании CLSController.exe в командой строке выбор доступных сценариев ограничен.</span><span class="sxs-lookup"><span data-stu-id="89a2a-122">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available.</span></span> <span data-ttu-id="89a2a-123">При использовании Windows PowerShell можно определять новые сценарии для использования в сеансах ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="89a2a-123">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>

<span data-ttu-id="89a2a-124">Как показано в статье [Обзор централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), элементы сценария:</span><span class="sxs-lookup"><span data-stu-id="89a2a-124">As introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the elements of a scenario are:</span></span>

  - <span data-ttu-id="89a2a-125">**Поставщики**   . Если вы знакомы с OCSLogger, поставщики — это компоненты, которые указывают OCSLogger, из чего система трассировки должна собирать журналы.</span><span class="sxs-lookup"><span data-stu-id="89a2a-125">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="89a2a-126">Поставщики — это те же компоненты, а во многих случаях их имя совпадает с компонентами в OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="89a2a-126">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="89a2a-127">Если вы не знакомы с OCSLogger, поставщики — это компоненты, зависящие от роли сервера, из которых Служба централизованного ведения журналов может собирать журналы.</span><span class="sxs-lookup"><span data-stu-id="89a2a-127">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="89a2a-128">Подробные сведения о конфигурации поставщиков приведены [в статье Настройка поставщиков для централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span><span class="sxs-lookup"><span data-stu-id="89a2a-128">For details about the configuration of providers, see [Configuring providers for Centralized Logging Service in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span></span>

  - <span data-ttu-id="89a2a-129">**Identity**   параметр — Identity задает область и имя сценария.</span><span class="sxs-lookup"><span data-stu-id="89a2a-129">**Identity**   The parameter –Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="89a2a-130">Например, вы можете задать глобальную область ("global") и задать для сценария идентификатор "LyssServiceScenario".</span><span class="sxs-lookup"><span data-stu-id="89a2a-130">For example, you could set a scope of “global” and identify the scenario with “LyssServiceScenario”.</span></span> <span data-ttu-id="89a2a-131">Если объединить эти два параметра, вы полните параметр Identity (например, "global/LyssServiceScenario").</span><span class="sxs-lookup"><span data-stu-id="89a2a-131">When you combine the two, you define the Identity (for example, “global/LyssServiceScenario”).</span></span>
    
    <span data-ttu-id="89a2a-p107">При необходимости можно использовать параметры –Name и –Parent. Параметр Name задается для уникальной идентификации сценария. Если используется параметр Name, необходимо также использовать параметр Parent, чтобы добавить сценарий в глобальную область или область узла.</span><span class="sxs-lookup"><span data-stu-id="89a2a-p107">Optionally, you can use the –Name and –Parent parameters. You define the Name parameter to uniquely identify the scenario. If you use Name, you must also use Parent to add the scenario to either global or site.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="89a2a-135">Если используются параметры Name и Parent, вы не можете применять параметр <STRONG>–Identity</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="89a2a-135">If you use the Name and Parent parameters, you cannot use the <STRONG>–Identity</STRONG> parameter.</span></span>

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="89a2a-136">Создание сценария с помощью командлета New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="89a2a-136">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="89a2a-137">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="89a2a-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="89a2a-138">Чтобы создать новый сценарий для сеанса ведения журнала, используйте [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) и определите имя сценария (то есть, как он будет однозначно идентифицирован).</span><span class="sxs-lookup"><span data-stu-id="89a2a-138">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="89a2a-139">Выберите тип формата ведения журнала из WPP (то есть препроцессор трассировки программного обеспечения Windows и значение по умолчанию), EventLog (то есть формат журнала событий Windows) или Иислог (то есть файл в формате ASCII, основанный на формате файла журнала IIS).</span><span class="sxs-lookup"><span data-stu-id="89a2a-139">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="89a2a-140">Затем определите уровень (как определено в разделе уровни ведения журнала в данном разделе) и флаги (как указано в разделе flags в этом разделе).</span><span class="sxs-lookup"><span data-stu-id="89a2a-140">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="89a2a-141">Для этого примера сценария мы используем LyssProvider как пример переменной поставщика.</span><span class="sxs-lookup"><span data-stu-id="89a2a-141">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="89a2a-142">Чтобы создать сценарий с помощью заданных параметров, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="89a2a-142">To create a scenario using the options defined, type:</span></span>
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    <span data-ttu-id="89a2a-143">Пример:</span><span class="sxs-lookup"><span data-stu-id="89a2a-143">For example:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    <span data-ttu-id="89a2a-144">Альтернативный формат с использованием –Name и –Parent:</span><span class="sxs-lookup"><span data-stu-id="89a2a-144">The alternate format using –Name and –Parent:</span></span>
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="89a2a-145">Создание сценария с несколькими поставщиками с помощью командлета New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="89a2a-145">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="89a2a-146">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="89a2a-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="89a2a-147">Можно использовать не больше двух сценариев для области действия.</span><span class="sxs-lookup"><span data-stu-id="89a2a-147">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="89a2a-148">Однако число поставщиков не ограничено.</span><span class="sxs-lookup"><span data-stu-id="89a2a-148">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="89a2a-149">В этом примере предположим, что мы создали три поставщика и хотим назначить все три из них определяемому вами сценарию.</span><span class="sxs-lookup"><span data-stu-id="89a2a-149">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="89a2a-150">Имена переменных поставщиков: LyssProvider, ABServerProvider и SIPStackProvider.</span><span class="sxs-lookup"><span data-stu-id="89a2a-150">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="89a2a-151">Чтобы определить и назначить несколько поставщиков сценарию, введите следующую команду в командной консоли Lync Server или в командной строке Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="89a2a-151">To define and assign multiple providers to a scenario, type the following at a Lync Server Management Shell or Windows PowerShell command prompt:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="89a2a-152">Так как она известна в Windows PowerShell, соглашение о создании хэш-таблицы значений с помощью <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> называется <EM>сплаттингом</EM>.</span><span class="sxs-lookup"><span data-stu-id="89a2a-152">As it is known in Windows PowerShell, the convention for creating a hash table of values using <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> is known as <EM>splatting</EM>.</span></span> <span data-ttu-id="89a2a-153">Подробнее о сплаттингом в Windows PowerShell можно узнать <A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>в статье.</span><span class="sxs-lookup"><span data-stu-id="89a2a-153">For details about splatting in Windows PowerShell, see <A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="89a2a-154">Изменение существующего сценария с помощью командлета Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="89a2a-154">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="89a2a-155">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="89a2a-155">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="89a2a-p111">Можно использовать не больше двух сценариев для области действия. Вы можете изменить выполняемые сценарии в любое время даже во время сеанса ведения журналов. Если переопределить выполняемые сценарии, текущий сеанс перестанет использовать удаленный сценарий и начнет применять новый сценарий. Однако данные ведения журналов, полученные с помощью удаленного сценария, останутся в полученных журналах. Чтобы определить новый сценарий, выполните следующие действия (если уже определенный поставщик "S4Provider" уже добавлен):</span><span class="sxs-lookup"><span data-stu-id="89a2a-p111">You are limited to two scenarios per scope. You can change which scenarios are running at any time, even when a logging capture session is in process. If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario. However, the logging information that was captured with the removed scenario remains in the captured logs. To define a new scenario, do the following (that is, assuming the addition of an already defined provider named “S4Provider”):</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    <span data-ttu-id="89a2a-161">Например:</span><span class="sxs-lookup"><span data-stu-id="89a2a-161">For example:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    <span data-ttu-id="89a2a-p112">Если вы хотите заменить поставщики, определить один поставщика или разделенный запятыми список поставщиков, чтобы заменить текущий набор. Если вы хотите только заменить один из нескольких поставщиков, добавьте текущие поставщики с новыми поставщиками, чтобы создать новый набор поставщиков, который содержит новые и существующие поставщики. Чтобы заменить все поставщики новым набором, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="89a2a-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    <span data-ttu-id="89a2a-165">Например, чтобы заменить текущий набор из $LyssProvider, $ABServerProvider и $SIPStackProvider на $LyssServiceProvider, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="89a2a-165">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    <span data-ttu-id="89a2a-166">Чтобы заменить только поставщик $LyssProvider из текущего набора $LyssProvider, $ABServerProvider и $SIPStackProvider на $LyssServiceProvider, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="89a2a-166">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="89a2a-167">Удаление существующего сценария с помощью командлета Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="89a2a-167">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="89a2a-168">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="89a2a-168">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="89a2a-169">Если вы хотите удалить сценарий, определенный ранее, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="89a2a-169">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    <span data-ttu-id="89a2a-170">Например, чтобы удалить заданный сценарий site:Redmond/LyssServiceScenario:</span><span class="sxs-lookup"><span data-stu-id="89a2a-170">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

<span data-ttu-id="89a2a-171">Командлет **Remove-CsClsScenario** удаляет указанный сценарий, но полученные трассировки все еще доступны в журналах.</span><span class="sxs-lookup"><span data-stu-id="89a2a-171">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a><span data-ttu-id="89a2a-172">Загрузка и выгрузка командлета Edit-CsClsScenario с помощью модуля ClsController.psm1</span><span class="sxs-lookup"><span data-stu-id="89a2a-172">To load and unload the Edit-CsClsScenario cmdlet using the ClsController.psm1 module</span></span>

1.  <span data-ttu-id="89a2a-173">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="89a2a-173">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="89a2a-174">Модуль ClsController.psm1 предоставляется как отдельная веб-загрузка.</span><span class="sxs-lookup"><span data-stu-id="89a2a-174">The ClsController.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="89a2a-175">Модуль входит в состав средств отладки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89a2a-175">The module is part of the Lync Server 2013 Debugging tools.</span></span> <span data-ttu-id="89a2a-176">По умолчанию средства отладки устанавливаются в каталог C:\Program Files\Lync Server 2013\Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="89a2a-176">By default, the debugging tools are installed in the directory C:\Program Files\Lync Server 2013\Debugging Tools.</span></span>

    
    </div>

2.  <span data-ttu-id="89a2a-177">В Windows PowerShell введите:</span><span class="sxs-lookup"><span data-stu-id="89a2a-177">From the Windows PowerShell, type:</span></span>
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="89a2a-178">При успешной загрузке модуля вы вернетесь в командную строку Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89a2a-178">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="89a2a-179">Чтобы убедиться, что модуль загружен и доступен параметр Edit-CsClsScenario, введите <CODE>Get-Help Edit-CsClsScenario</CODE>.</span><span class="sxs-lookup"><span data-stu-id="89a2a-179">To confirm that the module is loaded and that Edit-CsClsScenario is available, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="89a2a-180">Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="89a2a-180">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span>

    
    </div>

3.  <span data-ttu-id="89a2a-181">Чтобы выгрузить модули, введите:</span><span class="sxs-lookup"><span data-stu-id="89a2a-181">To unload the modules, type:</span></span>
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="89a2a-182">При успешной выгрузке модуля вы вернетесь в командную строку Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89a2a-182">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="89a2a-183">Чтобы убедиться, что модуль выгружается, введите <CODE>Get-Help Edit-CsClsScenario</CODE>.</span><span class="sxs-lookup"><span data-stu-id="89a2a-183">To confirm that the module is unloaded, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="89a2a-184">Windows PowerShell будет пытаться определить расположение справки для командлета и выполнить ошибку.</span><span class="sxs-lookup"><span data-stu-id="89a2a-184">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="89a2a-185">Удаление существующего поставщика из сценария с помощью командлета Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="89a2a-185">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="89a2a-186">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="89a2a-186">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="89a2a-187">Чтобы удалить поставщика из сценария AlwaysOn, введите:</span><span class="sxs-lookup"><span data-stu-id="89a2a-187">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    <span data-ttu-id="89a2a-188">Например:</span><span class="sxs-lookup"><span data-stu-id="89a2a-188">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    <span data-ttu-id="89a2a-p116">Параметры ScenarioName и ProviderName являются позиционными (т. е. их необходимо задать в ожидаемой позиции в командной строке). Имя параметра необязательно явно определять, если имя сценария находится во второй позиции, а поставщик — в третьей позиции относительно первой позиции имени командлета. Используя эту информацию, предыдущая команда вводится следующим образом:</span><span class="sxs-lookup"><span data-stu-id="89a2a-p116">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    <span data-ttu-id="89a2a-p117">Позиционное размещение значений параметров применяется только к параметрам –Scenario и –Provider. Все другие параметры нужно определить явно.</span><span class="sxs-lookup"><span data-stu-id="89a2a-p117">The positional placing of the parameter values applies only to –Scenario and –Provider. All other parameters must be explicitly defined.</span></span>

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="89a2a-194">Добавление поставщика в сценарий с помощью командлета Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="89a2a-194">To add a provider to a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="89a2a-195">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="89a2a-195">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="89a2a-196">Чтобы добавить поставщик в сценарий AlwaysOn, введите:</span><span class="sxs-lookup"><span data-stu-id="89a2a-196">To add a provider to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    <span data-ttu-id="89a2a-197">Например:</span><span class="sxs-lookup"><span data-stu-id="89a2a-197">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    <span data-ttu-id="89a2a-198">\-LogLevel может иметь тип Неустранимая ошибка, ошибка, предупреждение, info, Verbose, Debug или ALL.</span><span class="sxs-lookup"><span data-stu-id="89a2a-198">\-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="89a2a-199">— Flags могут быть любыми флагами, которые поддерживает поставщик, например TF\_Component, TF\_DIAG.</span><span class="sxs-lookup"><span data-stu-id="89a2a-199">–Flags can be any of the flags that the provider supports, such as TF\_COMPONENT, TF\_DIAG.</span></span> <span data-ttu-id="89a2a-200">Для параметра –Flags также можно указать значение ALL</span><span class="sxs-lookup"><span data-stu-id="89a2a-200">–Flags can also be of value ALL</span></span>
    
    <span data-ttu-id="89a2a-p119">Предыдущий пример также можно ввести, используя позиционность командлета. Например, чтобы добавить поставщик ChatServer в сценарий AlwaysOn, введите:</span><span class="sxs-lookup"><span data-stu-id="89a2a-p119">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

