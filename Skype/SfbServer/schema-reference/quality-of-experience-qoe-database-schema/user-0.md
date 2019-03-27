---
title: Таблица User
ms.reviewer: ''
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
ms.openlocfilehash: fcdc8682b86432613af79d5e4d2abbdb248fef0f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881676"
---
# <a name="user-table"></a><span data-ttu-id="72210-104">Таблица User</span><span class="sxs-lookup"><span data-stu-id="72210-104">User table</span></span>
 
<span data-ttu-id="72210-105">Таблица пользователей представляет собой вспомогательную таблицу, в которой хранится список различных пользователей, которые участвовали в сеансах, записанные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="72210-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="72210-106">Каждая запись в таблице представляет один пользователь.</span><span class="sxs-lookup"><span data-stu-id="72210-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="72210-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="72210-107">**Column**</span></span>|<span data-ttu-id="72210-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="72210-108">**Data Type**</span></span>|<span data-ttu-id="72210-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="72210-109">**Key/Index**</span></span>|<span data-ttu-id="72210-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="72210-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="72210-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="72210-111">**UserKey**</span></span> <br/> |<span data-ttu-id="72210-112">целое</span><span class="sxs-lookup"><span data-stu-id="72210-112">int</span></span>  <br/> |<span data-ttu-id="72210-113">Primary</span><span class="sxs-lookup"><span data-stu-id="72210-113">Primary</span></span>  <br/> |<span data-ttu-id="72210-114">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="72210-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="72210-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="72210-115">**URI**</span></span> <br/> |<span data-ttu-id="72210-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="72210-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="72210-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="72210-117">Unique</span></span>  <br/> |<span data-ttu-id="72210-118">Строка URI.</span><span class="sxs-lookup"><span data-stu-id="72210-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="72210-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="72210-119">**URIType**</span></span> <br/> |<span data-ttu-id="72210-120">целое</span><span class="sxs-lookup"><span data-stu-id="72210-120">int</span></span>  <br/> ||<span data-ttu-id="72210-121">1 — Неизвестный тип URI.</span><span class="sxs-lookup"><span data-stu-id="72210-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="72210-122">2 — URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="72210-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="72210-123">4 — URI конференции.</span><span class="sxs-lookup"><span data-stu-id="72210-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="72210-124">8 — URI телефона.</span><span class="sxs-lookup"><span data-stu-id="72210-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="72210-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="72210-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="72210-126">целое</span><span class="sxs-lookup"><span data-stu-id="72210-126">int</span></span>  <br/> |<span data-ttu-id="72210-127">Внешний</span><span class="sxs-lookup"><span data-stu-id="72210-127">Foreign</span></span>  <br/> |<span data-ttu-id="72210-128">Клиент пользователя, ссылается на таблицу клиентов.</span><span class="sxs-lookup"><span data-stu-id="72210-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="72210-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="72210-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="72210-130">datetime</span><span class="sxs-lookup"><span data-stu-id="72210-130">datetime</span></span>  <br/> ||<span data-ttu-id="72210-131">Новейшие метка времени, когда пользователь имел аудиовызов плохого качества.</span><span class="sxs-lookup"><span data-stu-id="72210-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="72210-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="72210-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="72210-133">datetime</span><span class="sxs-lookup"><span data-stu-id="72210-133">datetime</span></span>  <br/> ||<span data-ttu-id="72210-134">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="72210-134">For internal use only.</span></span>  <br/> |
   

