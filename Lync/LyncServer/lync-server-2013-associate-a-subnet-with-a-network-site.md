---
title: 'Lync Server 2013: связывание подсети с сетевым сайтом'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f961fef4fb9323c0eef642e4b7e70ede5da4ccf2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532746"
---
# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a><span data-ttu-id="b3b72-102">Связывание подсети с сетевым сайтом в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3b72-102">Associate a subnet with a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3b72-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b3b72-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b3b72-104">Каждая подсеть должна быть связана с определенным сетевым сайтом, так как при установлении нового сеанса данные подсети используются для определения сетевого сайта, в котором расположена конечная точка.</span><span class="sxs-lookup"><span data-stu-id="b3b72-104">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="b3b72-105">Когда расположение каждой стороны в сеансе известно, расширенные функции корпоративной голосовой связи могут применять эти сведения для определения способа обработки настройки и маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="b3b72-105">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b3b72-106">Все настроенные общедоступные IP-адреса пограничных пограничных серверов аудио-и видеоданных в развертывании должны быть добавлены в параметры конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="b3b72-106">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="b3b72-107">Эти IP-адреса добавляются в виде подсетей с маской 32.</span><span class="sxs-lookup"><span data-stu-id="b3b72-107">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="b3b72-108">Связанный сетевой сайт должен соответствовать соответствующему настроенному сетевому сайту.</span><span class="sxs-lookup"><span data-stu-id="b3b72-108">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="b3b72-109">Например, общедоступный IP-адрес, соответствующий пограничный сервер аудио-и видеоданных в центральном сайте Чикаго, будет NetworkSiteID в Чикаго.</span><span class="sxs-lookup"><span data-stu-id="b3b72-109">For example, the public IP address that corresponds to the A/V Edge Server in central site Chicago would be NetworkSiteID Chicago.</span></span> <span data-ttu-id="b3b72-110">Подробнее об общедоступных IP-адресах можно узнать в статье <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Определение требований к портам внешнего аудио-и видеоподключения для Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="b3b72-110">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b3b72-p103">Для указания списка IP-адресов, которые не связаны ни с одной подсетью, или подсети, которая не связана ни с одним сетевым сайтом, вызывается оповещение Key Health Indicator (основной индикатор работоспособности). Минимальный интервал вызова оповещения составляет 8 часов. Ниже приведены сведения об оповещении и пример:</span><span class="sxs-lookup"><span data-stu-id="b3b72-p103">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8-hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="b3b72-114"><STRONG>Источник:</STRONG> Служба политики пропускной способности CS (ядро)</span><span class="sxs-lookup"><span data-stu-id="b3b72-114"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="b3b72-115"><STRONG>Номер события:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="b3b72-115"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="b3b72-116"><STRONG>Уровень:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="b3b72-116"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="b3b72-117"><STRONG>Description:</STRONG> Подсети для следующих IP-адресов: &lt; список IP-адресов &gt; либо не настроен, либо подсети не связаны с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="b3b72-117"><STRONG>Description:</STRONG> The subnets for the following IP addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a Network Site.</span></span><BR><span data-ttu-id="b3b72-118"><STRONG>Причина:</STRONG> Подсети для соответствующих IP-адресов отсутствуют в параметрах конфигурации сети, или подсети не связаны с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="b3b72-118"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="b3b72-119"><STRONG>Решение:</STRONG> Добавьте подсети, соответствующие списку IP-адресов, в параметры конфигурации сети и свяжите каждую подсеть с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="b3b72-119"><STRONG>Resolution:</STRONG> Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="b3b72-p104">Например, если в оповещении указаны IP-адреса 10.121.248.226 и 10.121.249.20, либо эти IP-адреса не связаны с подсетью, либо подсеть, с которой связаны эти адреса, не принадлежит сетевому узлу. Если этим адресам соответствуют подсети 10.121.248.0/24 и 10.121.249.0/24, то для решения этой проблемы выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b3b72-p104">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="b3b72-122">Убедитесь в том, что IP-адрес 10.121.248.226 связан с подсетью 10.121.248.0/24, а IP-адрес 10.121.249.20 — с подсетью 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="b3b72-122">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
> <LI>
> <P><span data-ttu-id="b3b72-123">убедитесь, что подсети 10.121.249.0/24 и 10.121.248.0/24 связаны с сетевым узлом.</span><span class="sxs-lookup"><span data-stu-id="b3b72-123">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>



</div>

