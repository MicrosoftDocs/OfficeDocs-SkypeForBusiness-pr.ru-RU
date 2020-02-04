---
title: 'Lync Server 2013: таблица AudioSignal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 950c8457f80c69af5875064fff55c5ac7df61b24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a>Таблица AudioSignal в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-11-12_

Каждая запись представляет метрики звукового сигнала для одной конечной точки. Обычно каждый звонок состоит из двух записей: одной из них, а другая — для вызываемого абонента.


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
<td><p>На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>медиалинелабел</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>фромкаллер</strong></p></td>
<td><p>бит</p></td>
<td><p>Primary</p></td>
<td><p>0: данные вызывающего абонента</p>
<p>1: данные вызывающего абонента</p></td>
</tr>
<tr class="odd">
<td><p><strong>сендсигналлевел</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Обозначает уровень звукового сигнала после аналогового усиления контроля. Единицей измерения для этой метрики является Дбмо. Для приемлемого качества оно должно быть не менее 30 Дбмо. Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</p></td>
</tr>
<tr class="even">
<td><p><strong>реквсигналлевел</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Смотрите Сендсигналлевел.</p></td>
</tr>
<tr class="odd">
<td><p><strong>сендноиселевел</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Обозначает уровень звукового шума, поступающего после аналогового усиления. Единицей измерения для этой метрики является Дбмо. Для приемлемого качества оно должно быть менее 35 Дбмо. Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</p></td>
</tr>
<tr class="even">
<td><p><strong>реквноиселевел</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Смотрите Сендноиселевел.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ечоретурн</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Показатель возвращающего потери при возврате эха. Единицей измерения для этой метрики является dB. Более низкие значения представляют менее эхо. Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</p></td>
</tr>
<tr class="even">
<td><p><strong>аудиоспеакерглитчрате</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Среднее число сбоев в течение пяти минут для отрисовки динамик. Для хорошего качества это должно быть меньше, чем один за пять минут. Не сообщается серверам конференц-связи, серверам или IP-телефонам.</p></td>
</tr>
<tr class="odd">
<td><p><strong>аудиомикглитчрате</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Среднее число сбоев в течение пяти минут для захвата микрофона. Для хорошего качества это должно быть менее чем на одну 5 минут. Не сообщается серверам конференц-связи, серверам или IP-телефонам.</p></td>
</tr>
<tr class="even">
<td><p><strong>аудиотиместампдрифтратемик</strong></p></td>
<td><p>десятичное число (9, 2)</p></td>
<td><p> </p></td>
<td><p>Частота расхождения синхронизирующих сигналов для микрофона, относящихся к тактовой частоте процессора.</p></td>
</tr>
<tr class="odd">
<td><p><strong>аудиотиместампдрифтратеспк</strong></p></td>
<td><p>десятичное число (9, 2)</p></td>
<td><p> </p></td>
<td><p>Частота расхождения синхронизирующих импульсов устройства для динамиков относительно часов процессора.</p></td>
</tr>
<tr class="even">
<td><p><strong>аудиотиместамперрормикмс</strong></p></td>
<td><p>десятичное число (9, 2)</p></td>
<td><p> </p></td>
<td><p>Частота расхождения синхронизирующих импульсов устройства для динамиков относительно часов процессора.</p>
<p>Средняя пометка времени потока захвата микрофона в миллисекундах за последние 20 секунд звонка.</p></td>
</tr>
<tr class="odd">
<td><p><strong>аудиотиместамперрорспкмс</strong></p></td>
<td><p>десятичное число (9, 2)</p></td>
<td><p> </p></td>
<td><p>Средняя отметка времени линейного потока обработки динамиков в миллисекундах за последние 20 секунд вызова.</p></td>
</tr>
<tr class="even">
<td><p><strong>всентрикаусес</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>Голосовая связь — это режим двусторонней печати с ограниченными возможностями перерывов. Причины для записи голосового переключателя:</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>Причина может быть сочетанием отдельных причин. ENTER_VS_FORCEORCONVERGENCE может быть включена только в RegKey для целей тестирования.</p>
<p>Тип данных этого столбца изменен в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ечоевенткаусес</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Причины возникновения события echo:</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0x01</p>
<p>ECHO_EVENT_POSTAEC_ECHO 0x02</p>
<p>ECHO_EVENT_ANLP 0x04</p>
<p>ECHO_EVENT_DNLP 0x08</p>
<p>ECHO_EVENT_MIC_CLIPPING 0x10</p>
<p>ECHO_EVENT_BAD_STATE 0x20</p>
<p>Причина может быть сочетанием отдельных причин.</p></td>
</tr>
<tr class="even">
<td><p><strong>ечоперцентмиЦин</strong></p></td>
<td><p>десятичное число (5; 2)</p></td>
<td><p> </p></td>
<td><p>Процент времени, когда в потоке захвата микрофоном обнаруживался эхосигнал. Обычно низкие значения отображаются для гарнитур или телефонных трубок, а высокие значения – для телефонных или автономных динамиков. Для устройств, которые поддерживают встроенную возможность подавления акустического эхосигнала, высокие значения указывают утечку эхосигнала. Для других устройств эти единицы измерения не должны использоваться для оценки качества устройства.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ечоперцентсенд</strong></p></td>
<td><p>десятичное число (5; 2)</p></td>
<td></td>
<td><p>Процент времени, в течение которого обнаружено Эхо-сообщение в отправленном потоке. Высокий процент эха в потоках отправки указывает на наличие утечки эха.</p></td>
</tr>
<tr class="even">
<td><p><strong>рксагксигналлевел</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Уровень сигнала на сервере обновлений от шлюза; Это относится только к серверу обновлений. Единица измерения этой метрики — Дбов. Для хорошего качества допустимый диапазон должен составлять от [-30 до-18] Дбов.</p></td>
</tr>
<tr class="odd">
<td><p><strong>рксагкноиселевел</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Уровень сигнала на сервере обновлений от шлюза. Это относится только к серверу обновлений. Единица измерения этой метрики — Дбов. Для хорошего качества допустимый диапазон должен быть меньше, чем-50 Дбов.</p></td>
</tr>
<tr class="even">
<td><p><strong>рксавгагкгаин</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Автоматический контроль усиления (АГК) на стороне сервера-посредника.</p></td>
</tr>
<tr class="odd">
<td><p><strong>инитиалсигналлевелрмс</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td><p> </p></td>
<td><p>Среднее значение среднего квадрата для входящего сигнала, которое составляет до первых 30 секунд звонка.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Уровень сигнала, полученный на канале 1.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Уровень сигнала, полученный на канале 2.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Уровень шума, полученный на канале 1.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Уровень шума, полученный на канале 2.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Уровень сигнала, отправленный на канале 1.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Уровень сигнала, отправленный на канале 2.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Уровень шума, отправленный на канале 1.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Уровень шума, отправленный на канале 2.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

