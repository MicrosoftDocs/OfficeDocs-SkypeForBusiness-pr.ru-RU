---
title: 'Lync Server 2013: представление Прогрессрепорт'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 423d99211a89ef328bc62aca89a9b65141e128ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823597"
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
<td><p><strong>Еррортиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время возникновения ошибки. Используется в сочетании с Ерроррепортсек для уникальной идентификации ошибки.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ерроррепортсек</strong></p></td>
<td><p>целое</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации ошибки. Используется в сочетании с Еррортиме для уникальной идентификации ошибки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Прогрессрепортсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Идентификатор для идентификации отчета о ходе выполнения. Используется, чтобы отличать отчеты о ходе выполнения одного отчета об ошибках.</p></td>
</tr>
<tr class="even">
<td><p><strong>Мсдиагид</strong></p></td>
<td><p>целое</p></td>
<td><p>Идентификатор диагностики для отчета об ошибке.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Источник</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя сервера, отправившего ошибку (при отправке отчета из серверного компонента).</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя приложения, которое поступило об ошибке (при отправке отчета из серверного компонента).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Телеметрид</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Уникальный идентификатор, соответствующий сведениям о времени соединения для различных компонентов, участвующих в Конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Сессионсетуптиме</strong></p></td>
<td><p>целое</p></td>
<td><p>Время (в миллисекундах), требуемое конкретным компонентом для присоединения к Конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Мсдиагхеадер</strong></p></td>
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

