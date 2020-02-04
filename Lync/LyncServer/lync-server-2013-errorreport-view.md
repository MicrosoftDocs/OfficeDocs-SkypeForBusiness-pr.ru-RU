---
title: 'Lync Server 2013: представление Ерроррепорт'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a72b2f12c00248095b99198182b8c71bb945bfa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a>Ерроррепорт представления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-01-22_

В представлении Ерроррепорт хранятся сведения об ошибках, о которых сообщается. Каждая запись содержит один экземпляр ошибки. Эти ошибки регистрируются агентом CDR, который запущен на сервере переднего плана или отправлен клиентом. Это представление было представлено в Microsoft Lync Server 2013.


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
<td><p><strong>еррортиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время возникновения ошибки. Используется в сочетании с Ерроррепортсек для уникальной идентификации ошибки.</p></td>
</tr>
<tr class="even">
<td><p><strong>ерроррепортсек</strong></p></td>
<td><p>целое</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации ошибки. Используется в сочетании с Еррортиме для уникальной идентификации ошибки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>мсдиагид</strong></p></td>
<td><p>целое</p></td>
<td><p>Идентификатор диагностики для отчета об ошибке.</p></td>
</tr>
<tr class="even">
<td><p><strong>фромури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя, который поступил с ошибкой.</p></td>
</tr>
<tr class="odd">
<td><p><strong>фромуритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя, который поступил на ошибку. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>фромтенант</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент пользователя, который поступил с ошибкой. Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>таури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) пользователя, который является целью отчета об ошибке.</p></td>
</tr>
<tr class="even">
<td><p><strong>тауритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя, который является конечным лицом отчета об ошибке. Для получения дополнительных сведений ознакомьтесь с таблицей Уритипес.</p></td>
</tr>
<tr class="odd">
<td><p><strong>тотенант</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент пользователя, который является конечным лицом отчета об ошибке. Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) Конференции, которая была целью отчета об ошибке.</p></td>
</tr>
<tr class="odd">
<td><p><strong>конференцеуритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI конференции, которая была целью отчета об ошибке. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время запроса сеанса, в котором был создан отчет об ошибке. Используется в сочетании с Сессионидсек для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации запроса на сеанс, который является источником отчета об ошибке. Используется в сочетании с Сессионидтиме для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>диалогид</strong></p></td>
<td><p>варстринг (775)</p></td>
<td><p>ИДЕНТИФИКАТОР диалогового окна SIP сеанса, на который поступила ошибка. Формат:</p>
<p>диалоговое окно; тег "from-Tag"</p>
<p>Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</p>
<p>Cast (CAST (Екстерналид AS varbinary (max)) AS varchar (max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>клиентверсион</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Версия клиента, используемая пользователем, который поступил с ошибкой.</p></td>
</tr>
<tr class="even">
<td><p><strong>клиенттипе</strong></p></td>
<td><p>целое</p></td>
<td><p>Клиент, использованный пользователем, который поступил с ошибкой. Дополнительные сведения вы увидите <a href="lync-server-2013-useragentdef-table.md">в таблице усеражентдеф в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>клиенткатегори</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Имя категории клиента, используемой пользователем, который поступил с ошибкой.</p></td>
</tr>
<tr class="even">
<td><p><strong>Источник</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя сервера, отправившего ошибку (при отправке отчета из серверного компонента).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Приложение</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя приложения, которое поступило об ошибке (при отправке отчета из серверного компонента).</p></td>
</tr>
<tr class="even">
<td><p><strong>респонсекоде</strong></p></td>
<td><p>целое</p></td>
<td><p>Код ответа SIP в сеанс сообщения SIP с отчетом об ошибке.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Тип запроса, который завершился сбоем.</p></td>
</tr>
<tr class="even">
<td><p><strong>Контента</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Тип контента запроса, который завершился сбоем.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип сеанса. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-calltype-table.md">таблицей каллтипе в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>телеметрид</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Уникальный идентификатор, соответствующий сведениям о времени соединения для различных компонентов, участвующих в Конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>сетуптиме</strong></p></td>
<td><p>целое</p></td>
<td><p>Время (в миллисекундах), требуемое конкретным компонентом для присоединения к Конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>искаптуредбисервер</strong></p></td>
<td><p>бит</p></td>
<td><p>Указывает, был ли отчет об ошибке записан агентом CDR, запущенным на сервере переднего плана или отправлен клиентом.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Пометка</strong></p></td>
<td><p>smallint</p></td>
<td><p>Зарезервировано для будущего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>мсдиагхеадер</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Дополнительные сведения об ошибке.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>Полное доменное имя сервера переднего плана, отправившего отчет.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>Полное доменное имя пула, содержащего сервер переднего плана, отправивший отчет.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

