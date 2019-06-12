---
title: 'Lync Server 2013: tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 698d6b07d5662a403a7485d009a39a0a8beccc73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a>tblRoleType в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-06-25_

Тблролетипе — это статическая таблица подстановки с типами ролей и связанными с ними наборами разрешений.

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
<td><p>Ртипеид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор типа роли.</p></td>
</tr>
<tr class="even">
<td><p>Ртипедеск</p></td>
<td><p>nvarchar (256), NOT NULL</p></td>
<td><p>Описание типа роли. Доступно четыре роли:</p>
<ul>
<li><p>Член: участник комнаты чата</p></li>
<li><p>Руководитель: руководитель комнаты чата</p></li>
<li><p>Выставлено сообщение: выступающий для комнаты чата Аудиториум</p></li>
<li><p>Создатель: может создавать комнаты чата</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Ртипеалловедпермсет</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Наборы разрешений для роли. Используются следующие биты:</p>
<ul>
<li><p>2: значение true, если роль может управлять узлами.</p></li>
<li><p>4: значение true, если роль может создавать дочерние узлы.</p></li>
<li><p>7: значение true, если роль может присоединиться к комнате чата (или дочерним комнатам чатов для категории).</p></li>
<li><p>8: true, если роль может общаться в комнате чата (или в дочерних комнатах чата).</p></li>
<li><p>10: true, если роль может читать историю чата, даже если она не присоединяется к комнате чата.</p></li>
<li><p>11: true, если роль может видеть комнату чата. (Это улучшено с помощью таких факторов, как область видимости и видимость.)</p></li>
<li><p>12: true, если роль может общаться в комнате чата Аудиториум.</p></li>
<li><p>13: true, если роль может обойти правила видимости при просмотре узлов.</p></li>
</ul></td>
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
<td><p>Ртипеид</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

