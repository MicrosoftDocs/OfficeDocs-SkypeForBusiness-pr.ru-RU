---
title: Настройка поставщиков службы централизованного ведения журналов в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: Сводка. Сведения о настройке поставщиков сценариев для службы централизованного ведения журналов в Skype для бизнеса Server 2015.
ms.openlocfilehash: c96a87ea76930dbd99341667852a9731e56b88b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835169"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="34992-103">Настройка поставщиков службы централизованного ведения журналов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="34992-103">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="34992-104">**Сводка:** Узнайте, как настроить поставщиков сценариев для службы централизованного ведения журналов в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="34992-104">**Summary:** Learn how to configure scenario providers for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="34992-105">Концепции и конфигурация поставщиков в службе централизованного ведения журналов — одно из наиболее важных из понятий.</span><span class="sxs-lookup"><span data-stu-id="34992-105">The concepts and configuration of providers in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="34992-106">В модели трассиации Skype для бизнеса Server серверы напрямую сопобираются с компонентами роли сервера Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="34992-106">Theproviders map directly to Skype for Business Server server role components in the Skype for Business Server tracing model.</span></span> <span data-ttu-id="34992-107">Поставщик определяет компоненты Skype для бизнеса Server 2015, которые будут отслеживаться, тип сообщений (например, неудалось, ошибка или предупреждение) и флаги (например, TF_Connection или TF_Diag).</span><span class="sxs-lookup"><span data-stu-id="34992-107">The provider defines the components of a Skype for Business Server 2015 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF_Connection or TF_Diag).</span></span> <span data-ttu-id="34992-108">Поставщики — это отслеживаемые компоненты в каждой роли сервера Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="34992-108">Providers are the traceable components in each Skype for Business Server server role.</span></span> <span data-ttu-id="34992-109">С помощью поставщиков вы определяете уровень и тип трассии для компонентов (например, S4, SIPStack, IM и Presence).</span><span class="sxs-lookup"><span data-stu-id="34992-109">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="34992-110">Определенный поставщик используется в сценарии для группировки всех поставщиков для заданной логической коллекции, которая решает определенное условие проблемы.</span><span class="sxs-lookup"><span data-stu-id="34992-110">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>
  
<span data-ttu-id="34992-111">Для запуска функций службы централизованного ведения журналов с помощью оболочки управления Skype для бизнеса Server необходимо быть членом группы безопасности управления доступом на основе ролей (RBAC) CsAdministrator или CsServerAdministrator или настраиваемой роли RBAC, которая содержит какую-либо из этих двух групп.</span><span class="sxs-lookup"><span data-stu-id="34992-111">To run the Centralized Logging Service functions using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="34992-112">Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которые назначены этому командлету (включая все самостоятельно созданные роли RBAC), в командной командной Windows PowerShell Skype для бизнеса Server или командной Windows PowerShell командной Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="34992-112">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="34992-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="34992-113">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="34992-114">Остальная часть этого раздела посвящена определению поставщиков, изменению поставщика и определению поставщика для оптимизации устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="34992-114">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="34992-115">Существует два способа выдачи команд службы централизованного ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="34992-115">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="34992-116">You can use the CLSController.exe that is located, by default, in the directory C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="34992-116">You can use the CLSController.exe that is located, by default, in the directory C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span></span> <span data-ttu-id="34992-117">Для выдачи Windows PowerShell можно использовать командную Windows PowerShell Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="34992-117">Or, you can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="34992-118">С помощью Windows PowerShell вы можете определить новых поставщиков для использования в сеансах ведения журнала и получить полный контроль над их созданием, тем, что они собирают и на каком уровне собирают данные.</span><span class="sxs-lookup"><span data-stu-id="34992-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="34992-p104">Как уже упоминалось, поставщики являются очень мощным средством. Однако сценарии имеют большее значение, так как объединяют в себе все данные, необходимые для определения и выполнения трассировок компонентов, представленных поставщиками. Сценарии, которые являются коллекциями поставщиков, можно сравнить с выполнением пакетного файла, содержащего сотни команд, для сбора большого объема данных, что отличается от выполнения сотен команд по одной в командной строке.</span><span class="sxs-lookup"><span data-stu-id="34992-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span> 
  
