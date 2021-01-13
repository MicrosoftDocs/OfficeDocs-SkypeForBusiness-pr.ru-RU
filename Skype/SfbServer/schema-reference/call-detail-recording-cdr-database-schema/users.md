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
# <a name="users-table"></a><span data-ttu-id="7ab92-104">Таблица Users</span><span class="sxs-lookup"><span data-stu-id="7ab92-104">Users table</span></span>
 
<span data-ttu-id="7ab92-105">Таблица Users является вспомогательной.</span><span class="sxs-lookup"><span data-stu-id="7ab92-105">The Users table is a supporting table.</span></span> <span data-ttu-id="7ab92-106">В каждой записи таблицы хранится информация об одном пользователе, вовлеченном в вызовы или сеансы с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="7ab92-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="7ab92-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7ab92-107">**Column**</span></span>|<span data-ttu-id="7ab92-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="7ab92-108">**Data Type**</span></span>|<span data-ttu-id="7ab92-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="7ab92-109">**Key/Index**</span></span>|<span data-ttu-id="7ab92-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="7ab92-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7ab92-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="7ab92-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="7ab92-112">datetime</span><span class="sxs-lookup"><span data-stu-id="7ab92-112">datetime</span></span>  <br/> ||<span data-ttu-id="7ab92-113">Отметка времени для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="7ab92-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="7ab92-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="7ab92-114">**UserId**</span></span> <br/> |<span data-ttu-id="7ab92-115">int</span><span class="sxs-lookup"><span data-stu-id="7ab92-115">int</span></span>  <br/> |<span data-ttu-id="7ab92-116">Primary</span><span class="sxs-lookup"><span data-stu-id="7ab92-116">Primary</span></span>  <br/> |<span data-ttu-id="7ab92-117">Уникальный номер, идентифицирующий данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="7ab92-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="7ab92-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="7ab92-118">**UserUri**</span></span> <br/> |<span data-ttu-id="7ab92-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="7ab92-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="7ab92-120">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="7ab92-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="7ab92-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="7ab92-121">**TenantId**</span></span> <br/> |<span data-ttu-id="7ab92-122">int</span><span class="sxs-lookup"><span data-stu-id="7ab92-122">int</span></span>  <br/> |<span data-ttu-id="7ab92-123">Внешняя</span><span class="sxs-lookup"><span data-stu-id="7ab92-123">Foreign</span></span>  <br/> |<span data-ttu-id="7ab92-124">ИД клиента этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="7ab92-124">This user's Tenant ID.</span></span> <span data-ttu-id="7ab92-125">Дополнительные [сведения см. в](tenants.md) таблице Tenants.</span><span class="sxs-lookup"><span data-stu-id="7ab92-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="7ab92-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="7ab92-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="7ab92-127">int</span><span class="sxs-lookup"><span data-stu-id="7ab92-127">int</span></span>  <br/> |<span data-ttu-id="7ab92-128">Внешняя</span><span class="sxs-lookup"><span data-stu-id="7ab92-128">Foreign</span></span>  <br/> |<span data-ttu-id="7ab92-129">Тип URI этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="7ab92-129">This user's URI type.</span></span> <span data-ttu-id="7ab92-130">Дополнительные сведения см. в таблице [UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="7ab92-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

