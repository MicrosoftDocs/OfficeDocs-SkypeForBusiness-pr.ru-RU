---
title: 'Lync Server 2013: представление Таблица mcujoinsandleaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4f3f73606cfd05df17022770da7dcd1f5266b21
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a>Представление Таблица mcujoinsandleaves в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-01_

В представлении McuJoinsAndLeaves хранится информация о присоединении и выходе пользователей для одного сервера конференций. Каждая запись в этом представлении содержит сведения о звонке, сочетающие в себе данные о присоединении или отключении пользователя и сервере конференций. Это представление было представлено в Microsoft Lync Server 2013.


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
<td><p><strong>мкуури</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URI сервера конференций, к которому подключился пользователь.</p></td>
</tr>
<tr class="even">
<td><p><strong>мкууритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URI сервера конференций, к которому подключился пользователь. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</p></td>
</tr>
<tr class="even">
<td><p><strong>усеруритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип URI пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>усертенант</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Клиент пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны. Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>усерклиентверсион</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Версия клиента пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</p></td>
</tr>
<tr class="odd">
<td><p><strong>усерклиенттипе</strong></p></td>
<td><p>int</p></td>
<td><p>Версия клиента пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны. Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>усерклиенткатегори</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Имя категории пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</p></td>
</tr>
<tr class="odd">
<td><p><strong>мкуусеринстанце</strong></p></td>
<td><p>int</p></td>
<td><p>Уникально определяет комбинацию пользователя и устройства для пользователей, одновременно вошедших на несколько устройств.</p></td>
</tr>
<tr class="even">
<td><p><strong>исусерфромпстн</strong></p></td>
<td><p>Битовая</p></td>
<td><p>Разряд, указывающий, является ли пользователь внутренним.</p></td>
</tr>
<tr class="odd">
<td><p><strong>диалогсессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время запроса сеанса. Используется вместе с параметром SessionIdSeq для уникального определения сеанса. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>диалогсессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Идентификационный номер для идентификации сеанса. Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>Код диалога SIP этого сеанса. Формат: диалог;начальный тег;конечный тег.</p></td>
</tr>
<tr class="even">
<td><p><strong>усержоинтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время, когда пользователь присоединился к серверу конференций.</p></td>
</tr>
<tr class="odd">
<td><p><strong>усерлеаветиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время, когда пользователь вышел с сервера конференций.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

