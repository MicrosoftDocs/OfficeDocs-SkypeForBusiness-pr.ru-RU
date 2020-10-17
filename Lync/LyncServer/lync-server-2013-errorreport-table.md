---
title: 'Lync Server 2013: таблица ErrorReport'
description: 'Lync Server 2013: таблица ErrorReport.'
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
ms.openlocfilehash: 9c1cc65c396c16dc137255438f7ef7c32b2d0b78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572015"
---
# <a name="errorreport-table-in-lync-server-2013"></a>Таблица ErrorReport в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

В таблице ErrorReport хранятся сведения о возникших ошибках. Каждая запись соответствует одному случаю возникновения ошибки. Ошибки фиксируются агентом CDR, работающим на сервере переднего плана, или передаются клиентом.


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
<td><p><strong>Поля errortime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Дата и время возникновения ошибки.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер, идентифицирующий отчет об ошибках. Используется совместно с <strong>поля errortime</strong> для уникальной идентификации отчета об ошибках.</p></td>
</tr>
<tr class="odd">
<td><p><strong>еррорид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Уникальный идентификатор типа ошибки. Дополнительные сведения см. <a href="lync-server-2013-errordef-table.md">в таблице таблица errordef в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>фромусерид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Пользователь, создавший запрос, вызвавший ошибку. Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>таусерид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Конечный пользователь для запроса, вызвавшего ошибку. Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>конференцеуриид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Универсальный код ресурса (URI) Конференции, связанный с ошибкой. Дополнительные сведения см. <a href="lync-server-2013-conferenceuris-table.md">в таблице таблица conferenceuris в Lync Server 2013</a> . Как правило, если Конференцеуриид не имеет значение null, то либо Фромусерид, либо Таусерид будет иметь значение null.</p></td>
</tr>
<tr class="odd">
<td><p><strong>сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Правительства</p></td>
<td><p>В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор для идентификации сеанса. В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Сервер, который отправил отчет об ошибках (при отправке отчета с серверного компонента). Дополнительные сведения см. <a href="lync-server-2013-servers-table.md">в таблице Servers в Lync Server 2013</a> .</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Сервер, который отправил отчет об ошибках (при отправке отчета с серверного компонента). Дополнительные сведения приведены <a href="lync-server-2013-application-table.md">в таблице Application (приложение) в Lync Server 2013</a> .</p>
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
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Клиентская версия конечной точки, которая отправляет отчет об ошибках. Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>искаптуредбисервер</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>— Это отчет об ошибках, записанный агентом CDR, запущенным на сервере переднего плана или отправленным клиентом.</p></td>
</tr>
<tr class="even">
<td><p><strong>Флаг</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Зарезервировано для будущего использования.</p></td>
</tr>
<tr class="odd">
<td><p><strong>телеметрид</strong></p></td>
<td><p>Идентификатора</p></td>
<td></td>
<td><p>Уникальный идентификатор времени присоединения для различных компонентов, участвующих в конференции.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионсетуптиме</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Время (в миллисекундах), необходимое для присоединения к конференции определенного компонента.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Представляет полное доменное имя сервера, который создал отчет об ошибках.</p></td>
</tr>
<tr class="even">
<td><p><strong>пулид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Представляет полное доменное имя пула, в котором был создан отчет об ошибках.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

