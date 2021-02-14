---
title: tblFileToken
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: Таблица tblFileToken содержит временные маркеры для передачи файлов.
ms.openlocfilehash: 75d3d4df3affe3d12f94499efdb4337ade11af27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816019"
---
# <a name="tblfiletoken"></a><span data-ttu-id="89034-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="89034-103">tblFileToken</span></span>
 
<span data-ttu-id="89034-104">Таблица tblFileToken содержит временные маркеры для передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="89034-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="89034-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="89034-105">**Columns**</span></span>

|<span data-ttu-id="89034-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="89034-106">**Column**</span></span>|<span data-ttu-id="89034-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="89034-107">**Type**</span></span>|<span data-ttu-id="89034-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="89034-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="89034-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="89034-109">fileToken</span></span>  <br/> |<span data-ttu-id="89034-110">nvarchar (50), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="89034-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="89034-111">Уникальный маркер (GUID).</span><span class="sxs-lookup"><span data-stu-id="89034-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="89034-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="89034-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="89034-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="89034-113">int, not null</span></span>  <br/> |<span data-ttu-id="89034-114">Идентификатор субъекта, который передает файл.</span><span class="sxs-lookup"><span data-stu-id="89034-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="89034-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="89034-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="89034-116">GUID, не NULL</span><span class="sxs-lookup"><span data-stu-id="89034-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="89034-117">GUID узла комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="89034-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="89034-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="89034-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="89034-119">datetime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="89034-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="89034-p101">Срок действия. (Срок действия маркеров истекает через 30 минут, если они не были закреплены; см. описания в этом столбце.)</span><span class="sxs-lookup"><span data-stu-id="89034-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="89034-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="89034-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="89034-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="89034-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="89034-124">URL-адрес переданного файла (для использования службой соответствия).</span><span class="sxs-lookup"><span data-stu-id="89034-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="89034-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="89034-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="89034-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="89034-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="89034-127">URL-адрес эскиза переданного файла (для использования службой соответствия).</span><span class="sxs-lookup"><span data-stu-id="89034-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="89034-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="89034-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="89034-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="89034-129">datetime2</span></span>  <br/> |<span data-ttu-id="89034-130">Метка времени для фактической операции передачи файла (для использования службой соответствия).</span><span class="sxs-lookup"><span data-stu-id="89034-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="89034-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="89034-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="89034-132">bit</span><span class="sxs-lookup"><span data-stu-id="89034-132">bit</span></span>  <br/> |<span data-ttu-id="89034-133">True при отправке; False при загрузке (для использования службой соответствия).</span><span class="sxs-lookup"><span data-stu-id="89034-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="89034-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="89034-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="89034-135">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="89034-135">bit, not null</span></span>  <br/> |<span data-ttu-id="89034-136">True, если маркер закреплен.</span><span class="sxs-lookup"><span data-stu-id="89034-136">True if token is pinned.</span></span> <span data-ttu-id="89034-137">Он используется для с сохранением маркера в таблице до тех пор, пока служба соответствия не будет иметь возможность получить соответствующие поля из нее.</span><span class="sxs-lookup"><span data-stu-id="89034-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="89034-138">**Keys**</span><span class="sxs-lookup"><span data-stu-id="89034-138">**Keys**</span></span>

|<span data-ttu-id="89034-139">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="89034-139">**Column**</span></span>|<span data-ttu-id="89034-140">**Описание**</span><span class="sxs-lookup"><span data-stu-id="89034-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89034-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="89034-141">fileToken</span></span>  <br/> |<span data-ttu-id="89034-142">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="89034-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="89034-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="89034-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="89034-144">Внешний ключ для поиска в таблице tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="89034-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

