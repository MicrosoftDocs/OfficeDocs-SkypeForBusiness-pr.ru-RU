---
title: 'Lync Server 2013: Настройка поставщиков для централизованной службы ведения журналов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ba3d903b1d4a33048f5a66738897408c36a94e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="0551e-102">Настройка поставщиков для централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0551e-102">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0551e-103">_**Последнее изменение темы:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="0551e-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="0551e-104">Основные понятия и настройка *поставщиков* централизованной службы ведения журналов — это одна из самых важных.</span><span class="sxs-lookup"><span data-stu-id="0551e-104">The concepts and configuration of *providers* in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="0551e-105">*Поставщики* напрямую сопоставляются с компонентами роли сервера Lync Server в модели трассировки Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0551e-105">The *providers* map directly to Lync Server server role components in the Lync Server tracing model.</span></span> <span data-ttu-id="0551e-106">Поставщик определяет компоненты Lync Server 2013, которые будут трассироваться, тип сообщений (например, Неустранимая ошибка, ошибка или предупреждение) и флаги (например, TF\_Connection или TF\_diag).</span><span class="sxs-lookup"><span data-stu-id="0551e-106">The provider defines the components of a Lync Server 2013 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF\_Connection or TF\_Diag).</span></span> <span data-ttu-id="0551e-107">Поставщики — это компоненты для трассировки в каждой роли сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0551e-107">Providers are the traceable components in each Lync Server server role.</span></span> <span data-ttu-id="0551e-108">С помощью поставщиков вы определяете уровень и тип трассировки компонентов (например, S4, SIPStack, мгновенных сообщений и сведений о присутствии).</span><span class="sxs-lookup"><span data-stu-id="0551e-108">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="0551e-109">Определенный поставщик используется в сценарии для группирования всех поставщиков для указанной логической коллекции, которые относятся к определенному условию проблемы.</span><span class="sxs-lookup"><span data-stu-id="0551e-109">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>

<span data-ttu-id="0551e-110">Для запуска функций централизованной службы ведения журналов с помощью командной консоли Lync Server необходимо быть членом группы безопасности CsAdministrator или CsServerAdministrator с управлением доступом на основе ролей (RBAC) или настраиваемой роли RBAC, содержащей любой из Эти две группы.</span><span class="sxs-lookup"><span data-stu-id="0551e-110">To run the Centralized Logging Service functions using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="0551e-111">Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните следующую команду в командной консоли Lync Server или в командной строке Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0551e-111">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="0551e-112">Пример:</span><span class="sxs-lookup"><span data-stu-id="0551e-112">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="0551e-113">Оставшаяся часть этого раздела посвящена способам определения поставщиков, изменению поставщика и определениям, содержащимся в определении поставщика для оптимизации устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="0551e-113">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="0551e-114">Существует два способа выдача команд службы централизованного ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="0551e-114">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="0551e-115">Вы можете\\использовать файл CLSController. exe, расположенный по умолчанию, в папке C: Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="0551e-115">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="0551e-116">Вы также можете использовать командную консоль Lync Server для выполнения команд Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0551e-116">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="0551e-117">Важное отличие заключается в том, что при использовании CLSController. exe в командной строке предусмотрен ограниченный выбор сценариев, в которых поставщики уже определены и не могут быть изменены, но вы можете определить уровень ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="0551e-117">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available in which the providers are already defined and are not changeable, but you can define the log level.</span></span> <span data-ttu-id="0551e-118">С помощью Windows PowerShell вы можете определить новых поставщиков для использования в сеансах ведения журнала и получить полный контроль над их созданием, тем, что они собирают, и на каком уровне они собирают данные.</span><span class="sxs-lookup"><span data-stu-id="0551e-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="0551e-p104">Как уже упоминалось, поставщики являются очень мощным средством. Однако сценарии имеют большее значение, так как объединяют в себе все данные, необходимые для определения и выполнения трассировок компонентов, представленных поставщиками. Сценарии, которые являются коллекциями поставщиков, можно сравнить с выполнением пакетного файла, содержащего сотни команд, для сбора большого объема данных, что отличается от выполнения сотен команд по одной в командной строке.</span><span class="sxs-lookup"><span data-stu-id="0551e-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span><BR><span data-ttu-id="0551e-122">Вместо того чтобы потребовать глубокой детализации сведений о поставщиках, Служба централизованного ведения журналов предоставляет ряд сценариев, которые уже определены для вас.</span><span class="sxs-lookup"><span data-stu-id="0551e-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="0551e-123">Предоставленные сценарии покрывают большое количество различных проблем и неполадок, которые могут возникнуть.</span><span class="sxs-lookup"><span data-stu-id="0551e-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="0551e-124">В редких случаях может понадобиться создать и определить поставщиков и назначить их в сценарии.</span><span class="sxs-lookup"><span data-stu-id="0551e-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="0551e-125">Настоятельно рекомендуется ознакомиться с каждым предоставленным сценарием, прежде чем создавать новых поставщиков и сценарии.</span><span class="sxs-lookup"><span data-stu-id="0551e-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="0551e-126">Хотя здесь предоставляются сведения о создании поставщиков, чтобы вы могли ознакомиться с тем, как сценарии используют элементы поставщиков для сбора данных трассировок, сведения о самих поставщиках в настоящее время не предоставлены.</span><span class="sxs-lookup"><span data-stu-id="0551e-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span>



