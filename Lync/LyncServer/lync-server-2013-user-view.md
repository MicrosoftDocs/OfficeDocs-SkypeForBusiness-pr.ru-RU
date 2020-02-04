---
title: 'Lync Server 2013: представление пользователя'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8e88d7a9fa66f309bbd64ab064ec95adafc40b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="d7bd9-102">Представление пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7bd9-102">User view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7bd9-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d7bd9-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d7bd9-104">В представлении пользователя хранятся сведения о пользователях, которые участвовали в звонках или сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d7bd9-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="d7bd9-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d7bd9-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7bd9-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="d7bd9-106">Column</span></span></th>
<th><span data-ttu-id="d7bd9-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="d7bd9-107">Data Type</span></span></th>
<th><span data-ttu-id="d7bd9-108">Подробности</span><span class="sxs-lookup"><span data-stu-id="d7bd9-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7bd9-109">Идентификатора пользователя</span><span class="sxs-lookup"><span data-stu-id="d7bd9-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="d7bd9-110">целое</span><span class="sxs-lookup"><span data-stu-id="d7bd9-110">int</span></span></p></td>
<td><p><span data-ttu-id="d7bd9-111">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="d7bd9-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7bd9-112">усерури</span><span class="sxs-lookup"><span data-stu-id="d7bd9-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="d7bd9-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d7bd9-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d7bd9-114">Универсальный код ресурса (URI) пользователя.</span><span class="sxs-lookup"><span data-stu-id="d7bd9-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7bd9-115">тенанткэй</span><span class="sxs-lookup"><span data-stu-id="d7bd9-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="d7bd9-116">идентификатора</span><span class="sxs-lookup"><span data-stu-id="d7bd9-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d7bd9-117">Клиент пользователя.</span><span class="sxs-lookup"><span data-stu-id="d7bd9-117">Tenant of user.</span></span> <span data-ttu-id="d7bd9-118">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d7bd9-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7bd9-119">уритипе</span><span class="sxs-lookup"><span data-stu-id="d7bd9-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="d7bd9-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d7bd9-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7bd9-121">Тип универсального кода ресурса (URI) пользователя.</span><span class="sxs-lookup"><span data-stu-id="d7bd9-121">Type of user URI.</span></span> <span data-ttu-id="d7bd9-122">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d7bd9-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

