---
title: 'Lync Server 2013: таблица ProgressReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa8ca0341cd5b85418ef5f71234870ae4171af27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a>Таблица ProgressReport в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

Отчеты о состоянии основываются на данных, отправленных клиентом в базу данных после завершения вызова или сеанса. Отчеты о ходе выполнения будут записываться только для звонков и сеансов, которые определяет Lync Server 2013, может быть полезен в целях диагностики.

Поля Еррортиме, Ерроррепортсек и Прогрессрепортсек не обязательно ссылаются на ошибки, а также на сообщения, указывающие на состояние вызовов или сообщений.


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
<td><p><strong>Еррортиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Дата и время отчета об ошибках хода выполнения, который включает этот отчет о ходе выполнения. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-errorreport-table.md">таблицей ерроррепорт в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Еррорид</strong></p></td>
<td><p>целое</p></td>
<td><p>Основной, внешний</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер, используемый в сочетании с Еррортиме, Прогрессрепортсек для уникальной идентификации отчета о ходе выполнения. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-errorreport-table.md">таблицей ерроррепорт в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ерроррепортсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Основной, внешний</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер, идентифицирующий отчет об ошибке. Ерроррепорсек используется в сочетании с Еррортиме для уникальной идентификации отчета об ошибке. Дополнительные сведения приведены <a href="lync-server-2013-errorreport-table.md">в таблице ерроррепорт в Lync Server 2013</a></p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Прогрессрепортсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации отчета о ходе выполнения. Используется совместно с Еррортиме и Ерроррепортсек для уникальной идентификации отчета о ходе выполнения.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Мсдиагид</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Идентификатор диагностики отчета о ходе выполнения.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Источника</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Сервер, отправивший отчет об ошибке (при отправке отчета из серверного компонента). Более подробную информацию вы видите <a href="lync-server-2013-servers-table.md">в таблице Servers (серверы) в Lync Server 2013</a> . Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Процесс Lync Server, к которому относится отчет. Для получения дополнительных сведений ознакомьтесь с таблицей Application.</p></td>
</tr>
<tr class="even">
<td><p><strong>Подробности</strong></p></td>
<td><p>изображение</p></td>
<td></td>
<td><p>Сведения о отчете о состоянии, сохраняемые в двоичном формате для экономии места. Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</p>
<p>Cast (CAST (данные в формате varbinary (max)) AS varchar (max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>Телеметрид</strong></p></td>
<td><p>Идентификатора</p></td>
<td></td>
<td><p>Уникальный идентификатор, который соответствует сведениям о времени соединения для различных компонентов, участвующих в Конференции.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Сессионсетуптиме</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Время (в миллисекундах), в течение которого конкретный компонент присоединяется к Конференции.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

