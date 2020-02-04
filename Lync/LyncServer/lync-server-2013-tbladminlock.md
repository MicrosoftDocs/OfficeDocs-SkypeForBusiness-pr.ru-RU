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
ms.openlocfilehash: 89e1509a1a84e0a9dd03527eedfb0b9e6da1590e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladminlock-in-lync-server-2013"></a><span data-ttu-id="21b1a-102">tblAdminLock в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21b1a-102">tblAdminLock in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21b1a-103">_**Тема последнего изменения:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="21b1a-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="21b1a-104">Тбладминлокк содержит блокировку администратора, которая необходима для выполнения некоторых команд администратора.</span><span class="sxs-lookup"><span data-stu-id="21b1a-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>

### <a name="columns"></a><span data-ttu-id="21b1a-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="21b1a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21b1a-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="21b1a-106">Column</span></span></th>
<th><span data-ttu-id="21b1a-107">Тип</span><span class="sxs-lookup"><span data-stu-id="21b1a-107">Type</span></span></th>
<th><span data-ttu-id="21b1a-108">Описание</span><span class="sxs-lookup"><span data-stu-id="21b1a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21b1a-109">локкекспирестиме</span><span class="sxs-lookup"><span data-stu-id="21b1a-109">lockExpiresTime</span></span></p></td>
<td><p><span data-ttu-id="21b1a-110">DateTime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="21b1a-110">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="21b1a-111">Заблокируйте дату и время окончания срока действия.</span><span class="sxs-lookup"><span data-stu-id="21b1a-111">Lock expiration date and time.</span></span> <span data-ttu-id="21b1a-112">Владелец может периодически увеличивать это значение.</span><span class="sxs-lookup"><span data-stu-id="21b1a-112">The owner can extend this value periodically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21b1a-113">локксерверид</span><span class="sxs-lookup"><span data-stu-id="21b1a-113">lockServerID</span></span></p></td>
<td><p><span data-ttu-id="21b1a-114">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="21b1a-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="21b1a-115">Идентификатор сервера, владеющего блокировкой.</span><span class="sxs-lookup"><span data-stu-id="21b1a-115">ID of the server that owns the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21b1a-116">локкакторид</span><span class="sxs-lookup"><span data-stu-id="21b1a-116">lockActorID</span></span></p></td>
<td><p><span data-ttu-id="21b1a-117">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="21b1a-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="21b1a-118">Идентификатор участника, владеющего блокировкой.</span><span class="sxs-lookup"><span data-stu-id="21b1a-118">ID of the principal that owns the lock.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

