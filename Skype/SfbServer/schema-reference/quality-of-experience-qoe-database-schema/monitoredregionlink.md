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
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Таблица Мониторедрегионлинк является вспомогательной таблицей. Каждая запись представляет одну связь между двумя странами и областями.
ms.openlocfilehash: fdace97e0a7c9685f59471074cca64ede4fcc63d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294875"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="79bc7-104">Таблица MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="79bc7-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="79bc7-105">Таблица Мониторедрегионлинк является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="79bc7-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="79bc7-106">Каждая запись представляет одну связь между двумя странами и областями.</span><span class="sxs-lookup"><span data-stu-id="79bc7-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="79bc7-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="79bc7-107">**Column**</span></span>|<span data-ttu-id="79bc7-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="79bc7-108">**Data Type**</span></span>|<span data-ttu-id="79bc7-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="79bc7-109">**Key/Index**</span></span>|<span data-ttu-id="79bc7-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="79bc7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="79bc7-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="79bc7-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="79bc7-112">целое</span><span class="sxs-lookup"><span data-stu-id="79bc7-112">int</span></span>  <br/> |<span data-ttu-id="79bc7-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="79bc7-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="79bc7-114">На которую ссылается [Таблица "регион](region.md)".</span><span class="sxs-lookup"><span data-stu-id="79bc7-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="79bc7-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="79bc7-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="79bc7-116">целое</span><span class="sxs-lookup"><span data-stu-id="79bc7-116">int</span></span>  <br/> |<span data-ttu-id="79bc7-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="79bc7-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="79bc7-118">На которую ссылается [Таблица "регион](region.md)".</span><span class="sxs-lookup"><span data-stu-id="79bc7-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

