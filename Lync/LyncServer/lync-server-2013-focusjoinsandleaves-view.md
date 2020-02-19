---
title: 'Lync Server 2013: представление Таблица focusjoinsandleaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85e13c744ed92dcbcb70b2da851b915e8c6f8104
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a>Представление Таблица focusjoinsandleaves в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-01_

В представлении FocusJoinsAndLeaves хранятся данные о подключении и отключении от отдельной конференции. Каждая конференции продемонстрирована на этом представлении отдельной записью, которая создается при каждом подключении и отключении пользователя от этой конференции. Это представление было представлено в Microsoft Lync Server 2013.


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
<td><p>Время экземпляра конференции. Используется вместе с параметром SessionIdSeq для уникального определения экземпляра конференции. Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Идентификатор для определения экземпляра конференции. Используется вместе с параметром SessionIdTime для уникального определения экземпляра конференции. Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя, для которого получены данные о подключении или отключении от конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>усеруритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип URI пользователя, для которого получены данные о подключении или отключении от конференции. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>усертенант</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Клиент пользователя, для которого получены данные о подключении или отключении от конференции. Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>усерендпоинтид</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Уникальный идентификатор пользователя, для которого получены данные о подключении или отключении от конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>усерклиентверсион</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Версия клиента, используемая пользователем, для которого получены данные о подключении или отключении от конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>усерклиенттипе</strong></p></td>
<td><p>int</p></td>
<td><p>Клиент, используемый пользователем, для которого получены данные о подключении или отключении от конференции. Более подробную информацию можно узнать <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>усерклиенткатегори</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Имя категории клиента, используемой пользователем, для которого получены данные о подключении или отключении от конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>фокусусеринстанце</strong></p></td>
<td><p>int</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><strong>исусеринтернал</strong></p></td>
<td><p>Битовая</p></td>
<td><p>Разряд, указывающий, является ли пользователь внутренним.</p></td>
</tr>
<tr class="even">
<td><p><strong>диалогсессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время запроса сеанса. Используется вместе с параметром SessionIdSeq для уникального определения сеанса. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>диалогсессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Если пользователь выполнил вход одновременно на несколько компьютеров или устройств, параметр UserInstance используется для уникальной идентификации комбинации пользователя и устройства.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>Код диалога SIP этого сеанса. Формат: диалог;начальный тег;конечный тег.</p></td>
</tr>
<tr class="odd">
<td><p><strong>усержоинтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время подключения пользователя к конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>усерлеаветиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время отключения пользователя от конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserRole</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Роль пользователя в конференции (например, докладчик или участник).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

