---
title: Таблица DeviceDriver
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: Таблица DeviceDriver представляет собой вспомогательную таблицу. Каждая запись представляет драйвера устройства захвата или устройства обработки.
ms.openlocfilehash: 9a011c7e555bad71f453510dca7c310e2467a505
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920175"
---
# <a name="devicedriver-table"></a><span data-ttu-id="08d70-104">Таблица DeviceDriver</span><span class="sxs-lookup"><span data-stu-id="08d70-104">DeviceDriver table</span></span>
 
<span data-ttu-id="08d70-105">Таблица DeviceDriver представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="08d70-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="08d70-106">Каждая запись представляет драйвера устройства захвата или устройства обработки.</span><span class="sxs-lookup"><span data-stu-id="08d70-106">Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="08d70-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="08d70-107">**Column**</span></span>|<span data-ttu-id="08d70-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="08d70-108">**Data Type**</span></span>|<span data-ttu-id="08d70-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="08d70-109">**Key/Index**</span></span>|<span data-ttu-id="08d70-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="08d70-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="08d70-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="08d70-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="08d70-112">целое</span><span class="sxs-lookup"><span data-stu-id="08d70-112">int</span></span>  <br/> |<span data-ttu-id="08d70-113">Primary</span><span class="sxs-lookup"><span data-stu-id="08d70-113">Primary</span></span>  <br/> |<span data-ttu-id="08d70-114">Уникальный номер, идентифицирующий эту запись драйвера устройства.</span><span class="sxs-lookup"><span data-stu-id="08d70-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="08d70-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="08d70-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="08d70-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="08d70-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="08d70-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="08d70-117">unique</span></span>  <br/> |<span data-ttu-id="08d70-118">Имя драйвера для устройства.</span><span class="sxs-lookup"><span data-stu-id="08d70-118">Device driver name.</span></span>  <br/> |
   

