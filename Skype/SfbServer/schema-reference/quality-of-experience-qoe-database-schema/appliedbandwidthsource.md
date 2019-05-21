---
title: Таблица AppliedBandwidthSource
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: Таблица Апплиедбандвидссаурце является вспомогательной таблицей. Каждая запись представляет один источник.
ms.openlocfilehash: 6d40701b74dd5e7312a504127675eed686de7321
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295113"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="47603-104">Таблица AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="47603-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="47603-105">Таблица Апплиедбандвидссаурце является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="47603-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="47603-106">Каждая запись представляет один источник.</span><span class="sxs-lookup"><span data-stu-id="47603-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="47603-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="47603-107">**Column**</span></span>|<span data-ttu-id="47603-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="47603-108">**Data Type**</span></span>|<span data-ttu-id="47603-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="47603-109">**Key/Index**</span></span>|<span data-ttu-id="47603-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="47603-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="47603-111">**Апплиедбандвидссаурцекэй**</span><span class="sxs-lookup"><span data-stu-id="47603-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="47603-112">целое</span><span class="sxs-lookup"><span data-stu-id="47603-112">int</span></span>  <br/> |<span data-ttu-id="47603-113">Primary</span><span class="sxs-lookup"><span data-stu-id="47603-113">Primary</span></span>  <br/> |<span data-ttu-id="47603-114">Уникальный номер, идентифицирующий источник.</span><span class="sxs-lookup"><span data-stu-id="47603-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="47603-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="47603-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="47603-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="47603-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="47603-117">Повторя</span><span class="sxs-lookup"><span data-stu-id="47603-117">Unique</span></span>  <br/> |<span data-ttu-id="47603-118">Это источник установленного места для пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="47603-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="47603-119">Она описывает, откуда поступают ограничения пропускной способности (например, "сервер политики", "превратить сервер" или "модальность").</span><span class="sxs-lookup"><span data-stu-id="47603-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

