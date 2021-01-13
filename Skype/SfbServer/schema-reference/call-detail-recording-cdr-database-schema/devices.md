---
title: Таблица Devices в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Таблица устройств является вспомогательной. В каждой записи хранится информация об одном устройстве (стационарный телефон).
ms.openlocfilehash: da0d6ea8143fb8c81225e885fba1f05a90e2fda5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831819"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c36bc-104">Таблица Devices в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c36bc-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c36bc-105">Таблица устройств является вспомогательной.</span><span class="sxs-lookup"><span data-stu-id="c36bc-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="c36bc-106">В каждой записи хранится информация об одном устройстве (стационарный телефон).</span><span class="sxs-lookup"><span data-stu-id="c36bc-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="c36bc-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c36bc-107">**Column**</span></span>|<span data-ttu-id="c36bc-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="c36bc-108">**Data Type**</span></span>|<span data-ttu-id="c36bc-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="c36bc-109">**Key/Index**</span></span>|<span data-ttu-id="c36bc-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="c36bc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c36bc-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="c36bc-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="c36bc-112">int</span><span class="sxs-lookup"><span data-stu-id="c36bc-112">int</span></span>  <br/> |<span data-ttu-id="c36bc-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c36bc-113">Primary</span></span>  <br/> |<span data-ttu-id="c36bc-114">Уникальный номер, идентифицирующий версию оборудования.</span><span class="sxs-lookup"><span data-stu-id="c36bc-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="c36bc-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="c36bc-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="c36bc-116">int</span><span class="sxs-lookup"><span data-stu-id="c36bc-116">int</span></span>  <br/> |<span data-ttu-id="c36bc-117">Внешняя</span><span class="sxs-lookup"><span data-stu-id="c36bc-117">Foreign</span></span>  <br/> |<span data-ttu-id="c36bc-118">Производитель этого устройства.</span><span class="sxs-lookup"><span data-stu-id="c36bc-118">Manufacturer of this device.</span></span> <span data-ttu-id="c36bc-119">Дополнительные сведения см. в таблице [Manufacturers в Skype для бизнеса Server 2015.](manufacturers.md)</span><span class="sxs-lookup"><span data-stu-id="c36bc-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c36bc-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="c36bc-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="c36bc-121">int</span><span class="sxs-lookup"><span data-stu-id="c36bc-121">int</span></span>  <br/> |<span data-ttu-id="c36bc-122">Внешняя</span><span class="sxs-lookup"><span data-stu-id="c36bc-122">Foreign</span></span>  <br/> |<span data-ttu-id="c36bc-123">Версия оборудования этого устройства.</span><span class="sxs-lookup"><span data-stu-id="c36bc-123">Hardware version of this device.</span></span> <span data-ttu-id="c36bc-124">Дополнительные сведения см. в таблице [HardwareVersions в Skype для бизнеса Server 2015.](hardwareversions.md)</span><span class="sxs-lookup"><span data-stu-id="c36bc-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c36bc-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="c36bc-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="c36bc-126">bigint</span><span class="sxs-lookup"><span data-stu-id="c36bc-126">bigint</span></span>  <br/> ||<span data-ttu-id="c36bc-127">MAC-адрес</span><span class="sxs-lookup"><span data-stu-id="c36bc-127">MAC Address</span></span>  <br/> |
   

