---
title: Таблица User
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Таблица Users является вспомогательной таблицей. В каждой записи в таблице хранятся сведения о пользователях, участвующих в звонках или сеансах с записями в базе данных.
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814807"
---
# <a name="users-table"></a><span data-ttu-id="d4992-104">Таблица User</span><span class="sxs-lookup"><span data-stu-id="d4992-104">Users table</span></span>
 
<span data-ttu-id="d4992-105">Таблица Users является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="d4992-105">The Users table is a supporting table.</span></span> <span data-ttu-id="d4992-106">В каждой записи в таблице хранятся сведения о пользователях, участвующих в звонках или сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d4992-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="d4992-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d4992-107">**Column**</span></span>|<span data-ttu-id="d4992-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d4992-108">**Data Type**</span></span>|<span data-ttu-id="d4992-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="d4992-109">**Key/Index**</span></span>|<span data-ttu-id="d4992-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="d4992-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d4992-111">**некступдатетс**</span><span class="sxs-lookup"><span data-stu-id="d4992-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d4992-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d4992-112">datetime</span></span>  <br/> ||<span data-ttu-id="d4992-113">Метка времени для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d4992-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="d4992-114">**Идентификатора пользователя**</span><span class="sxs-lookup"><span data-stu-id="d4992-114">**UserId**</span></span> <br/> |<span data-ttu-id="d4992-115">целое</span><span class="sxs-lookup"><span data-stu-id="d4992-115">int</span></span>  <br/> |<span data-ttu-id="d4992-116">Primary</span><span class="sxs-lookup"><span data-stu-id="d4992-116">Primary</span></span>  <br/> |<span data-ttu-id="d4992-117">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="d4992-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="d4992-118">**усерури**</span><span class="sxs-lookup"><span data-stu-id="d4992-118">**UserUri**</span></span> <br/> |<span data-ttu-id="d4992-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d4992-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="d4992-120">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="d4992-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="d4992-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="d4992-121">**TenantId**</span></span> <br/> |<span data-ttu-id="d4992-122">целое</span><span class="sxs-lookup"><span data-stu-id="d4992-122">int</span></span>  <br/> |<span data-ttu-id="d4992-123">Другом</span><span class="sxs-lookup"><span data-stu-id="d4992-123">Foreign</span></span>  <br/> |<span data-ttu-id="d4992-124">Идентификатор клиента этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="d4992-124">This user's Tenant ID.</span></span> <span data-ttu-id="d4992-125">Дополнительные сведения см. в [таблице "клиенты](tenants.md) ".</span><span class="sxs-lookup"><span data-stu-id="d4992-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d4992-126">**уритипеид**</span><span class="sxs-lookup"><span data-stu-id="d4992-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="d4992-127">целое</span><span class="sxs-lookup"><span data-stu-id="d4992-127">int</span></span>  <br/> |<span data-ttu-id="d4992-128">Другом</span><span class="sxs-lookup"><span data-stu-id="d4992-128">Foreign</span></span>  <br/> |<span data-ttu-id="d4992-129">Тип универсального кода ресурса (URI) этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="d4992-129">This user's URI type.</span></span> <span data-ttu-id="d4992-130">Для получения дополнительных сведений ознакомьтесь с [таблицей уритипес](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="d4992-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

