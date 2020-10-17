---
title: 'Lync Server 2013: Включение маршрутизации Location-Based'
description: 'Lync Server 2013: Включение маршрутизации Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7844af5792468cd5645b6b42c857c63b943c2df1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557625"
---
# <a name="enabling-location-based-routing-in-lync-server-2013"></a>Включение маршрутизации Location-Based в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-04-26_

После развертывания корпоративной голосовой связи и определенных областей сети, сайтов и подсетей можно включить маршрутизацию Location-Based. Маршрутизация Location-Based должна быть включена для следующих элементов корпоративной голосовой связи:

  - Сетевые сайты

  - Конфигурации магистрали

  - Политики голосовой связи

  - Конфигурация маршрутизации

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>Включение маршрутизации Location-Based для сетевых сайтов

После развертывания корпоративной голосовой связи и настроенных сетевых сайтов можно приступать к настройке маршрутизации Location-Based. Сначала необходимо создать политику маршрутизации голосовой связи, чтобы связать сетевой сайт с подходящими использованиями PSTN. При назначении использования PSTN для политики маршрутизации голосовых вызовов обязательно используйте только использование PSTN, связанное с маршрутами голосовой связи, которые используют локальный шлюз PSTN для сайта, или шлюз PSTN, расположенный в регионе, где не требуются ограничения маршрутизации Location-Based. Создайте политики маршрутизации голосовой связи с помощью команды Lync Server Windows PowerShell, панели управления New — CsVoiceRoutingPolicy или Lync Server.

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

Дополнительные сведения см. в статье [New – CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).

В этом примере приведенная ниже таблица и команды Windows PowerShell иллюстрируют две политики маршрутизации голосовых вызовов и связанные с ними использование PSTN, определенные в этом сценарии. Только те параметры, которые относятся к Location-Based маршрутизации, включены в таблицу для целей иллюстрации.

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
<th>Политика маршрутизации голосовых вызовов 1</th>
<th>Политика маршрутизации голосовой связи 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Идентификатор политики голосовой связи</p></td>
<td><p>Политика маршрутизации голосовой связи Нью Дели</p></td>
<td><p>Политика маршрутизации голосовой связи Хидерабад</p></td>
</tr>
<tr class="even">
<td><p>Использование PSTN</p></td>
<td><p>Использование Нью Дели, использование УАТС Del, использование Хид УАТС</p></td>
<td><p>Использование Хидерабад, использование Хид УАТС, использование УАТС del</p></td>
</tr>
</tbody>
</table>

  

Затем настройте маршрутизацию Location-Based для соответствующих сетевых сайтов и свяжите с ними политики маршрутизации голосовых вызовов. Используйте команду Lync Server Windows PowerShell New-CsNetworkSite, чтобы включить маршрутизацию Location-Based и связать политики маршрутизации голосовых вызовов с сетевыми сайтами, которые должны применять ограничения маршрутизации.

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

В приведенном ниже примере показана Location-Based маршрутизация для двух различных сетевых сайтов, Нью Дели и Хидерабад, определенных в этом сценарии с помощью Lync Server Windows PowerShell. Только те параметры, которые относятся к Location-Based маршрутизации, включены в таблицу для целей иллюстрации.

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
<th>Сайт 1 (Нью Дели)</th>
<th>Сайт 2 (Хидерабад)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Имя сайта</p></td>
<td><p>Сайт 1 (Нью Дели)</p></td>
<td><p>Сайт 2 (Хидерабад)</p></td>
</tr>
<tr class="even">
<td><p>енаблелокатионбаседраутинг</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
</tr>
<tr class="odd">
<td><p>Политика маршрутизации голосовой связи</p></td>
<td><p>Политика маршрутизации голосовой связи Нью Дели</p></td>
<td><p>Политика маршрутизации голосовой связи Хидерабад</p></td>
</tr>
<tr class="even">
<td><p>Подсети</p></td>
<td><p>Подсеть 1 (Нью Дели)</p></td>
<td><p>Подсеть 2 (Хидерабад)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a>Включение маршрутизации Location-Based в магистрали

Прежде чем можно будет включить конфигурацию магистрали для маршрутизации Location-Based, необходимо создать конфигурацию магистрали для каждой магистрали или каждого сетевого сайта. Чтобы создать конфигурацию магистрали, используйте команду Windows PowerShell Lync Server с параметром New – CsTrunkConfiguration. Если несколько магистральных линий связаны с определенной системой (например, Gateway или УАТС), необходимо изменить каждую конфигурацию магистрали, чтобы включить Location-Based ограничения маршрутизации.

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

