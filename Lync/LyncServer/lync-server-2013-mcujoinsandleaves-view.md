---
title: 'Lync Server 2013: представление Мкужоинсандлеавес'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7592879a1c6c6cc6bbcac54fd843046b69acee83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a>Мкужоинсандлеавес представления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-01_

В представлении Мкужоинсандлеавес хранятся сведения о присоединениях и выходе пользователей на один сервер конференции. Каждая запись в этом представлении включает в себя сведения о звонках для одной комбинации присоединения пользователя или выхода из него и сервера конференц-связи. Это представление было представлено в Microsoft Lync Server 2013.


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
<td><p><strong>Сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время экземпляра Конференции. Используется в сочетании с Сессионидсек для уникальной идентификации экземпляра Конференции. Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Сессионидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации экземпляра Конференции. Используется в сочетании с Сессионидтиме для уникальной идентификации экземпляра Конференции. Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Мкуури</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Универсальный код ресурса (URI) сервера конференций, к которому подключен пользователь.</p></td>
</tr>
<tr class="even">
<td><p><strong>Мкууритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Универсальный код ресурса (URI) сервера конференций, к которому подключен пользователь. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Усерури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) пользователя, которому были собраны сведения о присоединении или выходе сервера конференций.</p></td>
</tr>
<tr class="even">
<td><p><strong>Усеруритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип универсального кода ресурса (URI), к которому были собраны сведения о присоединении или выходе сервера конференций. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Усертенант</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент пользователя, которому были собраны сведения о присоединении или выходе сервера конференций. Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Усерклиентверсион</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Версия клиента, используемая пользователем, для которого была собрана информация о присоединении или выходе сервера конференций.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Усерклиенттипе</strong></p></td>
<td><p>целое</p></td>
<td><p>Клиент, который использовался пользователем, которому присвоены данные для присоединения или выхода на сервер конференц-связи. Дополнительные сведения вы увидите <a href="lync-server-2013-useragentdef-table.md">в таблице усеражентдеф в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Усерклиенткатегори</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Название категории клиента, используемой пользователем, для которого была получена информация о приходе и выходе сервера конференций.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Мкуусеринстанце</strong></p></td>
<td><p>целое</p></td>
<td><p>Уникально определяет сочетание пользователей и устройств для пользователей, одновременно выполнивших вход на несколько устройств.</p></td>
</tr>
<tr class="even">
<td><p><strong>Исусерфромпстн</strong></p></td>
<td><p>бит</p></td>
<td><p>Бит, обозначающий, является ли пользователь внутренним.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Диалогсессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время запроса сеанса. Используется в сочетании с Сессионидсек для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Диалогсессионидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации сеанса. Используется в сочетании с Сессионидтиме для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Диалогид</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>ИДЕНТИФИКАТОР диалогового окна SIP для сеанса. Формат: диалоговое окно; тег.</p></td>
</tr>
<tr class="even">
<td><p><strong>Усержоинтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время присоединения пользователя к серверу конференц-связи.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Усерлеаветиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время, когда пользователь оставил сервер конференц-связи.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

