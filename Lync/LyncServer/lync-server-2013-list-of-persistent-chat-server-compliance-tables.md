---
title: 'Lync Server 2013: список таблиц соблюдения требований для сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31d3df9a0bfd5fa4b8b4acdda15ed86940c2572a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="f32c4-102">Список таблиц соблюдения требований для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f32c4-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f32c4-103">_**Тема последнего изменения:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="f32c4-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="f32c4-104">Схема базы данных соответствия требованиям к сохраненным Чатам состоит из следующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="f32c4-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="f32c4-105">Список таблиц соответствия требованиям сервера для работы с постоянной версией чата</span><span class="sxs-lookup"><span data-stu-id="f32c4-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f32c4-106">Таблица</span><span class="sxs-lookup"><span data-stu-id="f32c4-106">Table</span></span></th>
<th><span data-ttu-id="f32c4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f32c4-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f32c4-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f32c4-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f32c4-109">Содержит события соответствия требованиям, которые еще не были обработаны настроенным адаптером.</span><span class="sxs-lookup"><span data-stu-id="f32c4-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="f32c4-110">В этой таблице содержатся сохраняемые события, связанные с чат, такие как сообщения чата и загружаемые файлы.</span><span class="sxs-lookup"><span data-stu-id="f32c4-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="f32c4-111">(События участников отслеживаются таблицей ТблкомплианцепартиЦипант.)</span><span class="sxs-lookup"><span data-stu-id="f32c4-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="f32c4-112">(Серверы, обработавшие события в этой таблице, перечислены в таблице Тблкомплианцефанаут).</span><span class="sxs-lookup"><span data-stu-id="f32c4-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f32c4-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f32c4-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f32c4-114">Содержат серверы, которые обрабатывали событие соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f32c4-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="f32c4-115">Эта таблица тесно связана с таблицей Тблкомплианцедата.</span><span class="sxs-lookup"><span data-stu-id="f32c4-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f32c4-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f32c4-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f32c4-117">Включает в себя текущих участников для каждой службы чата и для каждого сервера.</span><span class="sxs-lookup"><span data-stu-id="f32c4-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="f32c4-118">Она поддерживается на основе событий присоединения и частей соответствия, полученных от службы сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="f32c4-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f32c4-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f32c4-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f32c4-120">Сведения о состоянии соответствия требованиям всего пула.</span><span class="sxs-lookup"><span data-stu-id="f32c4-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

