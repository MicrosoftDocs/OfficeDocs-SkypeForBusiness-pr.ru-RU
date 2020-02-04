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
ms.openlocfilehash: cd3933ff81fad6947fcc4ab1ff7a7dc9ad136c39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="d0444-102">Настройка сценариев для централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0444-102">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0444-103">_**Тема последнего изменения:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="d0444-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="d0444-104">Сценарии определяют область (глобальные, сайты, пулы или компьютеры) и поставщиков услуг, которые используются в централизованной службе ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="d0444-104">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="d0444-105">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span><span class="sxs-lookup"><span data-stu-id="d0444-105">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="d0444-106">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span><span class="sxs-lookup"><span data-stu-id="d0444-106">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="d0444-107">Если вы обнаружите, что сценарий необходимо изменить в соответствии с требованиями для устранения неполадок и ведения журнала, в средствах отладки Lync Server 2013 есть модуль Windows PowerShell с именем *клсконтроллер. PSM1* , который содержит функцию с именем *Edit-ксклссценарио*.</span><span class="sxs-lookup"><span data-stu-id="d0444-107">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Lync Server 2013 Debug Tools provides you a Windows PowerShell module named *ClsController.psm1* that contains a function named *Edit-CsClsScenario*.</span></span> <span data-ttu-id="d0444-108">The purpose of the module is to edit the properties of the named scenario.</span><span class="sxs-lookup"><span data-stu-id="d0444-108">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="d0444-109">Examples of how this module works are provided in this topic.</span><span class="sxs-lookup"><span data-stu-id="d0444-109">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="d0444-110">Средства отладки Lync Server 2013 загружаются по следующей ссылке:[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)</span><span class="sxs-lookup"><span data-stu-id="d0444-110">The Lync Server 2013 Debug Tools are downloaded from the following link: [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d0444-111">Для любой области действия (глобальной, области узла, пула и компьютера) одновременно можно использовать не больше двух сценариев.</span><span class="sxs-lookup"><span data-stu-id="d0444-111">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="d0444-112">Чтобы определить, какие сценарии выполняются в настоящее время, используйте Windows PowerShell и <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-ксклссценарио</A>.</span><span class="sxs-lookup"><span data-stu-id="d0444-112">To determine which scenarios are currently running, use Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>.</span></span> <span data-ttu-id="d0444-113">Используя Windows PowerShell и <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-ксклссценарио</A>, вы можете динамически менять, какие сценарии запущены.</span><span class="sxs-lookup"><span data-stu-id="d0444-113">By using Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A>, you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="d0444-114">Это можно сделать во время сеанса ведения журнала, чтобы скорректировать собираемые данные и поставщиков, от которых они собираются.</span><span class="sxs-lookup"><span data-stu-id="d0444-114">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span>



</div>

<span data-ttu-id="d0444-115">Для запуска функций централизованной службы ведения журналов с помощью командной консоли Lync Server вы должны быть членом группы безопасности Ксадминистратор или Кссерверадминистратор (или настраиваемой роли RBAC), содержащей либо из этих двух групп.</span><span class="sxs-lookup"><span data-stu-id="d0444-115">To run the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="d0444-116">Чтобы возвратить список всех ролей RBAC, которым назначен этот командлет, включая любые пользовательские роли RBAC, созданные пользователем, выполните следующую команду из командной консоли Lync Server Management Shell или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0444-116">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="d0444-117">Например:</span><span class="sxs-lookup"><span data-stu-id="d0444-117">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="d0444-118">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span><span class="sxs-lookup"><span data-stu-id="d0444-118">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="d0444-119">Существует два способа вывести централизованные команды службы ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="d0444-119">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="d0444-120">\\По умолчанию вы можете использовать файл клсконтроллер. exe, который находится в папке C: Program Files\\, которые представляют\\собой общие файлы Microsoft\\Lync Server 2013 клсажент.</span><span class="sxs-lookup"><span data-stu-id="d0444-120">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="d0444-121">Кроме того, вы можете использовать командную консоль Lync Server для выдаче команды Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0444-121">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="d0444-122">Важное отличие заключается в том, что при использовании Клсконтроллер. exe в командной строке имеется ограниченный выбор доступных сценариев.</span><span class="sxs-lookup"><span data-stu-id="d0444-122">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available.</span></span> <span data-ttu-id="d0444-123">Если вы используете Windows PowerShell, вы можете определить новые сценарии для использования в сеансах ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="d0444-123">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>

