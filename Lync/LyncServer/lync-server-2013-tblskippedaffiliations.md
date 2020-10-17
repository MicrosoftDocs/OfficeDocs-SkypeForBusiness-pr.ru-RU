---
title: 'Lync Server 2013: tblSkippedAffiliations'
description: 'Lync Server 2013: tblSkippedAffiliations.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31746cee7302d34a1d19b3059ca1da6beab9345d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563805"
---
# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="9365c-103">tblSkippedAffiliations в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9365c-103">tblSkippedAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9365c-104">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="9365c-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="9365c-105">tblSkippedAffiliations содержит назначения, которые не удалось прочесть (обычно из-за ошибок доступа к доменным службам Active Directory).</span><span class="sxs-lookup"><span data-stu-id="9365c-105">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="9365c-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="9365c-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9365c-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="9365c-107">Column</span></span></th>
<th><span data-ttu-id="9365c-108">Тип</span><span class="sxs-lookup"><span data-stu-id="9365c-108">Type</span></span></th>
<th><span data-ttu-id="9365c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9365c-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9365c-110">prinID</span><span class="sxs-lookup"><span data-stu-id="9365c-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="9365c-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="9365c-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9365c-112">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="9365c-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9365c-113">аффдескриптион</span><span class="sxs-lookup"><span data-stu-id="9365c-113">affDescription</span></span></p></td>
<td><p><span data-ttu-id="9365c-114">nvarchar (256), не NULL</span><span class="sxs-lookup"><span data-stu-id="9365c-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="9365c-115">Строка, идентифицирующая принадлежность.</span><span class="sxs-lookup"><span data-stu-id="9365c-115">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="9365c-116">Формат: GUID: {0} {1} &gt; идентификатор URI:{2}</span><span class="sxs-lookup"><span data-stu-id="9365c-116">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9365c-117">упдатедби</span><span class="sxs-lookup"><span data-stu-id="9365c-117">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="9365c-118">int, не NULL</span><span class="sxs-lookup"><span data-stu-id="9365c-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9365c-p101">Идентификатор субъекта, обновившего эту строку. Он всегда равен 1 (системный пользователь) поскольку синхронизация Active Directory является единственным источником этих записей.</span><span class="sxs-lookup"><span data-stu-id="9365c-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9365c-121">Keys</span><span class="sxs-lookup"><span data-stu-id="9365c-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9365c-122">Столбцы</span><span class="sxs-lookup"><span data-stu-id="9365c-122">Column(s)</span></span></th>
<th><span data-ttu-id="9365c-123">Описание</span><span class="sxs-lookup"><span data-stu-id="9365c-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9365c-124">&lt;prinID, Аффдескриптион&gt;</span><span class="sxs-lookup"><span data-stu-id="9365c-124">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="9365c-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="9365c-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9365c-126">prinID</span><span class="sxs-lookup"><span data-stu-id="9365c-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="9365c-127">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="9365c-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

