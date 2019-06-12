---
title: 'Lync Server 2013: таблица VideoStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98e0ad3f7c18032dd903d2f8d1d41428ccc12cf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a>Таблица VideoStream в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-12-13_

Каждая запись представляет один поток видео. Одна линия видеофайла обычно состоит из двух видеопотоков.


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
<td><p>На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Сессионсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>R, на который ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Медиалинелабел</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Стреамид</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный идентификатор в строке мультимедиа.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Видеопайлоаддескриптион</strong></p></td>
<td><p>smallint</p></td>
<td><p>Внешний, основной</p></td>
<td><p>Описание полезных данных. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-payloaddescription-table.md">таблицей пайлоаддескриптион в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Средняя колебание сети из статистики протокола управления временем в реальном времени (РТКП).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Життеринтерарривалмакс</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Максимальная колебание сети во время видеосеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Время кругового приема из статистики РТКП.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Раундтрипмакс</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Максимальное время кругового сеанса для видеопотока.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>десятичное число (5; 4)</p></td>
<td><p> </p></td>
<td><p>Средняя скорость потерь пакетов во время звонка.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Паккетлоссратемакс</strong></p></td>
<td><p>десятичное число (5; 4)</p></td>
<td><p> </p></td>
<td><p>Максимальное количество потерь пакетов, замеченное во время звонка.</p></td>
</tr>
<tr class="even">
<td><p><strong>Паккетутилизатион</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Число пакетов для видеопотока (транспортный протокол в реальном времени).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Самый пропускная способность</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Оценка пропускной способности для видеопотока.</p></td>
</tr>
<tr class="even">
<td><p><strong>Видеоресолутион</strong></p></td>
<td><p>char (9)</p></td>
<td><p> </p></td>
<td><p>Разрешение видео в пикселях, умноженное на высоту в пикселях. Отображается в виде строки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Видеобитратеавг</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Средняя скорость потока видео.</p></td>
</tr>
<tr class="even">
<td><p><strong>Инбаундвидеофрамератеавг</strong></p></td>
<td><p>десятичное число (9; 4)</p></td>
<td><p> </p></td>
<td><p>Полученная частота кадров видео.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Аутбаундвидеофрамератеавг</strong></p></td>
<td><p>десятичное число (9; 4)</p></td>
<td><p> </p></td>
<td><p>Частота отправки кадров видео.</p></td>
</tr>
<tr class="even">
<td><p><strong>Видеобитратемакс</strong></p></td>
<td><p>целое</p></td>
<td><p> </p></td>
<td><p>Максимальная скорость видеосигнала во время видеосеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Видеофрамелоссрате</strong></p></td>
<td><p>десятичное число (9; 4)</p></td>
<td><p> </p></td>
<td><p>Процент от общего числа потерянных кадров видео.</p></td>
</tr>
<tr class="even">
<td><p><strong>Видеофек</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>Недоступно.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLossPercentageAvg</strong></p></td>
<td><p>десятичное число (9; 4)</p></td>
<td></td>
<td><p>Процент от общего числа потерянных кадров видео.</p></td>
</tr>
<tr class="even">
<td><p><strong>Цифкуалитиратио</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Процент звонка, находился в разрешении общего формата обмена (циф).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Вгакуалитиратио</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Процент звонка, находился в режиме разрешающей способности VGA.</p></td>
</tr>
<tr class="even">
<td><p><strong>HD720QualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Процентное соотношение вызова, которое было установлено по адресу HD720.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Нонедропратио</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Процент продолжительности звонка без удаления кадров.</p></td>
</tr>
<tr class="even">
<td><p><strong>Бдропратио</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Процент продолжительности звонка с помощью функции B Frame Drop.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Бпдропратио</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Процент продолжительности звонка с помощью перетаскивания рамки BP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Бпспдропратио</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Процент продолжительности звонка с помощью БПСП Frame Drop.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Бпспидропратио</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Процент продолжительности звонка с помощью БПСПИ Frame Drop.</p></td>
</tr>
<tr class="even">
<td><p><strong>443</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>Получение потоковых данных на стороне получателя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Исходящее</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>Получение данных потока на стороне отправителя.</p></td>
</tr>
<tr class="even">
<td><p><strong>Сендерискаллерпаи</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>1 — направление потока для вызываемого абонента.</p>
<p>0 — направление потока из вызываемого объекта вызывающему абоненту.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Лоссконжестионперцент</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Указывает процент времени, в течение которого Звонок находился в состоянии перегрузки с потерей.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Делайконжестионперцент</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Указывает процент вызова, в течение которого перегрузка была вызвана отложенным поступлением сетевых пакетов.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Контентиондетектедперцент</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Указывает процент времени, в течение которого Звонок конкурирует за ресурсы сети.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Бандвидсестмин</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Минимальная сумма оценки пропускной способности, измеряемая во время звонка.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Бандвидсестмакс</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Максимальная степень оценки пропускной способности, измеряемая во время звонка.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Бандвидсестстддев</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Стандартное отклонение оценки пропускной способности, измеряемой во время звонка.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Бандвидсеставже</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Средняя сумма оценки пропускной способности, измеряемая во время звонка.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ловбандвидсформултивиев</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Процент звонка, когда конечная точка определила, что сетевое подключение не поддерживало функцию просмотра видео.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Релативеоневайтотал</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Общая сумма односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Релативеоневайавераже</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Средняя величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Релативеоневаймакс</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Максимальная сумма односторонняя задержка. Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Релативеоневайбурстоккурренцес</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Общее количество односторонних вхождений. Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. Этот показатель измеряет поток данных между клиентом и сервером.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Релативеоневайбурстденсити</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Общая односторонняя плотность нагрузки. Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. Этот показатель измеряет поток данных между клиентом и сервером.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Релативеоневайбурстдуратион</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Общая продолжительность односторонней длительности. Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. Этот показатель измеряет поток данных между клиентом и сервером.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Релативеоневайгапоккурренцес</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Общее количество односторонних вхождений. Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами. Этот показатель измеряет поток данных между клиентом и сервером.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Релативеоневайгапденсити</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Общая плотность односторонних зазоров. Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами. Этот показатель измеряет поток данных между клиентом и сервером.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Релативеоневайгапдуратион</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Общая продолжительность односторонних промежутков. Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами. Этот показатель измеряет поток данных между клиентом и сервером.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Видеопаккетлоссрате</strong></p></td>
<td><p>десятичное число (9; 4)</p></td>
<td></td>
<td><p>Частота потери видеопакетов.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Видеоаллокатебвавг</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Средний объем пропускной способности, выделенной для видео.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Сендкодектипес</strong></p></td>
<td><p>smallint</p></td>
<td><p>Другом</p></td>
<td><p>Тип видеокодеков, используемых отправителем. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-codecdescription-table.md">таблицей кодекдескриптион в Lync Server 2013</a> .</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Сендресолутионвидс</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Ширина разрешения, используемая отправителем.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Сендресолутионхеигхт</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Высота разрешения, используемая отправителем.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Сендфрамератеавераже</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Средняя скорость кадров видео, используемая отправителем.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Сендбитратемаксимум</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Максимальная скорость для отправителя.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Сендбитратеавераже</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Средняя скорость в битах для отправителя.</p></td>
</tr>
<tr class="even">
<td><p><strong>Сендвидеостреамсмакс</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Максимальное количество видеопотоков, используемых отправителем.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Реквкодектипес</strong></p></td>
<td><p>smallint</p></td>
<td><p>Другом</p></td>
<td><p>Видео коды, используемые получателем. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-codecdescription-table.md">таблицей кодекдескриптион в Lync Server 2013</a> .</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Реквресолутионвидс</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Ширина разрешения, используемая получателем.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Реквресолутионхеигхт</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Высота разрешения, используемая получателем.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverage</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Средняя частота кадров видео, используемая получателем.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Реквбитратемаксимум</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Максимальная скорость потока для получателя.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Реквбитратеавераже</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Средняя скорость потока для получателя.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Рекввидеостреамсмакс</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Максимальное количество видеопотоков для получателя.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Рекввидеостреамсмин</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Минимальный поток видеозаписи для получателя.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Рекввидеостреамсмоде</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Режим видео (например, коллекция или один поток) получателя.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLR</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Применена ставка потери пакетов после исправления ошибки переадресации.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Динамиккапабилитиперцент</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Процент времени, в течение которого был активен флаг динамической доступности.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ресолутионмин</strong></p></td>
<td><p>char (9)</p></td>
<td></td>
<td><p>Минимальное разрешение, измеряемое во время звонка.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ловбитратекаллперцент</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Процент звонка ниже минимального порогового значения скорости (70 килобит в секунду).</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercent</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Процент звонка ниже нижнего порогового значения частоты кадров (количество кадров в 7,5 в секунду, входящее).</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercent</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Процент звонка, который выполнялся по низким разрешению.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Дуратионсекондс</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Продолжительность звонка в секундах.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Исаггрегатеддата</strong></p></td>
<td><p>бит</p></td>
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

