---
title: 'Lync Server 2013: Тбладупдатес'
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
ms.openlocfilehash: 27fbbc6bb2fe68c2f4bfff91b999934069548d00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509486"
---
# <a name="tbladupdates-in-lync-server-2013"></a>Тбладупдатес в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-12_

Тбладупдатес содержит изменения доменных служб Active Directory, которые еще не были обработаны на последующих этапах синхронизации Active Directory.

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
<td><p>GUID, not null</p></td>
<td><p>Глобальный уникальный ИД измененного объекта.</p></td>
</tr>
<tr class="even">
<td><p>принадпас</p></td>
<td><p>nvarchar (384), not null</p></td>
<td><p>Различающееся имя объекта.</p></td>
</tr>
<tr class="odd">
<td><p>принаттрибутесчанжед</p></td>
<td><p>bit, not null</p></td>
<td><p>TRUE, если изменился хотя бы один атрибут объекта.</p></td>
</tr>
<tr class="even">
<td><p>принмемберсчанжед</p></td>
<td><p>bit, not null</p></td>
<td><p>TRUE, если изменилось членство.</p></td>
</tr>
<tr class="odd">
<td><p>принаффилиатионсчанжед</p></td>
<td><p>bit, not null</p></td>
<td><p>Не используется.</p></td>
</tr>
<tr class="even">
<td><p>принделетед</p></td>
<td><p>bit, not null</p></td>
<td><p>TRUE, если объект был удален.</p></td>
</tr>
<tr class="odd">
<td><p>ластупдатед</p></td>
<td><p>datetime, not null</p></td>
<td><p>Метка времени добавления строки.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

