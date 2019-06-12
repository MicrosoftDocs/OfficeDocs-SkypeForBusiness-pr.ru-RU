---
title: 'Lync Server 2013: tblPrincipalInvites'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1081dbec8575eac0cc2aca7fc434b5801668f447
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a>tblPrincipalInvites в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-06-25_

ТблпринЦипалинвитес включает приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением.

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
<td><p>Принид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор участника.</p></td>
</tr>
<tr class="even">
<td><p>ИНВИД</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Уникальный последовательный номер (для идентификатора участника), сформированный из таблицы Тблластинвитеид.</p></td>
</tr>
<tr class="odd">
<td><p>Нодеид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор узла (только для комнаты чата).</p></td>
</tr>
<tr class="even">
<td><p>Креатедон</p></td>
<td><p>DateTime, NOT NULL</p></td>
<td><p>Время создания.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Параметры

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
<td><p>&lt;Принид, Нодеид&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>Принид</p></td>
<td><p>Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</p></td>
</tr>
<tr class="odd">
<td><p>Нодеид</p></td>
<td><p>Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

