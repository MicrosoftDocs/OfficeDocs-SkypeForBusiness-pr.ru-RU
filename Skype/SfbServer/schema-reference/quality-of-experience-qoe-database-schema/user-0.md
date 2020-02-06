---
title: Таблица User
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: Таблица user — это вспомогательная таблица, в которой хранится список различных пользователей, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного пользователя.
ms.openlocfilehash: fcb6c4d45f1392c31ba87637d6e3a1a697f7be9e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805097"
---
# <a name="user-table"></a><span data-ttu-id="ee811-104">Таблица User</span><span class="sxs-lookup"><span data-stu-id="ee811-104">User table</span></span>
 
<span data-ttu-id="ee811-105">Таблица user — это вспомогательная таблица, в которой хранится список различных пользователей, которые участвовали в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ee811-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ee811-106">Каждая запись в таблице представляет одного пользователя.</span><span class="sxs-lookup"><span data-stu-id="ee811-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="ee811-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ee811-107">**Column**</span></span>|<span data-ttu-id="ee811-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee811-108">**Data Type**</span></span>|<span data-ttu-id="ee811-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="ee811-109">**Key/Index**</span></span>|<span data-ttu-id="ee811-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="ee811-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ee811-111">**усеркэй**</span><span class="sxs-lookup"><span data-stu-id="ee811-111">**UserKey**</span></span> <br/> |<span data-ttu-id="ee811-112">целое</span><span class="sxs-lookup"><span data-stu-id="ee811-112">int</span></span>  <br/> |<span data-ttu-id="ee811-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ee811-113">Primary</span></span>  <br/> |<span data-ttu-id="ee811-114">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="ee811-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="ee811-115">**КОД**</span><span class="sxs-lookup"><span data-stu-id="ee811-115">**URI**</span></span> <br/> |<span data-ttu-id="ee811-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ee811-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ee811-117">Повторя</span><span class="sxs-lookup"><span data-stu-id="ee811-117">Unique</span></span>  <br/> |<span data-ttu-id="ee811-118">Строка URI.</span><span class="sxs-lookup"><span data-stu-id="ee811-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="ee811-119">**уритипе**</span><span class="sxs-lookup"><span data-stu-id="ee811-119">**URIType**</span></span> <br/> |<span data-ttu-id="ee811-120">целое</span><span class="sxs-lookup"><span data-stu-id="ee811-120">int</span></span>  <br/> ||<span data-ttu-id="ee811-121">1 — неизвестный тип URI.</span><span class="sxs-lookup"><span data-stu-id="ee811-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="ee811-122">2 — это универсальный код ресурса пользователя.</span><span class="sxs-lookup"><span data-stu-id="ee811-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="ee811-123">4 — универсальный код ресурса Конференции.</span><span class="sxs-lookup"><span data-stu-id="ee811-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="ee811-124">8 — это универсальный код ресурса (URI) телефона.</span><span class="sxs-lookup"><span data-stu-id="ee811-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="ee811-125">**тенанткэй**</span><span class="sxs-lookup"><span data-stu-id="ee811-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="ee811-126">целое</span><span class="sxs-lookup"><span data-stu-id="ee811-126">int</span></span>  <br/> |<span data-ttu-id="ee811-127">Другом</span><span class="sxs-lookup"><span data-stu-id="ee811-127">Foreign</span></span>  <br/> |<span data-ttu-id="ee811-128">Клиент для пользователя, на который ссылается таблица "клиент".</span><span class="sxs-lookup"><span data-stu-id="ee811-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="ee811-129">**ластпуркаллтиме**</span><span class="sxs-lookup"><span data-stu-id="ee811-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="ee811-130">datetime</span><span class="sxs-lookup"><span data-stu-id="ee811-130">datetime</span></span>  <br/> ||<span data-ttu-id="ee811-131">Самая поздняя метка времени, когда пользователь приходил к вызову неудовлетворительного звука.</span><span class="sxs-lookup"><span data-stu-id="ee811-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="ee811-132">**некступдатетс**</span><span class="sxs-lookup"><span data-stu-id="ee811-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="ee811-133">datetime</span><span class="sxs-lookup"><span data-stu-id="ee811-133">datetime</span></span>  <br/> ||<span data-ttu-id="ee811-134">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="ee811-134">For internal use only.</span></span>  <br/> |
   

