---
title: Таблица CallPriorities в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: Таблица CallPriorities — это статическая таблица, в которой хранится список возможных приоритетов вызовов, такие как «emergency», «срочно» или «normal».
ms.openlocfilehash: faf4e7f04d7a63b096cb2369c21916e5fcb71a24
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213335"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3667e-103">Таблица CallPriorities в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3667e-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3667e-104">Таблица CallPriorities — это статическая таблица, в которой хранится список возможных приоритетов вызовов, такие как «emergency», «срочно» или «normal».</span><span class="sxs-lookup"><span data-stu-id="3667e-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="3667e-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="3667e-105">**Column**</span></span>|<span data-ttu-id="3667e-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3667e-106">**Data Type**</span></span>|<span data-ttu-id="3667e-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="3667e-107">**Key/Index**</span></span>|<span data-ttu-id="3667e-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="3667e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3667e-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="3667e-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="3667e-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="3667e-110">tinyint</span></span>  <br/> |<span data-ttu-id="3667e-111">Primary</span><span class="sxs-lookup"><span data-stu-id="3667e-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="3667e-112">**Priority**</span><span class="sxs-lookup"><span data-stu-id="3667e-112">**Priority**</span></span> <br/> |<span data-ttu-id="3667e-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3667e-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="3667e-114">Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="3667e-114">Allowed values:</span></span> <br/>  <span data-ttu-id="3667e-115">0 — Неизвестный</span><span class="sxs-lookup"><span data-stu-id="3667e-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="3667e-116">1 — не срочный</span><span class="sxs-lookup"><span data-stu-id="3667e-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="3667e-117">2 — Normal</span><span class="sxs-lookup"><span data-stu-id="3667e-117">2 - Normal</span></span> <br/>  <span data-ttu-id="3667e-118">3 - срочным</span><span class="sxs-lookup"><span data-stu-id="3667e-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="3667e-119">4 - аварийного</span><span class="sxs-lookup"><span data-stu-id="3667e-119">4 - Emergency</span></span> <br/> |
   

