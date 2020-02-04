---
title: 'Lync Server 2013: список таблиц регистрации звонков'
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
ms.openlocfilehash: b0c620eaf6b54a89604071a18f445d20816178bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a>Список таблиц регистрации звонков в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-18_

Схема базы данных для записи сведений о звонке (CDR) состоит из следующих таблиц.

<div>

## <a name="static-tables"></a>Статические таблицы


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-callpriorities-table.md">Таблица SessionCorrelation в Lync Server 2013</a></p></td>
<td><p>Хранит список возможных приоритетов звонков, например, экстренных, срочных, обычных, несрочных и т. д.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">Таблица Конференцежоинтимесрешолдс в Lync Server 2013</a></p></td>
<td><p>Хранит границы классификации, используемые в сводном отчете "время присоединения к Конференции".</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Таблица DeRegisterType в Lync Server 2013</a></p></td>
<td><p>Хранит список возможных причин, по которым пользователь может отменить регистрацию, например &quot;инициирование клиента&quot; &quot;, истек срок регистрации&quot; &quot;, сбой клиента&quot; и многое другое.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Таблица MediaList в Lync Server 2013</a></p></td>
<td><p>Хранит список типов мультимедиа, которые могут создавать записи в базе данных (например, мгновенные сообщения, звук, видео и передачу файлов).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">Таблица Пуржесеттингс в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о том, будут ли (и когда) устаревшие записи о вызовах автоматически удалены из базы данных CDR.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Таблица Roles в Lync Server 2013</a></p></td>
<td><p>Хранит список возможных ролей конференции (например, участника и выступающего).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">Таблица Сипреспонсеметадата в Lync Server 2013</a></p></td>
<td><p>Содержит список кодов ответов SIP и классификацию и определение каждого из этих кодов.</p></td>
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
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-table.md">Таблица ClientVersions в Lync Server 2013</a></p></td>
<td><p>Хранит клиентов (тип клиента и номер версии) каждого клиента, участвующего в вызове, с данными, захваченными в этой базе данных.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">Таблица ConferenceUris в Lync Server 2013</a></p></td>
<td><p>Хранит список Конференцеурис, используемых в звонках, связанных с Конференцией.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">Таблица ContentTypes в Lync Server 2013</a></p></td>
<td><p>Хранит список типов контента SIP, которые используются в одноранговых звонках и конференц-связи.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Таблица Devices в Lync Server 2013</a></p></td>
<td><p>Хранит список устройств, в том числе изготовителя, аппаратную версию и MAC-адрес.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о коде диалогового окна для каждого сеанса в базе данных.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">Таблица EdgeServers в Lync Server 2013</a></p></td>
<td><p>Хранит список пограничных серверов, которые используются при внешних звонках.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Таблица Gateways в Lync Server 2013</a></p></td>
<td><p>Хранит список шлюзов, используемых для звонков по протоколу голосовой связи через Интернет (VoIP).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Таблица HardwareVersions в Lync Server 2013</a></p></td>
<td><p>Хранит список аппаратных версий устройств (стационарных телефонов).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Таблица Manufacturers в Lync Server 2013</a></p></td>
<td><p>Хранит список изготовителей устройств (стационарный телефон).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Таблица Mcus в Lync Server 2013</a></p></td>
<td><p>В этой папке хранятся сведения о различных серверах конференций/V и их URI.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">Таблица MediationServers в Lync Server 2013</a></p></td>
<td><p>Хранит список серверов-посредников, используемых для звонков по протоколу VoIP.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Таблица Phones в Lync Server 2013</a></p></td>
<td><p>Хранит все телефонные номера, используемые для звонков по протоколу VoIP, которые были заархивированы или в которых были записаны сведения о звонках.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Таблица Pools в Lync Server 2013</a></p></td>
<td><p>Хранит имена групп, в которых регистрируются МГНОВЕНные сообщения.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Таблица Servers в Lync Server 2013</a></p></td>
<td><p>Хранит имена серверов, участвующих в звонках.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Таблица Tenants в Lync Server 2013</a></p></td>
<td><p>Хранит клиентов, которые поддерживаются текущим развертыванием. Некоторые клиентские сборки для корпоративных пользователей, федеративного пользователя, общего пользователя подключения к обмену мгновенными сообщениями и анонимные пользователи.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">Таблица Усеражентдеф в Lync Server 2013</a></p></td>
<td><p>Сопоставляет идентификаторы агента пользователя с описательными именами агента.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a></p></td>
<td><p>Хранит идентификаторы URI пользователей, которые участвовали в сеансах, записанных или архивированных в этой базе данных.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">Таблица Усерстатистикс в Lync Server 2013</a></p></td>
<td><p>Хранит сведения об использовании системы конкретным пользователем.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a>Таблицы, связанные с записями CDR конференций


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-table.md">Таблица Conferences в Lync Server 2013</a></p></td>
<td><p>Хранит сведения обо всех конференциях, которые были архивированы, а также о том, какие данные были записаны, включая Конференцеури, время начала и окончания.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">Таблица ConferenceSessionDetails в Lync Server 2013</a></p></td>
<td><p>В этой папке хранятся сведения о каждом сеансе конференции на базе SIP, в том числе время начала и окончания, идентификатор пользователя, код ответа и идентификатор диагностики для каждого сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">Таблица FocusJoinsAndLeaves в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о присоединениях и листьях конференций, в том числе о роли пользователей и клиентской версии.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">Таблица McuJoinsAndLeaves в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о серверах конференций (A/V), вовлеченных в конференцию, а также присоединения и выхода пользователей.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a>Таблицы для сообщений в конференциях по обмену мгновенными сообщениями


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferencemessagecount-table.md">Таблица ConferenceMessageCount в Lync Server 2013</a></p></td>
<td><p>Для каждой конференции с мгновенными сообщениями хранится количество сообщений, отправленных каждым пользователем.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">Таблица Имрепортсуммари в Lync Server 2013</a></p></td>
<td><p>Общие сведения о сеансах обмена мгновенными сообщениями, проводимых в Организации.</p></td>
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
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-sessiondetails-table.md">Таблица SessionDetails в Lync Server 2013</a></p></td>
<td><p>Хранит сведения обо всех одноранговых сеансах, в том числе время начала и окончания, идентификатор пользователя, код ответа и количество сообщений для каждого пользователя.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Таблица FileTransfers в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о сеансах передачи файлов, включая имя файла и результат (разрешено, отклонено или отменено).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Таблица Media в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о различных типах носителей, участвующих в одноранговых сеансах.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a>Таблица сведений о звонке VoIP


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-voipdetails-table.md">Таблица VoipDetails в Lync Server 2013</a></p></td>
<td><p>Для каждого из двух сторон VoIP/КТСОП звоните сведения о звонке, например номер телефона телефона VoIP, используемый шлюз, и какая сторона отключилась. Ссылка на <a href="lync-server-2013-sessiondetails-table.md">таблицу сессиондетаилс в Lync Server 2013</a> для значений "начало/окончание" и "код ответа" для вызова.</p>
<div>

