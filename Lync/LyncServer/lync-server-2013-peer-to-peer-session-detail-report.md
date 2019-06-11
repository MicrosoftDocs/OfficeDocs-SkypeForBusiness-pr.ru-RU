---
title: 'Lync Server 2013: одноранговый отчет о сеансе'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec73febb248a8b61979c0aad2df6977c9feccb91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="9366f-102">Отчет о одноранговых сеансах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9366f-102">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9366f-103">_**Тема последнего изменения:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="9366f-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="9366f-p101">Отчет по деталям однорангового сеанса (Peer-to-Peer Session Detail Report) предоставляет подробные сведения об одноранговом сеансе. Например, если выбрать сеанс обмена мгновенными сообщениями, то отчет предоставит сведения о количестве сообщений, отправленных в этом сеансе каждым из двух пользователей.</span><span class="sxs-lookup"><span data-stu-id="9366f-p101">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session. For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="9366f-106">Доступ к отчету по деталям однорангового сеанса</span><span class="sxs-lookup"><span data-stu-id="9366f-106">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="9366f-107">Отчет по деталям однорангового сеанса можно вызвать в любом из следующих отчетов (все они доступны на домашней странице отчетов мониторинга).</span><span class="sxs-lookup"><span data-stu-id="9366f-107">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="9366f-108">Отчет по инвентарю IP-телефонов</span><span class="sxs-lookup"><span data-stu-id="9366f-108">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="9366f-109">Отчет по активности пользователей</span><span class="sxs-lookup"><span data-stu-id="9366f-109">User Activity Report</span></span>

  - <span data-ttu-id="9366f-110">Отчет по контролю допуска звонков</span><span class="sxs-lookup"><span data-stu-id="9366f-110">Call Admission Control Report</span></span>

  - <span data-ttu-id="9366f-111">Отчет по списку отказов</span><span class="sxs-lookup"><span data-stu-id="9366f-111">Failure List Report</span></span>

<span data-ttu-id="9366f-112">В отчете сведения о одноранговых сеансах вы можете получить доступ к [отчету диагностики в Lync Server 2013](lync-server-2013-diagnostic-report.md) , щелкнув метрику диагностического отчета (подробности).</span><span class="sxs-lookup"><span data-stu-id="9366f-112">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="9366f-113">Можно также вызвать отчет по основным сбоям (Top Failures Report), щелкнув одну из следующих метрик:</span><span class="sxs-lookup"><span data-stu-id="9366f-113">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="9366f-114">Response (Ответ)</span><span class="sxs-lookup"><span data-stu-id="9366f-114">Response</span></span>

  - <span data-ttu-id="9366f-115">Диагностический идентификатор</span><span class="sxs-lookup"><span data-stu-id="9366f-115">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="9366f-116">Оптимальное использование отчета по деталям однорангового сеанса</span><span class="sxs-lookup"><span data-stu-id="9366f-116">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="9366f-p103">В отчете по деталям однорангового сеанса имеется большое количество метрик, многие из которых могут быть незнакомы системным администраторам. Однако во многих случаях при наведении указателя мыши на метку метрики отображаются всплывающие подсказки, дающие краткое описание этой метрики.</span><span class="sxs-lookup"><span data-stu-id="9366f-p103">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators. Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="9366f-p104">Следует отметить, что фактические метрики, которые отображаются в конкретном отчете, будут зависеть от типа выбранного однорангового сеанса. Для сеанса аудио- или видеосвязи и для сеанса обмена мгновенными сообщениями будут отображаться разные наборы метрик.</span><span class="sxs-lookup"><span data-stu-id="9366f-p104">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected. An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="9366f-121">Кроме того, поместив указатель мыши на метрику Response code (Код ответа) или Diagnostic ID (ИД диагностики), можно получить описание следующих значений.</span><span class="sxs-lookup"><span data-stu-id="9366f-121">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="9366f-122">Фильтры</span><span class="sxs-lookup"><span data-stu-id="9366f-122">Filters</span></span>

<span data-ttu-id="9366f-p105">Фильтры отсутствуют. Фильтрация отчета по деталям однорангового сеанса не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="9366f-p105">None. You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="9366f-125">Метрики сведений о сеансе</span><span class="sxs-lookup"><span data-stu-id="9366f-125">Session Information Metrics</span></span>

