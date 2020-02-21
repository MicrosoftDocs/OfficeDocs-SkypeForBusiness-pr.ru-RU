---
title: 'Lync Server 2013: представление Таблица voipdetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7911a203a46d9bfa5698d01dc43c27c5f789c89a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a>Представление Таблица voipdetails в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-18_

В представлении Таблица voipdetails хранятся сведения об одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP. Это представление было представлено в Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> В представлении Таблица voipdetails содержатся все столбцы в <A href="lync-server-2013-sessiondetails-view.md">представлении SessionDetails в Lync Server 2013</A> , а также столбцы, перечисленные ниже.



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>фромфоне</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) телефона пользователя, запустившего сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>тофоне</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) телефона пользователя, который присоединился к сеансу.</p></td>
</tr>
<tr class="odd">
<td><p><strong>дисконнектедбюри</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) пользователя, который отключил сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>дисконнектедбюритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип универсального кода ресурса (URI) пользователя, который отключил сеанс. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>дисконнектедбитенант</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Клиент пользователя, который отключил сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>дисконнектедбифоне</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) телефона пользователя, который отключил сеанс.</p></td>
</tr>
<tr class="odd">
<td><p><strong>фроммедиатионсервер</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Сервер-посредник, используемый пользователем, запустившего сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>томедиатионсервер</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Сервер-посредник, используемый пользователем, который присоединился к сеансу.</p></td>
</tr>
<tr class="odd">
<td><p><strong>фромгатевай</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Шлюз, используемый пользователем, запустившего сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>тогатевай</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Шлюз, используемый пользователем, который присоединился к сеансу.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

