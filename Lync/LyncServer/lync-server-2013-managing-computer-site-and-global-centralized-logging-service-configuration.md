---
title: Управление конфигурацией службы ведения журналов компьютера, сайта и глобальной централизованной организации
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f714c82fdc4ade0fc70b0a977e32ef46b26914d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a><span data-ttu-id="e38bc-102">Управление конфигурацией службы ведения журналов на компьютере, сайте и глобальном централизованном хранилище в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38bc-102">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e38bc-103">_**Тема последнего изменения:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="e38bc-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="e38bc-104">Централизованная служба ведения журнала может выполняться в области, содержащей один компьютер, пул компьютеров, а также на уровне сайта (определенного сайта, такого как Redmond сайта, который содержит коллекцию компьютеров и пулов в развертывании), или в глобальной области (то есть , все компьютеры и пулы в развертывании).</span><span class="sxs-lookup"><span data-stu-id="e38bc-104">The Centralized Logging Service can be run at a scope that includes a single computer, a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="e38bc-105">Чтобы настроить централизованную службу ведения журналов с помощью командной консоли Lync Server Management Shell, необходимо быть членом группы безопасности Ксадминистратор или Кссерверадминистратор управления доступом на основе ролей (RBAC) или настраиваемой роли RBAC, содержащей Любая из этих двух групп.</span><span class="sxs-lookup"><span data-stu-id="e38bc-105">To configure the Centralized Logging Service scope by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="e38bc-106">Чтобы возвратить список всех ролей RBAC, которым был назначен этот командлет (включая любые пользовательские роли RBAC, созданные пользователем), выполните следующую команду из командной консоли Lync Server Management Shell или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e38bc-106">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

<span data-ttu-id="e38bc-107">Например:</span><span class="sxs-lookup"><span data-stu-id="e38bc-107">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> <span data-ttu-id="e38bc-108">Windows PowerShell предлагает дополнительные параметры и дополнительные параметры настройки, недоступные с помощью Клсконтроллер. exe.</span><span class="sxs-lookup"><span data-stu-id="e38bc-108">Windows PowerShell provides you more options and additional configuration options that are not available by using CLSController.exe.</span></span> <span data-ttu-id="e38bc-109">Клсконтроллер обеспечивает быстрый и короткий метод для выполнения команд, но ограничен набором команд, доступных для Клсконтроллер.</span><span class="sxs-lookup"><span data-stu-id="e38bc-109">CLSController offers a quick, concise method to run commands, but is limited to the set of commands available for the CLSController.</span></span> <span data-ttu-id="e38bc-110">Windows PowerShell не ограничивается только командой, доступной для командного процессора Клсконтроллер, и предоставляет широкий набор команд и более широкий набор параметров.</span><span class="sxs-lookup"><span data-stu-id="e38bc-110">Windows PowerShell is not limited to just the command available to the command processor of the CLSController, and provides a wider set of commands and a richer set of options.</span></span> <span data-ttu-id="e38bc-111">Например, в Клсконтроллер. exe предусмотрены параметры области – Компьютеры и – пулы.</span><span class="sxs-lookup"><span data-stu-id="e38bc-111">For example, CLSController.exe does provide you with a scope options for –computers and –pools.</span></span> <span data-ttu-id="e38bc-112">С помощью Windows PowerShell вы можете указать, какие компьютеры или пулы в большинстве команд, и при определении новых сценариев (Клсконтроллер имеет конечное количество сценариев, которые не могут быть изменены пользователем). Вы можете определить сайт или глобальную область.</span><span class="sxs-lookup"><span data-stu-id="e38bc-112">With Windows PowerShell, you can indicate computers or pools in most commands, and when you define new scenarios (CLSController has a finite number of scenarios that are not user modifiable) you can define a site or global scope.</span></span> <span data-ttu-id="e38bc-113">Эта мощная функция Windows PowerShell позволяет определять сценарий для сайта или глобальной области, но ограничивает фактическое ведение журнала для компьютера или пула.</span><span class="sxs-lookup"><span data-stu-id="e38bc-113">This powerful feature of Windows PowerShell enables you to define a scenario a site or global scope, but limit the actual logging to a computer or pool.</span></span><BR><span data-ttu-id="e38bc-114">Существуют фундаментальные различия между командами командной строки, которые можно выполнять в Windows PowerShell или Клсконтроллер.</span><span class="sxs-lookup"><span data-stu-id="e38bc-114">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="e38bc-115">Windows PowerShell предоставляет богатый способ настройки и определения сценариев, а также повторно использовать эти сценарии для сценариев устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="e38bc-115">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="e38bc-116">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span><span class="sxs-lookup"><span data-stu-id="e38bc-116">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="e38bc-117">В отличие от командлетов Windows PowerShell, Клсконтроллер не может определять новые сценарии, управлять областью на сайте или глобальном уровне и многие другие ограничения набора команд, которые не могут быть настроены динамически.</span><span class="sxs-lookup"><span data-stu-id="e38bc-117">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="e38bc-118">Несмотря на то, что Клсконтроллер предоставляет средства для быстрого выполнения, Windows PowerShell предоставляет средства для продления функций централизованной службы ведения журналов, помимо возможностей, возможных для Клсконтроллер.</span><span class="sxs-lookup"><span data-stu-id="e38bc-118">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>



