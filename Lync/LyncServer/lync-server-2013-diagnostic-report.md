---
title: 'Lync Server 2013: диагностический отчет'
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
ms.openlocfilehash: 14a2fa69e0e2397b970850a91042f0241060f839
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="1f8d6-102">Диагностический отчет в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f8d6-102">Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f8d6-103">_**Тема последнего изменения:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="1f8d6-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="1f8d6-104">Диагностический отчет предоставляет сведения о сеансах, которые завершились с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-104">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="1f8d6-105">Эти сведения включают ИД диагностики и диагностический заголовок, переданные при сбое сеанса.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-105">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="1f8d6-106">ИД диагностики – это уникальный идентификатор (в виде заголовка ms-diagnostics), который возвращает добавленное сообщение SIP, а диагностический заголовок содержит дополнительное описание ИД диагностики.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-106">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="1f8d6-107">Отчет также может содержать дополнительные сведения об устранении неполадок, предоставляемые компонентом создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-107">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="1f8d6-108">Пример:</span><span class="sxs-lookup"><span data-stu-id="1f8d6-108">For example:</span></span>

  - <span data-ttu-id="1f8d6-p102">Код причины, предоставляемый шлюзом PSTN, которая привела к возникновению ошибки. Если происходит сбой в PSTN при обработке исходящего звонка, автоматически создается код причины ISUP. Например, шлюз PSTN может прислать код причины 34, говорящий о том, что для выполнения вызова нет доступного канала или цепи.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-p102">The cause code provided by the PSTN gateway that generated the failure. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="1f8d6-112">Полное доменное имя узла, порт и WinSock для ошибок подключения.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-112">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="1f8d6-p103">Запрашиваемые имена для ошибок разрешения DNS-имен. Разрешение DNS-имен выполняется при каждом обращении клиента к серверу имен и запросе IP-адреса, соответствующему указанному имени устройства.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-p103">Names being looked up for DNS resolution failures. DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="1f8d6-115">Доступ к диагностическому отчету</span><span class="sxs-lookup"><span data-stu-id="1f8d6-115">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="1f8d6-116">Отчет о диагностике можно получить, щелкнув метрику диагностического отчета (подробности) в [отчете о одноранговых сеансах в Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) или в отчете "сведения о конференции".</span><span class="sxs-lookup"><span data-stu-id="1f8d6-116">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1f8d6-117">Фильтры</span><span class="sxs-lookup"><span data-stu-id="1f8d6-117">Filters</span></span>

<span data-ttu-id="1f8d6-p104">Нет. В диагностическом отчете нельзя использовать фильтр.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-p104">None. You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="1f8d6-120">Показатели</span><span class="sxs-lookup"><span data-stu-id="1f8d6-120">Metrics</span></span>

