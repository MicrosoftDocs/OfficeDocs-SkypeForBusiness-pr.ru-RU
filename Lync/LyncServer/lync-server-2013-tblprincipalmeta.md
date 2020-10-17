---
title: 'Lync Server 2013: tblPrincipalMeta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d70b26dc074213c30248da0e13f137c8b1e2f58a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523646"
---
# <a name="tblprincipalmeta-in-lync-server-2013"></a>tblPrincipalMeta в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-12_

tblPrincipalMeta содержит субъекты, которые необходимо обновить из доменных служб Active Directory.

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
<td><p>prinID</p></td>
<td><p>int, not null</p></td>
<td><p>ИД субъекта.</p></td>
</tr>
<tr class="even">
<td><p>принаффилиатионсдирти</p></td>
<td><p>bit, не равно null</p></td>
<td><p>Значение true, если назначения субъектов требуется обновить.</p></td>
</tr>
<tr class="odd">
<td><p>принаттрибутесдирти</p></td>
<td><p>bit, не равно null</p></td>
<td><p>Значение true, если атрибуты субъектов требуется обновить.</p></td>
</tr>
<tr class="even">
<td><p>принделетед</p></td>
<td><p>bit, не равно null</p></td>
<td><p>Значение true, если субъект был удален.</p></td>
</tr>
<tr class="odd">
<td><p>трикаунт</p></td>
<td><p>int</p></td>
<td><p>Число попыток обновления субъекта из доменных служб Active Directory, предпринятых на данный момент.</p></td>
</tr>
<tr class="even">
<td><p>ласттри</p></td>
<td><p>datetime</p></td>
<td><p>Метка времени для последней попытки обновления субъекта. Может иметь значение null, если попытки обновления еще не предпринимались.</p></td>
</tr>
<tr class="odd">
<td><p>нексттри</p></td>
<td><p>datetime</p></td>
<td><p>Метка времени для следующего запланированного обновления. Может иметь значение null, если дальнейшее обновление не запланировано.</p></td>
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
<th>Столбец</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinID</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Внешний ключ с поиском в таблице tblPrincipal.prinID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

