---
title: 'Lync Server 2013: отчет об одноранговом сеансе'
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
ms.openlocfilehash: c977b2f9f9a6248ab7ba5d5391397d4cd4326a18
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="cbced-102">Отчет по деталям однорангового сеанса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbced-102">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbced-103">_**Последнее изменение темы:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="cbced-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="cbced-p101">Отчет по деталям однорангового сеанса (Peer-to-Peer Session Detail Report) предоставляет подробные сведения об одноранговом сеансе. Например, если выбрать сеанс обмена мгновенными сообщениями, то отчет предоставит сведения о количестве сообщений, отправленных в этом сеансе каждым из двух пользователей.</span><span class="sxs-lookup"><span data-stu-id="cbced-p101">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session. For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="cbced-106">Доступ к отчету по деталям однорангового сеанса</span><span class="sxs-lookup"><span data-stu-id="cbced-106">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="cbced-107">Отчет по деталям однорангового сеанса можно вызвать в любом из следующих отчетов (все они доступны на домашней странице отчетов мониторинга).</span><span class="sxs-lookup"><span data-stu-id="cbced-107">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="cbced-108">Отчет по запасам IP-телефонов (Phone Inventory Report)</span><span class="sxs-lookup"><span data-stu-id="cbced-108">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="cbced-109">Отчет по действиям пользователей (User Activity Report)</span><span class="sxs-lookup"><span data-stu-id="cbced-109">User Activity Report</span></span>

  - <span data-ttu-id="cbced-110">Отчет по контролю допуска звонков (Call Admission Control Report)</span><span class="sxs-lookup"><span data-stu-id="cbced-110">Call Admission Control Report</span></span>

  - <span data-ttu-id="cbced-111">Отчет по списку сбоев (Failure List Report)</span><span class="sxs-lookup"><span data-stu-id="cbced-111">Failure List Report</span></span>

<span data-ttu-id="cbced-112">В отчете по деталям однорангового сеанса можно получить доступ к [диагностическим отчетам в Lync Server 2013](lync-server-2013-diagnostic-report.md) , щелкнув метрику диагностического отчета (Details) (сведения).</span><span class="sxs-lookup"><span data-stu-id="cbced-112">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="cbced-113">Можно также вызвать отчет по основным сбоям (Top Failures Report), щелкнув одну из следующих метрик:</span><span class="sxs-lookup"><span data-stu-id="cbced-113">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="cbced-114">Отклик</span><span class="sxs-lookup"><span data-stu-id="cbced-114">Response</span></span>

  - <span data-ttu-id="cbced-115">Код диагностики</span><span class="sxs-lookup"><span data-stu-id="cbced-115">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="cbced-116">Оптимальное использование отчета по деталям однорангового сеанса</span><span class="sxs-lookup"><span data-stu-id="cbced-116">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="cbced-p103">В отчете по деталям однорангового сеанса имеется большое количество метрик, многие из которых могут быть незнакомы системным администраторам. Однако во многих случаях при наведении указателя мыши на метку метрики отображаются всплывающие подсказки, дающие краткое описание этой метрики.</span><span class="sxs-lookup"><span data-stu-id="cbced-p103">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators. Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="cbced-p104">Следует отметить, что фактические метрики, которые отображаются в конкретном отчете, будут зависеть от типа выбранного однорангового сеанса. Для сеанса аудио- или видеосвязи и для сеанса обмена мгновенными сообщениями будут отображаться разные наборы метрик.</span><span class="sxs-lookup"><span data-stu-id="cbced-p104">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected. An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="cbced-121">Кроме того, поместив указатель мыши на метрику Response code (Код ответа) или Diagnostic ID (ИД диагностики), можно получить описание следующих значений.</span><span class="sxs-lookup"><span data-stu-id="cbced-121">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="cbced-122">Фильтры</span><span class="sxs-lookup"><span data-stu-id="cbced-122">Filters</span></span>

<span data-ttu-id="cbced-p105">Фильтры отсутствуют. Фильтрация отчета по деталям однорангового сеанса не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="cbced-p105">None. You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="cbced-125">Метрики сведений о сеансе</span><span class="sxs-lookup"><span data-stu-id="cbced-125">Session Information Metrics</span></span>

