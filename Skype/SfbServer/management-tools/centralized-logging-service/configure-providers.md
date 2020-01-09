---
title: Настройка поставщиков для централизованной службы ведения журналов в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Сводка: сведения о том, как настроить поставщиков сценариев для централизованной службы ведения журналов в Skype для бизнеса Server 2015.'
ms.openlocfilehash: dcfa16ffa00e81153172570e67020cf287350cd9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991474"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="71be7-103">Настройка поставщиков для централизованной службы ведения журналов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="71be7-103">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="71be7-104">**Сводка:** Сведения о том, как настроить поставщиков сценариев для централизованной службы ведения журналов в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="71be7-104">**Summary:** Learn how to configure scenario providers for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="71be7-105">Концепция и настройка поставщиков в централизованной службе ведения журналов – это один из самых важных для вас моментов.</span><span class="sxs-lookup"><span data-stu-id="71be7-105">The concepts and configuration of providers in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="71be7-106">Сепровидерс прямо на серверные компоненты сервера Skype для бизнеса Server в модели трассировки Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="71be7-106">Theproviders map directly to Skype for Business Server server role components in the Skype for Business Server tracing model.</span></span> <span data-ttu-id="71be7-107">Поставщик определяет компоненты Skype для бизнеса Server 2015, которые будут отслеживаться, типы сообщений (например, неустранимые, ошибки или предупреждения), которые нужно собрать, и флаги (например, TF_Connection или TF_Diag).</span><span class="sxs-lookup"><span data-stu-id="71be7-107">The provider defines the components of a Skype for Business Server 2015 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF_Connection or TF_Diag).</span></span> <span data-ttu-id="71be7-108">Поставщики — это отслеживаемые компоненты, которые входят в каждую роль сервера Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="71be7-108">Providers are the traceable components in each Skype for Business Server server role.</span></span> <span data-ttu-id="71be7-109">С их помощью можно определить уровень и тип трассировки компонентов (например, S4, SIPStack, IM и Presence).</span><span class="sxs-lookup"><span data-stu-id="71be7-109">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="71be7-110">Определенный поставщик используется в сценарии для группировки всех поставщиков в логическую коллекцию, описывающую состояние определенной проблемы.</span><span class="sxs-lookup"><span data-stu-id="71be7-110">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>
  
<span data-ttu-id="71be7-111">Для запуска функций централизованной службы ведения журналов с помощью командной консоли Skype для бизнеса Server вы должны быть членами либо группами безопасности Ксадминистратор, либо Кссерверадминистратор на основе ролей, а также настраиваемой ролью RBAC, которая один из этих двух групп.</span><span class="sxs-lookup"><span data-stu-id="71be7-111">To run the Centralized Logging Service functions using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="71be7-112">Чтобы возвратить список всех ролей управления доступом на основе ролей (RBAC), которым был назначен этот командлет (включая любые пользовательские роли RBAC, созданные пользователем), выполните следующую команду в командной консоли управления Skype для бизнеса Server или Windows PowerShell. дачу</span><span class="sxs-lookup"><span data-stu-id="71be7-112">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="71be7-113">Например:</span><span class="sxs-lookup"><span data-stu-id="71be7-113">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="71be7-114">Остальная часть данной темы посвящена определению поставщиков, изменению поставщика и компонентов поставщика, упрощающих поиск и устранение неисправностей.</span><span class="sxs-lookup"><span data-stu-id="71be7-114">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="71be7-115">Существует два способа вывести централизованные команды службы ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="71be7-115">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="71be7-116">Вы можете использовать файл CLSController.exe, который по умолчанию расположен в каталоге C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="71be7-116">You can use the CLSController.exe that is located, by default, in the directory C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span></span> <span data-ttu-id="71be7-117">Кроме того, вы можете использовать командную консоль сервера Skype для бизнеса, чтобы выпустить команды Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71be7-117">Or, you can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="71be7-118">С помощью Windows PowerShell вы можете определять новых поставщиков в сеансах ведения журнала и получать полный контроль над их созданием, их сбором и уровнем собираемых данных.</span><span class="sxs-lookup"><span data-stu-id="71be7-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="71be7-p104">Как уже упоминалось, поставщики являются очень мощным средством. Однако сценарии имеют большее значение, так как объединяют в себе все данные, необходимые для определения и выполнения трассировок компонентов, представленных поставщиками. Сценарии, которые являются коллекциями поставщиков, можно сравнить с выполнением пакетного файла, содержащего сотни команд, для сбора большого объема данных, что отличается от выполнения сотен команд по одной в командной строке.</span><span class="sxs-lookup"><span data-stu-id="71be7-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span> 
  