<span data-ttu-id="34992-122">Вместо того чтобы подробно рыться в подробных сведениях о поставщиках, централизованная служба ведения журналов предоставляет ряд сценариев, уже определенных для вас.</span><span class="sxs-lookup"><span data-stu-id="34992-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="34992-123">Предоставленные сценарии покрывают большое количество различных проблем и неполадок, которые могут возникнуть.</span><span class="sxs-lookup"><span data-stu-id="34992-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="34992-124">В редких случаях может понадобиться создать и определить поставщиков и назначить их в сценарии.</span><span class="sxs-lookup"><span data-stu-id="34992-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="34992-125">Настоятельно рекомендуется ознакомиться с каждым предоставленным сценарием, прежде чем создавать новых поставщиков и сценарии.</span><span class="sxs-lookup"><span data-stu-id="34992-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="34992-126">Хотя здесь предоставляются сведения о создании поставщиков, чтобы вы могли ознакомиться с тем, как сценарии используют элементы поставщиков для сбора данных трассировок, сведения о самих поставщиках в настоящее время не предоставлены.</span><span class="sxs-lookup"><span data-stu-id="34992-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span> 
  
<span data-ttu-id="34992-127">Впервые представленная в службе централизованного ведения журналов в Skype для бизнеса [2015](centralized-logging-service.md)ключевые элементы определения поставщика для использования в сценарии:</span><span class="sxs-lookup"><span data-stu-id="34992-127">Introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>
  
- <span data-ttu-id="34992-128">**Поставщики** Если вы знакомы с OCSLogger, поставщики — это компоненты, из каких компонентов OCSLogger должен собирать журналы.</span><span class="sxs-lookup"><span data-stu-id="34992-128">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="34992-129">Поставщики — это те же компоненты, а во многих случаях их имя совпадает с компонентами в OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="34992-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="34992-130">Если вы не знакомы с OCSLogger, поставщики — это компоненты роли сервера, из которые централизованная служба ведения журналов может собирать журналы.</span><span class="sxs-lookup"><span data-stu-id="34992-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="34992-131">В случае службы централизованного ведения журналов CLSAgent является частью архитектуры службы централизованного ведения журналов, которая отслеживает компоненты, определенные в конфигурации поставщиков.</span><span class="sxs-lookup"><span data-stu-id="34992-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>
    
- <span data-ttu-id="34992-132">**Уровни ведения журнала** OCSLogger предоставляет возможность выбора нескольких уровней детализации для собранных данных.</span><span class="sxs-lookup"><span data-stu-id="34992-132">**Logging levels** OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="34992-133">Эта функция является неотъемлемой частью централизованной службы ведения журналов и сценариев и определяется с помощью параметра **Type.**</span><span class="sxs-lookup"><span data-stu-id="34992-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="34992-134">Вы можете выбрать следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="34992-134">You can choose from the following:</span></span>
    
  - <span data-ttu-id="34992-135">**Все** Собирает сообщения трассировки о неуявных ошибках, ошибках, предупреждениях, подробных и отлагежных сообщениях в журнал для определенного поставщика.</span><span class="sxs-lookup"><span data-stu-id="34992-135">**All** Collects trace messages of type fatal, error, warning, verbose, and debug info to the log for the defined provider.</span></span>
    
  - <span data-ttu-id="34992-136">**Неуявный** Собирает только сообщения трассировки, определенные как "Неудалось".</span><span class="sxs-lookup"><span data-stu-id="34992-136">**Fatal** Collects only the trace messages defined as "Fatal."</span></span>
    
  - <span data-ttu-id="34992-137">**Ошибка** Собирает только сообщения трассировки, определенные как "Ошибка" или "Неудательная ошибка".</span><span class="sxs-lookup"><span data-stu-id="34992-137">**Error** Collects only the trace messages defined as "Error" or "Fatal."</span></span>
    
  - <span data-ttu-id="34992-138">**Предупреждение** Собирает только сообщения трассировки типа "Предупреждение", "Ошибка" и "Неумеримая ошибка".</span><span class="sxs-lookup"><span data-stu-id="34992-138">**Warning** Collects only the trace messages of type "Warning," "Error" and "Fatal."</span></span>
    
  - <span data-ttu-id="34992-139">**Сведения** Собирает только сообщения трассировки, которые указывают на информационное сообщение для определенного поставщика, а также сообщения о неувядательных ошибках, ошибках и предупреждениях.</span><span class="sxs-lookup"><span data-stu-id="34992-139">**Info** Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
  - <span data-ttu-id="34992-140">**Подробное** Собирает все сообщения трассировки для определенного поставщика с ошибками, ошибками, предупреждениями и подробными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="34992-140">**Verbose** Collects all trace messages of type fatal, error, warning and verbose for the defined provider.</span></span>
    
  - <span data-ttu-id="34992-141">**Отлажка** по сути является эквивалентом "All" — собирает трассировки типа Fatal, Error, Warning, Info, Verbose и Debug для определенного поставщика.</span><span class="sxs-lookup"><span data-stu-id="34992-141">**Debug** this is essentially an equivalent of 'All' - collects traces of type Fatal, Error, Warning, Info, Verbose and Debug for the defined provider.</span></span>
    
