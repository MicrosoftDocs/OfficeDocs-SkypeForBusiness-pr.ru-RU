---
title: 'Lync Server 2013: tblNode'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84bf7cf57f9890093a56deb2e0769b82e92aa0ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a>tblNode в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-12_

Тблноде включает дерево объектов (с узлами "Категория" или "комната чата") как управляемое на панели управления Lync Server 2013 и административных командлетов.

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
<td><p>Нодеид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор узла (уникальный номер).</p></td>
</tr>
<tr class="even">
<td><p>Нодегуид</p></td>
<td><p>GUID, а не NULL</p></td>
<td><p>GUID узла.</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>целое</p></td>
<td><p>Идентификатор узла родителя. Корневой узел (с ИДЕНТИФИКАТОРом 1) также включает себя как родительский.</p></td>
</tr>
<tr class="even">
<td><p>Узла</p></td>
<td><p>bit, NOT NULL</p></td>
<td><p>Значение true, если узел является категорией.</p>
<p>Значение false, если узел является комнатой чата.</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>nvarchar (256), NOT NULL</p></td>
<td><p>Имя узла.</p></td>
</tr>
<tr class="even">
<td><p>Нодедеск</p></td>
<td><p>nvarchar (256), NOT NULL</p></td>
<td><p>Описание узла.</p></td>
</tr>
<tr class="odd">
<td><p>сообщение</p></td>
<td><p>бит</p></td>
<td><p>Для категорий:</p>
<ul>
<li><p>Значение true, если приглашения включены.</p></li>
<li><p>Значение false, если приглашения отключены.</p></li>
</ul>
<p>Для комнат:</p>
<ul>
<li><p>Значение false, если приглашения отключены (переопределяет родительскую категорию).</p></li>
<li><p>Значение null, если параметр приглашения наследуется от родительской категории.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>войдет</p></td>
<td><p>бит</p></td>
<td><p>Для категорий:</p>
<ul>
<li><p>Значение true, если история чата включена.</p></li>
<li><p>Значение false, если ведение журнала чата отключено.</p></li>
</ul>
<p>Для комнат:</p>
<ul>
<li><p>Значения.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Филепост</p></td>
<td><p>бит</p></td>
<td><p>Для категорий:</p>
<ul>
<li><p>Значение true, если отправка файлов разрешена.</p></li>
<li><p>Значение false, если отправка файлов запрещена.</p></li>
</ul>
<p>Для комнат:</p>
<ul>
<li><p>Значения.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>отключает</p></td>
<td><p>bit, NOT NULL</p></td>
<td><p>Значение true, если комната чата отключена. Применимо только к комнатам чата. (Ложь для категорий.)</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>расширения</p></td>
<td><p>smallint, NOT NULL</p></td>
<td><p>Поведение (Поиск в таблице Енумвалуе):</p>
<ul>
<li><p>4: обычный (обычные комнаты чата).</p></li>
<li><p>5: Аудиториум (Аудиториум) — комнаты чата только выступающие могут участвовать в программе.</p></li>
</ul>
<p>Применимо только к комнатам чата.</p></td>
</tr>
<tr class="odd">
<td><p>Отображение</p></td>
<td><p>smallint, NOT NULL</p></td>
<td><p>Visibility (Поиск в таблице Енумвалуе):</p>
<ul>
<li><p>2: частный</p></li>
<li><p>3: область охвата</p></li>
<li><p>6: открыть</p></li>
</ul>
<p>Применимо только к комнатам чата.</p></td>
</tr>
<tr class="even">
<td><p>Сиопид</p></td>
<td><p>Глобальный уникальный идентификатор (GUID)</p></td>
<td><p>GUID надстройки, если надстройка связана с этой комнатой чата. (В категориях нет надстроек.)</p>
<p>Сведения о надстройке ищутся в таблице Сиопвхителист.</p></td>
</tr>
<tr class="odd">
<td><p>Нодеаддедби</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор участника, который создал этот узел.</p></td>
</tr>
<tr class="even">
<td><p>Нодеаддедон</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Метка времени создания узла.</p></td>
</tr>
<tr class="odd">
<td><p>Нодеупдатедби</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор участника, который последним обновил этот узел.</p></td>
</tr>
<tr class="even">
<td><p>Нодеупдатедон</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Метка времени последнего обновления этого узла.</p></td>
</tr>
<tr class="odd">
<td><p>Пуржедон</p></td>
<td><p>datetime</p></td>
<td><p>Время последней операции очистки (удаления областей из таблицы ТблскопедпринЦипал и ролей из ТблпринЦипалроле таблицы), которые затронули этот узел. Это используется механизмом обновления внутреннего кэша в службе чата.</p></td>
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
<td><p>Нодеид</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>расширения</p></td>
<td><p>Внешний ключ с подстановкой в таблице Тбленумвалуе. Валуеид.</p></td>
</tr>
<tr class="odd">
<td><p>Отображение</p></td>
<td><p>Внешний ключ с подстановкой в таблице Тбленумвалуе. Валуеид.</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</p></td>
</tr>
<tr class="odd">
<td><p>Сиопид</p></td>
<td><p>Внешний ключ с подстановкой в таблице Тблсиопвхителист. Сиопид.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