<span data-ttu-id="9366f-126">В следующей таблице приведены сведения, которые предоставляются отчетом по деталям однорангового сеанса для каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="9366f-126">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="9366f-127">Метрики сведений о сеансе</span><span class="sxs-lookup"><span data-stu-id="9366f-127">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9366f-128">Имя</span><span class="sxs-lookup"><span data-stu-id="9366f-128">Name</span></span></th>
<th><span data-ttu-id="9366f-129">Описание</span><span class="sxs-lookup"><span data-stu-id="9366f-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9366f-130"><strong>Полное доменное имя пула</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-130"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-131">Полное доменное имя пула регистратора или пограничного сервера, участвующего в сеансе.</span><span class="sxs-lookup"><span data-stu-id="9366f-131">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9366f-132"><strong>Invite time (Время приглашения)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-132"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-133">Дата и время, когда было отправлено приглашение принять участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="9366f-133">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9366f-134"><strong>Response time (Время ответа)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-134"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-135">Дата и время, когда было получено принятие приглашения.</span><span class="sxs-lookup"><span data-stu-id="9366f-135">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9366f-136"><strong>From user (Пользователь-отправитель)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-136"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-137">SIP-адрес пользователя, инициировавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="9366f-137">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9366f-138"><strong>From user agent (Агент пользователя, инициатора сеанса)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-138"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-139">Программное обеспечение, используемое конечной точкой пользователя, инициировавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="9366f-139">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9366f-140"><strong>Is From user internal (Пользователь-инициатор внутренний?)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-140"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-141">Указывает, вошел ли пользователь, начавший сеанс, во внутреннюю сеть.</span><span class="sxs-lookup"><span data-stu-id="9366f-141">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9366f-142"><strong>Is From user integrated with desk phone (Пользователь-инициатор интегрирован со стационарным телефоном?)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-142"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-143">Указывает, интегрирована ли конечная точка пользователя, начавшего сеанс, с его стационарным телефоном.</span><span class="sxs-lookup"><span data-stu-id="9366f-143">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9366f-144"><strong>Session Priority (Приоритет сеанса)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-144"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-p106">Приоритет, назначенный сеансу. Возможные приоритеты: Unknown (Неизвестно); Non-Urgent (Несрочный); Normal (Обычный); Urgent (Срочный) и Emergency (Экстренный).</span><span class="sxs-lookup"><span data-stu-id="9366f-p106">Priority assigned to the session. Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9366f-147"><strong>Response code (Код ответа)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-147"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-148">Код ответа SIP, отправленный при сбое сеанса.</span><span class="sxs-lookup"><span data-stu-id="9366f-148">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9366f-149"><strong>Front end (Сервер переднего плана)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-149"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-150">Имя сервера переднего плана, использовавшегося в конференции.</span><span class="sxs-lookup"><span data-stu-id="9366f-150">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9366f-151"><strong>Capture time (Время регистрации)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-151"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-152">Дата и время регистрации сведений о сеансе.</span><span class="sxs-lookup"><span data-stu-id="9366f-152">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9366f-153"><strong>End time (Время окончания)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-153"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-154">Дата и время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="9366f-154">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9366f-155"><strong>To user (Пользователь-получатель)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-155"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-156">SIP-адрес пользователя, получившего приглашение к сеансу.</span><span class="sxs-lookup"><span data-stu-id="9366f-156">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9366f-157"><strong>To user agent (Агент пользователя-получателя)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-157"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-158">Программное обеспечение, использовавшееся конечной точкой пользователя, приглашенного принять участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="9366f-158">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9366f-159"><strong>Is To user internal (Пользователь-получатель внутренний?)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-159"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-160">Указывает, вошел ли пользователь, приглашенный принять участие в сеансе, во внутреннюю сеть.</span><span class="sxs-lookup"><span data-stu-id="9366f-160">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9366f-161"><strong>Is To user integrated with desk phone (Пользователь-получатель интегрирован со стационарным телефоном?)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-161"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-162">Указывает, интегрирована ли конечная точка пользователя, приглашенного принять участие в сеансе, с его стационарным телефоном.</span><span class="sxs-lookup"><span data-stu-id="9366f-162">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9366f-163"><strong>Is retried session (Повторный сеанс?)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-163"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-164">Указывает, являлся ли этот сеанс попыткой повтора сеанса, который завершился неудачно.</span><span class="sxs-lookup"><span data-stu-id="9366f-164">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9366f-165"><strong>Диагностический идентификатор</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-165"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-p107">Уникальный идентификатор (в форме заголовка ms-diagnostics), присоединенный к сообщению SIP, который часто содержит сведения, помогающий устранять ошибки. Поместите указатель мыши на этот идентификатор, чтобы увидеть дополнительные сведения о нем.</span><span class="sxs-lookup"><span data-stu-id="9366f-p107">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="9366f-168">Метрики для модальностей</span><span class="sxs-lookup"><span data-stu-id="9366f-168">Metrics for Modalities</span></span>

