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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212174"
---
# <a name="pool-table"></a><span data-ttu-id="a6b91-104">Таблица Pool</span><span class="sxs-lookup"><span data-stu-id="a6b91-104">Pool table</span></span>
 
<span data-ttu-id="a6b91-105">Таблица Pool представляет собой вспомогательную таблицу, в которой хранятся сведения о различных пулов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a6b91-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="a6b91-106">Каждая запись в таблице представляет один пул.</span><span class="sxs-lookup"><span data-stu-id="a6b91-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="a6b91-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="a6b91-107">**Column**</span></span>|<span data-ttu-id="a6b91-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="a6b91-108">**Data Type**</span></span>|<span data-ttu-id="a6b91-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="a6b91-109">**Key/Index**</span></span>|<span data-ttu-id="a6b91-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="a6b91-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a6b91-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="a6b91-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="a6b91-112">целое</span><span class="sxs-lookup"><span data-stu-id="a6b91-112">int</span></span>  <br/> |<span data-ttu-id="a6b91-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a6b91-113">Primary</span></span>  <br/> |<span data-ttu-id="a6b91-114">Уникальный номер, идентифицирующий этот пул.</span><span class="sxs-lookup"><span data-stu-id="a6b91-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="a6b91-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="a6b91-115">**PoolName**</span></span> <br/> |<span data-ttu-id="a6b91-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a6b91-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a6b91-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="a6b91-117">Unique</span></span>  <br/> |<span data-ttu-id="a6b91-118">Полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="a6b91-118">Pool FQDN.</span></span>  <br/> |
   

