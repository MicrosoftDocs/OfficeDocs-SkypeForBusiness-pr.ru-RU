---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: Тблфилетокен включает временные маркеры для целей обмена файлами.
ms.openlocfilehash: 573c921278521eb5b9ed7cc754dec9fa3471e9f4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814597"
---
# <a name="tblfiletoken"></a><span data-ttu-id="4b1f9-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="4b1f9-103">tblFileToken</span></span>
 
<span data-ttu-id="4b1f9-104">Тблфилетокен включает временные маркеры для целей обмена файлами.</span><span class="sxs-lookup"><span data-stu-id="4b1f9-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="4b1f9-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="4b1f9-105">**Columns**</span></span>

|<span data-ttu-id="4b1f9-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4b1f9-106">**Column**</span></span>|<span data-ttu-id="4b1f9-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="4b1f9-107">**Type**</span></span>|<span data-ttu-id="4b1f9-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4b1f9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4b1f9-109">филетокен</span><span class="sxs-lookup"><span data-stu-id="4b1f9-109">fileToken</span></span>  <br/> |<span data-ttu-id="4b1f9-110">nvarchar (50), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="4b1f9-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="4b1f9-111">Уникальный маркер (GUID).</span><span class="sxs-lookup"><span data-stu-id="4b1f9-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="4b1f9-112">филетокенусерид</span><span class="sxs-lookup"><span data-stu-id="4b1f9-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="4b1f9-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="4b1f9-113">int, not null</span></span>  <br/> |<span data-ttu-id="4b1f9-114">Идентификатор участника, который передает файл.</span><span class="sxs-lookup"><span data-stu-id="4b1f9-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="4b1f9-115">филетокенчаннелид</span><span class="sxs-lookup"><span data-stu-id="4b1f9-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="4b1f9-116">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="4b1f9-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="4b1f9-117">GUID узла комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="4b1f9-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="4b1f9-118">филетокенекспиредате</span><span class="sxs-lookup"><span data-stu-id="4b1f9-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="4b1f9-119">DateTime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="4b1f9-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="4b1f9-120">Время окончания срока действия.</span><span class="sxs-lookup"><span data-stu-id="4b1f9-120">Expiration time.</span></span> <span data-ttu-id="4b1f9-121">(Срок действия токенов истекает через 30 минут, за исключением случаев, когда они закреплены (в этой статье описаны следующие описания).</span><span class="sxs-lookup"><span data-stu-id="4b1f9-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="4b1f9-122">филетокенкомплианцефилеурл</span><span class="sxs-lookup"><span data-stu-id="4b1f9-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="4b1f9-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4b1f9-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4b1f9-124">URL-адрес перенесенного файла (для использования службы соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="4b1f9-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="4b1f9-125">филетокенкомплианцесумбнаилурл</span><span class="sxs-lookup"><span data-stu-id="4b1f9-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="4b1f9-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4b1f9-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4b1f9-127">URL-адрес миниатюры перенесенного файла (для использования службой соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="4b1f9-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="4b1f9-128">филетокенкомплианцетиме</span><span class="sxs-lookup"><span data-stu-id="4b1f9-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="4b1f9-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="4b1f9-129">datetime2</span></span>  <br/> |<span data-ttu-id="4b1f9-130">Метка времени для фактической операции передачи файлов (для использования службой соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="4b1f9-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="4b1f9-131">филетокенкомплианцеисуплоад</span><span class="sxs-lookup"><span data-stu-id="4b1f9-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="4b1f9-132">бит</span><span class="sxs-lookup"><span data-stu-id="4b1f9-132">bit</span></span>  <br/> |<span data-ttu-id="4b1f9-133">Значение true, если отправка; Значение false, если Download (для использования службы соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="4b1f9-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="4b1f9-134">филетокенкомплианцепиннед</span><span class="sxs-lookup"><span data-stu-id="4b1f9-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="4b1f9-135">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="4b1f9-135">bit, not null</span></span>  <br/> |<span data-ttu-id="4b1f9-136">Значение true, если маркер закреплен.</span><span class="sxs-lookup"><span data-stu-id="4b1f9-136">True if token is pinned.</span></span> <span data-ttu-id="4b1f9-137">Она используется для хранения токенов в таблице до тех пор, пока служба соответствия требованиям не сможет получить из нее нужные поля.</span><span class="sxs-lookup"><span data-stu-id="4b1f9-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="4b1f9-138">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="4b1f9-138">**Keys**</span></span>

|<span data-ttu-id="4b1f9-139">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4b1f9-139">**Column**</span></span>|<span data-ttu-id="4b1f9-140">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4b1f9-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4b1f9-141">филетокен</span><span class="sxs-lookup"><span data-stu-id="4b1f9-141">fileToken</span></span>  <br/> |<span data-ttu-id="4b1f9-142">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="4b1f9-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="4b1f9-143">филетокенчаннелид</span><span class="sxs-lookup"><span data-stu-id="4b1f9-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="4b1f9-144">Внешний ключ с подстановкой в таблице Тблноде. Нодегуид.</span><span class="sxs-lookup"><span data-stu-id="4b1f9-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

