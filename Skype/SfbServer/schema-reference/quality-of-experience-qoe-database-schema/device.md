---
title: Таблица Device
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Таблица Device представляет собой вспомогательную таблицу, в которой хранятся сведения о различных захвата или отображать устройств. Каждая запись в таблице представляет одно устройство.
ms.openlocfilehash: 346ea171b9a0c1b7a874b65a68b582c4167c57fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="device-table"></a><span data-ttu-id="66e5d-104">Таблица Device</span><span class="sxs-lookup"><span data-stu-id="66e5d-104">Device table</span></span>
 
<span data-ttu-id="66e5d-105">Таблица Device представляет собой вспомогательную таблицу, в которой хранятся сведения о различных захвата или отображать устройств.</span><span class="sxs-lookup"><span data-stu-id="66e5d-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="66e5d-106">Каждая запись в таблице представляет одно устройство.</span><span class="sxs-lookup"><span data-stu-id="66e5d-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="66e5d-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="66e5d-107">**Column**</span></span>|<span data-ttu-id="66e5d-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="66e5d-108">**Data Type**</span></span>|<span data-ttu-id="66e5d-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="66e5d-109">**Key/Index**</span></span>|<span data-ttu-id="66e5d-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="66e5d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="66e5d-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="66e5d-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="66e5d-112">целое</span><span class="sxs-lookup"><span data-stu-id="66e5d-112">int</span></span>  <br/> |<span data-ttu-id="66e5d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="66e5d-113">Primary</span></span>  <br/> |<span data-ttu-id="66e5d-114">Уникальный номер, идентифицирующий это устройство.</span><span class="sxs-lookup"><span data-stu-id="66e5d-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="66e5d-115">**Значения DeviceName**</span><span class="sxs-lookup"><span data-stu-id="66e5d-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="66e5d-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="66e5d-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="66e5d-117">Значения DeviceName и DeviceType уникальны</span><span class="sxs-lookup"><span data-stu-id="66e5d-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="66e5d-118">Имя устройства.</span><span class="sxs-lookup"><span data-stu-id="66e5d-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="66e5d-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="66e5d-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="66e5d-120">бит</span><span class="sxs-lookup"><span data-stu-id="66e5d-120">bit</span></span>  <br/> |<span data-ttu-id="66e5d-121">Значения DeviceName и DeviceType уникальны</span><span class="sxs-lookup"><span data-stu-id="66e5d-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="66e5d-122">Тип устройства.</span><span class="sxs-lookup"><span data-stu-id="66e5d-122">Device type.</span></span> <span data-ttu-id="66e5d-123">1 — для устройства захвата, 0 — это устройства обработки.</span><span class="sxs-lookup"><span data-stu-id="66e5d-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

