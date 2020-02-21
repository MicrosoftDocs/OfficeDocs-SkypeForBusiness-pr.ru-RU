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
ms.openlocfilehash: efadf0e5e850b825f6e5f47928e615ba32b9fd33
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblchat-in-lync-server-2013"></a>tblChat в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-12_

Таблица tblChat содержит все сообщения чата.

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
<td><p>channelId</p></td>
<td><p>int, not null</p></td>
<td><p>ИД узла.</p></td>
</tr>
<tr class="even">
<td><p>чатид</p></td>
<td><p>bigint, not null</p></td>
<td><p>Уникальный порядковый номер (для каждого ИД узла), определяющий порядок чата, который создается таблицей tblLastChatId.</p></td>
</tr>
<tr class="odd">
<td><p>чатдате</p></td>
<td><p>bigint, not null</p></td>
<td><p>Метка времени для сообщения чата.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, not null</p></td>
<td><p>ИД участника, отправителя сообщения.</p></td>
</tr>
<tr class="odd">
<td><p>Оповещатель</p></td>
<td><p>bit, not null</p></td>
<td><p>True, если сообщение является оповещением. В противном случае — False.</p></td>
</tr>
<tr class="even">
<td><p>содержимое</p></td>
<td><p>nvarchar (max), not null</p></td>
<td><p>Содержимое чата (версия обычного текста). Обычно содержимое представлено в виде обычного текста за следующими исключениями:</p>
<ul>
<li><p>Файлы, представленные в виде ссылок ma-filelink:.</p></li>
<li><p>Ссылки, представленные в виде элементов HTML (однако тип содержимого не может рассматриваться HTML).</p></li>
<li><p>Статьи, помеченные как "[STORY]....".</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>RTF</p></td>
<td><p>varchar (max)</p></td>
<td><p>Содержимое чата (версия RTF). Может иметь значение NULL, если клиент не предоставляет ее.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Key

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

