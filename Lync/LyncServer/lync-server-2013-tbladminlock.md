---
title: 'Lync Server 2013: tblAdminLock'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558665(v=OCS.15)
ms:contentKeyID: 48184560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cdfbc28f440fe9bbcc186e685cd5efdb5f23498
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladminlock-in-lync-server-2013"></a>tblAdminLock в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-06-25_

Тбладминлокк содержит блокировку администратора, которая необходима для выполнения некоторых команд администратора.

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
<td><p>Локкекспирестиме</p></td>
<td><p>DateTime, NOT NULL</p></td>
<td><p>Заблокируйте дату и время окончания срока действия. Владелец может периодически увеличивать это значение.</p></td>
</tr>
<tr class="even">
<td><p>Локксерверид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор сервера, владеющего блокировкой.</p></td>
</tr>
<tr class="odd">
<td><p>Локкакторид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор участника, владеющего блокировкой.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

