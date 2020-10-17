---
title: 'Lync Server 2013: отчет об одноранговом сеансе'
description: 'Lync Server 2013: подробный отчет о сеансе в одноранговой сети.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e712225fddabb646cc3b862f59601857a7df8eff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557285"
---
# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="9edb5-103">Отчет по деталям однорангового сеанса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9edb5-103">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9edb5-104">_**Последнее изменение темы:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="9edb5-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="9edb5-p101">Отчет по деталям однорангового сеанса (Peer-to-Peer Session Detail Report) предоставляет подробные сведения об одноранговом сеансе. Например, если выбрать сеанс обмена мгновенными сообщениями, то отчет предоставит сведения о количестве сообщений, отправленных в этом сеансе каждым из двух пользователей.</span><span class="sxs-lookup"><span data-stu-id="9edb5-p101">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session. For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="9edb5-107">Доступ к отчету по деталям однорангового сеанса</span><span class="sxs-lookup"><span data-stu-id="9edb5-107">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="9edb5-108">Отчет по деталям однорангового сеанса можно вызвать в любом из следующих отчетов (все они доступны на домашней странице отчетов мониторинга).</span><span class="sxs-lookup"><span data-stu-id="9edb5-108">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="9edb5-109">Отчет по запасам IP-телефонов (Phone Inventory Report)</span><span class="sxs-lookup"><span data-stu-id="9edb5-109">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="9edb5-110">Отчет по действиям пользователей (User Activity Report)</span><span class="sxs-lookup"><span data-stu-id="9edb5-110">User Activity Report</span></span>

  - <span data-ttu-id="9edb5-111">Отчет по контролю допуска звонков (Call Admission Control Report)</span><span class="sxs-lookup"><span data-stu-id="9edb5-111">Call Admission Control Report</span></span>

  - <span data-ttu-id="9edb5-112">Отчет по списку сбоев (Failure List Report)</span><span class="sxs-lookup"><span data-stu-id="9edb5-112">Failure List Report</span></span>

<span data-ttu-id="9edb5-113">В отчете по деталям однорангового сеанса можно получить доступ к [диагностическим отчетам в Lync Server 2013](lync-server-2013-diagnostic-report.md) , щелкнув метрику диагностического отчета (Details) (сведения).</span><span class="sxs-lookup"><span data-stu-id="9edb5-113">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="9edb5-114">Можно также вызвать отчет по основным сбоям (Top Failures Report), щелкнув одну из следующих метрик:</span><span class="sxs-lookup"><span data-stu-id="9edb5-114">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="9edb5-115">Отклик</span><span class="sxs-lookup"><span data-stu-id="9edb5-115">Response</span></span>

  - <span data-ttu-id="9edb5-116">Diagnostic ID (ИД диагностики)</span><span class="sxs-lookup"><span data-stu-id="9edb5-116">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="9edb5-117">Оптимальное использование отчета по деталям однорангового сеанса</span><span class="sxs-lookup"><span data-stu-id="9edb5-117">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="9edb5-p103">В отчете по деталям однорангового сеанса имеется большое количество метрик, многие из которых могут быть незнакомы системным администраторам. Однако во многих случаях при наведении указателя мыши на метку метрики отображаются всплывающие подсказки, дающие краткое описание этой метрики.</span><span class="sxs-lookup"><span data-stu-id="9edb5-p103">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators. Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="9edb5-p104">Следует отметить, что фактические метрики, которые отображаются в конкретном отчете, будут зависеть от типа выбранного однорангового сеанса. Для сеанса аудио- или видеосвязи и для сеанса обмена мгновенными сообщениями будут отображаться разные наборы метрик.</span><span class="sxs-lookup"><span data-stu-id="9edb5-p104">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected. An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="9edb5-122">Кроме того, поместив указатель мыши на метрику Response code (Код ответа) или Diagnostic ID (ИД диагностики), можно получить описание следующих значений.</span><span class="sxs-lookup"><span data-stu-id="9edb5-122">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="9edb5-123">Фильтры</span><span class="sxs-lookup"><span data-stu-id="9edb5-123">Filters</span></span>

<span data-ttu-id="9edb5-p105">Фильтры отсутствуют. Фильтрация отчета по деталям однорангового сеанса не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="9edb5-p105">None. You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="9edb5-126">Метрики сведений о сеансе</span><span class="sxs-lookup"><span data-stu-id="9edb5-126">Session Information Metrics</span></span>

