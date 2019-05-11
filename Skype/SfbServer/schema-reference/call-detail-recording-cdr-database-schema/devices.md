---
title: Таблица Devices в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: В таблице устройств представляет собой вспомогательную таблицу. Каждая запись сохранение информации о одно устройство (стационарный телефон).
ms.openlocfilehash: efd0894a36e02948a3a8cd9f3465dcdbd30f3e2d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901096"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="00eea-104">Таблица Devices в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="00eea-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="00eea-105">В таблице устройств представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="00eea-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="00eea-106">Каждая запись сохранение информации о одно устройство (стационарный телефон).</span><span class="sxs-lookup"><span data-stu-id="00eea-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="00eea-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="00eea-107">**Column**</span></span>|<span data-ttu-id="00eea-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="00eea-108">**Data Type**</span></span>|<span data-ttu-id="00eea-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="00eea-109">**Key/Index**</span></span>|<span data-ttu-id="00eea-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="00eea-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="00eea-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="00eea-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="00eea-112">целое</span><span class="sxs-lookup"><span data-stu-id="00eea-112">int</span></span>  <br/> |<span data-ttu-id="00eea-113">Primary</span><span class="sxs-lookup"><span data-stu-id="00eea-113">Primary</span></span>  <br/> |<span data-ttu-id="00eea-114">Уникальный номер, идентифицирующий версию оборудования.</span><span class="sxs-lookup"><span data-stu-id="00eea-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="00eea-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="00eea-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="00eea-116">целое</span><span class="sxs-lookup"><span data-stu-id="00eea-116">int</span></span>  <br/> |<span data-ttu-id="00eea-117">Внешний</span><span class="sxs-lookup"><span data-stu-id="00eea-117">Foreign</span></span>  <br/> |<span data-ttu-id="00eea-118">Производитель это устройство.</span><span class="sxs-lookup"><span data-stu-id="00eea-118">Manufacturer of this device.</span></span> <span data-ttu-id="00eea-119">В разделе [Таблица Manufacturers в Скайп для Business Server 2015](manufacturers.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="00eea-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="00eea-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="00eea-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="00eea-121">целое</span><span class="sxs-lookup"><span data-stu-id="00eea-121">int</span></span>  <br/> |<span data-ttu-id="00eea-122">Внешний</span><span class="sxs-lookup"><span data-stu-id="00eea-122">Foreign</span></span>  <br/> |<span data-ttu-id="00eea-123">Версия оборудования это устройство.</span><span class="sxs-lookup"><span data-stu-id="00eea-123">Hardware version of this device.</span></span> <span data-ttu-id="00eea-124">[Таблица hardwareversions в Скайп для Business Server 2015](hardwareversions.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="00eea-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="00eea-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="00eea-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="00eea-126">bigint</span><span class="sxs-lookup"><span data-stu-id="00eea-126">bigint</span></span>  <br/> ||<span data-ttu-id="00eea-127">MAC-адрес</span><span class="sxs-lookup"><span data-stu-id="00eea-127">MAC Address</span></span>  <br/> |
   

