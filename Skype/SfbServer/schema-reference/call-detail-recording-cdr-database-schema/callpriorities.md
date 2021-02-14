---
title: Таблица CallPriorities в Skype для бизнеса Server 2015
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: Таблица CallPriorities — это статическая таблица, в которую хранится список возможных приоритетов вызовов, таких как "экстренный", "срочный" или "обычный".
ms.openlocfilehash: 54fdd70dcd939cfeb227862d6152577c4c91d3b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813439"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ae103-103">Таблица CallPriorities в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="ae103-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ae103-104">Таблица CallPriorities — это статическая таблица, в которую хранится список возможных приоритетов вызовов, таких как "экстренный", "срочный" или "обычный".</span><span class="sxs-lookup"><span data-stu-id="ae103-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="ae103-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ae103-105">**Column**</span></span>|<span data-ttu-id="ae103-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ae103-106">**Data Type**</span></span>|<span data-ttu-id="ae103-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="ae103-107">**Key/Index**</span></span>|<span data-ttu-id="ae103-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="ae103-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ae103-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="ae103-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="ae103-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="ae103-110">tinyint</span></span>  <br/> |<span data-ttu-id="ae103-111">Primary</span><span class="sxs-lookup"><span data-stu-id="ae103-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="ae103-112">**Priority**</span><span class="sxs-lookup"><span data-stu-id="ae103-112">**Priority**</span></span> <br/> |<span data-ttu-id="ae103-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ae103-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="ae103-114">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="ae103-114">Allowed values:</span></span> <br/>  <span data-ttu-id="ae103-115">0 — неизвестно</span><span class="sxs-lookup"><span data-stu-id="ae103-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="ae103-116">1 — несрочные</span><span class="sxs-lookup"><span data-stu-id="ae103-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="ae103-117">2 — обычный</span><span class="sxs-lookup"><span data-stu-id="ae103-117">2 - Normal</span></span> <br/>  <span data-ttu-id="ae103-118">3 — срочный</span><span class="sxs-lookup"><span data-stu-id="ae103-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="ae103-119">4 — экстренный</span><span class="sxs-lookup"><span data-stu-id="ae103-119">4 - Emergency</span></span> <br/> |
   

