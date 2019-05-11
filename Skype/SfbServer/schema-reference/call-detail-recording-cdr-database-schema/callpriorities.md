---
title: Таблица CallPriorities в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: Таблица CallPriorities — это статическая таблица, в которой хранится список возможных приоритетов вызовов, такие как «emergency», «срочно» или «normal».
ms.openlocfilehash: aac21073e98d7c1ef8d137a736445b62e4fb9878
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901531"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="79af7-103">Таблица CallPriorities в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="79af7-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="79af7-104">Таблица CallPriorities — это статическая таблица, в которой хранится список возможных приоритетов вызовов, такие как «emergency», «срочно» или «normal».</span><span class="sxs-lookup"><span data-stu-id="79af7-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="79af7-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="79af7-105">**Column**</span></span>|<span data-ttu-id="79af7-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="79af7-106">**Data Type**</span></span>|<span data-ttu-id="79af7-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="79af7-107">**Key/Index**</span></span>|<span data-ttu-id="79af7-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="79af7-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="79af7-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="79af7-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="79af7-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="79af7-110">tinyint</span></span>  <br/> |<span data-ttu-id="79af7-111">Primary</span><span class="sxs-lookup"><span data-stu-id="79af7-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="79af7-112">**Priority**</span><span class="sxs-lookup"><span data-stu-id="79af7-112">**Priority**</span></span> <br/> |<span data-ttu-id="79af7-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="79af7-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="79af7-114">Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="79af7-114">Allowed values:</span></span> <br/>  <span data-ttu-id="79af7-115">0 — Неизвестный</span><span class="sxs-lookup"><span data-stu-id="79af7-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="79af7-116">1 — не срочный</span><span class="sxs-lookup"><span data-stu-id="79af7-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="79af7-117">2 — Normal</span><span class="sxs-lookup"><span data-stu-id="79af7-117">2 - Normal</span></span> <br/>  <span data-ttu-id="79af7-118">3 - срочным</span><span class="sxs-lookup"><span data-stu-id="79af7-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="79af7-119">4 - аварийного</span><span class="sxs-lookup"><span data-stu-id="79af7-119">4 - Emergency</span></span> <br/> |
   

