---
title: Таблица userstatistics
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Таблица userstatistics представляет собой вспомогательную таблицу. Каждая запись в таблице хранятся сведения об использовании отдельных пользователей системы. Эта таблица была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: c2e0acffa7b75b3c54781e3e4e9a8b033be5e440
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929982"
---
# <a name="userstatistics-table"></a><span data-ttu-id="cbf47-105">Таблица userstatistics</span><span class="sxs-lookup"><span data-stu-id="cbf47-105">UserStatistics table</span></span>
 
<span data-ttu-id="cbf47-106">Таблица userstatistics представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="cbf47-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="cbf47-107">Каждая запись в таблице хранятся сведения об использовании отдельных пользователей системы.</span><span class="sxs-lookup"><span data-stu-id="cbf47-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="cbf47-108">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cbf47-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="cbf47-109">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="cbf47-109">**Column**</span></span>|<span data-ttu-id="cbf47-110">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="cbf47-110">**Data Type**</span></span>|<span data-ttu-id="cbf47-111">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="cbf47-111">**Key/Index**</span></span>|<span data-ttu-id="cbf47-112">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="cbf47-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cbf47-113">**Идентификатор пользователя**</span><span class="sxs-lookup"><span data-stu-id="cbf47-113">**UserId**</span></span> <br/> |<span data-ttu-id="cbf47-114">целое</span><span class="sxs-lookup"><span data-stu-id="cbf47-114">int</span></span>  <br/> |<span data-ttu-id="cbf47-115">Primary</span><span class="sxs-lookup"><span data-stu-id="cbf47-115">Primary</span></span>  <br/> |<span data-ttu-id="cbf47-116">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="cbf47-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="cbf47-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="cbf47-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="cbf47-118">datetime</span><span class="sxs-lookup"><span data-stu-id="cbf47-118">datetime</span></span>  <br/> ||<span data-ttu-id="cbf47-119">Время последнего пользователя войти в систему.</span><span class="sxs-lookup"><span data-stu-id="cbf47-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="cbf47-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="cbf47-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="cbf47-121">datetime</span><span class="sxs-lookup"><span data-stu-id="cbf47-121">datetime</span></span>  <br/> ||<span data-ttu-id="cbf47-122">Время последней конференции, организованной пользователем.</span><span class="sxs-lookup"><span data-stu-id="cbf47-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="cbf47-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="cbf47-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="cbf47-124">datetime</span><span class="sxs-lookup"><span data-stu-id="cbf47-124">datetime</span></span>  <br/> ||<span data-ttu-id="cbf47-125">Время последнего сбоя вызова был данный пользователь.</span><span class="sxs-lookup"><span data-stu-id="cbf47-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="cbf47-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="cbf47-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="cbf47-127">datetime</span><span class="sxs-lookup"><span data-stu-id="cbf47-127">datetime</span></span>  <br/> ||<span data-ttu-id="cbf47-128">Время последнего пользователя сбоя вызова когда организатором конференции.</span><span class="sxs-lookup"><span data-stu-id="cbf47-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

