---
title: 'Lync Server 2013: ТблпринЦипалмемберс'
description: 'Lync Server 2013: ТблпринЦипалмемберс.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMembers
ms:assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615022(v=OCS.15)
ms:contentKeyID: 48184965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bbb8be0b83d09b1bd54ea98655558581e6df834
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573185"
---
# <a name="tblprincipalmembers-in-lync-server-2013"></a><span data-ttu-id="cbb26-103">ТблпринЦипалмемберс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbb26-103">tblPrincipalMembers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbb26-104">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="cbb26-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="cbb26-105">Таблица tblPrincipalMembers содержит сведения о членстве субъектов.</span><span class="sxs-lookup"><span data-stu-id="cbb26-105">tblPrincipalMembers contains principal memberships.</span></span>

### <a name="columns"></a><span data-ttu-id="cbb26-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="cbb26-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbb26-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="cbb26-107">Column</span></span></th>
<th><span data-ttu-id="cbb26-108">Тип</span><span class="sxs-lookup"><span data-stu-id="cbb26-108">Type</span></span></th>
<th><span data-ttu-id="cbb26-109">Описание</span><span class="sxs-lookup"><span data-stu-id="cbb26-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbb26-110">prinID</span><span class="sxs-lookup"><span data-stu-id="cbb26-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="cbb26-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="cbb26-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="cbb26-112">ИД субъекта.</span><span class="sxs-lookup"><span data-stu-id="cbb26-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbb26-113">мемберадпас</span><span class="sxs-lookup"><span data-stu-id="cbb26-113">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="cbb26-114">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="cbb26-114">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="cbb26-p101">Различающееся имя участника. Участник не должен быть субъектом (в таблице tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="cbb26-p101">Distinguished name of a member. A member does not have to be a principal (in tblPrincipal table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="cbb26-117">Keys</span><span class="sxs-lookup"><span data-stu-id="cbb26-117">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbb26-118">Столбец</span><span class="sxs-lookup"><span data-stu-id="cbb26-118">Column</span></span></th>
<th><span data-ttu-id="cbb26-119">Описание</span><span class="sxs-lookup"><span data-stu-id="cbb26-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbb26-120">&lt;prinID, Мемберадпас&gt;</span><span class="sxs-lookup"><span data-stu-id="cbb26-120">&lt;prinID, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="cbb26-121">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="cbb26-121">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbb26-122">prinID</span><span class="sxs-lookup"><span data-stu-id="cbb26-122">prinID</span></span></p></td>
<td><p><span data-ttu-id="cbb26-123">Внешний ключ для поиска в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="cbb26-123">Foreign key with lookup in tblPrincipal.prinID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

