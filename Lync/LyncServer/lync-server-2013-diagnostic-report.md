---
title: 'Lync Server 2013: диагностический отчет'
description: 'Lync Server 2013: диагностический отчет.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 198b836437285b464ba9172e59c9a60ed0a53b65
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576255"
---
# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="38d28-103">Диагностический отчет в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38d28-103">Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38d28-104">_**Последнее изменение темы:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="38d28-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="38d28-105">Диагностический отчет предоставляет сведения о сеансах, которые завершились с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="38d28-105">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="38d28-106">Эти сведения включают ИД диагностики и диагностический заголовок, переданные при сбое сеанса.</span><span class="sxs-lookup"><span data-stu-id="38d28-106">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="38d28-107">ИД диагностики — это уникальный идентификатор (в виде заголовка ms-diagnostics), который возвращает добавленное сообщение SIP, а диагностический заголовок содержит дополнительное описание ИД диагностики.</span><span class="sxs-lookup"><span data-stu-id="38d28-107">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="38d28-108">Отчет также может содержать дополнительные сведения об устранении неполадок, предоставляемые компонентом создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="38d28-108">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="38d28-109">Пример:</span><span class="sxs-lookup"><span data-stu-id="38d28-109">For example:</span></span>

  - <span data-ttu-id="38d28-p102">Код причины, предоставляемый шлюзом PSTN, которая привела к возникновению ошибки. Если происходит сбой в PSTN при обработке исходящего звонка, автоматически создается код причины ISUP. Например, шлюз PSTN может прислать код причины 34, говорящий о том, что для выполнения вызова нет доступного канала или цепи.</span><span class="sxs-lookup"><span data-stu-id="38d28-p102">The cause code provided by the PSTN gateway that generated the failure. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="38d28-113">Полное доменное имя узла, порт и WinSock для ошибок подключения.</span><span class="sxs-lookup"><span data-stu-id="38d28-113">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="38d28-p103">Запрашиваемые имена для ошибок разрешения DNS-имен. Разрешение DNS-имен выполняется при каждом обращении клиента к серверу имен и запросе IP-адреса, соответствующему указанному имени устройства.</span><span class="sxs-lookup"><span data-stu-id="38d28-p103">Names being looked up for DNS resolution failures. DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="38d28-116">Доступ к диагностическому отчету</span><span class="sxs-lookup"><span data-stu-id="38d28-116">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="38d28-117">Чтобы получить доступ к диагностическим отчетам, щелкните метрику диагностического отчета (Detail) в [отчете по деталям однорангового сеанса в Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) или подробный отчет по Конференции.</span><span class="sxs-lookup"><span data-stu-id="38d28-117">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="38d28-118">Фильтры</span><span class="sxs-lookup"><span data-stu-id="38d28-118">Filters</span></span>

<span data-ttu-id="38d28-p104">Нет. В диагностическом отчете нельзя использовать фильтр.</span><span class="sxs-lookup"><span data-stu-id="38d28-p104">None. You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="38d28-121">Метрики</span><span class="sxs-lookup"><span data-stu-id="38d28-121">Metrics</span></span>

