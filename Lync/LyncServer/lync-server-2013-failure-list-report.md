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
ms.openlocfilehash: 010e8314eb7d2cbb33354461bdc2a1eb2c5b2cf1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a><span data-ttu-id="89e2e-102">Отчет по списку отказов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89e2e-102">Failure List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89e2e-103">_**Последнее изменение темы:** 2012-07-02_</span><span class="sxs-lookup"><span data-stu-id="89e2e-103">_**Topic Last Modified:** 2012-07-02_</span></span>

<span data-ttu-id="89e2e-p101">Отчет Failure List (Список ошибок) предоставляет сведения об участниках однорангового сеанса (конференции), завершившегося с ошибкой. Эти сведения содержат URI пользователя, у которого возникла ошибка, а также код ответа SIP и ИД диагностики, связанные с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="89e2e-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>

<div>

## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="89e2e-106">Доступ к отчету Failure List (Список ошибок)</span><span class="sxs-lookup"><span data-stu-id="89e2e-106">Accessing the Failure List Report</span></span>

<span data-ttu-id="89e2e-107">Чтобы получить доступ к отчету по списку отказов, щелкните любой из следующих метрик в [отчете о распределении сбоев в Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span><span class="sxs-lookup"><span data-stu-id="89e2e-107">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span></span>

  - <span data-ttu-id="89e2e-108">Top diagnostic reasons (sessions) (Основные причины диагностики (сеансы))</span><span class="sxs-lookup"><span data-stu-id="89e2e-108">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="89e2e-109">Top modalities (sessions) (Основные условия (сеансы))</span><span class="sxs-lookup"><span data-stu-id="89e2e-109">Top modalities (sessions)</span></span>

  - <span data-ttu-id="89e2e-110">Top pools (sessions) (Основные пулы (сеансы))</span><span class="sxs-lookup"><span data-stu-id="89e2e-110">Top pools (sessions)</span></span>

  - <span data-ttu-id="89e2e-111">Top sources (sessions) (Основные источники (сеансы))</span><span class="sxs-lookup"><span data-stu-id="89e2e-111">Top sources (sessions)</span></span>

  - <span data-ttu-id="89e2e-112">Top components (sessions) (Основные компоненты (сеансы))</span><span class="sxs-lookup"><span data-stu-id="89e2e-112">Top components (sessions)</span></span>

  - <span data-ttu-id="89e2e-113">Top from users (sessions) (Основные пользователи с ошибками исходящей связи (сеансы))</span><span class="sxs-lookup"><span data-stu-id="89e2e-113">Top from users (sessions)</span></span>

  - <span data-ttu-id="89e2e-114">Top to users (sessions) (Основные пользователи с ошибками входящей связи (сеансы))</span><span class="sxs-lookup"><span data-stu-id="89e2e-114">Top to users (sessions)</span></span>

  - <span data-ttu-id="89e2e-115">Top from user agents (sessions) (Основные агенты пользователей, используемые в сеансах, завершившихся с ошибками (сеансы))</span><span class="sxs-lookup"><span data-stu-id="89e2e-115">Top from user agents (sessions)</span></span>

<span data-ttu-id="89e2e-116">В отчете по списку сбоев можно получить доступ к [отчету по деталям однорангового сеанса в Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) , щелкнув метрику сведений о сеансе для однорангового сеанса.</span><span class="sxs-lookup"><span data-stu-id="89e2e-116">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="89e2e-117">Чтобы открыть отчет Conference Detail (Сведения о конференции), щелкните показатель Conference (Конференция) для конференции.</span><span class="sxs-lookup"><span data-stu-id="89e2e-117">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="89e2e-118">Рекомендации по использованию отчета Failure List (Список ошибок)</span><span class="sxs-lookup"><span data-stu-id="89e2e-118">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="89e2e-p103">Чтобы просмотреть описание кода ответа или ИД диагностики, наведите указатель мыши на значение. Например, если вы наведете указатель мыши на Diagnostic ID (ИД диагностики) 7 025, то вы увидите следующую всплывающую подсказку:</span><span class="sxs-lookup"><span data-stu-id="89e2e-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>

<span data-ttu-id="89e2e-121">Internal server error creating media for user (Внутренняя ошибка сервера при создании среды для пользователя).</span><span class="sxs-lookup"><span data-stu-id="89e2e-121">Internal server error creating media for user.</span></span>

<span data-ttu-id="89e2e-122">Важно отметить, что отчет Failure List (Список ошибок) не предоставляет прямой способ получения списка всех пользователей, принимавших участие в хотя бы одном сеансе, закончившемся с ошибкой, или способ определения пользователей, которые наиболее часто участвовали в сеансах, закончившихся с ошибками.</span><span class="sxs-lookup"><span data-stu-id="89e2e-122">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="89e2e-123">(Для одного из них отчет о списке отказов не имеет возможностей фильтрации). Тем не менее, если вы экспортируете данные и затем преобразуете их в файл с разделителями запятыми, вы можете использовать Windows PowerShell, чтобы найти ответы на такие вопросы.</span><span class="sxs-lookup"><span data-stu-id="89e2e-123">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="89e2e-124">Например, предположим, что вы сохраняете данные в файле. CSV-файл с именем\\C\\:\_List Failure Data List. csv.</span><span class="sxs-lookup"><span data-stu-id="89e2e-124">For example, suppose you save the data to a .CSV file named C:\\Data\\Failure\_List.csv.</span></span> <span data-ttu-id="89e2e-125">Чтобы получить список пользователей, принимавших участие в хотя бы одном сеансе, закончившемся с ошибкой, используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="89e2e-125">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span>

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

<span data-ttu-id="89e2e-126">Эти команды возвращают сведения, схожие со следующими:</span><span class="sxs-lookup"><span data-stu-id="89e2e-126">That command will return a list similar to this:</span></span>

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

<span data-ttu-id="89e2e-127">Следующие команды возвращают общее число сеансов каждого пользователя, завершившихся с ошибкой:</span><span class="sxs-lookup"><span data-stu-id="89e2e-127">These two commands report back the total number of failed sessions that each user was involved in:</span></span>

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

<span data-ttu-id="89e2e-128">Эти команды возвращают сведения, схожие со следующими:</span><span class="sxs-lookup"><span data-stu-id="89e2e-128">That will return data similar to this:</span></span>

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a><span data-ttu-id="89e2e-129">Фильтры</span><span class="sxs-lookup"><span data-stu-id="89e2e-129">Filters</span></span>

<span data-ttu-id="89e2e-p105">Нет. В отчете Failure List (Список ошибок) нельзя использовать фильтр.</span><span class="sxs-lookup"><span data-stu-id="89e2e-p105">None. You cannot filter the Failure List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="89e2e-132">Метрик</span><span class="sxs-lookup"><span data-stu-id="89e2e-132">Metrics</span></span>

<span data-ttu-id="89e2e-133">В следующей таблице приведены сведения, содержащиеся в отчете Failure List (Список ошибок) для каждого звонка, завершившегося с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="89e2e-133">The following table lists the information provided in the Failure List Report for each failed call.</span></span>

### <a name="failure-list-report-metrics"></a><span data-ttu-id="89e2e-134">Показатели отчета Failure List (Список ошибок)</span><span class="sxs-lookup"><span data-stu-id="89e2e-134">Failure List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89e2e-135">Имя</span><span class="sxs-lookup"><span data-stu-id="89e2e-135">Name</span></span></th>
<th><span data-ttu-id="89e2e-136">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="89e2e-136">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="89e2e-137">Описание</span><span class="sxs-lookup"><span data-stu-id="89e2e-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89e2e-138"><strong>Reported time</strong> (Время создания отчета)</span><span class="sxs-lookup"><span data-stu-id="89e2e-138"><strong>Reported time</strong></span></span></p></td>
<td><p><span data-ttu-id="89e2e-139">Нет</span><span class="sxs-lookup"><span data-stu-id="89e2e-139">No</span></span></p></td>
<td><p><span data-ttu-id="89e2e-140">Дата и время создания отчета.</span><span class="sxs-lookup"><span data-stu-id="89e2e-140">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e2e-141"><strong>Запрос</strong></span><span class="sxs-lookup"><span data-stu-id="89e2e-141"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="89e2e-142">Нет</span><span class="sxs-lookup"><span data-stu-id="89e2e-142">No</span></span></p></td>
<td><p><span data-ttu-id="89e2e-p106">Тип запроса SIP, завершившегося с ошибкой. Например, INVITE или BYE.</span><span class="sxs-lookup"><span data-stu-id="89e2e-p106">SIP request type that failed. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e2e-145"><strong>Response code</strong> (Код ответа)</span><span class="sxs-lookup"><span data-stu-id="89e2e-145"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="89e2e-146">Нет</span><span class="sxs-lookup"><span data-stu-id="89e2e-146">No</span></span></p></td>
<td><p><span data-ttu-id="89e2e-147">Код ответа SIP, отправленный при сбое конференции.</span><span class="sxs-lookup"><span data-stu-id="89e2e-147">SIP response code sent when the conference failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e2e-148"><strong>Diagnostic ID</strong> (ИД диагностики)</span><span class="sxs-lookup"><span data-stu-id="89e2e-148"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="89e2e-149">Нет</span><span class="sxs-lookup"><span data-stu-id="89e2e-149">No</span></span></p></td>
<td><p><span data-ttu-id="89e2e-150">Уникальный идентификатор (в виде заголовка ms-diagnostics), добавленный к сообщению SIP, который предоставляет полезные сведения для устранения ошибок.</span><span class="sxs-lookup"><span data-stu-id="89e2e-150">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e2e-151"><strong>Join cost time (ms)</strong> (Время присоединения (мс))</span><span class="sxs-lookup"><span data-stu-id="89e2e-151"><strong>Join cost time (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="89e2e-152">Нет</span><span class="sxs-lookup"><span data-stu-id="89e2e-152">No</span></span></p></td>
<td><p><span data-ttu-id="89e2e-153">Период времени (в миллисекундах), требуемый для присоединения пользователя к конференции.</span><span class="sxs-lookup"><span data-stu-id="89e2e-153">Amount of time (in milliseconds) required for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e2e-154"><strong>From user</strong> (От пользователя)</span><span class="sxs-lookup"><span data-stu-id="89e2e-154"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="89e2e-155">Нет</span><span class="sxs-lookup"><span data-stu-id="89e2e-155">No</span></span></p></td>
<td><p><span data-ttu-id="89e2e-156">SIP-адрес пользователя, инициировавшего звонок.</span><span class="sxs-lookup"><span data-stu-id="89e2e-156">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e2e-157"><strong>From user agent</strong> (От агента пользователя)</span><span class="sxs-lookup"><span data-stu-id="89e2e-157"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="89e2e-158">Нет</span><span class="sxs-lookup"><span data-stu-id="89e2e-158">No</span></span></p></td>
<td><p><span data-ttu-id="89e2e-159">Программное обеспечение, используемое конечной точкой пользователя, инициировавшего звонок.</span><span class="sxs-lookup"><span data-stu-id="89e2e-159">Software used by the endpoint of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e2e-160"><strong>To user</strong> (К пользователю)</span><span class="sxs-lookup"><span data-stu-id="89e2e-160"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="89e2e-161">Нет</span><span class="sxs-lookup"><span data-stu-id="89e2e-161">No</span></span></p></td>
<td><p><span data-ttu-id="89e2e-162">SIP-адрес пользователя, принявшего звонок.</span><span class="sxs-lookup"><span data-stu-id="89e2e-162">SIP address of the user who was being called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

