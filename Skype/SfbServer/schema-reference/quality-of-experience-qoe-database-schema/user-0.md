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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212083"
---
# <a name="user-table"></a><span data-ttu-id="d231d-104">Таблица User</span><span class="sxs-lookup"><span data-stu-id="d231d-104">User table</span></span>
 
<span data-ttu-id="d231d-105">Таблица пользователей представляет собой вспомогательную таблицу, в которой хранится список различных пользователей, которые участвовали в сеансах, записанные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d231d-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="d231d-106">Каждая запись в таблице представляет один пользователь.</span><span class="sxs-lookup"><span data-stu-id="d231d-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="d231d-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d231d-107">**Column**</span></span>|<span data-ttu-id="d231d-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d231d-108">**Data Type**</span></span>|<span data-ttu-id="d231d-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="d231d-109">**Key/Index**</span></span>|<span data-ttu-id="d231d-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="d231d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d231d-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="d231d-111">**UserKey**</span></span> <br/> |<span data-ttu-id="d231d-112">целое</span><span class="sxs-lookup"><span data-stu-id="d231d-112">int</span></span>  <br/> |<span data-ttu-id="d231d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d231d-113">Primary</span></span>  <br/> |<span data-ttu-id="d231d-114">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="d231d-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="d231d-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="d231d-115">**URI**</span></span> <br/> |<span data-ttu-id="d231d-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d231d-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d231d-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="d231d-117">Unique</span></span>  <br/> |<span data-ttu-id="d231d-118">Строка URI.</span><span class="sxs-lookup"><span data-stu-id="d231d-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="d231d-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="d231d-119">**URIType**</span></span> <br/> |<span data-ttu-id="d231d-120">целое</span><span class="sxs-lookup"><span data-stu-id="d231d-120">int</span></span>  <br/> ||<span data-ttu-id="d231d-121">1 — Неизвестный тип URI.</span><span class="sxs-lookup"><span data-stu-id="d231d-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="d231d-122">2 — URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="d231d-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="d231d-123">4 — URI конференции.</span><span class="sxs-lookup"><span data-stu-id="d231d-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="d231d-124">8 — URI телефона.</span><span class="sxs-lookup"><span data-stu-id="d231d-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="d231d-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="d231d-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="d231d-126">целое</span><span class="sxs-lookup"><span data-stu-id="d231d-126">int</span></span>  <br/> |<span data-ttu-id="d231d-127">Внешний</span><span class="sxs-lookup"><span data-stu-id="d231d-127">Foreign</span></span>  <br/> |<span data-ttu-id="d231d-128">Клиент пользователя, ссылается на таблицу клиентов.</span><span class="sxs-lookup"><span data-stu-id="d231d-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="d231d-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="d231d-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="d231d-130">datetime</span><span class="sxs-lookup"><span data-stu-id="d231d-130">datetime</span></span>  <br/> ||<span data-ttu-id="d231d-131">Новейшие метка времени, когда пользователь имел аудиовызов плохого качества.</span><span class="sxs-lookup"><span data-stu-id="d231d-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="d231d-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d231d-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d231d-133">datetime</span><span class="sxs-lookup"><span data-stu-id="d231d-133">datetime</span></span>  <br/> ||<span data-ttu-id="d231d-134">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d231d-134">For internal use only.</span></span>  <br/> |
   

