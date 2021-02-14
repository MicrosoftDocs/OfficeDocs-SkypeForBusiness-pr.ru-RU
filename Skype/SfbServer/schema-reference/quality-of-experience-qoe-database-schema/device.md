---
title: Таблица Device
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Таблица "Устройство" представляет собой вспомогательную таблицу, в которой хранятся сведения о различных устройствах записи и отображения. Каждому устройству соответствует одна запись в таблице.
ms.openlocfilehash: 818458e41c71398f3df11ac9a47eeee0841c6dca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814749"
---
# <a name="device-table"></a><span data-ttu-id="8d872-104">Таблица Device</span><span class="sxs-lookup"><span data-stu-id="8d872-104">Device table</span></span>
 
<span data-ttu-id="8d872-p102">Таблица "Устройство" представляет собой вспомогательную таблицу, в которой хранятся сведения о различных устройствах записи и отображения. Каждому устройству соответствует одна запись в таблице.</span><span class="sxs-lookup"><span data-stu-id="8d872-p102">The Device table is a supporting table that stores information about the various capture or render devices. Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="8d872-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8d872-107">**Column**</span></span>|<span data-ttu-id="8d872-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8d872-108">**Data Type**</span></span>|<span data-ttu-id="8d872-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="8d872-109">**Key/Index**</span></span>|<span data-ttu-id="8d872-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="8d872-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8d872-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="8d872-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="8d872-112">int</span><span class="sxs-lookup"><span data-stu-id="8d872-112">int</span></span>  <br/> |<span data-ttu-id="8d872-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8d872-113">Primary</span></span>  <br/> |<span data-ttu-id="8d872-114">Уникальный номер, идентифицирующий это устройство.</span><span class="sxs-lookup"><span data-stu-id="8d872-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="8d872-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="8d872-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="8d872-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8d872-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8d872-117">Значения DeviceName и DeviceType уникальны</span><span class="sxs-lookup"><span data-stu-id="8d872-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="8d872-118">Имя устройства.</span><span class="sxs-lookup"><span data-stu-id="8d872-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="8d872-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="8d872-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="8d872-120">bit</span><span class="sxs-lookup"><span data-stu-id="8d872-120">bit</span></span>  <br/> |<span data-ttu-id="8d872-121">Значения DeviceName и DeviceType уникальны</span><span class="sxs-lookup"><span data-stu-id="8d872-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="8d872-p103">Тип устройства. 1 - устройство записи, 0 - устройство отображения.</span><span class="sxs-lookup"><span data-stu-id="8d872-p103">Device type. 1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

