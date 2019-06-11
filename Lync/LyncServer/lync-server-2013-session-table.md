---
title: 'Lync Server 2013: таблица Session'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab4eb63b95ecdf08c1967babba39cff2b2abf19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a>Таблица Session в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-09-09_

Каждая запись представляет собой один сеанс, в котором задействовано звуковое сопровождение, звук и видео. В нем содержатся общие сведения о сеансе. Сеанс определяется как диалоговое окно с помощью звукового или видеосигнала (SIP) между двумя конечными точками.


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
<td><p><strong>Конференцедатетиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Ссылка из <a href="lync-server-2013-dialog-table.md">таблицы диалогов в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Сессионсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Ссылка из <a href="lync-server-2013-dialog-table.md">таблицы диалогов в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Конференцекэй</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Клавиша Конференции. На которую ссылается <a href="lync-server-2013-conference-table.md">Таблица конференции в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Коррелатионкэй</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Ключ корреляции. На которую ссылается <a href="lync-server-2013-sessioncorrelation-table.md">Таблица сессионкоррелатион в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Диалогкатегори</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>Категория диалогового окна; 0 — это сервер Lync Server для устранения проблем; 1 — это сервер исправлений для шлюза PSTN Gateway.</p></td>
</tr>
<tr class="even">
<td><p><strong>Медиатионсервербипассфлаг</strong></p></td>
<td><p>бит</p></td>
<td></td>
<td><p>Флаг, указывающий, обходит ли звонок.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Медиабипассварнингфлаг</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Это поле, если оно указано, указывает, почему звонок не обходится даже в том случае, если идентификаторы обхода не совпадают. Для Lync Server определено только одно значение.</p>
<p>0x0001 — Неизвестный идентификатор обхода для сетевого адаптера по умолчанию.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Время начала звонка.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Время окончания звонка.</p></td>
</tr>
<tr class="even">
<td><p><strong>Каллерпул</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Пул вызывающего абонента. Указана <a href="lync-server-2013-pool-table.md">Таблица пула в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Каллипул</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Пул приемника вызова. Указана <a href="lync-server-2013-pool-table.md">Таблица пула в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Каллипаи</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Универсальный код ресурса (URI) SIP в удостоверении SIP (паи) принимающей конечной точки. Ссылка на которую имеется <a href="lync-server-2013-user-table.md">в таблице Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Каллерури</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>URI вызывающего абонента. Ссылка на которую имеется <a href="lync-server-2013-user-table.md">в таблице Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Каллерендпоинт</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Конечная точка вызывающего абонента. На которую ссылается <a href="lync-server-2013-endpoint-table.md">Таблица конечная точка в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Каллерусеражент</strong></p></td>
<td><p>бит</p></td>
<td><p>Другом</p></td>
<td><p>Агент пользователя вызывающего абонента. Ссылка из <a href="lync-server-2013-useragent-table.md">таблицы UserAgent в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Каллприорити</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Приоритет этого звонка.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Классифиедпуркалл</strong></p></td>
<td><p>бит</p></td>
<td></td>
<td><p>Этот столбец устарел и не используется в Microsoft Lync Server 2013. Вместо этого эти сведения выводятся в виде линий для отдельных носителей. Дополнительные сведения можно найти в <a href="lync-server-2013-medialine-table.md">таблице медиалине в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Каллерпаи</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>P-утвержденные-идентификационные данные пользователя, который присоединил звонок. Идентификатор P-Assert (паи) используется для передачи истинного удостоверения пользователя, который находил звонок.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Каллиендпоинт</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Конечная точка, в которой был получен звонок.</p></td>
</tr>
<tr class="even">
<td><p><strong>Каллиусеражент</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Агент пользователя, который использовался пользователем, который получил звонок. Агенты пользователей представляют собой клиентскую конечную точку.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Каллиури</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Универсальный код ресурса (URI) SIP пользователя, который получил звонок.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