</div>

<span data-ttu-id="e38bc-p104">Область одного компьютера можно определить при выполнении команд [Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15)) и [Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) с помощью параметра –Computers. Параметр –Computers принимает разделенный запятой список полных доменных имен для целевого компьютера.</span><span class="sxs-lookup"><span data-stu-id="e38bc-p104">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15)) and [Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) command using the –Computers parameter. The –Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="e38bc-121">С помощью параметра –Pools можно задать разделенный запятой список пулов, в которых должны выполняться команды ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="e38bc-121">You can also define –Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>



</div>

<span data-ttu-id="e38bc-122">В командлетах служб ведения журналов для **создания**и **удаления** сайтов определены \*\*\*\* сайты и глобальные области.</span><span class="sxs-lookup"><span data-stu-id="e38bc-122">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="e38bc-123">The following examples demonstrate how to set a site and a global scope.</span><span class="sxs-lookup"><span data-stu-id="e38bc-123">The following examples demonstrate how to set a site and a global scope.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e38bc-124">Показанные команды могут содержать параметры и концепции, описанные в других разделах.</span><span class="sxs-lookup"><span data-stu-id="e38bc-124">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="e38bc-125">Команды в примерах предназначены для демонстрации использования параметра <STRONG>–Identity</STRONG> для определения области, а другие параметры включены для полноты и для указания области.</span><span class="sxs-lookup"><span data-stu-id="e38bc-125">The example commands are intended to demonstrate the use of the <STRONG>–Identity</STRONG> parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="e38bc-126">Дополнительные сведения о командлетах <STRONG>Set-CsClsConfiguration</STRONG> см. в описании командлета <A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> в документации по применению.</span><span class="sxs-lookup"><span data-stu-id="e38bc-126">For details about the <STRONG>Set-CsClsConfiguration</STRONG> cmdlets, see <A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="e38bc-127">Чтобы получить текущую конфигурацию централизованной службы ведения журнала</span><span class="sxs-lookup"><span data-stu-id="e38bc-127">To retrieve the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="e38bc-128">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e38bc-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e38bc-129">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="e38bc-129">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration

<span data-ttu-id="e38bc-130">Используйте командлеты **New-CsClsConfiguration** и **Set-CsClsConfiguration** для создания новой конфигурации или для обновления существующей.</span><span class="sxs-lookup"><span data-stu-id="e38bc-130">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.</span></span>

<span data-ttu-id="e38bc-131">При выполнении командлета **Get-CsClsConfiguration** отображаются сведения, подобные показанным на следующем снимке экрана. В этом примере в развертывании имеется глобальная конфигурация по умолчанию, а конфигурации сайтов не определены:</span><span class="sxs-lookup"><span data-stu-id="e38bc-131">When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

