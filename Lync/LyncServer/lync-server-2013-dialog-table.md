---
title: 'Lync Server 2013: таблица Dialog'
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
ms.openlocfilehash: 2f0ef564ad1224ba9970b7cceb5db60e0eb344da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a>Таблица Dialog в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-02_

Диалоговая таблица — это вспомогательная таблица; Каждая запись отображает диалоговое окно протокола SIP.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Столбец</strong></th>
<th><strong>Тип данных</strong></th>
<th><strong>Ключ/индекс</strong></th>
<th><strong>Сведения</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>конференцедатетиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Время, когда агент качества (QoE) получает первый отчет от вызывающего или вызываемого абонента. Используется в сочетании с Сессионсек для уникальной идентификации сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Порядковый номер, чтобы отличать сеансы связи с одинаковым Конференцедатетиме.</p></td>
</tr>
<tr class="odd">
<td><p><strong>диалогид</strong></p></td>
<td><p>varchar (256)</p></td>
<td></td>
<td><p>ИДЕНТИФИКАТОР диалогового окна, который является глобально уникальным.</p></td>
</tr>
<tr class="even">
<td><p><strong>диалогидчекксум</strong></p></td>
<td><p>целое</p></td>
<td><p>индекса</p></td>
<td><p>Контрольная сумма идентификатора диалогового окна.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

