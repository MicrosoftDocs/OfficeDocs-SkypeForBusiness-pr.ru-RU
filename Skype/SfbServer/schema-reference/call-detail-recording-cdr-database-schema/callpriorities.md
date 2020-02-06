---
title: Таблица Каллприоритиес в Skype для бизнеса Server 2015
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: Таблица Каллприоритиес — это статическая таблица, в которой хранится список возможных приоритетов звонков, например "экстренная", "срочно" или "Обычная".
ms.openlocfilehash: 57ab4c2b190b14d26a7f8be1791eb70473f1eb3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815447"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4c2c7-103">Таблица Каллприоритиес в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="4c2c7-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4c2c7-104">Таблица Каллприоритиес — это статическая таблица, в которой хранится список возможных приоритетов звонков, например "экстренная", "срочно" или "Обычная".</span><span class="sxs-lookup"><span data-stu-id="4c2c7-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="4c2c7-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4c2c7-105">**Column**</span></span>|<span data-ttu-id="4c2c7-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="4c2c7-106">**Data Type**</span></span>|<span data-ttu-id="4c2c7-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="4c2c7-107">**Key/Index**</span></span>|<span data-ttu-id="4c2c7-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="4c2c7-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4c2c7-109">**приоритид**</span><span class="sxs-lookup"><span data-stu-id="4c2c7-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="4c2c7-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="4c2c7-110">tinyint</span></span>  <br/> |<span data-ttu-id="4c2c7-111">Primary</span><span class="sxs-lookup"><span data-stu-id="4c2c7-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="4c2c7-112">**Priority**</span><span class="sxs-lookup"><span data-stu-id="4c2c7-112">**Priority**</span></span> <br/> |<span data-ttu-id="4c2c7-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4c2c7-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="4c2c7-114">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="4c2c7-114">Allowed values:</span></span> <br/>  <span data-ttu-id="4c2c7-115">0 — неизвестно</span><span class="sxs-lookup"><span data-stu-id="4c2c7-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="4c2c7-116">1-срочный</span><span class="sxs-lookup"><span data-stu-id="4c2c7-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="4c2c7-117">2-обычный</span><span class="sxs-lookup"><span data-stu-id="4c2c7-117">2 - Normal</span></span> <br/>  <span data-ttu-id="4c2c7-118">3-Срочный</span><span class="sxs-lookup"><span data-stu-id="4c2c7-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="4c2c7-119">4-экстренная ситуация</span><span class="sxs-lookup"><span data-stu-id="4c2c7-119">4 - Emergency</span></span> <br/> |
   

