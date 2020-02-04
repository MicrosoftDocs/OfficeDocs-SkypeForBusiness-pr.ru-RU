---
title: 'Lync Server 2013: отчет о списке сбоев'
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
ms.openlocfilehash: 370008a5b33cc7eb45802fb02bdd9a873184ed5a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a>Отчет о списке отказов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-07-02_

Отчет Failure List (Список ошибок) предоставляет сведения об участниках однорангового сеанса (конференции), завершившегося с ошибкой. Эти сведения содержат URI пользователя, у которого возникла ошибка, а также код ответа SIP и ИД диагностики, связанные с ошибкой.

<div>

## <a name="accessing-the-failure-list-report"></a>Доступ к отчету Failure List (Список ошибок)

Для доступа к отчету о списке отказов достаточно щелкнуть один из указанных ниже метрик в [отчете о распределении неисправностей в Lync Server 2013](lync-server-2013-failure-distribution-report.md):

  - Top diagnostic reasons (sessions) (Основные причины диагностики (сеансы))

  - Top modalities (sessions) (Основные условия (сеансы))

  - Top pools (sessions) (Основные пулы (сеансы))

  - Top sources (sessions) (Основные источники (сеансы))

  - Top components (sessions) (Основные компоненты (сеансы))

  - Top from users (sessions) (Основные пользователи с ошибками исходящей связи (сеансы))

  - Top to users (sessions) (Основные пользователи с ошибками входящей связи (сеансы))

  - Top from user agents (sessions) (Основные агенты пользователей, используемые в сеансах, завершившихся с ошибками (сеансы))

Из отчета "список отказов" можно получить доступ к [отчету о одноранговых сеансах в Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) , щелкнув метрику "подробности сеанса" однорангового сеанса. Чтобы открыть отчет сведений о конференции, нажмите показатель «Конференция» для конференции.

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a>Рекомендации по использованию отчета Failure List (Список ошибок)

Чтобы просмотреть описание кода ответа или ИД диагностики, наведите указатель мыши на значение. Например, если вы наведете указатель мыши на Diagnostic ID (ИД диагностики) 7 025, то вы увидите следующую всплывающую подсказку:

Internal server error creating media for user (Внутренняя ошибка сервера при создании среды для пользователя).

Важно отметить, что отчет по списку ошибок не предоставляет прямой способ получения списка всех пользователей, принимавших участие в хотя бы одном сеансе, закончившемся с ошибкой, или способ определения пользователей, которые наиболее часто участвовали в сеансах, закончившихся с ошибками. (В одном случае у отчета "список отказов" нет возможностей фильтрации.) Однако если вы экспортируете данные, а затем преобразуете их в файл с разделителями-запятыми, вы можете использовать Windows PowerShell для поиска ответов на такие вопросы, как, например,. Например, предположим, что вы сохраняете данные в. CSV-файл с именем\\C\\:\_List Data failure. csv. Чтобы получить список пользователей, принимавших участие в хотя бы одном сеансе, закончившемся с ошибкой, используйте следующие команды:

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

## <a name="metrics"></a>Показатели

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
<th>Поддержка сортировки</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Время создания отчета</strong></p></td>
<td><p>Нет</p></td>
<td><p>Дата и время создания отчета.</p></td>
</tr>
<tr class="even">
<td><p><strong>Запрос</strong></p></td>
<td><p>Нет</p></td>
<td><p>Тип запроса SIP, завершившегося с ошибкой. Например, INVITE или BYE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Код ответа</strong></p></td>
<td><p>Нет</p></td>
<td><p>Код ответа SIP, отправленный при сбое конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>ИД диагностики</strong></p></td>
<td><p>Нет</p></td>
<td><p>Прикрепленный к SIP-сообщению уникальный идентификатор (в форме заголовка ms-diagnostics), который часто содержит информацию, полезную при поиске и устранении ошибок.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Время присоединения (мс)</strong></p></td>
<td><p>Нет</p></td>
<td><p>Период времени (в миллисекундах), требуемый для присоединения пользователя к конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Пользователь-отправитель</strong></p></td>
<td><p>Нет</p></td>
<td><p>SIP-адрес пользователя, инициировавшего вызов.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Агент пользователя, инициатора сеанса</strong></p></td>
<td><p>Нет</p></td>
<td><p>Программное обеспечение, используемое конечной точкой пользователя, инициировавшего звонок.</p></td>
</tr>
<tr class="even">
<td><p><strong>Пользователь-получатель</strong></p></td>
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

