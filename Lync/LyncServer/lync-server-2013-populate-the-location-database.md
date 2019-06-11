---
title: 'Lync Server 2013: заполнение базы данных местоположений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Populate the location database
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413069(v=OCS.15)
ms:contentKeyID: 48185939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08c1718c3d7ffdc79b82ac34016e79bf647ae6f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="22e4d-102">Заполнение базы данных местоположений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22e4d-102">Populate the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22e4d-103">_**Тема последнего изменения:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="22e4d-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="22e4d-p101">Чтобы автоматически определять расположение клиентов в сети, сначала требуется заполнить базу данных местоположений в *карте географических соответствий*, которая сопоставляет элементы сети с городскими адресами (например, улицей). Для определения карты географических соответствий вы можете использовать подсети, точки беспроводного доступа, коммутаторы и порты.</span><span class="sxs-lookup"><span data-stu-id="22e4d-p101">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses. You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="22e4d-106">Вы можете добавлять адреса в базу данных местоположений по отдельности или набором с помощью CSV-файла, который содержит форматы столбцов, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="22e4d-106">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="22e4d-p102">Если вы используете шлюз экстренного идентификационного номера местоположения (Emergency Location Identification Number — ELIN), включите ELIN в поле **CompanyName** для каждого расположения. Для каждого из расположений вы можете включить несколько номеров ELIN, разделяя их точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="22e4d-p102">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22e4d-109">Элемент сети</span><span class="sxs-lookup"><span data-stu-id="22e4d-109">Network Element</span></span></th>
<th><span data-ttu-id="22e4d-110">Обязательные столбцы</span><span class="sxs-lookup"><span data-stu-id="22e4d-110">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22e4d-111"><strong>Точка беспроводного доступа</strong></span><span class="sxs-lookup"><span data-stu-id="22e4d-111"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="22e4d-112">&lt;BSSID&gt;,&lt;Описание&gt;,&lt;расположение&gt;,&lt;CompanyName&gt;,&lt;хаусенумбер&gt;,&lt;хаусенумберсуффикс&gt;,&lt;преднаправленный&gt;,...</span><span class="sxs-lookup"><span data-stu-id="22e4d-112">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="22e4d-113">... &lt;Стритнаме&gt;,&lt;стритсуффикс&gt;,&lt;&gt;i Direction&lt;, City&gt;,&lt;штат&gt;,&lt;PostalCode&gt;, страна&lt;&gt;</span><span class="sxs-lookup"><span data-stu-id="22e4d-113">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22e4d-114"><strong>Subnet</strong></span><span class="sxs-lookup"><span data-stu-id="22e4d-114"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="22e4d-115">&lt;&gt;Подсеть&lt;,&gt;Описание&lt;,&gt;расположение&lt;,&gt;CompanyName&lt;,&gt;хаусенумбер&lt;,&gt;хаусенумберсуффикс&lt;, преднаправленный&gt;,...</span><span class="sxs-lookup"><span data-stu-id="22e4d-115">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="22e4d-116">... &lt;Стритнаме&gt;,&lt;стритсуффикс&gt;,&lt;&gt;i Direction&lt;, City&gt;,&lt;штат&gt;,&lt;PostalCode&gt;, страна&lt;&gt;</span><span class="sxs-lookup"><span data-stu-id="22e4d-116">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22e4d-117"><strong>Порт</strong></span><span class="sxs-lookup"><span data-stu-id="22e4d-117"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="22e4d-118">&lt;Чассисид&gt;,&lt;портидсубтипе&gt;,&lt;Портид&gt;,&lt;Описание&gt;,&lt;расположение&gt;,&lt;CompanyName&gt;,&lt;хаусенумбер&gt;,&lt; Хаусенумберсуффикс&gt;,...</span><span class="sxs-lookup"><span data-stu-id="22e4d-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="22e4d-119">... &lt;Преднаправленный&gt;,&lt;стритнаме&gt;,&lt;стритсуффикс&gt;,&lt;&gt;двусторонний&lt;, город&gt;,&lt;штат&gt;,&lt;индекс,&gt;&lt; Страну&gt;</span><span class="sxs-lookup"><span data-stu-id="22e4d-119">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22e4d-120"><strong>Коммутатор</strong></span><span class="sxs-lookup"><span data-stu-id="22e4d-120"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="22e4d-121">&lt;Чассисид&gt;,&lt;Описание&gt;,&lt;расположение&gt;,&lt;CompanyName&gt;,&lt;хаусенумбер&gt;,&lt;хаусенумберсуффикс&gt;,&lt;преднаправленный&gt;,...</span><span class="sxs-lookup"><span data-stu-id="22e4d-121">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="22e4d-122">... &lt;Стритнаме&gt;,&lt;стритсуффикс&gt;,&lt;&gt;i Direction&lt;, City&gt;,&lt;штат&gt;,&lt;PostalCode&gt;, страна&lt;&gt;</span><span class="sxs-lookup"><span data-stu-id="22e4d-122">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="22e4d-123">Если вы не заполняете базу данных расположений, и для параметра **Требуется местоположение** в политике местоположений задано значение **Да** или **Заявление об отказе**, клиент будет предлагать пользователю ввести расположение вручную.</span><span class="sxs-lookup"><span data-stu-id="22e4d-123">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="22e4d-124">Сведения о том, как заполнять базу данных расположения, можно найти в документации по оболочке Lync Server Management Shell для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="22e4d-124">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="22e4d-125">**Get-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="22e4d-125">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="22e4d-126">**Set-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="22e4d-126">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="22e4d-127">Remove-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="22e4d-127">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="22e4d-128">**Get-Кслисвирелессакцесспоинт**</span><span class="sxs-lookup"><span data-stu-id="22e4d-128">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="22e4d-129">**Set-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="22e4d-129">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="22e4d-130">**Remove-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="22e4d-130">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="22e4d-131">**Get-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="22e4d-131">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="22e4d-132">**Set-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="22e4d-132">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="22e4d-133">**Remove-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="22e4d-133">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="22e4d-134">**Get-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="22e4d-134">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="22e4d-135">**Set-Кслиспорт**</span><span class="sxs-lookup"><span data-stu-id="22e4d-135">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="22e4d-136">**Remove-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="22e4d-136">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="22e4d-137">Добавление элементов сети в базу данных расположений</span><span class="sxs-lookup"><span data-stu-id="22e4d-137">To add network elements to the location database</span></span>