<span data-ttu-id="9edb5-127">В следующей таблице приведены сведения, которые предоставляются отчетом по деталям однорангового сеанса для каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="9edb5-127">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="9edb5-128">Метрики сведений о сеансе</span><span class="sxs-lookup"><span data-stu-id="9edb5-128">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9edb5-129">Имя</span><span class="sxs-lookup"><span data-stu-id="9edb5-129">Name</span></span></th>
<th><span data-ttu-id="9edb5-130">Описание</span><span class="sxs-lookup"><span data-stu-id="9edb5-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9edb5-131"><strong>Pool FQDN (Полное доменное имя пула)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-131"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-132">Полное доменное имя пула регистратора или пограничного сервера, участвующего в сеансе.</span><span class="sxs-lookup"><span data-stu-id="9edb5-132">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9edb5-133"><strong>Invite time (Время приглашения)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-133"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-134">Дата и время, когда было отправлено приглашение принять участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="9edb5-134">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9edb5-135"><strong>Response time (Время ответа)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-135"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-136">Дата и время, когда было получено принятие приглашения.</span><span class="sxs-lookup"><span data-stu-id="9edb5-136">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9edb5-137"><strong>From user (Пользователь-инициатор)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-137"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-138">SIP-адрес пользователя, начавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="9edb5-138">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9edb5-139"><strong>From user agent (Агент пользователя-инициатора)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-139"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-140">Программное обеспечение, использовавшееся конечной точкой пользователя, начавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="9edb5-140">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9edb5-141"><strong>Is From user internal (Пользователь-инициатор внутренний?)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-141"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-142">Указывает, вошел ли пользователь, начавший сеанс, во внутреннюю сеть.</span><span class="sxs-lookup"><span data-stu-id="9edb5-142">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9edb5-143"><strong>Is From user integrated with desk phone (Пользователь-инициатор интегрирован со стационарным телефоном?)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-143"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-144">Указывает, интегрирована ли конечная точка пользователя, начавшего сеанс, с его стационарным телефоном.</span><span class="sxs-lookup"><span data-stu-id="9edb5-144">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9edb5-145"><strong>Session Priority (Приоритет сеанса)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-145"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-p106">Приоритет, назначенный сеансу. Возможные приоритеты: Unknown (Неизвестно); Non-Urgent (Несрочный); Normal (Обычный); Urgent (Срочный) и Emergency (Экстренный).</span><span class="sxs-lookup"><span data-stu-id="9edb5-p106">Priority assigned to the session. Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9edb5-148"><strong>Response code (Код ответа)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-148"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-149">SIP-код ответа, отправленный при сбое сеанса.</span><span class="sxs-lookup"><span data-stu-id="9edb5-149">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9edb5-150"><strong>Front end (Сервер переднего плана)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-150"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-151">Имя сервера переднего плана, использовавшегося в конференции.</span><span class="sxs-lookup"><span data-stu-id="9edb5-151">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9edb5-152"><strong>Capture time (Время регистрации)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-152"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-153">Дата и время регистрации сведений о сеансе.</span><span class="sxs-lookup"><span data-stu-id="9edb5-153">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9edb5-154"><strong>End time (Время окончания)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-154"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-155">Дата и время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="9edb5-155">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9edb5-156"><strong>To user (Пользователь-получатель)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-156"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-157">SIP-адрес пользователя, приглашенного принять участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="9edb5-157">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9edb5-158"><strong>To user agent (Агент пользователя-получателя)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-158"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-159">Программное обеспечение, использовавшееся конечной точкой пользователя, приглашенного принять участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="9edb5-159">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9edb5-160"><strong>Is To user internal (Пользователь-получатель внутренний?)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-160"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-161">Указывает, вошел ли пользователь, приглашенный принять участие в сеансе, во внутреннюю сеть.</span><span class="sxs-lookup"><span data-stu-id="9edb5-161">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9edb5-162"><strong>Is To user integrated with desk phone (Пользователь-получатель интегрирован со стационарным телефоном?)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-162"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-163">Указывает, интегрирована ли конечная точка пользователя, приглашенного принять участие в сеансе, с его стационарным телефоном.</span><span class="sxs-lookup"><span data-stu-id="9edb5-163">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9edb5-164"><strong>Is retried session (Повторный сеанс?)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-164"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-165">Указывает, являлся ли этот сеанс попыткой повтора сеанса, который завершился неудачно.</span><span class="sxs-lookup"><span data-stu-id="9edb5-165">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9edb5-166"><strong>Diagnostic ID (ИД диагностики)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-166"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-p107">Уникальный идентификатор (в форме заголовка ms-diagnostics), присоединенный к сообщению SIP, который часто содержит сведения, помогающий устранять ошибки. Поместите указатель мыши на этот идентификатор, чтобы увидеть дополнительные сведения о нем.</span><span class="sxs-lookup"><span data-stu-id="9edb5-p107">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="9edb5-169">Метрики для модальностей</span><span class="sxs-lookup"><span data-stu-id="9edb5-169">Metrics for Modalities</span></span>

