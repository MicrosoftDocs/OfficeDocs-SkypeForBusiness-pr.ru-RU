---
title: 'Lync Server 2013: подробный отчет о Конференции'
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
ms.openlocfilehash: 7e8e2cd992e83adb29c43935d4b4c7f223580d53
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a>Подробный отчет о конференции в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-22_

Подробный отчет по конференции содержит подробную информацию обо всех пользователях, принимавших участие в конференции. Например, вы можете просматривать такую информацию, как дата и время присоединения пользователя к конференции, дата и время покидания конференции, а также агент пользователя конечной точки, использованный для подключения этого пользователя к конференции. Вы также можете просмотреть информацию о роли пользователя в каждой конференции (например, выступающий или участник). Возможно, еще важнее то, что вы можете быстро просмотреть, какие пользователи успешно присоединились к конференции и участвовали в ней и какие пользователи не смогли этого сделать.

<div>

## <a name="accessing-the-conference-detail-report"></a>Доступ к подробному отчету по конференции

Подробный отчет по конференции можно открыть из следующих отчетов:

  - [Отчет по контролю за допуском звонков в Lync Server 2013](lync-server-2013-call-admission-control-report.md) (с помощью которого можно выбрать детальную метрику конференции)

  - [Отчет о списке отказов в Lync Server 2013](lync-server-2013-failure-list-report.md) (щелчок метрики конференции)

  - [Отчет о действиях пользователей в Lync Server 2013](lync-server-2013-user-activity-report.md) (щелчок метрики URI конференции)

В отчете сведения о конференции вы можете получить доступ к [отчету о диагностике в Lync Server 2013](lync-server-2013-diagnostic-report.md) , щелкнув метрику диагностического отчета (подробности).

</div>

<div>

## <a name="filters"></a>Фильтры

Нет. Вы не можете фильтровать подробный отчет по конференции.

</div>

<div>

## <a name="metrics"></a>Показатели

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
<th>Поддержка сортировки</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Идентификатор URI конференции</strong></p></td>
<td></td>
<td><p>URI, назначенный конференции. Например:</p>
<p>sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p><strong>Полное доменное имя пула</strong></p></td>
<td></td>
<td><p>Полное доменное имя пула Регистратора или участвующего в сеансе пограничного сервера.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Время начала</strong></p></td>
<td></td>
<td><p>Дата и время начала конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Организатор</strong></p></td>
<td></td>
<td><p>SIP-адрес пользователя, организовавшего конференцию.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Время окончания</strong></p></td>
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
<th>Поддержка сортировки</th>
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
<td><p><strong>Роль</strong></p></td>
<td></td>
<td><p>Роль (например, докладчик), которую играл участник конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Подключение</strong></p></td>
<td></td>
<td><p>Подключение участника к сети, обычно из внутренней сети или из внешней сети.</p></td>
</tr>
<tr class="even">
<td><p>Время присоединения</p></td>
<td></td>
<td><p>Дата и время присоединения участника к конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Время выхода</strong></p></td>
<td></td>
<td><p>Дата и время, когда участник покинул конференцию.</p></td>
</tr>
<tr class="even">
<td><p><strong>Агент пользователя</strong></p></td>
<td></td>
<td><p>Идентификатор для программного обеспечения, используемого конечной точкой участника.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Диагностический отчет</strong></p></td>
<td></td>
<td><p>Предоставляет сведения о диагностике и о поиске и устранении неполадок, включая коды отклика SIP, диагностические заголовки, значения времени присоединения к конференции и диагностические идентификаторы для неудачных сеансов.</p></td>
</tr>
</tbody>
</table>


В таблице ниже приведены сведения, указанные в разделе Conference модальностей в отчете "сведения о конференции".

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
<th>Поддержка сортировки</th>
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
<td><p><strong>Время присоединения</strong></p></td>
<td></td>
<td><p>Дата и время присоединения участника к конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Время ухода</strong></p></td>
<td></td>
<td><p>Дата и время покидания участником конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI сервера конференций</strong></p></td>
<td></td>
<td><p>URI для используемого в конференции сервера конференций.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Диагностический отчет</strong></p></td>
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

