---
title: 'Lync Server 2013: Тблфилетокен'
description: 'Lync Server 2013: Тблфилетокен.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c0a0465bd769cff5c23c00a98f79e2346232175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547635"
---
# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="cbba5-103">Тблфилетокен в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbba5-103">tblFileToken in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbba5-104">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="cbba5-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="cbba5-105">Таблица tblFileToken содержит временные маркеры для передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="cbba5-105">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="cbba5-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="cbba5-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbba5-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="cbba5-107">Column</span></span></th>
<th><span data-ttu-id="cbba5-108">Тип</span><span class="sxs-lookup"><span data-stu-id="cbba5-108">Type</span></span></th>
<th><span data-ttu-id="cbba5-109">Описание</span><span class="sxs-lookup"><span data-stu-id="cbba5-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbba5-110">филетокен</span><span class="sxs-lookup"><span data-stu-id="cbba5-110">fileToken</span></span></p></td>
<td><p><span data-ttu-id="cbba5-111">nvarchar (50), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="cbba5-111">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="cbba5-112">Уникальный маркер (GUID).</span><span class="sxs-lookup"><span data-stu-id="cbba5-112">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbba5-113">филетокенусерид</span><span class="sxs-lookup"><span data-stu-id="cbba5-113">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="cbba5-114">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="cbba5-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="cbba5-115">Идентификатор субъекта, который передает файл.</span><span class="sxs-lookup"><span data-stu-id="cbba5-115">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbba5-116">филетокенчаннелид</span><span class="sxs-lookup"><span data-stu-id="cbba5-116">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="cbba5-117">GUID, не NULL</span><span class="sxs-lookup"><span data-stu-id="cbba5-117">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="cbba5-118">GUID узла комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="cbba5-118">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbba5-119">филетокенекспиредате</span><span class="sxs-lookup"><span data-stu-id="cbba5-119">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="cbba5-120">datetime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="cbba5-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="cbba5-p101">Срок действия. (Срок действия маркеров истекает через 30 минут, если они не были закреплены; см. описания в этом столбце.)</span><span class="sxs-lookup"><span data-stu-id="cbba5-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbba5-123">филетокенкомплианцефилеурл</span><span class="sxs-lookup"><span data-stu-id="cbba5-123">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="cbba5-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cbba5-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cbba5-125">URL-адрес переданного файла (для использования службой соответствия).</span><span class="sxs-lookup"><span data-stu-id="cbba5-125">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbba5-126">филетокенкомплианцесумбнаилурл</span><span class="sxs-lookup"><span data-stu-id="cbba5-126">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="cbba5-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cbba5-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cbba5-128">URL-адрес эскиза переданного файла (для использования службой соответствия).</span><span class="sxs-lookup"><span data-stu-id="cbba5-128">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbba5-129">филетокенкомплианцетиме</span><span class="sxs-lookup"><span data-stu-id="cbba5-129">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="cbba5-130">datetime2</span><span class="sxs-lookup"><span data-stu-id="cbba5-130">datetime2</span></span></p></td>
<td><p><span data-ttu-id="cbba5-131">Метка времени для фактической операции передачи файла (для использования службой соответствия).</span><span class="sxs-lookup"><span data-stu-id="cbba5-131">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbba5-132">филетокенкомплианцеисуплоад</span><span class="sxs-lookup"><span data-stu-id="cbba5-132">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="cbba5-133">Битовая</span><span class="sxs-lookup"><span data-stu-id="cbba5-133">bit</span></span></p></td>
<td><p><span data-ttu-id="cbba5-134">True при отправке; False при загрузке (для использования службой соответствия).</span><span class="sxs-lookup"><span data-stu-id="cbba5-134">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbba5-135">филетокенкомплианцепиннед</span><span class="sxs-lookup"><span data-stu-id="cbba5-135">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="cbba5-136">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="cbba5-136">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="cbba5-p102">True, если маркер закреплен. Используется для сохранения маркера в таблице, пока служба соответствия не получит возможность извлечь из него соответствующие поля.</span><span class="sxs-lookup"><span data-stu-id="cbba5-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="cbba5-139">Keys</span><span class="sxs-lookup"><span data-stu-id="cbba5-139">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbba5-140">Столбец</span><span class="sxs-lookup"><span data-stu-id="cbba5-140">Column</span></span></th>
<th><span data-ttu-id="cbba5-141">Описание</span><span class="sxs-lookup"><span data-stu-id="cbba5-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbba5-142">филетокен</span><span class="sxs-lookup"><span data-stu-id="cbba5-142">fileToken</span></span></p></td>
<td><p><span data-ttu-id="cbba5-143">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="cbba5-143">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbba5-144">филетокенчаннелид</span><span class="sxs-lookup"><span data-stu-id="cbba5-144">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="cbba5-145">Внешний ключ для поиска в таблице tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="cbba5-145">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

