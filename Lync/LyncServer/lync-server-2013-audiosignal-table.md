---
title: 'Lync Server 2013: таблица таблица audiosignal'
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
ms.openlocfilehash: 2d09842cb8b905798855cef7e015e4d9b32e72dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a>Таблица Таблица audiosignal в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-11-12_

Каждая запись представляет метрики звукового сигнала для одной конечной точки. Обычно каждый вызов состоит из двух записей, один из которых является абонентом, а другой — для вызываемого абонента.


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
<td><p>Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионсек</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>медиалинелабел</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>фромкаллер</strong></p></td>
<td><p>Битовая</p></td>
<td><p>Primary</p></td>
<td><p>0: данные вызываемого абонента</p>
<p>1: данные вызывающего абонента</p></td>
</tr>
<tr class="odd">
<td><p><strong>сендсигналлевел</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Представляет уровень звукового сигнала, поступающего после аналогового усиления контроля. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть не менее 30 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</p></td>
</tr>
<tr class="even">
<td><p><strong>реквсигналлевел</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Обратитесь к разделу Сендсигналлевел.</p></td>
</tr>
<tr class="odd">
<td><p><strong>сендноиселевел</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Представляет уровень шума управления последующей аналоговой усилением. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть менее 35 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</p></td>
</tr>
<tr class="even">
<td><p><strong>реквноиселевел</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Обратитесь к разделу Сендноиселевел.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ечоретурн</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Метрика улучшения возврата эха. Единица измерения для этого показателя — дБ. Чем ниже значение, тем меньше эхосигнал. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</p></td>
</tr>
<tr class="even">
<td><p><strong>аудиоспеакерглитчрате</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Среднее число сбоев для отображения лаудспеакер в пять минут. Для хорошего качества должно быть не более одного сбоя в пять минут. Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</p></td>
</tr>
<tr class="odd">
<td><p><strong>аудиомикглитчрате</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Среднее число сбоев для записи микрофона в течение пяти минут. Для хорошего качества должно быть не более одного сбоя в пять минут. Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</p></td>
</tr>
<tr class="even">
<td><p><strong>аудиотиместампдрифтратемик</strong></p></td>
<td><p>десятичное число (9, 2)</p></td>
<td><p> </p></td>
<td><p>Частота расхождения сигналов для микрофона, относящихся к часам процессора.</p></td>
</tr>
<tr class="odd">
<td><p><strong>аудиотиместампдрифтратеспк</strong></p></td>
<td><p>десятичное число (9, 2)</p></td>
<td><p> </p></td>
<td><p>Частота расхождения сигналов для динамиков, относящихся к часам процессора.</p></td>
</tr>
<tr class="even">
<td><p><strong>аудиотиместамперрормикмс</strong></p></td>
<td><p>десятичное число (9, 2)</p></td>
<td><p> </p></td>
<td><p>Частота расхождения сигналов для динамиков, относящихся к часам процессора.</p>
<p>Средняя ошибка метки времени для потока захвата микрофоном, в миллисекундах, в последние 20 секунд вызова.</p></td>
</tr>
<tr class="odd">
<td><p><strong>аудиотиместамперрорспкмс</strong></p></td>
<td><p>десятичное число (9, 2)</p></td>
<td><p> </p></td>
<td><p>Средняя ошибка метки времени потока отображения динамиков, в миллисекундах, в последние 20 секунд вызова.</p></td>
</tr>
<tr class="even">
<td><p><strong>всентрикаусес</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>Речевой коммутатор — это полудуплексный режим с уменьшенной возможностью прерывания. Причины записи голосового переключателя:</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>Причина может быть сочетанием отдельных причин. В этом случае ENTER_VS_FORCEORCONVERGENCE может быть включен только в RegKey для тестового назначения.</p>
<p>Тип данных для этого столбца был изменен в Microsoft Lync Server 2013.</p></td>
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
<td><p>десятичное число (5, 2)</p></td>
<td><p> </p></td>
<td><p>Процент времени, когда в потоке записи микрофона обнаружено эхо-сообщений. Как правило, низкие значения для гарнитур и телефонов, а также для телефонов динамиков или отдельных динамиков. Для устройств, поддерживающих встроенную отдавление акустического эха, высокие значения указывают на наличие потерь эха. Для других устройств эта метрика не должна использоваться для оценки качества устройства.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ечоперцентсенд</strong></p></td>
<td><p>десятичное число (5, 2)</p></td>
<td></td>
<td><p>Процент времени, в течение которого обнаружено Эхо-сообщения в отправленном потоке. Высокое значение в отправленных потоках указывает на утечку эхосигнала.</p></td>
</tr>
<tr class="even">
<td><p><strong>рксагксигналлевел</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Уровень полученного сигнала на сервере-посреднике от шлюза; Это относится только к серверу-посреднику. Единица измерения — dBoV. Приемлемый диапазон для хорошего качества — от -30 до -18 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p><strong>рксагкноиселевел</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Уровень полученного сигнала на сервере-посреднике от шлюза. Этот показатель относится только к серверу-посреднику. Единица измерения — dBoV. Приемлемый диапазон для хорошего качества — ниже -50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p><strong>рксавгагкгаин</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Автоматический контроль усиления (АУДИОПОТОКУ) на стороне сервера-посредника.</p></td>
</tr>
<tr class="odd">
<td><p><strong>инитиалсигналлевелрмс</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td><p> </p></td>
<td><p>Средняя средняя квадрат (RMS) входящего сигнала до первого 30 секунд вызова.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Уровень сигнала, полученный на канале 1.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Уровень сигнала, полученный на канале 2.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Уровень шума, полученный на канале 1.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Уровень шума, полученного по каналу 2.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Уровень сигнала, отправленный на канале 1.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Уровень сигнала, отправленный по каналу 2.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Уровень шума, отправленный на канале 1.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Уровень шума, отправленный по каналу 2.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