1.  <span data-ttu-id="22e4d-138">Выполните следующий командлет, чтобы добавить расположение подсети в базу данных расположения.</span><span class="sxs-lookup"><span data-stu-id="22e4d-138">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="22e4d-p103">Для шлюзов ELIN укажите номер ELIN в поле CompanyName. Можно указать несколько номеров ELIN. Например:</span><span class="sxs-lookup"><span data-stu-id="22e4d-p103">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="22e4d-142">Вы также можете запустить следующие командлеты и использовать файл "subnets.csv" для массового обновления расположений подсетей.</span><span class="sxs-lookup"><span data-stu-id="22e4d-142">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="22e4d-143">Выполните следующий командлет, чтобы добавить беспроводные расположения в базу данных расположений.</span><span class="sxs-lookup"><span data-stu-id="22e4d-143">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="22e4d-144">Вы также можете запустить следующие командлеты и использовать файл "waps.csv" для массового обновления расположений точек беспроводного доступа.</span><span class="sxs-lookup"><span data-stu-id="22e4d-144">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="22e4d-145">Выполните следующий командлет, чтобы добавить расположения коммутаторов в базу данных расположений.</span><span class="sxs-lookup"><span data-stu-id="22e4d-145">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="22e4d-146">Вы также можете запустить следующие командлеты и использовать файл "switches.csv" для массового обновления расположений коммутаторов.</span><span class="sxs-lookup"><span data-stu-id="22e4d-146">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="22e4d-147">Выполните следующий командлет, чтобы добавить расположения портов в базу данных расположений.</span><span class="sxs-lookup"><span data-stu-id="22e4d-147">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="22e4d-p104">Значение по умолчанию PortIDSubType — LocallyAssigned. Также можно задать значения InterfaceAlias или InterfaceName</span><span class="sxs-lookup"><span data-stu-id="22e4d-p104">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="22e4d-150">Вы также можете запустить следующие командлеты и использовать файл "ports.csv" для массового обновления расположений портов.</span><span class="sxs-lookup"><span data-stu-id="22e4d-150">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

