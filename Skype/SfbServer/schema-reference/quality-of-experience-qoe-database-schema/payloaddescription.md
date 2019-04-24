---
title: Таблица PayloadDescription
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: Таблица PayloadDescription представляет собой вспомогательную таблицу. Каждая запись представляет один кодек, который используется в сеансе аудио или видео.
ms.openlocfilehash: 320542593479e3051992e8079abfdf9f54b0efc0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212188"
---
# <a name="payloaddescription-table"></a><span data-ttu-id="d860f-104">Таблица PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="d860f-104">PayloadDescription table</span></span>
 
<span data-ttu-id="d860f-105">Таблица PayloadDescription представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="d860f-105">The PayloadDescription table is a supporting table.</span></span> <span data-ttu-id="d860f-106">Каждая запись представляет один кодек, который используется в сеансе аудио или видео.</span><span class="sxs-lookup"><span data-stu-id="d860f-106">Each record represents one Codec, which is used in an audio or video session.</span></span>
  
|<span data-ttu-id="d860f-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d860f-107">**Column**</span></span>|<span data-ttu-id="d860f-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d860f-108">**Data Type**</span></span>|<span data-ttu-id="d860f-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="d860f-109">**Key/Index**</span></span>|<span data-ttu-id="d860f-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="d860f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d860f-111">**PayloadDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="d860f-111">**PayloadDescriptionKey**</span></span> <br/> |<span data-ttu-id="d860f-112">целое</span><span class="sxs-lookup"><span data-stu-id="d860f-112">int</span></span>  <br/> |<span data-ttu-id="d860f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d860f-113">Primary</span></span>  <br/> |<span data-ttu-id="d860f-114">Уникальный номер, обозначающий кодек.</span><span class="sxs-lookup"><span data-stu-id="d860f-114">Unique number identifying the Codec.</span></span>  <br/> |
|<span data-ttu-id="d860f-115">**PayloadDescription**</span><span class="sxs-lookup"><span data-stu-id="d860f-115">**PayloadDescription**</span></span> <br/> |<span data-ttu-id="d860f-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d860f-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d860f-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="d860f-117">Unique</span></span>  <br/> |<span data-ttu-id="d860f-118">Имя кодека.</span><span class="sxs-lookup"><span data-stu-id="d860f-118">Codec name.</span></span>  <br/> |
   

