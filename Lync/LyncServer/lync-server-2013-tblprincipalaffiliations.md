---
title: 'Lync Server 2013: tblPrincipalAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb5f6400de1c71b4d11101871b2dadedd232a9ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="40ccf-102">tblPrincipalAffiliations в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40ccf-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40ccf-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="40ccf-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="40ccf-104">ТблпринЦипалаффилиатионс содержит основные сведения о членстве в расположениях, в том числе о группах безопасности доменных служб Active Directory, в контейнерах Active Directory в доменах.</span><span class="sxs-lookup"><span data-stu-id="40ccf-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="40ccf-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="40ccf-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40ccf-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="40ccf-106">Column</span></span></th>
<th><span data-ttu-id="40ccf-107">Тип</span><span class="sxs-lookup"><span data-stu-id="40ccf-107">Type</span></span></th>
<th><span data-ttu-id="40ccf-108">Описание</span><span class="sxs-lookup"><span data-stu-id="40ccf-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40ccf-109">ПринЦипалид</span><span class="sxs-lookup"><span data-stu-id="40ccf-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="40ccf-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="40ccf-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="40ccf-111">Идентификатор присоединенного участника.</span><span class="sxs-lookup"><span data-stu-id="40ccf-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40ccf-112">Аффилиатионид</span><span class="sxs-lookup"><span data-stu-id="40ccf-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="40ccf-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="40ccf-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="40ccf-114">Идентификатор участника, представляющего назначение.</span><span class="sxs-lookup"><span data-stu-id="40ccf-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="40ccf-115">Каждый принципал (за исключением системных типов пользователей) также имеет свое Самоназначение.</span><span class="sxs-lookup"><span data-stu-id="40ccf-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40ccf-116">индекса</span><span class="sxs-lookup"><span data-stu-id="40ccf-116">index</span></span></p></td>
<td><p><span data-ttu-id="40ccf-117">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="40ccf-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="40ccf-118">Индекса.</span><span class="sxs-lookup"><span data-stu-id="40ccf-118">Index.</span></span> <span data-ttu-id="40ccf-119">Значение для самостоятельных принадлежностей —-1, а для других — для других — в пределах от 1 в каждом &lt;ПринЦипалид, аффилиатионид&gt; сегмент.</span><span class="sxs-lookup"><span data-stu-id="40ccf-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40ccf-120">Упдатедби</span><span class="sxs-lookup"><span data-stu-id="40ccf-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="40ccf-121">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="40ccf-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="40ccf-122">Основной участник, который обновил Последнее обновление.</span><span class="sxs-lookup"><span data-stu-id="40ccf-122">Principal that did the latest update.</span></span> <span data-ttu-id="40ccf-123">Обычно это 1, что означает синхронизацию Active Directory.</span><span class="sxs-lookup"><span data-stu-id="40ccf-123">This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="40ccf-124">Параметры</span><span class="sxs-lookup"><span data-stu-id="40ccf-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40ccf-125">Столбцов</span><span class="sxs-lookup"><span data-stu-id="40ccf-125">Columns</span></span></th>
<th><span data-ttu-id="40ccf-126">Описание</span><span class="sxs-lookup"><span data-stu-id="40ccf-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40ccf-127">&lt;ПринЦипалид, index, Аффилиатионид&gt;</span><span class="sxs-lookup"><span data-stu-id="40ccf-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="40ccf-128">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="40ccf-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40ccf-129">ПринЦипалид</span><span class="sxs-lookup"><span data-stu-id="40ccf-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="40ccf-130">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="40ccf-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40ccf-131">Аффилиатионид</span><span class="sxs-lookup"><span data-stu-id="40ccf-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="40ccf-132">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="40ccf-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

