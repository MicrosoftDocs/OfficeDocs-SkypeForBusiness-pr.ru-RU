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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213181"
---
# <a name="user-view"></a><span data-ttu-id="b683b-104">Представление пользователя</span><span class="sxs-lookup"><span data-stu-id="b683b-104">User view</span></span>
 
<span data-ttu-id="b683b-105">Представление пользователя хранятся сведения о пользователях, которые не связаны звонков или сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="b683b-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="b683b-106">В этом представлении была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b683b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b683b-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="b683b-107">**Column**</span></span>|<span data-ttu-id="b683b-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="b683b-108">**Data Type**</span></span>|<span data-ttu-id="b683b-109">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="b683b-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b683b-110">Идентификатор пользователя</span><span class="sxs-lookup"><span data-stu-id="b683b-110">UserId</span></span>  <br/> |<span data-ttu-id="b683b-111">целое</span><span class="sxs-lookup"><span data-stu-id="b683b-111">int</span></span>  <br/> |<span data-ttu-id="b683b-112">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="b683b-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="b683b-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="b683b-113">UserUri</span></span>  <br/> |<span data-ttu-id="b683b-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="b683b-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="b683b-115">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="b683b-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="b683b-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="b683b-116">TenantKey</span></span>  <br/> |<span data-ttu-id="b683b-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="b683b-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="b683b-118">Клиент пользователя.</span><span class="sxs-lookup"><span data-stu-id="b683b-118">Tenant of user.</span></span> <span data-ttu-id="b683b-119">В [таблице клиентов](tenants.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="b683b-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b683b-120">UriType</span><span class="sxs-lookup"><span data-stu-id="b683b-120">UriType</span></span>  <br/> |<span data-ttu-id="b683b-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b683b-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b683b-122">Тип URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="b683b-122">Type of user URI.</span></span> <span data-ttu-id="b683b-123">В [таблице UriTypes](uritypes.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="b683b-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

