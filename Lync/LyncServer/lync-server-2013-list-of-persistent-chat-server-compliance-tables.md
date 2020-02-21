---
title: 'Lync Server 2013: список таблиц соответствия сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 322b700b807f8654e96572a3c040ddd7fe0d1e5f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="cefea-102">Список таблиц соответствия сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cefea-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cefea-103">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="cefea-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="cefea-104">Схема базы данных соответствия сохраняемого чата состоит из следующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="cefea-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="cefea-105">Список таблиц соблюдения требований для сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="cefea-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cefea-106">Table</span><span class="sxs-lookup"><span data-stu-id="cefea-106">Table</span></span></th>
<th><span data-ttu-id="cefea-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cefea-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cefea-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cefea-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cefea-109">Содержит события соответствия, которые еще не были обработаны настроенным адаптером.</span><span class="sxs-lookup"><span data-stu-id="cefea-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="cefea-110">В этой таблице содержатся события, связанные с сохраняемым разговором, такие как сообщения чата и загрузка файлов.</span><span class="sxs-lookup"><span data-stu-id="cefea-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="cefea-111">(События, связанные с участниками, отслеживаются в таблице tblComplianceParticipant.)</span><span class="sxs-lookup"><span data-stu-id="cefea-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="cefea-112">(Серверы, которые обработали события, содержащиеся в этой таблице, приводятся в таблице tblComplianceFanout.)</span><span class="sxs-lookup"><span data-stu-id="cefea-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cefea-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cefea-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cefea-114">Содержит серверы, обработавшие события соответствия.</span><span class="sxs-lookup"><span data-stu-id="cefea-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="cefea-115">Эта таблица тесно связана с таблицей tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="cefea-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cefea-116"><a href="lync-server-2013-tblcomplianceparticipant.md">ТблкомплианцепартиЦипант в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cefea-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cefea-117">Содержит сведения о текущих участниках по службам чата и серверам.</span><span class="sxs-lookup"><span data-stu-id="cefea-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="cefea-118">Он поддерживается на основе событий присоединения и соответствия частей, полученных от службы сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cefea-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cefea-119"><a href="lync-server-2013-tblcompliancestate.md">Тблкомплианцестате в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cefea-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cefea-120">Содержит сведения о состоянии соответствия во всем пуле.</span><span class="sxs-lookup"><span data-stu-id="cefea-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

