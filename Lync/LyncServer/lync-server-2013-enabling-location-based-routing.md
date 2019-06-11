---
title: 'Lync Server 2013: Включение маршрутизации на основе местоположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 170ca1af77a84b655e90d5587fcd101cccf83c8a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a>Включение маршрутизации на основе местоположения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-04-26_

После развернутой голосовой связи и определения регионов сети, сайтов и подсетей вы можете включить маршрутизацию на основе местоположения. Для следующих корпоративных элементов голосовой связи должна быть включена маршрутизация на основе местоположения:

  - Сетевые сайты

  - Конфигурации магистрали

  - Политики голосовой связи

  - Настройка маршрутизации

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>Включение маршрутизации на основе местоположения на сайты сети

После того как вы развернули корпоративную голосовую почту и настроили сетевые сайты, вы можете настроить маршрутизацию на основе местоположения. Сначала необходимо создать политику маршрутизации голосовой связи для связи сайта сети с соответствующими использованием PSTN. Если вы назначаете использование PSTN для политики голосовой маршрутизации, убедитесь, что используются только использование PSTN, связанное с голосовыми маршрутами, которые используют локальные шлюзы PSTN для сайта, или шлюз PSTN, который находится в регионе, где не требуются ограничения на маршрутизацию на основе местоположения. С помощью команды Lync Server Windows PowerShell, панели управления New-Ксвоицераутингполици или Lync Server можно создавать политики голосовой маршрутизации.

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

Дополнительные сведения см. в разделе [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).

В этом примере приведенная ниже таблица и команды Windows PowerShell иллюстрируют две политики маршрутизации голосовой связи и использование PSTN, описанных в этом сценарии. В таблице ниже приведены только те параметры, которые относятся к маршрутизации на основе местоположения.

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Политика маршрутизации голосовой связи 1</th>
<th>Политика маршрутизации голосовой связи 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Идентификатор политики голосовой связи</p></td>
<td><p>Политика маршрутизации голосовой связи Делхи</p></td>
<td><p>Политика маршрутизации голосовой связи Хидерабад</p></td>
</tr>
<tr class="even">
<td><p>Использование PSTN</p></td>
<td><p>Использование Делхи, использование АТС DELETE, использование Хид УАТС</p></td>
<td><p>Использование Хидерабад, Хид УАТС, использование АТС Delete</p></td>
</tr>
</tbody>
</table>

  

Затем настройте маршрутизацию на основе местоположения для соответствующих сайтов сети и свяжите с ними политики маршрутизации голосовой связи. Используйте команду Lync Server Windows PowerShell New-Кснетворксите, чтобы включить маршрутизацию на основе местоположения и связать политики голосовой маршрутизации с сетевыми сайтами, которые должны применять ограничения маршрутизации.

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

В приведенной ниже таблице показана маршрутизация на основе местоположения для двух различных сайтов сети, Делхи и Хидерабад, определенных в этом сценарии, с помощью Lync Server Windows PowerShell. В таблице ниже приведены только те параметры, которые относятся к маршрутизации на основе местоположения.

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


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
<td><p>Имя сайта</p></td>
<td><p>Сайт 1 (Делхи)</p></td>
<td><p>Сайт 2 (Хидерабад)</p></td>
</tr>
<tr class="even">
<td><p>Енаблелокатионбаседраутинг</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>Политика маршрутизации голосовой связи</p></td>
<td><p>Политика маршрутизации голосовой связи Делхи</p></td>
<td><p>Политика маршрутизации голосовой связи Хидерабад</p></td>
</tr>
<tr class="even">
<td><p>Подсети</p></td>
<td><p>Подсеть 1 (Делхи)</p></td>
<td><p>Подсеть 2 (Хидерабад)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a>Включение маршрутизации на основе местоположения в магистральные магистрали

Прежде чем можно будет включить конфигурацию магистральной конфигурации для маршрутизации на основе расположения, необходимо создать конфигурацию магистрали для каждой магистрали или каждого из сайтов сети. Используйте команду Lync Server Windows PowerShell New-CsTrunkConfiguration для создания конфигурации канала магистрали. Если несколько магистральных каналов связаны с определенной системой (например, Gateway или УАТС), каждую из них нужно изменить, чтобы включить ограничения маршрутизации на основе местоположения.

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

