---
title: 'Lync Server 2013: tblComplianceState'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615045(v=OCS.15)
ms:contentKeyID: 48185937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fce70f05b317ac7467fd17306d6933c66087e5e6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancestate-in-lync-server-2013"></a>tblComplianceState в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-06-28_

Тблкомплианцестате включает в себя сведения о состоянии соответствия требованиям всего пула.

### <a name="columns"></a>Столбцов

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
<td><p>Ластпроцесседентрид</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Идентификатор последнего обработанного события соответствия требованиям.</p></td>
</tr>
<tr class="even">
<td><p>Активесерверид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор сервера соответствия, который удерживает монопольную блокировку для базы данных, или значение-1, если нет.</p></td>
</tr>
<tr class="odd">
<td><p>Локкекспиратионтиме</p></td>
<td><p>datetime2, NOT NULL</p></td>
<td><p>Заблокируйте срок действия (если Активесерверид не является 1).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