<span data-ttu-id="d0444-124">Как было представлено в [обзоре централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), элементы сценария описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="d0444-124">As introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the elements of a scenario are:</span></span>

  - <span data-ttu-id="d0444-125">**Поставщики**   если вы знакомы с окслогжер, поставщики — это компоненты, которые вы указываете, чтобы сообщить окслогжер о том, что механизм трассировки должен собирать журналы.</span><span class="sxs-lookup"><span data-stu-id="d0444-125">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="d0444-126">Поставщики — это те же компоненты, а во многих случаях их имя совпадает с компонентами в OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="d0444-126">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="d0444-127">Если вы не знакомы с Окслогжер, поставщики являются компонентами, специфичными для серверной роли, из которой Служба централизованного ведения журналов может собирать журналы.</span><span class="sxs-lookup"><span data-stu-id="d0444-127">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="d0444-128">Подробнее о настройке поставщиков вы узнаете в разделе [Настройка служб централизованного ведения журналов в Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span><span class="sxs-lookup"><span data-stu-id="d0444-128">For details about the configuration of providers, see [Configuring providers for Centralized Logging Service in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span></span>

  - <span data-ttu-id="d0444-129">**Identity**   параметр — Identity задает область и имя сценария.</span><span class="sxs-lookup"><span data-stu-id="d0444-129">**Identity**   The parameter –Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="d0444-130">Например, вы можете задать глобальную область ("global") и задать для сценария идентификатор "LyssServiceScenario".</span><span class="sxs-lookup"><span data-stu-id="d0444-130">For example, you could set a scope of “global” and identify the scenario with “LyssServiceScenario”.</span></span> <span data-ttu-id="d0444-131">Если объединить эти два параметра, выполните параметр Identity (например, "global/LyssServiceScenario").</span><span class="sxs-lookup"><span data-stu-id="d0444-131">When you combine the two, you define the Identity (for example, “global/LyssServiceScenario”).</span></span>
    
    <span data-ttu-id="d0444-p107">При необходимости можно использовать параметры –Name и –Parent. Параметр Name задается для уникальной идентификации сценария. Если используется параметр Name, необходимо также использовать параметр Parent, чтобы добавить сценарий в глобальную область или область узла.</span><span class="sxs-lookup"><span data-stu-id="d0444-p107">Optionally, you can use the –Name and –Parent parameters. You define the Name parameter to uniquely identify the scenario. If you use Name, you must also use Parent to add the scenario to either global or site.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d0444-135">Если используются параметры Name и Parent, вы не можете применять параметр <STRONG>–Identity</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d0444-135">If you use the Name and Parent parameters, you cannot use the <STRONG>–Identity</STRONG> parameter.</span></span>

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="d0444-136">Создание сценария с помощью командлета New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="d0444-136">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="d0444-137">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d0444-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d0444-p108">Чтобы создать сценарий для сеанса ведения журналов, используйте [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) и задайте имя сценария (т. е. его уникальный идентификатор). Выберите тип формата ведения журнала в WPP (т. е. препроцессор трассировки ПО Windows, значение по умолчанию), EventLog (т. е. формат журнала событий Windows) или IISLog (т. е. формат ASCII на основе формата IIS). Затем задайте уровень (как указано в подразделе "Уровни ведения журнала" в этом разделе) и флаги (см. "Флаги" в этом разделе).</span><span class="sxs-lookup"><span data-stu-id="d0444-p108">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) and define the name of the scenario (that is, how it will be uniquely identified). Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format). Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="d0444-141">Для этого примера сценария мы используем LyssProvider как пример переменной поставщика.</span><span class="sxs-lookup"><span data-stu-id="d0444-141">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="d0444-142">Чтобы создать сценарий с помощью заданных параметров, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d0444-142">To create a scenario using the options defined, type:</span></span>
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    <span data-ttu-id="d0444-143">Например:</span><span class="sxs-lookup"><span data-stu-id="d0444-143">For example:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    <span data-ttu-id="d0444-144">Альтернативный формат с использованием –Name и –Parent:</span><span class="sxs-lookup"><span data-stu-id="d0444-144">The alternate format using –Name and –Parent:</span></span>
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="d0444-145">Создание сценария с несколькими поставщиками с помощью командлета New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="d0444-145">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="d0444-146">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d0444-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d0444-147">You are limited to two scenarios per scope.</span><span class="sxs-lookup"><span data-stu-id="d0444-147">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="d0444-148">However, you are not limited to a set number of providers.</span><span class="sxs-lookup"><span data-stu-id="d0444-148">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="d0444-149">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span><span class="sxs-lookup"><span data-stu-id="d0444-149">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="d0444-150">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span><span class="sxs-lookup"><span data-stu-id="d0444-150">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="d0444-151">Чтобы определить сценарий и назначить ему несколько поставщиков, введите следующую команду в командной консоли Lync Server Management Shell или в командную строке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0444-151">To define and assign multiple providers to a scenario, type the following at a Lync Server Management Shell or Windows PowerShell command prompt:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0444-152">Так как она известна в Windows PowerShell, правило создания хэш-таблицы значений <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> называется <EM>Сплаттинг</EM>.</span><span class="sxs-lookup"><span data-stu-id="d0444-152">As it is known in Windows PowerShell, the convention for creating a hash table of values using <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> is known as <EM>splatting</EM>.</span></span> <span data-ttu-id="d0444-153">Подробные сведения о сплаттинг в Windows PowerShell можно найти <A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>в разделе.</span><span class="sxs-lookup"><span data-stu-id="d0444-153">For details about splatting in Windows PowerShell, see <A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="d0444-154">Изменение существующего сценария с помощью командлета Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="d0444-154">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="d0444-155">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d0444-155">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d0444-p111">Можно использовать не больше двух сценариев для области действия. Вы можете изменить выполняемые сценарии в любое время даже во время сеанса ведения журналов. Если переопределить выполняемые сценарии, текущий сеанс перестанет использовать удаленный сценарий и начнет применять новый сценарий. Однако данные ведения журналов, полученные с помощью удаленного сценария, останутся в полученных журналах. Чтобы определить новый сценарий, выполните следующие действия (если уже определенный поставщик "S4Provider" уже добавлен):</span><span class="sxs-lookup"><span data-stu-id="d0444-p111">You are limited to two scenarios per scope. You can change which scenarios are running at any time, even when a logging capture session is in process. If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario. However, the logging information that was captured with the removed scenario remains in the captured logs. To define a new scenario, do the following (that is, assuming the addition of an already defined provider named “S4Provider”):</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    <span data-ttu-id="d0444-161">Например:</span><span class="sxs-lookup"><span data-stu-id="d0444-161">For example:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    <span data-ttu-id="d0444-p112">Если вы хотите заменить поставщики, определить один поставщика или разделенный запятыми список поставщиков, чтобы заменить текущий набор. Если вы хотите только заменить один из нескольких поставщиков, добавьте текущие поставщики с новыми поставщиками, чтобы создать новый набор поставщиков, который содержит новые и существующие поставщики. Чтобы заменить все поставщики новым набором, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d0444-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    <span data-ttu-id="d0444-165">Например, чтобы заменить текущий набор из $LyssProvider, $ABServerProvider и $SIPStackProvider на $LyssServiceProvider, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d0444-165">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    <span data-ttu-id="d0444-166">Чтобы заменить только поставщик $LyssProvider из текущего набора $LyssProvider, $ABServerProvider и $SIPStackProvider на $LyssServiceProvider, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d0444-166">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="d0444-167">Удаление существующего сценария с помощью командлета Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="d0444-167">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="d0444-168">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d0444-168">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d0444-169">Если вы хотите удалить сценарий, определенный ранее, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d0444-169">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    <span data-ttu-id="d0444-170">Например, чтобы удалить заданный сценарий site:Redmond/LyssServiceScenario:</span><span class="sxs-lookup"><span data-stu-id="d0444-170">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

<span data-ttu-id="d0444-171">Командлет **Remove-CsClsScenario** удаляет указанный сценарий, но полученные трассировки все еще доступны в журналах.</span><span class="sxs-lookup"><span data-stu-id="d0444-171">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a><span data-ttu-id="d0444-172">Загрузка и выгрузка командлета Edit-Ксклссценарио с помощью модуля Клсконтроллер. PSM1</span><span class="sxs-lookup"><span data-stu-id="d0444-172">To load and unload the Edit-CsClsScenario cmdlet using the ClsController.psm1 module</span></span>

1.  <span data-ttu-id="d0444-173">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d0444-173">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d0444-174">Модуль Клсконтроллер. PSM1 предоставляется в виде отдельного веб-файла для загрузки.</span><span class="sxs-lookup"><span data-stu-id="d0444-174">The ClsController.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="d0444-175">Модуль входит в состав средств отладки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0444-175">The module is part of the Lync Server 2013 Debugging tools.</span></span> <span data-ttu-id="d0444-176">По умолчанию инструменты отладки устанавливаются в каталоге C:\Program Филес\линк Server 2013 \ Отладка.</span><span class="sxs-lookup"><span data-stu-id="d0444-176">By default, the debugging tools are installed in the directory C:\Program Files\Lync Server 2013\Debugging Tools.</span></span>

    
    </div>

2.  <span data-ttu-id="d0444-177">В Windows PowerShell введите:</span><span class="sxs-lookup"><span data-stu-id="d0444-177">From the Windows PowerShell, type:</span></span>
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="d0444-178">Успешная загрузка модуля возвращает вас в командную команду Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0444-178">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="d0444-179">Чтобы убедиться в том, что модуль загружен и что он доступен для редактирования, Ксклссценарио <CODE>Get-Help Edit-CsClsScenario</CODE>, введите.</span><span class="sxs-lookup"><span data-stu-id="d0444-179">To confirm that the module is loaded and that Edit-CsClsScenario is available, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="d0444-180">Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="d0444-180">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span>

    
    </div>

3.  <span data-ttu-id="d0444-181">Чтобы выгрузить модули, введите:</span><span class="sxs-lookup"><span data-stu-id="d0444-181">To unload the modules, type:</span></span>
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="d0444-182">Успешная выгрузка модуля возвращает вас в командную команду Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0444-182">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="d0444-183">Чтобы убедиться в том, что модуль выгружен, введите <CODE>Get-Help Edit-CsClsScenario</CODE>.</span><span class="sxs-lookup"><span data-stu-id="d0444-183">To confirm that the module is unloaded, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="d0444-184">Windows PowerShell попытается найти справку для командлета и не будет выполнена.</span><span class="sxs-lookup"><span data-stu-id="d0444-184">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="d0444-185">Удаление существующего поставщика из сценария с помощью командлета Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="d0444-185">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="d0444-186">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d0444-186">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d0444-187">Чтобы удалить поставщика из сценария AlwaysOn, введите:</span><span class="sxs-lookup"><span data-stu-id="d0444-187">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    <span data-ttu-id="d0444-188">Например:</span><span class="sxs-lookup"><span data-stu-id="d0444-188">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    <span data-ttu-id="d0444-p116">Параметры ScenarioName и ProviderName являются позиционными (т. е. их необходимо задать в ожидаемой позиции в командной строке). Имя параметра необязательно явно определять, если имя сценария находится во второй позиции, а поставщик — в третьей позиции относительно первой позиции имени командлета. Используя эту информацию, предыдущая команда вводится следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d0444-p116">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    <span data-ttu-id="d0444-p117">Позиционное размещение значений параметров применяется только к параметрам –Scenario и –Provider. Все другие параметры нужно определить явно.</span><span class="sxs-lookup"><span data-stu-id="d0444-p117">The positional placing of the parameter values applies only to –Scenario and –Provider. All other parameters must be explicitly defined.</span></span>

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="d0444-194">Добавление поставщика в сценарий с помощью командлета Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="d0444-194">To add a provider to a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="d0444-195">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d0444-195">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d0444-196">Чтобы добавить поставщик в сценарий AlwaysOn, введите:</span><span class="sxs-lookup"><span data-stu-id="d0444-196">To add a provider to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    <span data-ttu-id="d0444-197">Например:</span><span class="sxs-lookup"><span data-stu-id="d0444-197">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    <span data-ttu-id="d0444-198">\-Логлевел может иметь тип Неустранимая, ошибка, предупреждение, сведения, подробный, отладочный или все.</span><span class="sxs-lookup"><span data-stu-id="d0444-198">\-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="d0444-199">– Флаги могут быть любыми флагами, которые поддерживаются поставщиком, например\_TF Component,\_TF DIAG.</span><span class="sxs-lookup"><span data-stu-id="d0444-199">–Flags can be any of the flags that the provider supports, such as TF\_COMPONENT, TF\_DIAG.</span></span> <span data-ttu-id="d0444-200">Для параметра –Flags также можно указать значение ALL</span><span class="sxs-lookup"><span data-stu-id="d0444-200">–Flags can also be of value ALL</span></span>
    
    <span data-ttu-id="d0444-p119">Предыдущий пример также можно ввести, используя позиционность командлета. Например, чтобы добавить поставщик ChatServer в сценарий AlwaysOn, введите:</span><span class="sxs-lookup"><span data-stu-id="d0444-p119">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

