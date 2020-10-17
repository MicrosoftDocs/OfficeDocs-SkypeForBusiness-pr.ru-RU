---
title: 'Lync Server 2013: список таблиц QoE'
description: 'Lync Server 2013: список таблиц QoE.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 871babf246f616d306a03f84f9134605dd595999
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550045"
---
# <a name="list-of-qoe-tables-in-lync-server-2013"></a>Список таблиц QoE в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

Схема базы данных состоит из следующих таблиц.

**Вспомогательные таблицы**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Table</strong></th>
<th><strong>Описание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Таблица Аппшарингметрикссрешолд в Lync Server 2013</a></p></td>
<td><p>Сохранение оптимальных и приемлемых значений для показателей качества взаимодействия, используемых совместно с общим доступом к приложениям.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">Таблица Кодекдескриптион в Lync Server 2013</a></p></td>
<td><p>Сопоставляет уникальные идентификаторы кодека с соответствующим кодеком.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">IP-адрес таблицы в Lync Server 2013</a></p></td>
<td><p>Сопоставляет IP-адреса с уникальными идентификаторами IP-адресов, используемыми в других местах базы данных качества взаимодействия.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">Таблица Нетворкконнектиондетаил в Lync Server 2013</a></p></td>
<td><p>Сопоставляет типы сетевых подключений с идентификаторами сетевых подключений, используемыми в других местах базы данных качества взаимодействия.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">Таблица Таблица purgesettings (QoE) в Lync Server 2013</a></p></td>
<td><p>Хранит сведения, указывающие, будут ли (и когда) устаревшие записи качества взаимодействия автоматически удаляться из базы данных QoE.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">Таблица Трацерауте в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о маршрутизации для вызовов.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">Таблица Таблица useragentdef (QoE) в Lync Server 2013</a></p></td>
<td><p>Привязка идентификаторов агента пользователя к описательным именам агента.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">Таблица Таблица videometricsthreshold в Lync Server 2013</a></p></td>
<td><p>Сохранение оптимальных и приемлемых значений для показателей качества взаимодействия, используемых с видеовызовами.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a></p></td>
<td><p>Сохраняет строки и типы агентов пользователя для протокола SIP (UA), используемые в сеансах аудио и видео.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">Таблица user в Lync Server 2013</a></p></td>
<td><p>Хранение URI пользователей, конференций и телефонов, используемых в сеансах аудио и видео.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Таблица конечной точки в Lync Server 2013</a></p></td>
<td><p>Хранит полные доменные имена конечных точек, участвующих в сеансах аудио и видео.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Таблица pool в Lync Server 2013</a></p></td>
<td><p>Хранит имена пулов, к которым относятся данные метрики.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Таблица Devices в Lync Server 2013</a></p></td>
<td><p>Сохраняет устройства захвата и устройства отображения, которые используются в аудио-и видеовызовах.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">Таблица Таблица devicedriver в Lync Server 2013</a></p></td>
<td><p>Хранит драйвер устройства захвата и устройство отображения, которые используются в аудио-и видеовызовах.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Таблица конференций в Lync Server 2013</a></p></td>
<td><p>Хранит коды URI конференций для сценариев конференц-связи или DialogID для других сценариев.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">Таблица Таблица sessioncorrelation в Lync Server 2013</a></p></td>
<td><p>Хранит CorrelationID для звонков по PSTN.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">Таблица Таблица payloaddescription в Lync Server 2013</a></p></td>
<td><p>Сохраняет кодек, используемый в аудио-и видеовызовах.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">Таблица Таблица appliedbandwidthsource в Lync Server 2013</a></p></td>
<td><p>Хранит источник пропускной способности, используемый в аудио-и видеовызовах.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">Таблица MacAddress в Lync Server 2013</a></p></td>
<td><p>Хранит MAC-адрес конечных точек, участвующих в сеансах аудио и видео.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Таблица диалогов в Lync Server 2013</a></p></td>
<td><p>Сохраняет идентификатор диалога для сеансов аудио и видео.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Таблица Region в Lync Server 2013</a></p></td>
<td><p>Хранит область сети, определенную в параметре NC.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">Таблица Таблица usersite в Lync Server 2013</a></p></td>
<td><p>Сохранение сетевого сайта, определенного в параметре NC.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-subnet-table.md">Таблица Subnet в Lync Server 2013</a></p></td>
<td><p>Сохраняет подсеть, определенную в параметре NC.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">Таблица Таблица monitoredregionlink в Lync Server 2013</a></p></td>
<td><p>Хранит ссылку региона, определенную в параметре NC.</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">Таблица Таблица monitoredusersitelink</a></p></td>
<td><p>Сохраняет сетевые связи сайтов, определенные в параметре NC.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">Таблица Таблица endpointsubnet в Lync Server 2013</a></p></td>
<td><p>Хранит подсеть конечной точки, участвующей в сеансе аудио и видео.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Таблица Server в Lync Server 2013</a></p></td>
<td><p>Хранит полное доменное имя или IP-адрес сервера, через который проходит носитель.</p></td>
</tr>
</tbody>
</table>


