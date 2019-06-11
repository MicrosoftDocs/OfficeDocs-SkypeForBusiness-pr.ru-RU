---
title: 'Lync Server 2013: список представлений CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112e565c07c685c1ecdf5db1d8a2de8717ba959e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-views-in-lync-server-2013"></a>Список представлений CDR в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-01_

Представления предоставляют простой способ получить доступ к сведениям о наиболее распространенных сценариях, используемых для возврата данных из базы данных CDR. Рекомендуется использовать представления для создания настраиваемых отчетов вместо использования таблиц баз данных реальных CDR; Это связано с тем, что представления базы данных более удобны для обеспечения обратной совместимости с будущими выпусками Lync Server.


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
<td><p><a href="lync-server-2013-clientversions-view.md">Клиентверсионс представления в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о клиентском программном обеспечении и устройствах, используемых в сеансе связи.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencemessagecount-view.md">Конференцемессажекаунт представления в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о количестве сообщений, отправленных пользователями на Конференции.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-view.md">Представление "Конференции" в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о конференции, в том числе время начала, время окончания и организатора конференции.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-view.md">Конференцесессиондетаилс представления в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о сеансе для всех сеансов конференц-связи, в том числе время начала и окончания, идентификаторы пользователей, коды ответа и диагностические идентификаторы.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferenceuris-view.md">Конференцеурис представления в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о URI конференций, используемых на Конференции.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errorreport-view.md">Ерроррепорт представления в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения об ошибках, произошедших во время сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-filetransfers-view.md">Филетрансферс представления в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о сеансах передачи файлов, в том числе имя файла и о том, были ли данные приняты, отклонены или отменены.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-focusjoinsandleaves-view.md">Фокусжоинсандлеавес представления в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о присоединении к Конференции и оставлении действий.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mcujoinsandleaves-view.md">Мкужоинсандлеавес представления в Lync Server 2013</a></p></td>
<td><p>Возвращает объединенные сведения о присоединениях к Конференции и оставлении действий (каждое присоединение к Конференции сопоставлено с выходом на соответствующую конференцию).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-view.md">Мкус представления в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о серверах конференций.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-view.md">Представление мультимедиа в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о типах мультимедиа, используемых в одноранговых сеансах связи.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-view.md">Прогрессрепорт представления в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о завершенных сеансах.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-registration-view.md">Представление регистрации в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о регистрациях с помощью Lync Server.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessiondetails-view.md">Сессиондетаилс представления в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о одноранговых сеансах, включая VoIP-звонки по телефонным каналам, два сеанса обмена мгновенными сообщениями и другие одноранговые сеансы связи.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-user-view.md">Представление пользователя в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о пользователях, участвующих в сеансах связи.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-voipdetails-view.md">Воипдетаилс представления в Lync Server 2013</a></p></td>
<td><p>Возвращает сведения о одноранговых сеансах с участием по крайней мере одного пользователя VoIP (с голосовым вводом-выводом).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

