---
title: Таблица User
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: Таблица пользователей представляет собой вспомогательную таблицу, в которой хранится список различных пользователей, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет один пользователь.
ms.openlocfilehash: 3261133b8c36fe96fd847c075dce0be2a903c417
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="user-table"></a><span data-ttu-id="2a9b5-104">Таблица User</span><span class="sxs-lookup"><span data-stu-id="2a9b5-104">User table</span></span>
 
<span data-ttu-id="2a9b5-105">Таблица пользователей представляет собой вспомогательную таблицу, в которой хранится список различных пользователей, которые участвовали в сеансах, записанные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="2a9b5-106">Каждая запись в таблице представляет один пользователь.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="2a9b5-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2a9b5-107">**Column**</span></span>|<span data-ttu-id="2a9b5-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="2a9b5-108">**Data Type**</span></span>|<span data-ttu-id="2a9b5-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="2a9b5-109">**Key/Index**</span></span>|<span data-ttu-id="2a9b5-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="2a9b5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a9b5-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="2a9b5-111">**UserKey**</span></span> <br/> |<span data-ttu-id="2a9b5-112">целое</span><span class="sxs-lookup"><span data-stu-id="2a9b5-112">int</span></span>  <br/> |<span data-ttu-id="2a9b5-113">Primary</span><span class="sxs-lookup"><span data-stu-id="2a9b5-113">Primary</span></span>  <br/> |<span data-ttu-id="2a9b5-114">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="2a9b5-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="2a9b5-115">**URI**</span></span> <br/> |<span data-ttu-id="2a9b5-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="2a9b5-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="2a9b5-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="2a9b5-117">Unique</span></span>  <br/> |<span data-ttu-id="2a9b5-118">Строка URI.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="2a9b5-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="2a9b5-119">**URIType**</span></span> <br/> |<span data-ttu-id="2a9b5-120">целое</span><span class="sxs-lookup"><span data-stu-id="2a9b5-120">int</span></span>  <br/> ||<span data-ttu-id="2a9b5-121">1 — Неизвестный тип URI.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="2a9b5-122">2 — URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="2a9b5-123">4 — URI конференции.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="2a9b5-124">8 — URI телефона.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="2a9b5-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="2a9b5-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="2a9b5-126">целое</span><span class="sxs-lookup"><span data-stu-id="2a9b5-126">int</span></span>  <br/> |<span data-ttu-id="2a9b5-127">Внешний</span><span class="sxs-lookup"><span data-stu-id="2a9b5-127">Foreign</span></span>  <br/> |<span data-ttu-id="2a9b5-128">Клиент пользователя, ссылается на таблицу клиентов.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="2a9b5-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="2a9b5-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="2a9b5-130">datetime</span><span class="sxs-lookup"><span data-stu-id="2a9b5-130">datetime</span></span>  <br/> ||<span data-ttu-id="2a9b5-131">Новейшие метка времени, когда пользователь имел аудиовызов плохого качества.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="2a9b5-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="2a9b5-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="2a9b5-133">datetime</span><span class="sxs-lookup"><span data-stu-id="2a9b5-133">datetime</span></span>  <br/> ||<span data-ttu-id="2a9b5-134">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-134">For internal use only.</span></span>  <br/> |
   

