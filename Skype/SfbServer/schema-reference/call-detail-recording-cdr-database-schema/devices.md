---
title: Таблица Devices в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: В таблице устройств представляет собой вспомогательную таблицу. Каждая запись сохранение информации о одно устройство (стационарный телефон).
ms.openlocfilehash: f770f19fb94bf25bdb4c13e74dc41e05f6674788
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881704"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8d1d6-104">Таблица Devices в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8d1d6-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8d1d6-105">В таблице устройств представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="8d1d6-106">Каждая запись сохранение информации о одно устройство (стационарный телефон).</span><span class="sxs-lookup"><span data-stu-id="8d1d6-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="8d1d6-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8d1d6-107">**Column**</span></span>|<span data-ttu-id="8d1d6-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8d1d6-108">**Data Type**</span></span>|<span data-ttu-id="8d1d6-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="8d1d6-109">**Key/Index**</span></span>|<span data-ttu-id="8d1d6-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="8d1d6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8d1d6-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="8d1d6-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="8d1d6-112">целое</span><span class="sxs-lookup"><span data-stu-id="8d1d6-112">int</span></span>  <br/> |<span data-ttu-id="8d1d6-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8d1d6-113">Primary</span></span>  <br/> |<span data-ttu-id="8d1d6-114">Уникальный номер, идентифицирующий версию оборудования.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="8d1d6-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="8d1d6-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="8d1d6-116">целое</span><span class="sxs-lookup"><span data-stu-id="8d1d6-116">int</span></span>  <br/> |<span data-ttu-id="8d1d6-117">Внешний</span><span class="sxs-lookup"><span data-stu-id="8d1d6-117">Foreign</span></span>  <br/> |<span data-ttu-id="8d1d6-118">Производитель это устройство.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-118">Manufacturer of this device.</span></span> <span data-ttu-id="8d1d6-119">В разделе [Таблица Manufacturers в Скайп для Business Server 2015](manufacturers.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="8d1d6-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="8d1d6-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="8d1d6-121">целое</span><span class="sxs-lookup"><span data-stu-id="8d1d6-121">int</span></span>  <br/> |<span data-ttu-id="8d1d6-122">Внешний</span><span class="sxs-lookup"><span data-stu-id="8d1d6-122">Foreign</span></span>  <br/> |<span data-ttu-id="8d1d6-123">Версия оборудования это устройство.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-123">Hardware version of this device.</span></span> <span data-ttu-id="8d1d6-124">[Таблица hardwareversions в Скайп для Business Server 2015](hardwareversions.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="8d1d6-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="8d1d6-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="8d1d6-126">bigint</span><span class="sxs-lookup"><span data-stu-id="8d1d6-126">bigint</span></span>  <br/> ||<span data-ttu-id="8d1d6-127">MAC-адрес</span><span class="sxs-lookup"><span data-stu-id="8d1d6-127">MAC Address</span></span>  <br/> |
   

