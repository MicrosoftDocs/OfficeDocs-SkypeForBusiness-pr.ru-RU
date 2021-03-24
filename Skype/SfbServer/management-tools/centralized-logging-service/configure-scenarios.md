---
title: Настройка сценариев для централизованной службы ведения журнала в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: Сводка. Сведения о создании, изменении и устранении сценариев централизованной службы ведения журнала в Skype для бизнеса Server 2015.
ms.openlocfilehash: 6ec6764ce3717f38fead9e88c570895f1676310f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098845"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="d0e9c-103">Настройка сценариев для централизованной службы ведения журнала в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="d0e9c-103">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d0e9c-104">**Сводка:** Узнайте, как создавать, изменять и удалять сценарии для централизованной службы ведения журнала в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-104">**Summary:** Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d0e9c-105">Сценарии определяют область (то есть глобальный, сайт, пул или компьютер) и то, какие поставщики будут использовать в службе централизованного ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="d0e9c-106">С помощью сценариев вы включаете и отключаете трассировку поставщиков (например, S4, SIPStack, мгновенных сообщений и сведений о присутствии).</span><span class="sxs-lookup"><span data-stu-id="d0e9c-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="d0e9c-107">Настроив сценарий вы можете сгруппировать все поставщики заданной логической коллекции, которые решают определенную проблему.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="d0e9c-108">Если для устранения неполадок и ведения журнала необходимо изменить сценарий, средства отладки Skype для бизнеса Server 2015 предоставляют вам модуль Windows PowerShell ClsScenarioEdit.psm1, содержащий функцию с именемEdit-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Skype for Business Server 2015 Debug Tools provides you a Windows PowerShell module named ClsScenarioEdit.psm1 that contains a function namedEdit-CsClsScenario.</span></span> <span data-ttu-id="d0e9c-109">Предназначение этого модуля — изменение свойств именованного сценария.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="d0e9c-110">Примеры работы этого модуля представлены в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="d0e9c-111">Скачайте средства отладки Skype [](https://go.microsoft.com/fwlink/p/?LinkId=285257) для бизнеса Server 2015, прежде чем ходить дальше.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-111">Download the Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) before going any further.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d0e9c-112">Для любой области действия (глобальной, области узла, пула и компьютера) одновременно можно использовать не больше двух сценариев.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="d0e9c-113">Чтобы определить, какие сценарии в настоящее время запущены, Windows PowerShell [и Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d0e9c-113">To determine which scenarios are currently running, use Windows PowerShell and [Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span> <span data-ttu-id="d0e9c-114">С помощью Windows PowerShell [и Set-CsClsScenario](/powershell/module/skype/set-csclsscenario?view=skype-ps)можно динамически изменить сценарии.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-114">By using Windows PowerShell and [Set-CsClsScenario](/powershell/module/skype/set-csclsscenario?view=skype-ps), you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="d0e9c-115">Это можно сделать во время сеанса ведения журнала, чтобы скорректировать собираемые данные и поставщиков, от которых они собираются.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span> 
  
<span data-ttu-id="d0e9c-116">Чтобы запустить функции службы централизованного ведения журнала с помощью оболочки управления skype для бизнес-серверов, необходимо быть членом группы безопасности CsAdministrator или группы управления ролями CsServerAdministrator (RBAC) или настраиваемой роли RBAC, которая содержит обе эти группы.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-116">To run the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="d0e9c-117">Чтобы вернуть список всех ролей RBAC, на которые был назначен этот командлет, включая настраиваемые роли RBAC, созданные вами самостоятельно, запустите следующую команду из командной команды Skype для бизнеса server или Windows PowerShell запроса:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="d0e9c-118">Например:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-118">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="d0e9c-119">Остальная часть этого раздела посвящена определению сценария, изменению сценария, получению сведений о выполняемых сценариях, удалению сценария указанию содержимого сценария для оптимизации устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="d0e9c-120">Вы можете использовать командную оболочку Skype для бизнес-серверов для Windows PowerShell команд.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-120">You can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="d0e9c-121">При использовании Windows PowerShell можно определить новые сценарии для использования в сеансах ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-121">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>
  
<span data-ttu-id="d0e9c-122">Как было введено в службе централизованного ведения журнала [в Skype для бизнеса 2015 г.,](centralized-logging-service.md)элементами сценария являются:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-122">As introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the elements of a scenario are:</span></span>
  
- <span data-ttu-id="d0e9c-123">**Поставщики** Если вы знакомы с OCSLogger, поставщики — это компоненты, которые необходимо сообщить OCSLogger, из чего должен собирать журналы двигатель отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-123">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="d0e9c-124">Поставщики — это те же компоненты, а во многих случаях их имя совпадает с компонентами в OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-124">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="d0e9c-125">Если вы не знакомы с OCSLogger, поставщики являются определенными компонентами роли сервера, из них централизованная служба ведения журнала может собирать журналы.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-125">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="d0e9c-126">Сведения о конфигурации поставщиков см. в материале [Configure providers for Centralized Logging Service in Skype for Business Server 2015.](configure-providers.md)</span><span class="sxs-lookup"><span data-stu-id="d0e9c-126">For details about the configuration of providers, see [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span></span>
    
- <span data-ttu-id="d0e9c-127">**Identity** Параметр -Identity задает область и имя сценария.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-127">**Identity** The parameter -Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="d0e9c-128">Например, можно установить область "глобальный" и определить сценарий с помощью "LyssServiceScenario".</span><span class="sxs-lookup"><span data-stu-id="d0e9c-128">For example, you could set a scope of "global" and identify the scenario with "LyssServiceScenario".</span></span> <span data-ttu-id="d0e9c-129">При сочетании этих двух личных данных определяется идентификатор (например, "global/LyssServiceScenario").</span><span class="sxs-lookup"><span data-stu-id="d0e9c-129">When you combine the two, you define the Identity (for example, "global/LyssServiceScenario").</span></span>
    
    <span data-ttu-id="d0e9c-130">Необязательно можно использовать параметры -Name и -Parent.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-130">Optionally, you can use the -Name and -Parent parameters.</span></span> <span data-ttu-id="d0e9c-131">Параметр Name задается для уникальной идентификации сценария.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-131">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="d0e9c-132">Если используется параметр Name, необходимо также использовать параметр Parent, чтобы добавить сценарий в глобальную область или область узла.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-132">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="d0e9c-133">Если вы используете параметры Name и Parent, вы не можете использовать **параметр -Identity.**</span><span class="sxs-lookup"><span data-stu-id="d0e9c-133">If you use the Name and Parent parameters, you cannot use the **-Identity** parameter.</span></span>
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="d0e9c-134">Создание сценария с помощью командлета New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="d0e9c-134">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="d0e9c-135">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="d0e9c-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d0e9c-136">Чтобы создать новый сценарий для сеанса ведения журнала, используйте [New-CsClsProvider](/powershell/module/skype/new-csclsprovider?view=skype-ps) и определите имя сценария (т. е. как он будет однозначно идентифицирован).</span><span class="sxs-lookup"><span data-stu-id="d0e9c-136">To create a new scenario for a logging session, use [New-CsClsProvider](/powershell/module/skype/new-csclsprovider?view=skype-ps) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="d0e9c-137">Выберите тип формата ведения журнала из WPP (то есть предварительного отслеживания по умолчанию программного обеспечения Windows), EventLog (то есть формат журнала событий Windows) или IISLog (то есть файла формата ASCII на основе формата файла журнала IIS).</span><span class="sxs-lookup"><span data-stu-id="d0e9c-137">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="d0e9c-138">Далее определите Уровень (как определенный в разделе Уровни ведения журнала в этом разделе) и Флаги (как определено в разделе Флаги в этом разделе).</span><span class="sxs-lookup"><span data-stu-id="d0e9c-138">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="d0e9c-139">Для этого примера сценария мы используем LyssProvider как пример переменной поставщика.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-139">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="d0e9c-140">Чтобы создать сценарий с помощью заданных параметров, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-140">To create a scenario using the options defined, type:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    <span data-ttu-id="d0e9c-141">Например:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-141">For example:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    <span data-ttu-id="d0e9c-142">Альтернативный формат с помощью -Name и -Parent:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-142">The alternate format using -Name and -Parent:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="d0e9c-143">Создание сценария с несколькими поставщиками с помощью командлета New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="d0e9c-143">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="d0e9c-144">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="d0e9c-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d0e9c-145">Можно использовать не больше двух сценариев для области действия.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-145">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="d0e9c-146">Однако число поставщиков не ограничено.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-146">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="d0e9c-147">В этом примере предположим, что мы создали три поставщика и хотим назначить все три из них определяемому вами сценарию.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="d0e9c-148">Имена переменных поставщиков: LyssProvider, ABServerProvider и SIPStackProvider.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="d0e9c-149">Чтобы определить и назначить несколько поставщиков сценарию, введите следующее в командной Windows PowerShell Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-149">To define and assign multiple providers to a scenario, type the following at a Skype for Business Server Management Shell or Windows PowerShell command prompt:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > <span data-ttu-id="d0e9c-150">Как известно в Windows PowerShell, конвенция по созданию таблицы значений с использованием hash называется  `@{<variable>=<value1>, <value2>, <value>…}` assplatting.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-150">As it is known in Windows PowerShell, the convention for creating a hash table of values using  `@{<variable>=<value1>, <value2>, <value>…}` is known assplatting.</span></span> <span data-ttu-id="d0e9c-151">Подробные сведения о splatting в Windows PowerShell [https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10)) см. в .</span><span class="sxs-lookup"><span data-stu-id="d0e9c-151">For details about splatting in Windows PowerShell, see [https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10)).</span></span> 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="d0e9c-152">Изменение существующего сценария с помощью командлета Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="d0e9c-152">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="d0e9c-153">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="d0e9c-153">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d0e9c-154">Можно использовать не больше двух сценариев для области действия.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-154">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="d0e9c-155">Вы можете изменить выполняемые сценарии в любое время даже во время сеанса ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-155">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="d0e9c-156">Если переопределить выполняемые сценарии, текущий сеанс перестанет использовать удаленный сценарий и начнет применять новый сценарий.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-156">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="d0e9c-157">Однако данные ведения журналов, полученные с помощью удаленного сценария, останутся в полученных журналах.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-157">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="d0e9c-158">Чтобы определить новый сценарий, сделайте следующее (то есть при условии добавления уже определенного поставщика с именем "S4Provider"):</span><span class="sxs-lookup"><span data-stu-id="d0e9c-158">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named "S4Provider"):</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    <span data-ttu-id="d0e9c-159">Например:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-159">For example:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    <span data-ttu-id="d0e9c-p112">Если вы хотите заменить поставщики, определить один поставщика или разделенный запятыми список поставщиков, чтобы заменить текущий набор. Если вы хотите только заменить один из нескольких поставщиков, добавьте текущие поставщики с новыми поставщиками, чтобы создать новый набор поставщиков, который содержит новые и существующие поставщики. Чтобы заменить все поставщики новым набором, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    <span data-ttu-id="d0e9c-163">Например, чтобы заменить текущий набор из $LyssProvider, $ABServerProvider и $SIPStackProvider на $LyssServiceProvider, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-163">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    <span data-ttu-id="d0e9c-164">Чтобы заменить только поставщик $LyssProvider из текущего набора $LyssProvider, $ABServerProvider и $SIPStackProvider на $LyssServiceProvider, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-164">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="d0e9c-165">Удаление существующего сценария с помощью командлета Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="d0e9c-165">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="d0e9c-166">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="d0e9c-166">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d0e9c-167">Если вы хотите удалить сценарий, определенный ранее, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-167">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    <span data-ttu-id="d0e9c-168">Например, чтобы удалить заданный сценарий site:Redmond/LyssServiceScenario:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-168">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

