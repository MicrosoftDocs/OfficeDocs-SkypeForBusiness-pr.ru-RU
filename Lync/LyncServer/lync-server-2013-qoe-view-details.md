---
title: 'Lync Server 2013: сведения о просмотре QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e223ff2adee63eb8e13304e4df6db519e85014f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a>QoE просмотра данных в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-03_

В представлениях рассматриваются наиболее распространенные сценарии возврата данных из базы данных SQL QoE. Рекомендуется использовать представления для создания настраиваемых отчетов вместо прямого доступа к таблицам базы данных; Это связано с тем, что представления более удобны для обеспечения обратной совместимости с будущими выпусками.


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
<td><p><a href="lync-server-2013-audiostreamdetail-view.md">Аудиостреамдетаил представления в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о каждом звуковом потоке в базе данных.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialine-view.md">Медиалине представления в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о каждой строке мультимедиа в базе данных. Один звуковой сеанс обычно состоит из одной линии звукового файла. Один из звуковых и видеофайлов (A/V) обычно состоит из одной линии звукового файла и одной линии видеоклипа; Тем не менее, в этом сеансе могут содержаться две строки видеофайла, если используется устройство конференц-связи или если используется представление коллекции.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-networkconfigurationsettings-view.md">Нетворкконфигуратионсеттингс представления в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о конфигурации сети.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-view.md">Представление сеанса в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о сеансах с записями в базе данных.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-view.md">Представление "UserAgent" в Lync Server 2013</a></p></td>
<td><p>Хранит сведения об агентах пользователей, вовлеченных в сеансы с записями в базе данных.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostreamdetail-view.md">Видеостреамдетаил представления в Lync Server 2013</a></p></td>
<td><p>Хранит сведения о каждом видеопотоке в базе данных.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

