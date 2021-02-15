---
title: Таблица Users
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Таблица Users является вспомогательной. В каждой записи таблицы хранится информация об одном пользователе, вовлеченном в вызовы или сеансы с записями в базе данных.
ms.openlocfilehash: 1905efa9b87b0b94c55e3a72e8be86e9ab191661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831619"
---
# <a name="users-table"></a><span data-ttu-id="d2d71-104">Таблица Users</span><span class="sxs-lookup"><span data-stu-id="d2d71-104">Users table</span></span>
 
<span data-ttu-id="d2d71-105">Таблица Users является вспомогательной.</span><span class="sxs-lookup"><span data-stu-id="d2d71-105">The Users table is a supporting table.</span></span> <span data-ttu-id="d2d71-106">В каждой записи таблицы хранится информация об одном пользователе, вовлеченном в вызовы или сеансы с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d2d71-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="d2d71-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d2d71-107">**Column**</span></span>|<span data-ttu-id="d2d71-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d2d71-108">**Data Type**</span></span>|<span data-ttu-id="d2d71-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="d2d71-109">**Key/Index**</span></span>|<span data-ttu-id="d2d71-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="d2d71-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d2d71-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d2d71-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d2d71-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d2d71-112">datetime</span></span>  <br/> ||<span data-ttu-id="d2d71-113">Отметка времени для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d2d71-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="d2d71-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="d2d71-114">**UserId**</span></span> <br/> |<span data-ttu-id="d2d71-115">int</span><span class="sxs-lookup"><span data-stu-id="d2d71-115">int</span></span>  <br/> |<span data-ttu-id="d2d71-116">Primary</span><span class="sxs-lookup"><span data-stu-id="d2d71-116">Primary</span></span>  <br/> |<span data-ttu-id="d2d71-117">Уникальный номер, идентифицирующий данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="d2d71-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="d2d71-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="d2d71-118">**UserUri**</span></span> <br/> |<span data-ttu-id="d2d71-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d2d71-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="d2d71-120">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="d2d71-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="d2d71-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="d2d71-121">**TenantId**</span></span> <br/> |<span data-ttu-id="d2d71-122">int</span><span class="sxs-lookup"><span data-stu-id="d2d71-122">int</span></span>  <br/> |<span data-ttu-id="d2d71-123">Внешняя</span><span class="sxs-lookup"><span data-stu-id="d2d71-123">Foreign</span></span>  <br/> |<span data-ttu-id="d2d71-124">ИД клиента этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="d2d71-124">This user's Tenant ID.</span></span> <span data-ttu-id="d2d71-125">Дополнительные [сведения см.](tenants.md) в таблице Tenants.</span><span class="sxs-lookup"><span data-stu-id="d2d71-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d2d71-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="d2d71-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="d2d71-127">int</span><span class="sxs-lookup"><span data-stu-id="d2d71-127">int</span></span>  <br/> |<span data-ttu-id="d2d71-128">Внешняя</span><span class="sxs-lookup"><span data-stu-id="d2d71-128">Foreign</span></span>  <br/> |<span data-ttu-id="d2d71-129">Тип URI этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="d2d71-129">This user's URI type.</span></span> <span data-ttu-id="d2d71-130">Дополнительные сведения см. в таблице [UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="d2d71-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

