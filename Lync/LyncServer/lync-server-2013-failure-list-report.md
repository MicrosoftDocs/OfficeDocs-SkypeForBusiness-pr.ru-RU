---
title: 'Lync Server 2013: отчет по списку сбоев'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 467dbfe14cbcbe7a032439fd437d3ce2c58c6d46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515386"
---
# <a name="failure-list-report-in-lync-server-2013"></a>Отчет по списку отказов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-07-02_

Отчет Failure List (Список ошибок) предоставляет сведения об участниках однорангового сеанса (конференции), завершившегося с ошибкой. Эти сведения содержат URI пользователя, у которого возникла ошибка, а также код ответа SIP и ИД диагностики, связанные с ошибкой.

<div>

## <a name="accessing-the-failure-list-report"></a>Доступ к отчету Failure List (Список ошибок)

Чтобы получить доступ к отчету по списку отказов, щелкните любой из следующих метрик в [отчете о распределении сбоев в Lync Server 2013](lync-server-2013-failure-distribution-report.md):

  - Top diagnostic reasons (sessions) (Основные причины диагностики (сеансы))

  - Top modalities (sessions) (Основные условия (сеансы))

  - Top pools (sessions) (Основные пулы (сеансы))

  - Top sources (sessions) (Основные источники (сеансы))

  - Top components (sessions) (Основные компоненты (сеансы))

  - Top from users (sessions) (Основные пользователи с ошибками исходящей связи (сеансы))

  - Top to users (sessions) (Основные пользователи с ошибками входящей связи (сеансы))

  - Top from user agents (sessions) (Основные агенты пользователей, используемые в сеансах, завершившихся с ошибками (сеансы))

В отчете по списку сбоев можно получить доступ к [отчету по деталям однорангового сеанса в Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) , щелкнув метрику сведений о сеансе для однорангового сеанса. Чтобы открыть отчет Conference Detail (Сведения о конференции), щелкните показатель Conference (Конференция) для конференции.

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a>Рекомендации по использованию отчета Failure List (Список ошибок)

Чтобы просмотреть описание кода ответа или ИД диагностики, наведите указатель мыши на значение. Например, если вы наведете указатель мыши на Diagnostic ID (ИД диагностики) 7 025, то вы увидите следующую всплывающую подсказку:

Internal server error creating media for user (Внутренняя ошибка сервера при создании среды для пользователя).

Важно отметить, что отчет Failure List (Список ошибок) не предоставляет прямой способ получения списка всех пользователей, принимавших участие в хотя бы одном сеансе, закончившемся с ошибкой, или способ определения пользователей, которые наиболее часто участвовали в сеансах, закончившихся с ошибками. (Для одного из них отчет о списке отказов не имеет возможностей фильтрации). Тем не менее, если вы экспортируете данные и затем преобразуете их в файл с разделителями запятыми, вы можете использовать Windows PowerShell, чтобы найти ответы на такие вопросы. Например, предположим, что вы сохраняете данные в файле. CSV-файл с именем C: \\ \\ сбой данных \_List.csv. Чтобы получить список пользователей, принимавших участие в хотя бы одном сеансе, закончившемся с ошибкой, используйте следующие команды:

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

Эти команды возвращают сведения, схожие со следующими:

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

Следующие команды возвращают общее число сеансов каждого пользователя, завершившихся с ошибкой:

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

Эти команды возвращают сведения, схожие со следующими:

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a>Фильтры

Нет. В отчете Failure List (Список ошибок) нельзя использовать фильтр.

</div>

<div>

## <a name="metrics"></a>Метрики

В следующей таблице приведены сведения, содержащиеся в отчете Failure List (Список ошибок) для каждого звонка, завершившегося с ошибкой.

### <a name="failure-list-report-metrics"></a>Показатели отчета Failure List (Список ошибок)

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
<td><p><strong>Reported time</strong> (Время создания отчета)</p></td>
<td><p>Нет</p></td>
<td><p>Дата и время создания отчета.</p></td>
</tr>
<tr class="even">
<td><p><strong>Запрос</strong></p></td>
<td><p>Нет</p></td>
<td><p>Тип запроса SIP, завершившегося с ошибкой. Например, INVITE или BYE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Response code</strong> (Код ответа)</p></td>
<td><p>Нет</p></td>
<td><p>Код ответа SIP, отправленный при сбое конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnostic ID</strong> (ИД диагностики)</p></td>
<td><p>Нет</p></td>
<td><p>Уникальный идентификатор (в виде заголовка ms-diagnostics), добавленный к сообщению SIP, который предоставляет полезные сведения для устранения ошибок.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Join cost time (ms)</strong> (Время присоединения (мс))</p></td>
<td><p>Нет</p></td>
<td><p>Период времени (в миллисекундах), требуемый для присоединения пользователя к конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>From user</strong> (От пользователя)</p></td>
<td><p>Нет</p></td>
<td><p>SIP-адрес пользователя, инициировавшего звонок.</p></td>
</tr>
<tr class="odd">
<td><p><strong>From user agent</strong> (От агента пользователя)</p></td>
<td><p>Нет</p></td>
<td><p>Программное обеспечение, используемое конечной точкой пользователя, инициировавшего звонок.</p></td>
</tr>
<tr class="even">
<td><p><strong>To user</strong> (К пользователю)</p></td>
<td><p>Нет</p></td>
<td><p>SIP-адрес пользователя, принявшего звонок.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

