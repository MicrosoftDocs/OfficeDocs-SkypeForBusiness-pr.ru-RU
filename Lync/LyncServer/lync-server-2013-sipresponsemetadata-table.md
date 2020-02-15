---
title: 'Lync Server 2013: таблица Сипреспонсеметадата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 164c6e1541869a2976f283443f2fae9246f28007
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038861"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>Таблица Сипреспонсеметадата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Таблица SIPResponseMetaDataTable содержит список кодов ответа SIP, а также классификацию и определение каждого из этих кодов. Эти коды генерируются в ответ на события, затрагивающие устройства SIP и сеансы связи SIP; например, код ответа 403 создается, когда устройство SIP выполняет запрос, но сервер отказывается принять его на обработку.

Эта таблица была введена в Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Ключ или индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>респонсекоде</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Числовое значение, которое определяет код ответа SIP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Класс</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Общая классификация кода ответа. Возможные классификации:</p>
<ul>
<li><p>1 — информационные ответы</p></li>
<li><p>2 — успешные ответы</p></li>
<li><p>3 — ответы перенаправления</p></li>
<li><p>4 — ответы сбоя клиента</p></li>
<li><p>5 — ответы об отказах серверов</p></li>
<li><p>6 — ответы глобального сбоя</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Описание</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Описание кода ответа SIP. Например, для кода ответа 181 доступно следующее описание:</p>
<p>Вызов перенаправляется</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

