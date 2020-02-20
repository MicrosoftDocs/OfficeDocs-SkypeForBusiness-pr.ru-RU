---
title: 'Lync Server 2013: список представлений CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de760c2305ea4682ab53f3d0fabfcf3d06cf7e78
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-views-in-lync-server-2013"></a>Список представлений CDR в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-01_

Представления позволяют легко получить доступ к сведениям посредством наиболее распространенных сценариев извлечения данных из базы данных записей о звонках (CDR). Рекомендуется использовать представления для создания настраиваемых отчетов, а не таблиц базы данных CDR; Это связано с тем, что представления базы данных чаще всего поддерживают обратную совместимость с будущими выпусками Lync Server.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя представления</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-view.md">Представление Таблица clientversions в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о программном обеспечении и устройствах клиента, которые используются в сеансах связи.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencemessagecount-view.md">Представление Таблица conferencemessagecount в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о количестве сообщений, отправленных пользователями на конференции.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-view.md">Представление конференций в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о конференции, включая время начала, время окончания и инициатора конференции.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-view.md">Представление Таблица conferencesessiondetails в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о сеансе для всех сеансов конференц-связи, включая время начала и окончания, идентификаторы пользователей, коды ответа и диагностические идентификаторы.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferenceuris-view.md">Представление Таблица conferenceuris в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о кодах URI, используемых в конференции</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errorreport-view.md">Представление ErrorReport в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения об ошибках, возникших во время сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-filetransfers-view.md">Представление Таблица filetransfers в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о сеансах с передачей файлов, включая имя файла и сведения о том, была ли передача принята, отклонена или отменена.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-focusjoinsandleaves-view.md">Представление Таблица focusjoinsandleaves в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о действиях по присоединению к конференции и выходу из нее.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mcujoinsandleaves-view.md">Представление Таблица mcujoinsandleaves в Lync Server 2013</a></p></td>
<td><p>Возвращает объединенные сведения о действиях по присоединению к конференции и выходу из нее (каждое присоединение к конференции сопоставляется с соответствующим выходом из конференции).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-view.md">Представление MCUs в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о серверах конференц-связи.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-view.md">Представление мультимедиа в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о типах мультимедиа, используемых в одноранговых сеансах связи.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-view.md">Представление Таблица progressreport в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о завершенных сеансах.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-registration-view.md">Представление регистрации в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о регистрациях в Lync Server.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessiondetails-view.md">Представление SessionDetails в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения об одноранговых сеансах, включающих телефонные звонки VoIP-VoIP, двусторонние сеансы обмена мгновенными сообщениями или другие одноранговые сеансы связи.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-user-view.md">Пользовательское представление в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о пользователях, которые участвовали в сеансах связи.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-voipdetails-view.md">Представление Таблица voipdetails в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения об одноранговых сеансах как минимум с одним пользователем VoIP.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

