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
ms.openlocfilehash: 1fcd6cb462bd64f6fdcdbae93cfb733de0639898
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>Таблица Сипреспонсеметадата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

В Сипреспонсеметадататабле содержится список кодов ответов SIP, а также классификация и определение каждого из этих кодов. Эти коды генерируются в ответ на события, влияющие на устройства SIP и сеансы связи SIP; Например, код ответа 403 генерируется, когда устройство SIP делает запрос, но сервер отклоняет этот запрос.

Эта таблица введена в Microsoft Lync Server 2013.


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
<th>Ключ/индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>респонсекоде</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Числовое значение, представляющее код ответа SIP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Классов</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Общая классификация для кода ответа. Существуют следующие классификации:</p>
<ul>
<li><p>1 — Информационные ответы</p></li>
<li><p>2 – успешные ответы</p></li>
<li><p>3 – Ответы на перенаправление</p></li>
<li><p>4 – Ответы на ошибки клиента</p></li>
<li><p>5-Ответы на ошибки сервера</p></li>
<li><p>6 – Глобальный ответ на сбой</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Описание</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Описание кода ответа SIP. Например, код ответа 181 имеет следующее описание:</p>
<p>Переадресация звонка</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

