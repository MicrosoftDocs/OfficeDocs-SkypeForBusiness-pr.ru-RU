---
title: 'Lync Server 2013: таблица диалоговых окон'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 578b27a61e6af7114da19eb0d6d21dea38dba551
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a>Таблица диалогов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

Таблица Dialog является вспомогательной. Каждая запись представляет одно диалоговое окно SIP.


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
<td><p>Primary</p></td>
<td><p>Время получения  агентом качества обслуживания первого отчета от звонящего или вызываемого абонента. Используется совместно с SessionSeq для уникальной идентификации сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионсек</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Порядковый номер, позволяющий различать сеансы с одинаковым ConferenceDateTime.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogID</strong></p></td>
<td><p>varchar (256)</p></td>
<td></td>
<td><p>Глобальный уникальный идентификатор диалогового окна.</p></td>
</tr>
<tr class="even">
<td><p><strong>диалогидчекксум</strong></p></td>
<td><p>int</p></td>
<td><p>index</p></td>
<td><p>Контрольная сумма идентификатора диалогового окна.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

