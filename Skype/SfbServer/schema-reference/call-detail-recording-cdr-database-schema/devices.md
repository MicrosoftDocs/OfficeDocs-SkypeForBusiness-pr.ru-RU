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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Таблица "устройства" является вспомогательной таблицей. Каждая запись хранит информацию об одном устройстве (стационарном телефоне).
ms.openlocfilehash: e53a8947d106d6a92d7cf5cb881f20022e1bac69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815287"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="56a86-104">Таблица "устройства" в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="56a86-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="56a86-105">Таблица "устройства" является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="56a86-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="56a86-106">Каждая запись хранит информацию об одном устройстве (стационарном телефоне).</span><span class="sxs-lookup"><span data-stu-id="56a86-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="56a86-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="56a86-107">**Column**</span></span>|<span data-ttu-id="56a86-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="56a86-108">**Data Type**</span></span>|<span data-ttu-id="56a86-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="56a86-109">**Key/Index**</span></span>|<span data-ttu-id="56a86-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="56a86-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="56a86-111">**Устройства**</span><span class="sxs-lookup"><span data-stu-id="56a86-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="56a86-112">целое</span><span class="sxs-lookup"><span data-stu-id="56a86-112">int</span></span>  <br/> |<span data-ttu-id="56a86-113">Primary</span><span class="sxs-lookup"><span data-stu-id="56a86-113">Primary</span></span>  <br/> |<span data-ttu-id="56a86-114">Уникальный номер, идентифицирующий эту аппаратную версию.</span><span class="sxs-lookup"><span data-stu-id="56a86-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="56a86-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="56a86-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="56a86-116">целое</span><span class="sxs-lookup"><span data-stu-id="56a86-116">int</span></span>  <br/> |<span data-ttu-id="56a86-117">Другом</span><span class="sxs-lookup"><span data-stu-id="56a86-117">Foreign</span></span>  <br/> |<span data-ttu-id="56a86-118">Производитель этого устройства.</span><span class="sxs-lookup"><span data-stu-id="56a86-118">Manufacturer of this device.</span></span> <span data-ttu-id="56a86-119">Более подробную информацию вы увидите [в таблице изготовителей в Skype для бизнеса Server 2015](manufacturers.md) .</span><span class="sxs-lookup"><span data-stu-id="56a86-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="56a86-120">**хардвареверсионид**</span><span class="sxs-lookup"><span data-stu-id="56a86-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="56a86-121">целое</span><span class="sxs-lookup"><span data-stu-id="56a86-121">int</span></span>  <br/> |<span data-ttu-id="56a86-122">Другом</span><span class="sxs-lookup"><span data-stu-id="56a86-122">Foreign</span></span>  <br/> |<span data-ttu-id="56a86-123">Аппаратная версия этого устройства.</span><span class="sxs-lookup"><span data-stu-id="56a86-123">Hardware version of this device.</span></span> <span data-ttu-id="56a86-124">Для получения дополнительных сведений ознакомьтесь с [таблицей хардвареверсионс в Skype для бизнеса Server 2015](hardwareversions.md) .</span><span class="sxs-lookup"><span data-stu-id="56a86-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="56a86-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="56a86-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="56a86-126">bigint</span><span class="sxs-lookup"><span data-stu-id="56a86-126">bigint</span></span>  <br/> ||<span data-ttu-id="56a86-127">MAC-адрес</span><span class="sxs-lookup"><span data-stu-id="56a86-127">MAC Address</span></span>  <br/> |
   

