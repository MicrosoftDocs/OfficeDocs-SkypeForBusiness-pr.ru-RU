---
title: Настройка регистрации вызовов и параметров качества взаимодействия
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 504c2221e9f8a3ef32e2cebbb792f5e03aef15c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a>Настройка записи сведений о звонке и параметров качества обслуживания в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-17_

После связывания хранилища мониторинга с пулом переднего плана Настройте хранилище мониторинга, а затем установите и настройте службы отчетов SQL Server и Отслеживайте отчеты, которые можно управлять записью сведений о вызове (CDR) и качеством (QoE). наблюдение с помощью командной консоли Lync Server Management Shell. Командлеты командной консоли Lync Server позволяют включать и отключать мониторинг CDR и/или QoE для определенного сайта или для всего развертывания Lync Server. Это можно сделать с помощью команды.

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

При установке Microsoft Lync Server 2013 Вы также сможете установить предопределенную коллекцию глобальных параметров конфигурации для CDR и QoE. В следующей таблице приведены значения по умолчанию для некоторых из наиболее часто используемых CDR параметров.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Свойство</th>
<th>Описание</th>
<th>Значение по умолчанию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableCDR</p></td>
<td><p>Указывает, включен ли мониторинг регистрации вызовов (CDR). Если установлено значение True, то все записи CDR будут собираться и записываться в базу данных мониторинга.</p></td>
<td><p>Верно</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>Указывает, будут ли записи CDR периодически удаляться из базы данных. Если установлено значение True, то записи будут удаляться после периода времени, заданного в свойствах KeepCallDetailForDays (для записей CDR) и KeepErrorReportForDays (для ошибок CDR). Если параметр имеет значение False, то записи CDR будут сохраняться неопределенное время.</p></td>
<td><p>Верно</p></td>
</tr>
<tr class="odd">
<td><p>KeepCallDetailForDays</p></td>
<td><p>Задает период в днях, в течение которого записи CDR будут сохраняться в базе данных; все записи старше заданного количества дней будут автоматически удаляться. Однако это будет происходить только в том случае, если включена очистка.</p>
<p>В качестве значения параметра KeepCallDetailForDays может быть установлено любое целое число от 1 до 2562 дней (приблизительно 7 лет).</p></td>
<td><p>60 дней</p></td>
</tr>
<tr class="even">
<td><p>KeepErrorReportForDays</p></td>
<td><p>Указывает число дней, в течение которого сохраняются отчеты об ошибках CDR; все отчеты старше указанного числа дней будут автоматически удаляться. Отчеты об ошибках CDR — это диагностические отчеты, которые отправляются клиентскими приложениями (например, Microsoft Lync 2013).</p>
<p>В качестве значения этого свойства может быть установлено любое целое число от 1 до 2562 дней.</p></td>
<td><p>60 дней</p></td>
</tr>
</tbody>
</table>


Аналогично, значения по умолчанию для некоторых параметров QoE показаны в следующей таблице.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Свойство</th>
<th>Описание</th>
<th>Значение по умолчанию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableQoE</p></td>
<td><p>Указывает, включен ли мониторинг QoE. Если установлено значение True, то все записи QoE будут собираться и записываться в базу данных мониторинга.</p></td>
<td><p>Верно</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>Указывает, будут ли записи QoE периодически удаляться из базы данных. Если установлено значение True, то записи будут удаляться после периода времени, заданного в свойстве KeepQoEDataForDays. Если параметр имеет значение False, то записи QoE будут сохраняться неопределенное время.</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>KeepQoEDataForDays</p></td>
<td><p>Задает период в днях, в течение которого записи QoE будут сохраняться в базе данных; все записи старше заданного количества дней будут автоматически удаляться. Однако это будет происходить только в том случае, если включена очистка..</p>
<p>В качестве значения этого свойства может быть установлено любое целое число от 1 до 2562 дней.</p></td>
<td><p>60 дней</p></td>
</tr>
</tbody>
</table>


Если требуется изменить эти глобальные параметры, то это можно сделать с помощью командлетов Set-CsCdrConfiguration и Set-CsQoEConfiguration. Например, эта команда (выполнить из командной консоли Lync Server Management Shell) отключает CDR мониторинг в глобальной области. Это можно сделать, задав для свойства Енаблекдр значение false ($False):

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

Следует отметить, что отключение мониторинга не отделяет хранилище данных наблюдения от интерфейсного пула, не удаляет его и никаким другим образом не влияет на тыловую базу данных мониторинга. Если вы используете командную консоль Lync Server для отключения CDR или QoE, вы временно не сможете собирать и архивировать данные мониторинга в Lync Server. Чтобы возобновить сбор и архивацию, например, данных CDR, достаточно просто вернуть значение True ($True) свойству EnableCDR:

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

Аналогично, следующая команда отключает очистку записей QoE на глобальном уровне:

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

Помимо глобального уровня, параметры конфигурации CDR и QoE можно назначать на уровне сайта. Это обеспечивает дополнительную гибкость управления мониторингом; например, администратор может включить мониторинг CDR для сайта Redmond, но отключить мониторинг CDR для сайта Dublin. Для создания новых параметров конфигурации CDR на уровне сайта можно использовать команды, аналогичные следующей:

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

Следует учитывать, что параметры, настроенные на уровне сайта, имеют преимущество перед параметрами, настроенными на глобальном уровне. Например, предположим, что мониторинг CDR включен на глобальном уровне, но отключен на уровне сайта для сайта Redmond. Это означает, что сведения регистрации вызовов для пользователей сайта Redmond не будут архивироваться. Однако для пользователей других сайтов (т.е. пользователей, которыми управляют глобальные настройки) сведения регистрации вызовов будут архивироваться.

Для создания новых параметров конфигурации QoE на уровне сайта можно использовать команды, аналогичные следующей:

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

Чтобы получить дополнительные сведения, в командной консоли Lync Server введите следующие команды:

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

