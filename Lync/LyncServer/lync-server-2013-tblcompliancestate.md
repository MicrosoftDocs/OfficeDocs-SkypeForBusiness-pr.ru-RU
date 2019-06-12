---
title: 'Lync Server 2013: tblComplianceState'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615045(v=OCS.15)
ms:contentKeyID: 48185937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fce70f05b317ac7467fd17306d6933c66087e5e6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancestate-in-lync-server-2013"></a><span data-ttu-id="c97ac-102">tblComplianceState в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c97ac-102">tblComplianceState in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c97ac-103">_**Тема последнего изменения:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="c97ac-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="c97ac-104">Тблкомплианцестате включает в себя сведения о состоянии соответствия требованиям всего пула.</span><span class="sxs-lookup"><span data-stu-id="c97ac-104">tblComplianceState contains pool-wide compliance state information.</span></span>

### <a name="columns"></a><span data-ttu-id="c97ac-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="c97ac-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c97ac-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="c97ac-106">Column</span></span></th>
<th><span data-ttu-id="c97ac-107">Тип</span><span class="sxs-lookup"><span data-stu-id="c97ac-107">Type</span></span></th>
<th><span data-ttu-id="c97ac-108">Описание</span><span class="sxs-lookup"><span data-stu-id="c97ac-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c97ac-109">Ластпроцесседентрид</span><span class="sxs-lookup"><span data-stu-id="c97ac-109">lastProcessedEntryID</span></span></p></td>
<td><p><span data-ttu-id="c97ac-110">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="c97ac-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="c97ac-111">Идентификатор последнего обработанного события соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="c97ac-111">ID of the latest processed compliance event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97ac-112">Активесерверид</span><span class="sxs-lookup"><span data-stu-id="c97ac-112">activeServerID</span></span></p></td>
<td><p><span data-ttu-id="c97ac-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="c97ac-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c97ac-114">Идентификатор сервера соответствия, который удерживает монопольную блокировку для базы данных, или значение-1, если нет.</span><span class="sxs-lookup"><span data-stu-id="c97ac-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c97ac-115">Локкекспиратионтиме</span><span class="sxs-lookup"><span data-stu-id="c97ac-115">lockExpirationTime</span></span></p></td>
<td><p><span data-ttu-id="c97ac-116">datetime2, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="c97ac-116">datetime2, not null</span></span></p></td>
<td><p><span data-ttu-id="c97ac-117">Заблокируйте срок действия (если Активесерверид не является 1).</span><span class="sxs-lookup"><span data-stu-id="c97ac-117">Lock expiration time (if activeServerID is not -1).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

