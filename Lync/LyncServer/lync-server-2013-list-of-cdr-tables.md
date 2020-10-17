---
title: 'Lync Server 2013: список таблиц CDR'
description: 'Lync Server 2013: список таблиц CDR.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21d0f683ffeb0f5f1cbba5db4c45d248aa14e8e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558705"
---
# <a name="list-of-cdr-tables-in-lync-server-2013"></a>Список таблиц CDR в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-18_

Схема базы данных регистрации вызовов (call detail recording — CDR) состоит из следующих таблиц.

<div>

## <a name="static-tables"></a>Статические таблицы


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-callpriorities-table.md">Таблица Таблица callpriorities в Lync Server 2013</a></p></td>
<td><p>Сохранение списка возможных приоритетов вызовов (включая аварийные, срочные, обычные, несрочные и т. д.).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">Таблица Таблица conferencejointimethresholds в Lync Server 2013</a></p></td>
<td><p>Сохранение границ классификации, используемых в отчете со сводными данными по времени подсоединения к конференции.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Таблица Таблица deregistertype в Lync Server 2013</a></p></td>
<td><p>Хранит список возможных причин отмены регистрации пользователей, таких как &quot; инициирование клиента, &quot; &quot; срок действия регистрации, &quot; &quot; сбой клиента &quot; и многое другое.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Таблица Таблица medialist в Lync Server 2013</a></p></td>
<td><p>Сохранение списка типов мультимедиа, которые могут создавать записи в базе данных (например, чат, аудио, видео и передача файлов).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">Таблица Таблица purgesettings в Lync Server 2013</a></p></td>
<td><p>Сохранение информации, определяющей, следует ли (и когда) автоматически удалять устаревшие записи о вызовах из базы данных CDR.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Таблица Roles в Lync Server 2013</a></p></td>
<td><p>Сохранение списка возможных ролей участников конференции (например, участник и докладчик).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">Таблица Сипреспонсеметадата в Lync Server 2013</a></p></td>
<td><p>Сохранение списка кодов ответов SIP, классификации и определения каждого из этих кодов.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a>Вспомогательные таблицы


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-table.md">Таблица Таблица clientversions в Lync Server 2013</a></p></td>
<td><p>Сохранение клиентов (включая тип клиента и номер версии) каждого клиента, участвующего в вызове, с указанием информации, собранной в этой базе данных.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">Таблица Таблица conferenceuris в Lync Server 2013</a></p></td>
<td><p>Сохранение списка кодов URI конференций, которые используются в вызовах, связанных с конференцией.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">Таблица ContentTypes в Lync Server 2013</a></p></td>
<td><p>Сохранение списка типов содержимого SIP (Session Initiation Protocol), которые используются и в одноранговых вызовах, и в конференц-вызовах.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Таблица Devices в Lync Server 2013</a></p></td>
<td><p>Сохранение списка устройств, включая производителя, версию оборудования и MAC-адрес.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Таблица диалогов в Lync Server 2013</a></p></td>
<td><p>Сохранение идентификаторов диалогов для каждого сеанса в базе данных.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">Таблица Таблица edgeservers в Lync Server 2013</a></p></td>
<td><p>Сохранение списка пограничных серверов, которые используются для внешних вызовов.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Таблица Gateways в Lync Server 2013</a></p></td>
<td><p>Сохранение списка шлюзов, которые используются для вызовов по протоколу VoIP.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Таблица Таблица hardwareversions в Lync Server 2013</a></p></td>
<td><p>Сохранение списка аппаратных версий устройств (стационарный телефон).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Таблица производителей в Lync Server 2013</a></p></td>
<td><p>Сохранение списка производителей устройств (стационарный телефон).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Таблица MCUs в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о различных серверах конференц-связи (аудио-видео) и их кодов URI.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">Таблица Таблица mediationservers в Lync Server 2013</a></p></td>
<td><p>Сохранение списка серверов-посредников, используемых для выполнения вызовов по протоколу VoIP.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Таблица phones в Lync Server 2013</a></p></td>
<td><p>Сохранение всех номеров телефона, использованных для выполнения вызовов по протоколу VoIP, которые были архивированы или сведения о которых были зарегистрированы.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Таблица Pools в Lync Server 2013</a></p></td>
<td><p>Сохранение имен пула, в котором записываются мгновенные сообщения.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Таблица Servers в Lync Server 2013</a></p></td>
<td><p>Сохранение имен серверов, участвующих в вызовах.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Таблица клиентов в Lync Server 2013</a></p></td>
<td><p>Сохранение клиентов, поддерживаемых текущим развертыванием. Существует ряд встроенных клиентов для корпоративных пользователей, федеративных пользователей, пользователей с подключением к общедоступным системам обмена мгновенными сообщениями и анонимных пользователей.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">Таблица Таблица useragentdef в Lync Server 2013</a></p></td>
<td><p>Привязка идентификаторов агента пользователя к описательным именам агента.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a></p></td>
<td><p>Сохранение кодов URI пользователей, которые участвовали в сеансах, зарегистрированных или заархивированных в этой базе данных.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">Таблица Усерстатистикс в Lync Server 2013</a></p></td>
<td><p>Сохранение сведений об использовании системы отдельным пользователем.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a>Записи, относящиеся к конкретным записям CDR конференции


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-table.md">Таблица конференций в Lync Server 2013</a></p></td>
<td><p>Сохранение информации обо всех конференциях, которые были заархивированы или сведения о которых были зарегистрированы, включая URI конференции, время начала и окончания.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">Таблица Таблица conferencesessiondetails в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о каждом сеансе конференц-связи на основе SIP, включая время начала и окончания, идентификатор пользователя, код ответа и идентификатор диагностики для каждого сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">Таблица Таблица focusjoinsandleaves в Lync Server 2013</a></p></td>
<td><p>Сохранение сведений о присоединениях к конференциям и отключениям от них, включая роли пользователей и версии клиентов.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">Таблица Таблица mcujoinsandleaves в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о серверах конференц-связи (аудио-видео), задействованных в конференции, и сведений о времени подключения и отключения пользователей.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a>Таблицы для сообщений в чат-конференциях


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferencemessagecount-table.md">Таблица Таблица conferencemessagecount в Lync Server 2013</a></p></td>
<td><p>Сохранение количества сообщений, которые были отправлены каждым пользователем, для каждой чат-конференции.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">Таблица Имрепортсуммари в Lync Server 2013</a></p></td>
<td><p>Предоставление общего отчета по сеансам обмена мгновенными сообщениями, которые проводятся в организации.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a>Таблицы для одноранговых сеансов


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-sessiondetails-table.md">Таблица SessionDetails в Lync Server 2013</a></p></td>
<td><p>Сохранение информацию о каждом одноранговом сеансе, включая время начала и окончания, идентификатор пользователя, код ответа и количество сообщений каждого пользователя.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Таблица Таблица filetransfers в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о сеансах передачи файлов, включая имя файла и результат (принято, отклонено или отменено).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Таблица мультимедиа в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о различных типах носителей, используемых в ходе одноранговых сеансов.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a>Таблица для сведений о вызовах VoIP


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-voipdetails-table.md">Таблица Таблица voipdetails в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о вызове, включая идентификатор телефона VoIP, используемый шлюз и сторону, прервавшую вызов, для каждого двустороннего вызова VoIP/ТСОП. Ссылка на <a href="lync-server-2013-sessiondetails-table.md">таблицу SessionDetails в Lync Server 2013</a> для времени начала и окончания вызова и кода ответа.</p>
<div>

