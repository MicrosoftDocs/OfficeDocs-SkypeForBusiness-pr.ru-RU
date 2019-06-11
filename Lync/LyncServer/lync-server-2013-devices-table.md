---
title: 'Lync Server 2013: таблица Devices'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f78e0b4ba3bb5271a2de43e423dfa4b3baf17cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a>Таблица Devices в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-05-25_

Таблица "устройства" является вспомогательной таблицей. Каждая запись хранит информацию об одном устройстве (стационарном телефоне).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Ключ/индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Устройства</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный номер, идентифицирующий эту аппаратную версию.</p></td>
</tr>
<tr class="even">
<td><p><strong>ManufacturerId</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Производитель этого устройства. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-manufacturers-table.md">таблицей изготовителей в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Хардвареверсионид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Аппаратная версия этого устройства. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-hardwareversions-table.md">таблицей хардвареверсионс в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>MacAddress</strong></p></td>
<td><p>bigint</p></td>
<td></td>
<td><p>MAC-адрес</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

