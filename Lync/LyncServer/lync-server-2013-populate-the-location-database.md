---
title: 'Lync Server 2013: заполнение базы данных расположений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Populate the location database
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413069(v=OCS.15)
ms:contentKeyID: 48185939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 161a418728362da4817610dfa8e13be3046e3df6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a>Заполнение базы данных расположений в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-17_

Чтобы автоматически определять расположение клиентов в сети, сначала требуется заполнить базу данных местоположений в *карте географических соответствий*, которая сопоставляет элементы сети с городскими адресами (например, улицей). Для определения карты географических соответствий вы можете использовать подсети, точки беспроводного доступа, коммутаторы и порты.

Вы можете добавлять адреса в базу данных местоположений по отдельности или набором с помощью CSV-файла, который содержит форматы столбцов, описанные в следующей таблице.

Если вы используете шлюз экстренного идентификационного номера местоположения (Emergency Location Identification Number — ELIN), включите ELIN в поле **CompanyName** для каждого расположения. Для каждого из расположений вы можете включить несколько номеров ELIN, разделяя их точкой с запятой.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Элемент сети</th>
<th>Обязательные столбцы</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Точка беспроводного доступа</strong></p></td>
<td><p>&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;хаусенумбер&gt;,&lt;хаусенумберсуффикс&gt;,&lt;&gt;,... по направлению</p>
<p>... &lt;Стритнаме&gt;,&lt;стритсуффикс&gt;,&lt;&gt;двусторонний&lt;, City&gt;,&lt;штат&gt;,&lt;PostalCode&gt;, страна&lt;&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Подсеть</strong></p></td>
<td><p>&lt;&gt;Подсеть&lt;,&gt;Описание&lt;,&gt;расположение&lt;,&gt;название&lt;Организации&gt;,&lt;хаусенумбер&gt;,&lt;хаусенумберсуффикс, преднаправленный&gt;,...</p>
<p>... &lt;Стритнаме&gt;,&lt;стритсуффикс&gt;,&lt;&gt;двусторонний&lt;, City&gt;,&lt;штат&gt;,&lt;PostalCode&gt;, страна&lt;&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>Port</strong></p></td>
<td><p>&lt;Чассисид&gt;,&lt;портидсубтипе&gt;,&lt;Портид&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;хаусенумбер&gt;,&lt;хаусенумберсуффикс&gt;,...</p>
<p>... &lt;Преднаправленный&gt;,&lt;стритнаме&gt;,&lt;стритсуффикс&gt;,&lt;&gt;двусторонний&lt;, город&gt;,&lt;штат&gt;,&lt;PostalCode&gt;, страна&lt;&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Переключатель</strong></p></td>
<td><p>&lt;Чассисид&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;хаусенумбер&gt;,&lt;хаусенумберсуффикс&gt;,&lt;преднаправленный&gt;,...</p>
<p>... &lt;Стритнаме&gt;,&lt;стритсуффикс&gt;,&lt;&gt;двусторонний&lt;, City&gt;,&lt;штат&gt;,&lt;PostalCode&gt;, страна&lt;&gt;</p></td>
</tr>
</tbody>
</table>


Если вы не заполняете базу данных расположений, и для параметра **Location Required** (Требуется расположение) в политике расположения задано значение **Да** или **Заявление об отказе**, клиент будет предлагать пользователю ввести расположение вручную.

Для получения дополнительных сведений о заполнении базы данных расположений обратитесь к документации по консоли управления Lync Server для следующих командлетов:

  - **Get — Кслиссубнет**

  - **Set — Кслиссубнет**

  - Remove — Кслиссубнет

  - **Get — Кслисвирелессакцесспоинт**

  - **Set — Кслисвирелессакцесспоинт**

  - **Remove — Кслисвирелессакцесспоинт**

  - **Get — Кслиссвитч**

  - **Set — Кслиссвитч**

  - **Remove — Кслиссвитч**

  - **Get — Кслиспорт**

  - **Set — Кслиспорт**

  - **Remove — Кслиспорт**

<div>

## <a name="to-add-network-elements-to-the-location-database"></a>Добавление элементов сети в базу данных расположений

1.  Выполните следующий командлет, чтобы добавить расположение подсети в базу данных расположения.
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Для шлюзов ELIN укажите номер ELIN в поле CompanyName. Можно указать несколько номеров ELIN. Например:
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Вы также можете запустить следующие командлеты и использовать файл "subnets.csv" для массового обновления расположений подсетей.
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  Выполните следующий командлет, чтобы добавить беспроводные расположения в базу данных расположений.
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    Вы также можете запустить следующие командлеты и использовать файл "waps.csv" для массового обновления расположений точек беспроводного доступа.
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  Выполните следующий командлет, чтобы добавить расположения коммутаторов в базу данных расположений.
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Вы также можете запустить следующие командлеты и использовать файл "switches.csv" для массового обновления расположений коммутаторов.
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  Выполните следующий командлет, чтобы добавить расположения портов в базу данных расположений.
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    Значение по умолчанию PortIDSubType — LocallyAssigned. Также можно задать значения InterfaceAlias или InterfaceName
    
    Вы также можете запустить следующие командлеты и использовать файл "ports.csv" для массового обновления расположений портов.
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

