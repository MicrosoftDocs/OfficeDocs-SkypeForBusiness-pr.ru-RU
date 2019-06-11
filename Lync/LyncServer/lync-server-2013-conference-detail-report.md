---
title: 'Lync Server 2013: подробный отчет о Конференции'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac598c3f85211ad97f2d6266b74b6c524d76d006
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="e5864-102">Подробный отчет о конференции в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5864-102">Conference Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5864-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="e5864-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="e5864-p101">Подробный отчет по конференции содержит подробную информацию обо всех пользователях, принимавших участие в конференции. Например, вы можете просматривать такую информацию, как дата и время присоединения пользователя к конференции, дата и время покидания конференции, а также агент пользователя конечной точки, использованный для подключения этого пользователя к конференции. Вы также можете просмотреть информацию о роли пользователя в каждой конференции (например, выступающий или участник). Возможно, еще важнее то, что вы можете быстро просмотреть, какие пользователи успешно присоединились к конференции и участвовали в ней и какие пользователи не смогли этого сделать.</span><span class="sxs-lookup"><span data-stu-id="e5864-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="e5864-108">Доступ к подробному отчету по конференции</span><span class="sxs-lookup"><span data-stu-id="e5864-108">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="e5864-109">Подробный отчет по конференции можно открыть из следующих отчетов:</span><span class="sxs-lookup"><span data-stu-id="e5864-109">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="e5864-110">[Отчет по контролю за допуском звонков в Lync Server 2013](lync-server-2013-call-admission-control-report.md) (с помощью которого можно выбрать детальную метрику конференции)</span><span class="sxs-lookup"><span data-stu-id="e5864-110">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="e5864-111">[Отчет о списке отказов в Lync Server 2013](lync-server-2013-failure-list-report.md) (щелчок метрики конференции)</span><span class="sxs-lookup"><span data-stu-id="e5864-111">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="e5864-112">[Отчет о действиях пользователей в Lync Server 2013](lync-server-2013-user-activity-report.md) (щелчок метрики URI конференции)</span><span class="sxs-lookup"><span data-stu-id="e5864-112">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="e5864-113">В отчете сведения о конференции вы можете получить доступ к [отчету о диагностике в Lync Server 2013](lync-server-2013-diagnostic-report.md) , щелкнув метрику диагностического отчета (подробности).</span><span class="sxs-lookup"><span data-stu-id="e5864-113">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e5864-114">Фильтры</span><span class="sxs-lookup"><span data-stu-id="e5864-114">Filters</span></span>

<span data-ttu-id="e5864-p102">Нет. Вы не можете фильтровать подробный отчет по конференции.</span><span class="sxs-lookup"><span data-stu-id="e5864-p102">None. You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="e5864-117">Показатели</span><span class="sxs-lookup"><span data-stu-id="e5864-117">Metrics</span></span>

