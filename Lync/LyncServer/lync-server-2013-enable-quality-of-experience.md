---
title: 'Lync Server 2013: включение качества взаимодействия'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 558e7cfef48a472b4fd9ab7f538197313a8f112a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a><span data-ttu-id="55968-102">Обеспечение качества взаимодействия в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55968-102">Enable Quality of Experience in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55968-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="55968-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="55968-104">Служба отслеживания качества взаимодействия (QoE) записывает числовые данные, которые показывают качество мультимедиа-данных, и сведения об участниках, именах устройств, драйверах, IP-адресах и типах конечных точек, использованных во время звонка или сеанса.</span><span class="sxs-lookup"><span data-stu-id="55968-104">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="55968-105">Подробности можно найти [в разделе Планирование мониторинга в Lync Server 2013](lync-server-2013-planning-for-monitoring.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="55968-105">For details, see [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) in the Planning documentation.</span></span>

<span data-ttu-id="55968-106">Используйте следующую процедуру для включения службы качества взаимодействия для всей организации или для отдельных сайтов в организации.</span><span class="sxs-lookup"><span data-stu-id="55968-106">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55968-107">Чтобы включить службу качества взаимодействия, сначала необходимо настроить мониторинг и внутреннюю базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="55968-107">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="55968-108">Подробные сведения можно найти <A href="lync-server-2013-deploying-monitoring.md">в разделе Развертывание мониторинга в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="55968-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a><span data-ttu-id="55968-109">Включение QoE с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="55968-109">To enable QoE by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="55968-110">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55968-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="55968-111">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="55968-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="55968-112">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="55968-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="55968-113">На панели навигации слева нажмите **Мониторинг и архивация**, затем выберите **Данные о качестве взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="55968-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="55968-114">На странице **данных качества взаимодействия** выберите соответствующую коллекцию в таблице и последовательно выберите пункты **Действие** и **Включить отслеживание качества взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="55968-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="55968-115">Включение QoE с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="55968-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="55968-116">Вы можете включить QoE с помощью Windows PowerShell и командлета **Set-кскоеконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="55968-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="55968-117">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55968-117">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="55968-118">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55968-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="55968-119">Включение службы качества взаимодействия для одного расположения</span><span class="sxs-lookup"><span data-stu-id="55968-119">To enable QoE for a single location</span></span>

  - <span data-ttu-id="55968-120">Чтобы включить службу качества взаимодействия, установите параметр EnableQoE в значение True ($True).</span><span class="sxs-lookup"><span data-stu-id="55968-120">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="55968-121">Отключение службы качества взаимодействия для одного расположения</span><span class="sxs-lookup"><span data-stu-id="55968-121">To disable QoE for a single location</span></span>

  - <span data-ttu-id="55968-p105">Чтобы отключить службу качества взаимодействия, установите параметр EnableQoE в значение False ($False). При этом мониторинг не будет удален. Он приостановит сбор и хранение данных качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="55968-p105">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="55968-125">Использование одной команды для включения службы качества взаимодействия в нескольких расположениях</span><span class="sxs-lookup"><span data-stu-id="55968-125">To use a single command to enable QoE in multiple locations</span></span>

  - <span data-ttu-id="55968-126">Следующая команда включает службу качества взаимодействия для всех параметров конфигурации качества взаимодействия, используемых в текущий момент в организации.</span><span class="sxs-lookup"><span data-stu-id="55968-126">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

<span data-ttu-id="55968-127">Подробности можно найти в разделе [Set-кскоеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span><span class="sxs-lookup"><span data-stu-id="55968-127">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="55968-128">См. также</span><span class="sxs-lookup"><span data-stu-id="55968-128">See Also</span></span>


[<span data-ttu-id="55968-129">Планирование мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55968-129">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="55968-130">Развертывание мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55968-130">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

