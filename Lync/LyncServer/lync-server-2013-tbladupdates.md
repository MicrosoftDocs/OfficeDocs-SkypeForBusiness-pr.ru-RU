---
title: 'Lync Server 2013: tblADUpdates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f171d8346442f915cd71fb48d51bba80bcfa32ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="fd29d-102">tblADUpdates в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd29d-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd29d-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="fd29d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="fd29d-104">Тбладупдатес содержит изменения доменных служб Active Directory, которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fd29d-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="fd29d-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="fd29d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd29d-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="fd29d-106">Column</span></span></th>
<th><span data-ttu-id="fd29d-107">Тип</span><span class="sxs-lookup"><span data-stu-id="fd29d-107">Type</span></span></th>
<th><span data-ttu-id="fd29d-108">Описание</span><span class="sxs-lookup"><span data-stu-id="fd29d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd29d-109">Прингуид</span><span class="sxs-lookup"><span data-stu-id="fd29d-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="fd29d-110">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="fd29d-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="fd29d-111">Идентификатор GUID участника измененного объекта.</span><span class="sxs-lookup"><span data-stu-id="fd29d-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd29d-112">Принадпас</span><span class="sxs-lookup"><span data-stu-id="fd29d-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="fd29d-113">nvarchar (384), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fd29d-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="fd29d-114">Отличительное имя объекта.</span><span class="sxs-lookup"><span data-stu-id="fd29d-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd29d-115">Принаттрибутесчанжед</span><span class="sxs-lookup"><span data-stu-id="fd29d-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="fd29d-116">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fd29d-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="fd29d-117">Значение true, если по крайней мере один из атрибутов объекта изменился.</span><span class="sxs-lookup"><span data-stu-id="fd29d-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd29d-118">Принмемберсчанжед</span><span class="sxs-lookup"><span data-stu-id="fd29d-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="fd29d-119">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fd29d-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="fd29d-120">Значение true, если изменилось членство.</span><span class="sxs-lookup"><span data-stu-id="fd29d-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd29d-121">Принаффилиатионсчанжед</span><span class="sxs-lookup"><span data-stu-id="fd29d-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="fd29d-122">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fd29d-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="fd29d-123">Не используется.</span><span class="sxs-lookup"><span data-stu-id="fd29d-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd29d-124">Принделетед</span><span class="sxs-lookup"><span data-stu-id="fd29d-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="fd29d-125">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fd29d-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="fd29d-126">Значение true, если объект был удален.</span><span class="sxs-lookup"><span data-stu-id="fd29d-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd29d-127">Ластупдатед</span><span class="sxs-lookup"><span data-stu-id="fd29d-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="fd29d-128">DateTime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fd29d-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="fd29d-129">Метка времени вставки строки.</span><span class="sxs-lookup"><span data-stu-id="fd29d-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

