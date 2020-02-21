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
ms.openlocfilehash: d6d41e5959eaf596faaed25a9759534a9156f0d9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a>Связывание подсети с сетевым сайтом в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-19_

Каждая подсеть должна быть связана с определенным сетевым сайтом, так как при установлении нового сеанса данные подсети используются для определения сетевого сайта, в котором расположена конечная точка. Когда расположение каждой стороны в сеансе известно, расширенные функции корпоративной голосовой связи могут применять эти сведения для определения способа обработки настройки и маршрутизации звонков.

<div>


> [!IMPORTANT]  
> Все настроенные общедоступные IP-адреса пограничных пограничных серверов аудио-и видеоданных в развертывании должны быть добавлены в параметры конфигурации сети. Эти IP-адреса добавляются в виде подсетей с маской 32. Связанный сетевой сайт должен соответствовать соответствующему настроенному сетевому сайту. Например, общедоступный IP-адрес, соответствующий пограничный сервер аудио-и видеоданных в центральном сайте Чикаго, будет NetworkSiteID в Чикаго. Подробнее об общедоступных IP-адресах можно узнать в статье <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Определение требований к портам внешнего аудио-и видеоподключения для Lync Server 2013</A> в документации по планированию.



</div>

<div>


> [!NOTE]  
> Для указания списка IP-адресов, которые не связаны ни с одной подсетью, или подсети, которая не связана ни с одним сетевым сайтом, вызывается оповещение Key Health Indicator (основной индикатор работоспособности). Минимальный интервал вызова оповещения составляет 8 часов. Ниже приведены сведения об оповещении и пример:<BR><STRONG>Источник:</STRONG> Служба политики пропускной способности CS (ядро)<BR><STRONG>Номер события:</STRONG> 36034<BR><STRONG>Уровень:</STRONG> 2<BR><STRONG>Description:</STRONG> Подсети для следующих IP-адресов: &lt;список IP-адресов&gt; либо не настроен, либо подсети не связаны с сетевым сайтом.<BR><STRONG>Причина:</STRONG> Подсети для соответствующих IP-адресов отсутствуют в параметрах конфигурации сети, или подсети не связаны с сетевым сайтом.<BR><STRONG>Решение:</STRONG> Добавьте подсети, соответствующие списку IP-адресов, в параметры конфигурации сети и свяжите каждую подсеть с сетевым сайтом.<BR>Например, если в оповещении указаны IP-адреса 10.121.248.226 и 10.121.249.20, либо эти IP-адреса не связаны с подсетью, либо подсеть, с которой связаны эти адреса, не принадлежит сетевому узлу. Если этим адресам соответствуют подсети 10.121.248.0/24 и 10.121.249.0/24, то для решения этой проблемы выполните следующие действия: 
> <OL>
> <LI>
> <P>Убедитесь в том, что IP-адрес 10.121.248.226 связан с подсетью 10.121.248.0/24, а IP-адрес 10.121.249.20 — с подсетью 10.121.249.0/24.</P>
> <LI>
> <P>убедитесь, что подсети 10.121.249.0/24 и 10.121.248.0/24 связаны с сетевым узлом.</P></LI></OL>



</div>

Для получения подробных сведений о работе с подсетями сети обратитесь к документации по командной консоли Lync Server для следующих командлетов:

  - [New — CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [Get — CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [Set — CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [Remove — CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> Если нужно связать большое число подсетей с сетевыми сайтами, мы рекомендуем использовать файл данных с разделителями-запятыми (CSV-файл). CSV-файл должен содержать 4 столбца: <STRONG>IPAddress</STRONG> (IP-адрес), <STRONG>mask</STRONG> (маска), <STRONG>description</STRONG> (описание) и <STRONG>NetworkSiteID</STRONG> (ИД сетевого сайта).



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a>Связывание подсети с сетевым сайтом с помощью командной консоли

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы связать подсеть с сетевым сайтом, используйте командлет **New-CsNetworkSubnet**:
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    Пример:
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    В этом примере создается связь между подсетью 172.11.12.13 и сетевым узлом Chicago (Чикаго).

3.  Повторите шаг 2 для всех подсетей топологии.

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>Связывание подсетей с сетевыми узлами путем импорта CSV-файла

1.  Создайте CSV-файл, содержащий все добавляемые подсети. Например, создайте файл с именем **subnet.csv**, содержащий следующие данные:
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполните следующий командлет, чтобы импортировать файл **Subnet. csv**, а затем сохраните его содержимое в хранилище управления Lync Server.
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a>Связывание подсети с сетевым сайтом с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой панели навигации щелкните **Network Configuration** (Параметры сети).

3.  Нажмите кнопку навигации **Subnet** (Подсеть).

4.  Щелкните **New** (Создать).

5.  На странице **New Subnet** (Создание подсети) щелкните **Subnet ID** (ИД подсети) и затем введите первый адрес диапазона IP-адресов подсети, которую требуется связать с сетевым узлом.

6.  Щелкните **Mask** (Маска) и затем введите битовую маску, применяемую к подсети.

7.  Щелкните **ИД сетевого узла** и затем выберите ИД узла, в который необходимо добавить эту подсеть.
    
    <div>
    

    > [!NOTE]  
    > Если вы еще не создали сетевые сайты, то этот список будет пустым. Для получения дополнительных сведений о процедуре обратитесь к разделу <A href="lync-server-2013-create-or-modify-a-network-site.md">Создание или изменение сетевого сайта в Lync Server 2013</A>. Также для получения ИД сетевых сайтов можно использовать командлет <STRONG>Get-CsNetworkSite</STRONG>. Дополнительные сведения см. в документации Lync Server Management Shell.

    
    </div>

8.  В поле **Description** (Описание) введите дополнительные сведения об этой подсети.

9.  Щелкните **Commit** (Применить).

Повторите эти действия, чтобы добавить остальные подсети в сетевой узел.

</div>

</div>

<span> </span>

</div>

</div>

</div>

