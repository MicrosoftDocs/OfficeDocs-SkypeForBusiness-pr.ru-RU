---
title: 'Lync Server 2013: tblADUpdates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb4b5b73fb74c2337eeaa6b065396253a2cb0be4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a>tblADUpdates в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-12_

Тбладупдатес содержит изменения доменных служб Active Directory, которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory.

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
<td><p>прингуид</p></td>
<td><p>GUID, а не NULL</p></td>
<td><p>Идентификатор GUID участника измененного объекта.</p></td>
</tr>
<tr class="even">
<td><p>принадпас</p></td>
<td><p>nvarchar (384), NOT NULL</p></td>
<td><p>Отличительное имя объекта.</p></td>
</tr>
<tr class="odd">
<td><p>принаттрибутесчанжед</p></td>
<td><p>bit, NOT NULL</p></td>
<td><p>Значение true, если по крайней мере один из атрибутов объекта изменился.</p></td>
</tr>
<tr class="even">
<td><p>принмемберсчанжед</p></td>
<td><p>bit, NOT NULL</p></td>
<td><p>Значение true, если изменилось членство.</p></td>
</tr>
<tr class="odd">
<td><p>принаффилиатионсчанжед</p></td>
<td><p>bit, NOT NULL</p></td>
<td><p>Не используется.</p></td>
</tr>
<tr class="even">
<td><p>принделетед</p></td>
<td><p>bit, NOT NULL</p></td>
<td><p>Значение true, если объект был удален.</p></td>
</tr>
<tr class="odd">
<td><p>ластупдатед</p></td>
<td><p>DateTime, NOT NULL</p></td>
<td><p>Метка времени вставки строки.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

