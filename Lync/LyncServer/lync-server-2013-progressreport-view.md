---
title: 'Lync Server 2013: представление Прогрессрепорт'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa8d73981490503b26b77b79be6f42aab77703e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a>Прогрессрепорт представления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-01_

В представлении Прогрессрепорт хранятся сведения о завершенных сеансах. Отчеты о ходе выполнения будут записываться только для звонков и сеансов, которые определяет Lync Server 2013, может быть полезен в целях диагностики. Это представление было представлено в Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> Поля Еррортиме, Ерроррепортсек и Прогрессрепортсек не обязательно ссылаются на ошибки, а также на сообщения, указывающие на состояние вызовов или сообщений.



</div>


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
<td><p><strong>прогрессрепортсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Идентификатор для идентификации отчета о ходе выполнения. Используется, чтобы отличать отчеты о ходе выполнения одного отчета об ошибках.</p></td>
</tr>
<tr class="even">
<td><p><strong>мсдиагид</strong></p></td>
<td><p>целое</p></td>
<td><p>Идентификатор диагностики для отчета об ошибке.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Источник</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя сервера, отправившего ошибку (при отправке отчета из серверного компонента).</p></td>
</tr>
<tr class="even">
<td><p><strong>Приложение</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя приложения, которое поступило об ошибке (при отправке отчета из серверного компонента).</p></td>
</tr>
<tr class="odd">
<td><p><strong>телеметрид</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Уникальный идентификатор, соответствующий сведениям о времени соединения для различных компонентов, участвующих в Конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионсетуптиме</strong></p></td>
<td><p>целое</p></td>
<td><p>Время (в миллисекундах), требуемое конкретным компонентом для присоединения к Конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>мсдиагхеадер</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Дополнительные сведения об ошибке.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

