---
title: 'Lync Server 2013: Включение или отключение очистки архивных данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 308ba7b91fbe776ed49d72c54e2986ad95d080fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500946"
---
# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a><span data-ttu-id="e4bb4-102">Включение или отключение очистки архивных данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4bb4-102">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4bb4-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e4bb4-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e4bb4-104">В панели управления Lync Server 2013 вы можете использовать конфигурации архивации, чтобы включать и отключать очистку и настраивать реализацию очистки.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable purging and configure how purging is implemented.</span></span> <span data-ttu-id="e4bb4-105">Это включает следующие конфигурации архивирования:</span><span class="sxs-lookup"><span data-stu-id="e4bb4-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="e4bb4-106">Глобальная конфигурация, создаваемая по умолчанию при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="e4bb4-107">Необязательные конфигурации на уровне сайта или пула, которые можно создать и использовать для указания того, как архивирование реализуется для определенных сайтов или пулов.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="e4bb4-108">Начальная настройка конфигураций архивирования производится во время развертывания архивирования, но вы можете изменить, добавить и удалить конфигурации после развертывания.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="e4bb4-109">Для получения дополнительных сведений о способах реализации конфигурации архивации, в том числе о том, какие параметры можно указать и иерархию конфигураций архивации, посмотрите, [как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4bb4-110">Чтобы использовать архивацию для пользователей, размещенных в Lync Server 2013, необходимо настроить политики архивации, чтобы включить архивацию для внутренних коммуникаций, для внешних коммуникаций или для обоих.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-110">To use archiving for users who are homed on Lync Server 2013 you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="e4bb4-111">По умолчанию архивация не включена для внутренних и внешних коммуникаций.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="e4bb4-112">Прежде чем включать архивацию в любых политиках, необходимо указать соответствующие конфигурации архивации для развертывания и, при необходимости, для конкретных сайтов и пулов, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-112">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="e4bb4-113">Подробнее о том, как настроить архивацию, можно узнать в статье <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Настройка и назначение политик архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="e4bb4-114">Если вы решили после развертывания архивации, в которой вы хотите использовать интеграцию с Microsoft Exchange для хранения архивных данных и файлов на серверах Exchange 2013, а все пользователи размещены на серверах Exchange 2013, следует удалить конфигурацию базы данных SQL Server из топологии.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="e4bb4-115">Для этого необходимо использовать построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="e4bb4-116">Дополнительные сведения приведены в статье <A href="lync-server-2013-changing-archiving-database-options.md">изменение параметров базы данных архивации в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a><span data-ttu-id="e4bb4-117">Включение или отключение очистки для архивации</span><span class="sxs-lookup"><span data-stu-id="e4bb4-117">To enable or disable purging for archiving</span></span>

1.  <span data-ttu-id="e4bb4-118">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e4bb4-119">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e4bb4-120">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e4bb4-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e4bb4-121">В левой панели навигации щелкните **мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="e4bb4-122">В списке конфигураций архивации выберите название соответствующей глобальной конфигурации, конфигурации узла или пула, в меню **Правка** выберите пункт **Показать подробности** и затем сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-122">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="e4bb4-123">Чтобы включить очистку, установите флажок **Включить очистку данных архивации** и выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-123">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
        
          - <span data-ttu-id="e4bb4-124">Чтобы очистить все записи, щелкните **Очищать экспортированные и сохраненные данные архивации после максимального срока (дней)** и укажите число дней.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-124">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="e4bb4-125">Чтобы очистить только экспортированные данные, щелкните **Очищать только экспортированные данные архивации**.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-125">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
      - <span data-ttu-id="e4bb4-126">Чтобы отключить очистку, снимите флажок **Включить очистку данных архивации**.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-126">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>

