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
ms.openlocfilehash: ad3ef2afaa162219d140a4eaef204dc6e1e2ab02
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="2779e-102">Тбладупдатес в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2779e-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2779e-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2779e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2779e-104">Тбладупдатес содержит изменения доменных служб Active Directory, которые еще не были обработаны на последующих этапах синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2779e-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="2779e-105">Columns</span><span class="sxs-lookup"><span data-stu-id="2779e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2779e-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="2779e-106">Column</span></span></th>
<th><span data-ttu-id="2779e-107">Тип</span><span class="sxs-lookup"><span data-stu-id="2779e-107">Type</span></span></th>
<th><span data-ttu-id="2779e-108">Описание</span><span class="sxs-lookup"><span data-stu-id="2779e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2779e-109">прингуид</span><span class="sxs-lookup"><span data-stu-id="2779e-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="2779e-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="2779e-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="2779e-111">Глобальный уникальный ИД измененного объекта.</span><span class="sxs-lookup"><span data-stu-id="2779e-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2779e-112">принадпас</span><span class="sxs-lookup"><span data-stu-id="2779e-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="2779e-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="2779e-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="2779e-114">Различающееся имя объекта.</span><span class="sxs-lookup"><span data-stu-id="2779e-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2779e-115">принаттрибутесчанжед</span><span class="sxs-lookup"><span data-stu-id="2779e-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="2779e-116">bit, не равно null</span><span class="sxs-lookup"><span data-stu-id="2779e-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2779e-117">TRUE, если изменился хотя бы один атрибут объекта.</span><span class="sxs-lookup"><span data-stu-id="2779e-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2779e-118">принмемберсчанжед</span><span class="sxs-lookup"><span data-stu-id="2779e-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="2779e-119">bit, не равно null</span><span class="sxs-lookup"><span data-stu-id="2779e-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2779e-120">TRUE, если изменилось членство.</span><span class="sxs-lookup"><span data-stu-id="2779e-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2779e-121">принаффилиатионсчанжед</span><span class="sxs-lookup"><span data-stu-id="2779e-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="2779e-122">bit, не равно null</span><span class="sxs-lookup"><span data-stu-id="2779e-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2779e-123">Не используется.</span><span class="sxs-lookup"><span data-stu-id="2779e-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2779e-124">принделетед</span><span class="sxs-lookup"><span data-stu-id="2779e-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="2779e-125">bit, not null</span><span class="sxs-lookup"><span data-stu-id="2779e-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2779e-126">TRUE, если объект был удален.</span><span class="sxs-lookup"><span data-stu-id="2779e-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2779e-127">ластупдатед</span><span class="sxs-lookup"><span data-stu-id="2779e-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="2779e-128">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="2779e-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="2779e-129">Метка времени добавления строки.</span><span class="sxs-lookup"><span data-stu-id="2779e-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

