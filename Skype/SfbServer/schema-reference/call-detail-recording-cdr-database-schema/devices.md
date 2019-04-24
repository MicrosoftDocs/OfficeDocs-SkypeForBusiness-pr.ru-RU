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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213167"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4b2b3-104">Таблица Devices в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4b2b3-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4b2b3-105">В таблице устройств представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="4b2b3-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="4b2b3-106">Каждая запись сохранение информации о одно устройство (стационарный телефон).</span><span class="sxs-lookup"><span data-stu-id="4b2b3-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="4b2b3-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4b2b3-107">**Column**</span></span>|<span data-ttu-id="4b2b3-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="4b2b3-108">**Data Type**</span></span>|<span data-ttu-id="4b2b3-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="4b2b3-109">**Key/Index**</span></span>|<span data-ttu-id="4b2b3-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="4b2b3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4b2b3-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="4b2b3-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="4b2b3-112">целое</span><span class="sxs-lookup"><span data-stu-id="4b2b3-112">int</span></span>  <br/> |<span data-ttu-id="4b2b3-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4b2b3-113">Primary</span></span>  <br/> |<span data-ttu-id="4b2b3-114">Уникальный номер, идентифицирующий версию оборудования.</span><span class="sxs-lookup"><span data-stu-id="4b2b3-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="4b2b3-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="4b2b3-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="4b2b3-116">целое</span><span class="sxs-lookup"><span data-stu-id="4b2b3-116">int</span></span>  <br/> |<span data-ttu-id="4b2b3-117">Внешний</span><span class="sxs-lookup"><span data-stu-id="4b2b3-117">Foreign</span></span>  <br/> |<span data-ttu-id="4b2b3-118">Производитель это устройство.</span><span class="sxs-lookup"><span data-stu-id="4b2b3-118">Manufacturer of this device.</span></span> <span data-ttu-id="4b2b3-119">В разделе [Таблица Manufacturers в Скайп для Business Server 2015](manufacturers.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="4b2b3-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4b2b3-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="4b2b3-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="4b2b3-121">целое</span><span class="sxs-lookup"><span data-stu-id="4b2b3-121">int</span></span>  <br/> |<span data-ttu-id="4b2b3-122">Внешний</span><span class="sxs-lookup"><span data-stu-id="4b2b3-122">Foreign</span></span>  <br/> |<span data-ttu-id="4b2b3-123">Версия оборудования это устройство.</span><span class="sxs-lookup"><span data-stu-id="4b2b3-123">Hardware version of this device.</span></span> <span data-ttu-id="4b2b3-124">[Таблица hardwareversions в Скайп для Business Server 2015](hardwareversions.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="4b2b3-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4b2b3-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="4b2b3-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="4b2b3-126">bigint</span><span class="sxs-lookup"><span data-stu-id="4b2b3-126">bigint</span></span>  <br/> ||<span data-ttu-id="4b2b3-127">MAC-адрес</span><span class="sxs-lookup"><span data-stu-id="4b2b3-127">MAC Address</span></span>  <br/> |
   

