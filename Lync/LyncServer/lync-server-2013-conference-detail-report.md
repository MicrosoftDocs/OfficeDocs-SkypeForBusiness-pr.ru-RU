---
title: 'Lync Server 2013: подробный отчет по Конференции'
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
ms.openlocfilehash: e1c2a25105aec6cdf6d21193038f90ea852c5b3a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526036"
---
# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="194cd-102">Подробный отчет по конференции в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="194cd-102">Conference Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="194cd-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="194cd-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="194cd-p101">Подробный отчет по конференции содержит подробную информацию обо всех пользователях, принимавших участие в конференции. Например, вы можете просматривать такую информацию, как дата и время присоединения пользователя к конференции, дата и время покидания  конференции, а также агент пользователя конечной точки, использованный для подключения этого пользователя к конференции. Вы также можете просмотреть информацию о роли пользователя в каждой конференции (например, выступающий или участник). Возможно, еще важнее то, что вы можете быстро просмотреть, какие пользователи успешно присоединились к конференции и участвовали в ней и какие пользователи не смогли этого сделать.</span><span class="sxs-lookup"><span data-stu-id="194cd-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="194cd-108">Доступ к подробному отчету по конференции</span><span class="sxs-lookup"><span data-stu-id="194cd-108">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="194cd-109">Подробный отчет по конференции можно открыть из следующих отчетов:</span><span class="sxs-lookup"><span data-stu-id="194cd-109">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="194cd-110">[Отчет по контролю допуска звонков в Lync Server 2013](lync-server-2013-call-admission-control-report.md) (щелкнув метрику сведений для Конференции)</span><span class="sxs-lookup"><span data-stu-id="194cd-110">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="194cd-111">[Отчет по списку отказов в Lync Server 2013](lync-server-2013-failure-list-report.md) (щелкнув метрику конференции)</span><span class="sxs-lookup"><span data-stu-id="194cd-111">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="194cd-112">[Отчет об активности пользователей в Lync Server 2013](lync-server-2013-user-activity-report.md) (щелкнув метрику URI конференции)</span><span class="sxs-lookup"><span data-stu-id="194cd-112">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="194cd-113">Из подробного отчета по конференции вы можете получить доступ к [диагностическим отчету в Lync Server 2013](lync-server-2013-diagnostic-report.md) , щелкнув метрику диагностического отчета (Detail).</span><span class="sxs-lookup"><span data-stu-id="194cd-113">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="194cd-114">Фильтры</span><span class="sxs-lookup"><span data-stu-id="194cd-114">Filters</span></span>

<span data-ttu-id="194cd-p102">Нет. Вы не можете фильтровать подробный отчет по конференции.</span><span class="sxs-lookup"><span data-stu-id="194cd-p102">None. You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="194cd-117">Метрики</span><span class="sxs-lookup"><span data-stu-id="194cd-117">Metrics</span></span>

