---
title: Таблица DeviceDriver
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
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: Таблица DeviceDriver является вспомогательной. Каждая запись представляет драйвер, используемый устройством захвата или отображения.
ms.openlocfilehash: 1f83bfd014fa5fb49f4d0f900e01aeecfe2b5f46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823079"
---
# <a name="devicedriver-table"></a><span data-ttu-id="fe8cc-104">Таблица DeviceDriver</span><span class="sxs-lookup"><span data-stu-id="fe8cc-104">DeviceDriver table</span></span>
 
<span data-ttu-id="fe8cc-p102">Таблица DeviceDriver является вспомогательной. Каждая запись представляет драйвер, используемый устройством захвата или отображения.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-p102">The DeviceDriver table is a supporting table. Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="fe8cc-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="fe8cc-107">**Column**</span></span>|<span data-ttu-id="fe8cc-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fe8cc-108">**Data Type**</span></span>|<span data-ttu-id="fe8cc-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="fe8cc-109">**Key/Index**</span></span>|<span data-ttu-id="fe8cc-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="fe8cc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fe8cc-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="fe8cc-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="fe8cc-112">int</span><span class="sxs-lookup"><span data-stu-id="fe8cc-112">int</span></span>  <br/> |<span data-ttu-id="fe8cc-113">Primary</span><span class="sxs-lookup"><span data-stu-id="fe8cc-113">Primary</span></span>  <br/> |<span data-ttu-id="fe8cc-114">Уникальный номер, идентифицирующий эту запись драйвера устройства.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="fe8cc-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="fe8cc-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="fe8cc-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="fe8cc-117">unique</span><span class="sxs-lookup"><span data-stu-id="fe8cc-117">unique</span></span>  <br/> |<span data-ttu-id="fe8cc-118">Имя драйвера устройства.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-118">Device driver name.</span></span>  <br/> |
   