<span data-ttu-id="71be7-122">Вместо того, чтобы потребовать подробной информации о поставщиках, Служба централизованного ведения журналов предоставляет ряд сценариев, которые уже определены для вас.</span><span class="sxs-lookup"><span data-stu-id="71be7-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="71be7-123">Предоставленные сценарии покрывают большое количество различных проблем и неполадок, которые могут возникнуть.</span><span class="sxs-lookup"><span data-stu-id="71be7-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="71be7-124">В редких случаях может понадобиться создать и определить поставщиков и назначить их в сценарии.</span><span class="sxs-lookup"><span data-stu-id="71be7-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="71be7-125">Настоятельно рекомендуется ознакомиться с каждым предоставленным сценарием, прежде чем создавать новых поставщиков и сценарии.</span><span class="sxs-lookup"><span data-stu-id="71be7-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="71be7-126">Хотя здесь предоставляются сведения о создании поставщиков, чтобы вы могли ознакомиться с тем, как сценарии используют элементы поставщиков для сбора данных трассировок, сведения о самих поставщиках в настоящее время не предоставлены.</span><span class="sxs-lookup"><span data-stu-id="71be7-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span> 
  
<span data-ttu-id="71be7-127">Функция [централизованного ведения журналов в Skype для бизнеса 2015](centralized-logging-service.md)— ключевые элементы определения поставщика для использования в сценарии.</span><span class="sxs-lookup"><span data-stu-id="71be7-127">Introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>
  
- <span data-ttu-id="71be7-128">**Поставщики услуг** Если вы знакомы с Окслогжер, поставщики — это компоненты, которые вы указываете, чтобы сообщить Окслогжер о том, что ядро трассировки должно собирать журналы.</span><span class="sxs-lookup"><span data-stu-id="71be7-128">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="71be7-129">Поставщики — это те же компоненты, а во многих случаях их имя совпадает с компонентами в OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="71be7-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="71be7-130">Если вы не знакомы с Окслогжер, поставщики — это компоненты, специфичные для серверной роли, из которой Служба централизованного ведения журналов может собирать журналы.</span><span class="sxs-lookup"><span data-stu-id="71be7-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="71be7-131">В случае централизованной службы ведения журналов Клсажент — это архитектура централизованной службы ведения журналов, которая выполняет трассировку компонентов, которые вы определили в конфигурации провайдеров.</span><span class="sxs-lookup"><span data-stu-id="71be7-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>
    
