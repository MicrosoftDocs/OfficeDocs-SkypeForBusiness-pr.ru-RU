---
title: 'Lync Server 2013: развертывание регионов сети, сайтов и подсетей'
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
ms.openlocfilehash: 04c39a18147bad3f84bd345ec0a56b606db4cae4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a>Развертывание регионов сети, сайтов и подсетей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-03-12_

После развертывания корпоративной голосовой связи необходимо настроить следующие параметры:

  - Регионы сети

  - Сетевые сайты

  - Сетевые подсети

<div>

## <a name="define-network-regions"></a>Определение регионов сети

С помощью команды Lync Server Windows PowerShell, панели управления New-Кснетворкрегион или Lync Server можно определять регионы сети.

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

Дополнительные сведения можно найти в разделе [New-кснетворкрегион](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).

В этом примере Следующая команда Windows PowerShell иллюстрирует сетевую область, область 1 (Индия), определенную в этом сценарии.

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a>Определение сетевых сайтов

С помощью команды Lync Server Windows PowerShell, New-Кснетворксите или панели управления Lync Server можно определять сетевые сайты.

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

Дополнительные сведения можно найти в разделе [New-кснетворксите](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).

В этом примере в приведенной ниже таблице и команде Windows PowerShell для Lync Server показаны сетевые сайты, определенные в этом сценарии. В таблице ниже приведены только те параметры, которые относятся к маршрутизации на основе местоположения.

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
<th>Сайт 1 (Делхи)</th>
<th>Сайт 2 (Хидерабад)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Идентификатор сайта</p></td>
<td><p>Сайт 1 (Делхи)</p></td>
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

## <a name="define-network-subnets"></a>Определение подсетей сети

С помощью команды Lync Server Windows PowerShell, New-Кснетворксубнет или панели управления Lync Server можно определять сетевые подсети и назначать их сетевым сайтам.

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

Дополнительные сведения можно найти в разделе [New-кснетворксубнет](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

В этом примере приведенная ниже таблица и команды Windows PowerShell иллюстрируют Назначение сетевых подсетей сетевым сайтам, Делхи и Хидерабад, определенным в этом сценарии. В таблице ниже приведены только те параметры, которые относятся к маршрутизации на основе местоположения.

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
<th>Сайт 1 (Делхи)</th>
<th>Сайт 2 (Хидерабад)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>КОД подсети</p></td>
<td><p>172.16.0.0</p></td>
<td><p>192.168.1.0</p></td>
</tr>
<tr class="even">
<td><p>Маски</p></td>
<td><p>24</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>Идентификатор сайта</p></td>
<td><p>Сайт 1 (Делхи)</p></td>
<td><p>Сайт 2 (Хидерабад)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка маршрутизации на основе расположения в Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

