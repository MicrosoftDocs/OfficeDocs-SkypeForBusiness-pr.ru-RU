---
title: Настройка сценариев для централизованной службы ведения журналов в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Сводка: сведения о том, как создавать, изменять и удалять сценарии централизованной службы ведения журналов в Skype для бизнеса Server 2015.'
ms.openlocfilehash: b7cfcbc85df7d66374d2bf33d572b9e91b30edde
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816598"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="ff408-103">Настройка сценариев для централизованной службы ведения журналов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="ff408-103">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ff408-104">**Сводка:** Сведения о том, как создавать, изменять и удалять сценарии централизованной службы ведения журналов в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ff408-104">**Summary:** Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ff408-105">Сценарии определяют область (глобальные, сайты, пулы или компьютеры) и поставщиков услуг, которые используются в централизованной службе ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="ff408-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="ff408-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span><span class="sxs-lookup"><span data-stu-id="ff408-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="ff408-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span><span class="sxs-lookup"><span data-stu-id="ff408-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="ff408-108">Если вы обнаружите, что сценарий нужно изменить в соответствии с требованиями для устранения неполадок и ведения журнала, в средствах отладки Skype для Business Server 2015 есть модуль Windows PowerShell с именем Клссценариоедит. psm1, который содержит функцию Намедедит-Ксклссценарио.</span><span class="sxs-lookup"><span data-stu-id="ff408-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Skype for Business Server 2015 Debug Tools provides you a Windows PowerShell module named ClsScenarioEdit.psm1 that contains a function namedEdit-CsClsScenario.</span></span> <span data-ttu-id="ff408-109">The purpose of the module is to edit the properties of the named scenario.</span><span class="sxs-lookup"><span data-stu-id="ff408-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="ff408-110">Examples of how this module works are provided in this topic.</span><span class="sxs-lookup"><span data-stu-id="ff408-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="ff408-111">Перед тем как приступить к работе, загрузите [средства отладки](https://go.microsoft.com/fwlink/p/?LinkId=285257) Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ff408-111">Download the Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) before going any further.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ff408-112">Для любой области действия (глобальной, области узла, пула и компьютера) одновременно можно использовать не больше двух сценариев.</span><span class="sxs-lookup"><span data-stu-id="ff408-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="ff408-113">Чтобы определить, какие сценарии выполняются в настоящее время, используйте Windows PowerShell и [Get-ксклссценарио](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ff408-113">To determine which scenarios are currently running, use Windows PowerShell and [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span> <span data-ttu-id="ff408-114">Используя Windows PowerShell и [Set-ксклссценарио](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), вы можете динамически менять, какие сценарии запущены.</span><span class="sxs-lookup"><span data-stu-id="ff408-114">By using Windows PowerShell and [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="ff408-115">Это можно сделать во время сеанса ведения журнала, чтобы скорректировать собираемые данные и поставщиков, от которых они собираются.</span><span class="sxs-lookup"><span data-stu-id="ff408-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span> 
  
<span data-ttu-id="ff408-116">Для запуска функций централизованной службы ведения журналов с помощью командной консоли Skype для бизнеса Server вы должны быть членами либо группами безопасности Ксадминистратор, либо Кссерверадминистратор для управления доступом на основе ролей (RBAC) или настраиваемой роли RBAC, которая один из этих двух групп.</span><span class="sxs-lookup"><span data-stu-id="ff408-116">To run the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="ff408-117">Чтобы возвратить список всех ролей RBAC, которым назначен этот командлет, включая любые пользовательские роли RBAC, созданные пользователем, выполните следующую команду в командной консоли управления Skype для бизнеса Server или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff408-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="ff408-118">Например:</span><span class="sxs-lookup"><span data-stu-id="ff408-118">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="ff408-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span><span class="sxs-lookup"><span data-stu-id="ff408-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="ff408-120">Вы можете использовать командную консоль сервера Skype для бизнеса, чтобы выпустить команды Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff408-120">You can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="ff408-121">Если вы используете Windows PowerShell, вы можете определить новые сценарии для использования в сеансах ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="ff408-121">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>
  
<span data-ttu-id="ff408-122">Как это было представлено в [службе централизованного ведения журналов в Skype для бизнеса 2015](centralized-logging-service.md), элементы сценария описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="ff408-122">As introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the elements of a scenario are:</span></span>
  
- <span data-ttu-id="ff408-123">**Поставщики услуг** Если вы знакомы с Окслогжер, поставщики — это компоненты, которые вы указываете, чтобы сообщить Окслогжер о том, что ядро трассировки должно собирать журналы.</span><span class="sxs-lookup"><span data-stu-id="ff408-123">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="ff408-124">Поставщики — это те же компоненты, а во многих случаях их имя совпадает с компонентами в OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="ff408-124">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="ff408-125">Если вы не знакомы с Окслогжер, поставщики являются компонентами, специфичными для серверной роли, из которой Служба централизованного ведения журналов может собирать журналы.</span><span class="sxs-lookup"><span data-stu-id="ff408-125">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="ff408-126">Подробные сведения о настройке поставщиков можно найти в разделе [Настройка служб централизованного ведения журналов в Skype для бизнеса Server 2015](configure-providers.md).</span><span class="sxs-lookup"><span data-stu-id="ff408-126">For details about the configuration of providers, see [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span></span>
    
- <span data-ttu-id="ff408-127">**Identity (идентификация** ) Параметр-Identity задает область и имя сценария.</span><span class="sxs-lookup"><span data-stu-id="ff408-127">**Identity** The parameter -Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="ff408-128">Например, вы можете задать область "Global" и определить сценарий с помощью "Лисссервицесценарио".</span><span class="sxs-lookup"><span data-stu-id="ff408-128">For example, you could set a scope of "global" and identify the scenario with "LyssServiceScenario".</span></span> <span data-ttu-id="ff408-129">При объединении двух данных вы определяете удостоверение (например, "Global/Лисссервицесценарио").</span><span class="sxs-lookup"><span data-stu-id="ff408-129">When you combine the two, you define the Identity (for example, "global/LyssServiceScenario").</span></span>
    
    <span data-ttu-id="ff408-130">При необходимости можно использовать параметры-Name и-Parent.</span><span class="sxs-lookup"><span data-stu-id="ff408-130">Optionally, you can use the -Name and -Parent parameters.</span></span> <span data-ttu-id="ff408-131">Параметр Name задается для уникальной идентификации сценария.</span><span class="sxs-lookup"><span data-stu-id="ff408-131">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="ff408-132">Если используется параметр Name, необходимо также использовать параметр Parent, чтобы добавить сценарий в глобальную область или область узла.</span><span class="sxs-lookup"><span data-stu-id="ff408-132">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="ff408-133">Если вы используете параметры "имя" и "родительский", нельзя использовать параметр **-Identity** .</span><span class="sxs-lookup"><span data-stu-id="ff408-133">If you use the Name and Parent parameters, you cannot use the **-Identity** parameter.</span></span>
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="ff408-134">Создание сценария с помощью командлета New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="ff408-134">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="ff408-135">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="ff408-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ff408-p108">Чтобы создать сценарий для сеанса ведения журналов, используйте [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) и задайте имя сценария (т. е. его уникальный идентификатор). Выберите тип формата ведения журнала в WPP (т. е. препроцессор трассировки ПО Windows, значение по умолчанию), EventLog (т. е. формат журнала событий Windows) или IISLog (т. е. формат ASCII на основе формата IIS). Затем задайте уровень (как указано в подразделе "Уровни ведения журнала" в этом разделе) и флаги (см. "Флаги" в этом разделе).</span><span class="sxs-lookup"><span data-stu-id="ff408-p108">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) and define the name of the scenario (that is, how it will be uniquely identified). Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format). Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="ff408-139">Для этого примера сценария мы используем LyssProvider как пример переменной поставщика.</span><span class="sxs-lookup"><span data-stu-id="ff408-139">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="ff408-140">Чтобы создать сценарий с помощью заданных параметров, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ff408-140">To create a scenario using the options defined, type:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    <span data-ttu-id="ff408-141">Например:</span><span class="sxs-lookup"><span data-stu-id="ff408-141">For example:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    <span data-ttu-id="ff408-142">Альтернативный формат: с помощью параметров-Name и-Parent.</span><span class="sxs-lookup"><span data-stu-id="ff408-142">The alternate format using -Name and -Parent:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="ff408-143">Создание сценария с несколькими поставщиками с помощью командлета New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="ff408-143">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="ff408-144">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="ff408-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ff408-145">You are limited to two scenarios per scope.</span><span class="sxs-lookup"><span data-stu-id="ff408-145">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="ff408-146">However, you are not limited to a set number of providers.</span><span class="sxs-lookup"><span data-stu-id="ff408-146">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="ff408-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span><span class="sxs-lookup"><span data-stu-id="ff408-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="ff408-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span><span class="sxs-lookup"><span data-stu-id="ff408-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="ff408-149">Чтобы определить сценарий и назначить ему несколько поставщиков, введите следующую команду в командной консоли управления Skype для бизнеса Server или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff408-149">To define and assign multiple providers to a scenario, type the following at a Skype for Business Server Management Shell or Windows PowerShell command prompt:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > <span data-ttu-id="ff408-150">Так как она известна в Windows PowerShell, для создания хэш-таблицы значений используется `@{<variable>=<value1>, <value2>, <value>…}` известная ассплаттинг.</span><span class="sxs-lookup"><span data-stu-id="ff408-150">As it is known in Windows PowerShell, the convention for creating a hash table of values using  `@{<variable>=<value1>, <value2>, <value>…}` is known assplatting.</span></span> <span data-ttu-id="ff408-151">Подробные сведения о сплаттинг в Windows PowerShell можно найти [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)в разделе.</span><span class="sxs-lookup"><span data-stu-id="ff408-151">For details about splatting in Windows PowerShell, see [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760).</span></span> 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="ff408-152">Изменение существующего сценария с помощью командлета Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="ff408-152">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="ff408-153">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="ff408-153">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ff408-154">Можно использовать не больше двух сценариев для области действия.</span><span class="sxs-lookup"><span data-stu-id="ff408-154">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="ff408-155">Вы можете изменить выполняемые сценарии в любое время даже во время сеанса ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="ff408-155">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="ff408-156">Если переопределить выполняемые сценарии, текущий сеанс перестанет использовать удаленный сценарий и начнет применять новый сценарий.</span><span class="sxs-lookup"><span data-stu-id="ff408-156">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="ff408-157">Однако данные ведения журналов, полученные с помощью удаленного сценария, останутся в полученных журналах.</span><span class="sxs-lookup"><span data-stu-id="ff408-157">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="ff408-158">Чтобы определить новый сценарий, сделайте следующее (то есть, предполагается добавление уже определенного поставщика с именем "S4Provider"):</span><span class="sxs-lookup"><span data-stu-id="ff408-158">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named "S4Provider"):</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    <span data-ttu-id="ff408-159">Например:</span><span class="sxs-lookup"><span data-stu-id="ff408-159">For example:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    <span data-ttu-id="ff408-p112">Если вы хотите заменить поставщики, определить один поставщика или разделенный запятыми список поставщиков, чтобы заменить текущий набор. Если вы хотите только заменить один из нескольких поставщиков, добавьте текущие поставщики с новыми поставщиками, чтобы создать новый набор поставщиков, который содержит новые и существующие поставщики. Чтобы заменить все поставщики новым набором, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ff408-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    <span data-ttu-id="ff408-163">Например, чтобы заменить текущий набор из $LyssProvider, $ABServerProvider и $SIPStackProvider на $LyssServiceProvider, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ff408-163">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    <span data-ttu-id="ff408-164">Чтобы заменить только поставщик $LyssProvider из текущего набора $LyssProvider, $ABServerProvider и $SIPStackProvider на $LyssServiceProvider, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ff408-164">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="ff408-165">Удаление существующего сценария с помощью командлета Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="ff408-165">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="ff408-166">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="ff408-166">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ff408-167">Если вы хотите удалить сценарий, определенный ранее, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ff408-167">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    <span data-ttu-id="ff408-168">Например, чтобы удалить заданный сценарий site:Redmond/LyssServiceScenario:</span><span class="sxs-lookup"><span data-stu-id="ff408-168">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

