---
title: Представление пользователя
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
ms.openlocfilehash: 014b773a60cc053c0ec258c7dd853e31a590319c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="user-view"></a><span data-ttu-id="4f0d4-104">Представление пользователя</span><span class="sxs-lookup"><span data-stu-id="4f0d4-104">User view</span></span>
 
<span data-ttu-id="4f0d4-105">Представление пользователя хранятся сведения о пользователях, которые не связаны звонков или сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4f0d4-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="4f0d4-106">В этом представлении была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f0d4-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="4f0d4-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4f0d4-107">**Column**</span></span>|<span data-ttu-id="4f0d4-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="4f0d4-108">**Data Type**</span></span>|<span data-ttu-id="4f0d4-109">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="4f0d4-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4f0d4-110">Идентификатор пользователя</span><span class="sxs-lookup"><span data-stu-id="4f0d4-110">UserId</span></span>  <br/> |<span data-ttu-id="4f0d4-111">целое</span><span class="sxs-lookup"><span data-stu-id="4f0d4-111">int</span></span>  <br/> |<span data-ttu-id="4f0d4-112">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="4f0d4-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="4f0d4-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="4f0d4-113">UserUri</span></span>  <br/> |<span data-ttu-id="4f0d4-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="4f0d4-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="4f0d4-115">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="4f0d4-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="4f0d4-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="4f0d4-116">TenantKey</span></span>  <br/> |<span data-ttu-id="4f0d4-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="4f0d4-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="4f0d4-118">Клиент пользователя.</span><span class="sxs-lookup"><span data-stu-id="4f0d4-118">Tenant of user.</span></span> <span data-ttu-id="4f0d4-119">В [таблице клиентов](tenants.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="4f0d4-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4f0d4-120">UriType</span><span class="sxs-lookup"><span data-stu-id="4f0d4-120">UriType</span></span>  <br/> |<span data-ttu-id="4f0d4-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4f0d4-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4f0d4-122">Тип URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="4f0d4-122">Type of user URI.</span></span> <span data-ttu-id="4f0d4-123">В [таблице UriTypes](uritypes.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="4f0d4-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

