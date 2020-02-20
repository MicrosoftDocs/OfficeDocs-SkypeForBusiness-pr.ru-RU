---
title: 'Lync Server 2013: tblAdminLock'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558665(v=OCS.15)
ms:contentKeyID: 48184560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58bf1c04cb24f8fee668cd21f24fc7c9c1c5341d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladminlock-in-lync-server-2013"></a><span data-ttu-id="2cba9-102">tblAdminLock в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cba9-102">tblAdminLock in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cba9-103">_**Последнее изменение темы:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="2cba9-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="2cba9-104">tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.</span><span class="sxs-lookup"><span data-stu-id="2cba9-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>

### <a name="columns"></a><span data-ttu-id="2cba9-105">Columns</span><span class="sxs-lookup"><span data-stu-id="2cba9-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cba9-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="2cba9-106">Column</span></span></th>
<th><span data-ttu-id="2cba9-107">Тип</span><span class="sxs-lookup"><span data-stu-id="2cba9-107">Type</span></span></th>
<th><span data-ttu-id="2cba9-108">Описание</span><span class="sxs-lookup"><span data-stu-id="2cba9-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cba9-109">локкекспирестиме</span><span class="sxs-lookup"><span data-stu-id="2cba9-109">lockExpiresTime</span></span></p></td>
<td><p><span data-ttu-id="2cba9-110">datetime, не null</span><span class="sxs-lookup"><span data-stu-id="2cba9-110">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="2cba9-p101">Дата и время истечения срока блокировки. Владелец может периодически продлевать этот срок.</span><span class="sxs-lookup"><span data-stu-id="2cba9-p101">Lock expiration date and time. The owner can extend this value periodically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cba9-113">локксерверид</span><span class="sxs-lookup"><span data-stu-id="2cba9-113">lockServerID</span></span></p></td>
<td><p><span data-ttu-id="2cba9-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="2cba9-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2cba9-115">Идентификатора сервера, которому принадлежит блокировка.</span><span class="sxs-lookup"><span data-stu-id="2cba9-115">ID of the server that owns the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cba9-116">локкакторид</span><span class="sxs-lookup"><span data-stu-id="2cba9-116">lockActorID</span></span></p></td>
<td><p><span data-ttu-id="2cba9-117">int, не null</span><span class="sxs-lookup"><span data-stu-id="2cba9-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2cba9-118">Идентификатора участника, которому принадлежит блокировка.</span><span class="sxs-lookup"><span data-stu-id="2cba9-118">ID of the principal that owns the lock.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

