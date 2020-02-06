---
title: Таблица Device
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Таблица Device является вспомогательной таблицей, в которой хранятся сведения о различных устройствах захвата или рендеринге. Каждая запись в таблице представляет одно устройство.
ms.openlocfilehash: 93e6b2215fa1e20b930d678c45f10e26feffd351
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810157"
---
# <a name="device-table"></a><span data-ttu-id="16330-104">Таблица Device</span><span class="sxs-lookup"><span data-stu-id="16330-104">Device table</span></span>
 
<span data-ttu-id="16330-105">Таблица Device является вспомогательной таблицей, в которой хранятся сведения о различных устройствах захвата или рендеринге.</span><span class="sxs-lookup"><span data-stu-id="16330-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="16330-106">Каждая запись в таблице представляет одно устройство.</span><span class="sxs-lookup"><span data-stu-id="16330-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="16330-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="16330-107">**Column**</span></span>|<span data-ttu-id="16330-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="16330-108">**Data Type**</span></span>|<span data-ttu-id="16330-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="16330-109">**Key/Index**</span></span>|<span data-ttu-id="16330-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="16330-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="16330-111">**девицекэй**</span><span class="sxs-lookup"><span data-stu-id="16330-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="16330-112">целое</span><span class="sxs-lookup"><span data-stu-id="16330-112">int</span></span>  <br/> |<span data-ttu-id="16330-113">Primary</span><span class="sxs-lookup"><span data-stu-id="16330-113">Primary</span></span>  <br/> |<span data-ttu-id="16330-114">Уникальный номер, идентифицирующий это устройство.</span><span class="sxs-lookup"><span data-stu-id="16330-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="16330-115">**Водит**</span><span class="sxs-lookup"><span data-stu-id="16330-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="16330-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="16330-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="16330-117">Имя_устройства + DeviceType является уникальным</span><span class="sxs-lookup"><span data-stu-id="16330-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="16330-118">Имя устройства.</span><span class="sxs-lookup"><span data-stu-id="16330-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="16330-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="16330-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="16330-120">бит</span><span class="sxs-lookup"><span data-stu-id="16330-120">bit</span></span>  <br/> |<span data-ttu-id="16330-121">Имя_устройства + DeviceType является уникальным</span><span class="sxs-lookup"><span data-stu-id="16330-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="16330-122">Тип устройства.</span><span class="sxs-lookup"><span data-stu-id="16330-122">Device type.</span></span> <span data-ttu-id="16330-123">1 — устройство захвата, 0 — устройство рендеринга.</span><span class="sxs-lookup"><span data-stu-id="16330-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