**Таблицы для данных метрик**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Table</strong></th>
<th><strong>Описание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingstream-table.md">Таблица Аппшарингстреам в Lync Server 2013</a></p></td>
<td><p>Сохранение метрик качества взаимодействия для сетевых потоков, используемых для общего доступа к приложениям. Метрики качества взаимодействия для сетевых потоков, используемых для общего доступа к приложениям.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Таблица Sessions в Lync Server 2013</a></p></td>
<td><p>Хранит общие сведения о звуковом или аудио-или видеосеансе. Сеанс определяется как диалоговое окно аудио-или видеоsip между двумя конечными точками.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о каждой строке мультимедиа в сеансе. Линия мультимедиа — это коллекция из одного или нескольких аудио-и видеопотоков. Как правило, одна линия мультимедиа будет иметь два потока: аудио или видео.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">Таблица Таблица audiostream в Lync Server 2013</a></p></td>
<td><p>Сохраняет метрики качества звукового сопровождения для каждого звукового потока в линии мультимедиа.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">Таблица Таблица audiosignal в Lync Server 2013</a></p></td>
<td><p>Сохраняет метрики качества звукового устройства в линии мультимедиа. Это включает в себя метрики подавления эха и автоматические контрольные метрики (АУДИОПОТОКУ).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">Таблица Таблица videostream в Lync Server 2013</a></p></td>
<td><p>Хранит метрики качества мультимедиа для каждого звукового потока в линии мультимедиа.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">Таблица Таблица audioclientevent в Lync Server 2013</a></p></td>
<td><p>Хранит метрики качества аудио мультимедиа, собранные из клиентского события.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">Таблица Таблица videoclientevent в Lync Server 2013</a></p></td>
<td><p>Сохранение метрик качества мультимедиа, собранных из клиентского события.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Таблица Диагностикдата</strong></p></td>
<td><p>Хранение диагностических данных, предназначенных только для внутреннего использования.</p></td>
</tr>
</tbody>
</table>


**Таблицы для сводных данных**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Table</strong></th>
<th><strong>Описание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Таблица Серверсуммари</strong></p></td>
<td><p>Хранит сводные данные для серверов, эти данные используются только для отчетов о качестве взаимодействия (QoE).</p></td>
</tr>
<tr class="even">
<td><p><strong>Таблица Усерсуммари</strong></p></td>
<td><p>Хранит сводные данные для пользователей, эти данные используются только для отчетов QoE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Таблица Каллтипесуммари</strong></p></td>
<td><p>Хранение сводных данных для типов вызовов эти данные используются только для отчетов QoE.</p></td>
</tr>
</tbody>
</table>


**Таблицы для внутреннего использования сервером мониторинга**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Table</strong></th>
<th><strong>Описание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>дбконфигдатетиме</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>дбконфигинт</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd Table</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>Task Table</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>суммаритаблеконфигуратион</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>дберрормессаже</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>метрикссрешолд</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>дайлигхтсавингеарс</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>тимезонеконфигуратион</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZones</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Таблица CallSummary</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>Таблица Девицекаллсумари</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Таблица Tenant</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>видеокаллсуммаритабле</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>аскаллсуммаритабле</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