<span data-ttu-id="194cd-118">В следующей таблице приведены сведения из раздела информации о конференции, входящего в подробный отчет по конференции.</span><span class="sxs-lookup"><span data-stu-id="194cd-118">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="194cd-119">Метрики информации о конференции</span><span class="sxs-lookup"><span data-stu-id="194cd-119">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="194cd-120">Имя</span><span class="sxs-lookup"><span data-stu-id="194cd-120">Name</span></span></th>
<th><span data-ttu-id="194cd-121">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="194cd-121">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="194cd-122">Описание</span><span class="sxs-lookup"><span data-stu-id="194cd-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="194cd-123"><strong>Conference URI</strong> (URI конференции)</span><span class="sxs-lookup"><span data-stu-id="194cd-123"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194cd-p103">URI, назначенный конференции. Например:</span><span class="sxs-lookup"><span data-stu-id="194cd-p103">URI assigned to the conference. For example:</span></span></p>
<p><span data-ttu-id="194cd-126">SIP: kmyer@litwareinc. com; GRUU; непрозрачный = App: conf: Focus: ID: drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="194cd-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="194cd-127"><strong>Pool FQDN</strong> (Полное доменное имя пула)</span><span class="sxs-lookup"><span data-stu-id="194cd-127"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194cd-128">Полное доменное имя пула Регистратора или участвующего в сеансе пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="194cd-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="194cd-129"><strong>Start time</strong> (Время начала)</span><span class="sxs-lookup"><span data-stu-id="194cd-129"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194cd-130">Дата и время начала конференции.</span><span class="sxs-lookup"><span data-stu-id="194cd-130">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="194cd-131"><strong>Organizer</strong></span><span class="sxs-lookup"><span data-stu-id="194cd-131"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194cd-132">SIP-адрес пользователя, организовавшего конференцию.</span><span class="sxs-lookup"><span data-stu-id="194cd-132">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="194cd-133"><strong>End time</strong> (Время окончания)</span><span class="sxs-lookup"><span data-stu-id="194cd-133"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194cd-134">Дата и время завершения конференции.</span><span class="sxs-lookup"><span data-stu-id="194cd-134">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="194cd-135">В следующей таблице приведены сведения из раздела участия в конференции, входящего в подробный отчет по конференции.</span><span class="sxs-lookup"><span data-stu-id="194cd-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="194cd-136">Метрики участия в конференции</span><span class="sxs-lookup"><span data-stu-id="194cd-136">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="194cd-137">Имя</span><span class="sxs-lookup"><span data-stu-id="194cd-137">Name</span></span></th>
<th><span data-ttu-id="194cd-138">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="194cd-138">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="194cd-139">Описание</span><span class="sxs-lookup"><span data-stu-id="194cd-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="194cd-140"><strong>Пользователь</strong></span><span class="sxs-lookup"><span data-stu-id="194cd-140"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194cd-141">SIP-адрес пользователя, участвовавшего в конференции.</span><span class="sxs-lookup"><span data-stu-id="194cd-141">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="194cd-142"><strong>Role</strong></span><span class="sxs-lookup"><span data-stu-id="194cd-142"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194cd-143">Роль (например, выступающий) участника конференции.</span><span class="sxs-lookup"><span data-stu-id="194cd-143">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="194cd-144"><strong>Подключение</strong></span><span class="sxs-lookup"><span data-stu-id="194cd-144"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194cd-145">Возможность подключения к сети (обычно изнутри или извне) для участника.</span><span class="sxs-lookup"><span data-stu-id="194cd-145">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="194cd-146">Время присоединения</span><span class="sxs-lookup"><span data-stu-id="194cd-146">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194cd-147">Дата и время присоединения участника к конференции.</span><span class="sxs-lookup"><span data-stu-id="194cd-147">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="194cd-148"><strong>Leave time</strong> (Время ухода)</span><span class="sxs-lookup"><span data-stu-id="194cd-148"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194cd-149">Дата и время покидания участником конференции.</span><span class="sxs-lookup"><span data-stu-id="194cd-149">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="194cd-150"><strong>User agent</strong> (Агент пользователя)</span><span class="sxs-lookup"><span data-stu-id="194cd-150"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194cd-151">Идентификатор для программного обеспечения, используемого конечной точкой участника.</span><span class="sxs-lookup"><span data-stu-id="194cd-151">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="194cd-152"><strong>Diagnostic reports</strong> (Диагностические отчеты)</span><span class="sxs-lookup"><span data-stu-id="194cd-152"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194cd-p104">Предоставляет сведения о диагностике и о поиске и устранении неполадок, включая коды отклика SIP, диагностические заголовки, значения времени присоединения к конференции и диагностические идентификаторы для неудачных сеансов.</span><span class="sxs-lookup"><span data-stu-id="194cd-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="194cd-155">В следующей таблице перечислены сведения, представленные в разделе Conference модальности в информационном отчете о Конференции.</span><span class="sxs-lookup"><span data-stu-id="194cd-155">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="194cd-156">Метрики модальностей конференции</span><span class="sxs-lookup"><span data-stu-id="194cd-156">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="194cd-157">Имя</span><span class="sxs-lookup"><span data-stu-id="194cd-157">Name</span></span></th>
<th><span data-ttu-id="194cd-158">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="194cd-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="194cd-159">Описание</span><span class="sxs-lookup"><span data-stu-id="194cd-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="194cd-160"><strong>Пользователь</strong></span><span class="sxs-lookup"><span data-stu-id="194cd-160"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194cd-161">SIP-адрес пользователя, участвовавшего в конференции.</span><span class="sxs-lookup"><span data-stu-id="194cd-161">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="194cd-162"><strong>Join time</strong> (Время присоединения)</span><span class="sxs-lookup"><span data-stu-id="194cd-162"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194cd-163">Дата и время присоединения участника к конференции.</span><span class="sxs-lookup"><span data-stu-id="194cd-163">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="194cd-164"><strong>Leave time</strong> (Время ухода)</span><span class="sxs-lookup"><span data-stu-id="194cd-164"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194cd-165">Дата и время покидания участником конференции.</span><span class="sxs-lookup"><span data-stu-id="194cd-165">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="194cd-166"><strong>Conferencing server URI</strong> (URI сервера конференций)</span><span class="sxs-lookup"><span data-stu-id="194cd-166"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194cd-167">URI для используемого в конференции сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="194cd-167">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="194cd-168"><strong>Diagnostic reports</strong> (Диагностические отчеты)</span><span class="sxs-lookup"><span data-stu-id="194cd-168"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="194cd-p105">Предоставляет сведения о диагностике и о поиске и устранении неполадок, включая коды отклика SIP, диагностические заголовки, значения времени присоединения к конференции и диагностические идентификаторы для неудачных сеансов.</span><span class="sxs-lookup"><span data-stu-id="194cd-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

