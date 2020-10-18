---
title: 'Lync Server 2013: подробный отчет по Конференции'
description: 'Lync Server 2013: подробный отчет по Конференции.'
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
ms.openlocfilehash: 07c50b545f4a9ee3308a840fc2aa5a15e617a5bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577635"
---
# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="762b5-103">Подробный отчет по конференции в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="762b5-103">Conference Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="762b5-104">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="762b5-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="762b5-p101">Подробный отчет по конференции содержит подробную информацию обо всех пользователях, принимавших участие в конференции. Например, вы можете просматривать такую информацию, как дата и время присоединения пользователя к конференции, дата и время покидания  конференции, а также агент пользователя конечной точки, использованный для подключения этого пользователя к конференции. Вы также можете просмотреть информацию о роли пользователя в каждой конференции (например, выступающий или участник). Возможно, еще важнее то, что вы можете быстро просмотреть, какие пользователи успешно присоединились к конференции и участвовали в ней и какие пользователи не смогли этого сделать.</span><span class="sxs-lookup"><span data-stu-id="762b5-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="762b5-109">Доступ к подробному отчету по конференции</span><span class="sxs-lookup"><span data-stu-id="762b5-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="762b5-110">Подробный отчет по конференции можно открыть из следующих отчетов:</span><span class="sxs-lookup"><span data-stu-id="762b5-110">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="762b5-111">[Отчет по контролю допуска звонков в Lync Server 2013](lync-server-2013-call-admission-control-report.md) (щелкнув метрику сведений для Конференции)</span><span class="sxs-lookup"><span data-stu-id="762b5-111">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="762b5-112">[Отчет по списку отказов в Lync Server 2013](lync-server-2013-failure-list-report.md) (щелкнув метрику конференции)</span><span class="sxs-lookup"><span data-stu-id="762b5-112">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="762b5-113">[Отчет об активности пользователей в Lync Server 2013](lync-server-2013-user-activity-report.md) (щелкнув метрику URI конференции)</span><span class="sxs-lookup"><span data-stu-id="762b5-113">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="762b5-114">Из подробного отчета по конференции вы можете получить доступ к [диагностическим отчету в Lync Server 2013](lync-server-2013-diagnostic-report.md) , щелкнув метрику диагностического отчета (Detail).</span><span class="sxs-lookup"><span data-stu-id="762b5-114">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="762b5-115">Фильтры</span><span class="sxs-lookup"><span data-stu-id="762b5-115">Filters</span></span>

<span data-ttu-id="762b5-p102">Нет. Вы не можете фильтровать подробный отчет по конференции.</span><span class="sxs-lookup"><span data-stu-id="762b5-p102">None. You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="762b5-118">Метрики</span><span class="sxs-lookup"><span data-stu-id="762b5-118">Metrics</span></span>