Дополнительные сведения см. в статье [New – CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

В этом примере приведенные ниже команды Windows PowerShell иллюстрируют создание одной конфигурации магистрали для каждой магистрали в развертывании, определенном в этом сценарии.

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

После настройки магистрали для каждой магистрали можно использовать командную консоль Windows PowerShell Lync Server, Set-CsTrunkConfiguration, чтобы включить Location-Based маршрутизацию в магистральные сети, которые должны применять ограничения маршрутизации. Включите маршрутизацию Location-Based в магистрали, которые направляют вызовы на шлюзы PSTN, которые направляют вызовы в PSTN, и связывают сетевой сайт, на котором расположен шлюз.

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

Дополнительные сведения см. в статье [New – CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

В этом примере Location-Based маршрутизация включена для каждой магистрали, связанной с шлюзами PSTN в Нью Дели и Хидерабад:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

Не включайте Location-Based маршрутизацию для магистральных каналов, которые не направляют звонки в PSTN; Тем не менее, по-прежнему необходимо связать магистраль с сетевым сайтом, на котором размещается система, в качестве Location-Based ограничения маршрутизации, которые должны быть применены для вызовов PSTN, которые подключаются с помощью этой магистрали. В этом примере Location-Based маршрутизация не включена для каждой магистрали, связанной с системами УАТС в Нью Дели и Хидерабад:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
Конечные точки, которые подключены к системам, которые не направляют вызовы в PSTN (например, УАТС), будут иметь аналогичные ограничения в качестве конечных точек Lync для пользователей, для которых включена маршрутизация Location-Based. Это означает, что эти пользователи смогут размещать и принимать звонки пользователю Lync независимо от расположения пользователя. Кроме того, они могут выполнять прием вызовов в другие системы, которые не направляют вызовы в сеть PSTN (то есть конечная точка, подключенная к другой УАТС) независимо от того, к какому сетевому сайту относится система. Все входящие звонки, исходящие звонки, передачи звонков и переадресация вызовов, связанные с конечными точками PSTN, будут подвергаться Location-Based принудительной маршрутизации. Такие вызовы должны использовать только шлюзы PSTN, которые определены как локальные для таких систем.

В следующей таблице показана конфигурация магистрали четырех магистральных линий на двух различных сетевых сайтах: два подключения к шлюзам PSTN и два подключения к системам УАТС.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>енаблелокатионрестриктион</th>
<th>NetworkSiteID</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PstnGateway: магистраль 1 DEL — GW</p></td>
<td><p>Верно</p></td>
<td><p>Сайт 1 (Нью Дели)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: магистраль 2 ХИД — GW</p></td>
<td><p>Верно</p></td>
<td><p>Сайт 2 (Хидерабад)</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway: магистраль 3 DEL — УАТС</p></td>
<td><p>False</p></td>
<td><p>Сайт 1 (Нью Дели)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: магистраль 4 ХИД — УАТС</p></td>
<td><p>False</p></td>
<td><p>Сайт 2 (Хидерабад)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>Включение маршрутизации Location-Based политик голосовой связи

Чтобы обеспечить Location-Based маршрутизацию для определенных пользователей, настройте политику голосовой связи для этих пользователей, чтобы предотвратить обход платных звонков по сети PSTN. Используйте командную консоль Lync Server Windows PowerShell New — CsVoicePolicy, чтобы создать новую политику голосовой связи или Set — CsVoicePolicy, если используется существующая политика, чтобы включить Location-Based маршрутизацию, запретив обход бесплатных звонков по сети PSTN.

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

Дополнительные сведения см. в статье [New – CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).

В этом примере приведенная ниже таблица и команды Windows PowerShell иллюстрируют включение защиты от бесплатных бесплатных политик Нью Дели и Хидерабад голосовой связи, определенных в этом сценарии. Только те параметры, которые относятся к Location-Based маршрутизации, включены в таблицу для целей иллюстрации.

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
<td><p>Политика голосовой связи Нью Дели</p></td>
<td><p>Политика голосовой связи Хидерабад</p></td>
</tr>
<tr class="even">
<td><p>Использование PSTN</p></td>
<td><p>Использование Нью Дели, использование УАТС Del, использование Хид УАТС</p></td>
<td><p>Использование Хидерабад, использование Хид УАТС, использование УАТС del</p></td>
</tr>
<tr class="odd">
<td><p>превентпстнтоллбипасс</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>Включение маршрутизации Location-Based в конфигурации маршрутизации

Наконец, глобально разрешите Location-Based маршрутизацию в конфигурацию маршрутизации. Чтобы включить маршрутизацию Location-Based, используйте команду Windows PowerShell Lync Server с параметром New – Ксраутингконфигуратион.

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

Дополнительные сведения см. в статье [Set – ксраутингконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).

<div>


> [!NOTE]  
> Несмотря на то, что необходимо включить Location-Based маршрутизацию через глобальную конфигурацию, набор применяемых правил будет применяться только к сайтам, пользователям и магистральным линиям, для которых она настроена, как указано в этой документации.



</div>

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

