---
title: 'Lync Server 2013: подробный отчет по Конференции'
description: 'Lync Server 2013: подробный отчет по Конференции.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07c50b545f4a9ee3308a840fc2aa5a15e617a5bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577635"
---
# <a name="conference-detail-report-in-lync-server-2013"></a>Подробный отчет по конференции в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-22_

Подробный отчет по конференции содержит подробную информацию обо всех пользователях, принимавших участие в конференции. Например, вы можете просматривать такую информацию, как дата и время присоединения пользователя к конференции, дата и время покидания  конференции, а также агент пользователя конечной точки, использованный для подключения этого пользователя к конференции. Вы также можете просмотреть информацию о роли пользователя в каждой конференции (например, выступающий или участник). Возможно, еще важнее то, что вы можете быстро просмотреть, какие пользователи успешно присоединились к конференции и участвовали в ней и какие пользователи не смогли этого сделать.

<div>

## <a name="accessing-the-conference-detail-report"></a>Доступ к подробному отчету по конференции

Подробный отчет по конференции можно открыть из следующих отчетов:

  - [Отчет по контролю допуска звонков в Lync Server 2013](lync-server-2013-call-admission-control-report.md) (щелкнув метрику сведений для Конференции)

  - [Отчет по списку отказов в Lync Server 2013](lync-server-2013-failure-list-report.md) (щелкнув метрику конференции)

  - [Отчет об активности пользователей в Lync Server 2013](lync-server-2013-user-activity-report.md) (щелкнув метрику URI конференции)

Из подробного отчета по конференции вы можете получить доступ к [диагностическим отчету в Lync Server 2013](lync-server-2013-diagnostic-report.md) , щелкнув метрику диагностического отчета (Detail).

</div>

<div>

## <a name="filters"></a>Фильтры

Нет. Вы не можете фильтровать подробный отчет по конференции.

</div>

<div>

## <a name="metrics"></a>Метрики

В следующей таблице приведены сведения из раздела информации о конференции, входящего в подробный отчет по конференции.

### <a name="conference-information-metrics"></a>Метрики информации о конференции

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Возможность сортировки по этому показателю</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Conference URI</strong> (URI конференции)</p></td>
<td></td>
<td><p>URI, назначенный конференции. Например:</p>
<p>SIP: kmyer@litwareinc. com; GRUU; непрозрачный = App: conf: Focus: ID: drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool FQDN</strong> (Полное доменное имя пула)</p></td>
<td></td>
<td><p>Полное доменное имя пула Регистратора или участвующего в сеансе пограничного сервера.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Start time</strong> (Время начала)</p></td>
<td></td>
<td><p>Дата и время начала конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizer</strong></p></td>
<td></td>
<td><p>SIP-адрес пользователя, организовавшего конференцию.</p></td>
</tr>
<tr class="odd">
<td><p><strong>End time</strong> (Время окончания)</p></td>
<td></td>
<td><p>Дата и время завершения конференции.</p></td>
</tr>
</tbody>
</table>


В следующей таблице приведены сведения из раздела участия в конференции, входящего в подробный отчет по конференции.

### <a name="conference-participation-metrics"></a>Метрики участия в конференции

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Возможность сортировки по этому показателю</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Пользователь</strong></p></td>
<td></td>
<td><p>SIP-адрес пользователя, участвовавшего в конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Role</strong></p></td>
<td></td>
<td><p>Роль (например, выступающий) участника конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Подключение</strong></p></td>
<td></td>
<td><p>Возможность подключения к сети (обычно изнутри или извне) для участника.</p></td>
</tr>
<tr class="even">
<td><p>Время присоединения</p></td>
<td></td>
<td><p>Дата и время присоединения участника к конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Leave time</strong> (Время ухода)</p></td>
<td></td>
<td><p>Дата и время покидания участником конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>User agent</strong> (Агент пользователя)</p></td>
<td></td>
<td><p>Идентификатор для программного обеспечения, используемого конечной точкой участника.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Diagnostic reports</strong> (Диагностические отчеты)</p></td>
<td></td>
<td><p>Предоставляет сведения о диагностике и о поиске и устранении неполадок, включая коды отклика SIP, диагностические заголовки, значения времени присоединения к конференции и диагностические идентификаторы для неудачных сеансов.</p></td>
</tr>
</tbody>
</table>


В следующей таблице перечислены сведения, представленные в разделе Conference модальности в информационном отчете о Конференции.

### <a name="conference-modalities-metrics"></a>Метрики модальностей конференции

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Возможность сортировки по этому показателю</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Пользователь</strong></p></td>
<td></td>
<td><p>SIP-адрес пользователя, участвовавшего в конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Join time</strong> (Время присоединения)</p></td>
<td></td>
<td><p>Дата и время присоединения участника к конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Leave time</strong> (Время ухода)</p></td>
<td></td>
<td><p>Дата и время покидания участником конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Conferencing server URI</strong> (URI сервера конференций)</p></td>
<td></td>
<td><p>URI для используемого в конференции сервера конференций.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Diagnostic reports</strong> (Диагностические отчеты)</p></td>
<td></td>
<td><p>Предоставляет сведения о диагностике и о поиске и устранении неполадок, включая коды отклика SIP, диагностические заголовки, значения времени присоединения к конференции и диагностические идентификаторы для неудачных сеансов.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

