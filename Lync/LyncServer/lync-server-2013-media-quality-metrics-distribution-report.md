﻿---
title: Отчет по распределению метрик качества среды
TOCTitle: Отчет по распределению метрик качества среды
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205262(v=OCS.15)
ms:contentKeyID: 49311234
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Отчет по распределению метрик качества среды

 

_**Дата изменения раздела:** 2015-03-09_

Отчет по распределению метрик качества среды позволяет просматривать диаграмму, на которой отображаются значения распространения для метрик качества работы, такие как дрожание и потеря пакетов. Предположим, пользователи сделали 10 звонков; ниже приведен отчет по этим 10 звонкам со следующими значениями времени цикла:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Номер звонка</th>
<th>Время цикла (мс)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>4550</p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>50</p></td>
</tr>
</tbody>
</table>


Среднее время цикла составляет 500 мс (5000, разделенные на 10). 500 мс — это очень большое время цикла; соответственно, это может говорить о значительных проблемах, связанных с перегрузкой сети (продолжительное время цикла, как правило, свидетельствует о перегруженных сетях).

В реальной ситуации, вероятнее всего, 90 % вызовов будут иметь оптимальное значение времени цикла, тогда как один неудачный вызов сведет на нет все результаты. Если ориентироваться только на среднее время цикла, можно прийти к неверному заключению.

Отчет о распределении метрик качества среды позволяет избежать неправильных выводов, представляя визуализацию распределения определенных метрик (таких как время цикла). Эти диаграммы четко показывают, что девять вызовов были нормальными, а один — очень плохим. Очевидно, что может потребоваться дальнейшее выяснение причин сбоя этого вызова. Однако сама возможность узнать, что 9 из 10 вызовов были беспроблемными, позволяет избежать внесения существенных изменений в сеть (по крайней мере на данном этапе).

## Фильтры

Фильтры позволяют получать более точные и актуальные наборы данных или просматривать возвращаемые данные в разных комбинациях. В следующей таблице перечислены фильтры, которые можно использовать в отчете по распределению метрик качества среды.

### Фильтры отчета по распределению метрик качества среды

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
<td><p><strong>От</strong></p></td>
<td><p>Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</p>
<p>7/7/2012 13:00.</p>
<p>Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</p>
<p>7/7/2012</p>
<p>Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</p>
<p>7/3/2012</p>
<p>Неделя всегда начинается с воскресенья и заканчивается субботой.</p></td>
</tr>
<tr class="even">
<td><p><strong>До</strong></p></td>
<td><p>Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</p>
<p>7/7/2012 13:00.</p>
<p>Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</p>
<p>7/7/2012</p>
<p>Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</p>
<p>7/3/2012</p>
<p>Неделя всегда начинается с воскресения и заканчивается субботой.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Minimum in x axis</strong> (Минимальное значение на оси x)</p></td>
<td><p>Минимальное значение будет отображаться на оси X диаграммы.</p></td>
</tr>
<tr class="even">
<td><p><strong>Maximum in x axis</strong> (Максимальное значение на оси x)</p></td>
<td><p>Максимальное значение будет отображаться на оси X диаграммы.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Тип доступа</strong></p></td>
<td><p>Указывает, вошел ли клиент из внутренней или внешней сети при выполнении звонка. Выберите одно из значений:</p>
<ul>
<li><p>[Все]</p></li>
<li><p>Внутренние</p></li>
<li><p>Внешние</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Указывает, использовал ли внешний клиент VPN-подключение при выполнении звонка. Выберите одно из значений:</p>
<ul>
<li><p>[Все]</p></li>
<li><p>VPN</p></li>
<li><p>Не VPN</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Тип сети</strong></p></td>
<td><p>Указание типа сети, к которой был подключен клиент при выполнении вызова. Выберите одно из значений:</p>
<ul>
<li><p>[Все]</p></li>
<li><p>Проводная</p></li>
<li><p>Беспроводная</p></li>
</ul></td>
</tr>
</tbody>
</table>

