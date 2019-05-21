---
title: Таблица "устройства" в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Таблица "устройства" является вспомогательной таблицей. Каждая запись хранит информацию об одном устройстве (стационарном телефоне).
ms.openlocfilehash: 145637b6385677007efa47cd21b3f0ea7d7f88f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296380"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3bbb5-104">Таблица "устройства" в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="3bbb5-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3bbb5-105">Таблица "устройства" является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="3bbb5-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="3bbb5-106">Каждая запись хранит информацию об одном устройстве (стационарном телефоне).</span><span class="sxs-lookup"><span data-stu-id="3bbb5-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="3bbb5-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="3bbb5-107">**Column**</span></span>|<span data-ttu-id="3bbb5-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3bbb5-108">**Data Type**</span></span>|<span data-ttu-id="3bbb5-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="3bbb5-109">**Key/Index**</span></span>|<span data-ttu-id="3bbb5-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="3bbb5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3bbb5-111">**Устройства**</span><span class="sxs-lookup"><span data-stu-id="3bbb5-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="3bbb5-112">целое</span><span class="sxs-lookup"><span data-stu-id="3bbb5-112">int</span></span>  <br/> |<span data-ttu-id="3bbb5-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3bbb5-113">Primary</span></span>  <br/> |<span data-ttu-id="3bbb5-114">Уникальный номер, идентифицирующий эту аппаратную версию.</span><span class="sxs-lookup"><span data-stu-id="3bbb5-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="3bbb5-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="3bbb5-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="3bbb5-116">целое</span><span class="sxs-lookup"><span data-stu-id="3bbb5-116">int</span></span>  <br/> |<span data-ttu-id="3bbb5-117">Другом</span><span class="sxs-lookup"><span data-stu-id="3bbb5-117">Foreign</span></span>  <br/> |<span data-ttu-id="3bbb5-118">Производитель этого устройства.</span><span class="sxs-lookup"><span data-stu-id="3bbb5-118">Manufacturer of this device.</span></span> <span data-ttu-id="3bbb5-119">Более подробную информацию вы увидите [в таблице изготовителей в Skype для бизнеса Server 2015](manufacturers.md) .</span><span class="sxs-lookup"><span data-stu-id="3bbb5-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3bbb5-120">**Хардвареверсионид**</span><span class="sxs-lookup"><span data-stu-id="3bbb5-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="3bbb5-121">целое</span><span class="sxs-lookup"><span data-stu-id="3bbb5-121">int</span></span>  <br/> |<span data-ttu-id="3bbb5-122">Другом</span><span class="sxs-lookup"><span data-stu-id="3bbb5-122">Foreign</span></span>  <br/> |<span data-ttu-id="3bbb5-123">Аппаратная версия этого устройства.</span><span class="sxs-lookup"><span data-stu-id="3bbb5-123">Hardware version of this device.</span></span> <span data-ttu-id="3bbb5-124">Для получения дополнительных сведений ознакомьтесь с [таблицей хардвареверсионс в Skype для бизнеса Server 2015](hardwareversions.md) .</span><span class="sxs-lookup"><span data-stu-id="3bbb5-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3bbb5-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="3bbb5-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="3bbb5-126">bigint</span><span class="sxs-lookup"><span data-stu-id="3bbb5-126">bigint</span></span>  <br/> ||<span data-ttu-id="3bbb5-127">MAC-адрес</span><span class="sxs-lookup"><span data-stu-id="3bbb5-127">MAC Address</span></span>  <br/> |
   

