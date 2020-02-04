---
title: 'Lync Server 2013: представление Воипдетаилс'
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
ms.openlocfilehash: db65da0af7c34d1121e97436af47750186706b68
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a>Воипдетаилс представления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-18_

В представлении Воипдетаилс хранятся сведения о одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP. Это представление было представлено в Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> В представлении Воипдетаилс содержатся все столбцы в <A href="lync-server-2013-sessiondetails-view.md">представлении сессиондетаилс в Lync Server 2013</A> в дополнение к столбцам, перечисленным ниже.



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
<th>Подробности</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>фромфоне</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI телефона пользователя, запустившего сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>тофоне</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) пользователя, который присоединился к сеансу.</p></td>
</tr>
<tr class="odd">
<td><p><strong>дисконнектедбюри</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) пользователя, который отключил сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>дисконнектедбюритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя, который отключил сеанс. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>дисконнектедбитенант</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент пользователя, который отключил сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>дисконнектедбифоне</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) пользователя, который отключил сеанс.</p></td>
</tr>
<tr class="odd">
<td><p><strong>фроммедиатионсервер</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Сервер исправлений, используемый пользователем, который запустил сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>томедиатионсервер</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Сервер исправлений, используемый пользователем, который присоединил сеанс.</p></td>
</tr>
<tr class="odd">
<td><p><strong>фромгатевай</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Шлюз, используемый пользователем, который запустил сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>тогатевай</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Шлюз, используемый пользователем, который присоединился к сеансу.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