<span data-ttu-id="cbced-126">В следующей таблице приведены сведения, которые предоставляются отчетом по деталям однорангового сеанса для каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="cbced-126">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="cbced-127">Метрики сведений о сеансе</span><span class="sxs-lookup"><span data-stu-id="cbced-127">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbced-128">Имя</span><span class="sxs-lookup"><span data-stu-id="cbced-128">Name</span></span></th>
<th><span data-ttu-id="cbced-129">Описание</span><span class="sxs-lookup"><span data-stu-id="cbced-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbced-130"><strong>Pool FQDN (Полное доменное имя пула)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-130"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-131">Полное доменное имя пула регистратора или пограничного сервера, участвующего в сеансе.</span><span class="sxs-lookup"><span data-stu-id="cbced-131">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbced-132"><strong>Invite time (Время приглашения)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-132"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-133">Дата и время, когда было отправлено приглашение принять участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="cbced-133">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbced-134"><strong>Response time (Время ответа)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-134"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-135">Дата и время, когда было получено принятие приглашения.</span><span class="sxs-lookup"><span data-stu-id="cbced-135">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbced-136"><strong>From user (Пользователь-инициатор)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-136"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-137">SIP-адрес пользователя, начавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="cbced-137">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbced-138"><strong>From user agent (Агент пользователя-инициатора)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-138"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-139">Программное обеспечение, использовавшееся конечной точкой пользователя, начавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="cbced-139">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbced-140"><strong>Is From user internal (Пользователь-инициатор внутренний?)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-140"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-141">Указывает, вошел ли пользователь, начавший сеанс, во внутреннюю сеть.</span><span class="sxs-lookup"><span data-stu-id="cbced-141">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbced-142"><strong>Is From user integrated with desk phone (Пользователь-инициатор интегрирован со стационарным телефоном?)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-142"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-143">Указывает, интегрирована ли конечная точка пользователя, начавшего сеанс, с его стационарным телефоном.</span><span class="sxs-lookup"><span data-stu-id="cbced-143">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbced-144"><strong>Session Priority (Приоритет сеанса)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-144"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-p106">Приоритет, назначенный сеансу. Возможные приоритеты: Unknown (Неизвестно); Non-Urgent (Несрочный); Normal (Обычный); Urgent (Срочный) и Emergency (Экстренный).</span><span class="sxs-lookup"><span data-stu-id="cbced-p106">Priority assigned to the session. Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbced-147"><strong>Response code (Код ответа)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-147"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-148">SIP-код ответа, отправленный при сбое сеанса.</span><span class="sxs-lookup"><span data-stu-id="cbced-148">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbced-149"><strong>Front end (Сервер переднего плана)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-149"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-150">Имя сервера переднего плана, использовавшегося в конференции.</span><span class="sxs-lookup"><span data-stu-id="cbced-150">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbced-151"><strong>Capture time (Время регистрации)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-151"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-152">Дата и время регистрации сведений о сеансе.</span><span class="sxs-lookup"><span data-stu-id="cbced-152">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbced-153"><strong>End time (Время окончания)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-153"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-154">Дата и время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="cbced-154">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbced-155"><strong>To user (Пользователь-получатель)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-155"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-156">SIP-адрес пользователя, приглашенного принять участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="cbced-156">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbced-157"><strong>To user agent (Агент пользователя-получателя)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-157"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-158">Программное обеспечение, использовавшееся конечной точкой пользователя, приглашенного принять участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="cbced-158">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbced-159"><strong>Is To user internal (Пользователь-получатель внутренний?)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-159"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-160">Указывает, вошел ли пользователь, приглашенный принять участие в сеансе, во внутреннюю сеть.</span><span class="sxs-lookup"><span data-stu-id="cbced-160">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbced-161"><strong>Is To user integrated with desk phone (Пользователь-получатель интегрирован со стационарным телефоном?)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-161"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-162">Указывает, интегрирована ли конечная точка пользователя, приглашенного принять участие в сеансе, с его стационарным телефоном.</span><span class="sxs-lookup"><span data-stu-id="cbced-162">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbced-163"><strong>Is retried session (Повторный сеанс?)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-163"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-164">Указывает, являлся ли этот сеанс попыткой повтора сеанса, который завершился неудачно.</span><span class="sxs-lookup"><span data-stu-id="cbced-164">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbced-165"><strong>Diagnostic ID</strong> (ИД диагностики)</span><span class="sxs-lookup"><span data-stu-id="cbced-165"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-p107">Уникальный идентификатор (в форме заголовка ms-diagnostics), присоединенный к сообщению SIP, который часто содержит сведения, помогающий устранять ошибки. Поместите указатель мыши на этот идентификатор, чтобы увидеть дополнительные сведения о нем.</span><span class="sxs-lookup"><span data-stu-id="cbced-p107">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="cbced-168">Метрики для модальностей</span><span class="sxs-lookup"><span data-stu-id="cbced-168">Metrics for Modalities</span></span>

