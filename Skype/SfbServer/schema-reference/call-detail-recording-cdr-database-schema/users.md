---
title: Таблица User
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: В таблице пользователей представляет собой вспомогательную таблицу. Каждая запись в таблице хранятся сведения о одного пользователя, участвующего в звонков или сеансах с записями в базе данных.
ms.openlocfilehash: fbe3ff7d2570f78cdf3b3418629fb9fd6209d944
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929989"
---
# <a name="users-table"></a><span data-ttu-id="ba55d-104">Таблица User</span><span class="sxs-lookup"><span data-stu-id="ba55d-104">Users table</span></span>
 
<span data-ttu-id="ba55d-105">В таблице пользователей представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="ba55d-105">The Users table is a supporting table.</span></span> <span data-ttu-id="ba55d-106">Каждая запись в таблице хранятся сведения о одного пользователя, участвующего в звонков или сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ba55d-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="ba55d-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ba55d-107">**Column**</span></span>|<span data-ttu-id="ba55d-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ba55d-108">**Data Type**</span></span>|<span data-ttu-id="ba55d-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="ba55d-109">**Key/Index**</span></span>|<span data-ttu-id="ba55d-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="ba55d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ba55d-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="ba55d-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="ba55d-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ba55d-112">datetime</span></span>  <br/> ||<span data-ttu-id="ba55d-113">Метка времени для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="ba55d-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="ba55d-114">**Идентификатор пользователя**</span><span class="sxs-lookup"><span data-stu-id="ba55d-114">**UserId**</span></span> <br/> |<span data-ttu-id="ba55d-115">целое</span><span class="sxs-lookup"><span data-stu-id="ba55d-115">int</span></span>  <br/> |<span data-ttu-id="ba55d-116">Primary</span><span class="sxs-lookup"><span data-stu-id="ba55d-116">Primary</span></span>  <br/> |<span data-ttu-id="ba55d-117">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba55d-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="ba55d-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="ba55d-118">**UserUri**</span></span> <br/> |<span data-ttu-id="ba55d-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="ba55d-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="ba55d-120">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba55d-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="ba55d-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="ba55d-121">**TenantId**</span></span> <br/> |<span data-ttu-id="ba55d-122">целое</span><span class="sxs-lookup"><span data-stu-id="ba55d-122">int</span></span>  <br/> |<span data-ttu-id="ba55d-123">Внешний</span><span class="sxs-lookup"><span data-stu-id="ba55d-123">Foreign</span></span>  <br/> |<span data-ttu-id="ba55d-124">Идентификатор клиента этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba55d-124">This user's Tenant ID.</span></span> <span data-ttu-id="ba55d-125">В [таблице клиентов](tenants.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="ba55d-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ba55d-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="ba55d-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="ba55d-127">целое</span><span class="sxs-lookup"><span data-stu-id="ba55d-127">int</span></span>  <br/> |<span data-ttu-id="ba55d-128">Внешний</span><span class="sxs-lookup"><span data-stu-id="ba55d-128">Foreign</span></span>  <br/> |<span data-ttu-id="ba55d-129">Тип URI этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba55d-129">This user's URI type.</span></span> <span data-ttu-id="ba55d-130">В [таблице UriTypes](uritypes.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="ba55d-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