<span data-ttu-id="e38bc-132">![Выход выборки из Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Выход выборки из Get-CsClsConfiguration.")</span><span class="sxs-lookup"><span data-stu-id="e38bc-132">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="e38bc-133">Чтобы получить текущую конфигурацию централизованной службы ведения журналов из локального магазина компьютера</span><span class="sxs-lookup"><span data-stu-id="e38bc-133">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1.  <span data-ttu-id="e38bc-134">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e38bc-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e38bc-135">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="e38bc-135">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -LocalStore

<span data-ttu-id="e38bc-136">При использовании первого примера, где **Get-ксклсконфигуратион** не задает параметры, команда ссылается на центральное хранилище для управления данными.</span><span class="sxs-lookup"><span data-stu-id="e38bc-136">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="e38bc-137">Если указать параметр — Локалсторе, команда будет ссылаться на компьютер Локалсторе вместо центрального хранилища.</span><span class="sxs-lookup"><span data-stu-id="e38bc-137">If you specify the parameter –LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="e38bc-138">Получение списка сценариев, определенных в текущий момент</span><span class="sxs-lookup"><span data-stu-id="e38bc-138">To retrieve a listing of scenarios currently defined</span></span>

1.  <span data-ttu-id="e38bc-139">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e38bc-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e38bc-140">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="e38bc-140">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    <span data-ttu-id="e38bc-141">Например для получения сценариев, определенных в глобальной области, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="e38bc-141">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

<span data-ttu-id="e38bc-142">Командлет **Get-CsClsConfiguration** всегда отображает сценарии, которые являются частью конфигурации заданной области.</span><span class="sxs-lookup"><span data-stu-id="e38bc-142">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope’s configuration.</span></span> <span data-ttu-id="e38bc-143">В большинстве случаев отображаются не все сценарии, кроме того, отображаемые сценарии сокращаются.</span><span class="sxs-lookup"><span data-stu-id="e38bc-143">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="e38bc-144">Используемая здесь команда отображает список всех сценариев и частичные сведения об используемых поставщиках, настройках и флагах.</span><span class="sxs-lookup"><span data-stu-id="e38bc-144">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="e38bc-145">Обновление глобальной области для централизованной службы ведения журналов с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e38bc-145">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="e38bc-146">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e38bc-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e38bc-147">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="e38bc-147">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    <span data-ttu-id="e38bc-148">Например:</span><span class="sxs-lookup"><span data-stu-id="e38bc-148">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

<span data-ttu-id="e38bc-p109">При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле развертывания задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда влияет на компьютеры и пулы на всех сайтах и задает в качестве размера переключения на новый журнал трассировки значение 40 МБ.</span><span class="sxs-lookup"><span data-stu-id="e38bc-p109">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="e38bc-151">Обновление области сайта для централизованной службы ведения журналов с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e38bc-151">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="e38bc-152">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e38bc-152">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e38bc-153">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="e38bc-153">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    <span data-ttu-id="e38bc-154">Например:</span><span class="sxs-lookup"><span data-stu-id="e38bc-154">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e38bc-p110">Как отмечено в примере, расположением файлов журнала по умолчанию является каталог %TEMP%\Tracing. Однако так как фактически файл записывает CLSAgent, который выполняется как сетевая служба, переменная %TEMP% расширяется до %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span><span class="sxs-lookup"><span data-stu-id="e38bc-p110">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

    
    </div>

<span data-ttu-id="e38bc-p111">При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле сайта Redmond задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда не повлияет на компьютеры и пулы на других сайтах, которые продолжат использовать текущее значение размера переключения на новый журнал трассировки, определенное либо по умолчанию (20 МБ), либо во время запуска сеанса ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="e38bc-p111">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="e38bc-159">Создание новой конфигурации централизованной службы ведения журнала</span><span class="sxs-lookup"><span data-stu-id="e38bc-159">To create a new Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="e38bc-160">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e38bc-160">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e38bc-161">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="e38bc-161">Type the following at the command-line prompt:</span></span>
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e38bc-162">Командлет New-CsClsConfiguration предоставляет доступ к большому количеству необязательных параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e38bc-162">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="e38bc-163">Сведения о параметрах конфигурации можно найти в <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">статьях Get-ксклсконфигуратион</A> и общие сведения о <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">централизованных параметрах конфигурации службы ведения журналов в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e38bc-163">For details about the configuration options, see <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> and <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Understanding Centralized Logging Service configuration settings in Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="e38bc-164">Например для создания новой конфигурации, которая определяет сетевую папку для файлов кэша, а также период и размер переключения для файлов журнала, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e38bc-164">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

<span data-ttu-id="e38bc-165">Тщательно спланируйте создание новых конфигураций и определите, как вы определяете новые свойства для централизованной службы ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="e38bc-165">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="e38bc-166">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span><span class="sxs-lookup"><span data-stu-id="e38bc-166">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="e38bc-167">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span><span class="sxs-lookup"><span data-stu-id="e38bc-167">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="e38bc-168">Удаление существующей конфигурации службы централизованного ведения журнала</span><span class="sxs-lookup"><span data-stu-id="e38bc-168">To remove an existing Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="e38bc-169">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e38bc-169">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e38bc-170">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="e38bc-170">Type the following at the command-line prompt:</span></span>
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    <span data-ttu-id="e38bc-171">Например, чтобы удалить созданную конфигурацию централизованной службы ведения журналов, чтобы продлить время переключения на файл журнала, измените размер файла журнала продолжения и установите для него расположение кэша файлов журнала, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e38bc-171">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e38bc-172">Это новая конфигурация, созданная в процедуре "Создание новой конфигурации централизованной службы ведения журнала".</span><span class="sxs-lookup"><span data-stu-id="e38bc-172">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

    
    </div>

<span data-ttu-id="e38bc-173">Если удалить конфигурацию уровня сайта, сайт будет использовать глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="e38bc-173">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e38bc-174">См. также</span><span class="sxs-lookup"><span data-stu-id="e38bc-174">See Also</span></span>


[<span data-ttu-id="e38bc-175">Общие сведения об централизованной службе ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38bc-175">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="e38bc-176">Управление централизованными параметрами конфигурации службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38bc-176">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
<span data-ttu-id="e38bc-177">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e38bc-177">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="e38bc-178">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e38bc-178">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span></span>  
<span data-ttu-id="e38bc-179">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e38bc-179">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="e38bc-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e38bc-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

