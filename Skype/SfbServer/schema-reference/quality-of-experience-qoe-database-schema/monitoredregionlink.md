---
title: Таблица MonitoredRegionLink
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Таблица monitoredregionlink представляет собой вспомогательную таблицу. Каждая запись представляет одну связь между двумя странах или регионах.
ms.openlocfilehash: 0df5cd8abe957ed952bdf656a67e1d423cc57f33
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884416"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="4ae01-104">Таблица MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="4ae01-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="4ae01-105">Таблица monitoredregionlink представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="4ae01-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="4ae01-106">Каждая запись представляет одну связь между двумя странах или регионах.</span><span class="sxs-lookup"><span data-stu-id="4ae01-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="4ae01-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4ae01-107">**Column**</span></span>|<span data-ttu-id="4ae01-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="4ae01-108">**Data Type**</span></span>|<span data-ttu-id="4ae01-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="4ae01-109">**Key/Index**</span></span>|<span data-ttu-id="4ae01-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="4ae01-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4ae01-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="4ae01-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="4ae01-112">целое</span><span class="sxs-lookup"><span data-stu-id="4ae01-112">int</span></span>  <br/> |<span data-ttu-id="4ae01-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="4ae01-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="4ae01-114">Ссылка из [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="4ae01-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="4ae01-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="4ae01-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="4ae01-116">целое</span><span class="sxs-lookup"><span data-stu-id="4ae01-116">int</span></span>  <br/> |<span data-ttu-id="4ae01-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="4ae01-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="4ae01-118">Ссылка из [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="4ae01-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

