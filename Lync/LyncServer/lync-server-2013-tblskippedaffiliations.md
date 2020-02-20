---
title: 'Lync Server 2013: tblSkippedAffiliations'
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
ms.openlocfilehash: d21dbda8b649588e691d285c62ff865e9f001308
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="96992-102">tblSkippedAffiliations в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96992-102">tblSkippedAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96992-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="96992-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="96992-104">tblSkippedAffiliations содержит назначения, которые не удалось прочесть (обычно из-за ошибок доступа к доменным службам Active Directory).</span><span class="sxs-lookup"><span data-stu-id="96992-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="96992-105">Columns</span><span class="sxs-lookup"><span data-stu-id="96992-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96992-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="96992-106">Column</span></span></th>
<th><span data-ttu-id="96992-107">Тип</span><span class="sxs-lookup"><span data-stu-id="96992-107">Type</span></span></th>
<th><span data-ttu-id="96992-108">Описание</span><span class="sxs-lookup"><span data-stu-id="96992-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96992-109">prinID</span><span class="sxs-lookup"><span data-stu-id="96992-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="96992-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="96992-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="96992-111">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="96992-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96992-112">аффдескриптион</span><span class="sxs-lookup"><span data-stu-id="96992-112">affDescription</span></span></p></td>
<td><p><span data-ttu-id="96992-113">nvarchar (256), не NULL</span><span class="sxs-lookup"><span data-stu-id="96992-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="96992-114">Строка, идентифицирующая принадлежность.</span><span class="sxs-lookup"><span data-stu-id="96992-114">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="96992-115">Формат: GUID: {0} {1} &gt; идентификатор URI:{2}</span><span class="sxs-lookup"><span data-stu-id="96992-115">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96992-116">упдатедби</span><span class="sxs-lookup"><span data-stu-id="96992-116">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="96992-117">int, не NULL</span><span class="sxs-lookup"><span data-stu-id="96992-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="96992-p101">Идентификатор субъекта, обновившего эту строку. Он всегда равен 1 (системный пользователь) поскольку синхронизация Active Directory является единственным источником этих записей.</span><span class="sxs-lookup"><span data-stu-id="96992-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="96992-120">Keys</span><span class="sxs-lookup"><span data-stu-id="96992-120">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96992-121">Столбцы</span><span class="sxs-lookup"><span data-stu-id="96992-121">Column(s)</span></span></th>
<th><span data-ttu-id="96992-122">Описание</span><span class="sxs-lookup"><span data-stu-id="96992-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96992-123">&lt;prinID, Аффдескриптион&gt;</span><span class="sxs-lookup"><span data-stu-id="96992-123">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="96992-124">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="96992-124">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96992-125">prinID</span><span class="sxs-lookup"><span data-stu-id="96992-125">prinID</span></span></p></td>
<td><p><span data-ttu-id="96992-126">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="96992-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

