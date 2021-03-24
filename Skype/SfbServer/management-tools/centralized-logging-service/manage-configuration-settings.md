---
title: Управление настройками централизованной службы ведения журнала в Skype для бизнеса Server 2015
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
description: Сводка. Сведения о том, как извлекать, обновлять и создавать параметры конфигурации для централизованной службы ведения журнала в Skype для бизнеса Server 2015.
ms.openlocfilehash: fb2d66e6ff72bc5fb5a4c8c987713f3ca7030ab5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098865"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="a985c-103">Управление настройками централизованной службы ведения журнала в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="a985c-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="a985c-104">**Сводка:** Узнайте, как извлекать, обновлять и создавать параметры конфигурации для централизованной службы ведения журнала в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a985c-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="a985c-105">Централизованная служба ведения журнала управляется и настраивается параметрами, созданными и используемыми диспетчером централизованной службы ведения журнала (CLSController) для отправки команд агенту централизованной службы ведения журнала на отдельном компьютере (CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="a985c-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="a985c-106">Агент обрабатывает команды, отправленные ему, и (в случае команды Начните) использует конфигурацию сценариев, поставщиков, продолжительность трассировки и флаги, чтобы начать сбор журналов трассировки в соответствии с предоставленной информацией о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a985c-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="a985c-107">Не все Windows PowerShell, перечисленные для централизованной службы ведения журнала, предназначены для использования в локальном развертывании Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a985c-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="a985c-108">Несмотря на то, что они могут работать, следующие cmdlets не предназначены для работы с локальной развертыванием Skype для бизнеса Server 2015:</span><span class="sxs-lookup"><span data-stu-id="a985c-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="a985c-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](/powershell/module/skype/new-csclsregion?view=skype-ps)и [Remove-CsClsRegion](/powershell/module/skype/remove-csclsregion?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a985c-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="a985c-110">**Командлеты CsClsSearchTerm:** [Get-CsClsSearchTerm](/powershell/module/skype/get-csclssearchterm?view=skype-ps) и [Set-CsClsSearchTerm](/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a985c-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="a985c-111">**Группы CsClsSecurityGroup:** [Get-CsClsSecurityGroup,](/powershell/module/skype/get-csclssecuritygroup?view=skype-ps) [Set-CsClsSecurityGroup,](/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)  [New-CsClsSecurityGroup](/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)и [Remove-CsClsSecurityGroup](/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a985c-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="a985c-112">Параметры, определенные в этих cmdlets, не будут препятствовать или вызывать любое неблагоприятное поведение, но они предназначены для использования в Microsoft 365 или Office 365 и не привратят ожидаемых результатов в локальном развертывании.</span><span class="sxs-lookup"><span data-stu-id="a985c-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 or Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="a985c-113">Это не означает полную бесполезность таких командлетов в локальных развертываниях, но вопрос об их использовании выходит за рамки данной документации.</span><span class="sxs-lookup"><span data-stu-id="a985c-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="a985c-114">Централизованная служба ведения журнала может работать в области, которая включает один компьютер или пул компьютеров, в области сайта (то есть определенном сайте, например на сайте Redmond, который содержит коллекцию компьютеров и пулов в развертывании), или в глобальной области (то есть всех компьютерах и пулах в развертывании).</span><span class="sxs-lookup"><span data-stu-id="a985c-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="a985c-115">Чтобы настроить область централизованной службы ведения журнала с помощью оболочки управления Skype для бизнес-серверов, необходимо быть членом группы безопасности CsAdministrator или группы управления ролями CsServerAdministrator (RBAC) или настраиваемой роли RBAC, которая содержит обе эти две группы.</span><span class="sxs-lookup"><span data-stu-id="a985c-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="a985c-116">Чтобы вернуть список всех ролей RBAC, на которые был назначен этот командлет (включая настраиваемые роли RBAC, созданные самостоятельно), запустите следующую команду из командной команды Skype для бизнеса server или Windows PowerShell запроса:</span><span class="sxs-lookup"><span data-stu-id="a985c-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="a985c-117">Например:</span><span class="sxs-lookup"><span data-stu-id="a985c-117">For example:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="a985c-118">Существуют фундаментальные различия между командами командной строки, которые можно выполнить в Windows PowerShell CLSController.</span><span class="sxs-lookup"><span data-stu-id="a985c-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="a985c-119">Windows PowerShell предоставляет богатый метод настройки и определения сценариев, а также эффективного использования этих сценариев для сценариев устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="a985c-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="a985c-120">Хотя CLSController позволяет быстро и эффективно выполнять команды и получать результаты, набор команд этого средства ограничен командами, доступными из командной строки.</span><span class="sxs-lookup"><span data-stu-id="a985c-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="a985c-121">В отличие Windows PowerShell командлетов CLSController не может определять новые сценарии, управлять областью на сайте или глобальном уровне и многими другими ограничениями конечного командного набора, который не может быть динамически настроен.</span><span class="sxs-lookup"><span data-stu-id="a985c-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="a985c-122">Хотя CLSController предоставляет средство для быстрого выполнения, Windows PowerShell предоставляет средства для расширения функций службы централизованного ведения журнала за пределами возможностей CLSController.</span><span class="sxs-lookup"><span data-stu-id="a985c-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="a985c-123">При выполнении команды [Search-CsClsLogging,](/powershell/module/skype/search-csclslogging?view=skype-ps) [Show-CsClsLogging,](/powershell/module/skype/show-csclslogging?view=skype-ps) [Start-CsClsLogging,](/powershell/module/skype/start-csclslogging?view=skype-ps) [Stop-CsClsLogging,](/powershell/module/skype/stop-csclslogging?view=skype-ps) [Sync-CsClsLogging](/powershell/module/skype/sync-csclslogging?view=skype-ps) и [Update-CsClsLogging](/powershell/module/skype/update-csclslogging?view=skype-ps) можно определить один компьютер.</span><span class="sxs-lookup"><span data-stu-id="a985c-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="a985c-124">Параметр -Computers принимает разделенный запятой список полностью квалифицированных доменных имен (FQDNs) для целевого компьютера.</span><span class="sxs-lookup"><span data-stu-id="a985c-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="a985c-125">Вы также можете определить пулы и разделенный запятой список пулов, на которые необходимо выполнить команды ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="a985c-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="a985c-126">Области site и Global определяются в октах **New-**, **Set-** и **Remove-Centralized** Logging Service.</span><span class="sxs-lookup"><span data-stu-id="a985c-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="a985c-127">В следующих примерах показано, как задать область сайта и глобальную область.</span><span class="sxs-lookup"><span data-stu-id="a985c-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a985c-128">Показанные команды могут содержать параметры и концепции, описанные в других разделах.</span><span class="sxs-lookup"><span data-stu-id="a985c-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="a985c-129">Команды в примере предназначены для демонстрации использования параметра **-Identity** для определения области, а остальные параметры включаются для полноты и для указания области.</span><span class="sxs-lookup"><span data-stu-id="a985c-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="a985c-130">Дополнительные сведения о командлетах **Set-CsClsConfiguration** см. в описании командлета [Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps) в документации по применению.</span><span class="sxs-lookup"><span data-stu-id="a985c-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="a985c-131">Чтобы получить текущую конфигурацию централизованной службы ведения журнала</span><span class="sxs-lookup"><span data-stu-id="a985c-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="a985c-132">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="a985c-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a985c-133">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="a985c-133">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration
   ```

<span data-ttu-id="a985c-134">Для создания новой конфигурации или обновления существующей конфигурации используйте комлеты **New-CsClsConfiguration** и **Set-CsClsConfiguration.** При запуске **Get-CsClsConfiguration** отображаются сведения, аналогичные следующему снимку экрана, где развертывание в настоящее время имеет глобальную конфигурацию по умолчанию, но конфигурации сайтов не определены:</span><span class="sxs-lookup"><span data-stu-id="a985c-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![Пример вывода get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="a985c-136">Извлечение текущей конфигурации централизованной службы ведения журнала из локального магазина компьютера</span><span class="sxs-lookup"><span data-stu-id="a985c-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="a985c-137">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="a985c-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a985c-138">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="a985c-138">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="a985c-139">При использовании первого примера, в котором **Get-CsClsConfiguration** не указывает никаких параметров, команда ссылается на центральный хранилище управления данными.</span><span class="sxs-lookup"><span data-stu-id="a985c-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="a985c-140">Если указать параметр -LocalStore, команда ссылается на компьютер LocalStore, а не на центральный магазин управления.</span><span class="sxs-lookup"><span data-stu-id="a985c-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="a985c-141">Получение листинга сценариев, определенных в текущий момент</span><span class="sxs-lookup"><span data-stu-id="a985c-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="a985c-142">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="a985c-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a985c-143">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="a985c-143">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="a985c-144">Например, для получения сценариев, определенных в глобальной области, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="a985c-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="a985c-145">В cmdlet **Get-CsClsConfiguration** всегда отображаются сценарии, которые являются частью конфигурации данной области.</span><span class="sxs-lookup"><span data-stu-id="a985c-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="a985c-146">В большинстве случаев отображаются не все сценарии, кроме того, отображаемые сценарии сокращаются.</span><span class="sxs-lookup"><span data-stu-id="a985c-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="a985c-147">Используемая здесь команда отображает список всех сценариев и частичные сведения об используемых поставщиках, настройках и флагах.</span><span class="sxs-lookup"><span data-stu-id="a985c-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="a985c-148">Обновление глобальной области для централизированной службы ведения журнала с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a985c-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="a985c-149">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="a985c-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a985c-150">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="a985c-150">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="a985c-151">Пример:</span><span class="sxs-lookup"><span data-stu-id="a985c-151">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="a985c-p111">При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле развертывания задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда влияет на компьютеры и пулы на всех сайтах и задает в качестве размера переключения на новый журнал трассировки значение 40 МБ.</span><span class="sxs-lookup"><span data-stu-id="a985c-p111">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="a985c-154">Обновление области сайта для централизированной службы ведения журнала с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a985c-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="a985c-155">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="a985c-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a985c-156">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="a985c-156">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="a985c-157">Пример:</span><span class="sxs-lookup"><span data-stu-id="a985c-157">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="a985c-p112">Как отмечено в примере, расположением файлов журнала по умолчанию является каталог %TEMP%\Tracing. Однако, так как фактически файл записывает CLSAgent, который выполняется как сетевая служба, переменная %TEMP% расширяется до %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span><span class="sxs-lookup"><span data-stu-id="a985c-p112">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="a985c-p113">При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле сайта Redmond задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда не повлияет на компьютеры и пулы на других сайтах, которые продолжат использовать текущее значение размера переключения на новый журнал трассировки, определенное либо по умолчанию (20 МБ), либо во время запуска сеанса ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="a985c-p113">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="a985c-162">Создание новой конфигурации централизованной службы ведения журнала</span><span class="sxs-lookup"><span data-stu-id="a985c-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="a985c-163">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="a985c-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a985c-164">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="a985c-164">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="a985c-165">Командлет New-CsClsConfiguration предоставляет доступ к большому количеству необязательных параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a985c-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="a985c-166">Сведения о параметрах конфигурации см. в [материале Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings.](/previous-versions/office/lync-server-2013/lync-server-2013-understanding-centralized-logging-service-configuration-settings)</span><span class="sxs-lookup"><span data-stu-id="a985c-166">For details about the configuration options, see [Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-understanding-centralized-logging-service-configuration-settings).</span></span>

<span data-ttu-id="a985c-167">Например, для создания новой конфигурации, которая определяет сетевую папку для файлов кэша, а также период и размер переключения для файлов журнала, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a985c-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="a985c-168">Необходимо тщательно спланировать создание новых конфигураций и определить новые свойства для централизированной службы ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="a985c-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="a985c-169">Необходимо проявлять осторожность при изменениях и учитывать их влияние на возможность правильного ведения журналов в проблемных сценариях.</span><span class="sxs-lookup"><span data-stu-id="a985c-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="a985c-170">В конфигурацию следует вносить такие изменения, которые улучшат возможности управления журналами и позволят задать такие значения размера и периода переключения, которые помогут устранить возможные проблемы.</span><span class="sxs-lookup"><span data-stu-id="a985c-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="a985c-171">Удаление существующей конфигурации централизованной службы ведения журнала</span><span class="sxs-lookup"><span data-stu-id="a985c-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="a985c-172">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="a985c-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a985c-173">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="a985c-173">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="a985c-174">Например, чтобы удалить конфигурацию службы централизованного ведения журнала, созданную для увеличения времени опрокидываемого файла журнала, увеличить размер файла журнала опрокидывательных журналов и установить расположение кэша файла журнала в сетевой совместной сети следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a985c-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="a985c-175">Это новая конфигурация, созданная в процедуре "Создание новой конфигурации централизованной службы ведения журнала".</span><span class="sxs-lookup"><span data-stu-id="a985c-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="a985c-176">Если удалить конфигурацию уровня сайта, сайт будет использовать глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="a985c-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="a985c-177">См. также</span><span class="sxs-lookup"><span data-stu-id="a985c-177">See also</span></span>

[<span data-ttu-id="a985c-178">Настройка поставщиков для централизованной службы ведения журнала в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="a985c-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="a985c-179">Настройка сценариев для централизованной службы ведения журнала в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="a985c-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="a985c-180">Централизованная служба ведения журнала в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="a985c-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="a985c-181">Set-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="a985c-181">Set-CsClsConfiguration</span></span>](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="a985c-182">Get-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="a985c-182">Get-CsClsConfiguration</span></span>](/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="a985c-183">New-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="a985c-183">New-CsClsConfiguration</span></span>](/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="a985c-184">Remove-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="a985c-184">Remove-CsClsConfiguration</span></span>](/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)