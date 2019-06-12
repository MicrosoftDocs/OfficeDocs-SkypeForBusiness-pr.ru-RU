---
title: 'Lync Server 2013: tblPrincipalMembers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalMembers
ms:assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615022(v=OCS.15)
ms:contentKeyID: 48184965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b35af88b4b1c0e32ceb6af97b379ded66b437f7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmembers-in-lync-server-2013"></a><span data-ttu-id="79978-102">tblPrincipalMembers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79978-102">tblPrincipalMembers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79978-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="79978-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="79978-104">ТблпринЦипалмемберс включает участников участника.</span><span class="sxs-lookup"><span data-stu-id="79978-104">tblPrincipalMembers contains principal memberships.</span></span>

### <a name="columns"></a><span data-ttu-id="79978-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="79978-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79978-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="79978-106">Column</span></span></th>
<th><span data-ttu-id="79978-107">Тип</span><span class="sxs-lookup"><span data-stu-id="79978-107">Type</span></span></th>
<th><span data-ttu-id="79978-108">Описание</span><span class="sxs-lookup"><span data-stu-id="79978-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79978-109">Принид</span><span class="sxs-lookup"><span data-stu-id="79978-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="79978-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="79978-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="79978-111">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="79978-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79978-112">Мемберадпас</span><span class="sxs-lookup"><span data-stu-id="79978-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="79978-113">nvarchar (384), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="79978-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="79978-114">Отличительное имя участника.</span><span class="sxs-lookup"><span data-stu-id="79978-114">Distinguished name of a member.</span></span> <span data-ttu-id="79978-115">Участник может не быть участником (в таблице ТблпринЦипал).</span><span class="sxs-lookup"><span data-stu-id="79978-115">A member does not have to be a principal (in tblPrincipal table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="79978-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="79978-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79978-117">Столбец</span><span class="sxs-lookup"><span data-stu-id="79978-117">Column</span></span></th>
<th><span data-ttu-id="79978-118">Описание</span><span class="sxs-lookup"><span data-stu-id="79978-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79978-119">&lt;Принид, Мемберадпас&gt;</span><span class="sxs-lookup"><span data-stu-id="79978-119">&lt;prinID, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="79978-120">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="79978-120">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79978-121">Принид</span><span class="sxs-lookup"><span data-stu-id="79978-121">prinID</span></span></p></td>
<td><p><span data-ttu-id="79978-122">Внешний ключ с подстановкой в ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="79978-122">Foreign key with lookup in tblPrincipal.prinID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

