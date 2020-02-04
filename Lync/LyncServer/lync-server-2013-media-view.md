---
title: 'Lync Server 2013: представление мультимедиа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad833bc84d488221d46822686077cfde2cda0ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a>Представление мультимедиа в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-01_

В представлении мультимедиа хранятся сведения о одном типе мультимедиа, используемом в одноранговых сеансах. Один сеанс будет представлен в таблице несколькими записями, если используется более одного типа мультимедиа. Это представление было представлено в Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> Представление мультимедиа не следует использовать для расчета длительности мультимедиа для сеанса. В этом представлении содержатся сведения о сигналах обмена мультимедийными данными в сеансе. Обмен мультимедийными данными выполняется запросом приглашения, а StartTime указывает время отправки приглашения. Время приглашения не обязательно означает время начала воспроизведения мультимедиа, так как средство мультимедиа запускается только после принятия сеанса.



</div>

В представлении мультимедиа содержатся все столбцы в [представлении сессиондетаилс в Lync Server 2013](lync-server-2013-sessiondetails-view.md) в дополнение к указанным ниже.


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
<td><p><strong>Media</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип мультимедиа. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-medialist-table.md">таблицей медиалист в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>медиастарттиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время отправки запроса мультимедиа.</p></td>
</tr>
<tr class="odd">
<td><p><strong>медиаендтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время окончания сеанса.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