<span data-ttu-id="cbced-169">В следующей таблице приведены сведения, которые предоставляются отчетом по деталям однорангового сеанса для всех модальностей сеанса.</span><span class="sxs-lookup"><span data-stu-id="cbced-169">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="cbced-170">Метрики для модальностей</span><span class="sxs-lookup"><span data-stu-id="cbced-170">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbced-171">Имя</span><span class="sxs-lookup"><span data-stu-id="cbced-171">Name</span></span></th>
<th><span data-ttu-id="cbced-172">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="cbced-172">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="cbced-173">Описание</span><span class="sxs-lookup"><span data-stu-id="cbced-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbced-174"><strong>Модальности</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-174"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-175">Нет</span><span class="sxs-lookup"><span data-stu-id="cbced-175">No</span></span></p></td>
<td><p><span data-ttu-id="cbced-p108">Модальности, использованные в сеансе, например, обмен мгновенными сообщениями или передача файла.</span><span class="sxs-lookup"><span data-stu-id="cbced-p108">Modalities used in the session. For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbced-178"><strong>From user messages (Сообщения пользователя-инициатора)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-178"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-179">Нет</span><span class="sxs-lookup"><span data-stu-id="cbced-179">No</span></span></p></td>
<td><p><span data-ttu-id="cbced-180">Количество сообщений, отправленных пользователем, начавшим сеанс.</span><span class="sxs-lookup"><span data-stu-id="cbced-180">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbced-181"><strong>To user messages (Сообщения пользователя-получателя)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-181"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-182">Нет</span><span class="sxs-lookup"><span data-stu-id="cbced-182">No</span></span></p></td>
<td><p><span data-ttu-id="cbced-183">Количество сообщений, отправленных пользователем, приглашенным принять участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="cbced-183">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="cbced-184">Метрики для диагностических отчетов</span><span class="sxs-lookup"><span data-stu-id="cbced-184">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="cbced-185">В следующей таблице приведены сведения, которые отчет по деталям однорангового сеанса предоставляет для каждого диагностического отчета.</span><span class="sxs-lookup"><span data-stu-id="cbced-185">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="cbced-186">Метрики для диагностических отчетов</span><span class="sxs-lookup"><span data-stu-id="cbced-186">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbced-187">Имя</span><span class="sxs-lookup"><span data-stu-id="cbced-187">Name</span></span></th>
<th><span data-ttu-id="cbced-188">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="cbced-188">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="cbced-189">Описание</span><span class="sxs-lookup"><span data-stu-id="cbced-189">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbced-190"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-190"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-191">Нет</span><span class="sxs-lookup"><span data-stu-id="cbced-191">No</span></span></p></td>
<td><p><span data-ttu-id="cbced-192">При нажатии этой метрики отображается диагностический отчет для данного сеанса.</span><span class="sxs-lookup"><span data-stu-id="cbced-192">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbced-193"><strong>Report time (Время отчета)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-193"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-194">Нет</span><span class="sxs-lookup"><span data-stu-id="cbced-194">No</span></span></p></td>
<td><p><span data-ttu-id="cbced-195">Дата и время создания отчета.</span><span class="sxs-lookup"><span data-stu-id="cbced-195">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbced-196"><strong>Запрос</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-196"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-197">Нет</span><span class="sxs-lookup"><span data-stu-id="cbced-197">No</span></span></p></td>
<td><p><span data-ttu-id="cbced-p109">SIP-тип запроса. Например, INVITE или BYE.</span><span class="sxs-lookup"><span data-stu-id="cbced-p109">SIP request type. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbced-200"><strong>Diagnostic ID (ИД диагностики)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-200"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-201">Нет</span><span class="sxs-lookup"><span data-stu-id="cbced-201">No</span></span></p></td>
<td><p><span data-ttu-id="cbced-202">Уникальный идентификатор (в форме заголовка ms-diagnostics), присоединенный к сообщению SIP, который часто содержит сведения, помогающий устранять ошибки.</span><span class="sxs-lookup"><span data-stu-id="cbced-202">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbced-203"><strong>Content type</strong> (Тип содержимого)</span><span class="sxs-lookup"><span data-stu-id="cbced-203"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-204">Нет</span><span class="sxs-lookup"><span data-stu-id="cbced-204">No</span></span></p></td>
<td><p><span data-ttu-id="cbced-p110">Тип контента мультимедиа, использовавшегося в конференции. Например, распространенным типом контента является Application/sdp. Протокол SDP — это стандартный Интернет-протокол, используемый для объявления о сеансе, приглашения принять участие в сеансе и других форм инициации сеанса мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="cbced-p110">Type of media content used in the conference. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbced-208"><strong>Reported by (Сообщил)</strong></span><span class="sxs-lookup"><span data-stu-id="cbced-208"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="cbced-209">Нет</span><span class="sxs-lookup"><span data-stu-id="cbced-209">No</span></span></p></td>
<td><p><span data-ttu-id="cbced-210">Компьютер (клиент или сервер), который сообщил о проблеме.</span><span class="sxs-lookup"><span data-stu-id="cbced-210">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