<span data-ttu-id="d0e9c-169">Командлет **Remove-CsClsScenario** удаляет указанный сценарий, но полученные трассировки все еще доступны в журналах.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-169">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a><span data-ttu-id="d0e9c-170">Загрузка и разгрузка Edit-CsClsScenario с помощью модуля ClsScenarioEdit.psm1</span><span class="sxs-lookup"><span data-stu-id="d0e9c-170">To load and unload the Edit-CsClsScenario cmdlet using the ClsScenarioEdit.psm1 module</span></span>

1. <span data-ttu-id="d0e9c-171">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="d0e9c-171">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d0e9c-172">Модуль ClsScenarioEdit.psm1 предоставляется в качестве отдельного веб-скачивания.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-172">The ClsScenarioEdit.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="d0e9c-173">Модуль является частью средств отладки Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-173">The module is part of the Skype for Business Server 2015 Debugging tools.</span></span> <span data-ttu-id="d0e9c-174">По умолчанию средства отладки устанавливаются в каталогЕ C:\Program Files\Skype для бизнеса Server 2015\Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-174">By default, the debugging tools are installed in the directory C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> 
  
2. <span data-ttu-id="d0e9c-175">Из Windows PowerShell введите:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-175">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="d0e9c-176">Успешная загрузка модуля возвращает вас к Windows PowerShell командной подсказке.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-176">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="d0e9c-177">Чтобы подтвердить загрузку модуля и наличие Edit-CsClsScenario, введите  `Get-Help Edit-CsClsScenario` .</span><span class="sxs-lookup"><span data-stu-id="d0e9c-177">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="d0e9c-178">Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-178">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="d0e9c-179">Чтобы выгрузить модули, введите:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-179">To unload the modules, type:</span></span>
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > <span data-ttu-id="d0e9c-180">Успешная разгрузка модуля возвращает вас к Windows PowerShell командной подсказке.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-180">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="d0e9c-181">Чтобы подтвердить, что модуль разгружен, введите  `Get-Help Edit-CsClsScenario` .</span><span class="sxs-lookup"><span data-stu-id="d0e9c-181">To confirm that the module is unloaded, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="d0e9c-182">Windows PowerShell будет пытаться найти справку для cmdlet и сбой.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-182">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span> 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="d0e9c-183">Удаление существующего поставщика из сценария с помощью командлета Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="d0e9c-183">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="d0e9c-184">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="d0e9c-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d0e9c-185">Из Windows PowerShell введите:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-185">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="d0e9c-186">Успешная загрузка модуля возвращает вас к Windows PowerShell командной подсказке.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-186">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="d0e9c-187">Чтобы подтвердить загрузку модуля и наличие Edit-CsClsScenario, введите  `Get-Help Edit-CsClsScenario` .</span><span class="sxs-lookup"><span data-stu-id="d0e9c-187">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="d0e9c-188">Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-188">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="d0e9c-189">Чтобы удалить поставщика из сценария AlwaysOn, введите:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-189">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   <span data-ttu-id="d0e9c-190">Например:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-190">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   <span data-ttu-id="d0e9c-p117">Параметры ScenarioName и ProviderName являются позиционными (т. е. их необходимо задать в ожидаемой позиции в командной строке). Имя параметра необязательно явно определять, если имя сценария находится во второй позиции, а поставщик — в третьей позиции относительно первой позиции имени командлета. Используя эту информацию, предыдущая команда вводится следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-p117">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   <span data-ttu-id="d0e9c-194">Позиционное размещение значений параметров применяется только к -Scenario и -Provider.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-194">The positional placing of the parameter values applies only to -Scenario and -Provider.</span></span> <span data-ttu-id="d0e9c-195">Все другие параметры нужно определить явно.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-195">All other parameters must be explicitly defined.</span></span>
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="d0e9c-196">Добавление поставщика в сценарий с помощью командлета Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="d0e9c-196">To add a provider to a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="d0e9c-197">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="d0e9c-197">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d0e9c-198">Чтобы добавить поставщик в сценарий AlwaysOn, введите:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-198">To add a provider to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    <span data-ttu-id="d0e9c-199">Например:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-199">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    <span data-ttu-id="d0e9c-200">Значением -Loglevel может быть Fatal, Error, Warning, Info, Verbose, Debug или All.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-200">-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="d0e9c-201">-Флаги могут быть любыми флагами, поддерживаемыми поставщиком, например TF_COMPONENT, TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="d0e9c-201">-Flags can be any of the flags that the provider supports, such as TF_COMPONENT, TF_DIAG.</span></span> <span data-ttu-id="d0e9c-202">-Флаги также могут иметь значение ALL</span><span class="sxs-lookup"><span data-stu-id="d0e9c-202">-Flags can also be of value ALL</span></span>
    
   <span data-ttu-id="d0e9c-p120">Предыдущий пример также можно ввести, используя позиционность командлета. Например, чтобы добавить поставщик ChatServer в сценарий AlwaysOn, введите:</span><span class="sxs-lookup"><span data-stu-id="d0e9c-p120">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```