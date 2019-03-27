---
title: Таблица Pool
ms.reviewer: ''
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
ms.openlocfilehash: ae8695316bdea6ba858bf9a4d334dc6075b99d50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874020"
---
# <a name="pool-table"></a><span data-ttu-id="84f0d-104">Таблица Pool</span><span class="sxs-lookup"><span data-stu-id="84f0d-104">Pool table</span></span>
 
<span data-ttu-id="84f0d-105">Таблица Pool представляет собой вспомогательную таблицу, в которой хранятся сведения о различных пулов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="84f0d-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="84f0d-106">Каждая запись в таблице представляет один пул.</span><span class="sxs-lookup"><span data-stu-id="84f0d-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="84f0d-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="84f0d-107">**Column**</span></span>|<span data-ttu-id="84f0d-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="84f0d-108">**Data Type**</span></span>|<span data-ttu-id="84f0d-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="84f0d-109">**Key/Index**</span></span>|<span data-ttu-id="84f0d-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="84f0d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="84f0d-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="84f0d-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="84f0d-112">целое</span><span class="sxs-lookup"><span data-stu-id="84f0d-112">int</span></span>  <br/> |<span data-ttu-id="84f0d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="84f0d-113">Primary</span></span>  <br/> |<span data-ttu-id="84f0d-114">Уникальный номер, идентифицирующий этот пул.</span><span class="sxs-lookup"><span data-stu-id="84f0d-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="84f0d-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="84f0d-115">**PoolName**</span></span> <br/> |<span data-ttu-id="84f0d-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="84f0d-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="84f0d-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="84f0d-117">Unique</span></span>  <br/> |<span data-ttu-id="84f0d-118">Полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="84f0d-118">Pool FQDN.</span></span>  <br/> |
   

