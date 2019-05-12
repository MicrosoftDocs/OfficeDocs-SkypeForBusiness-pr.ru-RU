---
title: Представление пользователя
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: Представление пользователя хранятся сведения о пользователях, которые не связаны звонков или сеансах с записями в базе данных. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: f4e255f2de8dd087308ee46c64ef301cc0e9d390
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930080"
---
# <a name="user-view"></a><span data-ttu-id="ec536-104">Представление пользователя</span><span class="sxs-lookup"><span data-stu-id="ec536-104">User view</span></span>
 
<span data-ttu-id="ec536-105">Представление пользователя хранятся сведения о пользователях, которые не связаны звонков или сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ec536-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="ec536-106">В этом представлении была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ec536-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="ec536-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ec536-107">**Column**</span></span>|<span data-ttu-id="ec536-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ec536-108">**Data Type**</span></span>|<span data-ttu-id="ec536-109">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="ec536-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ec536-110">Идентификатор пользователя</span><span class="sxs-lookup"><span data-stu-id="ec536-110">UserId</span></span>  <br/> |<span data-ttu-id="ec536-111">целое</span><span class="sxs-lookup"><span data-stu-id="ec536-111">int</span></span>  <br/> |<span data-ttu-id="ec536-112">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="ec536-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="ec536-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="ec536-113">UserUri</span></span>  <br/> |<span data-ttu-id="ec536-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="ec536-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ec536-115">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="ec536-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="ec536-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="ec536-116">TenantKey</span></span>  <br/> |<span data-ttu-id="ec536-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="ec536-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="ec536-118">Клиент пользователя.</span><span class="sxs-lookup"><span data-stu-id="ec536-118">Tenant of user.</span></span> <span data-ttu-id="ec536-119">В [таблице клиентов](tenants.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="ec536-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ec536-120">UriType</span><span class="sxs-lookup"><span data-stu-id="ec536-120">UriType</span></span>  <br/> |<span data-ttu-id="ec536-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ec536-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ec536-122">Тип URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="ec536-122">Type of user URI.</span></span> <span data-ttu-id="ec536-123">В [таблице UriTypes](uritypes.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="ec536-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

