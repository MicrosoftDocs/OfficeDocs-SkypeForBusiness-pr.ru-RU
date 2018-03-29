---
title: Таблица MonitoredRegionLink
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
ms.openlocfilehash: 471291788dabee412bffef641624afad2a2c10b4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="0fcab-104">Таблица MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="0fcab-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="0fcab-105">Таблица monitoredregionlink представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="0fcab-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="0fcab-106">Каждая запись представляет одну связь между двумя странах или регионах.</span><span class="sxs-lookup"><span data-stu-id="0fcab-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="0fcab-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="0fcab-107">**Column**</span></span>|<span data-ttu-id="0fcab-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="0fcab-108">**Data Type**</span></span>|<span data-ttu-id="0fcab-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="0fcab-109">**Key/Index**</span></span>|<span data-ttu-id="0fcab-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="0fcab-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0fcab-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="0fcab-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="0fcab-112">целое</span><span class="sxs-lookup"><span data-stu-id="0fcab-112">int</span></span>  <br/> |<span data-ttu-id="0fcab-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="0fcab-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="0fcab-114">Ссылка из [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="0fcab-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="0fcab-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="0fcab-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="0fcab-116">целое</span><span class="sxs-lookup"><span data-stu-id="0fcab-116">int</span></span>  <br/> |<span data-ttu-id="0fcab-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="0fcab-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="0fcab-118">Ссылка из [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="0fcab-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