<span data-ttu-id="e5864-118">В следующей таблице приведены сведения из раздела информации о конференции, входящего в подробный отчет по конференции.</span><span class="sxs-lookup"><span data-stu-id="e5864-118">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="e5864-119">Метрики информации о конференции</span><span class="sxs-lookup"><span data-stu-id="e5864-119">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5864-120">Имя</span><span class="sxs-lookup"><span data-stu-id="e5864-120">Name</span></span></th>
<th><span data-ttu-id="e5864-121">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="e5864-121">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e5864-122">Описание</span><span class="sxs-lookup"><span data-stu-id="e5864-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5864-123"><strong>Идентификатор URI конференции</strong></span><span class="sxs-lookup"><span data-stu-id="e5864-123"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5864-p103">URI, назначенный конференции. Например:</span><span class="sxs-lookup"><span data-stu-id="e5864-p103">URI assigned to the conference. For example:</span></span></p>
<p><span data-ttu-id="e5864-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="e5864-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5864-127"><strong>Полное доменное имя пула</strong></span><span class="sxs-lookup"><span data-stu-id="e5864-127"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5864-128">Полное доменное имя пула Регистратора или участвующего в сеансе пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="e5864-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5864-129"><strong>Время начала</strong></span><span class="sxs-lookup"><span data-stu-id="e5864-129"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5864-130">Дата и время начала конференции.</span><span class="sxs-lookup"><span data-stu-id="e5864-130">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5864-131"><strong>Организатор</strong></span><span class="sxs-lookup"><span data-stu-id="e5864-131"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5864-132">SIP-адрес пользователя, организовавшего конференцию.</span><span class="sxs-lookup"><span data-stu-id="e5864-132">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5864-133"><strong>Время окончания</strong></span><span class="sxs-lookup"><span data-stu-id="e5864-133"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5864-134">Дата и время завершения конференции.</span><span class="sxs-lookup"><span data-stu-id="e5864-134">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e5864-135">В следующей таблице приведены сведения из раздела участия в конференции, входящего в подробный отчет по конференции.</span><span class="sxs-lookup"><span data-stu-id="e5864-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="e5864-136">Метрики участия в конференции</span><span class="sxs-lookup"><span data-stu-id="e5864-136">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5864-137">Имя</span><span class="sxs-lookup"><span data-stu-id="e5864-137">Name</span></span></th>
<th><span data-ttu-id="e5864-138">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="e5864-138">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e5864-139">Описание</span><span class="sxs-lookup"><span data-stu-id="e5864-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5864-140"><strong>Пользователь</strong></span><span class="sxs-lookup"><span data-stu-id="e5864-140"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5864-141">SIP-адрес пользователя, участвовавшего в конференции.</span><span class="sxs-lookup"><span data-stu-id="e5864-141">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5864-142"><strong>Роль</strong></span><span class="sxs-lookup"><span data-stu-id="e5864-142"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5864-143">Роль (например, докладчик), которую играл участник конференции.</span><span class="sxs-lookup"><span data-stu-id="e5864-143">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5864-144"><strong>Подключение</strong></span><span class="sxs-lookup"><span data-stu-id="e5864-144"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5864-145">Подключение участника к сети, обычно из внутренней сети или из внешней сети.</span><span class="sxs-lookup"><span data-stu-id="e5864-145">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5864-146">Время присоединения</span><span class="sxs-lookup"><span data-stu-id="e5864-146">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5864-147">Дата и время присоединения участника к конференции.</span><span class="sxs-lookup"><span data-stu-id="e5864-147">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5864-148"><strong>Время выхода</strong></span><span class="sxs-lookup"><span data-stu-id="e5864-148"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5864-149">Дата и время, когда участник покинул конференцию.</span><span class="sxs-lookup"><span data-stu-id="e5864-149">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5864-150"><strong>Агент пользователя</strong></span><span class="sxs-lookup"><span data-stu-id="e5864-150"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5864-151">Идентификатор для программного обеспечения, используемого конечной точкой участника.</span><span class="sxs-lookup"><span data-stu-id="e5864-151">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5864-152"><strong>Диагностический отчет</strong></span><span class="sxs-lookup"><span data-stu-id="e5864-152"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5864-p104">Предоставляет сведения о диагностике и о поиске и устранении неполадок, включая коды отклика SIP, диагностические заголовки, значения времени присоединения к конференции и диагностические идентификаторы для неудачных сеансов.</span><span class="sxs-lookup"><span data-stu-id="e5864-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e5864-155">В таблице ниже приведены сведения, указанные в разделе Conference модальностей в отчете "сведения о конференции".</span><span class="sxs-lookup"><span data-stu-id="e5864-155">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="e5864-156">Метрики модальностей конференции</span><span class="sxs-lookup"><span data-stu-id="e5864-156">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5864-157">Имя</span><span class="sxs-lookup"><span data-stu-id="e5864-157">Name</span></span></th>
<th><span data-ttu-id="e5864-158">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="e5864-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e5864-159">Описание</span><span class="sxs-lookup"><span data-stu-id="e5864-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5864-160"><strong>Пользователь</strong></span><span class="sxs-lookup"><span data-stu-id="e5864-160"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5864-161">SIP-адрес пользователя, участвовавшего в конференции.</span><span class="sxs-lookup"><span data-stu-id="e5864-161">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5864-162"><strong>Время присоединения</strong></span><span class="sxs-lookup"><span data-stu-id="e5864-162"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5864-163">Дата и время присоединения участника к конференции.</span><span class="sxs-lookup"><span data-stu-id="e5864-163">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5864-164"><strong>Время ухода</strong></span><span class="sxs-lookup"><span data-stu-id="e5864-164"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5864-165">Дата и время покидания участником конференции.</span><span class="sxs-lookup"><span data-stu-id="e5864-165">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5864-166"><strong>URI сервера конференций</strong></span><span class="sxs-lookup"><span data-stu-id="e5864-166"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5864-167">URI для используемого в конференции сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="e5864-167">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5864-168"><strong>Диагностический отчет</strong></span><span class="sxs-lookup"><span data-stu-id="e5864-168"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5864-p105">Предоставляет сведения о диагностике и о поиске и устранении неполадок, включая коды отклика SIP, диагностические заголовки, значения времени присоединения к конференции и диагностические идентификаторы для неудачных сеансов.</span><span class="sxs-lookup"><span data-stu-id="e5864-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

