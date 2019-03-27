---
title: tblFileToken
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: Таблица tblFileToken содержит временные маркеры для передачи файлов.
ms.openlocfilehash: 46553a4b8752e2a95691dc2042a2632845166fc7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881300"
---
# <a name="tblfiletoken"></a><span data-ttu-id="2a836-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="2a836-103">tblFileToken</span></span>
 
<span data-ttu-id="2a836-104">Таблица tblFileToken содержит временные маркеры для передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="2a836-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="2a836-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="2a836-105">**Columns**</span></span>

|<span data-ttu-id="2a836-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2a836-106">**Column**</span></span>|<span data-ttu-id="2a836-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="2a836-107">**Type**</span></span>|<span data-ttu-id="2a836-108">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="2a836-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2a836-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="2a836-109">fileToken</span></span>  <br/> |<span data-ttu-id="2a836-110">nvarchar (50), отлично от null</span><span class="sxs-lookup"><span data-stu-id="2a836-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="2a836-111">Уникальный маркер (GUID).</span><span class="sxs-lookup"><span data-stu-id="2a836-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="2a836-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="2a836-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="2a836-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="2a836-113">int, not null</span></span>  <br/> |<span data-ttu-id="2a836-114">Идентификатор субъекта, который передает файл.</span><span class="sxs-lookup"><span data-stu-id="2a836-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="2a836-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="2a836-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="2a836-116">Идентификатор GUID, не может быть null</span><span class="sxs-lookup"><span data-stu-id="2a836-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="2a836-117">GUID узла комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="2a836-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="2a836-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="2a836-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="2a836-119">DateTime, не может быть null</span><span class="sxs-lookup"><span data-stu-id="2a836-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="2a836-120">Время истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="2a836-120">Expiration time.</span></span> <span data-ttu-id="2a836-121">(Маркеры срок действия которых истекает через 30 минут, пока не прикрепленных (см. следующие описания в этой статье).</span><span class="sxs-lookup"><span data-stu-id="2a836-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="2a836-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="2a836-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="2a836-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2a836-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="2a836-124">URL-адрес переданного файла (для использования службой соответствия).</span><span class="sxs-lookup"><span data-stu-id="2a836-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="2a836-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="2a836-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="2a836-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2a836-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="2a836-127">URL-адрес эскиза переданного файла (для использования службой соответствия).</span><span class="sxs-lookup"><span data-stu-id="2a836-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="2a836-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="2a836-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="2a836-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="2a836-129">datetime2</span></span>  <br/> |<span data-ttu-id="2a836-130">Метка времени для операции переноса исходный файл (для использования службой соответствия).</span><span class="sxs-lookup"><span data-stu-id="2a836-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="2a836-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="2a836-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="2a836-132">бит</span><span class="sxs-lookup"><span data-stu-id="2a836-132">bit</span></span>  <br/> |<span data-ttu-id="2a836-133">Значение true, если отправка; False при загрузке (для использования службой соответствия).</span><span class="sxs-lookup"><span data-stu-id="2a836-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="2a836-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="2a836-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="2a836-135">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="2a836-135">bit, not null</span></span>  <br/> |<span data-ttu-id="2a836-136">Значение true, если прикрепленных маркер.</span><span class="sxs-lookup"><span data-stu-id="2a836-136">True if token is pinned.</span></span> <span data-ttu-id="2a836-137">Он используется для хранения маркера в таблице, пока служба соответствия имеет возможность получать соответствующие поля из нее.</span><span class="sxs-lookup"><span data-stu-id="2a836-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="2a836-138">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="2a836-138">**Keys**</span></span>

|<span data-ttu-id="2a836-139">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2a836-139">**Column**</span></span>|<span data-ttu-id="2a836-140">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="2a836-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a836-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="2a836-141">fileToken</span></span>  <br/> |<span data-ttu-id="2a836-142">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="2a836-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="2a836-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="2a836-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="2a836-144">Внешний ключ с подстановкой в таблице tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="2a836-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

