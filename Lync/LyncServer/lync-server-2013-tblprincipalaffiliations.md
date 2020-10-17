---
title: 'Lync Server 2013: ТблпринЦипалаффилиатионс'
description: 'Lync Server 2013: ТблпринЦипалаффилиатионс.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c373147a58300e64f22e60e989a777c59b2653
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547485"
---
# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="b8883-103">ТблпринЦипалаффилиатионс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8883-103">tblPrincipalAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8883-104">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b8883-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b8883-105">ТблпринЦипалаффилиатионс содержит основные сведения о членстве в расположениях, включая группы безопасности доменных служб Active Directory, в контейнерах Active Directory в доменах.</span><span class="sxs-lookup"><span data-stu-id="b8883-105">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="b8883-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="b8883-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8883-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="b8883-107">Column</span></span></th>
<th><span data-ttu-id="b8883-108">Тип</span><span class="sxs-lookup"><span data-stu-id="b8883-108">Type</span></span></th>
<th><span data-ttu-id="b8883-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b8883-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8883-110">принЦипалид</span><span class="sxs-lookup"><span data-stu-id="b8883-110">principalID</span></span></p></td>
<td><p><span data-ttu-id="b8883-111">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="b8883-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b8883-112">Идентификатор присоединенного субъекта.</span><span class="sxs-lookup"><span data-stu-id="b8883-112">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8883-113">аффилиатионид</span><span class="sxs-lookup"><span data-stu-id="b8883-113">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="b8883-114">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="b8883-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b8883-p101">Идентификатор субъекта, представляющего присоединение. Каждый субъект (за исключением типов пользователей системы) также присоединен сам к себе.</span><span class="sxs-lookup"><span data-stu-id="b8883-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8883-117">index</span><span class="sxs-lookup"><span data-stu-id="b8883-117">index</span></span></p></td>
<td><p><span data-ttu-id="b8883-118">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="b8883-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b8883-119">Индекса.</span><span class="sxs-lookup"><span data-stu-id="b8883-119">Index.</span></span> <span data-ttu-id="b8883-120">Значение для самоназначений равно-1, а для других присоединений он последовательно увеличивается от 1 в каждом &lt; сегменте принЦипалид, аффилиатионид &gt; .</span><span class="sxs-lookup"><span data-stu-id="b8883-120">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8883-121">упдатедби</span><span class="sxs-lookup"><span data-stu-id="b8883-121">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="b8883-122">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="b8883-122">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b8883-p103">Субъект, выполнивший последнее обновление. Обычно это 1, что означает синхронизацию с Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b8883-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b8883-125">Keys</span><span class="sxs-lookup"><span data-stu-id="b8883-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8883-126">Столбцы</span><span class="sxs-lookup"><span data-stu-id="b8883-126">Columns</span></span></th>
<th><span data-ttu-id="b8883-127">Описание</span><span class="sxs-lookup"><span data-stu-id="b8883-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8883-128">&lt;ПринЦипалид, index, Аффилиатионид&gt;</span><span class="sxs-lookup"><span data-stu-id="b8883-128">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="b8883-129">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="b8883-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8883-130">принЦипалид</span><span class="sxs-lookup"><span data-stu-id="b8883-130">principalID</span></span></p></td>
<td><p><span data-ttu-id="b8883-131">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="b8883-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8883-132">аффилиатионид</span><span class="sxs-lookup"><span data-stu-id="b8883-132">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="b8883-133">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="b8883-133">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

