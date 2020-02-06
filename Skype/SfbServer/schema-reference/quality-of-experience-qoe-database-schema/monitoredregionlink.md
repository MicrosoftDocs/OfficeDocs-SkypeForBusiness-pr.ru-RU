---
title: Таблица MonitoredRegionLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Таблица Мониторедрегионлинк является вспомогательной таблицей. Каждая запись представляет одну связь между двумя странами и областями.
ms.openlocfilehash: a6b92460e2b097460681023f7d6877f02c046bdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807817"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="bd05b-104">Таблица MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="bd05b-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="bd05b-105">Таблица Мониторедрегионлинк является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="bd05b-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="bd05b-106">Каждая запись представляет одну связь между двумя странами и областями.</span><span class="sxs-lookup"><span data-stu-id="bd05b-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="bd05b-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="bd05b-107">**Column**</span></span>|<span data-ttu-id="bd05b-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="bd05b-108">**Data Type**</span></span>|<span data-ttu-id="bd05b-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="bd05b-109">**Key/Index**</span></span>|<span data-ttu-id="bd05b-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="bd05b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd05b-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="bd05b-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="bd05b-112">целое</span><span class="sxs-lookup"><span data-stu-id="bd05b-112">int</span></span>  <br/> |<span data-ttu-id="bd05b-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="bd05b-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="bd05b-114">На которую ссылается [Таблица "регион](region.md)".</span><span class="sxs-lookup"><span data-stu-id="bd05b-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="bd05b-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="bd05b-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="bd05b-116">целое</span><span class="sxs-lookup"><span data-stu-id="bd05b-116">int</span></span>  <br/> |<span data-ttu-id="bd05b-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="bd05b-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="bd05b-118">На которую ссылается [Таблица "регион](region.md)".</span><span class="sxs-lookup"><span data-stu-id="bd05b-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

