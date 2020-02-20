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
ms.openlocfilehash: 554491ebdc09789a2704835dc0dce3ddc34f8b0b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a>Таблица Sessions в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-09-09_

Каждая запись представляет один сеанс, который включает звук, аудио и видео. Он содержит общие сведения о сеансе. Сеанс определяется как диалоговое окно аудио-и видеоинициации (SIP) между двумя конечными точками.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Column</strong></th>
<th><strong>Тип данных</strong></th>
<th><strong>Ключ или индекс</strong></th>
<th><strong>Details</strong></th>
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
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Ссылка из <a href="lync-server-2013-dialog-table.md">таблицы диалогов в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>конференцекэй</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Ключ конференции. Ссылка из <a href="lync-server-2013-conference-table.md">таблицы конференций в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>коррелатионкэй</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Ключ корреляции. Ссылка из <a href="lync-server-2013-sessioncorrelation-table.md">таблицы таблица sessioncorrelation в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>диалогкатегори</strong></p></td>
<td><p>Битовая</p></td>
<td><p> </p></td>
<td><p>Категория диалоговых окон; 0 — сервер Lync Server — это ветвь сервера-посредника; 1 — сервер-посредник для шлюза PSTN.</p></td>
</tr>
<tr class="even">
<td><p><strong>медиатионсервербипассфлаг</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Флаг, указывающий, выполнял ли вызов обход сервера-посредника.</p></td>
</tr>
<tr class="odd">
<td><p><strong>медиабипассварнингфлаг</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Если это поле присутствует, оно указывает, почему вызов не может быть обойден, даже если идентификаторы обхода совпадают. Для Lync Server определено только одно значение.</p>
<p>0x0001 — неизвестный идентификатор обхода для сетевого адаптера по умолчанию.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Время начала вызова.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Время окончания вызова.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллерпул</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Пул вызывающего абонента. Указан из <a href="lync-server-2013-pool-table.md">таблицы пула в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллипул</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Пул приемника вызовов. Указан из <a href="lync-server-2013-pool-table.md">таблицы пула в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллипаи</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Универсальный код ресурса (URI) SIP в удостоверении (PAI) принимающей конечной точки. Ссылка из <a href="lync-server-2013-user-table.md">таблицы Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллерури</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>URI вызывающего абонента. Ссылка из <a href="lync-server-2013-user-table.md">таблицы Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллерендпоинт</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Конечная точка вызывающего абонента. Указана в <a href="lync-server-2013-endpoint-table.md">таблице конечная точка в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллерусеражент</strong></p></td>
<td><p>Битовая</p></td>
<td><p>Правительства</p></td>
<td><p>Агент пользователя вызывающего абонента. Ссылка из <a href="lync-server-2013-useragent-table.md">таблицы UserAgent в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллприорити</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Приоритет этого вызова.</p></td>
</tr>
<tr class="odd">
<td><p><strong>классифиедпуркалл</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Этот столбец устарел и не используется в Microsoft Lync Server 2013. Вместо этого эти сведения выводятся на основе линий отдельных носителей. Для получения дополнительных сведений обратитесь к <a href="lync-server-2013-medialine-table.md">таблице MediaLine в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>каллерпаи</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>P — утверждено — идентификатор пользователя, который поместил вызов. P-Assert-Identity (PAI) используется для передачи истинного удостоверения пользователя, который поместил вызов.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллиендпоинт</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Конечная точка, в которой был получен вызов.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллиусеражент</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Агент пользователя, который использовался пользователем, получившим вызов. Агенты пользователей представляют устройство конечной точки клиента.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллиури</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Универсальный код ресурса (URI) SIP пользователя, который получил вызов.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

