---
title: 'Lync Server 2013: таблица таблица focusjoinsandleaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f7691a008dae1fc822b6632a60f5324bb4e80fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500836"
---
# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a>Таблица Таблица focusjoinsandleaves в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Каждая запись в этой таблице содержит сведения о CDR для одного пользователя и оставляют информацию для одной конференции. Каждая конференция представлена в этой таблице по одной записи на каждый раз, когда пользователь присоединяется к Конференции и покидает ее.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Ключ или индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Время экземпляра конференции. Используется совместно с <strong>сессионидсек</strong> для уникальной идентификации экземпляра Конференции. Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Основной, Внешний</p></td>
<td><p>Идентификатор для определения экземпляра конференции. Используется совместно с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции. Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>диалогсессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Время запроса сеанса. В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>диалогсессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Идентификатор для идентификации сеанса. В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Уникальный номер, идентифицирующий этого пользователя, на который ссылается <a href="lync-server-2013-users-table.md">таблица Users в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>фокусусеринстанце</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Если пользователь вошел в систему на нескольких компьютерах или устройствах одновременно, <strong>усеринстанце</strong> используется для уникальной идентификации комбинации "пользователь-устройство".</p></td>
</tr>
<tr class="odd">
<td><p><strong>исусеринтернал</strong></p></td>
<td><p>Битовая</p></td>
<td><p> </p></td>
<td><p>Указывает, вошел ли пользователь из внутренней сети или нет.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserRole</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Роль этого пользователя в конференции, например докладчик или участник.</p></td>
</tr>
<tr class="odd">
<td><p><strong>усержоинтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Время, когда этот пользователь присоединяется к Конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>усерлеаветиме</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Время, когда этот пользователь покидает Конференцию.</p></td>
</tr>
<tr class="odd">
<td><p><strong>клиентверид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Версия клиентского программного обеспечения пользователя, на которую ссылается <a href="lync-server-2013-clientversions-table.md">таблица таблица clientversions в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>усерендпоинтид</strong></p></td>
<td><p>Идентификатора</p></td>
<td></td>
<td><p>Глобальный уникальный идентификатор (GUID) конечной точки, используемой в Конференции.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

