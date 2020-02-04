---
title: 'Lync Server 2013: Включение и отключение очистки архивированных данных'
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
ms.openlocfilehash: 3b06d21cc0154ea57bc028c87c835e4de9a00f1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a><span data-ttu-id="df75a-102">Включение и отключение очистки архивированных данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df75a-102">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df75a-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="df75a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="df75a-104">В панели управления Lync Server 2013 вы можете включать и отключать очистку с помощью конфигураций архивации, а также настраивать способ реализации очистки.</span><span class="sxs-lookup"><span data-stu-id="df75a-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable purging and configure how purging is implemented.</span></span> <span data-ttu-id="df75a-105">К ним относятся следующие конфигурации архивации:</span><span class="sxs-lookup"><span data-stu-id="df75a-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="df75a-106">Глобальная конфигурация, создаваемая по умолчанию при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df75a-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="df75a-107">Необязательные конфигурации уровня сайта и пула, которые можно создать и использовать для определения способа реализации архивации для конкретных сайтов или пулов.</span><span class="sxs-lookup"><span data-stu-id="df75a-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="df75a-108">Первоначально конфигурации архивации задаются при развертывании архивации, но вы можете изменить, добавить и удалить настройки после развертывания.</span><span class="sxs-lookup"><span data-stu-id="df75a-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="df75a-109">Сведения о том, как работают конфигурации архивации, в том числе о параметрах, которые можно указать и в иерархии конфигураций архивации, описаны в разделе [Использование архивации в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="df75a-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df75a-110">Чтобы использовать архивацию для пользователей, использующих Lync Server 2013, необходимо настроить политики архивации, чтобы указать, следует ли включать архивирование для внутренней связи, для внешней связи или для обоих.</span><span class="sxs-lookup"><span data-stu-id="df75a-110">To use archiving for users who are homed on Lync Server 2013 you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="df75a-111">По умолчанию архивация не включена для внутренней и внешней связи.</span><span class="sxs-lookup"><span data-stu-id="df75a-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="df75a-112">Перед включением архивации в любых политиках следует задать соответствующие конфигурации архивации для развертывания и (необязательно) для определенных сайтов и пулов, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="df75a-112">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="df75a-113">Подробнее о том, как включить архивацию, можно найти <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">в разделе Настройка и назначение политик архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="df75a-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="df75a-114">Если вы решите, что после развертывания архивации вы хотите использовать интеграцию с Microsoft Exchange для хранения данных и файлов на серверах Exchange 2013, а все пользователи будут размещены на серверах Exchange 2013, необходимо удалить конфигурацию базы данных SQL Server. из топологии.</span><span class="sxs-lookup"><span data-stu-id="df75a-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="df75a-115">Для этого необходимо использовать Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="df75a-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="df75a-116">Подробнее смотрите в разделе <A href="lync-server-2013-changing-archiving-database-options.md">изменение параметров базы данных для архивации в Lync Server 2013</A> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="df75a-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a><span data-ttu-id="df75a-117">Включение и отключение очистки для архивации</span><span class="sxs-lookup"><span data-stu-id="df75a-117">To enable or disable purging for archiving</span></span>

1.  <span data-ttu-id="df75a-118">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="df75a-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="df75a-119">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df75a-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="df75a-120">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="df75a-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="df75a-121">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="df75a-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="df75a-122">В списке конфигураций архивации щелкните имя подходящей глобальной конфигурации либо конфигурации сайта или пула, щелкните **Изменить** и **Показать подробности**, затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="df75a-122">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="df75a-123">Для включения функции удаления данных установите флажок **Разрешить удаление данных архивации**, затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="df75a-123">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
        
          - <span data-ttu-id="df75a-124">Для удаления всех записей выберите **Очищать экспортированные данные архивации, а также данные архивации по окончании максимального срока хранения (дн.)**, затем укажите количество дней.</span><span class="sxs-lookup"><span data-stu-id="df75a-124">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="df75a-125">Для удаления только экспортированных данных выберите **Удалять только экспортированные данные архивации**.</span><span class="sxs-lookup"><span data-stu-id="df75a-125">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
      - <span data-ttu-id="df75a-126">Для отключения функции удаления данных снимите флажок **Разрешить удаление данных архивации**.</span><span class="sxs-lookup"><span data-stu-id="df75a-126">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>

5.  <span data-ttu-id="df75a-127">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="df75a-127">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="df75a-128">Включение и отключение очистки данных архивации с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="df75a-128">Enabling or Disabling the Purging of Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="df75a-129">Включение и отключение автоматической очистки данных архивации может осуществляться с помощью Windows PowerShell и командлета **Set-ксарчивингконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="df75a-129">Enabling and disabling the automated purging of archiving data can be managed by using Windows PowerShell and the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="df75a-130">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df75a-130">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="df75a-131">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df75a-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a><span data-ttu-id="df75a-132">Включение очистки всех данных архивации</span><span class="sxs-lookup"><span data-stu-id="df75a-132">To enable the purging of all archiving data</span></span>

  - <span data-ttu-id="df75a-133">Чтобы включить очистку всех данных архивации, задайте для свойства **енаблепургинг** значение true ($true).</span><span class="sxs-lookup"><span data-stu-id="df75a-133">To enable the purging of all archiving data set the **EnablePurging** property to true ($True).</span></span> <span data-ttu-id="df75a-134">Например:</span><span class="sxs-lookup"><span data-stu-id="df75a-134">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    <span data-ttu-id="df75a-135">После запуска этой команды каждый день на сервере Lync Server будут очищены все записи архивации, предшествующие значению, указанному в свойстве **кипарчивингдатафордайс** .</span><span class="sxs-lookup"><span data-stu-id="df75a-135">After this command is run, then every day Lync Server will purge all archiving records older than the value specified for the **KeepArchivingDataForDays** property.</span></span>

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a><span data-ttu-id="df75a-136">Включение очистки только для экспортированных данных архивации</span><span class="sxs-lookup"><span data-stu-id="df75a-136">To enable the purging only of exported archiving data</span></span>

  - <span data-ttu-id="df75a-137">Чтобы ограничить удаление записями, которые были экспортированы в файл данных (с помощью командлета [Export-ксарчивингдата](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) ), необходимо также задать для свойства Пуржеекспортедарчивесонли значение True ($true).</span><span class="sxs-lookup"><span data-stu-id="df75a-137">To limit purging to archiving records that have been exported to a data file (by using the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet) you must also set the PurgeExportedArchivesOnly property to True ($True).</span></span> <span data-ttu-id="df75a-138">Например:</span><span class="sxs-lookup"><span data-stu-id="df75a-138">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    <span data-ttu-id="df75a-139">После запуска этой команды Lync Server будет очищать только те записи, которые удовлетворяют двум условиям: 1), чем значение, указанное в свойстве **кипарчивингдатафордайс** ; и 2) они экспортированы с помощью командлета **Export-ксарчивингдата** .</span><span class="sxs-lookup"><span data-stu-id="df75a-139">After this command is run, Lync Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the **KeepArchivingDataForDays** property; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a><span data-ttu-id="df75a-140">Отключение очистки всех данных архивации</span><span class="sxs-lookup"><span data-stu-id="df75a-140">To disable the purging of all archiving data</span></span>

  - <span data-ttu-id="df75a-141">Чтобы отключить автоматическую очистку записей архивации, установите для свойства **Енаблепургинг** значение False ($false).</span><span class="sxs-lookup"><span data-stu-id="df75a-141">To disable the automated purging of archiving records, set the **EnablePurging** property to False ($False).</span></span> <span data-ttu-id="df75a-142">Например:</span><span class="sxs-lookup"><span data-stu-id="df75a-142">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

<span data-ttu-id="df75a-143">Дополнительные сведения, в том числе дополнительные параметры очистки данных для архивации, можно найти в разделе справки по командлету [Set-ксарчивингконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="df75a-143">For more information, including additional options for purging archiving data, see the help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="df75a-144">См. также</span><span class="sxs-lookup"><span data-stu-id="df75a-144">See Also</span></span>


[<span data-ttu-id="df75a-145">Как работает архивация в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df75a-145">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="df75a-146">Настройка и назначение политик архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df75a-146">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[<span data-ttu-id="df75a-147">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="df75a-147">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