</div>

<span data-ttu-id="0551e-127">В статье [Обзор централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)ключевые элементы определения поставщика для использования в сценарии:</span><span class="sxs-lookup"><span data-stu-id="0551e-127">Introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>

  - <span data-ttu-id="0551e-128">**Поставщики**   . Если вы знакомы с OCSLogger, поставщики — это компоненты, которые указывают OCSLogger, из чего система трассировки должна собирать журналы.</span><span class="sxs-lookup"><span data-stu-id="0551e-128">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="0551e-129">Поставщики — это те же компоненты, а во многих случаях их имя совпадает с компонентами в OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="0551e-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="0551e-130">Если вы не знакомы с OCSLogger, поставщики — это компоненты, зависящие от роли сервера, из которых Служба централизованного ведения журналов может собирать журналы.</span><span class="sxs-lookup"><span data-stu-id="0551e-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="0551e-131">В случае централизованной службы ведения журналов CLSAgent — это архитектурная часть централизованной службы ведения журналов, которая выполняет трассировку компонентов, которые вы определили в конфигурации поставщиков.</span><span class="sxs-lookup"><span data-stu-id="0551e-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>

  - <span data-ttu-id="0551e-132">**Уровни ведения журнала**   OCSLogger предоставил возможность выбрать количество уровней детализации собранных данных.</span><span class="sxs-lookup"><span data-stu-id="0551e-132">**Logging levels**   OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="0551e-133">Эта функция является неотъемлемой частью централизованной службы ведения журналов и сценариев и определяется с помощью параметра **Type** .</span><span class="sxs-lookup"><span data-stu-id="0551e-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="0551e-134">Вы можете выбрать следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="0551e-134">You can choose from the following:</span></span>
    
      - <span data-ttu-id="0551e-135">**ALL**   собирает сообщения трассировки типа "Неустранимая ошибка", "ошибка", "предупреждение" и "сведения" в журнал для определенного поставщика.</span><span class="sxs-lookup"><span data-stu-id="0551e-135">**All**   Collects trace messages of type fatal, error, warning, and info to the log for the defined provider.</span></span>
    
      - <span data-ttu-id="0551e-136">**Неустранимая**   ошибка собирает только сообщения трассировки, указывающие на сбой определенного поставщика.</span><span class="sxs-lookup"><span data-stu-id="0551e-136">**Fatal**   Collects only the trace messages that indicate a failure for the defined provider.</span></span>
    
      - <span data-ttu-id="0551e-137">**Ошибка**   собирает только сообщения трассировки, указывающие на ошибку определенного поставщика, а также неустранимые сообщения.</span><span class="sxs-lookup"><span data-stu-id="0551e-137">**Error**   Collects only the trace messages that indicate an error for the defined provider, plus fatal messages.</span></span>
    
      - <span data-ttu-id="0551e-138">**Предупреждение**   собирает только сообщения трассировки, указывающие предупреждение для определенного поставщика, а также неустранимые сообщения и сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="0551e-138">**Warning**   Collects only the trace messages that indicate a warning for the defined provider, plus fatal and error messages.</span></span>
    
      - <span data-ttu-id="0551e-139">**Info**   собирает только сообщения трассировки, указывающие информационное сообщение для определенного поставщика, а также неустранимые, ошибочные и предупреждающие сообщения.</span><span class="sxs-lookup"><span data-stu-id="0551e-139">**Info**   Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
      - <span data-ttu-id="0551e-140">**Verbose**   собирает все сообщения трассировки типа "Неустранимая ошибка", "ошибка", "предупреждение" и "информация" для определенного поставщика.</span><span class="sxs-lookup"><span data-stu-id="0551e-140">**Verbose**   Collects all trace messages of type fatal, error, warning and info for the defined provider.</span></span>

  - <span data-ttu-id="0551e-141">**Flags**   OCSLogger предоставляет возможность выбора флагов для каждого поставщика, определяющего тип данных, которые можно получить из файлов трассировки.</span><span class="sxs-lookup"><span data-stu-id="0551e-141">**Flags**   OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="0551e-142">В зависимости от поставщика можно задать следующие флаги:</span><span class="sxs-lookup"><span data-stu-id="0551e-142">You can chose the following flags, based on the provider:</span></span>
    
      - <span data-ttu-id="0551e-143">**TF\_Connection**   предоставляет записи журнала, связанные с подключением.</span><span class="sxs-lookup"><span data-stu-id="0551e-143">**TF\_Connection**   Provides connection-related log entries.</span></span> <span data-ttu-id="0551e-144">Эти журналы включают сведения о подключениях к определенному компоненту.</span><span class="sxs-lookup"><span data-stu-id="0551e-144">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="0551e-145">Кроме того, может быть включен большой объем сведений сетевого уровня (то есть для компонентов без концепции подключения).</span><span class="sxs-lookup"><span data-stu-id="0551e-145">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
      - <span data-ttu-id="0551e-146">**TF\_Security**   предоставляет все события и записи журнала, связанные с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="0551e-146">**TF\_Security**   Provides all events/log entries related to security.</span></span> <span data-ttu-id="0551e-147">Например, для SipStack, это события безопасности, такие как ошибки проверки домена и ошибки проверки подлинности и авторизации клиентов.</span><span class="sxs-lookup"><span data-stu-id="0551e-147">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
      - <span data-ttu-id="0551e-148">**TF\_DIAG**   предоставляет события диагностики, которые можно использовать для диагностики или устранения неполадок в компоненте.</span><span class="sxs-lookup"><span data-stu-id="0551e-148">**TF\_Diag**   Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="0551e-149">Например, для SipStack это ошибки сертификатов или ошибки/предупреждения, связанные с DNS.</span><span class="sxs-lookup"><span data-stu-id="0551e-149">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
      - <span data-ttu-id="0551e-150">**TF\_Protocol**   предоставляет сообщения протокола, такие как SIP и Объединенные сообщения с пакетным кодеком сообщества.</span><span class="sxs-lookup"><span data-stu-id="0551e-150">**TF\_Protocol**   Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
      - <span data-ttu-id="0551e-151">**Компонент\_**   TF включает ведение журнала для компонентов, указанных как часть поставщиков.</span><span class="sxs-lookup"><span data-stu-id="0551e-151">**TF\_Component**   Enables logging on the components specified as part of the providers.</span></span>
    
      - <span data-ttu-id="0551e-152">**Все**   задает все доступные флаги, доступные для поставщика.</span><span class="sxs-lookup"><span data-stu-id="0551e-152">**All**   Sets all available flags available for the provider.</span></span>

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="0551e-153">Просмотр сведений о существующих поставщиках сценариев централизованной службы ведения журналов</span><span class="sxs-lookup"><span data-stu-id="0551e-153">To review information about existing Centralized Logging Service scenario providers</span></span>

