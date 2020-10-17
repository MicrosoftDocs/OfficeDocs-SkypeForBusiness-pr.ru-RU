---
title: 'Lync Server 2013: развертывание областей сети, сайтов и подсетей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b95d9f7e38e3169474aee33a3004b388c0b13f14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531152"
---
# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a>Развертывание областей сети, сайтов и подсетей в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-03-12_

После развертывания корпоративной голосовой связи необходимо настроить следующие параметры.

  - Регионы сети

  - Сетевые сайты

  - Подсети сети

<div>

## <a name="define-network-regions"></a>Определение областей сети

Определение областей сети с помощью команды Lync Server Windows PowerShell, панели управления New — CsNetworkRegion или Lync Server.

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

Дополнительные сведения см. в статье [New – CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).

В этом примере приведенная ниже команда Windows PowerShell иллюстрирует регион сети, регион 1 (Индия), определенный в этом сценарии.

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a>Определение сетевых сайтов

Используйте командную консоль Lync Server Windows PowerShell, New-CsNetworkSite или панель управления Lync Server для определения сетевых сайтов.

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

Дополнительные сведения см. в статье [New – CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).

В этом примере приведенная ниже таблица и команда Windows PowerShell для Lync Server иллюстрируют сетевые сайты, определенные в этом сценарии. Только те параметры, которые относятся к Location-Based маршрутизации, включены в таблицу для целей иллюстрации.

    New-CsNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
    New-CsNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Сайт 1 (Нью Дели)</th>
<th>Сайт 2 (Хидерабад)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Идентификатор сайта</p></td>
<td><p>Сайт 1 (Нью Дели)</p></td>
<td><p>Сайт 2 (Хидерабад)</p></td>
</tr>
<tr class="even">
<td><p>КОД региона</p></td>
<td><p>Регион 1 (Индия)</p></td>
<td><p>Регион 1 (Индия)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a>Определение сетевых подсетей

Используйте командную консоль Lync Server Windows PowerShell New-CsNetworkSubnet или панель управления Lync Server, чтобы определить сетевые подсети и назначить их сетевым сайтам.

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

Дополнительные сведения см. в статье [New – CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

В этом примере приведенная ниже таблица и команды Windows PowerShell иллюстрируют Назначение сетевых подсетей сетевым сайтам, Нью Дели и Хидерабад, определенным в этом сценарии. Только те параметры, которые относятся к Location-Based маршрутизации, включены в таблицу для целей иллюстрации.

    New-CsNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
    New-CsNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Сайт 1 (Нью Дели)</th>
<th>Сайт 2 (Хидерабад)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Идентификатор подсети</p></td>
<td><p>192.168.0.0</p></td>
<td><p>192.168.1.0</p></td>
</tr>
<tr class="even">
<td><p>Маска</p></td>
<td><p>открыт</p></td>
<td><p>открыт</p></td>
</tr>
<tr class="odd">
<td><p>Идентификатор сайта</p></td>
<td><p>Сайт 1 (Нью Дели)</p></td>
<td><p>Сайт 2 (Хидерабад)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка маршрутизации Location-Based в Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