- <span data-ttu-id="34992-142">**Флаги** OCSLogger предоставляет возможность выбирать флаги для каждого поставщика, определяя тип информации, которую можно получить из файлов трассировки.</span><span class="sxs-lookup"><span data-stu-id="34992-142">**Flags** OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="34992-143">В зависимости от поставщика можно задать следующие флаги:</span><span class="sxs-lookup"><span data-stu-id="34992-143">You can chose the following flags, based on the provider:</span></span>
    
  - <span data-ttu-id="34992-144">**TF_Connection** Предоставляет записи журнала, связанные с подключением.</span><span class="sxs-lookup"><span data-stu-id="34992-144">**TF_Connection** Provides connection-related log entries.</span></span> <span data-ttu-id="34992-145">Эти журналы включают сведения о подключениях к определенному компоненту.</span><span class="sxs-lookup"><span data-stu-id="34992-145">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="34992-146">Кроме того, может быть включен большой объем сведений сетевого уровня (то есть для компонентов без концепции подключения).</span><span class="sxs-lookup"><span data-stu-id="34992-146">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
  - <span data-ttu-id="34992-147">**TF_Security** Предоставляет все события и записи журнала, связанные с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="34992-147">**TF_Security** Provides all events/log entries related to security.</span></span> <span data-ttu-id="34992-148">Например, для SipStack, это события безопасности, такие как ошибки проверки домена и ошибки проверки подлинности и авторизации клиентов.</span><span class="sxs-lookup"><span data-stu-id="34992-148">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
  - <span data-ttu-id="34992-149">**TF_Diag** Предоставляет события диагностики, которые можно использовать для диагностики или устранения неполадок компонента.</span><span class="sxs-lookup"><span data-stu-id="34992-149">**TF_Diag** Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="34992-150">Например, для SipStack это ошибки сертификатов или ошибки/предупреждения, связанные с DNS.</span><span class="sxs-lookup"><span data-stu-id="34992-150">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
  - <span data-ttu-id="34992-151">**TF_Protocol** Предоставляет сообщения протокола, такие как сообщения SIP и объединенный кодек сообщества.</span><span class="sxs-lookup"><span data-stu-id="34992-151">**TF_Protocol** Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
  - <span data-ttu-id="34992-152">**TF_Component** Включает ведение журнала для компонентов, указанных в составе поставщиков.</span><span class="sxs-lookup"><span data-stu-id="34992-152">**TF_Component** Enables logging on the components specified as part of the providers.</span></span>
    
  - <span data-ttu-id="34992-153">**Все** Устанавливает все доступные флаги, доступные для поставщика.</span><span class="sxs-lookup"><span data-stu-id="34992-153">**All** Sets all available flags available for the provider.</span></span>
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="34992-154">Просмотр сведений о существующих поставщиках сценариев службы централизованного ведения журналов</span><span class="sxs-lookup"><span data-stu-id="34992-154">To review information about existing Centralized Logging Service scenario providers</span></span>

