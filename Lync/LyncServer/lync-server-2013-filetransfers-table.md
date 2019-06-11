---
title: 'Lync Server 2013: таблица FileTransfers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71e53e59e3ed1391adebff8b7c4046ef3c23aa21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a>Таблица FileTransfers в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

Каждая запись представляет собой один сеанс передачи файлов.


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
<td><p><strong>Сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Время запроса сеанса. Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Сессионидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Основной, внешний</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации сеанса. Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Имя файла</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Имя файла.</p></td>
</tr>
<tr class="even">
<td><p><strong>Филеидентити</strong></p></td>
<td><p>идентификатора</p></td>
<td></td>
<td><p>Уникальный идентификатор, позволяющий отличать передачу файлов с одним и тем же именем файла.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Файлах</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p>Primary</p></td>
<td><p>Используется для идентификации каждого сообщения к исполнению, связанного с этим сообщением.</p></td>
</tr>
<tr class="even">
<td><p><strong>Отвечать</strong></p></td>
<td><p>бит</p></td>
<td></td>
<td><p>Может иметь значение истина или NULL. Если значение равно TRUE, то значение "отклонить" и "Отмена" будет равно NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Отклонил</strong></p></td>
<td><p>бит</p></td>
<td></td>
<td><p>Может иметь значение истина или NULL. Если значение равно TRUE, то "принимать" и "Отмена" будут иметь значение NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>Отмена</strong>.</p></td>
<td><p>бит</p></td>
<td></td>
<td><p>Может иметь значение истина или NULL. Если значение равно TRUE, то принять и отклонить будет значение NULL.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

