---
title: 'Lync Server 2013: tblPrincipalMeta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b9b067b9d04ecb32a3e43dbbd1f8435c00fa0c0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a>tblPrincipalMeta в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-12_

ТблпринЦипалмета содержит участников, которые необходимо обновлять из доменных служб Active Directory.

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
<td><p>Принид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор участника.</p></td>
</tr>
<tr class="even">
<td><p>Принаффилиатионсдирти</p></td>
<td><p>bit, NOT NULL</p></td>
<td><p>Значение true, если присвоить участникам участники необходимо обновлять.</p></td>
</tr>
<tr class="odd">
<td><p>Принаттрибутесдирти</p></td>
<td><p>bit, NOT NULL</p></td>
<td><p>Значение true, если атрибуты участника нужно обновить.</p></td>
</tr>
<tr class="even">
<td><p>Принделетед</p></td>
<td><p>bit, NOT NULL</p></td>
<td><p>Значение true, если участник удален.</p></td>
</tr>
<tr class="odd">
<td><p>Трикаунт</p></td>
<td><p>целое</p></td>
<td><p>Количество попыток обновления участника из доменных служб Active Directory, произошедших в данный момент.</p></td>
</tr>
<tr class="even">
<td><p>Ласттри</p></td>
<td><p>datetime</p></td>
<td><p>Метка времени последней попытки обновить участника. Может иметь значение null, если вы еще не пытались обновить обновление.</p></td>
</tr>
<tr class="odd">
<td><p>Нексттри</p></td>
<td><p>datetime</p></td>
<td><p>Метка времени для следующего запланированного обновления. Может иметь значение null, если дальнейшее обновление не запланировано.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Параметры

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
<td><p>Принид</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>Принид</p></td>
<td><p>Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