1.  <span data-ttu-id="0551e-154">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0551e-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0551e-155">Чтобы просмотреть конфигурацию существующих поставщиков, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0551e-155">To review the configuration of existing providers, type the following:</span></span>
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    <span data-ttu-id="0551e-156">Например, чтобы просмотреть сведения о глобальном помощнике конференц-связи, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="0551e-156">For example, to review information about the global conferencing attendant, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA"
    
    <span data-ttu-id="0551e-157">Команда отображает список поставщиков со связанными флагами, параметрами и компонентами.</span><span class="sxs-lookup"><span data-stu-id="0551e-157">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="0551e-158">Если отображаемая информация не хватает или слишком длинная длина списка для стандартного формата списка Windows PowerShell, можно отобразить дополнительные сведения, определив другой метод вывода.</span><span class="sxs-lookup"><span data-stu-id="0551e-158">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="0551e-159">Для этого выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0551e-159">To do this, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    <span data-ttu-id="0551e-160">В выходе этой команды отображается каждый поставщик. Каждая запись состоит из пяти строк: имя поставщика, тип ведения журнала, уровень ведения журнала, флаги, GUID и роль.</span><span class="sxs-lookup"><span data-stu-id="0551e-160">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span>

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="0551e-161">Определение нового поставщика сценария для централизованной службы ведения журналов</span><span class="sxs-lookup"><span data-stu-id="0551e-161">To define a new Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="0551e-162">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0551e-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0551e-p113">Поставщик сценария состоит из отслеживаемого компонента, используемых флагов и уровня детализации собираемых данных. Это определяется следующей командой:</span><span class="sxs-lookup"><span data-stu-id="0551e-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    <span data-ttu-id="0551e-165">Например, определение поставщика трассировки, которое указывает, что нужно собирать с поставщика Lyss и при каком уровне детализации, выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0551e-165">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

