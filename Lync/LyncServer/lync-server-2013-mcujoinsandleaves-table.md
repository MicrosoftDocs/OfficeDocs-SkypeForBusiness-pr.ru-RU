---
title: 'Lync Server 2013: таблица McuJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 204906deb88a2067b7304088515b25fee2da0350
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a>Таблица McuJoinsAndLeaves в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

Каждая запись в этой таблице включает сведения о звонках для одной комбинации присоединения или выхода из нее и сервера конференций. Например, если пользователь присоединяется к Конференции, которая включает веб-конференции и звуковые и видеоэлементы, для подключения к веб-конференции пользователя будет создана одна запись, а для голосовых и видеоконференций пользователя будет создана другая запись.


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
<th>Ключ/индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Время экземпляра Конференции. Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации экземпляра Конференции. Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Основной, внешний</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации экземпляра Конференции. Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции. Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Идентификатора пользователя</strong></p></td>
<td><p>целое</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Уникальный номер, идентифицирующий этого пользователя. Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>мкуусеринстанце</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Если пользователь входит в систему на нескольких компьютерах или устройствах одновременно, Мкуусеринстанце однозначно определяет сочетание пользователей и устройств.</p></td>
</tr>
<tr class="odd">
<td><p><strong>исфромпстн</strong></p></td>
<td><p>бит</p></td>
<td><p> </p></td>
<td><p>Присоединение пользователя к сети PSTN или нет.</p></td>
</tr>
<tr class="even">
<td><p><strong>мкуид</strong></p></td>
<td><p>целое</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Уникальный номер, идентифицирующий этот сервер конференц-связи. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-mcus-table.md">таблицей мкус в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>диалогсессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Другом</p></td>
<td><p>Время запроса сеанса. Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>диалогсессионидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации сеанса. Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>усержоинтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Время присоединения пользователя к этому серверу конференций.</p></td>
</tr>
<tr class="even">
<td><p><strong>усерлеаветиме</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Время, когда этот пользователь покидает этот сервер конференц-связи.</p></td>
</tr>
<tr class="odd">
<td><p><strong>клиентверид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Идентификатор, указывающий номер версии клиентского программного обеспечения, используемого на Конференции. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-clientversions-table.md">таблицей клиентверсионс в Lync Server 2013</a> .</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

