---
title: 'Lync Server 2013: таблица таблица progressreport'
description: 'Lync Server 2013: таблица таблица progressreport.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d36ee2ab75410ea2462da4b647ef5b45afefb1bb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579825"
---
# <a name="progressreport-table-in-lync-server-2013"></a>Таблица Таблица progressreport в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Отчеты о ходе выполнения строятся на основе данных, отправляемых клиентом в базу данных после завершения вызова или сеанса. Отчеты о ходе выполнения записываются только для тех звонков и сеансов, которые Lync Server 2013 определяет как полезные для диагностических целей.

Поля ErrorTime, ErrorReportSeq и ProgressReportSeq могут относиться не к ошибкам, а к сообщениям, указывающим состояние вызовов или сообщений.


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
<th>Ключ или индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Поля errortime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Дата и время отчета об ошибках хода выполнения, который содержит этот отчет о ходе выполнения. Дополнительные сведения см. <a href="lync-server-2013-errorreport-table.md">в таблице errorreport в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>еррорид</strong></p></td>
<td><p>int</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Идентификатор, используемый вместе с ErrorTime и ProgressReportSeq для однозначного определения отчета о ходе выполнения. Дополнительные сведения см. <a href="lync-server-2013-errorreport-table.md">в таблице errorreport в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Идентификатор отчета об ошибках. ErrorReporSeq используется вместе с ErrorTime для однозначного определения отчета об ошибках. Дополнительные сведения см. <a href="lync-server-2013-errorreport-table.md">в таблице errorreport в Lync Server 2013</a></p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>прогрессрепортсек</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Идентификатор отчета о ходе выполнения. Используется вместе с ErrorTime и ErrorReportSeq для однозначного определения отчета о ходе выполнения.</p></td>
</tr>
<tr class="odd">
<td><p><strong>мсдиагид</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Диагностический идентификатор отчета о ходе выполнения.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Сервер, который отправил отчет об ошибках (если отчет был отправлен из серверного компонента). Дополнительные сведения см. <a href="lync-server-2013-servers-table.md">в таблице Servers в Lync Server 2013</a> . Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Процесс Lync Server, к которому относится отчет. Дополнительные сведения см. в таблице приложений.</p></td>
</tr>
<tr class="even">
<td><p><strong>Detail</strong></p></td>
<td><p>изображение</p></td>
<td></td>
<td><p>Сведения о выполнении сохраняются в двоичном формате для экономии места. Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:</p>
<p>cast(cast(Detail as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>телеметрид</strong></p></td>
<td><p>Идентификатора</p></td>
<td></td>
<td><p>Уникальный идентификатор, который сопоставляет сведения о времени присоединения для разных компонентов, вовлеченных в конференцию.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионсетуптиме</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Время (в миллисекундах) для присоединения к конференции конкретного компонента.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

