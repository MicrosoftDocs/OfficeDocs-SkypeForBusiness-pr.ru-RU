---
title: 'Lync Server 2013: представление Таблица progressreport'
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
ms.openlocfilehash: 492f7f5e34631de5ff843a00dd3fdf75b6f32f00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513226"
---
# <a name="progressreport-view-in-lync-server-2013"></a>Представление Таблица progressreport в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-01_

В представлении ProgressReport хранятся сведения о завершенных сеансах. Отчеты о ходе выполнения записываются только для тех звонков и сеансов, которые Lync Server 2013 определяет как полезные для диагностических целей. Это представление было представлено в Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> Поля ErrorTime, ErrorReportSeq и ProgressReportSeq могут относиться не к ошибкам, а к сообщениям, указывающим состояние вызовов или сообщений.



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
<td><p>Идентификационный номер ошибки. В сочетании со значением ErrorTime уникально идентифицирует ошибку.</p></td>
</tr>
<tr class="odd">
<td><p><strong>прогрессрепортсек</strong></p></td>
<td><p>int</p></td>
<td><p>Идентификатор отчета о ходе выполнения. Используется для различения отчетов о ходе выполнения в рамках одного отчета об ошибках.</p></td>
</tr>
<tr class="even">
<td><p><strong>мсдиагид</strong></p></td>
<td><p>int</p></td>
<td><p>ИД диагностики для отчета об ошибках.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Имя сервера, с которого поступило сообщение об ошибке (если отчет был отправлен серверным компонентом).</p></td>
</tr>
<tr class="even">
<td><p><strong>Приложение</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Имя приложения, в котором произошла ошибка (если отчет был отправлен компонентом сервера).</p></td>
</tr>
<tr class="odd">
<td><p><strong>телеметрид</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Уникальный идентификатор времени присоединения для различных компонентов, участвующих в конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионсетуптиме</strong></p></td>
<td><p>int</p></td>
<td><p>Время (в миллисекундах), требуемое определенному компоненту для присоединения к конференции.</p></td>
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

