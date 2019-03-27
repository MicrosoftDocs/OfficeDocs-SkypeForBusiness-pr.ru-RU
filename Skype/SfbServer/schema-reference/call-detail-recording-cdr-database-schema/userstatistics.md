---
title: Таблица userstatistics
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Таблица userstatistics представляет собой вспомогательную таблицу. Каждая запись в таблице хранятся сведения об использовании отдельных пользователей системы. Эта таблица была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 45f34a1e8905d19b5ce48d94824591f25ec1ef28
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883597"
---
# <a name="userstatistics-table"></a><span data-ttu-id="c1436-105">Таблица userstatistics</span><span class="sxs-lookup"><span data-stu-id="c1436-105">UserStatistics table</span></span>
 
<span data-ttu-id="c1436-106">Таблица userstatistics представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="c1436-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="c1436-107">Каждая запись в таблице хранятся сведения об использовании отдельных пользователей системы.</span><span class="sxs-lookup"><span data-stu-id="c1436-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="c1436-108">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1436-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c1436-109">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c1436-109">**Column**</span></span>|<span data-ttu-id="c1436-110">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="c1436-110">**Data Type**</span></span>|<span data-ttu-id="c1436-111">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="c1436-111">**Key/Index**</span></span>|<span data-ttu-id="c1436-112">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="c1436-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c1436-113">**Идентификатор пользователя**</span><span class="sxs-lookup"><span data-stu-id="c1436-113">**UserId**</span></span> <br/> |<span data-ttu-id="c1436-114">целое</span><span class="sxs-lookup"><span data-stu-id="c1436-114">int</span></span>  <br/> |<span data-ttu-id="c1436-115">Primary</span><span class="sxs-lookup"><span data-stu-id="c1436-115">Primary</span></span>  <br/> |<span data-ttu-id="c1436-116">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1436-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="c1436-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="c1436-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="c1436-118">datetime</span><span class="sxs-lookup"><span data-stu-id="c1436-118">datetime</span></span>  <br/> ||<span data-ttu-id="c1436-119">Время последнего пользователя войти в систему.</span><span class="sxs-lookup"><span data-stu-id="c1436-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="c1436-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="c1436-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="c1436-121">datetime</span><span class="sxs-lookup"><span data-stu-id="c1436-121">datetime</span></span>  <br/> ||<span data-ttu-id="c1436-122">Время последней конференции, организованной пользователем.</span><span class="sxs-lookup"><span data-stu-id="c1436-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="c1436-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="c1436-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="c1436-124">datetime</span><span class="sxs-lookup"><span data-stu-id="c1436-124">datetime</span></span>  <br/> ||<span data-ttu-id="c1436-125">Время последнего сбоя вызова был данный пользователь.</span><span class="sxs-lookup"><span data-stu-id="c1436-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="c1436-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="c1436-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="c1436-127">datetime</span><span class="sxs-lookup"><span data-stu-id="c1436-127">datetime</span></span>  <br/> ||<span data-ttu-id="c1436-128">Время последнего пользователя сбоя вызова когда организатором конференции.</span><span class="sxs-lookup"><span data-stu-id="c1436-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