<span data-ttu-id="9366f-169">В следующей таблице приведены сведения, которые предоставляются отчетом по деталям однорангового сеанса для всех модальностей сеанса.</span><span class="sxs-lookup"><span data-stu-id="9366f-169">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="9366f-170">Метрики для модальностей</span><span class="sxs-lookup"><span data-stu-id="9366f-170">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9366f-171">Имя</span><span class="sxs-lookup"><span data-stu-id="9366f-171">Name</span></span></th>
<th><span data-ttu-id="9366f-172">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="9366f-172">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9366f-173">Описание</span><span class="sxs-lookup"><span data-stu-id="9366f-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9366f-174"><strong>Modalities (Модальности)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-174"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-175">Нет</span><span class="sxs-lookup"><span data-stu-id="9366f-175">No</span></span></p></td>
<td><p><span data-ttu-id="9366f-p108">Модальности, использованные в сеансе, например, обмен мгновенными сообщениями или передача файла.</span><span class="sxs-lookup"><span data-stu-id="9366f-p108">Modalities used in the session. For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9366f-178"><strong>From user messages (Сообщения пользователя-инициатора)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-178"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-179">Нет</span><span class="sxs-lookup"><span data-stu-id="9366f-179">No</span></span></p></td>
<td><p><span data-ttu-id="9366f-180">Количество сообщений, отправленных пользователем, начавшим сеанс.</span><span class="sxs-lookup"><span data-stu-id="9366f-180">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9366f-181"><strong>To user messages (Сообщения пользователя-получателя)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-181"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-182">Нет</span><span class="sxs-lookup"><span data-stu-id="9366f-182">No</span></span></p></td>
<td><p><span data-ttu-id="9366f-183">Количество сообщений, отправленных пользователем, приглашенным принять участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="9366f-183">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="9366f-184">Метрики для диагностических отчетов</span><span class="sxs-lookup"><span data-stu-id="9366f-184">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="9366f-185">В следующей таблице приведены сведения, которые отчет по деталям однорангового сеанса предоставляет для каждого диагностического отчета.</span><span class="sxs-lookup"><span data-stu-id="9366f-185">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="9366f-186">Метрики для диагностических отчетов</span><span class="sxs-lookup"><span data-stu-id="9366f-186">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9366f-187">Имя</span><span class="sxs-lookup"><span data-stu-id="9366f-187">Name</span></span></th>
<th><span data-ttu-id="9366f-188">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="9366f-188">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9366f-189">Описание</span><span class="sxs-lookup"><span data-stu-id="9366f-189">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9366f-190"><strong>Подробности</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-190"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-191">Нет</span><span class="sxs-lookup"><span data-stu-id="9366f-191">No</span></span></p></td>
<td><p><span data-ttu-id="9366f-192">При нажатии этой метрики отображается диагностический отчет для данного сеанса.</span><span class="sxs-lookup"><span data-stu-id="9366f-192">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9366f-193"><strong>Reported time (Время создания отчета)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-193"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-194">Нет</span><span class="sxs-lookup"><span data-stu-id="9366f-194">No</span></span></p></td>
<td><p><span data-ttu-id="9366f-195">Дата и время создания отчета.</span><span class="sxs-lookup"><span data-stu-id="9366f-195">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9366f-196"><strong>Запрос</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-196"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-197">Нет</span><span class="sxs-lookup"><span data-stu-id="9366f-197">No</span></span></p></td>
<td><p><span data-ttu-id="9366f-p109">SIP-тип запроса. Например, INVITE или BYE.</span><span class="sxs-lookup"><span data-stu-id="9366f-p109">SIP request type. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9366f-200"><strong>Diagnostic ID (ИД диагностики)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-200"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-201">Нет</span><span class="sxs-lookup"><span data-stu-id="9366f-201">No</span></span></p></td>
<td><p><span data-ttu-id="9366f-202">Прикрепленный к SIP-сообщению уникальный идентификатор (в форме заголовка ms-diagnostics), который часто содержит информацию, полезную при поиске и устранении ошибок.</span><span class="sxs-lookup"><span data-stu-id="9366f-202">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9366f-203"><strong>Тип содержимого</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-203"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-204">Нет</span><span class="sxs-lookup"><span data-stu-id="9366f-204">No</span></span></p></td>
<td><p><span data-ttu-id="9366f-p110">Тип контента мультимедиа, использовавшегося в конференции. Например, распространенным типом контента является Application/sdp. Протокол SDP – это стандартный Интернет-протокол, используемый для объявления о сеансе, приглашения принять участие в сеансе и других форм инициации сеанса мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="9366f-p110">Type of media content used in the conference. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9366f-208"><strong>Reported by (Сообщил)</strong></span><span class="sxs-lookup"><span data-stu-id="9366f-208"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="9366f-209">Нет</span><span class="sxs-lookup"><span data-stu-id="9366f-209">No</span></span></p></td>
<td><p><span data-ttu-id="9366f-210">Компьютер (клиент или сервер), который сообщил о проблеме.</span><span class="sxs-lookup"><span data-stu-id="9366f-210">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

