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
ms.openlocfilehash: 3fc3d74e6613f54f346e00328f1fae929f7def27
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a><span data-ttu-id="7e505-102">Отчет по списку отказов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e505-102">Failure List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e505-103">_**Последнее изменение темы:** 2012-07-02_</span><span class="sxs-lookup"><span data-stu-id="7e505-103">_**Topic Last Modified:** 2012-07-02_</span></span>

<span data-ttu-id="7e505-p101">Отчет Failure List (Список ошибок) предоставляет сведения об участниках однорангового сеанса (конференции), завершившегося с ошибкой. Эти сведения содержат URI пользователя, у которого возникла ошибка, а также код ответа SIP и ИД диагностики, связанные с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="7e505-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>

<div>

## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="7e505-106">Доступ к отчету Failure List (Список ошибок)</span><span class="sxs-lookup"><span data-stu-id="7e505-106">Accessing the Failure List Report</span></span>

<span data-ttu-id="7e505-107">Чтобы получить доступ к отчету по списку отказов, щелкните любой из следующих метрик в [отчете о распределении сбоев в Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span><span class="sxs-lookup"><span data-stu-id="7e505-107">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span></span>

  - <span data-ttu-id="7e505-108">Top diagnostic reasons (sessions) (Основные причины диагностики (сеансы))</span><span class="sxs-lookup"><span data-stu-id="7e505-108">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="7e505-109">Top modalities (sessions) (Основные условия (сеансы))</span><span class="sxs-lookup"><span data-stu-id="7e505-109">Top modalities (sessions)</span></span>

  - <span data-ttu-id="7e505-110">Top pools (sessions) (Основные пулы (сеансы))</span><span class="sxs-lookup"><span data-stu-id="7e505-110">Top pools (sessions)</span></span>

  - <span data-ttu-id="7e505-111">Top sources (sessions) (Основные источники (сеансы))</span><span class="sxs-lookup"><span data-stu-id="7e505-111">Top sources (sessions)</span></span>

  - <span data-ttu-id="7e505-112">Top components (sessions) (Основные компоненты (сеансы))</span><span class="sxs-lookup"><span data-stu-id="7e505-112">Top components (sessions)</span></span>

  - <span data-ttu-id="7e505-113">Top from users (sessions) (Основные пользователи с ошибками исходящей связи (сеансы))</span><span class="sxs-lookup"><span data-stu-id="7e505-113">Top from users (sessions)</span></span>

  - <span data-ttu-id="7e505-114">Top to users (sessions) (Основные пользователи с ошибками входящей связи (сеансы))</span><span class="sxs-lookup"><span data-stu-id="7e505-114">Top to users (sessions)</span></span>

  - <span data-ttu-id="7e505-115">Top from user agents (sessions) (Основные агенты пользователей, используемые в сеансах, завершившихся с ошибками (сеансы))</span><span class="sxs-lookup"><span data-stu-id="7e505-115">Top from user agents (sessions)</span></span>

<span data-ttu-id="7e505-116">В отчете по списку сбоев можно получить доступ к [отчету по деталям однорангового сеанса в Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) , щелкнув метрику сведений о сеансе для однорангового сеанса.</span><span class="sxs-lookup"><span data-stu-id="7e505-116">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="7e505-117">Чтобы открыть отчет Conference Detail (Сведения о конференции), щелкните показатель Conference (Конференция) для конференции.</span><span class="sxs-lookup"><span data-stu-id="7e505-117">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="7e505-118">Рекомендации по использованию отчета Failure List (Список ошибок)</span><span class="sxs-lookup"><span data-stu-id="7e505-118">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="7e505-p103">Чтобы просмотреть описание кода ответа или ИД диагностики, наведите указатель мыши на значение. Например, если вы наведете указатель мыши на Diagnostic ID (ИД диагностики) 7 025, то вы увидите следующую всплывающую подсказку:</span><span class="sxs-lookup"><span data-stu-id="7e505-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>

<span data-ttu-id="7e505-121">Internal server error creating media for user (Внутренняя ошибка сервера при создании среды для пользователя).</span><span class="sxs-lookup"><span data-stu-id="7e505-121">Internal server error creating media for user.</span></span>

<span data-ttu-id="7e505-122">Важно отметить, что отчет Failure List (Список ошибок) не предоставляет прямой способ получения списка всех пользователей, принимавших участие в хотя бы одном сеансе, закончившемся с ошибкой, или способ определения пользователей, которые наиболее часто участвовали в сеансах, закончившихся с ошибками.</span><span class="sxs-lookup"><span data-stu-id="7e505-122">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="7e505-123">(Для одного из них отчет о списке отказов не имеет возможностей фильтрации). Тем не менее, если вы экспортируете данные и затем преобразуете их в файл с разделителями запятыми, вы можете использовать Windows PowerShell, чтобы найти ответы на такие вопросы.</span><span class="sxs-lookup"><span data-stu-id="7e505-123">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="7e505-124">Например, предположим, что вы сохраняете данные в файле. CSV-файл с именем\\C\\:\_List Failure Data List. csv.</span><span class="sxs-lookup"><span data-stu-id="7e505-124">For example, suppose you save the data to a .CSV file named C:\\Data\\Failure\_List.csv.</span></span> <span data-ttu-id="7e505-125">Чтобы получить список пользователей, принимавших участие в хотя бы одном сеансе, закончившемся с ошибкой, используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="7e505-125">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span>

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

<span data-ttu-id="7e505-126">Эти команды возвращают сведения, схожие со следующими:</span><span class="sxs-lookup"><span data-stu-id="7e505-126">That command will return a list similar to this:</span></span>

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

<span data-ttu-id="7e505-127">Следующие команды возвращают общее число сеансов каждого пользователя, завершившихся с ошибкой:</span><span class="sxs-lookup"><span data-stu-id="7e505-127">These two commands report back the total number of failed sessions that each user was involved in:</span></span>

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

<span data-ttu-id="7e505-128">Эти команды возвращают сведения, схожие со следующими:</span><span class="sxs-lookup"><span data-stu-id="7e505-128">That will return data similar to this:</span></span>

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7e505-129">Фильтры</span><span class="sxs-lookup"><span data-stu-id="7e505-129">Filters</span></span>

<span data-ttu-id="7e505-p105">Нет. В отчете Failure List (Список ошибок) нельзя использовать фильтр.</span><span class="sxs-lookup"><span data-stu-id="7e505-p105">None. You cannot filter the Failure List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7e505-132">Метрик</span><span class="sxs-lookup"><span data-stu-id="7e505-132">Metrics</span></span>

<span data-ttu-id="7e505-133">В следующей таблице приведены сведения, содержащиеся в отчете Failure List (Список ошибок) для каждого звонка, завершившегося с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="7e505-133">The following table lists the information provided in the Failure List Report for each failed call.</span></span>

### <a name="failure-list-report-metrics"></a><span data-ttu-id="7e505-134">Показатели отчета Failure List (Список ошибок)</span><span class="sxs-lookup"><span data-stu-id="7e505-134">Failure List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e505-135">Имя</span><span class="sxs-lookup"><span data-stu-id="7e505-135">Name</span></span></th>
<th><span data-ttu-id="7e505-136">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="7e505-136">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7e505-137">Описание</span><span class="sxs-lookup"><span data-stu-id="7e505-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e505-138"><strong>Reported time</strong> (Время создания отчета)</span><span class="sxs-lookup"><span data-stu-id="7e505-138"><strong>Reported time</strong></span></span></p></td>
<td><p><span data-ttu-id="7e505-139">Нет</span><span class="sxs-lookup"><span data-stu-id="7e505-139">No</span></span></p></td>
<td><p><span data-ttu-id="7e505-140">Дата и время создания отчета.</span><span class="sxs-lookup"><span data-stu-id="7e505-140">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e505-141"><strong>Запрос</strong></span><span class="sxs-lookup"><span data-stu-id="7e505-141"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="7e505-142">Нет</span><span class="sxs-lookup"><span data-stu-id="7e505-142">No</span></span></p></td>
<td><p><span data-ttu-id="7e505-p106">Тип запроса SIP, завершившегося с ошибкой. Например, INVITE или BYE.</span><span class="sxs-lookup"><span data-stu-id="7e505-p106">SIP request type that failed. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e505-145"><strong>Response code</strong> (Код ответа)</span><span class="sxs-lookup"><span data-stu-id="7e505-145"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="7e505-146">Нет</span><span class="sxs-lookup"><span data-stu-id="7e505-146">No</span></span></p></td>
<td><p><span data-ttu-id="7e505-147">Код ответа SIP, отправленный при сбое конференции.</span><span class="sxs-lookup"><span data-stu-id="7e505-147">SIP response code sent when the conference failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e505-148"><strong>Diagnostic ID</strong> (ИД диагностики)</span><span class="sxs-lookup"><span data-stu-id="7e505-148"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="7e505-149">Нет</span><span class="sxs-lookup"><span data-stu-id="7e505-149">No</span></span></p></td>
<td><p><span data-ttu-id="7e505-150">Уникальный идентификатор (в виде заголовка ms-diagnostics), добавленный к сообщению SIP, который предоставляет полезные сведения для устранения ошибок.</span><span class="sxs-lookup"><span data-stu-id="7e505-150">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e505-151"><strong>Join cost time (ms)</strong> (Время присоединения (мс))</span><span class="sxs-lookup"><span data-stu-id="7e505-151"><strong>Join cost time (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="7e505-152">Нет</span><span class="sxs-lookup"><span data-stu-id="7e505-152">No</span></span></p></td>
<td><p><span data-ttu-id="7e505-153">Период времени (в миллисекундах), требуемый для присоединения пользователя к конференции.</span><span class="sxs-lookup"><span data-stu-id="7e505-153">Amount of time (in milliseconds) required for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e505-154"><strong>From user</strong> (От пользователя)</span><span class="sxs-lookup"><span data-stu-id="7e505-154"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="7e505-155">Нет</span><span class="sxs-lookup"><span data-stu-id="7e505-155">No</span></span></p></td>
<td><p><span data-ttu-id="7e505-156">SIP-адрес пользователя, инициировавшего звонок.</span><span class="sxs-lookup"><span data-stu-id="7e505-156">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e505-157"><strong>From user agent</strong> (От агента пользователя)</span><span class="sxs-lookup"><span data-stu-id="7e505-157"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="7e505-158">Нет</span><span class="sxs-lookup"><span data-stu-id="7e505-158">No</span></span></p></td>
<td><p><span data-ttu-id="7e505-159">Программное обеспечение, используемое конечной точкой пользователя, инициировавшего звонок.</span><span class="sxs-lookup"><span data-stu-id="7e505-159">Software used by the endpoint of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e505-160"><strong>To user</strong> (К пользователю)</span><span class="sxs-lookup"><span data-stu-id="7e505-160"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="7e505-161">Нет</span><span class="sxs-lookup"><span data-stu-id="7e505-161">No</span></span></p></td>
<td><p><span data-ttu-id="7e505-162">SIP-адрес пользователя, принявшего звонок.</span><span class="sxs-lookup"><span data-stu-id="7e505-162">SIP address of the user who was being called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