> [!NOTE]  
> Если один из участников звонка является пользователем VoIP или на него вовлечен сервер-посредник, в этой таблице будет создана запись. Сведения о вызовах VoIP и VoIP, не посвященных коммутируемой телефонной сети общего пользования (PSTN), записываются в <A href="lync-server-2013-sessiondetails-table.md">таблицу сессиондетаилс в Lync Server 2013</A>.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a>Таблица для аудита звонков E9-1-1


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-locations-table.md">Таблица Locations в Lync Server 2013</a></p></td>
<td><p>Для каждого вызова экстренной помощи, например улучшенного звонка в 9-1-1 (E9-1-1), можно хранить сведения о его местонахождении. Ссылка на <a href="lync-server-2013-sessiondetails-table.md">таблицу сессиондетаилс в Lync Server 2013</a> для значений "начало/окончание" и "код ответа" для вызова.</p>
<div>

> [!NOTE]  
> Эта таблица включает большой двоичный объект Location для вызова E9-1-1. Ссылка на таблицу Сессиондетаилс для получения более подробной информации о звонке.


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
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-application-table.md">Таблица Application в Lync Server 2013</a></p></td>
<td><p>В этой папке хранятся сведения о различных процессах в Lync Server 2013, которые используются в маршруте и соединениях.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">Таблица CallType в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о типах звонка, например "звук", "мгновенные сообщения", "звук и видео" и "общий доступ к приложениям".</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">Таблица Ерроркатегори в Lync Server 2013</a></p></td>
<td><p>Хранит понятное имя для каждого диагностического классификация Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">Таблица ErrorDef в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о типах ошибок и их определениях.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">Таблица ErrorReport в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о возникших ошибках.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">Таблица ProgressReport в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о ходе выполнения различных шагов, участвующих в процессах Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


Таблицы, приведенные в следующем списке, используются для внутренних целей на сервере Lync Server. Эти сведения не описаны в настоящем документе.

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a>Таблицы для внутреннего использования в Lync Server


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
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
<td><p><strong>Интерфейсная таблица</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Таблица Мсмкпроцессинг</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>суммаритаблеконфигуратион</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Таблица "синдикации"</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>Таблица Синдикаторстенантмап</strong></p></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Таблица задач</strong></p></td>
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
<td><p><strong>Часовых поясов</strong></p></td>
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