<span data-ttu-id="b3b72-124">Для получения подробных сведений о работе с подсетями сети обратитесь к документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="b3b72-124">For details about working with network subnets, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="b3b72-125">New — CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b3b72-125">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [<span data-ttu-id="b3b72-126">Get — CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b3b72-126">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [<span data-ttu-id="b3b72-127">Set — CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b3b72-127">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [<span data-ttu-id="b3b72-128">Remove — CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b3b72-128">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> <span data-ttu-id="b3b72-p105">Если нужно связать большое число подсетей с сетевыми сайтами, мы рекомендуем использовать файл данных с разделителями-запятыми (CSV-файл). CSV-файл должен содержать 4 столбца: <STRONG>IPAddress</STRONG> (IP-адрес), <STRONG>mask</STRONG> (маска), <STRONG>description</STRONG> (описание) и <STRONG>NetworkSiteID</STRONG> (ИД сетевого сайта).</span><span class="sxs-lookup"><span data-stu-id="b3b72-p105">If you are working with a large number of subnets, we recommend using a comma-separated values (CSV) file to associate the subnets to sites. The CSV file must have the following four columns: <STRONG>IPAddress</STRONG>, <STRONG>mask</STRONG>, <STRONG>description</STRONG>, <STRONG>NetworkSiteID</STRONG>.</span></span>



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a><span data-ttu-id="b3b72-131">Связывание подсети с сетевым сайтом с помощью командной консоли</span><span class="sxs-lookup"><span data-stu-id="b3b72-131">To associate a subnet with a network site by using Management Shell</span></span>

1.  <span data-ttu-id="b3b72-132">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b3b72-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b3b72-133">Чтобы связать подсеть с сетевым сайтом, используйте командлет **New-CsNetworkSubnet**:</span><span class="sxs-lookup"><span data-stu-id="b3b72-133">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    <span data-ttu-id="b3b72-134">Пример:</span><span class="sxs-lookup"><span data-stu-id="b3b72-134">For example:</span></span>
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    <span data-ttu-id="b3b72-135">В этом примере создается связь между подсетью 172.11.12.13 и сетевым узлом Chicago (Чикаго).</span><span class="sxs-lookup"><span data-stu-id="b3b72-135">In this example, you created an association between the subnet 172.11.12.13 and the network site “Chicago”.</span></span>

3.  <span data-ttu-id="b3b72-136">Повторите шаг 2 для всех подсетей топологии.</span><span class="sxs-lookup"><span data-stu-id="b3b72-136">Repeat step 2 for all subnets in your topology.</span></span>

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="b3b72-137">Связывание подсетей с сетевыми узлами путем импорта CSV-файла</span><span class="sxs-lookup"><span data-stu-id="b3b72-137">To associate subnets with network sites by importing a CSV file</span></span>

1.  <span data-ttu-id="b3b72-p106">Создайте CSV-файл, содержащий все добавляемые подсети. Например, создайте файл с именем **subnet.csv**, содержащий следующие данные:</span><span class="sxs-lookup"><span data-stu-id="b3b72-p106">Create a CSV file that includes all of the subnets you want to add. For example, create a file named **subnet.csv** with the following content:</span></span>
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  <span data-ttu-id="b3b72-140">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b3b72-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b3b72-141">Выполните следующий командлет, чтобы импортировать **subnet.csv**, а затем сохраните его содержимое в хранилище управления Lync Server:</span><span class="sxs-lookup"><span data-stu-id="b3b72-141">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="b3b72-142">Связывание подсети с сетевым сайтом с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="b3b72-142">To associate a subnet with a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b3b72-143">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3b72-143">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b3b72-144">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b3b72-144">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="b3b72-145">В левой панели навигации щелкните **Network Configuration** (Параметры сети).</span><span class="sxs-lookup"><span data-stu-id="b3b72-145">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="b3b72-146">Нажмите кнопку навигации **Subnet** (Подсеть).</span><span class="sxs-lookup"><span data-stu-id="b3b72-146">Click the **Subnet** navigation button.</span></span>

4.  <span data-ttu-id="b3b72-147">Щелкните **New** (Создать).</span><span class="sxs-lookup"><span data-stu-id="b3b72-147">Click **New**.</span></span>

5.  <span data-ttu-id="b3b72-148">На странице **New Subnet** (Создание подсети) щелкните **Subnet ID** (ИД подсети) и затем введите первый адрес диапазона IP-адресов подсети, которую требуется связать с сетевым узлом.</span><span class="sxs-lookup"><span data-stu-id="b3b72-148">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6.  <span data-ttu-id="b3b72-149">Щелкните **Mask** (Маска) и затем введите битовую маску, применяемую к подсети.</span><span class="sxs-lookup"><span data-stu-id="b3b72-149">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7.  <span data-ttu-id="b3b72-150">Щелкните **ИД сетевого узла** и затем выберите ИД узла, в который необходимо добавить эту подсеть.</span><span class="sxs-lookup"><span data-stu-id="b3b72-150">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b3b72-151">Если вы еще не создали сетевые сайты, то этот список будет пустым.</span><span class="sxs-lookup"><span data-stu-id="b3b72-151">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="b3b72-152">Для получения дополнительных сведений о процедуре обратитесь к разделу <A href="lync-server-2013-create-or-modify-a-network-site.md">Создание или изменение сетевого сайта в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b3b72-152">For details about the procedure, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="b3b72-153">Также для получения ИД сетевых сайтов можно использовать командлет <STRONG>Get-CsNetworkSite</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b3b72-153">You can also retrieve site IDs for your deployment by running the <STRONG>Get-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="b3b72-154">Дополнительные сведения см. в документации Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b3b72-154">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="b3b72-155">В поле **Description** (Описание) введите дополнительные сведения об этой подсети.</span><span class="sxs-lookup"><span data-stu-id="b3b72-155">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9.  <span data-ttu-id="b3b72-156">Щелкните **Commit** (Применить).</span><span class="sxs-lookup"><span data-stu-id="b3b72-156">Click **Commit**.</span></span>

<span data-ttu-id="b3b72-157">Повторите эти действия, чтобы добавить остальные подсети в сетевой узел.</span><span class="sxs-lookup"><span data-stu-id="b3b72-157">Repeat these steps to add other subnets to a network site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

