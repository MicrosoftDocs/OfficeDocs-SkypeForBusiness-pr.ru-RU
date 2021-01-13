---
title: Представление пользователя
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: Представление User хранит информацию о пользователях, участвовавших в звонках или сеансах с записями в базе данных. Это представление впервые было введено в Microsoft Lync Server 2013.
ms.openlocfilehash: 03af849f9185d90d1c7888c1946b47ee2ef38db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831699"
---
# <a name="user-view"></a><span data-ttu-id="9073a-104">Представление пользователя</span><span class="sxs-lookup"><span data-stu-id="9073a-104">User view</span></span>
 
<span data-ttu-id="9073a-105">Представление User хранит информацию о пользователях, участвовавших в звонках или сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="9073a-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="9073a-106">Это представление впервые было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9073a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="9073a-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9073a-107">**Column**</span></span>|<span data-ttu-id="9073a-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="9073a-108">**Data Type**</span></span>|<span data-ttu-id="9073a-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="9073a-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9073a-110">UserId</span><span class="sxs-lookup"><span data-stu-id="9073a-110">UserId</span></span>  <br/> |<span data-ttu-id="9073a-111">int</span><span class="sxs-lookup"><span data-stu-id="9073a-111">int</span></span>  <br/> |<span data-ttu-id="9073a-112">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="9073a-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="9073a-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="9073a-113">UserUri</span></span>  <br/> |<span data-ttu-id="9073a-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="9073a-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="9073a-115">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="9073a-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="9073a-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="9073a-116">TenantKey</span></span>  <br/> |<span data-ttu-id="9073a-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="9073a-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="9073a-118">Клиент пользователя.</span><span class="sxs-lookup"><span data-stu-id="9073a-118">Tenant of user.</span></span> <span data-ttu-id="9073a-119">Дополнительные [сведения см. в](tenants.md) таблице Tenants.</span><span class="sxs-lookup"><span data-stu-id="9073a-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="9073a-120">UriType</span><span class="sxs-lookup"><span data-stu-id="9073a-120">UriType</span></span>  <br/> |<span data-ttu-id="9073a-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9073a-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9073a-122">Тип URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="9073a-122">Type of user URI.</span></span> <span data-ttu-id="9073a-123">Дополнительные сведения см. в таблице [UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="9073a-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

