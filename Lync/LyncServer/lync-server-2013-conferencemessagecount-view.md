---
title: 'Lync Server 2013: представление Конференцемессажекаунт'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0324c9913a607057c4e1cd161a9040b83d6bd29b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-view-in-lync-server-2013"></a>Конференцемессажекаунт представления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-01_

В представлении Конференцемессажекаунт хранятся сведения о количестве сообщений, отправленных пользователем на конференцию. Это представление было представлено в Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> В представлении Конференцемессажекаунт содержатся все столбцы в <A href="lync-server-2013-conferencesessiondetails-view.md">представлении конференцесессиондетаилс в Lync Server 2013</A> в дополнение к столбцам, перечисленным ниже.



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
<td><p><strong>Усерури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) пользователя, отправившего сообщение.</p></td>
</tr>
<tr class="even">
<td><p><strong>Усеруритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя, отправившего сообщения. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Усертенант</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Клиент пользователя, отправившего сообщения. Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Усермессажекаунт</strong></p></td>
<td><p>smallint</p></td>
<td><p>Количество сообщений, отправленных пользователем во время сеанса конференции.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

