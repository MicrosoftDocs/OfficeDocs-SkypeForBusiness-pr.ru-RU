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
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Таблица Users является вспомогательной таблицей. В каждой записи в таблице хранятся сведения о пользователях, участвующих в звонках или сеансах с записями в базе данных.
ms.openlocfilehash: 0dcc2fda73305be2bbe6a7a5c546dac0b05f8273
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295701"
---
# <a name="users-table"></a><span data-ttu-id="dbdde-104">Таблица User</span><span class="sxs-lookup"><span data-stu-id="dbdde-104">Users table</span></span>
 
<span data-ttu-id="dbdde-105">Таблица Users является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="dbdde-105">The Users table is a supporting table.</span></span> <span data-ttu-id="dbdde-106">В каждой записи в таблице хранятся сведения о пользователях, участвующих в звонках или сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="dbdde-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="dbdde-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="dbdde-107">**Column**</span></span>|<span data-ttu-id="dbdde-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="dbdde-108">**Data Type**</span></span>|<span data-ttu-id="dbdde-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="dbdde-109">**Key/Index**</span></span>|<span data-ttu-id="dbdde-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="dbdde-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dbdde-111">**Некступдатетс**</span><span class="sxs-lookup"><span data-stu-id="dbdde-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="dbdde-112">datetime</span><span class="sxs-lookup"><span data-stu-id="dbdde-112">datetime</span></span>  <br/> ||<span data-ttu-id="dbdde-113">Метка времени для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="dbdde-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="dbdde-114">**Идентификатора пользователя**</span><span class="sxs-lookup"><span data-stu-id="dbdde-114">**UserId**</span></span> <br/> |<span data-ttu-id="dbdde-115">целое</span><span class="sxs-lookup"><span data-stu-id="dbdde-115">int</span></span>  <br/> |<span data-ttu-id="dbdde-116">Primary</span><span class="sxs-lookup"><span data-stu-id="dbdde-116">Primary</span></span>  <br/> |<span data-ttu-id="dbdde-117">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="dbdde-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="dbdde-118">**Усерури**</span><span class="sxs-lookup"><span data-stu-id="dbdde-118">**UserUri**</span></span> <br/> |<span data-ttu-id="dbdde-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="dbdde-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="dbdde-120">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="dbdde-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="dbdde-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="dbdde-121">**TenantId**</span></span> <br/> |<span data-ttu-id="dbdde-122">целое</span><span class="sxs-lookup"><span data-stu-id="dbdde-122">int</span></span>  <br/> |<span data-ttu-id="dbdde-123">Другом</span><span class="sxs-lookup"><span data-stu-id="dbdde-123">Foreign</span></span>  <br/> |<span data-ttu-id="dbdde-124">Идентификатор клиента этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="dbdde-124">This user's Tenant ID.</span></span> <span data-ttu-id="dbdde-125">Дополнительные сведения см. в [таблице "клиенты](tenants.md) ".</span><span class="sxs-lookup"><span data-stu-id="dbdde-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="dbdde-126">**Уритипеид**</span><span class="sxs-lookup"><span data-stu-id="dbdde-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="dbdde-127">целое</span><span class="sxs-lookup"><span data-stu-id="dbdde-127">int</span></span>  <br/> |<span data-ttu-id="dbdde-128">Другом</span><span class="sxs-lookup"><span data-stu-id="dbdde-128">Foreign</span></span>  <br/> |<span data-ttu-id="dbdde-129">Тип универсального кода ресурса (URI) этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="dbdde-129">This user's URI type.</span></span> <span data-ttu-id="dbdde-130">Для получения дополнительных сведений ознакомьтесь с [таблицей уритипес](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="dbdde-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

