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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: В представлении пользователя хранятся сведения о пользователях, которые участвовали в звонках или сеансах с записями в базе данных. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 1d170b558dbf77cd8ebeff09a914826830d5621d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814837"
---
# <a name="user-view"></a><span data-ttu-id="e03d6-104">Представление пользователя</span><span class="sxs-lookup"><span data-stu-id="e03d6-104">User view</span></span>
 
<span data-ttu-id="e03d6-105">В представлении пользователя хранятся сведения о пользователях, которые участвовали в звонках или сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e03d6-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="e03d6-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e03d6-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="e03d6-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e03d6-107">**Column**</span></span>|<span data-ttu-id="e03d6-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="e03d6-108">**Data Type**</span></span>|<span data-ttu-id="e03d6-109">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="e03d6-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e03d6-110">Идентификатора пользователя</span><span class="sxs-lookup"><span data-stu-id="e03d6-110">UserId</span></span>  <br/> |<span data-ttu-id="e03d6-111">целое</span><span class="sxs-lookup"><span data-stu-id="e03d6-111">int</span></span>  <br/> |<span data-ttu-id="e03d6-112">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="e03d6-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="e03d6-113">усерури</span><span class="sxs-lookup"><span data-stu-id="e03d6-113">UserUri</span></span>  <br/> |<span data-ttu-id="e03d6-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e03d6-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="e03d6-115">Универсальный код ресурса (URI) пользователя.</span><span class="sxs-lookup"><span data-stu-id="e03d6-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="e03d6-116">тенанткэй</span><span class="sxs-lookup"><span data-stu-id="e03d6-116">TenantKey</span></span>  <br/> |<span data-ttu-id="e03d6-117">идентификатора</span><span class="sxs-lookup"><span data-stu-id="e03d6-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="e03d6-118">Клиент пользователя.</span><span class="sxs-lookup"><span data-stu-id="e03d6-118">Tenant of user.</span></span> <span data-ttu-id="e03d6-119">Дополнительные сведения см. в [таблице "клиенты](tenants.md) ".</span><span class="sxs-lookup"><span data-stu-id="e03d6-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e03d6-120">уритипе</span><span class="sxs-lookup"><span data-stu-id="e03d6-120">UriType</span></span>  <br/> |<span data-ttu-id="e03d6-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e03d6-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e03d6-122">Тип универсального кода ресурса (URI) пользователя.</span><span class="sxs-lookup"><span data-stu-id="e03d6-122">Type of user URI.</span></span> <span data-ttu-id="e03d6-123">Для получения дополнительных сведений ознакомьтесь с [таблицей уритипес](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="e03d6-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