<span data-ttu-id="ff408-169">Командлет **Remove-CsClsScenario** удаляет указанный сценарий, но полученные трассировки все еще доступны в журналах.</span><span class="sxs-lookup"><span data-stu-id="ff408-169">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a><span data-ttu-id="ff408-170">Загрузка и выгрузка командлета Edit-CsClsScenario с помощью модуля ClsScenarioEdit.psm1</span><span class="sxs-lookup"><span data-stu-id="ff408-170">To load and unload the Edit-CsClsScenario cmdlet using the ClsScenarioEdit.psm1 module</span></span>

1. <span data-ttu-id="ff408-171">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="ff408-171">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ff408-172">Модуль ClsScenarioEdit.psm1 предоставляется как отдельная веб-загрузка.</span><span class="sxs-lookup"><span data-stu-id="ff408-172">The ClsScenarioEdit.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="ff408-173">Модуль входит в состав средств отладки в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ff408-173">The module is part of the Skype for Business Server 2015 Debugging tools.</span></span> <span data-ttu-id="ff408-174">По умолчанию средства отладки устанавливаются в каталог C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="ff408-174">By default, the debugging tools are installed in the directory C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> 
  
2. <span data-ttu-id="ff408-175">В Windows PowerShell введите:</span><span class="sxs-lookup"><span data-stu-id="ff408-175">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="ff408-176">Успешная загрузка модуля возвращает вас в командную команду Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff408-176">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="ff408-177">Чтобы убедиться в том, что модуль загружен и что он доступен для редактирования, Ксклссценарио `Get-Help Edit-CsClsScenario`, введите.</span><span class="sxs-lookup"><span data-stu-id="ff408-177">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="ff408-178">Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="ff408-178">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="ff408-179">Чтобы выгрузить модули, введите:</span><span class="sxs-lookup"><span data-stu-id="ff408-179">To unload the modules, type:</span></span>
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > <span data-ttu-id="ff408-180">Успешная выгрузка модуля возвращает вас в командную команду Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff408-180">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="ff408-181">Чтобы убедиться в том, что модуль выгружен, введите `Get-Help Edit-CsClsScenario`.</span><span class="sxs-lookup"><span data-stu-id="ff408-181">To confirm that the module is unloaded, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="ff408-182">Windows PowerShell попытается найти справку для командлета и не будет выполнена.</span><span class="sxs-lookup"><span data-stu-id="ff408-182">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span> 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="ff408-183">Удаление существующего поставщика из сценария с помощью командлета Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="ff408-183">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="ff408-184">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="ff408-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ff408-185">В Windows PowerShell введите:</span><span class="sxs-lookup"><span data-stu-id="ff408-185">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="ff408-186">Успешная загрузка модуля возвращает вас в командную команду Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff408-186">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="ff408-187">Чтобы убедиться в том, что модуль загружен и что он доступен для редактирования, Ксклссценарио `Get-Help Edit-CsClsScenario`, введите.</span><span class="sxs-lookup"><span data-stu-id="ff408-187">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="ff408-188">Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="ff408-188">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="ff408-189">Чтобы удалить поставщика из сценария AlwaysOn, введите:</span><span class="sxs-lookup"><span data-stu-id="ff408-189">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   <span data-ttu-id="ff408-190">Например:</span><span class="sxs-lookup"><span data-stu-id="ff408-190">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   <span data-ttu-id="ff408-p117">Параметры ScenarioName и ProviderName являются позиционными (т. е. их необходимо задать в ожидаемой позиции в командной строке). Имя параметра необязательно явно определять, если имя сценария находится во второй позиции, а поставщик — в третьей позиции относительно первой позиции имени командлета. Используя эту информацию, предыдущая команда вводится следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ff408-p117">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   <span data-ttu-id="ff408-194">Позиционные размещения значений параметров применяются только к-сценарию и-поставщику.</span><span class="sxs-lookup"><span data-stu-id="ff408-194">The positional placing of the parameter values applies only to -Scenario and -Provider.</span></span> <span data-ttu-id="ff408-195">Все другие параметры нужно определить явно.</span><span class="sxs-lookup"><span data-stu-id="ff408-195">All other parameters must be explicitly defined.</span></span>
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="ff408-196">Добавление поставщика в сценарий с помощью командлета Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="ff408-196">To add a provider to a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="ff408-197">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="ff408-197">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ff408-198">Чтобы добавить поставщик в сценарий AlwaysOn, введите:</span><span class="sxs-lookup"><span data-stu-id="ff408-198">To add a provider to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    <span data-ttu-id="ff408-199">Например:</span><span class="sxs-lookup"><span data-stu-id="ff408-199">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    <span data-ttu-id="ff408-200">Значением -Loglevel может быть Fatal, Error, Warning, Info, Verbose, Debug или All.</span><span class="sxs-lookup"><span data-stu-id="ff408-200">-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="ff408-201">Флагами могут быть любые флаги, поддерживаемые поставщиком, например TF_COMPONENT, TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="ff408-201">-Flags can be any of the flags that the provider supports, such as TF_COMPONENT, TF_DIAG.</span></span> <span data-ttu-id="ff408-202">-Флаги также могут иметь значение "все"</span><span class="sxs-lookup"><span data-stu-id="ff408-202">-Flags can also be of value ALL</span></span>
    
   <span data-ttu-id="ff408-p120">Предыдущий пример также можно ввести, используя позиционность командлета. Например, чтобы добавить поставщик ChatServer в сценарий AlwaysOn, введите:</span><span class="sxs-lookup"><span data-stu-id="ff408-p120">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
