---
title: 'Lync Server 2013: Тблкомплианцестате'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615045(v=OCS.15)
ms:contentKeyID: 48185937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84608b7cb701fe4c394ed413539759d9469a5a4e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509416"
---
# <a name="tblcompliancestate-in-lync-server-2013"></a>Тблкомплианцестате в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-28_

Таблица tblComplianceState содержит сведения о состоянии соответствия во всем пуле.

### <a name="columns"></a>Столбцы

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ластпроцесседентрид</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Идентификатор последнего обработанного события соответствия.</p></td>
</tr>
<tr class="even">
<td><p>активесерверид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор сервера соответствия, на котором находится монопольная блокировка базы данных, или -1 при ее отсутствии.</p></td>
</tr>
<tr class="odd">
<td><p>локкекспиратионтиме</p></td>
<td><p>datetime2, NOT NULL</p></td>
<td><p>Время окончания блокировки (если значение activeServerID не равно -1).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

