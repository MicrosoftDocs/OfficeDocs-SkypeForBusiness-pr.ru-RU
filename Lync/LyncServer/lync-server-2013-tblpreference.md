---
title: 'Lync Server 2013: tblPreference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 652312c5ca48a140ee7f17486ef98debb4e08672
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a>tblPreference в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-24_

Тблпреференце включает клиентские настройки пользователей. Обычно используется клиентами, предшествующими Lync 2013.

### <a name="columns"></a>Столбцов

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Префлабел</p></td>
<td><p>nvarchar (255), NOT NULL</p></td>
<td><p>Надпись с таким же форматом &lt;, как:&gt;URI SIP пользователя, | имя пользователя. &lt;наборы&gt;параметров.</p></td>
</tr>
<tr class="even">
<td><p>Префсекид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Последовательный номер (на метку) для целей управления версиями.</p></td>
</tr>
<tr class="odd">
<td><p>Префконтент</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>Закодированное содержимое.</p></td>
</tr>
<tr class="even">
<td><p>Ластмодифиедби</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор участника, который обновил предпочтение.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Ключ

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;Префлабел, Префсекид&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