<span data-ttu-id="38d28-122">В следующей таблице перечислены сведения, содержащиеся в диагностическом отчете.</span><span class="sxs-lookup"><span data-stu-id="38d28-122">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="38d28-123">Показатели отчета Diagnostic Report (Диагностический отчет)</span><span class="sxs-lookup"><span data-stu-id="38d28-123">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38d28-124">Имя</span><span class="sxs-lookup"><span data-stu-id="38d28-124">Name</span></span></th>
<th><span data-ttu-id="38d28-125">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="38d28-125">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="38d28-126">Описание</span><span class="sxs-lookup"><span data-stu-id="38d28-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38d28-127"><strong>Reported time</strong> (Время создания отчета)</span><span class="sxs-lookup"><span data-stu-id="38d28-127"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="38d28-128">Нет</span><span class="sxs-lookup"><span data-stu-id="38d28-128">No</span></span></p></td>
<td><p><span data-ttu-id="38d28-129">Дата и время создания отчета.</span><span class="sxs-lookup"><span data-stu-id="38d28-129">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d28-130"><strong>Response code</strong> (Код ответа)</span><span class="sxs-lookup"><span data-stu-id="38d28-130"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="38d28-131">Нет</span><span class="sxs-lookup"><span data-stu-id="38d28-131">No</span></span></p></td>
<td><p><span data-ttu-id="38d28-132">Код ответа SIP, отправленный при сбое сеанса.</span><span class="sxs-lookup"><span data-stu-id="38d28-132">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d28-133"><strong>Request type</strong> (Тип запроса)</span><span class="sxs-lookup"><span data-stu-id="38d28-133"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="38d28-134">Нет</span><span class="sxs-lookup"><span data-stu-id="38d28-134">No</span></span></p></td>
<td><p><span data-ttu-id="38d28-p105">Тип запроса SIP, завершившегося с ошибкой. Например, INVITE, BYE или SERVICE.</span><span class="sxs-lookup"><span data-stu-id="38d28-p105">SIP request type that failed. For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d28-137"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="38d28-137"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="38d28-138">Нет</span><span class="sxs-lookup"><span data-stu-id="38d28-138">No</span></span></p></td>
<td><p><span data-ttu-id="38d28-139">Источник ошибки.</span><span class="sxs-lookup"><span data-stu-id="38d28-139">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d28-140"><strong>From user URI</strong> (URI пользователя, инициатора сеанса)</span><span class="sxs-lookup"><span data-stu-id="38d28-140"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="38d28-141">Нет</span><span class="sxs-lookup"><span data-stu-id="38d28-141">No</span></span></p></td>
<td><p><span data-ttu-id="38d28-142">SIP-адрес пользователя, инициировавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="38d28-142">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d28-143"><strong>From user agent</strong> (Агент пользователя, инициатора сеанса)</span><span class="sxs-lookup"><span data-stu-id="38d28-143"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="38d28-144">Нет</span><span class="sxs-lookup"><span data-stu-id="38d28-144">No</span></span></p></td>
<td><p><span data-ttu-id="38d28-145">Программное обеспечение, используемое конечной точкой пользователя, инициировавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="38d28-145">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d28-146"><strong>Diagnostic ID</strong> (ИД диагностики)</span><span class="sxs-lookup"><span data-stu-id="38d28-146"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="38d28-147">Нет</span><span class="sxs-lookup"><span data-stu-id="38d28-147">No</span></span></p></td>
<td><p><span data-ttu-id="38d28-148">Уникальный идентификатор (в форме заголовка ms-diagnostics), присоединенный к сообщению SIP, который часто содержит сведения, помогающий устранять ошибки.</span><span class="sxs-lookup"><span data-stu-id="38d28-148">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d28-149"><strong>Content type</strong> (Тип содержимого)</span><span class="sxs-lookup"><span data-stu-id="38d28-149"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="38d28-150">Нет</span><span class="sxs-lookup"><span data-stu-id="38d28-150">No</span></span></p></td>
<td><p><span data-ttu-id="38d28-p106">Тип содержимого мультимедиа, которое привело к ошибке. Например, общий тип содержимого Application/sdp. Протокол SDP — это стандартный протокол Интернета, который используется для оповещений сеансов, приглашений сеансов и других видов инициирования сеансов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="38d28-p106">Type of media content that failed. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d28-154"><strong>Приложение</strong></span><span class="sxs-lookup"><span data-stu-id="38d28-154"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="38d28-155">Нет</span><span class="sxs-lookup"><span data-stu-id="38d28-155">No</span></span></p></td>
<td><p><span data-ttu-id="38d28-156">Приложение, используемое при возникновении ошибки.</span><span class="sxs-lookup"><span data-stu-id="38d28-156">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d28-157"><strong>To user URI</strong> (URI пользователя, получившего приглашение к сеансу)</span><span class="sxs-lookup"><span data-stu-id="38d28-157"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="38d28-158">Нет</span><span class="sxs-lookup"><span data-stu-id="38d28-158">No</span></span></p></td>
<td><p><span data-ttu-id="38d28-159">SIP-адрес пользователя, получившего приглашение к сеансу.</span><span class="sxs-lookup"><span data-stu-id="38d28-159">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d28-160">Время присоединения к конференции (мс)</span><span class="sxs-lookup"><span data-stu-id="38d28-160">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="38d28-161">Нет</span><span class="sxs-lookup"><span data-stu-id="38d28-161">No</span></span></p></td>
<td><p><span data-ttu-id="38d28-162">Период времени (в миллисекундах), требуемый для присоединения пользователя к конференции.</span><span class="sxs-lookup"><span data-stu-id="38d28-162">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d28-163"><strong>Diagnostic header</strong> (Заголовок диагностики)</span><span class="sxs-lookup"><span data-stu-id="38d28-163"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="38d28-164">Нет</span><span class="sxs-lookup"><span data-stu-id="38d28-164">No</span></span></p></td>
<td><p><span data-ttu-id="38d28-165">Описание ИД диагностики.</span><span class="sxs-lookup"><span data-stu-id="38d28-165">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="38d28-166">Список ошибок диагностики можно найти на [странице заголовков MS-Diagnostics](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span><span class="sxs-lookup"><span data-stu-id="38d28-166">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

