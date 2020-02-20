---
title: 'Lync Server 2013: Тблфилетокен'
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
ms.openlocfilehash: 9e3d80b1a326140a94b840c212fc8577a73e468f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="bbb67-102">Тблфилетокен в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbb67-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbb67-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bbb67-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bbb67-104">Таблица tblFileToken содержит временные маркеры для передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="bbb67-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="bbb67-105">Columns</span><span class="sxs-lookup"><span data-stu-id="bbb67-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bbb67-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="bbb67-106">Column</span></span></th>
<th><span data-ttu-id="bbb67-107">Тип</span><span class="sxs-lookup"><span data-stu-id="bbb67-107">Type</span></span></th>
<th><span data-ttu-id="bbb67-108">Описание</span><span class="sxs-lookup"><span data-stu-id="bbb67-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bbb67-109">филетокен</span><span class="sxs-lookup"><span data-stu-id="bbb67-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="bbb67-110">nvarchar (50), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bbb67-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="bbb67-111">Уникальный маркер (GUID).</span><span class="sxs-lookup"><span data-stu-id="bbb67-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbb67-112">филетокенусерид</span><span class="sxs-lookup"><span data-stu-id="bbb67-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="bbb67-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bbb67-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bbb67-114">Идентификатор субъекта, который передает файл.</span><span class="sxs-lookup"><span data-stu-id="bbb67-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbb67-115">филетокенчаннелид</span><span class="sxs-lookup"><span data-stu-id="bbb67-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="bbb67-116">GUID, не NULL</span><span class="sxs-lookup"><span data-stu-id="bbb67-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="bbb67-117">GUID узла комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="bbb67-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbb67-118">филетокенекспиредате</span><span class="sxs-lookup"><span data-stu-id="bbb67-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="bbb67-119">datetime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bbb67-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="bbb67-p101">Срок действия. (Срок действия маркеров истекает через 30 минут, если они не были закреплены; см. описания в этом столбце.)</span><span class="sxs-lookup"><span data-stu-id="bbb67-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbb67-122">филетокенкомплианцефилеурл</span><span class="sxs-lookup"><span data-stu-id="bbb67-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="bbb67-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bbb67-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bbb67-124">URL-адрес переданного файла (для использования службой соответствия).</span><span class="sxs-lookup"><span data-stu-id="bbb67-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbb67-125">филетокенкомплианцесумбнаилурл</span><span class="sxs-lookup"><span data-stu-id="bbb67-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="bbb67-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bbb67-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bbb67-127">URL-адрес эскиза переданного файла (для использования службой соответствия).</span><span class="sxs-lookup"><span data-stu-id="bbb67-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbb67-128">филетокенкомплианцетиме</span><span class="sxs-lookup"><span data-stu-id="bbb67-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="bbb67-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="bbb67-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="bbb67-130">Метка времени для фактической операции передачи файла (для использования службой соответствия).</span><span class="sxs-lookup"><span data-stu-id="bbb67-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbb67-131">филетокенкомплианцеисуплоад</span><span class="sxs-lookup"><span data-stu-id="bbb67-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="bbb67-132">Битовая</span><span class="sxs-lookup"><span data-stu-id="bbb67-132">bit</span></span></p></td>
<td><p><span data-ttu-id="bbb67-133">True при отправке; False при загрузке (для использования службой соответствия).</span><span class="sxs-lookup"><span data-stu-id="bbb67-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbb67-134">филетокенкомплианцепиннед</span><span class="sxs-lookup"><span data-stu-id="bbb67-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="bbb67-135">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bbb67-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="bbb67-p102">True, если маркер закреплен. Используется для сохранения маркера в таблице, пока служба соответствия не получит возможность извлечь из него соответствующие поля.</span><span class="sxs-lookup"><span data-stu-id="bbb67-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="bbb67-138">Keys</span><span class="sxs-lookup"><span data-stu-id="bbb67-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bbb67-139">Столбец</span><span class="sxs-lookup"><span data-stu-id="bbb67-139">Column</span></span></th>
<th><span data-ttu-id="bbb67-140">Описание</span><span class="sxs-lookup"><span data-stu-id="bbb67-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bbb67-141">филетокен</span><span class="sxs-lookup"><span data-stu-id="bbb67-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="bbb67-142">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="bbb67-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbb67-143">филетокенчаннелид</span><span class="sxs-lookup"><span data-stu-id="bbb67-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="bbb67-144">Внешний ключ для поиска в таблице tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="bbb67-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

