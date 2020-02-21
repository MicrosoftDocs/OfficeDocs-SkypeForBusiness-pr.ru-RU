---
title: 'Lync Server 2013: представление конференций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f01d7fb0a2cb0526d4d6954b303a7cf78bb9333
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a>Представление конференций в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-01_

В представлении конференций хранятся сведения о конференциях. Это представление было представлено в Microsoft Lync Server 2013.


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
<td><p><strong>сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время запроса сеанса. Используется вместе с параметром SessionIdSeq для уникального определения сеанса. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Идентификационный номер для идентификации сеанса. Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>конференцеури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>конференцеуритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип URI конференции. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>конфинстанце</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Используется для повторяющихся конференций. Все экземпляры повторяющейся конференции имеют один и тот же ConferenceUri, но разные значения ConfInstance.</p></td>
</tr>
<tr class="even">
<td><p><strong>конференцестарттиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время начала конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>конференцеендтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время окончания конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>организерури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя, организовавшего конференцию.</p></td>
</tr>
<tr class="odd">
<td><p><strong>организертипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип URI пользователя, организовавшего конференцию. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>организертенант</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Клиент пользователя, организовавшего конференцию. Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ресурсов</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Полное доменное имя пула, в котором размещена конференция.</p></td>
</tr>
<tr class="even">
<td><p><strong>Флаг</strong></p></td>
<td><p>smallint</p></td>
<td><p>Битовая маска, содержащая атрибуты конференции. Возможные значения:</p>
<p>0X01 – искусственная транзакция</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

