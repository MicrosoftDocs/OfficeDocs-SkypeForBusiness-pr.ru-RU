---
title: 'Lync Server 2013: список таблиц соответствия сервера сохраняемого чата'
description: 'Lync Server 2013: список таблиц соответствия сервера сохраняемого чата.'
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
ms.openlocfilehash: 47cb28a0ca4180327c2adc48d80e9e41171a7bfc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550075"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="04c29-103">Список таблиц соответствия сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04c29-103">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04c29-104">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="04c29-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="04c29-105">Схема базы данных соответствия сохраняемого чата состоит из следующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="04c29-105">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="04c29-106">Список таблиц соблюдения требований для сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="04c29-106">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04c29-107">Table</span><span class="sxs-lookup"><span data-stu-id="04c29-107">Table</span></span></th>
<th><span data-ttu-id="04c29-108">Описание</span><span class="sxs-lookup"><span data-stu-id="04c29-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04c29-109"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="04c29-109"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="04c29-110">Содержит события соответствия, которые еще не были обработаны настроенным адаптером.</span><span class="sxs-lookup"><span data-stu-id="04c29-110">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="04c29-111">В этой таблице содержатся события, связанные с сохраняемым разговором, такие как сообщения чата и загрузка файлов.</span><span class="sxs-lookup"><span data-stu-id="04c29-111">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="04c29-112">(События, связанные с участниками, отслеживаются в таблице tblComplianceParticipant.)</span><span class="sxs-lookup"><span data-stu-id="04c29-112">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="04c29-113">(Серверы, которые обработали события, содержащиеся в этой таблице, приводятся в таблице tblComplianceFanout.)</span><span class="sxs-lookup"><span data-stu-id="04c29-113">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04c29-114"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="04c29-114"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="04c29-115">Содержит серверы, обработавшие события соответствия.</span><span class="sxs-lookup"><span data-stu-id="04c29-115">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="04c29-116">Эта таблица тесно связана с таблицей tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="04c29-116">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04c29-117"><a href="lync-server-2013-tblcomplianceparticipant.md">ТблкомплианцепартиЦипант в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="04c29-117"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="04c29-118">Содержит сведения о текущих участниках по службам чата и серверам.</span><span class="sxs-lookup"><span data-stu-id="04c29-118">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="04c29-119">Он поддерживается на основе событий присоединения и соответствия частей, полученных от службы сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="04c29-119">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04c29-120"><a href="lync-server-2013-tblcompliancestate.md">Тблкомплианцестате в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="04c29-120"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="04c29-121">Содержит сведения о состоянии соответствия во всем пуле.</span><span class="sxs-lookup"><span data-stu-id="04c29-121">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

