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
ms.openlocfilehash: 0a57e4a3c7a5fdcc1825c140cb6e26f8cede8dc1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="5f808-102">ТблпринЦипалаффилиатионс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f808-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f808-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5f808-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5f808-104">ТблпринЦипалаффилиатионс содержит основные сведения о членстве в расположениях, включая группы безопасности доменных служб Active Directory, в контейнерах Active Directory в доменах.</span><span class="sxs-lookup"><span data-stu-id="5f808-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="5f808-105">Columns</span><span class="sxs-lookup"><span data-stu-id="5f808-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f808-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="5f808-106">Column</span></span></th>
<th><span data-ttu-id="5f808-107">Тип</span><span class="sxs-lookup"><span data-stu-id="5f808-107">Type</span></span></th>
<th><span data-ttu-id="5f808-108">Описание</span><span class="sxs-lookup"><span data-stu-id="5f808-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f808-109">принЦипалид</span><span class="sxs-lookup"><span data-stu-id="5f808-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="5f808-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="5f808-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5f808-111">Идентификатор присоединенного субъекта.</span><span class="sxs-lookup"><span data-stu-id="5f808-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f808-112">аффилиатионид</span><span class="sxs-lookup"><span data-stu-id="5f808-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="5f808-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="5f808-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5f808-p101">Идентификатор субъекта, представляющего присоединение. Каждый субъект (за исключением типов пользователей системы) также присоединен сам к себе.</span><span class="sxs-lookup"><span data-stu-id="5f808-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f808-116">index</span><span class="sxs-lookup"><span data-stu-id="5f808-116">index</span></span></p></td>
<td><p><span data-ttu-id="5f808-117">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5f808-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5f808-118">Индекса.</span><span class="sxs-lookup"><span data-stu-id="5f808-118">Index.</span></span> <span data-ttu-id="5f808-119">Значение для самоназначений равно-1, а для других присоединений он последовательно увеличивается от 1 в каждом &lt;сегменте ПринЦипалид, аффилиатионид.&gt;</span><span class="sxs-lookup"><span data-stu-id="5f808-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f808-120">упдатедби</span><span class="sxs-lookup"><span data-stu-id="5f808-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="5f808-121">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5f808-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5f808-p103">Субъект, выполнивший последнее обновление. Обычно это 1, что означает синхронизацию с Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5f808-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5f808-124">Keys</span><span class="sxs-lookup"><span data-stu-id="5f808-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f808-125">Columns</span><span class="sxs-lookup"><span data-stu-id="5f808-125">Columns</span></span></th>
<th><span data-ttu-id="5f808-126">Описание</span><span class="sxs-lookup"><span data-stu-id="5f808-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f808-127">&lt;ПринЦипалид, index, Аффилиатионид&gt;</span><span class="sxs-lookup"><span data-stu-id="5f808-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="5f808-128">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="5f808-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f808-129">принЦипалид</span><span class="sxs-lookup"><span data-stu-id="5f808-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="5f808-130">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="5f808-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f808-131">аффилиатионид</span><span class="sxs-lookup"><span data-stu-id="5f808-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="5f808-132">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="5f808-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