1. <span data-ttu-id="34992-155">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="34992-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="34992-156">Чтобы просмотреть конфигурацию существующих поставщиков, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="34992-156">To review the configuration of existing providers, type the following:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    <span data-ttu-id="34992-157">Например, чтобы просмотреть сведения о глобальном помощнике конференц-связи, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="34992-157">For example, to review information about the global conferencing attendant, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    <span data-ttu-id="34992-158">Команда отображает список поставщиков со связанными флагами, параметрами и компонентами.</span><span class="sxs-lookup"><span data-stu-id="34992-158">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="34992-159">Если отображаемой информации недостаточно или список слишком длинный для формата Windows PowerShell списка по умолчанию, можно отобразить дополнительные сведения, определив другой метод вывода.</span><span class="sxs-lookup"><span data-stu-id="34992-159">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="34992-160">Для этого выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="34992-160">To do this, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    <span data-ttu-id="34992-161">В выходе этой команды отображается каждый поставщик. Каждая запись состоит из пяти строк: имя поставщика, тип ведения журнала, уровень ведения журнала, флаги, GUID и роль.</span><span class="sxs-lookup"><span data-stu-id="34992-161">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span> 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="34992-162">Определение нового поставщика сценария службы централизованного ведения журналов</span><span class="sxs-lookup"><span data-stu-id="34992-162">To define a new Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="34992-163">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="34992-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="34992-p113">Поставщик сценария состоит из отслеживаемого компонента, используемых флагов и уровня детализации собираемых данных. Это определяется следующей командой:</span><span class="sxs-lookup"><span data-stu-id="34992-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    <span data-ttu-id="34992-166">Например, определение поставщика трассировки, которое указывает, что нужно собирать с поставщика Lyss и при каком уровне детализации, выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="34992-166">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

<span data-ttu-id="34992-167">Уровень -Level собирает сообщения о неуявных ошибках, ошибках, предупреждениях и сведениях.</span><span class="sxs-lookup"><span data-stu-id="34992-167">The -Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="34992-168">Все используемые флаги определены для поставщика Lyss и включают TF_Connection, TF_Diag и TF_Protocol.После определения переменной $LyssProvider ее можно использовать с помощью cmdlet **New-CsClsScenario** для сбора трассировок от поставщика Lyss.</span><span class="sxs-lookup"><span data-stu-id="34992-168">The flags used are all of those defined for the Lyss provider, and include TF_Connection, TF_Diag and TF_Protocol.After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="34992-169">Чтобы завершить создание и назначение поставщика новому сценарию, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="34992-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

<span data-ttu-id="34992-170">где $LyssProvider — это переменная, содержащая определенный сценарий, созданный с помощью командлета **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="34992-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="34992-171">Изменение существующего поставщика сценария службы централизованного ведения журналов</span><span class="sxs-lookup"><span data-stu-id="34992-171">To change an existing Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="34992-172">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="34992-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="34992-173">Чтобы обновить или изменить конфигурацию существующего поставщика, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="34992-173">To update or change the configuration of an existing provider, type:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    <span data-ttu-id="34992-174">Затем обновите сценарий, чтобы назначить поставщика. Введите следующее:</span><span class="sxs-lookup"><span data-stu-id="34992-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

