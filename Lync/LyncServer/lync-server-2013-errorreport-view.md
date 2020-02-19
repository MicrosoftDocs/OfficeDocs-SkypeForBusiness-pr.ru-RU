---
title: 'Lync Server 2013: представление ErrorReport'
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
ms.openlocfilehash: a1430ab1cc00b29ed834ff078cbe70a1265a2162
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a>Представление ErrorReport в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-22_

В представлении ErrorReport сохраняется информация о возникших ошибках. Каждая запись соответствует одному случаю возникновения ошибки. Ошибки фиксируются агентом CDR, работающим на сервере переднего плана, или передаются клиентом. Это представление было представлено в Microsoft Lync Server 2013.


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
<td><p><strong>Поля errortime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время возникновения ошибки. Используется в сочетании с параметром ErrorReportSeq для уникальной идентификации ошибки.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Идентификатор ошибки. Используется в сочетании с параметром ErrorTime для уникальной идентификации ошибки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>мсдиагид</strong></p></td>
<td><p>int</p></td>
<td><p>Диагностический идентификатор для сообщения об ошибке.</p></td>
</tr>
<tr class="even">
<td><p><strong>фромури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя, инициировавшего ошибку.</p></td>
</tr>
<tr class="odd">
<td><p><strong>фромуритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип URI пользователя, отправившего ошибку. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>фромтенант</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Клиент пользователя, который поступил с ошибкой. Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>таури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя, который был целью сообщения об ошибке.</p></td>
</tr>
<tr class="even">
<td><p><strong>тауритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип URI пользователя, который был целью сообщения об ошибке. См. таблицу UriTypes для получения дополнительной информации.</p></td>
</tr>
<tr class="odd">
<td><p><strong>тотенант</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Клиент пользователя, который нацелен на отчет об ошибках. Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>конференцеури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI конференции, которая была целью сообщения об ошибке.</p></td>
</tr>
<tr class="odd">
<td><p><strong>конференцеуритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип URI конференции, которая была целью отчета об ошибках. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время запроса сеанса, созданного отчетом об ошибках. Используется вместе с параметром SessionIdSeq для уникального определения сеанса. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации запроса сеанса, созданного отчетом об ошибках. Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>варстринг (775)</p></td>
<td><p>Диалоговый идентификатор SIP сеанса, инициировавшего ошибку. Используется следующий формат:</p>
<p>диалоговое окно; from — Tag; to – Tag</p>
<p>Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</p>
<p>cast(cast(ExternalId as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Версии клиента, используемого пользователем, инициировавшим ошибку.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Клиент, используемый пользователем, который поступил с ошибкой. Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>клиенткатегори</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Имя категории клиента, используемого пользователем, инициировавшим ошибку.</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Имя сервера, с которого поступило сообщение об ошибке (если отчет был отправлен серверным компонентом).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Приложение</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Имя приложения, инициировавшего ошибку (если отчет был отправлен серверным компонентом).</p></td>
</tr>
<tr class="even">
<td><p><strong>респонсекоде</strong></p></td>
<td><p>int</p></td>
<td><p>Код ответа SIP на сеанс SIP-сообщения, содержащего отчет об ошибках.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Тип запроса с отказом.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Тип содержимого запроса с отказом.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип сеанса. Дополнительные сведения см. <a href="lync-server-2013-calltype-table.md">в таблице CallType в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>телеметрид</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Уникальный идентификатор времени присоединения для различных компонентов, участвующих в конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>сетуптиме</strong></p></td>
<td><p>int</p></td>
<td><p>Время (в миллисекундах), необходимое для присоединения к конференции определенного компонента.</p></td>
</tr>
<tr class="even">
<td><p><strong>искаптуредбисервер</strong></p></td>
<td><p>Битовая</p></td>
<td><p>Указывает, был ли данный отчет об ошибках получен агентом CDR, работающим на сервере переднего плана, или отправлен клиентом.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Флаг</strong></p></td>
<td><p>smallint</p></td>
<td><p>Зарезервировано для будущего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>мсдиагхеадер</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Дополнительные сведения об ошибке.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Интерфейса</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>Полное доменное имя сервера переднего плана, который отправил отчет.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ресурсов</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>Полное доменное имя пула, содержащего сервер переднего плана, который отправил отчет.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

