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
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: Таблица Каллприоритиес — это статическая таблица, в которой хранится список возможных приоритетов звонков, например "экстренная", "срочно" или "Обычная".
ms.openlocfilehash: 6d324ce11b2e149378b6275441cb4a2467a641db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296569"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c766e-103">Таблица Каллприоритиес в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c766e-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c766e-104">Таблица Каллприоритиес — это статическая таблица, в которой хранится список возможных приоритетов звонков, например "экстренная", "срочно" или "Обычная".</span><span class="sxs-lookup"><span data-stu-id="c766e-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="c766e-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c766e-105">**Column**</span></span>|<span data-ttu-id="c766e-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="c766e-106">**Data Type**</span></span>|<span data-ttu-id="c766e-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="c766e-107">**Key/Index**</span></span>|<span data-ttu-id="c766e-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="c766e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c766e-109">**Приоритид**</span><span class="sxs-lookup"><span data-stu-id="c766e-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="c766e-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="c766e-110">tinyint</span></span>  <br/> |<span data-ttu-id="c766e-111">Primary</span><span class="sxs-lookup"><span data-stu-id="c766e-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="c766e-112">**Priority**</span><span class="sxs-lookup"><span data-stu-id="c766e-112">**Priority**</span></span> <br/> |<span data-ttu-id="c766e-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c766e-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="c766e-114">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="c766e-114">Allowed values:</span></span> <br/>  <span data-ttu-id="c766e-115">0 — неизвестно</span><span class="sxs-lookup"><span data-stu-id="c766e-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="c766e-116">1-срочный</span><span class="sxs-lookup"><span data-stu-id="c766e-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="c766e-117">2-обычный</span><span class="sxs-lookup"><span data-stu-id="c766e-117">2 - Normal</span></span> <br/>  <span data-ttu-id="c766e-118">3-Срочный</span><span class="sxs-lookup"><span data-stu-id="c766e-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="c766e-119">4-экстренная ситуация</span><span class="sxs-lookup"><span data-stu-id="c766e-119">4 - Emergency</span></span> <br/> |
   

