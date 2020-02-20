---
title: 'Lync Server 2013: Тбладупдатес'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee3f0d881e26c3d26773b1b59feca3d1d02665dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="2c04f-102">Тбладупдатес в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c04f-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c04f-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2c04f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2c04f-104">Тбладупдатес содержит изменения доменных служб Active Directory, которые еще не были обработаны на последующих этапах синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2c04f-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="2c04f-105">Columns</span><span class="sxs-lookup"><span data-stu-id="2c04f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c04f-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="2c04f-106">Column</span></span></th>
<th><span data-ttu-id="2c04f-107">Тип</span><span class="sxs-lookup"><span data-stu-id="2c04f-107">Type</span></span></th>
<th><span data-ttu-id="2c04f-108">Описание</span><span class="sxs-lookup"><span data-stu-id="2c04f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c04f-109">прингуид</span><span class="sxs-lookup"><span data-stu-id="2c04f-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="2c04f-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="2c04f-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="2c04f-111">Глобальный уникальный ИД измененного объекта.</span><span class="sxs-lookup"><span data-stu-id="2c04f-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c04f-112">принадпас</span><span class="sxs-lookup"><span data-stu-id="2c04f-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="2c04f-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="2c04f-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="2c04f-114">Различающееся имя объекта.</span><span class="sxs-lookup"><span data-stu-id="2c04f-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c04f-115">принаттрибутесчанжед</span><span class="sxs-lookup"><span data-stu-id="2c04f-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="2c04f-116">bit, не равно null</span><span class="sxs-lookup"><span data-stu-id="2c04f-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2c04f-117">TRUE, если изменился хотя бы один атрибут объекта.</span><span class="sxs-lookup"><span data-stu-id="2c04f-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c04f-118">принмемберсчанжед</span><span class="sxs-lookup"><span data-stu-id="2c04f-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="2c04f-119">bit, не равно null</span><span class="sxs-lookup"><span data-stu-id="2c04f-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2c04f-120">TRUE, если изменилось членство.</span><span class="sxs-lookup"><span data-stu-id="2c04f-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c04f-121">принаффилиатионсчанжед</span><span class="sxs-lookup"><span data-stu-id="2c04f-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="2c04f-122">bit, не равно null</span><span class="sxs-lookup"><span data-stu-id="2c04f-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2c04f-123">Не используется.</span><span class="sxs-lookup"><span data-stu-id="2c04f-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c04f-124">принделетед</span><span class="sxs-lookup"><span data-stu-id="2c04f-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="2c04f-125">bit, not null</span><span class="sxs-lookup"><span data-stu-id="2c04f-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2c04f-126">TRUE, если объект был удален.</span><span class="sxs-lookup"><span data-stu-id="2c04f-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c04f-127">ластупдатед</span><span class="sxs-lookup"><span data-stu-id="2c04f-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="2c04f-128">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="2c04f-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="2c04f-129">Метка времени добавления строки.</span><span class="sxs-lookup"><span data-stu-id="2c04f-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