- <span data-ttu-id="71be7-132">**Уровни ведения журнала** Окслогжер предоставил возможность выбрать количество уровней детализации для собираемых данных.</span><span class="sxs-lookup"><span data-stu-id="71be7-132">**Logging levels** OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="71be7-133">Эта функция является неотъемлемой частью централизованной службы ведения журналов и сценариев и определяется параметром **Type** .</span><span class="sxs-lookup"><span data-stu-id="71be7-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="71be7-134">Можно выбрать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="71be7-134">You can choose from the following:</span></span>
    
  - <span data-ttu-id="71be7-135">**Все** Собирает сообщения трассировки для типа "неустранимые", "ошибка", "предупреждение", "подробный" и "сведения об отладке" в журнал для определенного поставщика.</span><span class="sxs-lookup"><span data-stu-id="71be7-135">**All** Collects trace messages of type fatal, error, warning, verbose, and debug info to the log for the defined provider.</span></span>
    
  - <span data-ttu-id="71be7-136">**Критическая** ошибка Собирает только сообщения трассировки, определенные как неустранимые.</span><span class="sxs-lookup"><span data-stu-id="71be7-136">**Fatal** Collects only the trace messages defined as "Fatal."</span></span>
    
  - <span data-ttu-id="71be7-137">**Ошибка** Собирает только сообщения трассировки, определенные как "ошибка" или "критическая".</span><span class="sxs-lookup"><span data-stu-id="71be7-137">**Error** Collects only the trace messages defined as "Error" or "Fatal."</span></span>
    
  - <span data-ttu-id="71be7-138">**Предупреждение** Собираются только сообщения трассировки типа "предупреждение", "ошибка" и "Неустранимая".</span><span class="sxs-lookup"><span data-stu-id="71be7-138">**Warning** Collects only the trace messages of type "Warning," "Error" and "Fatal."</span></span>
    
  - <span data-ttu-id="71be7-139">**Сведения** Собирает только сообщения трассировки, указывающие информационное сообщение для определенного поставщика, а также неустранимые, ошибки и предупреждающие сообщения.</span><span class="sxs-lookup"><span data-stu-id="71be7-139">**Info** Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
  - <span data-ttu-id="71be7-140">**Подробный** Собирает все сообщения трассировки типа "Неустранимая", "ошибка", "предупреждение" и "подробный" для определенного поставщика.</span><span class="sxs-lookup"><span data-stu-id="71be7-140">**Verbose** Collects all trace messages of type fatal, error, warning and verbose for the defined provider.</span></span>
    
  - <span data-ttu-id="71be7-141">**Отладка** , по сути, является эквивалентом ALL — собирает данные о фатальных ошибках, ошибки, предупреждениях, данных, подробных и отладочных значениях для определенного поставщика.</span><span class="sxs-lookup"><span data-stu-id="71be7-141">**Debug** this is essentially an equivalent of 'All' - collects traces of type Fatal, Error, Warning, Info, Verbose and Debug for the defined provider.</span></span>
    
- <span data-ttu-id="71be7-142">**Flags (флаги** ) Окслогжер предоставил вариант выбора флагов для каждого поставщика, который определил тип данных, которые можно извлечь из файлов трассировки.</span><span class="sxs-lookup"><span data-stu-id="71be7-142">**Flags** OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="71be7-143">В зависимости от поставщика можно задать следующие флаги:</span><span class="sxs-lookup"><span data-stu-id="71be7-143">You can chose the following flags, based on the provider:</span></span>
    
  - <span data-ttu-id="71be7-144">**TF_Connection** Предоставляет записи журнала, связанные с подключением.</span><span class="sxs-lookup"><span data-stu-id="71be7-144">**TF_Connection** Provides connection-related log entries.</span></span> <span data-ttu-id="71be7-145">Эти журналы включают сведения о подключениях к определенному компоненту.</span><span class="sxs-lookup"><span data-stu-id="71be7-145">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="71be7-146">Кроме того, может быть включен большой объем сведений сетевого уровня (то есть для компонентов без концепции подключения).</span><span class="sxs-lookup"><span data-stu-id="71be7-146">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
  - <span data-ttu-id="71be7-147">**TF_Security** Предоставляет все события и записи журнала, связанные с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="71be7-147">**TF_Security** Provides all events/log entries related to security.</span></span> <span data-ttu-id="71be7-148">Например, для SipStack, это события безопасности, такие как ошибки проверки домена и ошибки проверки подлинности и авторизации клиентов.</span><span class="sxs-lookup"><span data-stu-id="71be7-148">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
  - <span data-ttu-id="71be7-149">**TF_Diag** Предоставляет события диагностики, которые можно использовать для диагностики и устранения неполадок в компоненте.</span><span class="sxs-lookup"><span data-stu-id="71be7-149">**TF_Diag** Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="71be7-150">Например, для SipStack это ошибки сертификатов или ошибки/предупреждения, связанные с DNS.</span><span class="sxs-lookup"><span data-stu-id="71be7-150">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
  - <span data-ttu-id="71be7-151">**TF_Protocol** Предоставляет сообщения протоколов, такие как SIP и Объединенные кодеки кодеков для сообщества.</span><span class="sxs-lookup"><span data-stu-id="71be7-151">**TF_Protocol** Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
  - <span data-ttu-id="71be7-152">**TF_Component** Включает ведение журнала для компонентов, указанных в составе поставщиков.</span><span class="sxs-lookup"><span data-stu-id="71be7-152">**TF_Component** Enables logging on the components specified as part of the providers.</span></span>
    
  - <span data-ttu-id="71be7-153">**Все** Задает все доступные флаги, доступные для поставщика.</span><span class="sxs-lookup"><span data-stu-id="71be7-153">**All** Sets all available flags available for the provider.</span></span>
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="71be7-154">Просмотр сведений о существующих поставщиках сценариев централизованной службы ведения журнала</span><span class="sxs-lookup"><span data-stu-id="71be7-154">To review information about existing Centralized Logging Service scenario providers</span></span>

