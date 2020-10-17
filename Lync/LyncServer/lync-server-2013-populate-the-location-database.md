---
title: 'Lync Server 2013: заполнение базы данных расположений'
description: 'Lync Server 2013: заполните базу данных местоположений.'
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
ms.openlocfilehash: c6cf3204795ae2c4f8248517b84d7a5ac1bad0d9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543175"
---
# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="8f3b6-103">Заполнение базы данных расположений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f3b6-103">Populate the location database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f3b6-104">_**Последнее изменение темы:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="8f3b6-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="8f3b6-p101">Чтобы автоматически определять расположение клиентов в сети, сначала требуется заполнить базу данных местоположений в *карте географических соответствий*, которая сопоставляет элементы сети с городскими адресами (например, улицей). Для определения карты географических соответствий вы можете использовать подсети, точки беспроводного доступа, коммутаторы и порты.</span><span class="sxs-lookup"><span data-stu-id="8f3b6-p101">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses. You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="8f3b6-107">Вы можете добавлять адреса в базу данных местоположений по отдельности или набором с помощью CSV-файла, который содержит форматы столбцов, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="8f3b6-107">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="8f3b6-p102">Если вы используете шлюз экстренного идентификационного номера местоположения (Emergency Location Identification Number — ELIN), включите ELIN в поле **CompanyName** для каждого расположения. Для каждого из расположений вы можете включить несколько номеров ELIN, разделяя их точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="8f3b6-p102">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f3b6-110">Элемент сети</span><span class="sxs-lookup"><span data-stu-id="8f3b6-110">Network Element</span></span></th>
<th><span data-ttu-id="8f3b6-111">Обязательные столбцы</span><span class="sxs-lookup"><span data-stu-id="8f3b6-111">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f3b6-112"><strong>Точка беспроводного доступа</strong></span><span class="sxs-lookup"><span data-stu-id="8f3b6-112"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="8f3b6-113">&lt;BSSID &gt; , &lt; Description &gt; , &lt; Location &gt; , &lt; CompanyName &gt; , &lt; хаусенумбер &gt; , &lt; хаусенумберсуффикс &gt; , &lt; ,... по направлению &gt;</span><span class="sxs-lookup"><span data-stu-id="8f3b6-113">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="8f3b6-114">... &lt; Стритнаме &gt; , &lt; Стритсуффикс &gt; , &lt; двусторонний &gt; , City, &lt; &gt; &lt; штат &gt; , &lt; PostalCode &gt; , &lt; страна&gt;</span><span class="sxs-lookup"><span data-stu-id="8f3b6-114">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f3b6-115"><strong>Subnet</strong></span><span class="sxs-lookup"><span data-stu-id="8f3b6-115"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="8f3b6-116">&lt;Подсеть &gt; , &lt; Описание &gt; , &lt; расположение &gt; , &lt; название организации &gt; , &lt; хаусенумбер &gt; , &lt; хаусенумберсуффикс &gt; , &lt; преднаправленный &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="8f3b6-116">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="8f3b6-117">... &lt; Стритнаме &gt; , &lt; Стритсуффикс &gt; , &lt; двусторонний &gt; , City, &lt; &gt; &lt; штат &gt; , &lt; PostalCode &gt; , &lt; страна&gt;</span><span class="sxs-lookup"><span data-stu-id="8f3b6-117">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f3b6-118"><strong>Port</strong></span><span class="sxs-lookup"><span data-stu-id="8f3b6-118"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="8f3b6-119">&lt;Чассисид &gt; , &lt; портидсубтипе &gt; , &lt; Портид &gt; , &lt; Description &gt; , &lt; Location &gt; , &lt; CompanyName &gt; , &lt; хаусенумбер &gt; , &lt; хаусенумберсуффикс &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="8f3b6-119">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="8f3b6-120">... &lt; Преднаправленный &gt; , &lt; стритнаме &gt; , &lt; стритсуффикс &gt; , &lt; двусторонний &gt; , &lt; город &gt; , &lt; штат &gt; , PostalCode, &lt; &gt; &lt; страна&gt;</span><span class="sxs-lookup"><span data-stu-id="8f3b6-120">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f3b6-121"><strong>Переключатель</strong></span><span class="sxs-lookup"><span data-stu-id="8f3b6-121"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="8f3b6-122">&lt;Чассисид &gt; , &lt; Description &gt; , &lt; Location &gt; , &lt; CompanyName &gt; , &lt; хаусенумбер &gt; , &lt; хаусенумберсуффикс &gt; , &lt; преднаправленный &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="8f3b6-122">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="8f3b6-123">... &lt; Стритнаме &gt; , &lt; Стритсуффикс &gt; , &lt; двусторонний &gt; , City, &lt; &gt; &lt; штат &gt; , &lt; PostalCode &gt; , &lt; страна&gt;</span><span class="sxs-lookup"><span data-stu-id="8f3b6-123">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8f3b6-124">Если вы не заполняете базу данных расположений, и для параметра **Location Required** (Требуется расположение) в политике расположения задано значение **Да** или **Заявление об отказе**, клиент будет предлагать пользователю ввести расположение вручную.</span><span class="sxs-lookup"><span data-stu-id="8f3b6-124">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="8f3b6-125">Для получения дополнительных сведений о заполнении базы данных расположений обратитесь к документации по консоли управления Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="8f3b6-125">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="8f3b6-126">**Get — Кслиссубнет**</span><span class="sxs-lookup"><span data-stu-id="8f3b6-126">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="8f3b6-127">**Set — Кслиссубнет**</span><span class="sxs-lookup"><span data-stu-id="8f3b6-127">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="8f3b6-128">Remove-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="8f3b6-128">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="8f3b6-129">**Get — Кслисвирелессакцесспоинт**</span><span class="sxs-lookup"><span data-stu-id="8f3b6-129">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="8f3b6-130">**Set — Кслисвирелессакцесспоинт**</span><span class="sxs-lookup"><span data-stu-id="8f3b6-130">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="8f3b6-131">**Remove — Кслисвирелессакцесспоинт**</span><span class="sxs-lookup"><span data-stu-id="8f3b6-131">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="8f3b6-132">**Get — Кслиссвитч**</span><span class="sxs-lookup"><span data-stu-id="8f3b6-132">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="8f3b6-133">**Set — Кслиссвитч**</span><span class="sxs-lookup"><span data-stu-id="8f3b6-133">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="8f3b6-134">**Remove — Кслиссвитч**</span><span class="sxs-lookup"><span data-stu-id="8f3b6-134">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="8f3b6-135">**Get — Кслиспорт**</span><span class="sxs-lookup"><span data-stu-id="8f3b6-135">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="8f3b6-136">**Set — Кслиспорт**</span><span class="sxs-lookup"><span data-stu-id="8f3b6-136">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="8f3b6-137">**Remove — Кслиспорт**</span><span class="sxs-lookup"><span data-stu-id="8f3b6-137">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="8f3b6-138">Добавление элементов сети в базу данных расположений</span><span class="sxs-lookup"><span data-stu-id="8f3b6-138">To add network elements to the location database</span></span>

