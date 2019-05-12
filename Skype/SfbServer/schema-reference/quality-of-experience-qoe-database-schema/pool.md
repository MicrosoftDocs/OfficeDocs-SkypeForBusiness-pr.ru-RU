---
title: Таблица Pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Таблица Pool представляет собой вспомогательную таблицу, в которой хранятся сведения о различных пулов переднего плана. Каждая запись в таблице представляет один пул.
ms.openlocfilehash: c4451f274e9afadbb7903e4095be22120c430689
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920065"
---
# <a name="pool-table"></a><span data-ttu-id="a0304-104">Таблица Pool</span><span class="sxs-lookup"><span data-stu-id="a0304-104">Pool table</span></span>
 
<span data-ttu-id="a0304-105">Таблица Pool представляет собой вспомогательную таблицу, в которой хранятся сведения о различных пулов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a0304-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="a0304-106">Каждая запись в таблице представляет один пул.</span><span class="sxs-lookup"><span data-stu-id="a0304-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="a0304-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="a0304-107">**Column**</span></span>|<span data-ttu-id="a0304-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="a0304-108">**Data Type**</span></span>|<span data-ttu-id="a0304-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="a0304-109">**Key/Index**</span></span>|<span data-ttu-id="a0304-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="a0304-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a0304-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="a0304-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="a0304-112">целое</span><span class="sxs-lookup"><span data-stu-id="a0304-112">int</span></span>  <br/> |<span data-ttu-id="a0304-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a0304-113">Primary</span></span>  <br/> |<span data-ttu-id="a0304-114">Уникальный номер, идентифицирующий этот пул.</span><span class="sxs-lookup"><span data-stu-id="a0304-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="a0304-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="a0304-115">**PoolName**</span></span> <br/> |<span data-ttu-id="a0304-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a0304-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a0304-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="a0304-117">Unique</span></span>  <br/> |<span data-ttu-id="a0304-118">Полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="a0304-118">Pool FQDN.</span></span>  <br/> |
   

