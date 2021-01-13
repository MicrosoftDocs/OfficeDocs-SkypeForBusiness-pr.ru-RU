---
title: Таблица UserStatistics
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Таблица UserStatistics предназначена для поддержки. В каждой записи таблицы хранится информация об использовании системы отдельным пользователем. Эта таблица была представлена в Microsoft Lync Server 2013.
ms.openlocfilehash: 65017c9f807b272097b39bac88c80cc81e617ff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813109"
---
# <a name="userstatistics-table"></a><span data-ttu-id="1f0ab-105">Таблица UserStatistics</span><span class="sxs-lookup"><span data-stu-id="1f0ab-105">UserStatistics table</span></span>
 
<span data-ttu-id="1f0ab-106">Таблица UserStatistics предназначена для поддержки.</span><span class="sxs-lookup"><span data-stu-id="1f0ab-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="1f0ab-107">В каждой записи таблицы хранится информация об использовании системы отдельным пользователем.</span><span class="sxs-lookup"><span data-stu-id="1f0ab-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="1f0ab-108">Эта таблица была представлена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1f0ab-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="1f0ab-109">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="1f0ab-109">**Column**</span></span>|<span data-ttu-id="1f0ab-110">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1f0ab-110">**Data Type**</span></span>|<span data-ttu-id="1f0ab-111">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="1f0ab-111">**Key/Index**</span></span>|<span data-ttu-id="1f0ab-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="1f0ab-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1f0ab-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="1f0ab-113">**UserId**</span></span> <br/> |<span data-ttu-id="1f0ab-114">int</span><span class="sxs-lookup"><span data-stu-id="1f0ab-114">int</span></span>  <br/> |<span data-ttu-id="1f0ab-115">Primary</span><span class="sxs-lookup"><span data-stu-id="1f0ab-115">Primary</span></span>  <br/> |<span data-ttu-id="1f0ab-116">Уникальный номер, идентифицирующий данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="1f0ab-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="1f0ab-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="1f0ab-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="1f0ab-118">datetime</span><span class="sxs-lookup"><span data-stu-id="1f0ab-118">datetime</span></span>  <br/> ||<span data-ttu-id="1f0ab-119">Время последнего входа пользователя в систему.</span><span class="sxs-lookup"><span data-stu-id="1f0ab-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="1f0ab-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="1f0ab-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="1f0ab-121">datetime</span><span class="sxs-lookup"><span data-stu-id="1f0ab-121">datetime</span></span>  <br/> ||<span data-ttu-id="1f0ab-122">Время последней конференции, организованной пользователем.</span><span class="sxs-lookup"><span data-stu-id="1f0ab-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="1f0ab-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="1f0ab-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="1f0ab-124">datetime</span><span class="sxs-lookup"><span data-stu-id="1f0ab-124">datetime</span></span>  <br/> ||<span data-ttu-id="1f0ab-125">Время последнего сбоя вызова пользователя.</span><span class="sxs-lookup"><span data-stu-id="1f0ab-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="1f0ab-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="1f0ab-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="1f0ab-127">datetime</span><span class="sxs-lookup"><span data-stu-id="1f0ab-127">datetime</span></span>  <br/> ||<span data-ttu-id="1f0ab-128">Время последнего сбоя вызова, когда организатором конференции был данный пользователь.</span><span class="sxs-lookup"><span data-stu-id="1f0ab-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