1.  <span data-ttu-id="8f3b6-139">Выполните следующий командлет, чтобы добавить расположение подсети в базу данных расположения.</span><span class="sxs-lookup"><span data-stu-id="8f3b6-139">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="8f3b6-p103">Для шлюзов ELIN укажите номер ELIN в поле CompanyName. Можно указать несколько номеров ELIN. Например:</span><span class="sxs-lookup"><span data-stu-id="8f3b6-p103">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="8f3b6-143">Вы также можете запустить следующие командлеты и использовать файл "subnets.csv" для массового обновления расположений подсетей.</span><span class="sxs-lookup"><span data-stu-id="8f3b6-143">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="8f3b6-144">Выполните следующий командлет, чтобы добавить беспроводные расположения в базу данных расположений.</span><span class="sxs-lookup"><span data-stu-id="8f3b6-144">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="8f3b6-145">Вы также можете запустить следующие командлеты и использовать файл "waps.csv" для массового обновления расположений точек беспроводного доступа.</span><span class="sxs-lookup"><span data-stu-id="8f3b6-145">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="8f3b6-146">Выполните следующий командлет, чтобы добавить расположения коммутаторов в базу данных расположений.</span><span class="sxs-lookup"><span data-stu-id="8f3b6-146">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="8f3b6-147">Вы также можете запустить следующие командлеты и использовать файл "switches.csv" для массового обновления расположений коммутаторов.</span><span class="sxs-lookup"><span data-stu-id="8f3b6-147">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="8f3b6-148">Выполните следующий командлет, чтобы добавить расположения портов в базу данных расположений.</span><span class="sxs-lookup"><span data-stu-id="8f3b6-148">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="8f3b6-p104">Значение по умолчанию PortIDSubType — LocallyAssigned. Также можно задать значения InterfaceAlias или InterfaceName</span><span class="sxs-lookup"><span data-stu-id="8f3b6-p104">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="8f3b6-151">Вы также можете запустить следующие командлеты и использовать файл "ports.csv" для массового обновления расположений портов.</span><span class="sxs-lookup"><span data-stu-id="8f3b6-151">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

