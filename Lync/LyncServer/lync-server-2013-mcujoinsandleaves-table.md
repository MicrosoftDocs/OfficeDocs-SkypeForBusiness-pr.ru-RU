---
title: 'Lync Server 2013: таблица таблица mcujoinsandleaves'
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
ms.openlocfilehash: f4aa5fb14ff16d13b1cdff72f15c648f9e353922
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524736"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a>Таблица Таблица mcujoinsandleaves в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Каждая запись в этой таблице содержит сведения о вызовах для одной комбинации присоединения или выхода пользователя и сервера конференц-связи. Например, если пользователь присоединяется к Конференции, которая включает веб-конференции и аудио-и видеоэлементы, будет создана одна запись для соединения веб-конференций этого пользователя, а для подключения аудио-и видеоконференций пользователя будет создана другая запись.


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
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Основной, Внешний</p></td>
<td><p>Уникальный номер, идентифицирующий данного пользователя. Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>мкуусеринстанце</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Если пользователь вошел в систему на нескольких компьютерах или устройствах одновременно, Мкуусеринстанце уникально идентифицирует сочетание "пользователь-устройство".</p></td>
</tr>
<tr class="odd">
<td><p><strong>исфромпстн</strong></p></td>
<td><p>Битовая</p></td>
<td><p> </p></td>
<td><p>Присоединение пользователя к сети PSTN или нет.</p></td>
</tr>
<tr class="even">
<td><p><strong>мкуид</strong></p></td>
<td><p>int</p></td>
<td><p>Основной, Внешний</p></td>
<td><p>Уникальный номер, идентифицирующий этот сервер конференц-связи. Дополнительные сведения см. <a href="lync-server-2013-mcus-table.md">в таблице MCUs в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>диалогсессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Правительства</p></td>
<td><p>Время запроса сеанса. В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>диалогсессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор для идентификации сеанса. В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>усержоинтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Время, когда этот пользователь присоединяется к этому серверу конференций.</p></td>
</tr>
<tr class="even">
<td><p><strong>усерлеаветиме</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Время, когда этот пользователь покидает этот сервер конференц-связи.</p></td>
</tr>
<tr class="odd">
<td><p><strong>клиентверид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор, указывающий номер версии клиентского программного обеспечения, используемого в Конференции. Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