1. <span data-ttu-id="71be7-155">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="71be7-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="71be7-156">Чтобы просмотреть конфигурацию существующих поставщиков, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="71be7-156">To review the configuration of existing providers, type the following:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    <span data-ttu-id="71be7-157">Например, чтобы просмотреть сведения о глобальном помощнике конференц-связи, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="71be7-157">For example, to review information about the global conferencing attendant, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    <span data-ttu-id="71be7-158">Команда отображает список поставщиков со связанными флагами, параметрами и компонентами.</span><span class="sxs-lookup"><span data-stu-id="71be7-158">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="71be7-159">Если отображаемая информация не является достаточной или список слишком велик для стандартного формата списка Windows PowerShell, вы можете отобразить дополнительные сведения, определив другой метод вывода.</span><span class="sxs-lookup"><span data-stu-id="71be7-159">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="71be7-160">Для этого выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="71be7-160">To do this, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    <span data-ttu-id="71be7-161">В выходе этой команды отображается каждый поставщик. Каждая запись состоит из пяти строк: имя поставщика, тип ведения журнала, уровень ведения журнала, флаги, GUID и роль.</span><span class="sxs-lookup"><span data-stu-id="71be7-161">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span> 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="71be7-162">Определение нового поставщика сценария для централизованной службы ведения журнала</span><span class="sxs-lookup"><span data-stu-id="71be7-162">To define a new Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="71be7-163">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="71be7-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="71be7-p113">Поставщик сценария состоит из отслеживаемого компонента, используемых флагов и уровня детализации собираемых данных. Это определяется следующей командой:</span><span class="sxs-lookup"><span data-stu-id="71be7-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    <span data-ttu-id="71be7-166">Например, определение поставщика трассировки, которое указывает, что нужно собирать с поставщика Lyss и при каком уровне детализации, выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="71be7-166">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

<span data-ttu-id="71be7-167">На уровне собраны неустранимые, ошибки, предупреждения и информационные сообщения.</span><span class="sxs-lookup"><span data-stu-id="71be7-167">The -Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="71be7-168">Все используемые флаги определены для поставщика Лисс и включают TF_Connection, TF_Diag и TF_Protocol. После определения переменной $LyssProvider ее можно использовать с командлетом **New-ксклссценарио** для сбора трассировок из поставщика Лисс.</span><span class="sxs-lookup"><span data-stu-id="71be7-168">The flags used are all of those defined for the Lyss provider, and include TF_Connection, TF_Diag and TF_Protocol.After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="71be7-169">Чтобы завершить создание и назначение поставщика новому сценарию, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="71be7-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

<span data-ttu-id="71be7-170">где $LyssProvider — это переменная, содержащая определенный сценарий, созданный с помощью командлета **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="71be7-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="71be7-171">Изменение существующего поставщика сценариев для централизованной службы ведения журнала</span><span class="sxs-lookup"><span data-stu-id="71be7-171">To change an existing Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="71be7-172">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="71be7-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="71be7-173">Чтобы обновить или изменить конфигурацию существующего поставщика, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="71be7-173">To update or change the configuration of an existing provider, type:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    <span data-ttu-id="71be7-174">Затем обновите сценарий, чтобы назначить поставщика. Введите следующее:</span><span class="sxs-lookup"><span data-stu-id="71be7-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

