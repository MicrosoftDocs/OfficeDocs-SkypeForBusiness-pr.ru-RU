---
title: 'Lync Server 2013: список таблиц качества взаимодействия'
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
ms.openlocfilehash: c3161415b65c8e85ace7968ab29d86c0d0c5387a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a>Список таблиц качества взаимодействия в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-02_

Схема базы данных состоит из следующих таблиц.

**Вспомогательные таблицы**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Таблица</strong></th>
<th><strong>Описание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Таблица Аппшарингметрикссрешолд в Lync Server 2013</a></p></td>
<td><p>Хранение оптимальных и приемлемых значений для показателей качества взаимодействия, используемых совместно с приложением.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">Таблица Кодекдескриптион в Lync Server 2013</a></p></td>
<td><p>Сопоставляет уникальные идентификаторы кодека с соответствующими кодеками.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">Таблица IP-адреса в Lync Server 2013</a></p></td>
<td><p>Сопоставляет IP-адреса с уникальными идентификаторами IP-адресов, которые используются в базе данных качества обслуживания.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">Таблица Нетворкконнектиондетаил в Lync Server 2013</a></p></td>
<td><p>Сопоставляет типы сетевых подключений с идентификаторами сетевых подключений, используемыми в базе данных качества обслуживания.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">Пуржесеттингс Table (QoE) в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о том, что (и когда) устаревшие записи качества обслуживания будут автоматически удалены из базы данных QoE.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">Таблица использованием Traceroute в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о маршрутизации для звонков.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">Усеражентдеф Table (QoE) в Lync Server 2013</a></p></td>
<td><p>Сопоставляет идентификаторы агента пользователя с описательными именами агента.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">Таблица Видеометрикссрешолд в Lync Server 2013</a></p></td>
<td><p>Хранение оптимальных и приемлемых значений для показателей качества взаимодействия, используемых с видеозвонками.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a></p></td>
<td><p>В сеансах голосовой и видеосвязи для протоколов SIP (UA) User Agent (агент запуска сеанса) хранятся строки и типы UA.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">Таблица User в Lync Server 2013</a></p></td>
<td><p>Хранит URI пользователей, конференций и телефонных номеров, используемых в сеансах голосовой связи и видео.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Таблица Endpoint в Lync Server 2013</a></p></td>
<td><p>Хранит полные доменные имена конечных точек, участвующих в звуковых и видеосеансах.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Таблица Pool в Lync Server 2013</a></p></td>
<td><p>Хранит имена пулов, которым принадлежат данные метрик.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Таблица Device в Lync Server 2013</a></p></td>
<td><p>Хранит устройства захвата и устройства рендеринга, используемые в голосовых и видеозвонках.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">Таблица DeviceDriver в Lync Server 2013</a></p></td>
<td><p>Хранит драйвер устройства захвата и устройство рендеринга, которое используется в голосовых и видеозвонках.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Таблица Conference в Lync Server 2013</a></p></td>
<td><p>Хранит коды URI конференций для сценариев конференции или Диалогид для других сценариев.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">Таблица SessionCorrelation в Lync Server 2013</a></p></td>
<td><p>Содержит сведения о корреляции для КОММУТИРУЕМых звонков.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">Таблица PayloadDescription в Lync Server 2013</a></p></td>
<td><p>Хранит кодек, используемый в голосовых и видеозвонках.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">Таблица AppliedBandwidthSource в Lync Server 2013</a></p></td>
<td><p>Сохранение источника пропускной способности, используемой в голосовых и видеозвонках.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">Таблица MacAddress в Lync Server 2013</a></p></td>
<td><p>Хранит MAC-адрес конечных точек, участвующих в сеансах аудио и видео.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Таблица Dialog в Lync Server 2013</a></p></td>
<td><p>Хранит идентификатор диалога для звуковых и видеосеансов.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Таблица Region в Lync Server 2013</a></p></td>
<td><p>Хранит сетевой регион, определенный в параметрах NC.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">Таблица UserSite в Lync Server 2013</a></p></td>
<td><p>Сохранение сетевого сайта, определенного в параметрах NC.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-subnet-table.md">Таблица Subnet в Lync Server 2013</a></p></td>
<td><p>Хранит подсеть, определенную в параметрах NC.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">Таблица MonitoredRegionLink в Lync Server 2013</a></p></td>
<td><p>Хранит ссылку на регион, определенную в параметрах NC.</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">Таблица MonitoredUserSiteLink</a></p></td>
<td><p>Хранит ссылки на сайты сети, определенные в параметрах NC.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">Таблица EndpointSubnet в Lync Server 2013</a></p></td>
<td><p>Хранит подсеть конечной точки, участвующей в звуковых и видеосеансах.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Таблица Server в Lync Server 2013</a></p></td>
<td><p>Хранит полное доменное имя или IP-адрес сервера, через который восходит носитель.</p></td>
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
<th><strong>Таблица</strong></th>
<th><strong>Описание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingstream-table.md">Таблица Аппшарингстреам в Lync Server 2013</a></p></td>
<td><p>Хранение метрик качества для сетевых потоков, используемых для совместного использования приложений. Показатели качества взаимодействия для сетевых потоков, используемых для совместного использования приложений.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Таблица Session в Lync Server 2013</a></p></td>
<td><p>Хранит общие сведения о звуковых и видеофайлах, а также о звуковых и видеосеансах. Сеанс определяется как звуковое или видеодиалоговое окно SIP между двумя конечными точками.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о каждой строке мультимедиа в сеансе. Линия мультимедиа — это коллекция из одного или нескольких звуковых и видеопотоков. Обычно в одной линии есть два потока: аудио-или видеофайлы.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">Таблица AudioStream в Lync Server 2013</a></p></td>
<td><p>Хранит метрики качества звукового файла в линии мультимедиа для каждого звукового потока.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">Таблица AudioSignal в Lync Server 2013</a></p></td>
<td><p>Сохраняет метрики качества звукового файла в линии мультимедиа. Это включает в себя метрики для подавления эха (AEC) и автоматических показателей контроля усиления (АГК).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">Таблица VideoStream в Lync Server 2013</a></p></td>
<td><p>Хранит метрики качества видео для каждого звукового потока в строке мультимедиа.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">Таблица AudioClientEvent в Lync Server 2013</a></p></td>
<td><p>Сохраняет показатели качества звуковых файлов мультимедиа, полученные из клиентского события.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">Таблица VideoClientEvent в Lync Server 2013</a></p></td>
<td><p>Хранит метрики качества видео, собранные из клиентского события.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Таблица Диагностикдата</strong></p></td>
<td><p>Хранит диагностические данные, предназначенные только для внутреннего использования.</p></td>
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
<th><strong>Таблица</strong></th>
<th><strong>Описание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Таблица Серверсуммари</strong></p></td>
<td><p>Хранит сводные данные для серверов, эти данные используются только для отчетов о качестве опыта (QoE).</p></td>
</tr>
<tr class="even">
<td><p><strong>Таблица Усерсуммари</strong></p></td>
<td><p>Хранит сводные данные для пользователей, эти данные используются только для отчетов QoE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Таблица Каллтипесуммари</strong></p></td>
<td><p>Хранить сводные данные для типов звонков эти данные используются только для отчетов QoE.</p></td>
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
<th><strong>Таблица</strong></th>
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
<td><p><strong>Интерфейсная таблица</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>Таблица задач</strong></p></td>
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
<td><p><strong>Часовых поясов</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Таблица Каллсуммари</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>Таблица Девицекаллсумари</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Таблица "клиент"</strong></p></td>
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

