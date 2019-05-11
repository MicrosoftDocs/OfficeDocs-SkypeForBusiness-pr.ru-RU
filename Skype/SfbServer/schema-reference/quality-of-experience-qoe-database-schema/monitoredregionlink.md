---
title: Таблица MonitoredRegionLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Таблица monitoredregionlink представляет собой вспомогательную таблицу. Каждая запись представляет одну связь между двумя странах или регионах.
ms.openlocfilehash: 125f29a25b2ee039649dd47dcc405e208d0cd254
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920154"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="c5878-104">Таблица MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="c5878-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="c5878-105">Таблица monitoredregionlink представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="c5878-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="c5878-106">Каждая запись представляет одну связь между двумя странах или регионах.</span><span class="sxs-lookup"><span data-stu-id="c5878-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="c5878-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c5878-107">**Column**</span></span>|<span data-ttu-id="c5878-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="c5878-108">**Data Type**</span></span>|<span data-ttu-id="c5878-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="c5878-109">**Key/Index**</span></span>|<span data-ttu-id="c5878-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="c5878-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c5878-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="c5878-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="c5878-112">целое</span><span class="sxs-lookup"><span data-stu-id="c5878-112">int</span></span>  <br/> |<span data-ttu-id="c5878-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="c5878-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="c5878-114">Ссылка из [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="c5878-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="c5878-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="c5878-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="c5878-116">целое</span><span class="sxs-lookup"><span data-stu-id="c5878-116">int</span></span>  <br/> |<span data-ttu-id="c5878-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="c5878-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="c5878-118">Ссылка из [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="c5878-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

