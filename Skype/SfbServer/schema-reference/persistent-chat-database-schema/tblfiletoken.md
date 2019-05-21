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
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: Тблфилетокен включает временные маркеры для целей обмена файлами.
ms.openlocfilehash: 108c9738657354881324ec720f50a51605530922
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295407"
---
# <a name="tblfiletoken"></a><span data-ttu-id="dbaa5-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="dbaa5-103">tblFileToken</span></span>
 
<span data-ttu-id="dbaa5-104">Тблфилетокен включает временные маркеры для целей обмена файлами.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="dbaa5-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="dbaa5-105">**Columns**</span></span>

|<span data-ttu-id="dbaa5-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="dbaa5-106">**Column**</span></span>|<span data-ttu-id="dbaa5-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="dbaa5-107">**Type**</span></span>|<span data-ttu-id="dbaa5-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="dbaa5-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dbaa5-109">Филетокен</span><span class="sxs-lookup"><span data-stu-id="dbaa5-109">fileToken</span></span>  <br/> |<span data-ttu-id="dbaa5-110">nvarchar (50), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="dbaa5-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="dbaa5-111">Уникальный маркер (GUID).</span><span class="sxs-lookup"><span data-stu-id="dbaa5-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="dbaa5-112">Филетокенусерид</span><span class="sxs-lookup"><span data-stu-id="dbaa5-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="dbaa5-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="dbaa5-113">int, not null</span></span>  <br/> |<span data-ttu-id="dbaa5-114">Идентификатор участника, который передает файл.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="dbaa5-115">Филетокенчаннелид</span><span class="sxs-lookup"><span data-stu-id="dbaa5-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="dbaa5-116">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="dbaa5-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="dbaa5-117">GUID узла комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="dbaa5-118">Филетокенекспиредате</span><span class="sxs-lookup"><span data-stu-id="dbaa5-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="dbaa5-119">DateTime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="dbaa5-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="dbaa5-120">Время окончания срока действия.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-120">Expiration time.</span></span> <span data-ttu-id="dbaa5-121">(Срок действия токенов истекает через 30 минут, за исключением случаев, когда они закреплены (в этой статье описаны следующие описания).</span><span class="sxs-lookup"><span data-stu-id="dbaa5-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="dbaa5-122">Филетокенкомплианцефилеурл</span><span class="sxs-lookup"><span data-stu-id="dbaa5-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="dbaa5-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dbaa5-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="dbaa5-124">URL-адрес перенесенного файла (для использования службы соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="dbaa5-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="dbaa5-125">Филетокенкомплианцесумбнаилурл</span><span class="sxs-lookup"><span data-stu-id="dbaa5-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="dbaa5-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dbaa5-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="dbaa5-127">URL-адрес миниатюры перенесенного файла (для использования службой соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="dbaa5-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="dbaa5-128">Филетокенкомплианцетиме</span><span class="sxs-lookup"><span data-stu-id="dbaa5-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="dbaa5-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="dbaa5-129">datetime2</span></span>  <br/> |<span data-ttu-id="dbaa5-130">Метка времени для фактической операции передачи файлов (для использования службой соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="dbaa5-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="dbaa5-131">Филетокенкомплианцеисуплоад</span><span class="sxs-lookup"><span data-stu-id="dbaa5-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="dbaa5-132">бит</span><span class="sxs-lookup"><span data-stu-id="dbaa5-132">bit</span></span>  <br/> |<span data-ttu-id="dbaa5-133">Значение true, если отправка; Значение false, если Download (для использования службы соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="dbaa5-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="dbaa5-134">Филетокенкомплианцепиннед</span><span class="sxs-lookup"><span data-stu-id="dbaa5-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="dbaa5-135">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="dbaa5-135">bit, not null</span></span>  <br/> |<span data-ttu-id="dbaa5-136">Значение true, если маркер закреплен.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-136">True if token is pinned.</span></span> <span data-ttu-id="dbaa5-137">Она используется для хранения токенов в таблице до тех пор, пока служба соответствия требованиям не сможет получить из нее нужные поля.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="dbaa5-138">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="dbaa5-138">**Keys**</span></span>

|<span data-ttu-id="dbaa5-139">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="dbaa5-139">**Column**</span></span>|<span data-ttu-id="dbaa5-140">**Описание**</span><span class="sxs-lookup"><span data-stu-id="dbaa5-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dbaa5-141">Филетокен</span><span class="sxs-lookup"><span data-stu-id="dbaa5-141">fileToken</span></span>  <br/> |<span data-ttu-id="dbaa5-142">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="dbaa5-143">Филетокенчаннелид</span><span class="sxs-lookup"><span data-stu-id="dbaa5-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="dbaa5-144">Внешний ключ с подстановкой в таблице Тблноде. Нодегуид.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

