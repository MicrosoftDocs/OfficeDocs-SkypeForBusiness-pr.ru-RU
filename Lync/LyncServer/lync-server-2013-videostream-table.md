---
title: 'Lync Server 2013: таблица таблица videostream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00abc61fc7ba83b94f3228de91eb9fa6810fc93c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a>Таблица Таблица videostream в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-12-13_

Каждая запись представляет один видеопоток. Одна линия видеопотока обычно содержит два видеопотока.


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
<td><p>R, на который ссылается <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>медиалинелабел</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>стреамид</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный идентификатор в линии мультимедиа.</p></td>
</tr>
<tr class="odd">
<td><p><strong>видеопайлоаддескриптион</strong></p></td>
<td><p>smallint</p></td>
<td><p>Внешний, основной</p></td>
<td><p>Описание полезных данных. Дополнительные сведения см. <a href="lync-server-2013-payloaddescription-table.md">в таблице таблица payloaddescription в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>життеринтерарривал</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Средний уровень дрожания в сети на основе статистики протокола RTCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>життеринтерарривалмакс</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Максимальная колебание сети во время сеанса видеосвязи.</p></td>
</tr>
<tr class="even">
<td><p><strong>Обработки</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Время приема-передачи на основе статистики RTCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>раундтрипмакс</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Максимальное время кругового пути для видеопотока.</p></td>
</tr>
<tr class="even">
<td><p><strong>паккетлоссрате</strong></p></td>
<td><p>десятичное число (5, 4)</p></td>
<td><p> </p></td>
<td><p>Средний коэффициент потерь пакетов в течение вызова.</p></td>
</tr>
<tr class="odd">
<td><p><strong>паккетлоссратемакс</strong></p></td>
<td><p>десятичное число (5, 4)</p></td>
<td><p> </p></td>
<td><p>Максимальная потеря пакетов, наблюдавшаяся в течение вызова.</p></td>
</tr>
<tr class="even">
<td><p><strong>паккетутилизатион</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Количество пакетов для видеопотока (RTP).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Самый полоса пропускания</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Оценка пропускной способности для видеопотока.</p></td>
</tr>
<tr class="even">
<td><p><strong>видеоресолутион</strong></p></td>
<td><p>char (9)</p></td>
<td><p> </p></td>
<td><p>Разрешение видео в пикселах (ширина умножается на высоту в пикселах). Указывается как строка.</p></td>
</tr>
<tr class="odd">
<td><p><strong>видеобитратеавг</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Средняя скорость передачи видеопотока.</p></td>
</tr>
<tr class="even">
<td><p><strong>инбаундвидеофрамератеавг</strong></p></td>
<td><p>десятичное число (9, 4)</p></td>
<td><p> </p></td>
<td><p>Полученная частота видеокадров.</p></td>
</tr>
<tr class="odd">
<td><p><strong>аутбаундвидеофрамератеавг</strong></p></td>
<td><p>десятичное число (9, 4)</p></td>
<td><p> </p></td>
<td><p>Частота отправки видеокадров.</p></td>
</tr>
<tr class="even">
<td><p><strong>видеобитратемакс</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Максимальная скорость видеопотока во время видеосеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>видеофрамелоссрате</strong></p></td>
<td><p>десятичное число (9, 4)</p></td>
<td><p> </p></td>
<td><p>Процент от общего числа потерянных видеокадров.</p></td>
</tr>
<tr class="even">
<td><p><strong>видеофек</strong></p></td>
<td><p>Битовая</p></td>
<td><p> </p></td>
<td><p>Недоступно.</p></td>
</tr>
<tr class="odd">
<td><p><strong>видеолокалфрамелоссперцентажеавг</strong></p></td>
<td><p>десятичное число (9, 4)</p></td>
<td></td>
<td><p>Процент от общего числа потерянных видеокадров.</p></td>
</tr>
<tr class="even">
<td><p><strong>Цифкуалитиратио</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Процентное соотношение вызова, находилось в стандартном разрешении формата обмена данными (CIF).</p></td>
</tr>
<tr class="odd">
<td><p><strong>вгакуалитиратио</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Процентное соотношение вызовов, находилось при разрешении VGA.</p></td>
</tr>
<tr class="even">
<td><p><strong>HD720QualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Процентное соотношение вызова, находилось по разрешению HD720.</p></td>
</tr>
<tr class="odd">
<td><p><strong>нонедропратио</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Процент времени вызова без перетаскивания кадров.</p></td>
</tr>
<tr class="even">
<td><p><strong>бдропратио</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Процент времени вызова с помощью параметра B Frame Drop.</p></td>
</tr>
<tr class="odd">
<td><p><strong>бпдропратио</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Процент времени вызова с удалением кадра BP.</p></td>
</tr>
<tr class="even">
<td><p><strong>бпспдропратио</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Процент времени вызова с БПСП Frame Drop.</p></td>
</tr>
<tr class="odd">
<td><p><strong>бпспидропратио</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Процент времени вызова с БПСПИ Frame Drop.</p></td>
</tr>
<tr class="even">
<td><p><strong>Получение</strong></p></td>
<td><p>Битовая</p></td>
<td><p> </p></td>
<td><p>Получение потоковых данных на стороне получателя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Прав</strong></p></td>
<td><p>Битовая</p></td>
<td><p> </p></td>
<td><p>Получение потоковых данных на стороне отправителя.</p></td>
</tr>
<tr class="even">
<td><p><strong>сендерискаллерпаи</strong></p></td>
<td><p>Битовая</p></td>
<td><p> </p></td>
<td><p>1 означает направление потока от вызывающего абонента вызываемому абоненту.</p>
<p>0 означает направление потока от вызываемого абонента вызывающему абоненту.</p></td>
</tr>
<tr class="odd">
<td><p><strong>лоссконжестионперцент</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Указывает процент времени, в течение которого вызов находился в состоянии перегрузки потерь.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>делайконжестионперцент</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Указывает процент вызова, в течение которого перегрузка была вызвана задержкой появления сетевых пакетов.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>контентиондетектедперцент</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Указывает процент времени, в течение которого вызов конкурирует за ресурсы сети.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>бандвидсестмин</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Минимальная сумма оценки пропускной способности, измеренной во время вызова.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>бандвидсестмакс</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Максимальный объем оценки пропускной способности, измеренной во время вызова.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>бандвидсестстддев</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Стандартное отклонение оценки пропускной способности, измеренной во время вызова.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>бандвидсеставже</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Средняя величина оценки пропускной способности, измеренной во время вызова.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ловбандвидсформултивиев</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Процент вызова, в котором конечная точка определила, что сетевое подключение не поддерживает просмотр видео.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>релативеоневайтотал</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Общая величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>релативеоневайавераже</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Средняя величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>релативеоневаймакс</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Максимальная величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>релативеоневайбурстоккурренцес</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Общее число повторов пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>релативеоневайбурстденсити</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Общая плотность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>релативеоневайбурстдуратион</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Общая длительность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>релативеоневайгапоккурренцес</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Общее число повторов разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>релативеоневайгапденсити</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Общая плотность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>релативеоневайгапдуратион</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Общая длительность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>видеопаккетлоссрате</strong></p></td>
<td><p>десятичное число (9, 4)</p></td>
<td></td>
<td><p>Скорость потери видеопакетов.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>видеоаллокатебвавг</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Средний объем выделенной полосы пропускания для видео.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>сендкодектипес</strong></p></td>
<td><p>smallint</p></td>
<td><p>Правительства</p></td>
<td><p>Тип видеокодеков, используемых отправителем. Дополнительные сведения см. <a href="lync-server-2013-codecdescription-table.md">в таблице кодекдескриптион в Lync Server 2013</a> .</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>сендресолутионвидс</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ширина разрешения, используемая отправителем.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>сендресолутионхеигхт</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Высота разрешения, используемая отправителем.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>сендфрамератеавераже</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Средняя скорость передачи видеокадров, используемая отправителем.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>сендбитратемаксимум</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Максимальная скорость передачи для отправителя.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>сендбитратеавераже</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Средняя скорость потока для отправителя.</p></td>
</tr>
<tr class="even">
<td><p><strong>сендвидеостреамсмакс</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Максимальное число видеопотоков, используемых отправителем.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>реквкодектипес</strong></p></td>
<td><p>smallint</p></td>
<td><p>Правительства</p></td>
<td><p>Видеокоды, используемые получателем. Дополнительные сведения см. <a href="lync-server-2013-codecdescription-table.md">в таблице кодекдескриптион в Lync Server 2013</a> .</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>реквресолутионвидс</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ширина разрешения, используемая получателем.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>реквресолутионхеигхт</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Высота разрешения, используемая получателем.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>реквфрамератеавераже</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Средняя частота видеокадров, используемая получателем.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>реквбитратемаксимум</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Максимальная скорость потока для получателя.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>реквбитратеавераже</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Средняя скорость потока для получателя.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>рекввидеостреамсмакс</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Максимальное число видеопотоков для приемника.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>рекввидеостреамсмин</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Минимальное количество видеопотоков для приемника.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>рекввидеостреамсмоде</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Видеорежим (например, коллекция или один поток) для приемника.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>видеопостфекплр</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Скорость потери пакетов после применения коррекции ошибок переадресации.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>динамиккапабилитиперцент</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Процент времени, в течение которого был активен флаг динамической возможности.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ресолутионмин</strong></p></td>
<td><p>char (9)</p></td>
<td></td>
<td><p>Минимальное разрешение, измеренное во время вызова.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ловбитратекаллперцент</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Процент вызова ниже минимального порогового значения скорости (70 килобит в секунду).</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ловфрамератекаллперцент</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Процент вызовов ниже минимального порога частоты кадров (7,5 кадров в секунду, входящий трафик).</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ловресолутионкаллперцент</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Процент звонков, произошедших с наименьшим разрешением.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>дуратионсекондс</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Продолжительность звонка в секундах.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>исаггрегатеддата</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Указывает, были ли данные объединены из нескольких вызовов.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

