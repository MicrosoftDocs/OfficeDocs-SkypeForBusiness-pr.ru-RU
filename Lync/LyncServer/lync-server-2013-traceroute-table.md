---
title: 'Lync Server 2013: таблица Трацерауте'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 057253527615164b4b8b22a1fa13e7ea48778ee1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193492"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a>Таблица Трацерауте в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-02-21_

Таблица TraceRoute содержит сведения о маршрутизации звонков. Эта таблица была введена в Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Column</strong></th>
<th><strong>Тип данных</strong></th>
<th><strong>Ключ или индекс</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>конференцедатетиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Дата и время начала звонка.</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионсек</strong></p></td>
<td><p>int</p></td>
<td><p>Основной, Внешний</p></td>
<td><p>Уникальный идентификатор, используемых для однозначной идентификации звонков, которые могут начаться одновременно.</p></td>
</tr>
<tr class="odd">
<td><p><strong>медиалинелабел</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Представляет тип видеоканала, используемого для звонка. Допускаются следующие значения:</p>
<ul>
<li><p>0 — звук</p></li>
<li><p>1 — видео</p></li>
<li><p>2 — панорамное видео</p></li>
<li><p>3 — общий доступ к приложениям и рабочим столам</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>фромкаллер</strong></p></td>
<td><p>Битовая</p></td>
<td><p>Primary</p></td>
<td><p>Конечная точка, выполнившая звонок.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Перехода</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Переход между сетями.</p></td>
</tr>
<tr class="even">
<td><p><strong>ипаддресскэй</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Уникальный идентификатор IP-адреса. Сведения об IP-адресе хранятся в <a href="lync-server-2013-ipaddress-table.md">таблице IPAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ПРИЕМА</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Время цикла. Это время, которое требуется на то, чтобы пакет с голосовыми данными достиг назначения и отправил обратно уведомление о том, что он был получен.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

