---
title: 'Lync Server 2013: создание конфигурации архивации для управления архивацией определенных сайтов или пулов'
description: 'Lync Server 2013: создание конфигурации архивации для управления архивацией определенных сайтов или пулов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating an Archiving configuration to manage Archiving for specific sites or pools
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205251(v=OCS.15)
ms:contentKeyID: 48185361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ab19f2d8900693ef0fcb14d8f6d862b22c355bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563115"
---
# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a><span data-ttu-id="07e1c-103">Создание конфигурации архивации в Lync Server 2013 для управления архивацией определенных сайтов или пулов</span><span class="sxs-lookup"><span data-stu-id="07e1c-103">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07e1c-104">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="07e1c-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="07e1c-105">В панели управления Lync Server 2013 вы можете использовать конфигурации архивации для управления реализацией архивации в развертывании.</span><span class="sxs-lookup"><span data-stu-id="07e1c-105">In Lync Server 2013 Control Panel, you use Archiving configurations to control how archiving is implemented in your deployment.</span></span> <span data-ttu-id="07e1c-106">Это включает следующие конфигурации архивирования:</span><span class="sxs-lookup"><span data-stu-id="07e1c-106">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="07e1c-107">Глобальная конфигурация, создаваемая по умолчанию при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="07e1c-107">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="07e1c-108">Необязательные конфигурации на уровне сайта или пула, которые можно создать и использовать для указания того, как архивирование реализуется для определенных сайтов или пулов.</span><span class="sxs-lookup"><span data-stu-id="07e1c-108">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="07e1c-109">Начальная настройка конфигураций архивирования производится во время развертывания архивирования, но вы можете изменить, добавить и удалить конфигурации после развертывания.</span><span class="sxs-lookup"><span data-stu-id="07e1c-109">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="07e1c-110">Для получения дополнительных сведений о способах реализации конфигурации архивации, в том числе о том, какие параметры можно указать и иерархию конфигураций архивации, посмотрите, [как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="07e1c-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07e1c-111">Чтобы использовать архивацию, необходимо настроить политики архивации, чтобы включить архивацию для внутренних коммуникаций, для внешних коммуникаций или для пользователей, размещенных в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="07e1c-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="07e1c-112">По умолчанию архивирование не включено ни для внутренней, ни для внешней связи.</span><span class="sxs-lookup"><span data-stu-id="07e1c-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="07e1c-113">Перед включением архивирования в любой политике необходимо задать подходящие конфигурации архивирования для развертывания и, если требуется, для определенных сайтов и пулов, как описано в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="07e1c-113">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="07e1c-114">Подробнее о том, как настроить архивацию, можно узнать в статье <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Настройка и назначение политик архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="07e1c-114">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="07e1c-115">Если вы решили после развертывания архивации, в которой вы хотите использовать интеграцию с Microsoft Exchange для хранения архивных данных и файлов на серверах Exchange 2013, а все пользователи размещены на серверах Exchange 2013, следует удалить конфигурацию базы данных SQL Server из топологии.</span><span class="sxs-lookup"><span data-stu-id="07e1c-115">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="07e1c-116">Для этого необходимо использовать построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="07e1c-116">You must use Topology Builder to do this.</span></span> <span data-ttu-id="07e1c-117">Дополнительные сведения приведены в статье <A href="lync-server-2013-changing-archiving-database-options.md">изменение параметров базы данных архивации в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="07e1c-117">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a><span data-ttu-id="07e1c-118">Создание конфигурации архивирования для сайта или пула</span><span class="sxs-lookup"><span data-stu-id="07e1c-118">To create an archiving configuration for a site or pool</span></span>

1.  <span data-ttu-id="07e1c-119">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="07e1c-119">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="07e1c-120">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="07e1c-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="07e1c-121">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="07e1c-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="07e1c-122">В левой панели навигации щелкните **мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="07e1c-122">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="07e1c-123">На странице **Конфигурация архивирования** щелкните **Создать**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="07e1c-123">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="07e1c-124">Чтобы создать конфигурацию архивирования сайта, щелкните элемент **Конфигурация сайта**, а затем в разделе **выбора сайта** выберите сайт, который требуется настроить для архивирования.</span><span class="sxs-lookup"><span data-stu-id="07e1c-124">To create a site archiving configuration, click **Site Configuration** and then, in **Select a site**, select the site to be configured for archiving.</span></span>
    
      - <span data-ttu-id="07e1c-125">Чтобы создать конфигурацию архивирования пула, щелкните элемент **Конфигурация пула**, а затем в разделе **выбора пула** выберите пул, который требуется настроить для архивирования.</span><span class="sxs-lookup"><span data-stu-id="07e1c-125">To create a pool archiving configuration, click **Pool Configuration** and then, in **Select a pool**, select the pool to be configured for archiving.</span></span>

