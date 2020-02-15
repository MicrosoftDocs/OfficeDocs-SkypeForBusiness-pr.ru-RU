---
title: 'Lync Server 2013: tblNode'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81a57d54663b1adf837a4ca38896dd7da3eff883
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a>tblNode в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-12_

tblNode содержит дерево объектов (с узлами категории или комнаты чата), которое управляется в панели управления Lync Server 2013 и административные командлеты.

### <a name="columns"></a>Columns

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
<td><p>nodeID</p></td>
<td><p>int, не null</p></td>
<td><p>ИД узла (уникальное число).</p></td>
</tr>
<tr class="even">
<td><p>нодегуид</p></td>
<td><p>GUID, not null</p></td>
<td><p>Глобальный уникальный ИД узла.</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>int</p></td>
<td><p>ИД узла родительского элемента. Корневой узел (с ИД 1) включает себя в качестве родительского элемента.</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>bit, не равно null</p></td>
<td><p>True, если узел является категорией.</p>
<p>False, если узел является комнатой чата.</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>nvarchar (256), не может быть null</p></td>
<td><p>Имя узла.</p></td>
</tr>
<tr class="even">
<td><p>нодедеск</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>Описание узла.</p></td>
</tr>
<tr class="odd">
<td><p>invite</p></td>
<td><p>Битовая</p></td>
<td><p>Для категорий:</p>
<ul>
<li><p>True, если приглашения включены.</p></li>
<li><p>False, если приглашения отключены.</p></li>
</ul>
<p>Для комнат:</p>
<ul>
<li><p>False, если приглашения отключены (переопределяет родительскую категорию).</p></li>
<li><p>Null, если настройки приглашений наследуются от родительской категории.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>шедших</p></td>
<td><p>Битовая</p></td>
<td><p>Для категорий:</p>
<ul>
<li><p>True, если журнал чата включен.</p></li>
<li><p>False, если журнал чата отключен.</p></li>
</ul>
<p>Для комнат:</p>
<ul>
<li><p>Определен.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>филепост</p></td>
<td><p>Битовая</p></td>
<td><p>Для категорий:</p>
<ul>
<li><p>True, если передача файлов разрешена.</p></li>
<li><p>False, если передача файлов запрещена.</p></li>
</ul>
<p>Для комнат:</p>
<ul>
<li><p>Определен.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>активирован</p></td>
<td><p>bit, not null</p></td>
<td><p>True, если комната чата отключена. Применяется только к комнатам чата. (Для категорий — False.)</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>такое</p></td>
<td><p>smallint, не может быть null</p></td>
<td><p>Поведение (поиск в таблице EnumValue):</p>
<ul>
<li><p>4: Normal (обычные комнаты чата).</p></li>
<li><p>5: Auditorium (комнаты чата аудитории, участвовать могут только докладчики).</p></li>
</ul>
<p>Применимо только к комнатам чата.</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>smallint, not null</p></td>
<td><p>Видимость (поиск в таблице EnumValue):</p>
<ul>
<li><p>2: Private</p></li>
<li><p>3: Scoped</p></li>
<li><p>6: Open</p></li>
</ul>
<p>Применяется только для комнат чата.</p></td>
</tr>
<tr class="even">
<td><p>сиопид</p></td>
<td><p>GUID</p></td>
<td><p>Глобальный уникальный ИД надстройки, если надстройка связана с этой комнатой чата. (Категории не имеют надстроек.)</p>
<p>Для поиска сведений о надстройках используется таблица SiopWhiteList.</p></td>
</tr>
<tr class="odd">
<td><p>нодеаддедби</p></td>
<td><p>int, not null</p></td>
<td><p>ИД субъекта, который создал этот узел.</p></td>
</tr>
<tr class="even">
<td><p>нодеаддедон</p></td>
<td><p>bigint, not null</p></td>
<td><p>Метка времени создания узла.</p></td>
</tr>
<tr class="odd">
<td><p>нодеупдатедби</p></td>
<td><p>int, not null</p></td>
<td><p>ИД субъекта, который выполнил последнее обновление этого узла.</p></td>
</tr>
<tr class="even">
<td><p>нодеупдатедон</p></td>
<td><p>bigint, not null</p></td>
<td><p>Метка времени последнего обновления этого узла.</p></td>
</tr>
<tr class="odd">
<td><p>пуржедон</p></td>
<td><p>datetime</p></td>
<td><p>Время последней операции очистки (удаление областей из таблицы tblScopedPrincipal и ролей из таблицы tblPrincipalRole) для этого узла. Используется механизмом обновления внутреннего кэша службы чата.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Keys

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
<td><p>nodeID</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>такое</p></td>
<td><p>Внешний ключ с поиском в таблице tblEnumValue.valueID.</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>Внешний ключ с поиском в таблице tblEnumValue.valueID.</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>Внешний ключ с поиском в таблице tblNode.nodeID.</p></td>
</tr>
<tr class="odd">
<td><p>сиопид</p></td>
<td><p>Внешний ключ с поиском в таблице tblSiopWhiteList.siopId.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