> [!NOTE]  
> Если один участник вызова является пользователем VoIP или при выполнении вызова задействован сервер-посредник, в этой таблице создается соответствующая запись. Сведения о вызовах VoIP/VoIP, не связанных с телефонной телефонной сетью общего пользования (PSTN), записываются в <A href="lync-server-2013-sessiondetails-table.md">таблицу SessionDetails в Lync Server 2013</A>.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a>Таблица для аудита вызовов E9-1-1


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-locations-table.md">Таблица Locations в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о каждом экстренном вызове, например вызове Enhanced 9-1-1 (E9-1-1). Ссылка на <a href="lync-server-2013-sessiondetails-table.md">таблицу SessionDetails в Lync Server 2013</a> для времени начала и окончания вызова и кода ответа.</p>
<div>

> [!NOTE]  
> В этой таблице содержится только большой двоичный объект местоположения для вызова E9-1-1. Ссылается на таблицу SessionDetails, в которой указываются другие подробные сведения о вызове.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a>Таблицы для устранения неполадок


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-application-table.md">Таблица Application в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о различных процессах в Lync Server 2013, участвующих в маршрутизации и подключениях.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">Таблица CallType в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о типах вызовов, например «аудио», «чат», «аудио и видео» и «общий доступ к приложениям».</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">Таблица ErrorCategory в Lync Server 2013</a></p></td>
<td><p>Хранит понятное имя каждого диагностической классификации Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">Таблица Таблица errordef в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о типах ошибок и их определениях.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">Таблица ErrorReport в Lync Server 2013</a></p></td>
<td><p>Сохранение информации о возникших ошибках.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">Таблица Таблица progressreport в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о ходе выполнения различных действий, связанных с процессами Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


Таблицы, приведенные в следующем списке, используются внутренними средствами Lync Server. Сведения о них не приведены в данном документе.

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a>Таблицы для внутреннего использования сервером Lync Server


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Описание</th>
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
<td><p><strong>дберрормессаже</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>FrontEnd Table</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MSMQProcessing Table</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>суммаритаблеконфигуратион</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Syndicators Table</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>SyndicatorsTenantMap Table</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Task Table</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserStatistics</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UsageSummary_UQ</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>усажесуммари</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>дайлигхтсавингеарс</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>тимезонеконфигуратион</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZones</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>FailureSummary_UQ</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>фаилуресуммари</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>серверсуммари</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>мсдиагметадата</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

