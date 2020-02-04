---
title: 'Lync Server 2013: tblChat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615031(v=OCS.15)
ms:contentKeyID: 48185203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f3879924b37fa535973116af599f4713c58a207
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblchat-in-lync-server-2013"></a>tblChat в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-12_

Тблчат включает в себя все сообщения чата.

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
<td><p>чаннелид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор узла.</p></td>
</tr>
<tr class="even">
<td><p>чатид</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Уникальный порядковый номер (код узла), который определяет порядок помещения в чат, созданный Тблластчатид таблицей.</p></td>
</tr>
<tr class="odd">
<td><p>чатдате</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Метка времени для сообщения чата.</p></td>
</tr>
<tr class="even">
<td><p>Идентификатора пользователя</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор участника плаката.</p></td>
</tr>
<tr class="odd">
<td><p>"о себе"</p></td>
<td><p>bit, NOT NULL</p></td>
<td><p>Значение true, если сообщение является предупредительным сообщением. В противном случае — false.</p></td>
</tr>
<tr class="even">
<td><p>конфликтов</p></td>
<td><p>nvarchar (max), NOT NULL</p></td>
<td><p>Содержимое чата (версия обычного текста). Содержимое обычно задается в виде обычного текста со следующими исключениями:</p>
<ul>
<li><p>Файлы представлены в виде ссылок MA-филелинк: Links.</p></li>
<li><p>Ссылки представлены в виде HTML-элемента (несмотря на то, что тип контента не может считаться HTML).</p></li>
<li><p>Истории в формате "[История]........".</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>RTF</p></td>
<td><p>varchar (max)</p></td>
<td><p>Содержимое чата (версия RTF). Может иметь значение null, если клиент не предоставил его.</p></td>
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
<td><p>&lt;Чаннелид, чат&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

