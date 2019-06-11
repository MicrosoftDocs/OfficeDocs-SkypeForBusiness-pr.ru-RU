---
title: 'Lync Server 2013: таблица Кодекдескриптион'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: CodecDescription table
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204797(v=OCS.15)
ms:contentKeyID: 48183802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f9c6cbdfd24517308321f5f3838fba56e90f842
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="codecdescription-table-in-lync-server-2013"></a>Таблица Кодекдескриптион в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-17_

В таблице Кодекдескриптион уникальные идентификаторы кодека сопоставляются с соответствующими кодеками. Кодеки используются для кодирования цифровых сигналов для передачи и трансляции, а затем для расшифровки этих сигналов для воспроизведения. Эта таблица введена в Microsoft Lync Server 2013


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Столбец</strong></th>
<th><strong>Тип данных</strong></th>
<th><strong>Ключ/индекс</strong></th>
<th><strong>Сведения</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Кодекдескриптионкэй</strong></p></td>
<td><p>smallint</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный идентификатор, присвоенный кодеку.</p></td>
</tr>
<tr class="even">
<td><p><strong>CodecDescription</strong></p></td>
<td><p>varchar (256)</p></td>
<td><p>Повторя</p></td>
<td><p>Уникальное описание кодека, соответствующего Кодекдескриптионкэй.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

