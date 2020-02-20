---
title: 'Lync Server 2013: Тблкомплианцестате'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615045(v=OCS.15)
ms:contentKeyID: 48185937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a744a29d36106e921c65925588f285af6d1390e5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcompliancestate-in-lync-server-2013"></a><span data-ttu-id="987d7-102">Тблкомплианцестате в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="987d7-102">tblComplianceState in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="987d7-103">_**Последнее изменение темы:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="987d7-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="987d7-104">Таблица tblComplianceState содержит сведения о состоянии соответствия во всем пуле.</span><span class="sxs-lookup"><span data-stu-id="987d7-104">tblComplianceState contains pool-wide compliance state information.</span></span>

### <a name="columns"></a><span data-ttu-id="987d7-105">Columns</span><span class="sxs-lookup"><span data-stu-id="987d7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="987d7-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="987d7-106">Column</span></span></th>
<th><span data-ttu-id="987d7-107">Тип</span><span class="sxs-lookup"><span data-stu-id="987d7-107">Type</span></span></th>
<th><span data-ttu-id="987d7-108">Описание</span><span class="sxs-lookup"><span data-stu-id="987d7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="987d7-109">ластпроцесседентрид</span><span class="sxs-lookup"><span data-stu-id="987d7-109">lastProcessedEntryID</span></span></p></td>
<td><p><span data-ttu-id="987d7-110">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="987d7-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="987d7-111">Идентификатор последнего обработанного события соответствия.</span><span class="sxs-lookup"><span data-stu-id="987d7-111">ID of the latest processed compliance event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="987d7-112">активесерверид</span><span class="sxs-lookup"><span data-stu-id="987d7-112">activeServerID</span></span></p></td>
<td><p><span data-ttu-id="987d7-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="987d7-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="987d7-114">Идентификатор сервера соответствия, на котором находится монопольная блокировка базы данных, или -1 при ее отсутствии.</span><span class="sxs-lookup"><span data-stu-id="987d7-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="987d7-115">локкекспиратионтиме</span><span class="sxs-lookup"><span data-stu-id="987d7-115">lockExpirationTime</span></span></p></td>
<td><p><span data-ttu-id="987d7-116">datetime2, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="987d7-116">datetime2, not null</span></span></p></td>
<td><p><span data-ttu-id="987d7-117">Время окончания блокировки (если значение activeServerID не равно -1).</span><span class="sxs-lookup"><span data-stu-id="987d7-117">Lock expiration time (if activeServerID is not -1).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

