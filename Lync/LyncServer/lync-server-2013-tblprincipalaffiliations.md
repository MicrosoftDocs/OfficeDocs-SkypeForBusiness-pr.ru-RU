---
title: 'Lync Server 2013: ТблпринЦипалаффилиатионс'
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
ms.openlocfilehash: ee16c492a42cb98ff3b5f326bd6f43a57c4d3f56
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="bdb92-102">ТблпринЦипалаффилиатионс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdb92-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdb92-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bdb92-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bdb92-104">ТблпринЦипалаффилиатионс содержит основные сведения о членстве в расположениях, включая группы безопасности доменных служб Active Directory, в контейнерах Active Directory в доменах.</span><span class="sxs-lookup"><span data-stu-id="bdb92-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="bdb92-105">Columns</span><span class="sxs-lookup"><span data-stu-id="bdb92-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdb92-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="bdb92-106">Column</span></span></th>
<th><span data-ttu-id="bdb92-107">Тип</span><span class="sxs-lookup"><span data-stu-id="bdb92-107">Type</span></span></th>
<th><span data-ttu-id="bdb92-108">Описание</span><span class="sxs-lookup"><span data-stu-id="bdb92-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdb92-109">принЦипалид</span><span class="sxs-lookup"><span data-stu-id="bdb92-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="bdb92-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="bdb92-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bdb92-111">Идентификатор присоединенного субъекта.</span><span class="sxs-lookup"><span data-stu-id="bdb92-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdb92-112">аффилиатионид</span><span class="sxs-lookup"><span data-stu-id="bdb92-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="bdb92-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="bdb92-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bdb92-p101">Идентификатор субъекта, представляющего присоединение. Каждый субъект (за исключением типов пользователей системы) также присоединен сам к себе.</span><span class="sxs-lookup"><span data-stu-id="bdb92-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdb92-116">index</span><span class="sxs-lookup"><span data-stu-id="bdb92-116">index</span></span></p></td>
<td><p><span data-ttu-id="bdb92-117">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bdb92-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bdb92-118">Индекса.</span><span class="sxs-lookup"><span data-stu-id="bdb92-118">Index.</span></span> <span data-ttu-id="bdb92-119">Значение для самоназначений равно-1, а для других присоединений он последовательно увеличивается от 1 в каждом &lt;сегменте ПринЦипалид, аффилиатионид.&gt;</span><span class="sxs-lookup"><span data-stu-id="bdb92-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdb92-120">упдатедби</span><span class="sxs-lookup"><span data-stu-id="bdb92-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="bdb92-121">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bdb92-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bdb92-p103">Субъект, выполнивший последнее обновление. Обычно это 1, что означает синхронизацию с Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bdb92-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="bdb92-124">Keys</span><span class="sxs-lookup"><span data-stu-id="bdb92-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdb92-125">Columns</span><span class="sxs-lookup"><span data-stu-id="bdb92-125">Columns</span></span></th>
<th><span data-ttu-id="bdb92-126">Описание</span><span class="sxs-lookup"><span data-stu-id="bdb92-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdb92-127">&lt;ПринЦипалид, index, Аффилиатионид&gt;</span><span class="sxs-lookup"><span data-stu-id="bdb92-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="bdb92-128">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="bdb92-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdb92-129">принЦипалид</span><span class="sxs-lookup"><span data-stu-id="bdb92-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="bdb92-130">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="bdb92-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdb92-131">аффилиатионид</span><span class="sxs-lookup"><span data-stu-id="bdb92-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="bdb92-132">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="bdb92-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

