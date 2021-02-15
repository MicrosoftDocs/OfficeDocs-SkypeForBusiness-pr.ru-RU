---
title: Управление настройками службы централизованного ведения журналов в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Сводка. Узнайте, как извлекать, обновлять и создавать параметры конфигурации для службы централизованного ведения журналов в Skype для бизнеса Server 2015.
ms.openlocfilehash: dd292465d65116dc1f497a733ca8e010e57b9137
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835159"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="5bfe5-103">Управление настройками службы централизованного ведения журналов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="5bfe5-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="5bfe5-104">**Сводка:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="5bfe5-105">Служба централизованного ведения журналов управляется и настраивается параметрами, созданными и используемыми контроллером централизованной службы ведения журналов (CLSController) для отправки команд агенту централизованной службы ведения журналов (CLSAgent) отдельного компьютера.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="5bfe5-106">Агент обрабатывает команды, которые ему отправляются, и (в случае команды "Начните") использует конфигурацию сценариев, поставщиков, продолжительность трассировки и флаги, чтобы начать собирать журналы трассировки в соответствии с предоставленными сведениями о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="5bfe5-107">Не все Windows PowerShell, перечисленные для службы централизованного ведения журналов, предназначены для локального развертывания Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="5bfe5-108">Несмотря на то что они могут показаться работоудаными, следующие cmdlets не предназначены для работы с локального развертывания Skype для бизнеса Server 2015:</span><span class="sxs-lookup"><span data-stu-id="5bfe5-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="5bfe5-109">**CsClsRegion cmdlets:** [Get-CsClsRegion,](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) [Set-CsClsRegion,](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps) [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)и [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5bfe5-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="5bfe5-110">**Командлеты CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) и [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5bfe5-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="5bfe5-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup,](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps) [Set-CsClsSecurityGroup,](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps) [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)и [Remove-CsClsSecurityGroup.](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="5bfe5-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="5bfe5-112">Параметры, определенные в этих cmdlets, не препятствуют работе и не вызывают никаких отрицательных последствий, но они предназначены для использования с Microsoft 365 или Office 365 и не дают ожидаемых результатов в локальном развертывании.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 or Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="5bfe5-113">Это не означает полную бесполезность таких командлетов в локальных развертываниях, но вопрос об их использовании выходит за рамки данной документации.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="5bfe5-114">Централизованную службу ведения журналов можно запустить в области, которая включает один компьютер или пул компьютеров, на уровне сайта (то есть на определенном сайте, например на сайте Redmond, который содержит коллекцию компьютеров и пулов в развертывании) или на глобальном уровне (то есть на всех компьютерах и пулах в развертывании).</span><span class="sxs-lookup"><span data-stu-id="5bfe5-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="5bfe5-115">Чтобы настроить область службы централизованного ведения журналов с помощью оболочки управления Skype для бизнеса Server, необходимо быть участником групп безопасности управления доступом на основе ролей (RBAC) CsAdministrator или CsServerAdministrator, а также настраиваемой роли RBAC, которая содержит какую-либо из этих двух групп.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="5bfe5-116">Чтобы получить список всех ролей RBAC, которые были назначены этому командлету (включая все самостоятельно созданные роли RBAC), запустите следующую команду в командной Windows PowerShell Командная Windows PowerShell Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="5bfe5-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="5bfe5-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="5bfe5-117">For example:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="5bfe5-118">Существуют фундаментальные различия между командами командной строки, которые можно выполнить в Windows PowerShell clSController.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="5bfe5-119">Windows PowerShell предоставляет богатый метод для настройки и определения сценариев, а также для эффективного использования этих сценариев для сценариев устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="5bfe5-120">Хотя CLSController позволяет быстро и эффективно выполнять команды и получать результаты, набор команд этого средства ограничен командами, доступными из командной строки.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="5bfe5-121">В отличие от Windows PowerShell командлетов CLSController не может определять новые сценарии, управлять областью на уровне сайта или на глобальном уровне и многими другими ограничениями ограниченного набора команд, который не может быть динамически настроен.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="5bfe5-122">Хотя CLSController предоставляет средства для быстрого выполнения, Windows PowerShell предоставляет средства для расширения функций централизованной службы ведения журналов за пределами возможностей CLSController.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="5bfe5-123">Область одного компьютера может быть определена во время выполнения команды [Search-CsClsLogging,](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps) [Show-CsClsLogging,](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps) [Start-CsClsLogging,](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps) [Stop-CsClsLogging,](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps) [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) и [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) с помощью параметра -Computers.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="5bfe5-124">Параметр -Computers принимает разделенный запятой список полного доменного имени (FQDNs) для целевого компьютера.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="5bfe5-125">Можно также определить пулы -Pools и разделенный запятой список пулов, в которые необходимо выполнить команды ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="5bfe5-126">Области сайта и глобальные области определяются в cmdlets **New-**, **Set-** и **Remove-Centralized** Logging Service.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="5bfe5-127">В следующих примерах показано, как задать область сайта и глобальную область.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5bfe5-128">Показанные команды могут содержать параметры и концепции, описанные в других разделах.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="5bfe5-129">Примеры команд предназначены для демонстрации использования параметра **-Identity** для определения области, а остальные параметры включаются для полноты и указания области.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="5bfe5-130">Дополнительные сведения о командлетах **Set-CsClsConfiguration** см. в описании командлета [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) в документации по применению.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="5bfe5-131">Извлечение текущей конфигурации службы централизованного ведения журналов</span><span class="sxs-lookup"><span data-stu-id="5bfe5-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="5bfe5-132">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="5bfe5-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="5bfe5-133">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="5bfe5-133">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration
   ```

<span data-ttu-id="5bfe5-134">Используйте для создания новой конфигурации или обновления существующей конфигурации с помощью cmdlets **New-CsClsConfiguration** и **Set-CsClsConfiguration.** При запуске **Get-CsClsConfiguration** отображаются сведения, похожие на следующие снимки экрана, где в развертывании в настоящее время установлена глобальная конфигурация по умолчанию, но конфигурации сайта не определены:</span><span class="sxs-lookup"><span data-stu-id="5bfe5-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![Пример выходных данных из get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="5bfe5-136">Извлечение текущей конфигурации службы централизованного ведения журналов с локального компьютера</span><span class="sxs-lookup"><span data-stu-id="5bfe5-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="5bfe5-137">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="5bfe5-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="5bfe5-138">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="5bfe5-138">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="5bfe5-139">При использовании первого примера, в котором **get-CsClsConfiguration** не указывает никаких параметров, команда ссылается на центральное хранилище управления для данных.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="5bfe5-140">Если указан параметр -LocalStore, команда ссылается на компьютер LocalStore, а не центральное хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="5bfe5-141">Получение листинга сценариев, определенных в текущий момент</span><span class="sxs-lookup"><span data-stu-id="5bfe5-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="5bfe5-142">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="5bfe5-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="5bfe5-143">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="5bfe5-143">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="5bfe5-144">Например, для получения сценариев, определенных в глобальной области, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="5bfe5-145">Этот cmdlet **Get-CsClsConfiguration** всегда отображает сценарии, в которые входит конфигурация заданной области.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="5bfe5-146">В большинстве случаев отображаются не все сценарии, кроме того, отображаемые сценарии сокращаются.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="5bfe5-147">Используемая здесь команда отображает список всех сценариев и частичные сведения об используемых поставщиках, настройках и флагах.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="5bfe5-148">Обновление глобальной области для службы централизованного ведения журналов с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5bfe5-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="5bfe5-149">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="5bfe5-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="5bfe5-150">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="5bfe5-150">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="5bfe5-151">Пример:</span><span class="sxs-lookup"><span data-stu-id="5bfe5-151">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="5bfe5-p111">При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле развертывания задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда влияет на компьютеры и пулы на всех сайтах и задает в качестве размера переключения на новый журнал трассировки значение 40 МБ.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-p111">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="5bfe5-154">Обновление области сайта для службы централизованного ведения журналов с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5bfe5-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="5bfe5-155">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="5bfe5-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="5bfe5-156">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="5bfe5-156">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="5bfe5-157">Пример:</span><span class="sxs-lookup"><span data-stu-id="5bfe5-157">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="5bfe5-p112">Как отмечено в примере, расположением файлов журнала по умолчанию является каталог %TEMP%\Tracing. Однако, так как фактически файл записывает CLSAgent, который выполняется как сетевая служба, переменная %TEMP% расширяется до %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-p112">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="5bfe5-p113">При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле сайта Redmond задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда не повлияет на компьютеры и пулы на других сайтах, которые продолжат использовать текущее значение размера переключения на новый журнал трассировки, определенное либо по умолчанию (20 МБ), либо во время запуска сеанса ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-p113">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="5bfe5-162">Создание новой конфигурации службы централизованного ведения журналов</span><span class="sxs-lookup"><span data-stu-id="5bfe5-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="5bfe5-163">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="5bfe5-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="5bfe5-164">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="5bfe5-164">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="5bfe5-165">Командлет New-CsClsConfiguration предоставляет доступ к большому количеству необязательных параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="5bfe5-166">Подробные сведения о параметрах конфигурации см. в настройках [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) и [Understanding Centralized Logging Service Configuration Settings.](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)</span><span class="sxs-lookup"><span data-stu-id="5bfe5-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span>

<span data-ttu-id="5bfe5-167">Например, для создания новой конфигурации, которая определяет сетевую папку для файлов кэша, а также период и размер переключения для файлов журнала, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5bfe5-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="5bfe5-168">Следует тщательно спланировать создание новых конфигураций и определение новых свойств для службы централизованного ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="5bfe5-169">Необходимо проявлять осторожность при изменениях и учитывать их влияние на возможность правильного ведения журналов в проблемных сценариях.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="5bfe5-170">В конфигурацию следует вносить такие изменения, которые улучшат возможности управления журналами и позволят задать такие значения размера и периода переключения, которые помогут устранить возможные проблемы.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="5bfe5-171">Удаление существующей конфигурации службы централизованного ведения журналов</span><span class="sxs-lookup"><span data-stu-id="5bfe5-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="5bfe5-172">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="5bfe5-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="5bfe5-173">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="5bfe5-173">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="5bfe5-174">Например, чтобы удалить конфигурацию службы централизованного ведения журналов, созданную для увеличения времени переката файла журнала, увеличить размер файла журнала отката и установить расположение кэша файлов журнала в сетевую папку следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5bfe5-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="5bfe5-175">Это новая конфигурация, созданная в процедуре "Создание новой конфигурации службы централизованного ведения журналов".</span><span class="sxs-lookup"><span data-stu-id="5bfe5-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="5bfe5-176">Если удалить конфигурацию уровня сайта, сайт будет использовать глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="5bfe5-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="5bfe5-177">См. также</span><span class="sxs-lookup"><span data-stu-id="5bfe5-177">See also</span></span>

[<span data-ttu-id="5bfe5-178">Настройка поставщиков службы централизованного ведения журналов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="5bfe5-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="5bfe5-179">Настройка сценариев для службы централизованного ведения журналов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="5bfe5-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="5bfe5-180">Служба централизованного ведения журналов в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="5bfe5-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="5bfe5-181">Set-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5bfe5-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="5bfe5-182">Get-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5bfe5-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="5bfe5-183">New-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5bfe5-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="5bfe5-184">Remove-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5bfe5-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
