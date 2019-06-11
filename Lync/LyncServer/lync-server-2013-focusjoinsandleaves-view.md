---
title: 'Lync Server 2013: представление Фокусжоинсандлеавес'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e1302bf744b0954d00eae4f4cc27454b2889745
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a>Фокусжоинсандлеавес представления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-01_

В представлении Фокусжоинсандлеавес хранятся сведения о присоединениях и оставлении данных для одной конференции. Каждое собрание представлено в этом представлении записью, которая записывается каждый раз, когда пользователь присоединяется к Конференции, и оставляет ее. Это представление было представлено в Microsoft Lync Server 2013.


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
<td><p><strong>Усерури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI), на который были собраны сведения о присоединении или закрытии Конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Усеруритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип универсального кода ресурса (URI), на который были собраны сведения о приходе или закрытии Конференции. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Усертенант</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент для пользователя, которому были собраны сведения о присоединении к Конференции или выходе из нее. Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Усерендпоинтид</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Уникальный идентификатор пользователя, для которого была собрана информация о присоединении к Конференции или выходе из нее.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Усерклиентверсион</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Версия клиента, используемая пользователем, для которого была собрана информация о присоединении к Конференции или выходе из нее.</p></td>
</tr>
<tr class="even">
<td><p><strong>Усерклиенттипе</strong></p></td>
<td><p>целое</p></td>
<td><p>Клиент, используемый пользователем, для которого были собраны сведения о присоединении к Конференции или выходе из нее. Для получения дополнительных сведений ознакомьтесь <a href="lync-server-2013-useragentdef-table.md">с таблицей усеражентдеф в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Усерклиенткатегори</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Имя категории клиента, используемой пользователем, для которого были собраны сведения о приходе или закрытии Конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Фокусусеринстанце</strong></p></td>
<td><p>целое</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><strong>Исусеринтернал</strong></p></td>
<td><p>бит</p></td>
<td><p>Бит, обозначающий, является ли пользователь внутренним.</p></td>
</tr>
<tr class="even">
<td><p><strong>Диалогсессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время запроса сеанса. Используется в сочетании с Сессионидсек для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Диалогсессионидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Если пользователь входит в систему на нескольких компьютерах или устройствах одновременно, Усеринстанце используется для уникальной идентификации комбинации пользователей и устройств.</p></td>
</tr>
<tr class="even">
<td><p><strong>Диалогид</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>ИДЕНТИФИКАТОР диалогового окна SIP для сеанса. Формат: диалоговое окно; тег.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Усержоинтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время, в которое пользователь присоединился к Конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Усерлеаветиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время, когда пользователь оставил Конференцию.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserRole</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Роль пользователя на Конференции, например докладчика или участника.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

