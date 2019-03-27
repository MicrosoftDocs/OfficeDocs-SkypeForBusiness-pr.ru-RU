---
title: Представление пользователя
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: Представление пользователя хранятся сведения о пользователях, которые не связаны звонков или сеансах с записями в базе данных. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 9e631c101660e8f14bca25f019f5d991a0d9aadd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877645"
---
# <a name="user-view"></a><span data-ttu-id="fab0d-104">Представление пользователя</span><span class="sxs-lookup"><span data-stu-id="fab0d-104">User view</span></span>
 
<span data-ttu-id="fab0d-105">Представление пользователя хранятся сведения о пользователях, которые не связаны звонков или сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="fab0d-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="fab0d-106">В этом представлении была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fab0d-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="fab0d-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="fab0d-107">**Column**</span></span>|<span data-ttu-id="fab0d-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fab0d-108">**Data Type**</span></span>|<span data-ttu-id="fab0d-109">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="fab0d-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fab0d-110">Идентификатор пользователя</span><span class="sxs-lookup"><span data-stu-id="fab0d-110">UserId</span></span>  <br/> |<span data-ttu-id="fab0d-111">целое</span><span class="sxs-lookup"><span data-stu-id="fab0d-111">int</span></span>  <br/> |<span data-ttu-id="fab0d-112">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="fab0d-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="fab0d-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="fab0d-113">UserUri</span></span>  <br/> |<span data-ttu-id="fab0d-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="fab0d-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="fab0d-115">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="fab0d-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="fab0d-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="fab0d-116">TenantKey</span></span>  <br/> |<span data-ttu-id="fab0d-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="fab0d-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="fab0d-118">Клиент пользователя.</span><span class="sxs-lookup"><span data-stu-id="fab0d-118">Tenant of user.</span></span> <span data-ttu-id="fab0d-119">В [таблице клиентов](tenants.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="fab0d-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="fab0d-120">UriType</span><span class="sxs-lookup"><span data-stu-id="fab0d-120">UriType</span></span>  <br/> |<span data-ttu-id="fab0d-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fab0d-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="fab0d-122">Тип URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="fab0d-122">Type of user URI.</span></span> <span data-ttu-id="fab0d-123">В [таблице UriTypes](uritypes.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="fab0d-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

