---
title: Таблица User
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: В таблице пользователей представляет собой вспомогательную таблицу. Каждая запись в таблице хранятся сведения о одного пользователя, участвующего в звонков или сеансах с записями в базе данных.
ms.openlocfilehash: b14350d060485a57b4af42cbfe26db729872f6f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="users-table"></a><span data-ttu-id="bd662-104">Таблица User</span><span class="sxs-lookup"><span data-stu-id="bd662-104">Users table</span></span>
 
<span data-ttu-id="bd662-105">В таблице пользователей представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="bd662-105">The Users table is a supporting table.</span></span> <span data-ttu-id="bd662-106">Каждая запись в таблице хранятся сведения о одного пользователя, участвующего в звонков или сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="bd662-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="bd662-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="bd662-107">**Column**</span></span>|<span data-ttu-id="bd662-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="bd662-108">**Data Type**</span></span>|<span data-ttu-id="bd662-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="bd662-109">**Key/Index**</span></span>|<span data-ttu-id="bd662-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="bd662-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd662-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="bd662-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="bd662-112">datetime</span><span class="sxs-lookup"><span data-stu-id="bd662-112">datetime</span></span>  <br/> ||<span data-ttu-id="bd662-113">Метка времени для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="bd662-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="bd662-114">**Идентификатор пользователя**</span><span class="sxs-lookup"><span data-stu-id="bd662-114">**UserId**</span></span> <br/> |<span data-ttu-id="bd662-115">целое</span><span class="sxs-lookup"><span data-stu-id="bd662-115">int</span></span>  <br/> |<span data-ttu-id="bd662-116">Primary</span><span class="sxs-lookup"><span data-stu-id="bd662-116">Primary</span></span>  <br/> |<span data-ttu-id="bd662-117">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="bd662-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="bd662-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="bd662-118">**UserUri**</span></span> <br/> |<span data-ttu-id="bd662-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="bd662-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="bd662-120">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="bd662-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="bd662-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="bd662-121">**TenantId**</span></span> <br/> |<span data-ttu-id="bd662-122">целое</span><span class="sxs-lookup"><span data-stu-id="bd662-122">int</span></span>  <br/> |<span data-ttu-id="bd662-123">Внешний</span><span class="sxs-lookup"><span data-stu-id="bd662-123">Foreign</span></span>  <br/> |<span data-ttu-id="bd662-124">Идентификатор клиента этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="bd662-124">This user's Tenant ID.</span></span> <span data-ttu-id="bd662-125">В [таблице клиентов](tenants.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="bd662-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="bd662-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="bd662-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="bd662-127">целое</span><span class="sxs-lookup"><span data-stu-id="bd662-127">int</span></span>  <br/> |<span data-ttu-id="bd662-128">Внешний</span><span class="sxs-lookup"><span data-stu-id="bd662-128">Foreign</span></span>  <br/> |<span data-ttu-id="bd662-129">Тип URI этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="bd662-129">This user's URI type.</span></span> <span data-ttu-id="bd662-130">В [таблице UriTypes](uritypes.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="bd662-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

