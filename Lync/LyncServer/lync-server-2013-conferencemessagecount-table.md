---
title: 'Lync Server 2013: таблица ConferenceMessageCount'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d2994f02bf087ef55edff6b2153e7504f881b03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a>Таблица ConferenceMessageCount в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

Каждая запись в этой таблице представляет одного пользователя в одной конференции для обмена мгновенными сообщениями и включает количество сообщений, отправленных этим пользователем. Каждая конференция представлена в этой таблице несколькими записями; одна запись для каждого пользователя.


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
<td><p><strong>Сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Время экземпляра Конференции. Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации экземпляра Конференции. Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Сессионидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Основной, внешний</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации экземпляра Конференции. Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции. Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Идентификатора пользователя</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Уникальный номер, идентифицирующий этого пользователя, на который ссылается <a href="lync-server-2013-users-table.md">Таблица "Пользователи" в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Мессажекаунт</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>Количество сообщений, отправленных этим пользователем во время данной Конференции.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

