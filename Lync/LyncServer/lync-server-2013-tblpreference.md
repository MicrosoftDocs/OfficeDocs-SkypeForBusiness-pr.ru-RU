---
title: 'Lync Server 2013: Тблпреференце'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d1405634ad92b3f2cde2d085875648d738d6200
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a>Тблпреференце в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-24_

Тблпреференце содержит параметры клиента для пользователей. Обычно они используются клиентами, предшествующими Lync 2013.

### <a name="columns"></a>Columns

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
<td><p>префлабел</p></td>
<td><p>nvarchar (255), не равно null</p></td>
<td><p>Метка с форматом: &lt;URI&gt;SIP пользователя | username. &lt;набор&gt;параметров.</p></td>
</tr>
<tr class="even">
<td><p>префсекид</p></td>
<td><p>int, not null</p></td>
<td><p>Порядковый номер (каждой отдельной метки) для управления версиями.</p></td>
</tr>
<tr class="odd">
<td><p>префконтент</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>Зашифрованное содержимое.</p></td>
</tr>
<tr class="even">
<td><p>lastModifiedBy</p></td>
<td><p>int, не равно null</p></td>
<td><p>Идентификатор субъекта, обновившего параметр.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Key

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;Префлабел, Префсекид&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

