---
title: 'Lync Server 2013: таблица ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8de4163f94d5848808c5b01c34b1676d3a0bbcff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a>Таблица ErrorReport в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

В таблице Ерроррепорт хранятся сведения о возникших ошибках. Каждая запись содержит один экземпляр ошибки. Эти ошибки регистрируются агентом CDR, который запущен на сервере переднего плана или отправлен клиентом.


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
<td><p><strong>еррортиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Дата и время, когда возникла ошибка.</p></td>
</tr>
<tr class="even">
<td><p><strong>ерроррепортсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации отчета об ошибке. Используется в сочетании с <strong>еррортиме</strong> для уникальной идентификации отчета об ошибке.</p></td>
</tr>
<tr class="odd">
<td><p><strong>еррорид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Уникальный идентификатор типа ошибки. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-errordef-table.md">таблицей еррордеф в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>фромусерид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Пользователь, который поступил на этот запрос, вызвавший ошибку. Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>таусерид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Конечный пользователь для запроса, вызвавшего ошибку. Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>конференцеуриид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Универсальный код ресурса (URI) для Конференции, связанный с ошибкой. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-conferenceuris-table.md">таблицей конференцеурис в Lync Server 2013</a> . Как правило, если Конференцеуриид не имеет значение null, то либо Фромусерид, либо Таусерид будет NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Другом</p></td>
<td><p>Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации сеанса. Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Источника</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Сервер, отправивший отчет об ошибке (при отправке отчета из серверного компонента). Более подробную информацию вы видите <a href="lync-server-2013-servers-table.md">в таблице Servers (серверы) в Lync Server 2013</a> .</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Сервер, отправивший отчет об ошибке (при отправке отчета из серверного компонента). Дополнительные сведения приведены <a href="lync-server-2013-application-table.md">в таблице приложение Lync Server 2013</a> .</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>мсдиагхеадер</strong></p></td>
<td><p>изображение</p></td>
<td><p> </p></td>
<td><p>Дополнительные сведения об ошибке.</p>
<p>Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><strong>клиентверсионид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Клиентская версия конечной точки, отправляющей отчет об ошибке. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-clientversions-table.md">таблицей клиентверсионс в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>искаптуредбисервер</strong></p></td>
<td><p>бит</p></td>
<td></td>
<td><p>Отчет об ошибке, записанный агентом CDR, который запущен на сервере переднего плана или отправляется клиентом.</p></td>
</tr>
<tr class="even">
<td><p><strong>Пометка</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Зарезервировано для будущего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>телеметрид</strong></p></td>
<td><p>Идентификатора</p></td>
<td></td>
<td><p>Уникальный идентификатор, соответствующий сведениям о времени соединения для различных компонентов, участвующих в Конференции.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионсетуптиме</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Время (в миллисекундах), требуемое конкретным компонентом для присоединения к Конференции.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>серверид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Представляет полное доменное имя сервера, который сгенерировал отчет об ошибке.</p></td>
</tr>
<tr class="even">
<td><p><strong>пулид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Представляет полное доменное имя пула, в котором был создан отчет об ошибке.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