<span data-ttu-id="0551e-166">Параметр –Level указывает сбор сообщений типа неустранимая ошибка, ошибка, предупреждение и информация.</span><span class="sxs-lookup"><span data-stu-id="0551e-166">The –Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="0551e-167">Используются все флажки, определенные для поставщика Lyss и включающие подключения TF\_, TF\_diag и TF\_Protocol.</span><span class="sxs-lookup"><span data-stu-id="0551e-167">The flags used are all of those defined for the Lyss provider, and include TF\_Connection, TF\_Diag and TF\_Protocol.</span></span>

<span data-ttu-id="0551e-168">После определения переменной $LyssProvider можно использовать ее в командлете **New-CsClsScenario** для сбора трассировок с поставщика Lyss.</span><span class="sxs-lookup"><span data-stu-id="0551e-168">After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="0551e-169">Чтобы завершить создание и назначение поставщика новому сценарию, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0551e-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="0551e-170">где $LyssProvider — это переменная, содержащая определенный сценарий, созданный с помощью командлета **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="0551e-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="0551e-171">Изменение существующего поставщика сценариев централизованной службы ведения журналов</span><span class="sxs-lookup"><span data-stu-id="0551e-171">To change an existing Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="0551e-172">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0551e-172">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0551e-173">Чтобы обновить или изменить конфигурацию существующего поставщика, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0551e-173">To update or change the configuration of an existing provider, type:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    <span data-ttu-id="0551e-174">Затем обновите сценарий, чтобы назначить поставщика. Введите следующее:</span><span class="sxs-lookup"><span data-stu-id="0551e-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="0551e-175">Конечный результат выполнения команды — обновление флагов и уровня поставщика назначенного для сайта сценария: Redmond/RedmondLyssInfo.</span><span class="sxs-lookup"><span data-stu-id="0551e-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="0551e-176">Новый сценарий можно просмотреть с помощью командлета Get-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="0551e-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="0551e-177">Дополнительные сведения см. в разделе [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span><span class="sxs-lookup"><span data-stu-id="0551e-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span></span>

<div class="">


> [!WARNING]  
> <span data-ttu-id="0551e-178"><STRONG>New-ClsCsProvider</STRONG> не определяет допустимость флагов.</span><span class="sxs-lookup"><span data-stu-id="0551e-178"><STRONG>New-ClsCsProvider</STRONG> does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="0551e-179">Убедитесь, что названия флагов указаны верно (например, TF_DIAG или TF_CONNECTION).</span><span class="sxs-lookup"><span data-stu-id="0551e-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="0551e-180">Если названия флагов указаны неверно, поставщик не вернет ожидаемые сведения журналов.</span><span class="sxs-lookup"><span data-stu-id="0551e-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>



