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
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: Таблица user — это вспомогательная таблица, в которой хранится список различных пользователей, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного пользователя.
ms.openlocfilehash: a9f72793d3b287406b1b3b7e1ad360e7f5abc598
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294616"
---
# <a name="user-table"></a><span data-ttu-id="51e5a-104">Таблица User</span><span class="sxs-lookup"><span data-stu-id="51e5a-104">User table</span></span>
 
<span data-ttu-id="51e5a-105">Таблица user — это вспомогательная таблица, в которой хранится список различных пользователей, которые участвовали в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="51e5a-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="51e5a-106">Каждая запись в таблице представляет одного пользователя.</span><span class="sxs-lookup"><span data-stu-id="51e5a-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="51e5a-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="51e5a-107">**Column**</span></span>|<span data-ttu-id="51e5a-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="51e5a-108">**Data Type**</span></span>|<span data-ttu-id="51e5a-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="51e5a-109">**Key/Index**</span></span>|<span data-ttu-id="51e5a-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="51e5a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="51e5a-111">**Усеркэй**</span><span class="sxs-lookup"><span data-stu-id="51e5a-111">**UserKey**</span></span> <br/> |<span data-ttu-id="51e5a-112">целое</span><span class="sxs-lookup"><span data-stu-id="51e5a-112">int</span></span>  <br/> |<span data-ttu-id="51e5a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="51e5a-113">Primary</span></span>  <br/> |<span data-ttu-id="51e5a-114">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="51e5a-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="51e5a-115">**КОД**</span><span class="sxs-lookup"><span data-stu-id="51e5a-115">**URI**</span></span> <br/> |<span data-ttu-id="51e5a-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="51e5a-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="51e5a-117">Повторя</span><span class="sxs-lookup"><span data-stu-id="51e5a-117">Unique</span></span>  <br/> |<span data-ttu-id="51e5a-118">Строка URI.</span><span class="sxs-lookup"><span data-stu-id="51e5a-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="51e5a-119">**Уритипе**</span><span class="sxs-lookup"><span data-stu-id="51e5a-119">**URIType**</span></span> <br/> |<span data-ttu-id="51e5a-120">целое</span><span class="sxs-lookup"><span data-stu-id="51e5a-120">int</span></span>  <br/> ||<span data-ttu-id="51e5a-121">1 — неизвестный тип URI.</span><span class="sxs-lookup"><span data-stu-id="51e5a-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="51e5a-122">2 — это универсальный код ресурса пользователя.</span><span class="sxs-lookup"><span data-stu-id="51e5a-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="51e5a-123">4 — универсальный код ресурса Конференции.</span><span class="sxs-lookup"><span data-stu-id="51e5a-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="51e5a-124">8 — это универсальный код ресурса (URI) телефона.</span><span class="sxs-lookup"><span data-stu-id="51e5a-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="51e5a-125">**Тенанткэй**</span><span class="sxs-lookup"><span data-stu-id="51e5a-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="51e5a-126">целое</span><span class="sxs-lookup"><span data-stu-id="51e5a-126">int</span></span>  <br/> |<span data-ttu-id="51e5a-127">Другом</span><span class="sxs-lookup"><span data-stu-id="51e5a-127">Foreign</span></span>  <br/> |<span data-ttu-id="51e5a-128">Клиент для пользователя, на который ссылается таблица "клиент".</span><span class="sxs-lookup"><span data-stu-id="51e5a-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="51e5a-129">**Ластпуркаллтиме**</span><span class="sxs-lookup"><span data-stu-id="51e5a-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="51e5a-130">datetime</span><span class="sxs-lookup"><span data-stu-id="51e5a-130">datetime</span></span>  <br/> ||<span data-ttu-id="51e5a-131">Самая поздняя метка времени, когда пользователь приходил к вызову неудовлетворительного звука.</span><span class="sxs-lookup"><span data-stu-id="51e5a-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="51e5a-132">**Некступдатетс**</span><span class="sxs-lookup"><span data-stu-id="51e5a-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="51e5a-133">datetime</span><span class="sxs-lookup"><span data-stu-id="51e5a-133">datetime</span></span>  <br/> ||<span data-ttu-id="51e5a-134">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="51e5a-134">For internal use only.</span></span>  <br/> |
   