5.  <span data-ttu-id="07e1c-126">В разделе **Новый параметр архивирования**, в раскрывающемся списке **Параметр архивирования** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="07e1c-126">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="07e1c-127">Чтобы включить архивирование только для сеансов обмена мгновенными сообщениями, щелкните **Архивировать сеансы обмена мгновенными сообщениями**.</span><span class="sxs-lookup"><span data-stu-id="07e1c-127">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="07e1c-128">Чтобы включить архивирование для обмена мгновенными сообщениями и веб-конференций, щелкните элемент **Archive IM and web conferencing sessions** (Архивировать сеансы обмена мгновенными сообщениями и веб-конференций).</span><span class="sxs-lookup"><span data-stu-id="07e1c-128">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="07e1c-129">Чтобы отключить политику архивирования, щелкните **Отключить архивирование**.</span><span class="sxs-lookup"><span data-stu-id="07e1c-129">To disable archiving for the policy, click **Disable archiving**.</span></span>

6.  <span data-ttu-id="07e1c-130">Также в разделе **Новый параметр архивирования** выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="07e1c-130">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="07e1c-131">Чтобы заблокировать действия, когда архивирование невозможно, установите флажок **Block instant messaging (IM) or web conferencing sessions if archiving fails** (Блокировать сеансы обмена мгновенными сообщениями или веб-конференций, если не удается выполнить архивирование).</span><span class="sxs-lookup"><span data-stu-id="07e1c-131">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="07e1c-132">Чтобы использовать Microsoft Exchange Server для хранения архивных данных, установите флажок **интеграция Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="07e1c-132">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="07e1c-133">Чтобы включить удаление данных, установите флажок **Включить удаление архивных данных**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="07e1c-133">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="07e1c-134">Чтобы задать удаление после определенного числа дней, щелкните **Удалять экспортированные архивные данные и сохраненные архивные данные максимум в течение (дней)**, а затем задайте число дней.</span><span class="sxs-lookup"><span data-stu-id="07e1c-134">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="07e1c-135">Чтобы ограничить удаление только теми данными, которые были экспортированы, щелкните **Удалять только экспортированные архивные данные**.</span><span class="sxs-lookup"><span data-stu-id="07e1c-135">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="07e1c-136">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="07e1c-136">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="07e1c-137">Создание параметров конфигурации архивации с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="07e1c-137">Creating Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="07e1c-138">Параметры конфигурации архивации можно создать с помощью Windows PowerShell и командлета New-CsArchivingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="07e1c-138">Archiving configuration settings can be created by using Windows PowerShell and the New-CsArchivingConfiguration cmdlet.</span></span> <span data-ttu-id="07e1c-139">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07e1c-139">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="07e1c-140">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="07e1c-140">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a><span data-ttu-id="07e1c-141">Создание новой коллекции параметров конфигурации архивации для сайта</span><span class="sxs-lookup"><span data-stu-id="07e1c-141">To create a new collection of archiving configuration settings for a site</span></span>

  - <span data-ttu-id="07e1c-142">Следующая команда создает новую коллекцию параметров конфигурации архивации для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="07e1c-142">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a><span data-ttu-id="07e1c-143">Создание новой коллекции параметров конфигурации архивации, которые разрешают только архивацию мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="07e1c-143">To create a new collection of archiving configuration settings that only allow IM archiving</span></span>

  - <span data-ttu-id="07e1c-p107">Поскольку в предыдущей команде не было указано никаких параметров, кроме обязательного параметра Identity, новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств. Чтобы создать параметры, использующие другие значения свойств, просто включите соответствующий параметр и его значение. Например, чтобы создать коллекцию параметров конфигурации архивации, которая по умолчанию разрешает только архивацию сеансов обмена мгновенными сообщениями, используйте команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="07e1c-p107">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions, only use a command like this:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a><span data-ttu-id="07e1c-147">Указание нескольких значений свойств при создании параметров конфигурации архивации</span><span class="sxs-lookup"><span data-stu-id="07e1c-147">To specify multiple property values when creating archiving configuration settings</span></span>

  - <span data-ttu-id="07e1c-p108">Чтобы изменить несколько значений свойств, можно включить несколько параметров. Например, следующая команда настраивает новые параметры для архивации сеансов обмена мгновенными сообщениями и для блокирования обмена мгновенными сообщениями при недоступности службы архивации:</span><span class="sxs-lookup"><span data-stu-id="07e1c-p108">Multiple property values can be modified by including multiple parameters. For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

<span data-ttu-id="07e1c-150">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [New – CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="07e1c-150">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="07e1c-151">См. также</span><span class="sxs-lookup"><span data-stu-id="07e1c-151">See Also</span></span>


[<span data-ttu-id="07e1c-152">Принцип работы архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07e1c-152">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="07e1c-153">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="07e1c-153">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