5.  <span data-ttu-id="e4bb4-127">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-127">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e4bb4-128">Включение или отключение очистки данных архивации с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4bb4-128">Enabling or Disabling the Purging of Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e4bb4-129">Включение и отключение автоматической очистки данных архивации может осуществляться с помощью Windows PowerShell и командлета **Set – CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="e4bb4-129">Enabling and disabling the automated purging of archiving data can be managed by using Windows PowerShell and the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="e4bb4-130">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4bb4-130">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e4bb4-131">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="e4bb4-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a><span data-ttu-id="e4bb4-132">Включение очистки всех данных архивации</span><span class="sxs-lookup"><span data-stu-id="e4bb4-132">To enable the purging of all archiving data</span></span>

  - <span data-ttu-id="e4bb4-133">Чтобы включить очистку всех данных архивации, установите для свойства **EnablePurging** значение True ($True).</span><span class="sxs-lookup"><span data-stu-id="e4bb4-133">To enable the purging of all archiving data set the **EnablePurging** property to true ($True).</span></span> <span data-ttu-id="e4bb4-134">Пример:</span><span class="sxs-lookup"><span data-stu-id="e4bb4-134">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    <span data-ttu-id="e4bb4-135">После выполнения этой команды каждый день Lync Server будет очищать все записи архивации старше значения, указанного для свойства **KeepArchivingDataForDays** .</span><span class="sxs-lookup"><span data-stu-id="e4bb4-135">After this command is run, then every day Lync Server will purge all archiving records older than the value specified for the **KeepArchivingDataForDays** property.</span></span>

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a><span data-ttu-id="e4bb4-136">Включение очистки только экспортированных данных архивации</span><span class="sxs-lookup"><span data-stu-id="e4bb4-136">To enable the purging only of exported archiving data</span></span>

  - <span data-ttu-id="e4bb4-137">Чтобы ограничить удаление записями, экспортированными в файл данных (с помощью командлета [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) ), необходимо также задать для свойства Пуржеекспортедарчивесонли значение True ($true).</span><span class="sxs-lookup"><span data-stu-id="e4bb4-137">To limit purging to archiving records that have been exported to a data file (by using the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet) you must also set the PurgeExportedArchivesOnly property to True ($True).</span></span> <span data-ttu-id="e4bb4-138">Например:</span><span class="sxs-lookup"><span data-stu-id="e4bb4-138">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    <span data-ttu-id="e4bb4-139">После выполнения этой команды Lync Server будет очищать только записи архивации, соответствующие двум условиям: 1), которые старше значения, указанного для свойства **KeepArchivingDataForDays** ; и 2) они были экспортированы с помощью командлета **Export-CsArchivingData** .</span><span class="sxs-lookup"><span data-stu-id="e4bb4-139">After this command is run, Lync Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the **KeepArchivingDataForDays** property; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a><span data-ttu-id="e4bb4-140">Отключение очистки всех данных архивации</span><span class="sxs-lookup"><span data-stu-id="e4bb4-140">To disable the purging of all archiving data</span></span>

  - <span data-ttu-id="e4bb4-141">Чтобы отключить автоматическую очистку записей архивации, установите для свойства **EnablePurging** значение False ($False).</span><span class="sxs-lookup"><span data-stu-id="e4bb4-141">To disable the automated purging of archiving records, set the **EnablePurging** property to False ($False).</span></span> <span data-ttu-id="e4bb4-142">Пример:</span><span class="sxs-lookup"><span data-stu-id="e4bb4-142">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

<span data-ttu-id="e4bb4-143">Для получения дополнительных сведений, в том числе дополнительных вариантов очистки данных архивации, обратитесь к разделу "Справка" для командлета [Set – CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="e4bb4-143">For more information, including additional options for purging archiving data, see the help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4bb4-144">См. также</span><span class="sxs-lookup"><span data-stu-id="e4bb4-144">See Also</span></span>


[<span data-ttu-id="e4bb4-145">Принцип работы архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4bb4-145">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="e4bb4-146">Настройка и назначение политик архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4bb4-146">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[<span data-ttu-id="e4bb4-147">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="e4bb4-147">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

