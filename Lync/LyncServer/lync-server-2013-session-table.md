---
title: 'Lync Server 2013: таблица Session'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81b97d6a7521add62817147ae87995508b841f2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732399"
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
<td><p><strong>конференцедатетиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Ссылка из <a href="lync-server-2013-dialog-table.md">таблицы диалогов в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Ссылка из <a href="lync-server-2013-dialog-table.md">таблицы диалогов в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>конференцекэй</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Клавиша Конференции. На которую ссылается <a href="lync-server-2013-conference-table.md">Таблица конференции в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>коррелатионкэй</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Ключ корреляции. На которую ссылается <a href="lync-server-2013-sessioncorrelation-table.md">Таблица сессионкоррелатион в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>диалогкатегори</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>Категория диалогового окна; 0 — это сервер Lync Server для устранения проблем; 1 — это сервер исправлений для шлюза PSTN Gateway.</p></td>
</tr>
<tr class="even">
<td><p><strong>медиатионсервербипассфлаг</strong></p></td>
<td><p>бит</p></td>
<td></td>
<td><p>Флаг, указывающий, обходит ли звонок.</p></td>
</tr>
<tr class="odd">
<td><p><strong>медиабипассварнингфлаг</strong></p></td>
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
<td><p><strong>каллерпул</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Пул вызывающего абонента. Указана <a href="lync-server-2013-pool-table.md">Таблица пула в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллипул</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Пул приемника вызова. Указана <a href="lync-server-2013-pool-table.md">Таблица пула в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллипаи</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Универсальный код ресурса (URI) SIP в удостоверении SIP (паи) принимающей конечной точки. Ссылка на которую имеется <a href="lync-server-2013-user-table.md">в таблице Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллерури</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>URI вызывающего абонента. Ссылка на которую имеется <a href="lync-server-2013-user-table.md">в таблице Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллерендпоинт</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Конечная точка вызывающего абонента. На которую ссылается <a href="lync-server-2013-endpoint-table.md">Таблица конечная точка в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллерусеражент</strong></p></td>
<td><p>бит</p></td>
<td><p>Другом</p></td>
<td><p>Агент пользователя вызывающего абонента. Ссылка из <a href="lync-server-2013-useragent-table.md">таблицы UserAgent в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллприорити</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Приоритет этого звонка.</p></td>
</tr>
<tr class="odd">
<td><p><strong>классифиедпуркалл</strong></p></td>
<td><p>бит</p></td>
<td></td>
<td><p>Этот столбец устарел и не используется в Microsoft Lync Server 2013. Вместо этого эти сведения выводятся в виде линий для отдельных носителей. Дополнительные сведения можно найти в <a href="lync-server-2013-medialine-table.md">таблице медиалине в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>каллерпаи</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>P-утвержденные-идентификационные данные пользователя, который присоединил звонок. Идентификатор P-Assert (паи) используется для передачи истинного удостоверения пользователя, который находил звонок.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллиендпоинт</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Конечная точка, в которой был получен звонок.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллиусеражент</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Агент пользователя, который использовался пользователем, который получил звонок. Агенты пользователей представляют собой клиентскую конечную точку.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллиури</strong></p></td>
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