<span data-ttu-id="9edb5-170">В следующей таблице приведены сведения, которые предоставляются отчетом по деталям однорангового сеанса для всех модальностей сеанса.</span><span class="sxs-lookup"><span data-stu-id="9edb5-170">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="9edb5-171">Метрики для модальностей</span><span class="sxs-lookup"><span data-stu-id="9edb5-171">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9edb5-172">Имя</span><span class="sxs-lookup"><span data-stu-id="9edb5-172">Name</span></span></th>
<th><span data-ttu-id="9edb5-173">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="9edb5-173">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9edb5-174">Описание</span><span class="sxs-lookup"><span data-stu-id="9edb5-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9edb5-175"><strong>Модальности</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-175"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-176">Нет</span><span class="sxs-lookup"><span data-stu-id="9edb5-176">No</span></span></p></td>
<td><p><span data-ttu-id="9edb5-p108">Модальности, использованные в сеансе, например, обмен мгновенными сообщениями или передача файла.</span><span class="sxs-lookup"><span data-stu-id="9edb5-p108">Modalities used in the session. For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9edb5-179"><strong>From user messages (Сообщения пользователя-инициатора)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-179"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-180">Нет</span><span class="sxs-lookup"><span data-stu-id="9edb5-180">No</span></span></p></td>
<td><p><span data-ttu-id="9edb5-181">Количество сообщений, отправленных пользователем, начавшим сеанс.</span><span class="sxs-lookup"><span data-stu-id="9edb5-181">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9edb5-182"><strong>To user messages (Сообщения пользователя-получателя)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-182"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-183">Нет</span><span class="sxs-lookup"><span data-stu-id="9edb5-183">No</span></span></p></td>
<td><p><span data-ttu-id="9edb5-184">Количество сообщений, отправленных пользователем, приглашенным принять участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="9edb5-184">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="9edb5-185">Метрики для диагностических отчетов</span><span class="sxs-lookup"><span data-stu-id="9edb5-185">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="9edb5-186">В следующей таблице приведены сведения, которые отчет по деталям однорангового сеанса предоставляет для каждого диагностического отчета.</span><span class="sxs-lookup"><span data-stu-id="9edb5-186">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="9edb5-187">Метрики для диагностических отчетов</span><span class="sxs-lookup"><span data-stu-id="9edb5-187">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9edb5-188">Имя</span><span class="sxs-lookup"><span data-stu-id="9edb5-188">Name</span></span></th>
<th><span data-ttu-id="9edb5-189">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="9edb5-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9edb5-190">Описание</span><span class="sxs-lookup"><span data-stu-id="9edb5-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9edb5-191"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-191"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-192">Нет</span><span class="sxs-lookup"><span data-stu-id="9edb5-192">No</span></span></p></td>
<td><p><span data-ttu-id="9edb5-193">При нажатии этой метрики отображается диагностический отчет для данного сеанса.</span><span class="sxs-lookup"><span data-stu-id="9edb5-193">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9edb5-194"><strong>Report time (Время отчета)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-194"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-195">Нет</span><span class="sxs-lookup"><span data-stu-id="9edb5-195">No</span></span></p></td>
<td><p><span data-ttu-id="9edb5-196">Дата и время создания отчета.</span><span class="sxs-lookup"><span data-stu-id="9edb5-196">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9edb5-197"><strong>Запрос</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-197"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-198">Нет</span><span class="sxs-lookup"><span data-stu-id="9edb5-198">No</span></span></p></td>
<td><p><span data-ttu-id="9edb5-p109">SIP-тип запроса. Например, INVITE или BYE.</span><span class="sxs-lookup"><span data-stu-id="9edb5-p109">SIP request type. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9edb5-201"><strong>Diagnostic ID (ИД диагностики)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-201"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-202">Нет</span><span class="sxs-lookup"><span data-stu-id="9edb5-202">No</span></span></p></td>
<td><p><span data-ttu-id="9edb5-203">Уникальный идентификатор (в форме заголовка ms-diagnostics), присоединенный к сообщению SIP, который часто содержит сведения, помогающий устранять ошибки.</span><span class="sxs-lookup"><span data-stu-id="9edb5-203">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9edb5-204"><strong>Content type</strong> (Тип содержимого)</span><span class="sxs-lookup"><span data-stu-id="9edb5-204"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-205">Нет</span><span class="sxs-lookup"><span data-stu-id="9edb5-205">No</span></span></p></td>
<td><p><span data-ttu-id="9edb5-p110">Тип контента мультимедиа, использовавшегося в конференции. Например, распространенным типом контента является Application/sdp. Протокол SDP — это стандартный Интернет-протокол, используемый для объявления о сеансе, приглашения принять участие в сеансе и других форм инициации сеанса мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="9edb5-p110">Type of media content used in the conference. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9edb5-209"><strong>Reported by (Сообщил)</strong></span><span class="sxs-lookup"><span data-stu-id="9edb5-209"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="9edb5-210">Нет</span><span class="sxs-lookup"><span data-stu-id="9edb5-210">No</span></span></p></td>
<td><p><span data-ttu-id="9edb5-211">Компьютер (клиент или сервер), который сообщил о проблеме.</span><span class="sxs-lookup"><span data-stu-id="9edb5-211">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

