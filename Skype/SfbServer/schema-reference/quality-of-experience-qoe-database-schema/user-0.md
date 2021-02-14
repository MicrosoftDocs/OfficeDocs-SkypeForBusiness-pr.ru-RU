---
title: Таблица User
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: Таблица User является таблицей поддержки, в которой хранится список разных пользователей, участвовавших в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного пользователя.
ms.openlocfilehash: 5c84f0b947199fa497964cb1689dccc571a98d14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800079"
---
# <a name="user-table"></a><span data-ttu-id="11a34-104">Таблица User</span><span class="sxs-lookup"><span data-stu-id="11a34-104">User table</span></span>
 
<span data-ttu-id="11a34-p102">Таблица User является таблицей поддержки, в которой хранится список разных пользователей, участвовавших в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного пользователя.</span><span class="sxs-lookup"><span data-stu-id="11a34-p102">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="11a34-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="11a34-107">**Column**</span></span>|<span data-ttu-id="11a34-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="11a34-108">**Data Type**</span></span>|<span data-ttu-id="11a34-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="11a34-109">**Key/Index**</span></span>|<span data-ttu-id="11a34-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="11a34-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="11a34-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="11a34-111">**UserKey**</span></span> <br/> |<span data-ttu-id="11a34-112">int</span><span class="sxs-lookup"><span data-stu-id="11a34-112">int</span></span>  <br/> |<span data-ttu-id="11a34-113">Primary</span><span class="sxs-lookup"><span data-stu-id="11a34-113">Primary</span></span>  <br/> |<span data-ttu-id="11a34-114">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="11a34-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="11a34-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="11a34-115">**URI**</span></span> <br/> |<span data-ttu-id="11a34-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="11a34-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="11a34-117">Уникальные</span><span class="sxs-lookup"><span data-stu-id="11a34-117">Unique</span></span>  <br/> |<span data-ttu-id="11a34-118">Строка URI.</span><span class="sxs-lookup"><span data-stu-id="11a34-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="11a34-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="11a34-119">**URIType**</span></span> <br/> |<span data-ttu-id="11a34-120">int</span><span class="sxs-lookup"><span data-stu-id="11a34-120">int</span></span>  <br/> ||<span data-ttu-id="11a34-121">1 — неизвестный тип URI.</span><span class="sxs-lookup"><span data-stu-id="11a34-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="11a34-122">2 — URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="11a34-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="11a34-123">4 — URI конференции.</span><span class="sxs-lookup"><span data-stu-id="11a34-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="11a34-124">8 — URI телефона.</span><span class="sxs-lookup"><span data-stu-id="11a34-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="11a34-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="11a34-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="11a34-126">int</span><span class="sxs-lookup"><span data-stu-id="11a34-126">int</span></span>  <br/> |<span data-ttu-id="11a34-127">Внешняя</span><span class="sxs-lookup"><span data-stu-id="11a34-127">Foreign</span></span>  <br/> |<span data-ttu-id="11a34-128">Клиент пользователя, ссылается на таблицу клиентов.</span><span class="sxs-lookup"><span data-stu-id="11a34-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="11a34-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="11a34-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="11a34-130">datetime</span><span class="sxs-lookup"><span data-stu-id="11a34-130">datetime</span></span>  <br/> ||<span data-ttu-id="11a34-131">Последняя метка времени, когда пользователь имел аудиовызов плохого качества.</span><span class="sxs-lookup"><span data-stu-id="11a34-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="11a34-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="11a34-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="11a34-133">datetime</span><span class="sxs-lookup"><span data-stu-id="11a34-133">datetime</span></span>  <br/> ||<span data-ttu-id="11a34-134">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="11a34-134">For internal use only.</span></span>  <br/> |
   

