---
title: Представление пользователя
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: В представлении пользователя хранятся сведения о пользователях, которые участвовали в звонках или сеансах с записями в базе данных. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 2fe0ba4748a776a8f17065a3c5db21d34bd6340d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295743"
---
# <a name="user-view"></a><span data-ttu-id="5d2f0-104">Представление пользователя</span><span class="sxs-lookup"><span data-stu-id="5d2f0-104">User view</span></span>
 
<span data-ttu-id="5d2f0-105">В представлении пользователя хранятся сведения о пользователях, которые участвовали в звонках или сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="5d2f0-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="5d2f0-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d2f0-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="5d2f0-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5d2f0-107">**Column**</span></span>|<span data-ttu-id="5d2f0-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="5d2f0-108">**Data Type**</span></span>|<span data-ttu-id="5d2f0-109">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="5d2f0-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5d2f0-110">Идентификатора пользователя</span><span class="sxs-lookup"><span data-stu-id="5d2f0-110">UserId</span></span>  <br/> |<span data-ttu-id="5d2f0-111">целое</span><span class="sxs-lookup"><span data-stu-id="5d2f0-111">int</span></span>  <br/> |<span data-ttu-id="5d2f0-112">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d2f0-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="5d2f0-113">Усерури</span><span class="sxs-lookup"><span data-stu-id="5d2f0-113">UserUri</span></span>  <br/> |<span data-ttu-id="5d2f0-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5d2f0-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="5d2f0-115">Универсальный код ресурса (URI) пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d2f0-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="5d2f0-116">Тенанткэй</span><span class="sxs-lookup"><span data-stu-id="5d2f0-116">TenantKey</span></span>  <br/> |<span data-ttu-id="5d2f0-117">идентификатора</span><span class="sxs-lookup"><span data-stu-id="5d2f0-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="5d2f0-118">Клиент пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d2f0-118">Tenant of user.</span></span> <span data-ttu-id="5d2f0-119">Дополнительные сведения см. в [таблице "клиенты](tenants.md) ".</span><span class="sxs-lookup"><span data-stu-id="5d2f0-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="5d2f0-120">Уритипе</span><span class="sxs-lookup"><span data-stu-id="5d2f0-120">UriType</span></span>  <br/> |<span data-ttu-id="5d2f0-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5d2f0-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="5d2f0-122">Тип универсального кода ресурса (URI) пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d2f0-122">Type of user URI.</span></span> <span data-ttu-id="5d2f0-123">Для получения дополнительных сведений ознакомьтесь с [таблицей уритипес](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="5d2f0-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

