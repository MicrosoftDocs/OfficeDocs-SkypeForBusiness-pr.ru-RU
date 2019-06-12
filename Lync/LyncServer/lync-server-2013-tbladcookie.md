---
title: 'Lync Server 2013: tblADCookie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eef65e18de609f7e10fed4aaad9283612778070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a>tblADCookie в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-06-25_

Тбладкукие включает в себя текущие cookie-файлы для синхронизации протокола Lightweight Directory Access.

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
<td><p>Прингуид</p></td>
<td><p>GUID, а не NULL</p></td>
<td><p>Идентификатор GUID участника отслеживаемого домена.</p></td>
</tr>
<tr class="even">
<td><p>Приндчост</p></td>
<td><p>nvarchar (255)</p></td>
<td><p>Полное доменное имя (FQDN) текущего контроллера домена, используемого для синхронизации доменных служб Active Directory. Имеет информационное значение.</p></td>
</tr>
<tr class="odd">
<td><p>Адкконтент</p></td>
<td><p>изображение (двоичное)</p></td>
<td><p>Cookie синхронизации Active Directory.</p></td>
</tr>
<tr class="even">
<td><p>Ластупдатед</p></td>
<td><p>datetime</p></td>
<td><p>Метка времени со временем обновления строки.</p></td>
</tr>
<tr class="odd">
<td><p>Локкедунтил</p></td>
<td><p>datetime</p></td>
<td><p>Время, по истечении которого изменения строки будут заблокированы. Это является частью механизма программного обеспечения, который гарантирует, что только одна из служб чата выполняет синхронизацию службы каталогов Active Directory за один раз.</p></td>
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
<th>Столбцы (-ы)</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Прингуид</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>Прингуид</p></td>
<td><p>Внешний ключ с подстановкой в таблице Principal. Прингуид.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