</div>

<span data-ttu-id="0551e-181">Если необходимо добавить в этот сценарий дополнительных поставщиков, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0551e-181">If you want to add additional providers to this scenario, type the following:</span></span>

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

<span data-ttu-id="0551e-182">где каждый поставщик, определенный с помощью директивы Add, уже был определен с помощью процесса **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="0551e-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="0551e-183">Чтобы удалить поставщика сценария</span><span class="sxs-lookup"><span data-stu-id="0551e-183">To remove a scenario provider</span></span>

1.  <span data-ttu-id="0551e-184">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0551e-184">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0551e-185">Приведенные командлеты позволяют обновить существующих поставщиков и создать новых.</span><span class="sxs-lookup"><span data-stu-id="0551e-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="0551e-186">Чтобы удалить поставщика, необходимо использовать директиву Replace для параметра Provider в командлете **Set-CsClsScenario**.</span><span class="sxs-lookup"><span data-stu-id="0551e-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="0551e-187">Единственным способом полностью удалить поставщика является замена его на переопределенного поставщика того же типа с тем же именем, что выполняется с помощью директивы Update.</span><span class="sxs-lookup"><span data-stu-id="0551e-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="0551e-188">Например, наш поставщик LyssProvider определяется с помощью конвейера WPP в качестве типа журнала, уровня "Отладка", а флаги\_Set — TF\_Connection и TF DIAG.</span><span class="sxs-lookup"><span data-stu-id="0551e-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF\_CONNECTION and TF\_DIAG.</span></span> <span data-ttu-id="0551e-189">Необходимо изменить флаги на All.</span><span class="sxs-lookup"><span data-stu-id="0551e-189">You need to change the flags to “All”.</span></span> <span data-ttu-id="0551e-190">Чтобы изменить поставщика, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0551e-190">To change the provider, type the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  <span data-ttu-id="0551e-191">Если необходимо полностью удалить сценарий и связанных с ним поставщиков, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0551e-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    <span data-ttu-id="0551e-192">Пример:</span><span class="sxs-lookup"><span data-stu-id="0551e-192">For example:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="0551e-193">Командлет <STRONG>Remove-CsClsScenario</STRONG> не запрашивает подтверждения.</span><span class="sxs-lookup"><span data-stu-id="0551e-193">The cmdlet <STRONG>Remove-CsClsScenario</STRONG> does not prompt you for confirmation.</span></span> <span data-ttu-id="0551e-194">Сценарий удаляется вместе со всеми назначенными ему поставщиками.</span><span class="sxs-lookup"><span data-stu-id="0551e-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="0551e-195">Можно повторно создать сценарий, повторно выполнив команды, которые использовались для его исходного создания.</span><span class="sxs-lookup"><span data-stu-id="0551e-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="0551e-196">Процедуры восстановления удаленных сценариев или поставщиков не существует.</span><span class="sxs-lookup"><span data-stu-id="0551e-196">There is no procedure to recover removed scenarios or providers.</span></span>

    
    </div>

<span data-ttu-id="0551e-197">При удалении сценария с помощью командлета **Remove-CsClsScenario** вы полностью удаляете сценарий из области применения.</span><span class="sxs-lookup"><span data-stu-id="0551e-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="0551e-198">Чтобы использовать созданные сценарии и поставщиков, которые являются частью сценария, необходимо создать новых поставщиков и назначить их новому сценарию.</span><span class="sxs-lookup"><span data-stu-id="0551e-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0551e-199">См. также</span><span class="sxs-lookup"><span data-stu-id="0551e-199">See Also</span></span>


[<span data-ttu-id="0551e-200">Get — CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="0551e-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[<span data-ttu-id="0551e-201">New — CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="0551e-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[<span data-ttu-id="0551e-202">Remove — CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="0551e-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[<span data-ttu-id="0551e-203">Set — CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="0551e-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[<span data-ttu-id="0551e-204">New — CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="0551e-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