<span data-ttu-id="1f8d6-121">В следующей таблице перечислены сведения, содержащиеся в диагностическом отчете.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-121">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="1f8d6-122">Показатели отчета Diagnostic Report (Диагностический отчет)</span><span class="sxs-lookup"><span data-stu-id="1f8d6-122">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f8d6-123">Имя</span><span class="sxs-lookup"><span data-stu-id="1f8d6-123">Name</span></span></th>
<th><span data-ttu-id="1f8d6-124">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="1f8d6-124">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1f8d6-125">Описание</span><span class="sxs-lookup"><span data-stu-id="1f8d6-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f8d6-126"><strong>Время создания отчета</strong></span><span class="sxs-lookup"><span data-stu-id="1f8d6-126"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="1f8d6-127">Нет</span><span class="sxs-lookup"><span data-stu-id="1f8d6-127">No</span></span></p></td>
<td><p><span data-ttu-id="1f8d6-128">Дата и время создания отчета.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-128">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f8d6-129"><strong>Код ответа</strong></span><span class="sxs-lookup"><span data-stu-id="1f8d6-129"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="1f8d6-130">Нет</span><span class="sxs-lookup"><span data-stu-id="1f8d6-130">No</span></span></p></td>
<td><p><span data-ttu-id="1f8d6-131">Код ответа SIP, отправленный при сбое сеанса.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-131">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f8d6-132"><strong>Тип запроса</strong></span><span class="sxs-lookup"><span data-stu-id="1f8d6-132"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="1f8d6-133">Нет</span><span class="sxs-lookup"><span data-stu-id="1f8d6-133">No</span></span></p></td>
<td><p><span data-ttu-id="1f8d6-p105">Тип запроса SIP, завершившегося с ошибкой. Например, INVITE, BYE или SERVICE.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-p105">SIP request type that failed. For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f8d6-136"><strong>Источник</strong></span><span class="sxs-lookup"><span data-stu-id="1f8d6-136"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="1f8d6-137">Нет</span><span class="sxs-lookup"><span data-stu-id="1f8d6-137">No</span></span></p></td>
<td><p><span data-ttu-id="1f8d6-138">Источник ошибки.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-138">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f8d6-139"><strong>URI пользователя, инициатора сеанса</strong></span><span class="sxs-lookup"><span data-stu-id="1f8d6-139"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="1f8d6-140">Нет</span><span class="sxs-lookup"><span data-stu-id="1f8d6-140">No</span></span></p></td>
<td><p><span data-ttu-id="1f8d6-141">SIP-адрес пользователя, инициировавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-141">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f8d6-142"><strong>Агент пользователя, инициатора сеанса</strong></span><span class="sxs-lookup"><span data-stu-id="1f8d6-142"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="1f8d6-143">Нет</span><span class="sxs-lookup"><span data-stu-id="1f8d6-143">No</span></span></p></td>
<td><p><span data-ttu-id="1f8d6-144">Программное обеспечение, используемое конечной точкой пользователя, инициировавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-144">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f8d6-145"><strong>ИД диагностики</strong></span><span class="sxs-lookup"><span data-stu-id="1f8d6-145"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="1f8d6-146">Нет</span><span class="sxs-lookup"><span data-stu-id="1f8d6-146">No</span></span></p></td>
<td><p><span data-ttu-id="1f8d6-147">Прикрепленный к SIP-сообщению уникальный идентификатор (в форме заголовка ms-diagnostics), который часто содержит информацию, полезную при поиске и устранении ошибок.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-147">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f8d6-148"><strong>Тип содержимого</strong></span><span class="sxs-lookup"><span data-stu-id="1f8d6-148"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="1f8d6-149">Нет</span><span class="sxs-lookup"><span data-stu-id="1f8d6-149">No</span></span></p></td>
<td><p><span data-ttu-id="1f8d6-p106">Тип содержимого мультимедиа, которое привело к ошибке. Например, общий тип содержимого Application/sdp. Протокол SDP – это стандартный протокол Интернета, который используется для оповещений сеансов, приглашений сеансов и других видов инициирования сеансов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-p106">Type of media content that failed. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f8d6-153"><strong>Приложение</strong></span><span class="sxs-lookup"><span data-stu-id="1f8d6-153"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="1f8d6-154">Нет</span><span class="sxs-lookup"><span data-stu-id="1f8d6-154">No</span></span></p></td>
<td><p><span data-ttu-id="1f8d6-155">Приложение, используемое при возникновении ошибки.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-155">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f8d6-156"><strong>URI пользователя, получившего приглашение к сеансу</strong></span><span class="sxs-lookup"><span data-stu-id="1f8d6-156"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="1f8d6-157">Нет</span><span class="sxs-lookup"><span data-stu-id="1f8d6-157">No</span></span></p></td>
<td><p><span data-ttu-id="1f8d6-158">SIP-адрес пользователя, получившего приглашение к сеансу.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-158">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f8d6-159">Время присоединения к конференции (мс)</span><span class="sxs-lookup"><span data-stu-id="1f8d6-159">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="1f8d6-160">Нет</span><span class="sxs-lookup"><span data-stu-id="1f8d6-160">No</span></span></p></td>
<td><p><span data-ttu-id="1f8d6-161">Период времени (в миллисекундах), требуемый для присоединения пользователя к конференции.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-161">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f8d6-162"><strong>Заголовок диагностики</strong></span><span class="sxs-lookup"><span data-stu-id="1f8d6-162"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="1f8d6-163">Нет</span><span class="sxs-lookup"><span data-stu-id="1f8d6-163">No</span></span></p></td>
<td><p><span data-ttu-id="1f8d6-164">Описание ИД диагностики.</span><span class="sxs-lookup"><span data-stu-id="1f8d6-164">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1f8d6-165">Список ошибок диагностики можно найти на [странице заголовков MS-Diagnostics](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx).</span><span class="sxs-lookup"><span data-stu-id="1f8d6-165">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

