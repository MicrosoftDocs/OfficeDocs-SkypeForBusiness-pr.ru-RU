---
title: 'Lync Server 2013: размещение данных и файлов журналов SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfae4aef6e6f5ec0a33fe64d42ea7bfd093badee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Размещение данных и файлов журналов SQL Server для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

При планировании и развертывании Microsoft SQL Server 2012 или Microsoft SQL Server 2008 R2 с пакетом обновления 1 (SP1) для пула переднего плана Lync Server 2013, важно учесть, что размещение файлов данных и журналов на физических жестких дисках для повышения производительности. Рекомендуемая конфигурация диска — реализация набора RAID 1 + 0 с использованием 6 шпинделей. Размещение всех файлов базы данных и журналов, используемых интерфейсным пулом и связанными ролями и службами серверов (то есть сервера архивации и мониторинга, службы группы ответа Lync Server, службы приостановки вызовов Lync Server) на набор дисков RAID с помощью Lync Server Мастер развертывания приведет к тому, что конфигурация была протестирована на хорошую производительность. В следующей таблице подробно описываются файлы базы данных и их назначение.

<div>


> [!NOTE]  
> Если для политик и конфигураций SQL Server требуется более специализированная установка, файлы базы данных и журналов можно установить в любое заданное расположение с помощью командной консоли Lync Server. Более подробную информацию можно узнать <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">в статье Установка базы данных с помощью командной консоли Lync Server в Lync server 2013</A> .



</div>

### <a name="data-and-log-files-for-central-management-store"></a>Файлы данных и журналов для центрального хранилища управления

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Файлы баз данных центрального хранилища управления</th>
<th>Назначение файла данных или журнала</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XDS. ldf</p></td>
<td><p>Файл журнала транзакций для центрального хранилища управления</p></td>
</tr>
<tr class="even">
<td><p>XDS. mdf</p></td>
<td><p>Поддерживает конфигурацию текущей топологии Lync Server 2013, определенную и опубликованную построителем топологий</p></td>
</tr>
<tr class="odd">
<td><p>LIS. mdf</p></td>
<td><p>Файл данных службы сведений о расположении</p></td>
</tr>
<tr class="even">
<td><p>LIS. ldf</p></td>
<td><p>Журнал транзакций для файла данных службы сведений о расположении</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>Файлы данных и журналов для пользователей, конференц-связи и адресной книги

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Основные файлы базы данных Lync Server 2013</th>
<th>Назначение файла данных или журнала</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTC. mdf</p></td>
<td><p>Постоянные данные пользователя (например, списки управления доступом (ACL), контакты, запланированные конференции)</p></td>
</tr>
<tr class="even">
<td><p>RTC. ldf</p></td>
<td><p>Журнал транзакций для данных RTC</p></td>
</tr>
<tr class="odd">
<td><p>Журнал RTCDyn. mdf</p></td>
<td><p>Поддерживает временные данные пользователя (данные среды выполнения присутствия)</p></td>
</tr>
<tr class="even">
<td><p>Журнал RTCDyn. ldf</p></td>
<td><p>Журнал транзакций для данных журнал RTCDyn</p></td>
</tr>
<tr class="odd">
<td><p>Rtcab. mdf</p></td>
<td><p>База данных адресной книги для связи в режиме реального времени (RTC) — это репозиторий SQL Server, в котором хранятся данные службы адресной книги.</p></td>
</tr>
<tr class="even">
<td><p>Rtcab. ldf</p></td>
<td><p>Журнал транзакций для службы адресной книги</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal. mdb</p></td>
<td><p>Размещение каталога конференций</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds. mdf</p></td>
<td><p>Поддерживает резервное копирование данных пользователя</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds. ldf</p></td>
<td><p>Журнал транзакций для данных Rtcxds</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>Файлы данных и журналов для Парковки вызовов и группы ответа

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>База данных приложения</th>
<th>Назначение файла данных или журнала</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Кпсдин. mdf</p></td>
<td><p>Динамическая информационная база данных для приложения парковки вызовов</p></td>
</tr>
<tr class="even">
<td><p>Кпсдин. ldf</p></td>
<td><p>Журнал транзакций для файла данных приложения парковки вызовов</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig. mdf</p></td>
<td><p>Файл данных службы группы ответа Lync Server для настройки служб</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig. ldf</p></td>
<td><p>Файл журнала транзакций для конфигурации приложения группы ответа</p></td>
</tr>
<tr class="odd">
<td><p>Ргсдин. mdf</p></td>
<td><p>Файл данных службы группы ответа для выполняемых операций</p></td>
</tr>
<tr class="even">
<td><p>Ргсдин. ldf</p></td>
<td><p>Журнал транзакций для файла данных времени выполнения, связанных со службой группы ответа</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>Файлы данных и журналов для сервера архивации и мониторинга

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Файлы базы данных архивации и мониторинга</th>
<th>Назначение файла данных или журнала</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr. mdf</p></td>
<td><p>Хранилище данных для процесса записи сведений о вызовах (CDR) сервера мониторинга</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr. ldf</p></td>
<td><p>Журнал транзакций для данных регистрации вызовов (CDR)</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics. mdf</p></td>
<td><p>Файл данных качества взаимодействия, хранящийся на сервере мониторинга</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics. ldf</p></td>
<td><p>Журнал транзакций для данных мониторинга</p></td>
</tr>
<tr class="odd">
<td><p>Lcslog. mdf</p></td>
<td><p>Файл данных для хранения данных о мгновенных сообщениях и конференц-связи на сервере архивации</p></td>
</tr>
<tr class="even">
<td><p>Lcslog. ldf</p></td>
<td><p>Журнал транзакций для данных архивации</p></td>
</tr>
</tbody>
</table>


В этом разделе упоминаются диски и массивы RAID. Обратите внимание на то, что при настройке ресурсов SQL Server под диском понимается отдельное устройство. Жесткий диск с двумя разделами, одним для файлов журналов, а другим для файлов данных, не равноценен двум дискам, выделенным для тех же целей.

Когда речь идет о массивах RAID, следует иметь в виду, что существует ряд различных технологий RAID от разных поставщиков. А с распространением сетей хранения данных (SAN) выделенные массивы RAID используются все реже. Вы должны обратиться к поставщику RAID или SAN, чтобы определить оптимальную конфигурацию для вашей структуры диска при настройке производительности SQL Server с помощью Lync Server 2013.

Также обратите внимание на то, что не все диски одинаковы по своим показателям — некоторые работают быстрее, чем другие. Даже диски от одного производителя могут различаться по производительности из-за скорости вращения, размера аппаратного кэша и других факторов.

</div>

<span> </span>

</div>

</div>

</div>

