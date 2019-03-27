---
title: Таблица User
ms.reviewer: ''
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
ms.openlocfilehash: 3929ba33737c107ee60ec1e31beebb1addbb2e3f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885563"
---
# <a name="users-table"></a><span data-ttu-id="8ac82-104">Таблица User</span><span class="sxs-lookup"><span data-stu-id="8ac82-104">Users table</span></span>
 
<span data-ttu-id="8ac82-105">В таблице пользователей представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="8ac82-105">The Users table is a supporting table.</span></span> <span data-ttu-id="8ac82-106">Каждая запись в таблице хранятся сведения о одного пользователя, участвующего в звонков или сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="8ac82-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="8ac82-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8ac82-107">**Column**</span></span>|<span data-ttu-id="8ac82-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8ac82-108">**Data Type**</span></span>|<span data-ttu-id="8ac82-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="8ac82-109">**Key/Index**</span></span>|<span data-ttu-id="8ac82-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="8ac82-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8ac82-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="8ac82-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="8ac82-112">datetime</span><span class="sxs-lookup"><span data-stu-id="8ac82-112">datetime</span></span>  <br/> ||<span data-ttu-id="8ac82-113">Метка времени для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="8ac82-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="8ac82-114">**Идентификатор пользователя**</span><span class="sxs-lookup"><span data-stu-id="8ac82-114">**UserId**</span></span> <br/> |<span data-ttu-id="8ac82-115">целое</span><span class="sxs-lookup"><span data-stu-id="8ac82-115">int</span></span>  <br/> |<span data-ttu-id="8ac82-116">Primary</span><span class="sxs-lookup"><span data-stu-id="8ac82-116">Primary</span></span>  <br/> |<span data-ttu-id="8ac82-117">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="8ac82-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="8ac82-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="8ac82-118">**UserUri**</span></span> <br/> |<span data-ttu-id="8ac82-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="8ac82-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="8ac82-120">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="8ac82-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="8ac82-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="8ac82-121">**TenantId**</span></span> <br/> |<span data-ttu-id="8ac82-122">целое</span><span class="sxs-lookup"><span data-stu-id="8ac82-122">int</span></span>  <br/> |<span data-ttu-id="8ac82-123">Внешний</span><span class="sxs-lookup"><span data-stu-id="8ac82-123">Foreign</span></span>  <br/> |<span data-ttu-id="8ac82-124">Идентификатор клиента этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="8ac82-124">This user's Tenant ID.</span></span> <span data-ttu-id="8ac82-125">В [таблице клиентов](tenants.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="8ac82-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="8ac82-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="8ac82-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="8ac82-127">целое</span><span class="sxs-lookup"><span data-stu-id="8ac82-127">int</span></span>  <br/> |<span data-ttu-id="8ac82-128">Внешний</span><span class="sxs-lookup"><span data-stu-id="8ac82-128">Foreign</span></span>  <br/> |<span data-ttu-id="8ac82-129">Тип URI этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="8ac82-129">This user's URI type.</span></span> <span data-ttu-id="8ac82-130">В [таблице UriTypes](uritypes.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="8ac82-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

