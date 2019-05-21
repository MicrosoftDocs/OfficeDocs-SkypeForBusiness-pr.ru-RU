---
title: Таблица Pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Таблица Pool — это вспомогательная таблица, в которой хранятся сведения о различных пулах интерфейсов переднего плана. Каждая запись в таблице представляет один пул.
ms.openlocfilehash: c101a10d40292c89c29e108739195a97fa22e5c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294805"
---
# <a name="pool-table"></a><span data-ttu-id="b279a-104">Таблица Pool</span><span class="sxs-lookup"><span data-stu-id="b279a-104">Pool table</span></span>
 
<span data-ttu-id="b279a-105">Таблица Pool — это вспомогательная таблица, в которой хранятся сведения о различных пулах интерфейсов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b279a-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="b279a-106">Каждая запись в таблице представляет один пул.</span><span class="sxs-lookup"><span data-stu-id="b279a-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="b279a-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="b279a-107">**Column**</span></span>|<span data-ttu-id="b279a-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="b279a-108">**Data Type**</span></span>|<span data-ttu-id="b279a-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="b279a-109">**Key/Index**</span></span>|<span data-ttu-id="b279a-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="b279a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b279a-111">**Пулкэй**</span><span class="sxs-lookup"><span data-stu-id="b279a-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="b279a-112">целое</span><span class="sxs-lookup"><span data-stu-id="b279a-112">int</span></span>  <br/> |<span data-ttu-id="b279a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b279a-113">Primary</span></span>  <br/> |<span data-ttu-id="b279a-114">Уникальный номер, идентифицирующий этот пул.</span><span class="sxs-lookup"><span data-stu-id="b279a-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="b279a-115">**Пулнаме**</span><span class="sxs-lookup"><span data-stu-id="b279a-115">**PoolName**</span></span> <br/> |<span data-ttu-id="b279a-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b279a-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b279a-117">Повторя</span><span class="sxs-lookup"><span data-stu-id="b279a-117">Unique</span></span>  <br/> |<span data-ttu-id="b279a-118">Полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="b279a-118">Pool FQDN.</span></span>  <br/> |
   

