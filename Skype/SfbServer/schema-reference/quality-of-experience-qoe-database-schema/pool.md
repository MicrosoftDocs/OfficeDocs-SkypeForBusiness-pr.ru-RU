---
title: Таблица Pool
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Таблица Pool представляет собой вспомогательную таблицу, в которой хранятся сведения о различных пулов переднего плана. Каждая запись в таблице представляет один пул.
ms.openlocfilehash: 8ce54d4b0a20fa405f34bb14b3eecb9ad395884e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="pool-table"></a><span data-ttu-id="e514c-104">Таблица Pool</span><span class="sxs-lookup"><span data-stu-id="e514c-104">Pool table</span></span>
 
<span data-ttu-id="e514c-105">Таблица Pool представляет собой вспомогательную таблицу, в которой хранятся сведения о различных пулов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="e514c-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="e514c-106">Каждая запись в таблице представляет один пул.</span><span class="sxs-lookup"><span data-stu-id="e514c-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="e514c-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e514c-107">**Column**</span></span>|<span data-ttu-id="e514c-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="e514c-108">**Data Type**</span></span>|<span data-ttu-id="e514c-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="e514c-109">**Key/Index**</span></span>|<span data-ttu-id="e514c-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="e514c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e514c-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="e514c-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="e514c-112">целое</span><span class="sxs-lookup"><span data-stu-id="e514c-112">int</span></span>  <br/> |<span data-ttu-id="e514c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e514c-113">Primary</span></span>  <br/> |<span data-ttu-id="e514c-114">Уникальный номер, идентифицирующий этот пул.</span><span class="sxs-lookup"><span data-stu-id="e514c-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="e514c-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="e514c-115">**PoolName**</span></span> <br/> |<span data-ttu-id="e514c-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e514c-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e514c-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="e514c-117">Unique</span></span>  <br/> |<span data-ttu-id="e514c-118">Полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="e514c-118">Pool FQDN.</span></span>  <br/> |
   

