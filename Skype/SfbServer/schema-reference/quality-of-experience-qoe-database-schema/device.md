---
title: Таблица Device
ms.reviewer: ''
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
ms.openlocfilehash: 09af6ee11ebc821d123e847fbad812479d9d7bb0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212251"
---
# <a name="device-table"></a><span data-ttu-id="34653-104">Таблица Device</span><span class="sxs-lookup"><span data-stu-id="34653-104">Device table</span></span>
 
<span data-ttu-id="34653-105">Таблица Device представляет собой вспомогательную таблицу, в которой хранятся сведения о различных захвата или отображать устройств.</span><span class="sxs-lookup"><span data-stu-id="34653-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="34653-106">Каждая запись в таблице представляет одно устройство.</span><span class="sxs-lookup"><span data-stu-id="34653-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="34653-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="34653-107">**Column**</span></span>|<span data-ttu-id="34653-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="34653-108">**Data Type**</span></span>|<span data-ttu-id="34653-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="34653-109">**Key/Index**</span></span>|<span data-ttu-id="34653-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="34653-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="34653-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="34653-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="34653-112">целое</span><span class="sxs-lookup"><span data-stu-id="34653-112">int</span></span>  <br/> |<span data-ttu-id="34653-113">Primary</span><span class="sxs-lookup"><span data-stu-id="34653-113">Primary</span></span>  <br/> |<span data-ttu-id="34653-114">Уникальный номер, идентифицирующий это устройство.</span><span class="sxs-lookup"><span data-stu-id="34653-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="34653-115">**Значения DeviceName**</span><span class="sxs-lookup"><span data-stu-id="34653-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="34653-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34653-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="34653-117">Значения DeviceName и DeviceType уникальны</span><span class="sxs-lookup"><span data-stu-id="34653-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="34653-118">Имя устройства.</span><span class="sxs-lookup"><span data-stu-id="34653-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="34653-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="34653-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="34653-120">бит</span><span class="sxs-lookup"><span data-stu-id="34653-120">bit</span></span>  <br/> |<span data-ttu-id="34653-121">Значения DeviceName и DeviceType уникальны</span><span class="sxs-lookup"><span data-stu-id="34653-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="34653-122">Тип устройства.</span><span class="sxs-lookup"><span data-stu-id="34653-122">Device type.</span></span> <span data-ttu-id="34653-123">1 — для устройства захвата, 0 — это устройства обработки.</span><span class="sxs-lookup"><span data-stu-id="34653-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