Дополнительные сведения можно найти в разделе [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

В этом примере следующие команды Windows PowerShell иллюстрируют создание одной конфигурации магистрали для каждой магистрали в развертывании, определенном в этом сценарии.

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

После настройки магистральной конфигурации для каждой магистрали вы можете использовать команду Lync Server Windows PowerShell Set-CsTrunkConfiguration, чтобы включить маршрутизацию на основе местоположения для каналов, которые должны применять ограничения маршрутизации. Включите маршрутизацию с учетом местоположения на магистральы, которые направляют звонки на шлюзы PSTN, которые направляют звонки в КТСОП и связывают сетевой сайт, на котором расположен шлюз.

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

Дополнительные сведения можно найти в разделе [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

В этом примере для каждой магистрали, связанной с шлюзами PSTN в Делхи и Хидерабад, включена маршрутизация на основе местоположения.

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

Не включайте маршрутизацию на основе местоположения для каналов связи, которые не направляют звонки в КТСОП. Однако вы по-прежнему обязаны привязать магистраль к сетевому сайту, на котором система находится в качестве ограничений маршрутизации на основе местоположения, для звонков по КОММУТИРУЕМой линии, подсоединенной с помощью этой магистрали, должны быть принудительно использовать ограничения на расположение. В этом примере маршрутизация на основе местоположения не включена для каждой магистрали, связанной с системами УАТС в Делхи и Хидерабад:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
Конечные точки, которые подключены к системам, не накладываемым на протокол PSTN (например, УАТС), имеют аналогичные ограничения в качестве конечных точек Lync для пользователей, для которых включена маршрутизация на основе местоположения. Это означает, что эти пользователи смогут размещать и принимать звонки на пользователей Lync, независимо от местонахождения пользователя. Кроме того, они смогут принимать звонки в другие системы и из них, которые не направляют звонки в сеть PSTN (например, конечную точку, подключенную к другой УАТС) независимо от того, с какой сетевой страницы связана система. Все входящие звонки, звонки и переадресация звонков, связанные с конечными точками PSTN, будут применяться для маршрутизации на основе местоположения. Такие звонки должны использовать только шлюзы PSTN, определенные как локальные для таких систем.

В приведенной ниже таблице показана конфигурация магистрали с четырьмя магистральами на двух разных сетевых сайтах: два соединения с шлюзами PSTN и двумя подключенными к системам АТС.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Енаблелокатионрестриктион</th>
<th>Нетворкситеид</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Пстнгатевай: магистраль 1 DEL-GW</p></td>
<td><p>True</p></td>
<td><p>Сайт 1 (Делхи)</p></td>
</tr>
<tr class="even">
<td><p>Пстнгатевай: магистраль 2 ХИД-GW</p></td>
<td><p>True</p></td>
<td><p>Сайт 2 (Хидерабад)</p></td>
</tr>
<tr class="odd">
<td><p>Пстнгатевай: магистраль 3 DEL-УАТС</p></td>
<td><p>False</p></td>
<td><p>Сайт 1 (Делхи)</p></td>
</tr>
<tr class="even">
<td><p>Пстнгатевай: ХИД-УАТС (магистральная линия 4)</p></td>
<td><p>False</p></td>
<td><p>Сайт 2 (Хидерабад)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>Включение маршрутизации на основе местоположения в политики голосовой связи

Чтобы обеспечить возможность маршрутизации с учетом расположения определенным пользователям, настройте политику голосовой связи пользователей, чтобы отключить бесплатный звонок. Используйте команду Lync Server Windows PowerShell New-Ксвоицеполици, чтобы создать новую политику голосовой связи или Set-Ксвоицеполици, при использовании существующей политики для включения маршрутизации на основе местоположения, запретив бесплатный звонок по протоколу PSTN.

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

Дополнительные сведения можно найти в разделе [New-ксвоицеполици](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).

В этом примере приведенная ниже таблица и команды Windows PowerShell иллюстрируют использование политик голосовой связи по Делхи и Хидерабад, описанных в этом сценарии, в целях предотвращения бесплатной поддержки PSTN. В таблице ниже приведены только те параметры, которые относятся к маршрутизации на основе местоположения.

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Политика голосовой связи 1</th>
<th>Политика голосовой связи 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Идентификатор политики голосовой связи</p></td>
<td><p>Политика голосовой связи Делхи</p></td>
<td><p>Политика голосовой связи Хидерабад</p></td>
</tr>
<tr class="even">
<td><p>Использование PSTN</p></td>
<td><p>Использование Делхи, использование АТС DELETE, использование Хид УАТС</p></td>
<td><p>Использование Хидерабад, Хид УАТС, использование АТС Delete</p></td>
</tr>
<tr class="odd">
<td><p>Превентпстнтоллбипасс</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>Включение маршрутизации на основе местоположения в конфигурации маршрутизации

Наконец, глобально включите маршрутизацию на основе местоположения в конфигурацию маршрутизации. Используйте команду Lync Server Windows PowerShell New-Ксраутингконфигуратион, чтобы включить маршрутизацию на основе местоположения.

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

Дополнительные сведения можно найти в разделе [Set-ксраутингконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).

<div>


> [!NOTE]  
> Если маршрутизация на основе расположения должна быть включена через глобальную конфигурацию, набор применяемых правил будет применяться только для сайтов, пользователей и магистральных каналов, для которых она настроена, как указано в этой документации.



</div>

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

