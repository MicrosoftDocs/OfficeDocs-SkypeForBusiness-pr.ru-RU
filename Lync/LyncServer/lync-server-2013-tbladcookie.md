---
title: 'Lync Server 2013: tblADCookie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf372f3dfc39f3ca90cbe0019af09e8d9dd33d26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509516"
---
# <a name="tbladcookie-in-lync-server-2013"></a>tblADCookie в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-25_

tblADCookie содержит текущие файлы cookie синхронизации для протокола LDAP.

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
<td><p>прингуид</p></td>
<td><p>GUID, не NULL</p></td>
<td><p>GUID субъекта для домена, за которым осуществляется мониторинг.</p></td>
</tr>
<tr class="even">
<td><p>приндчост</p></td>
<td><p>nvarchar (255)</p></td>
<td><p>Полное доменное имя (FQDN) текущего контроллера домена, используемого для синхронизации доменных служб Active Directory. Имеет информационное значение.</p></td>
</tr>
<tr class="odd">
<td><p>адкконтент</p></td>
<td><p>image (binary)</p></td>
<td><p>Файл cookie синхронизации Active Directory.</p></td>
</tr>
<tr class="even">
<td><p>ластупдатед</p></td>
<td><p>datetime</p></td>
<td><p>Метка времени со временем обновления строки.</p></td>
</tr>
<tr class="odd">
<td><p>локкедунтил</p></td>
<td><p>datetime</p></td>
<td><p>время, до которого строка заблокирована для внесения изменений. Это часть механизма программной блокировки, которая обеспечивает одновременное выполнение синхронизации Active Directory только одной службой чата.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Keys

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбцы</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>прингуид</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>прингуид</p></td>
<td><p>Внешний ключ с поиском в таблице Principal.prinGuid.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

