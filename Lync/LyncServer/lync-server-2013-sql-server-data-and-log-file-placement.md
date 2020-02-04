---
title: 'Lync Server 2013: размещение данных и файла журнала SQL Server'
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
ms.openlocfilehash: 197141ea62307631eab206fce5403d25b4d89583
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Размещение данных и файла журнала SQL Server для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-21_

При планировании и развертывании Microsoft SQL Server 2012 или Microsoft SQL Server 2008 R2 SP1 для пула Lync Server 2013, важно помнить, что при работе с данными и файлами журнала на физических жестких дисках будет размещаться файл данных и журнал. Рекомендуемая конфигурация диска — это реализация 1 + 0 RAID-массива с использованием шести дисков. Размещение всех файлов базы данных и журналов, которые используются интерфейсным пулом и связанными ролями и службами сервера (то есть сервера архивирования и мониторинга, службы группы ответов Lync Server, службы «Служба поддержки пользователей» Lync Server) на диск RAID, установленный с помощью Lync Server Мастер развертывания приведет к тому, что конфигурация была протестирована на предмет оптимальной производительности. Файлы базы данных и их ответственные описаны в таблице ниже.

<div>


> [!NOTE]  
> Если ваши политики и конфигурации SQL Server требуют более специализированной установки, файлы базы данных и журнала можно установить в любое предопределенное расположение с помощью командной консоли Lync Server Management Shell. Дополнительные сведения о том, как <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">установить базу данных с помощью командной консоли Lync Server Management Shell, вы увидите в Lync server 2013</A> .



</div>

### <a name="data-and-log-files-for-central-management-store"></a>Файлы данных и журналов для централизованного управления хранилищем

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Файлы баз данных централизованного управления хранилищем</th>
<th>Файл данных или назначение журнала</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XDS. ldf</p></td>
<td><p>Файл журнала транзакций для хранилища центрального управления</p></td>
</tr>
<tr class="even">
<td><p>XDS. mdf</p></td>
<td><p>Сохраняет конфигурацию текущей топологии Lync Server 2013, определенную и опубликованную с помощью построителя топологии.</p></td>
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


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>Файлы данных и журналов для пользователей, конференций и адресной книги

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Файлы базы данных основного Lync Server 2013</th>
<th>Файл данных или назначение журнала</th>
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
<td><p>Рткдин. mdf</p></td>
<td><p>Поддерживает временные пользовательские данные (данные среды выполнения присутствия)</p></td>
</tr>
<tr class="even">
<td><p>Рткдин. ldf</p></td>
<td><p>Журнал транзакций для данных Рткдин</p></td>
</tr>
<tr class="odd">
<td><p>Рткаб. mdf</p></td>
<td><p>База данных адресной книги в реальном времени (RTC) — это репозиторий SQL Server, в котором хранятся сведения о службе адресной книги</p></td>
</tr>
<tr class="even">
<td><p>Рткаб. ldf</p></td>
<td><p>Журнал транзакций для службы «адресная книга»</p></td>
</tr>
<tr class="odd">
<td><p>Ртклокал. mdb</p></td>
<td><p>Размещение каталога конференций</p></td>
</tr>
<tr class="even">
<td><p>Рткксдс. mdf</p></td>
<td><p>Сохранение резервной копии данных пользователя</p></td>
</tr>
<tr class="odd">
<td><p>Рткксдс. ldf</p></td>
<td><p>Журнал транзакций для данных Рткксдс</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>Файлы данных и журналов для парковки звонков и группы ответа

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>данных приложения</th>
<th>Файл данных или назначение журнала</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Кпсдин. mdf</p></td>
<td><p>Динамическая информационная база данных для приложения парковки звонков</p></td>
</tr>
<tr class="even">
<td><p>Кпсдин. ldf</p></td>
<td><p>Журнал транзакций для файла данных приложения с приостановкой звонков</p></td>
</tr>
<tr class="odd">
<td><p>Ргсконфиг. mdf</p></td>
<td><p>Файл данных службы группы ответа Lync Server для настройки служб</p></td>
</tr>
<tr class="even">
<td><p>Ргсконфиг. ldf</p></td>
<td><p>Файл журнала транзакций для конфигурации приложения группы ответа</p></td>
</tr>
<tr class="odd">
<td><p>Ргсдин. mdf</p></td>
<td><p>Файл данных службы группы ответа для операций среды выполнения</p></td>
</tr>
<tr class="even">
<td><p>Ргсдин. ldf</p></td>
<td><p>Журнал транзакций для файла данных среды выполнения службы группы ответа</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>Файлы данных и журналов для архивации и мониторинга сервера

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Архивирование и мониторинг файлов базы данных</th>
<th>Файл данных или назначение журнала</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Лкскдр. mdf</p></td>
<td><p>Хранилище данных для процесса записи сведений о звонке (CDR) на сервере мониторинга</p></td>
</tr>
<tr class="even">
<td><p>Лкскдр. ldf</p></td>
<td><p>Журнал транзакций для данных записи сведений о звонке (CDR)</p></td>
</tr>
<tr class="odd">
<td><p>Коеметрикс. mdf</p></td>
<td><p>Файл данных качества взаимодействия, хранящийся на сервере мониторинга</p></td>
</tr>
<tr class="even">
<td><p>Коеметрикс. ldf</p></td>
<td><p>Журнал транзакций для наблюдения за данными</p></td>
</tr>
<tr class="odd">
<td><p>Лкслог. mdf</p></td>
<td><p>Файл данных для хранения данных о мгновенных сообщениях и конференц-связи на сервере архивации</p></td>
</tr>
<tr class="even">
<td><p>Лкслог. ldf</p></td>
<td><p>Журнал транзакций для архивации данных</p></td>
</tr>
</tbody>
</table>


В этом разделе приведены ссылки на диск и на наборы RAID. Обратите внимание, что в конфигурации ресурсов SQL Server обращение к диску означает, что это одно аппаратное устройство. Жесткий диск с двумя разделами, один из которых хранит файлы журнала и другой раздел, содержащий файлы данных, отличается от двух дисков, каждый из которых предназначен для файлов журнала или данных.

В ссылках на массивы RAID существуют различные технологии RAID различных производителей. И с ростом числа сетей хранения данных (SAN) наборы RAID, выделенные для одной системы, рарер. Вы должны обратиться к поставщику RAID или сети хранения данных, чтобы определить оптимальную конфигурацию для вашего макета диска при настройке производительности SQL Server с помощью Lync Server 2013.

Кроме того, обратите внимание на то, что не все диски создаются одинаково. Некоторые действия выполняются лучше, чем другие. Даже диски одного и того же производителя могут варьироваться в зависимости от скорости вращения, размера кэша оборудования и других факторов.

</div>

<span> </span>

</div>

</div>

</div>