<span data-ttu-id="762b5-119">В следующей таблице приведены сведения из раздела информации о конференции, входящего в подробный отчет по конференции.</span><span class="sxs-lookup"><span data-stu-id="762b5-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="762b5-120">Метрики информации о конференции</span><span class="sxs-lookup"><span data-stu-id="762b5-120">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="762b5-121">Имя</span><span class="sxs-lookup"><span data-stu-id="762b5-121">Name</span></span></th>
<th><span data-ttu-id="762b5-122">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="762b5-122">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="762b5-123">Описание</span><span class="sxs-lookup"><span data-stu-id="762b5-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="762b5-124"><strong>Conference URI</strong> (URI конференции)</span><span class="sxs-lookup"><span data-stu-id="762b5-124"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="762b5-p103">URI, назначенный конференции. Например:</span><span class="sxs-lookup"><span data-stu-id="762b5-p103">URI assigned to the conference. For example:</span></span></p>
<p><span data-ttu-id="762b5-127">SIP: kmyer@litwareinc. com; GRUU; непрозрачный = App: conf: Focus: ID: drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="762b5-127">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="762b5-128"><strong>Pool FQDN</strong> (Полное доменное имя пула)</span><span class="sxs-lookup"><span data-stu-id="762b5-128"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="762b5-129">Полное доменное имя пула Регистратора или участвующего в сеансе пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="762b5-129">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="762b5-130"><strong>Start time</strong> (Время начала)</span><span class="sxs-lookup"><span data-stu-id="762b5-130"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="762b5-131">Дата и время начала конференции.</span><span class="sxs-lookup"><span data-stu-id="762b5-131">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="762b5-132"><strong>Organizer</strong></span><span class="sxs-lookup"><span data-stu-id="762b5-132"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="762b5-133">SIP-адрес пользователя, организовавшего конференцию.</span><span class="sxs-lookup"><span data-stu-id="762b5-133">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="762b5-134"><strong>End time</strong> (Время окончания)</span><span class="sxs-lookup"><span data-stu-id="762b5-134"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="762b5-135">Дата и время завершения конференции.</span><span class="sxs-lookup"><span data-stu-id="762b5-135">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="762b5-136">В следующей таблице приведены сведения из раздела участия в конференции, входящего в подробный отчет по конференции.</span><span class="sxs-lookup"><span data-stu-id="762b5-136">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="762b5-137">Метрики участия в конференции</span><span class="sxs-lookup"><span data-stu-id="762b5-137">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="762b5-138">Имя</span><span class="sxs-lookup"><span data-stu-id="762b5-138">Name</span></span></th>
<th><span data-ttu-id="762b5-139">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="762b5-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="762b5-140">Описание</span><span class="sxs-lookup"><span data-stu-id="762b5-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="762b5-141"><strong>Пользователь</strong></span><span class="sxs-lookup"><span data-stu-id="762b5-141"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="762b5-142">SIP-адрес пользователя, участвовавшего в конференции.</span><span class="sxs-lookup"><span data-stu-id="762b5-142">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="762b5-143"><strong>Role</strong></span><span class="sxs-lookup"><span data-stu-id="762b5-143"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="762b5-144">Роль (например, выступающий) участника конференции.</span><span class="sxs-lookup"><span data-stu-id="762b5-144">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="762b5-145"><strong>Подключение</strong></span><span class="sxs-lookup"><span data-stu-id="762b5-145"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="762b5-146">Возможность подключения к сети (обычно изнутри или извне) для участника.</span><span class="sxs-lookup"><span data-stu-id="762b5-146">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="762b5-147">Время присоединения</span><span class="sxs-lookup"><span data-stu-id="762b5-147">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="762b5-148">Дата и время присоединения участника к конференции.</span><span class="sxs-lookup"><span data-stu-id="762b5-148">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="762b5-149"><strong>Leave time</strong> (Время ухода)</span><span class="sxs-lookup"><span data-stu-id="762b5-149"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="762b5-150">Дата и время покидания участником конференции.</span><span class="sxs-lookup"><span data-stu-id="762b5-150">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="762b5-151"><strong>User agent</strong> (Агент пользователя)</span><span class="sxs-lookup"><span data-stu-id="762b5-151"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="762b5-152">Идентификатор для программного обеспечения, используемого конечной точкой участника.</span><span class="sxs-lookup"><span data-stu-id="762b5-152">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="762b5-153"><strong>Diagnostic reports</strong> (Диагностические отчеты)</span><span class="sxs-lookup"><span data-stu-id="762b5-153"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="762b5-p104">Предоставляет сведения о диагностике и о поиске и устранении неполадок, включая коды отклика SIP, диагностические заголовки, значения времени присоединения к конференции и диагностические идентификаторы для неудачных сеансов.</span><span class="sxs-lookup"><span data-stu-id="762b5-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="762b5-156">В следующей таблице перечислены сведения, представленные в разделе Conference модальности в информационном отчете о Конференции.</span><span class="sxs-lookup"><span data-stu-id="762b5-156">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="762b5-157">Метрики модальностей конференции</span><span class="sxs-lookup"><span data-stu-id="762b5-157">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="762b5-158">Имя</span><span class="sxs-lookup"><span data-stu-id="762b5-158">Name</span></span></th>
<th><span data-ttu-id="762b5-159">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="762b5-159">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="762b5-160">Описание</span><span class="sxs-lookup"><span data-stu-id="762b5-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="762b5-161"><strong>Пользователь</strong></span><span class="sxs-lookup"><span data-stu-id="762b5-161"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="762b5-162">SIP-адрес пользователя, участвовавшего в конференции.</span><span class="sxs-lookup"><span data-stu-id="762b5-162">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="762b5-163"><strong>Join time</strong> (Время присоединения)</span><span class="sxs-lookup"><span data-stu-id="762b5-163"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="762b5-164">Дата и время присоединения участника к конференции.</span><span class="sxs-lookup"><span data-stu-id="762b5-164">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="762b5-165"><strong>Leave time</strong> (Время ухода)</span><span class="sxs-lookup"><span data-stu-id="762b5-165"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="762b5-166">Дата и время покидания участником конференции.</span><span class="sxs-lookup"><span data-stu-id="762b5-166">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="762b5-167"><strong>Conferencing server URI</strong> (URI сервера конференций)</span><span class="sxs-lookup"><span data-stu-id="762b5-167"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="762b5-168">URI для используемого в конференции сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="762b5-168">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="762b5-169"><strong>Diagnostic reports</strong> (Диагностические отчеты)</span><span class="sxs-lookup"><span data-stu-id="762b5-169"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="762b5-p105">Предоставляет сведения о диагностике и о поиске и устранении неполадок, включая коды отклика SIP, диагностические заголовки, значения времени присоединения к конференции и диагностические идентификаторы для неудачных сеансов.</span><span class="sxs-lookup"><span data-stu-id="762b5-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