<span data-ttu-id="34992-175">Конечный результат выполнения команды — обновление флагов и уровня поставщика назначенного для сайта сценария: Redmond/RedmondLyssInfo.</span><span class="sxs-lookup"><span data-stu-id="34992-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="34992-176">Новый сценарий можно просмотреть с помощью командлета Get-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="34992-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="34992-177">Дополнительные сведения см. в разделе [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="34992-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span>
> [!CAUTION]
> <span data-ttu-id="34992-178">**New-ClsCsProvider** не определяет допустимость флагов.</span><span class="sxs-lookup"><span data-stu-id="34992-178">**New-ClsCsProvider** does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="34992-179">Убедитесь, что названия флагов указаны верно (например, TF_DIAG или TF_CONNECTION).</span><span class="sxs-lookup"><span data-stu-id="34992-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="34992-180">Если названия флагов указаны неверно, поставщик не вернет ожидаемые сведения журналов.</span><span class="sxs-lookup"><span data-stu-id="34992-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>
  
<span data-ttu-id="34992-181">Если необходимо добавить в этот сценарий дополнительных поставщиков, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="34992-181">If you want to add additional providers to this scenario, type the following:</span></span>

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

<span data-ttu-id="34992-182">где каждый поставщик, определенный с помощью директивы Add, уже был определен с помощью процесса **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="34992-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>
### <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="34992-183">Чтобы удалить поставщика сценария</span><span class="sxs-lookup"><span data-stu-id="34992-183">To remove a scenario provider</span></span>

1. <span data-ttu-id="34992-184">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="34992-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="34992-185">Приведенные командлеты позволяют обновить существующих поставщиков и создать новых.</span><span class="sxs-lookup"><span data-stu-id="34992-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="34992-186">Чтобы удалить поставщика, необходимо использовать директиву Replace для параметра Provider в командлете **Set-CsClsScenario**.</span><span class="sxs-lookup"><span data-stu-id="34992-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="34992-187">Единственным способом полностью удалить поставщика является замена его на переопределенного поставщика того же типа с тем же именем, что выполняется с помощью директивы Update.</span><span class="sxs-lookup"><span data-stu-id="34992-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="34992-188">Например, наш поставщик LyssProvider определен с типом журнала WPP, уровнем "Отладка" и флагами TF_CONNECTION и TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="34992-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF_CONNECTION and TF_DIAG.</span></span> <span data-ttu-id="34992-189">Необходимо изменить флаги на "Все".</span><span class="sxs-lookup"><span data-stu-id="34992-189">You need to change the flags to "All".</span></span> <span data-ttu-id="34992-190">Чтобы изменить поставщика, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="34992-190">To change the provider, type the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. <span data-ttu-id="34992-191">Если необходимо полностью удалить сценарий и связанных с ним поставщиков, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="34992-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    <span data-ttu-id="34992-192">Пример:</span><span class="sxs-lookup"><span data-stu-id="34992-192">For example:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > <span data-ttu-id="34992-193">Командлет **Remove-CsClsScenario** не запрашивает подтверждения.</span><span class="sxs-lookup"><span data-stu-id="34992-193">The cmdlet **Remove-CsClsScenario** does not prompt you for confirmation.</span></span> <span data-ttu-id="34992-194">Сценарий удаляется вместе со всеми назначенными ему поставщиками.</span><span class="sxs-lookup"><span data-stu-id="34992-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="34992-195">Можно повторно создать сценарий, повторно выполнив команды, которые использовались для его исходного создания.</span><span class="sxs-lookup"><span data-stu-id="34992-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="34992-196">Процедуры восстановления удаленных сценариев или поставщиков не существует.</span><span class="sxs-lookup"><span data-stu-id="34992-196">There is no procedure to recover removed scenarios or providers.</span></span>
  
<span data-ttu-id="34992-197">При удалении сценария с помощью командлета **Remove-CsClsScenario** вы полностью удаляете сценарий из области применения.</span><span class="sxs-lookup"><span data-stu-id="34992-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="34992-198">Чтобы использовать созданные сценарии и поставщиков, которые являются частью сценария, необходимо создать новых поставщиков и назначить их новому сценарию.</span><span class="sxs-lookup"><span data-stu-id="34992-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>
## <a name="see-also"></a><span data-ttu-id="34992-199">См. также</span><span class="sxs-lookup"><span data-stu-id="34992-199">See also</span></span>

[<span data-ttu-id="34992-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="34992-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="34992-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="34992-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="34992-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="34992-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="34992-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="34992-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="34992-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="34992-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
