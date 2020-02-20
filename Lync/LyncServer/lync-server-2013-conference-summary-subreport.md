---
title: 'Lync Server 2013: сводный отчет по конференциям'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cc0e61333b491a4d28e42167a9e60823e0331d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a>Сводный отчет по конференциям в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-06_

Вложенный сводный отчет о конференции содержит обзор неудачных сеансов конференц-связи. Такие неудачные сеансы дополнительно делятся по типу — сеансы Focus и сеансы MCU.

<div>

## <a name="filters"></a>Фильтры

Фильтры позволяют вам возвратить уточненный набор данных или просматривать возвращенные данные различными способами. В следующей таблице перечислены фильтры, которые вы можете использовать во вложенном сводном отчете о конференции.

### <a name="conference-summary-subreport-filters"></a>Фильтры вложенного сводного отчета о конференции

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</p>
<p>7/7/2012 1:00 PM</p>
<p>Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</p>
<p>7/7/2012</p>
<p>Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</p>
<p>7/3/2012</p>
<p>Неделя всегда начинается с воскресенья и заканчивается субботой.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</p>
<p>7/7/2012 13:00.</p>
<p>Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</p>
<p>7/7/2012</p>
<p>Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</p>
<p>7/3/2012</p>
<p>Неделя всегда начинается с воскресения и заканчивается субботой.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ресурсов</strong></p></td>
<td><p>Полное доменное имя пула Регистраторов или пограничного сервера. Вы можете выбрать отдельный пул или щелкнуть элемент <strong>[All]</strong> (Все) для просмотра данных из всех пулов. Этот раскрывающийся список заполняется автоматически на основании записей в базе данных.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Метрик

В следующей таблице перечислены сведения, представленные во вложенном сводном отчете о конференции.

### <a name="conference-summary-subreport-metrics"></a>Метрики вложенного сводного отчета о конференции

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Возможность сортировки по этому показателю</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Total conferences</strong> (Всего конференций)</p></td>
<td><p>Нет</p></td>
<td><p>Общее количество проведенных конференций.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total conference sessions</strong> (Всего сеансов конференций)</p></td>
<td><p>Нет</p></td>
<td><p>Общее количество сеансов конференций. Отдельная конференция может иметь несколько сеансов; например, конференция может включать в себя как сеанс Focus, так и сеанс MCU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Overall session failure rate</strong> (Общий уровень сбоев сеансов)</p></td>
<td><p>Нет</p></td>
<td><p>Процентное отношение всех конференций, завершившихся со сбоем.</p></td>
</tr>
<tr class="even">
<td><p><strong>Focus sessions</strong> (Сеансы Focus)</p></td>
<td><p>Нет</p></td>
<td><p>Общее количество сеансов Focus.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Focus failure rate</strong> (Уровень сбоев Focus)</p></td>
<td><p>Нет</p></td>
<td><p>Процентное отношение сеансов Focus, завершившихся со сбоем.</p></td>
</tr>
<tr class="even">
<td><p>MCU sessions (Сеансы с MCU)</p></td>
<td><p>Нет</p></td>
<td><p>Общее количество сеансов MCU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MCU failure rate</strong> (Уровень сбоев MCU)</p></td>
<td><p>Нет</p></td>
<td><p>Процентное отношение сеансов MCU, завершившихся со сбоем.</p></td>
</tr>
<tr class="even">
<td><p><strong>MCU sessions by modality</strong> (Сеансы MCU по модальности)</p></td>
<td><p>Нет</p></td>
<td><p>Общее количество сеансов MCU, сгруппированных по модальности (например, конференции с обменом мгновенными сообщениями).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Failure rate by modality</strong> (Уровень сбоев по модальности)</p></td>
<td><p>Нет</p></td>
<td><p>Процентное отношение неудачных сеансов MCU, сгруппированных по модальности (например, конференции с обменом мгновенными сообщениями).</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

