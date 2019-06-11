---
title: 'Lync Server 2013: связь подсети с сетевым сайтом'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec5a896af6312fecf53259ac10e72f99598d4a7e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a>Связь подсети с сетевым сайтом в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-19_

Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated. Когда вы узнаете о расположении каждой стороны в сеансе, опытные функции голосовой связи могут применять эти данные, чтобы определить способ обработки настройки и маршрутизации звонков.

<div>


> [!IMPORTANT]  
> All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings. These IP addresses are added as subnets with a mask of 32. The associated network site should correspond to the appropriate configured network site. Например, общедоступный IP-адрес, соответствующий пограничным серверам A/V на центральном веб-сайте Чикаго, будет Нетворкситеид в Чикаго. Дополнительные сведения об общедоступных IP-адресах можно найти в статьях <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Определение внешних параметров брандмауэра/V и портов для Lync Server 2013</A> в документации по планированию.



</div>

<div>


> [!NOTE]  
> Для указания списка IP-адресов, которые не связаны ни с одной подсетью, или подсети, которая не связана ни с одним сетевым сайтом, вызывается оповещение Key Health Indicator (основной индикатор работоспособности). Минимальный интервал вызова оповещения составляет 8 часов. Ниже приведены сведения об оповещении и пример:<BR><STRONG>Источник:</STRONG> Служба политики пропускной способности CS (ядро)<BR><STRONG>Номер события:</STRONG> 36034<BR><STRONG>Уровень:</STRONG> 2<BR><STRONG>Описание:</STRONG> Подсети для указанных ниже IP-адресов: &lt;список IP-адресов&gt; либо не настроен, либо подсети не связаны с сетевым сайтом.<BR><STRONG>Причина:</STRONG> В параметрах сетевой конфигурации отсутствуют подсети для соответствующих IP-адресов, или подсети не связаны с сетевым сайтом.<BR><STRONG>Решение:</STRONG> Добавьте подсети, соответствующие списку IP-адресов, в параметры конфигурации сети и свяжите каждую подсеть с сайтом сети.<BR>Например, если в оповещении указаны IP-адреса 10.121.248.226 и 10.121.249.20, либо эти IP-адреса не связаны с подсетью, либо подсеть, с которой связаны эти адреса, не принадлежит сетевому узлу. Если этим адресам соответствуют подсети 10.121.248.0/24 и 10.121.249.0/24, то для решения этой проблемы выполните следующие действия: 
> <OL>
> <LI>
> <P>Убедитесь в том, что IP-адрес 10.121.248.226 связан с подсетью 10.121.248.0/24, а IP-адрес 10.121.249.20 — с подсетью 10.121.249.0/24.</P>
> <LI>
> <P>Убедитесь, в том что обе подсети 10.121.248.0/24 и 10.121.249.0/24 связаны с сетевым сайтом.</P></LI></OL>



</div>

Дополнительные сведения о работе с сетевыми подсетями можно найти в документации по оболочке Lync Server Management Shell для следующих командлетов:

  - [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> Если вы работаете с большим количеством подсетей, рекомендуется использовать CSV-файл, чтобы связать подсети с сайтами. В CSV-файле должны быть четыре столбца: <STRONG>IPAddress</STRONG>, <STRONG>Маска</STRONG>, <STRONG>Описание</STRONG>, <STRONG>нетворкситеид</STRONG>.



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a>Связывание подсети с сетевым сайтом с помощью командной консоли

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Чтобы связать подсеть с сетевым сайтом, используйте командлет **New-CsNetworkSubnet**:
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    Например:
    
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

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Выполните следующий командлет для импорта **Subnet. csv**, а затем сохраните его содержимое в магазине Lync Server Management.
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a>Связывание подсети с сетевым сайтом с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой области навигации щелкните элемент **Конфигурация сети**.

3.  Нажмите кнопку навигации **Подсеть**.

4.  Выберите **Создать**.

5.  На странице **Создание подсети** щелкните **ИД подсети**, затем введите первый адрес диапазона IP-адресов подсети, которую требуется связать с сетевым узлом.

6.  Щелкните **Маска**, затем введите битовую маску, применяемую к подсети.

7.  Щелкните **ИД сетевого узла**, затем выберите ИД узла, в который необходимо добавить эту подсеть.
    
    <div>
    

    > [!NOTE]  
    > Если вы еще не создали сетевые сайты, то этот список будет пустым. Подробнее об этой процедуре можно найти <A href="lync-server-2013-create-or-modify-a-network-site.md">в разделе Создание или изменение сетевого сайта в Lync Server 2013</A>. Также для получения ИД сетевых сайтов можно использовать командлет <STRONG>Get-CsNetworkSite</STRONG>. Подробные сведения можно найти в руководстве по среде Lync Server Management Shell.

    
    </div>

8.  В поле **Описание** введите дополнительные сведения об этой подсети.

9.  Нажмите **Исполнить**.

Повторите эти действия, чтобы добавить остальные подсети в сетевой узел.

</div>

</div>

<span> </span>

</div>

</div>

</div>

