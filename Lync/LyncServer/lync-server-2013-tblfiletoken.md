---
title: 'Lync Server 2013: tblFileToken'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9146c168e62bd0602a76cd77ab678c84ba5e44da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="bf9c0-102">tblFileToken в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf9c0-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf9c0-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bf9c0-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bf9c0-104">Тблфилетокен включает временные маркеры для целей обмена файлами.</span><span class="sxs-lookup"><span data-stu-id="bf9c0-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="bf9c0-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="bf9c0-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf9c0-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="bf9c0-106">Column</span></span></th>
<th><span data-ttu-id="bf9c0-107">Тип</span><span class="sxs-lookup"><span data-stu-id="bf9c0-107">Type</span></span></th>
<th><span data-ttu-id="bf9c0-108">Описание</span><span class="sxs-lookup"><span data-stu-id="bf9c0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf9c0-109">Филетокен</span><span class="sxs-lookup"><span data-stu-id="bf9c0-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-110">nvarchar (50), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bf9c0-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-111">Уникальный маркер (GUID).</span><span class="sxs-lookup"><span data-stu-id="bf9c0-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf9c0-112">Филетокенусерид</span><span class="sxs-lookup"><span data-stu-id="bf9c0-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bf9c0-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-114">Идентификатор участника, который передает файл.</span><span class="sxs-lookup"><span data-stu-id="bf9c0-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf9c0-115">Филетокенчаннелид</span><span class="sxs-lookup"><span data-stu-id="bf9c0-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-116">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="bf9c0-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-117">GUID узла комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="bf9c0-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf9c0-118">Филетокенекспиредате</span><span class="sxs-lookup"><span data-stu-id="bf9c0-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-119">DateTime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bf9c0-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-120">Время окончания срока действия.</span><span class="sxs-lookup"><span data-stu-id="bf9c0-120">Expiration time.</span></span> <span data-ttu-id="bf9c0-121">(Срок действия токенов истекает через 30 минут, за исключением случаев, когда они закреплены (в этой статье описаны следующие описания).</span><span class="sxs-lookup"><span data-stu-id="bf9c0-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf9c0-122">Филетокенкомплианцефилеурл</span><span class="sxs-lookup"><span data-stu-id="bf9c0-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bf9c0-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-124">URL-адрес перенесенного файла (для использования службы соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="bf9c0-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf9c0-125">Филетокенкомплианцесумбнаилурл</span><span class="sxs-lookup"><span data-stu-id="bf9c0-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bf9c0-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-127">URL-адрес миниатюры перенесенного файла (для использования службой соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="bf9c0-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf9c0-128">Филетокенкомплианцетиме</span><span class="sxs-lookup"><span data-stu-id="bf9c0-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="bf9c0-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-130">Метка времени для фактической операции передачи файлов (для использования службой соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="bf9c0-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf9c0-131">Филетокенкомплианцеисуплоад</span><span class="sxs-lookup"><span data-stu-id="bf9c0-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-132">бит</span><span class="sxs-lookup"><span data-stu-id="bf9c0-132">bit</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-133">Значение true, если отправка; Значение false, если Download (для использования службы соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="bf9c0-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf9c0-134">Филетокенкомплианцепиннед</span><span class="sxs-lookup"><span data-stu-id="bf9c0-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-135">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bf9c0-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-136">Значение true, если маркер закреплен.</span><span class="sxs-lookup"><span data-stu-id="bf9c0-136">True if token is pinned.</span></span> <span data-ttu-id="bf9c0-137">Она используется для хранения токенов в таблице до тех пор, пока служба соответствия требованиям не сможет получить из нее нужные поля.</span><span class="sxs-lookup"><span data-stu-id="bf9c0-137">It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="bf9c0-138">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf9c0-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf9c0-139">Столбец</span><span class="sxs-lookup"><span data-stu-id="bf9c0-139">Column</span></span></th>
<th><span data-ttu-id="bf9c0-140">Описание</span><span class="sxs-lookup"><span data-stu-id="bf9c0-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf9c0-141">Филетокен</span><span class="sxs-lookup"><span data-stu-id="bf9c0-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-142">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="bf9c0-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf9c0-143">Филетокенчаннелид</span><span class="sxs-lookup"><span data-stu-id="bf9c0-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="bf9c0-144">Внешний ключ с подстановкой в таблице Тблноде. Нодегуид.</span><span class="sxs-lookup"><span data-stu-id="bf9c0-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