<span data-ttu-id="71be7-p115">Конечный результат выполнения команды — обновление флагов и уровня поставщика назначенного для сайта сценария: Redmond/RedmondLyssInfo. Новый сценарий можно просмотреть с помощью командлета Get-CsClsScenario. Дополнительные сведения см. в разделе [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="71be7-p115">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it. You can view the new scenario by using Get-CsClsScenario. For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span>
> [!CAUTION]
> <span data-ttu-id="71be7-178">**New-ClsCsProvider** не определяет допустимость флагов.</span><span class="sxs-lookup"><span data-stu-id="71be7-178">**New-ClsCsProvider** does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="71be7-179">Убедитесь, что названия флагов указаны верно (например, TF_DIAG или TF_CONNECTION).</span><span class="sxs-lookup"><span data-stu-id="71be7-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="71be7-180">Если названия флагов указаны неверно, поставщик не вернет ожидаемые сведения журналов.</span><span class="sxs-lookup"><span data-stu-id="71be7-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>
  
<span data-ttu-id="71be7-181">Если необходимо добавить в этот сценарий дополнительных поставщиков, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="71be7-181">If you want to add additional providers to this scenario, type the following:</span></span>

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

<span data-ttu-id="71be7-182">где каждый поставщик, определенный с помощью директивы Add, уже был определен с помощью процесса **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="71be7-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>
### <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="71be7-183">Удаление поставщика сценария</span><span class="sxs-lookup"><span data-stu-id="71be7-183">To remove a scenario provider</span></span>

1. <span data-ttu-id="71be7-184">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="71be7-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="71be7-185">Приведенные командлеты позволяют обновить существующих поставщиков и создать новых.</span><span class="sxs-lookup"><span data-stu-id="71be7-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="71be7-186">Чтобы удалить поставщика, необходимо использовать директиву Replace для параметра Provider в командлете **Set-CsClsScenario**.</span><span class="sxs-lookup"><span data-stu-id="71be7-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="71be7-187">Единственным способом полностью удалить поставщика является замена его на переопределенного поставщика того же типа с тем же именем, что выполняется с помощью директивы Update.</span><span class="sxs-lookup"><span data-stu-id="71be7-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="71be7-188">Например, наш поставщик LyssProvider определен с типом журнала WPP, уровнем "Отладка" и флагами TF_CONNECTION и TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="71be7-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF_CONNECTION and TF_DIAG.</span></span> <span data-ttu-id="71be7-189">Вы должны изменить флаги на "все".</span><span class="sxs-lookup"><span data-stu-id="71be7-189">You need to change the flags to "All".</span></span> <span data-ttu-id="71be7-190">Чтобы изменить поставщика, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="71be7-190">To change the provider, type the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. <span data-ttu-id="71be7-191">Если необходимо полностью удалить сценарий и связанных с ним поставщиков, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="71be7-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    <span data-ttu-id="71be7-192">Например:</span><span class="sxs-lookup"><span data-stu-id="71be7-192">For example:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > <span data-ttu-id="71be7-193">Командлет **Remove-CsClsScenario** не запрашивает подтверждения.</span><span class="sxs-lookup"><span data-stu-id="71be7-193">The cmdlet **Remove-CsClsScenario** does not prompt you for confirmation.</span></span> <span data-ttu-id="71be7-194">Сценарий удаляется вместе со всеми назначенными ему поставщиками.</span><span class="sxs-lookup"><span data-stu-id="71be7-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="71be7-195">Можно повторно создать сценарий, повторно выполнив команды, которые использовались для его исходного создания.</span><span class="sxs-lookup"><span data-stu-id="71be7-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="71be7-196">Процедуры восстановления удаленных сценариев или поставщиков не существует.</span><span class="sxs-lookup"><span data-stu-id="71be7-196">There is no procedure to recover removed scenarios or providers.</span></span>
  
<span data-ttu-id="71be7-197">При удалении сценария с помощью командлета **Remove-CsClsScenario** вы полностью удаляете сценарий из области применения.</span><span class="sxs-lookup"><span data-stu-id="71be7-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="71be7-198">Чтобы использовать созданные сценарии и поставщиков, которые являются частью сценария, необходимо создать новых поставщиков и назначить их новому сценарию.</span><span class="sxs-lookup"><span data-stu-id="71be7-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>
## <a name="see-also"></a><span data-ttu-id="71be7-199">См. также</span><span class="sxs-lookup"><span data-stu-id="71be7-199">See also</span></span>

[<span data-ttu-id="71be7-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="71be7-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="71be7-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="71be7-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="71be7-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="71be7-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="71be7-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="71be7-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="71be7-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="71be7-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
