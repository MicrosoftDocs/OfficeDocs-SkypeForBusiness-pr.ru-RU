---
title: Управление параметрами конфигурации централизованной службы ведения журналов в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: Сводка. Узнайте, как получать, обновлять и создавать параметры конфигурации для централизованной службы ведения журналов в Skype для бизнеса Server 2015.
ms.openlocfilehash: ed75aab211f2d2abbf0a2007fd83e5be8bb70404
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221179"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="e6435-103">Управление параметрами конфигурации централизованной службы ведения журналов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="e6435-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="e6435-104">**Сводка:** Узнайте, как извлекать, обновлять и создавать параметры конфигурации для централизованной службы ведения журналов в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e6435-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="e6435-105">Централизованная служба ведения журналов контролируется и настраивается параметрами и параметрами, которые создаются и используются централизованным контроллером службы ведения журналов (CLSController) для отправки команд в агент службы централизованного ведения журналов (CLSAgent) отдельного компьютера.</span><span class="sxs-lookup"><span data-stu-id="e6435-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="e6435-106">Агент обрабатывает отправляемые им команды и (в случае команды запуска) использует конфигурацию сценариев, поставщиков, продолжительность трассировки и флаги для начала сбора журналов трассировки в соответствии с предоставленными сведениями о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e6435-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="e6435-107">Не все командлеты Windows PowerShell, перечисленные для централизованной службы ведения журналов, предназначены для использования с локальными развертываниями Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e6435-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="e6435-108">Несмотря на то, что они могут показаться работоспособными, следующие командлеты не предназначены для работы с локальными развертываниями Skype для бизнеса Server 2015:</span><span class="sxs-lookup"><span data-stu-id="e6435-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="e6435-109">**Командлеты CsClsRegion:** [Get – CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set — CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)и [Remove – CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e6435-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="e6435-110">**Командлеты CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) и [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e6435-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="e6435-111">**Командлеты CsClsSecurityGroup:** [Get – CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set — CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)и [Remove – CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e6435-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="e6435-112">Параметры, определенные в этих командлетах, не мешают или не вызывают каких – либо неблагоприятных поведений, но они предназначены для использования с Microsoft 365 или Office 365 и не будут давать ожидаемые результаты в локальных развертываниях.</span><span class="sxs-lookup"><span data-stu-id="e6435-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 or Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="e6435-113">Это не означает полную бесполезность таких командлетов в локальных развертываниях, но вопрос об их использовании выходит за рамки данной документации.</span><span class="sxs-lookup"><span data-stu-id="e6435-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="e6435-114">Централизованную службу ведения журналов можно запустить в области, которая включает один компьютер или пул компьютеров, на уровне сайта (то есть, определенного сайта, такого как Redmond сайта, содержащего коллекцию компьютеров и пулов в развертывании) или в глобальной области (то есть на всех компьютерах и в пулах в развертывании).</span><span class="sxs-lookup"><span data-stu-id="e6435-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="e6435-115">Чтобы настроить область Службы централизованного ведения журналов с помощью командной консоли Skype для бизнеса Server, необходимо быть членом группы безопасности CsAdministrator или CsServerAdministrator с управлением доступом на основе ролей (RBAC) или настраиваемой роли RBAC, которая содержит любую из этих двух групп.</span><span class="sxs-lookup"><span data-stu-id="e6435-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="e6435-116">Чтобы получить список всех ролей RBAC, которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните следующую команду в командной консоли Skype для бизнеса Server или в командной строке Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e6435-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="e6435-117">Например:</span><span class="sxs-lookup"><span data-stu-id="e6435-117">For example:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="e6435-118">Существуют фундаментальные различия между командами командной строки, которые можно запускать в Windows PowerShell или CLSController.</span><span class="sxs-lookup"><span data-stu-id="e6435-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="e6435-119">Windows PowerShell предоставляет богатый метод настройки и определения сценариев, а также повторное использование этих сценариев для сценариев устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="e6435-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="e6435-120">Хотя CLSController позволяет быстро и эффективно выполнять команды и получать результаты, набор команд этого средства ограничен командами, доступными из командной строки.</span><span class="sxs-lookup"><span data-stu-id="e6435-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="e6435-121">В отличие от командлетов Windows PowerShell, CLSController не может определять новые сценарии, управлять областью на сайте или глобальном уровне, а также многие другие ограничения набора команд, которые не могут быть настроены динамически.</span><span class="sxs-lookup"><span data-stu-id="e6435-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="e6435-122">Хотя CLSController предоставляет средства для быстрого выполнения, Windows PowerShell предоставляет средства для расширения функциональности централизованной службы ведения журналов помимо того, что возможно в CLSController.</span><span class="sxs-lookup"><span data-stu-id="e6435-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="e6435-123">Область одного компьютера можно определить во время выполнения команды [Search — CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start — CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync – CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) и [Update/CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) с помощью параметра – Computers.</span><span class="sxs-lookup"><span data-stu-id="e6435-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="e6435-124">Параметр-Computers принимает разделенный запятыми список полных доменных имен (FQDN) конечного компьютера.</span><span class="sxs-lookup"><span data-stu-id="e6435-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="e6435-125">Кроме того, можно определить пулы и разделенные запятыми список пулов, в которых будут выполняться команды ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="e6435-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="e6435-126">Сайты и глобальные области определены в командлетах службы ведения журналов **New-**, **Set-** и **Remove-** централизованный.</span><span class="sxs-lookup"><span data-stu-id="e6435-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="e6435-127">В следующих примерах показано, как задать область сайта и глобальную область.</span><span class="sxs-lookup"><span data-stu-id="e6435-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6435-128">Показанные команды могут содержать параметры и концепции, описанные в других разделах.</span><span class="sxs-lookup"><span data-stu-id="e6435-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="e6435-129">Примеры команд предназначены для демонстрации использования параметра **– Identity** для определения области, а другие параметры — для полноты и указания области.</span><span class="sxs-lookup"><span data-stu-id="e6435-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="e6435-130">Дополнительные сведения о командлетах **Set-CsClsConfiguration** см. в описании командлета [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) в документации по применению.</span><span class="sxs-lookup"><span data-stu-id="e6435-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="e6435-131">Получение текущей конфигурации централизованной службы ведения журналов</span><span class="sxs-lookup"><span data-stu-id="e6435-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="e6435-132">Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="e6435-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e6435-133">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="e6435-133">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration
   ```

<span data-ttu-id="e6435-134">Используйте командлеты **New – CsClsConfiguration** и **Set – CsClsConfiguration** для создания новой конфигурации или для обновления существующей конфигурации. При выполнении командлета **Get-CsClsConfiguration**отображаются сведения, аналогичные приведенным на следующем снимке экрана, где в настоящее время развертывание содержит глобальную конфигурацию по умолчанию, но не определено ни одной конфигурации сайта:</span><span class="sxs-lookup"><span data-stu-id="e6435-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![Пример выходных данных Get – CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="e6435-136">Получение текущей конфигурации централизованной службы ведения журналов из локального хранилища компьютера</span><span class="sxs-lookup"><span data-stu-id="e6435-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="e6435-137">Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="e6435-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e6435-138">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="e6435-138">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="e6435-139">При использовании первого примера, когда **Get – CsClsConfiguration** не задает параметры, команда ссылается на центральное хранилище управления данными.</span><span class="sxs-lookup"><span data-stu-id="e6435-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="e6435-140">Если указать параметр – Локалсторе, команда будет ссылаться на компьютер Локалсторе вместо центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="e6435-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="e6435-141">Получение листинга сценариев, определенных в текущий момент</span><span class="sxs-lookup"><span data-stu-id="e6435-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="e6435-142">Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="e6435-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e6435-143">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="e6435-143">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="e6435-144">Например, для получения сценариев, определенных в глобальной области, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="e6435-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="e6435-145">Командлет **Get – CsClsConfiguration** всегда отображает сценарии, которые являются частью конфигурации данной области.</span><span class="sxs-lookup"><span data-stu-id="e6435-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="e6435-146">В большинстве случаев отображаются не все сценарии, кроме того, отображаемые сценарии сокращаются.</span><span class="sxs-lookup"><span data-stu-id="e6435-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="e6435-147">Используемая здесь команда отображает список всех сценариев и частичные сведения об используемых поставщиках, настройках и флагах.</span><span class="sxs-lookup"><span data-stu-id="e6435-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="e6435-148">Обновление глобальной области для централизованной службы ведения журналов с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6435-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="e6435-149">Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="e6435-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e6435-150">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="e6435-150">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="e6435-151">Пример:</span><span class="sxs-lookup"><span data-stu-id="e6435-151">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="e6435-p111">При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле развертывания задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда влияет на компьютеры и пулы на всех сайтах и задает в качестве размера переключения на новый журнал трассировки значение 40 МБ.</span><span class="sxs-lookup"><span data-stu-id="e6435-p111">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="e6435-154">Обновление области сайта для централизованной службы ведения журналов с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6435-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="e6435-155">Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="e6435-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e6435-156">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="e6435-156">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="e6435-157">Пример:</span><span class="sxs-lookup"><span data-stu-id="e6435-157">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="e6435-p112">Как отмечено в примере, расположением файлов журнала по умолчанию является каталог %TEMP%\Tracing. Однако, так как фактически файл записывает CLSAgent, который выполняется как сетевая служба, переменная %TEMP% расширяется до %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span><span class="sxs-lookup"><span data-stu-id="e6435-p112">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="e6435-p113">При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле сайта Redmond задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда не повлияет на компьютеры и пулы на других сайтах, которые продолжат использовать текущее значение размера переключения на новый журнал трассировки, определенное либо по умолчанию (20 МБ), либо во время запуска сеанса ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="e6435-p113">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="e6435-162">Создание новой конфигурации централизованной службы ведения журналов</span><span class="sxs-lookup"><span data-stu-id="e6435-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="e6435-163">Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="e6435-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e6435-164">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="e6435-164">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="e6435-165">Командлет New-CsClsConfiguration предоставляет доступ к большому количеству необязательных параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e6435-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="e6435-166">Сведения о параметрах конфигурации приведены в статье [Get – CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) и [сведения о параметрах конфигурации службы централизованного ведения журналов](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span><span class="sxs-lookup"><span data-stu-id="e6435-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span>

<span data-ttu-id="e6435-167">Например, для создания новой конфигурации, которая определяет сетевую папку для файлов кэша, а также период и размер переключения для файлов журнала, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e6435-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="e6435-168">Следует тщательно спланировать создание новых конфигураций и определить новые свойства централизованной службы ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="e6435-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="e6435-169">Необходимо проявлять осторожность при изменениях и учитывать их влияние на возможность правильного ведения журналов в проблемных сценариях.</span><span class="sxs-lookup"><span data-stu-id="e6435-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="e6435-170">В конфигурацию следует вносить такие изменения, которые улучшат возможности управления журналами и позволят задать такие значения размера и периода переключения, которые помогут устранить возможные проблемы.</span><span class="sxs-lookup"><span data-stu-id="e6435-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="e6435-171">Удаление существующей конфигурации централизованной службы ведения журналов</span><span class="sxs-lookup"><span data-stu-id="e6435-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="e6435-172">Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="e6435-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e6435-173">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="e6435-173">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="e6435-174">Например, чтобы удалить созданную конфигурацию централизованной службы ведения журналов, чтобы увеличить время переключения файла журнала, увеличьте размер файла журнала продолжения и установите для расположения кэша файлов журнала следующий сетевой ресурс:</span><span class="sxs-lookup"><span data-stu-id="e6435-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="e6435-175">Это новая конфигурация, созданная в процедуре "Создание новой конфигурации централизованной службы ведения журналов".</span><span class="sxs-lookup"><span data-stu-id="e6435-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="e6435-176">Если удалить конфигурацию уровня сайта, сайт будет использовать глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="e6435-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="e6435-177">См. также</span><span class="sxs-lookup"><span data-stu-id="e6435-177">See also</span></span>

[<span data-ttu-id="e6435-178">Настройка поставщиков для централизованной службы ведения журналов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="e6435-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="e6435-179">Настройка сценариев для централизованной службы ведения журналов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="e6435-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="e6435-180">Централизованная служба ведения журналов в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="e6435-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="e6435-181">Set — CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="e6435-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="e6435-182">Get — CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="e6435-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="e6435-183">New — CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="e6435-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="e6435-184">Remove — CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="e6435-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
